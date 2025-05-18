-- NATAN DEAD REAILS - Versão Completa com Janela, Notificações e Adição de Botões
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local Title = Instance.new("TextLabel")
local AddButton = Instance.new("TextButton")
local NotifyFrame = Instance.new("Frame")
local NotifyText = Instance.new("TextLabel")

-- GUI Setup
ScreenGui.Name = "NatanDeadReails"
ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
MainFrame.Position = UDim2.new(0.3, 0, 0.3, 0)
MainFrame.Size = UDim2.new(0, 300, 0, 200)
MainFrame.Active = true
MainFrame.Draggable = true

UICorner.CornerRadius = UDim.new(0, 12)
UICorner.Parent = MainFrame

Title.Name = "Title"
Title.Parent = MainFrame
Title.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
Title.Size = UDim2.new(1, 0, 0, 40)
Title.Text = "NATAN DEAD REAILS"
Title.TextColor3 = Color3.new(1,1,1)
Title.TextSize = 22
Title.Font = Enum.Font.FredokaOne

AddButton.Name = "AddButton"
AddButton.Parent = MainFrame
AddButton.Position = UDim2.new(0, 20, 0, 60)
AddButton.Size = UDim2.new(0, 260, 0, 40)
AddButton.BackgroundColor3 = Color3.fromRGB(0, 150, 255)
AddButton.Text = "Adicionar botão de notificação"
AddButton.TextColor3 = Color3.new(1,1,1)
AddButton.TextSize = 18
AddButton.Font = Enum.Font.SourceSansBold

NotifyFrame.Name = "NotifyFrame"
NotifyFrame.Parent = ScreenGui
NotifyFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
NotifyFrame.Position = UDim2.new(0.4, 0, 0.8, 0)
NotifyFrame.Size = UDim2.new(0, 250, 0, 50)
NotifyFrame.Visible = false

NotifyText.Name = "NotifyText"
NotifyText.Parent = NotifyFrame
NotifyText.Text = ""
NotifyText.Size = UDim2.new(1, 0, 1, 0)
NotifyText.TextColor3 = Color3.new(1, 1, 1)
NotifyText.TextScaled = true
NotifyText.Font = Enum.Font.GothamBold
NotifyText.BackgroundTransparency = 1

-- Função para mostrar notificação
function notify(msg)
    NotifyText.Text = msg
    NotifyFrame.Visible = true
    wait(2.5)
    NotifyFrame.Visible = false
end

-- Botão adiciona outro botão ao menu
AddButton.MouseButton1Click:Connect(function()
    local NewButton = Instance.new("TextButton")
    NewButton.Size = UDim2.new(0, 260, 0, 35)
    NewButton.Position = UDim2.new(0, 20, 0, 110)
    NewButton.BackgroundColor3 = Color3.fromRGB(0, 255, 100)
    NewButton.Text = "Exibir notificação de exemplo"
    NewButton.TextColor3 = Color3.new(1,1,1)
    NewButton.TextSize = 16
    NewButton.Font = Enum.Font.SourceSansBold
    NewButton.Parent = MainFrame

    NewButton.MouseButton1Click:Connect(function()
        notify("Isso é uma notificação!")
    end)
end)
