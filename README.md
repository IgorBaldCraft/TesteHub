--// TesteHub GUI
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local PlayerGui = player:WaitForChild("PlayerGui")

-- Criando ScreenGui
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "TesteHub"
screenGui.Parent = PlayerGui
screenGui.ResetOnSpawn = false

-- Criando Frame principal
local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 300, 0, 200)
mainFrame.Position = UDim2.new(0.3, 0, 0.3, 0)
mainFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
mainFrame.BorderSizePixel = 0
mainFrame.Active = true
mainFrame.Draggable = true
mainFrame.Parent = screenGui

-- Título
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 40)
title.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
title.Text = "TesteHub"
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.Font = Enum.Font.SourceSansBold
title.TextSize = 20
title.Parent = mainFrame

-- Botão exemplo 1
local button1 = Instance.new("TextButton")
button1.Size = UDim2.new(0.8, 0, 0, 40)
button1.Position = UDim2.new(0.1, 0, 0.3, 0)
button1.BackgroundColor3 = Color3.fromRGB(70, 70, 70)
button1.Text = "Testar Função 1"
button1.TextColor3 = Color3.fromRGB(255, 255, 255)
button1.Font = Enum.Font.SourceSansBold
button1.TextSize = 18
button1.Parent = mainFrame

-- Botão exemplo 2
local button2 = button1:Clone()
button2.Position = UDim2.new(0.1, 0, 0.55, 0)
button2.Text = "Testar Função 2"
button2.Parent = mainFrame

-- Funções dos botões
button1.MouseButton1Click:Connect(function()
    game.StarterGui:SetCore("SendNotification", {
        Title = "TesteHub",
        Text = "Você clicou na Função 1!",
        Duration = 3
    })
end)

button2.MouseButton1Click:Connect(function()
    game.StarterGui:SetCore("SendNotification", {
        Title = "TesteHub",
        Text = "Função 2 foi ativada!",
        Duration = 3
    })
end)

-- Botão de fechar
local closeBtn = Instance.new("TextButton")
closeBtn.Size = UDim2.new(0, 30, 0, 30)
closeBtn.Position = UDim2.new(1, -35, 0, 5)
closeBtn.BackgroundColor3 = Color3.fromRGB(200, 50, 50)
closeBtn.Text = "X"
closeBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
closeBtn.Font = Enum.Font.SourceSansBold
closeBtn.TextSize = 18
closeBtn.Parent = mainFrame

closeBtn.MouseButton1Click:Connect(function()
    screenGui.Enabled = false
end)

