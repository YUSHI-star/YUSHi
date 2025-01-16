local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()

local screenGui = Instance.new("ScreenGui")
screenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

local frame = Instance.new("Frame")
frame.Size = UDim2.new(0.4, 0, 0.4, 0)
frame.Position = UDim2.new(0.35, 0, 0.28, 0)
frame.BackgroundColor3 = Color3.new(0, 0, 0)
frame.BorderColor3 = Color3.new(255, 255, 0)
frame.BorderSizePixel = 3 
frame.Parent = screenGui

local closeButton = Instance.new("TextButton")
closeButton.Size = UDim2.new(0.1, 0.0, 0.2, 0)
closeButton.Position = UDim2.new(0.9, 0, 0., 0)
closeButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
closeButton.Text = "X"
closeButton.TextColor3 = Color3.new(1, 1, 1)
closeButton.Font = Enum.Font.GothamBlack
closeButton.TextSize = 24
closeButton.Parent = frame

local imageLabel = Instance.new("ImageLabel")
imageLabel.Size = UDim2.new(0.275, 0, 0.55, 0)
imageLabel.Position = UDim2.new(0.01, 0., 0.3, 0)
imageLabel.BackgroundColor3 = Color3.new(1, 1, 1)
imageLabel.Image = "rbxassetid://121960046717999"
imageLabel.Parent = frame

local imageLabelCorner = Instance.new("UICorner")
imageLabelCorner.CornerRadius = UDim.new(0, 8)
imageLabelCorner.Parent = imageLabel


local title = Instance.new("TextLabel")
title.Size = UDim2.new(0.8, 0, 0.2, 0)
title.Position = UDim2.new(0.1, 0.19, 0, 0)
title.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
title.Text = "Abrir o YUSHI HUB"
title.TextColor3 = Color3.new(1, 1, 1)
title.Font = Enum.Font.GothamBlack
title.TextSize = 24
title.Parent = frame

local textBox = Instance.new("TextBox")
textBox.Size = UDim2.new(0.6, 0., 0.2, 0.3)
textBox.Position = UDim2.new(0.3, 0, 0.3, 0)
textBox.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
textBox.Text = "____"
textBox.TextColor3 = Color3.new(1, 1, 1)
textBox.Font = Enum.Font.GothamBlack
textBox.TextSize = 18
textBox.Parent = frame

local textBoxCorner = Instance.new("UICorner")
textBoxCorner.CornerRadius = UDim.new(0, 6)
textBoxCorner.Parent = textBox

local enterKeyButton = Instance.new("TextButton")
enterKeyButton.Size = UDim2.new(0.29, 0, 0.15, 0)
enterKeyButton.Position = UDim2.new(0.3, 0, 0.55, 0)
enterKeyButton.BackgroundColor3 = Color3.new(0.3, 0.3, 0.3)
enterKeyButton.Text = "Verificar a key"
enterKeyButton.TextColor3 = Color3.new(1, 1, 1)
enterKeyButton.Font = Enum.Font.GothamBlack
enterKeyButton.TextSize = 18
enterKeyButton.Parent = frame

local enterKeyButtonCorner = Instance.new("UICorner")
enterKeyButtonCorner.CornerRadius = UDim.new(0, 6)
enterKeyButtonCorner.Parent = enterKeyButton

local getKeyButton = Instance.new("TextButton")
getKeyButton.Size = UDim2.new(0.29, 0, 0.15, 0)
getKeyButton.Position = UDim2.new(0.61, 0, 0.55, 0)
getKeyButton.BackgroundColor3 = Color3.new(0.3, 0.3, 0.3)
getKeyButton.Text = "DESATIVADO"
getKeyButton.TextColor3 = Color3.new(1, 1, 1)
getKeyButton.Font = Enum.Font.GothamBlack
getKeyButton.TextSize = 18
getKeyButton.Parent = frame

local getKeyButtonCorner = Instance.new("UICorner")
getKeyButtonCorner.CornerRadius = UDim.new(0, 6)
getKeyButtonCorner.Parent = getKeyButton

local function setClipboardWithURL()
    setclipboard("chicheat")
end

local getKeyButton = Instance.new("TextButton")
getKeyButton.Size = UDim2.new(0.6, 0, 0.15, 0)
getKeyButton.Position = UDim2.new(0.3, 0, 0.72, 0)
getKeyButton.BackgroundColor3 = Color3.new(0.3, 0.3, 0.3)
getKeyButton.Text = "copiar grupo do whatsapp"
getKeyButton.TextColor3 = Color3.new(1, 1, 1)
getKeyButton.Font = Enum.Font.GothamBlack
getKeyButton.TextSize = 18
getKeyButton.Parent = frame

local getKeyButtonCorner = Instance.new("UICorner")
getKeyButtonCorner.CornerRadius = UDim.new(0, 6)
getKeyButtonCorner.Parent = getKeyButton

local function setClipboardWithURL()
    setclipboard("https://whatsapp.com/channel/0029VazTewDL2ATvkHbOxJ1I")
end

getKeyButton.MouseButton1Click:Connect(setClipboardWithURL)
