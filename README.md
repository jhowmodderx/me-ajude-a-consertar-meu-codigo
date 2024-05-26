local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

function CreateESP(player)
    local ESP = Instance.new("BillboardGui")
    ESP.Name = "ESP"
    ESP.Adornee = player.Character:FindFirstChild("HumanoidRootPart")
    ESP.Size = UDim2.new(0, 100, 0, 20)
    ESP.StudsOffset = Vector3.new(0, 3, 0)
    ESP.AlwaysOnTop = true
    ESP.Parent = player.Character

    
-- Suponha que você tenha uma instância chamada "player" representando o jogador alvo
local player = game.Players.LocalPlayer

local line = Instance.new("CanvasLine")
line.From = Vector2.new(0, 0) -- Posição inicial (por exemplo, a posição da cabeça do jogador)
line.To = Vector2.new(100, 100) -- Posição final (pode ser ajustada conforme necessário)
line.Thickness = 2
line.Color = Color3.new(1, 0, 0) -- Vermelho

-- Adicione a linha à câmera ou a um objeto na cena
line.Parent = game.Workspace.CurrentCamera


-- Suponha que você tenha uma instância chamada "player" representando o jogador alvo
local player = game.Players.LocalPlayer

local box = Instance.new("CanvasFrame")
box.Size = UDim2.new(0, 100, 0, 200) -- Tamanho da caixa (ajuste conforme necessário)
box.Position = UDim2.new(0.5, -50, 0.5, -100) -- Posição centralizada (ajuste conforme necessário)
box.BackgroundTransparency = 0.5
box.BackgroundColor3 = Color3.new(1, 0, 0) -- Vermelho

-- Adicione a caixa à câmera ou a um objeto na cena
box.Parent = game.Workspace.CurrentCamera


end

for _, player in pairs(Players:GetPlayers()) do
    if player ~= LocalPlayer and player.TeamColor ~= LocalPlayer.TeamColor then
        CreateESP(player)
    end
end

local OrionLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/shlexware/Orion/main/source"))()

local Window = OrionLib:MakeWindow({
    Name = "SowTeam Hub",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "SowTeamConfig"
})


local Tab = Window:MakeTab({
    Name = "Functions",
    Icon = "rbxassetid://4483345998"
})

local Section = Tab:AddSection({
    Name = "SowTeam functions"
})


local ESPToggle = Tab:AddToggle({
    Name = "Ativar Esps (não tem como desativar)",
    Default = false,
    Callback = function(Value)
        if Value then
            print("Esp ON!")
            Label.Visible = true
        else
            print("Esp OFF!")
            Label.Visible = false
        end
    end
})
    

