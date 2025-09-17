-- LocalScript dentro do botão Toggle
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local toggleButton = script.Parent
local toggleActive = false

local toolName = "Divergent Fist"
local autoActivateDelay = 0.4

-- Atualiza visualmente o botão
local function updateButton()
	if toggleActive then
		toggleButton.Text = "AUTO ON"
		toggleButton.BackgroundColor3 = Color3.fromRGB(0, 170, 0)
	else
		toggleButton.Text = "AUTO OFF"
		toggleButton.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
	end
end

updateButton()

-- Alterna o botão
toggleButton.MouseButton1Click:Connect(function()
	toggleActive = not toggleActive
	updateButton()
end)

-- Função para detectar a Tool correta
local function monitorTool(tool)
	if not tool:IsA("Tool") then return end
	if tool.Name ~= toolName then return end

	tool.Activated:Connect(function()
		if toggle
