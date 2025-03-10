local player = game.Players.LocalPlayer 
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = game.CoreGui

-- Create Open Button
local openButton = Instance.new("TextButton")
openButton.Size = UDim2.new(0, 50, 0, 50)
openButton.Position = UDim2.new(0, 10, 0, 10)
openButton.BackgroundTransparency = 0.5
openButton.Text = "😏"
openButton.Parent = screenGui

-- Apply UI Styling
local function applyUIStyling(gui)
    local uiCorner = Instance.new("UICorner")
    uiCorner.CornerRadius = UDim.new(0, 8)
    uiCorner.Parent = gui

    local uiStroke = Instance.new("UIStroke")
    uiStroke.Thickness = 1
    uiStroke.Color = Color3.fromRGB(150, 150, 150)
    uiStroke.Parent = gui
end

applyUIStyling(openButton)

-- Create Main GUI
local mainGui = Instance.new("Frame")
mainGui.Size = UDim2.new(0, 200, 0, 120)
mainGui.Position = UDim2.new(0.5, -100, 0.5, -60)
mainGui.BackgroundTransparency = 0.5
mainGui.Visible = false
mainGui.Parent = screenGui

applyUIStyling(mainGui)

-- Draggability
local dragging, dragInput, dragStart, startPos
local function update(input)
    local delta = input.Position - dragStart
    mainGui.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
end

mainGui.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        dragging = true
        dragStart = input.Position
        startPos = mainGui.Position

        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                dragging = false
            end
        end)
    end
end)

mainGui.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement then
        dragInput = input
    end
end)

game:GetService("UserInputService").InputChanged:Connect(function(input)
    if input == dragInput and dragging then
        update(input)
    end
end)

-- Create Label
local titleLabel = Instance.new("TextLabel")
titleLabel.Size = UDim2.new(1, 0, 0, 30)
titleLabel.Text = "Hitbox made by Lucksad"
titleLabel.BackgroundTransparency = 1
titleLabel.TextScaled = true
titleLabel.TextColor3 = Color3.new(1, 1, 1)
titleLabel.Parent = mainGui

-- Create Expand Hitbox Button
local expandButton = Instance.new("TextButton")
expandButton.Size = UDim2.new(0.8, 0, 0, 40)
expandButton.Position = UDim2.new(0.1, 0, 0.5, -20)
expandButton.Text = "Expand Hitbox"
expandButton.BackgroundTransparency = 0.5
expandButton.Parent = mainGui

applyUIStyling(expandButton)

-- Hitbox Expansion Logic
_G.HeadSize = 20
_G.Disabled = true

game:GetService('RunService').RenderStepped:Connect(function()
    if not _G.Disabled then
        for _, v in pairs(game:GetService('Players'):GetPlayers()) do
            if v ~= player then -- Ignore the player using the script
                pcall(function()
                    local rootPart = v.Character and v.Character:FindFirstChild("HumanoidRootPart")
                    if rootPart then
                        rootPart.Size = Vector3.new(_G.HeadSize, _G.HeadSize, _G.HeadSize)
                        rootPart.Transparency = 0.7
                        rootPart.BrickColor = BrickColor.new("Really blue")
                        rootPart.Material = Enum.Material.Neon
                        rootPart.CanCollide = false
                    end
                end)
            end
        end
    end
end)

-- Toggle Hitbox Expansion
expandButton.MouseButton1Click:Connect(function()
    _G.Disabled = not _G.Disabled
end)

-- Toggle GUI Visibility
openButton.MouseButton1Click:Connect(function()
    mainGui.Visible = not mainGui.Visible
end)
