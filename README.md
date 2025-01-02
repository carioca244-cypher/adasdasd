Configurações
local tempoEntreAcoes = 5 -- segundos
local quantidadeMaxima = 100 -- itens
local recursoAlvo = "Trigo" -- mude para o recurso desejado

Funções
local function coletarRecurso()
local player = game.Players.LocalPlayer
local caracter = player.Character
if caracter then
for _, objeto in pairs(workspace:GetChildren()) do
if objeto.Name == recursoAlvo and objeto:IsA("BasePart") then
local distancia = (caracter.HumanoidRootPart.Position - objeto.Position).magnitude
if distancia <= 10 then
caracter.HumanoidRootPart.CFrame = objeto.CFrame
wait(0.5)
objeto:Activate()
end
end
end
end
end

Loop principal
while true do
coletarRecurso()
wait(tempoEntreAcoes)
end
