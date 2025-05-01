local Players = game:GetService("Players")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

local gui = Instance.new("ScreenGui", playerGui)
gui.Name = "S7HubGui"
gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

local mainFrame = Instance.new("Frame", gui)
mainFrame.Size = UDim2.new(0, 200, 0, 300)
mainFrame.Position = UDim2.new(0.5, -100, 0.5, -150)
mainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
mainFrame.BorderSizePixel = 0
mainFrame.Name = "MainFrame"

local corner = Instance.new("UICorner", mainFrame)
corner.CornerRadius = UDim.new(0, 8)

local title = Instance.new("TextLabel", mainFrame)
title.Size = UDim2.new(1, 0, 0, 30)
title.BackgroundTransparency = 1
title.Text = "S7 Hub"
title.TextColor3 = Color3.new(1, 1, 1)
title.TextScaled = true
title.Font = Enum.Font.SourceSansBold

local stopButton = Instance.new("TextButton", mainFrame)
stopButton.Size = UDim2.new(1, -20, 0, 40)
stopButton.Position = UDim2.new(0, 10, 0, 50)
stopButton.Text = "STOP TWEEN"
stopButton.TextColor3 = Color3.new(1, 1, 1)
stopButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
stopButton.Font = Enum.Font.SourceSans
stopButton.TextScaled = true

stopButton.MouseButton1Click:Connect(function()
    StopTween() -- Função que já existe no seu script
end)

local discordButton = Instance.new("TextButton", mainFrame)
discordButton.Size = UDim2.new(1, -20, 0, 40)
discordButton.Position = UDim2.new(0, 10, 0, 100)
discordButton.Text = "discord"
discordButton.TextColor3 = Color3.new(1, 1, 1)
discordButton.BackgroundColor3 = Color3.fromRGB(88, 101, 242)
discordButton.Font = Enum.Font.SourceSans
discordButton.TextScaled = true

discordButton.MouseButton1Click:Connect(function()
    setclipboard("https://discord.gg/jfKVrrMx")
    game.StarterGui:SetCore("SendNotification", {
        Title = "Discord Copied!",
        Text = "Link do servidor copiado para a área de transferência.",
        Duration = 3
    })
end)

local credit = Instance.new("TextLabel", mainFrame)
credit.Size = UDim2.new(1, 0, 0, 30)
credit.Position = UDim2.new(0, 0, 1, -30)
credit.BackgroundTransparency = 1
credit.Text = "Created By Pedrin031"
credit.TextColor3 = Color3.fromRGB(200, 200, 200)
credit.TextScaled = true
credit.Font = Enum.Font.SourceSansItalic
