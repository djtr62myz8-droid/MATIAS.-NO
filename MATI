--========================================================
-- P A N E L   M x 4
-- KEY: free2026
-- DISCORD: https://discord.gg/J7tNTHaGS
--========================================================

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")

local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

local GUI_NAME = "MX4_PANEL"

--========================================================
-- KEY SYSTEM
--========================================================

local REQUIRED_KEY = "free2026"
local DISCORD = "https://discord.gg/J7tNTHaGS"

local keyGui = Instance.new("ScreenGui")
keyGui.Name = "MX4_KEY_SYSTEM"
keyGui.ResetOnSpawn = false
keyGui.IgnoreGuiInset = true
keyGui.DisplayOrder = 5000
keyGui.Parent = playerGui

local keyFrame = Instance.new("Frame")
keyFrame.Size = UDim2.fromOffset(340,220)
keyFrame.Position = UDim2.new(0.5,-170,0.5,-110)
keyFrame.BackgroundColor3 = Color3.fromRGB(12,15,25)
keyFrame.BackgroundTransparency = 0.08
keyFrame.BorderSizePixel = 0
keyFrame.Parent = keyGui

local keyCorner = Instance.new("UICorner")
keyCorner.CornerRadius = UDim.new(0,14)
keyCorner.Parent = keyFrame

local keyStroke = Instance.new("UIStroke")
keyStroke.Thickness = 2
keyStroke.Color = Color3.fromRGB(125,75,255)
keyStroke.Parent = keyFrame

local keyTitle = Instance.new("TextLabel")
keyTitle.Size = UDim2.new(1,-20,0,35)
keyTitle.Position = UDim2.fromOffset(10,10)
keyTitle.BackgroundTransparency = 1
keyTitle.Text = "P A N E L   M x 4"
keyTitle.TextColor3 = Color3.new(1,1,1)
keyTitle.TextSize = 18
keyTitle.Font = Enum.Font.GothamBlack
keyTitle.Parent = keyFrame

local keySub = Instance.new("TextLabel")
keySub.Size = UDim2.new(1,-20,0,20)
keySub.Position = UDim2.fromOffset(10,42)
keySub.BackgroundTransparency = 1
keySub.Text = "I N G R E S A   L A   K E Y"
keySub.TextColor3 = Color3.fromRGB(150,155,175)
keySub.TextSize = 8
keySub.Font = Enum.Font.GothamBold
keySub.Parent = keyFrame

--========================================================
-- KEY BOX
--========================================================

local keyBox = Instance.new("TextBox")
keyBox.Size = UDim2.new(1,-40,0,38)
keyBox.Position = UDim2.fromOffset(20,70)
keyBox.BackgroundColor3 = Color3.fromRGB(28,33,49)
keyBox.BackgroundTransparency = 0.05
keyBox.BorderSizePixel = 0

-- IMPORTANTE:
-- La Key se ve normalmente mientras escribes.
-- NO usar TextPassword.
keyBox.Text = ""
keyBox.PlaceholderText = "KEY"
keyBox.TextColor3 = Color3.new(1,1,1)
keyBox.PlaceholderColor3 = Color3.fromRGB(120,125,140)
keyBox.TextSize = 12
keyBox.Font = Enum.Font.GothamBold
keyBox.ClearTextOnFocus = false
keyBox.TextXAlignment = Enum.TextXAlignment.Center
keyBox.Parent = keyFrame

local keyBoxCorner = Instance.new("UICorner")
keyBoxCorner.CornerRadius = UDim.new(0,8)
keyBoxCorner.Parent = keyBox

--========================================================
-- ENTER
--========================================================

local enterButton = Instance.new("TextButton")
enterButton.Size = UDim2.new(1,-40,0,35)
enterButton.Position = UDim2.fromOffset(20,115)
enterButton.BackgroundColor3 = Color3.fromRGB(125,75,255)
enterButton.BorderSizePixel = 0
enterButton.Text = "E N T R A R"
enterButton.TextColor3 = Color3.new(1,1,1)
enterButton.TextSize = 10
enterButton.Font = Enum.Font.GothamBold
enterButton.Parent = keyFrame

local enterCorner = Instance.new("UICorner")
enterCorner.CornerRadius = UDim.new(0,8)
enterCorner.Parent = enterButton

--========================================================
-- DISCORD
--========================================================

local discordButton = Instance.new("TextButton")
discordButton.Size = UDim2.new(1,-40,0,35)
discordButton.Position = UDim2.fromOffset(20,160)
discordButton.BackgroundColor3 = Color3.fromRGB(45,50,70)
discordButton.BorderSizePixel = 0
discordButton.Text = "D I S C O R D"
discordButton.TextColor3 = Color3.new(1,1,1)
discordButton.TextSize = 10
discordButton.Font = Enum.Font.GothamBold
discordButton.Parent = keyFrame

local discordCorner = Instance.new("UICorner")
discordCorner.CornerRadius = UDim.new(0,8)
discordCorner.Parent = discordButton

discordButton.MouseButton1Click:Connect(function()
	-- Roblox no permite copiar directamente al portapapeles
	-- desde un LocalScript normal.
	discordButton.Text = DISCORD

	task.delay(4,function()
		if discordButton and discordButton.Parent then
			discordButton.Text = "D I S C O R D"
		end
	end)
end)

--========================================================
-- VALIDACIÓN
--========================================================

local unlocked = false

local function checkKey()
	if keyBox.Text == REQUIRED_KEY then
		unlocked = true
		keyGui:Destroy()
	else
		enterButton.Text = "K E Y   I N C O R R E C T A"

		task.delay(1,function()
			if enterButton and enterButton.Parent then
				enterButton.Text = "E N T R A R"
			end
		end)
	end
end

enterButton.MouseButton1Click:Connect(checkKey)

keyBox.FocusLost:Connect(function(enterPressed)
	if enterPressed then
		checkKey()
	end
end)

repeat
	task.wait()
until unlocked

--========================================================
-- COLORES
--========================================================

local Themes = {
	Purple = Color3.fromRGB(125,75,255),
	White  = Color3.fromRGB(255,255,255),
	Blue   = Color3.fromRGB(60,140,255),
	Red    = Color3.fromRGB(255,70,80),
	Green  = Color3.fromRGB(60,220,120),
	Cyan   = Color3.fromRGB(50,220,255),
	Pink   = Color3.fromRGB(255,80,190),
	Orange = Color3.fromRGB(255,150,50),
	Yellow = Color3.fromRGB(255,220,60)
}

local Accent = Themes.Purple

--========================================================
-- ESTADOS
--========================================================

local AimEnabled = false
local ESPEnabled = false
local ESPBoxEnabled = false
local ESPNameEnabled = false
local ESPDistanceEnabled = false
local ESPHealthEnabled = false
local ESPRGBEnabled = false

local CrosshairEnabled = true
local NoClipEnabled = false
local FlyEnabled = false

local FOV = 120
local Smoothness = 0.15
local FlySpeed = 60

local visuals = {}
local currentTarget = nil

--========================================================
-- LIMPIAR PANEL ANTERIOR
--========================================================

local old = playerGui:FindFirstChild(GUI_NAME)

if old then
	old:Destroy()
end

--========================================================
-- GUI PRINCIPAL
--========================================================

local gui = Instance.new("ScreenGui")
gui.Name = GUI_NAME
gui.ResetOnSpawn = false
gui.IgnoreGuiInset = true
gui.DisplayOrder = 999
gui.Parent = playerGui

local main = Instance.new("Frame")
main.Name = "Main"
main.Size = UDim2.fromOffset(500,350)
main.Position = UDim2.new(0.5,-250,0.5,-175)
main.BackgroundColor3 = Color3.fromRGB(12,15,25)
main.BackgroundTransparency = 0.12
main.BorderSizePixel = 0
main.Parent = gui

local mainCorner = Instance.new("UICorner")
mainCorner.CornerRadius = UDim.new(0,14)
mainCorner.Parent = main

local mainStroke = Instance.new("UIStroke")
mainStroke.Thickness = 2
mainStroke.Color = Accent
mainStroke.Parent = main

--========================================================
-- FONDO TRANSPARENTE
--========================================================

local background = Instance.new("Frame")
background.Size = UDim2.fromScale(1,1)
background.BackgroundColor3 = Color3.fromRGB(20,24,38)
background.BackgroundTransparency = 0.30
background.BorderSizePixel = 0
background.Parent = main

local bgCorner = Instance.new("UICorner")
bgCorner.CornerRadius = UDim.new(0,14)
bgCorner.Parent = background

local gradient = Instance.new("UIGradient")
gradient.Rotation = 35
gradient.Color = ColorSequence.new({
	ColorSequenceKeypoint.new(0,Color3.fromRGB(35,20,75)),
	ColorSequenceKeypoint.new(0.5,Color3.fromRGB(20,30,60)),
	ColorSequenceKeypoint.new(1,Color3.fromRGB(50,20,70))
})
gradient.Parent = background

--========================================================
-- HEADER
--========================================================

local header = Instance.new("Frame")
header.Size = UDim2.new(1,0,0,52)
header.BackgroundTransparency = 1
header.ZIndex = 10
header.Parent = main

local title = Instance.new("TextLabel")
title.Size = UDim2.new(1,-70,0,30)
title.Position = UDim2.fromOffset(16,5)
title.BackgroundTransparency = 1
title.Text = "P A N E L   M x 4"
title.TextColor3 = Color3.new(1,1,1)
title.TextSize = 18
title.Font = Enum.Font.GothamBlack
title.TextXAlignment = Enum.TextXAlignment.Left
title.ZIndex = 11
title.Parent = header

local subtitle = Instance.new("TextLabel")
subtitle.Size = UDim2.new(1,-70,0,15)
subtitle.Position = UDim2.fromOffset(17,32)
subtitle.BackgroundTransparency = 1
subtitle.Text = "C O N T R O L   P A N E L"
subtitle.TextColor3 = Color3.fromRGB(155,160,175)
subtitle.TextSize = 8
subtitle.Font = Enum.Font.Gotham
subtitle.TextXAlignment = Enum.TextXAlignment.Left
subtitle.ZIndex = 11
subtitle.Parent = header

--========================================================
-- CERRAR
--========================================================

local close = Instance.new("TextButton")
close.Size = UDim2.fromOffset(32,32)
close.Position = UDim2.new(1,-42,0,10)
close.BackgroundColor3 = Color3.fromRGB(45,25,35)
close.Text = "X"
close.TextColor3 = Color3.fromRGB(255,80,90)
close.TextSize = 14
close.Font = Enum.Font.GothamBold
close.AutoButtonColor = false
close.ZIndex = 20
close.Parent = header

local closeCorner = Instance.new("UICorner")
closeCorner.CornerRadius = UDim.new(0,8)
closeCorner.Parent = close

--========================================================
-- REABRIR
--========================================================

local reopen = Instance.new("TextButton")
reopen.Size = UDim2.fromOffset(190,40)
reopen.Position = UDim2.new(0.5,-95,0,12)
reopen.BackgroundColor3 = Color3.fromRGB(15,18,30)
reopen.BackgroundTransparency = 0.12
reopen.Text = "P A N E L   M x 4"
reopen.TextColor3 = Color3.new(1,1,1)
reopen.TextSize = 12
reopen.Font = Enum.Font.GothamBlack
reopen.Visible = false
reopen.AutoButtonColor = false
reopen.Parent = gui

local reopenCorner = Instance.new("UICorner")
reopenCorner.CornerRadius = UDim.new(0,10)
reopenCorner.Parent = reopen

local reopenStroke = Instance.new("UIStroke")
reopenStroke.Thickness = 2
reopenStroke.Color = Accent
reopenStroke.Parent = reopen

close.MouseButton1Click:Connect(function()
	main.Visible = false
	reopen.Visible = true
end)

reopen.MouseButton1Click:Connect(function()
	main.Visible = true
	reopen.Visible = false
end)

--========================================================
-- SIDEBAR
--========================================================

local sidebar = Instance.new("Frame")
sidebar.Size = UDim2.new(0,125,1,-62)
sidebar.Position = UDim2.fromOffset(8,55)
sidebar.BackgroundTransparency = 1
sidebar.ZIndex = 5
sidebar.Parent = main

local content = Instance.new("Frame")
content.Size = UDim2.new(1,-145,1,-62)
content.Position = UDim2.fromOffset(137,55)
content.BackgroundColor3 = Color3.fromRGB(18,22,35)
content.BackgroundTransparency = 0.22
content.BorderSizePixel = 0
content.ZIndex = 4
content.Parent = main

local contentCorner = Instance.new("UICorner")
contentCorner.CornerRadius = UDim.new(0,10)
contentCorner.Parent = content

local pages = {}
local tabs = {}

--========================================================
-- PÁGINAS
--========================================================

local function createPage(name,text,y)

	local tab = Instance.new("TextButton")
	tab.Size = UDim2.new(1,0,0,36)
	tab.Position = UDim2.fromOffset(0,y)
	tab.BackgroundTransparency = 1
	tab.Text = text
	tab.TextColor3 = Color3.fromRGB(150,155,175)
	tab.TextSize = 9
	tab.Font = Enum.Font.GothamBold
	tab.TextXAlignment = Enum.TextXAlignment.Left
	tab.AutoButtonColor = false
	tab.ZIndex = 8
	tab.Parent = sidebar

	local padding = Instance.new("UIPadding")
	padding.PaddingLeft = UDim.new(0,10)
	padding.Parent = tab

	local page = Instance.new("ScrollingFrame")
	page.Size = UDim2.new(1,-16,1,-16)
	page.Position = UDim2.fromOffset(8,8)
	page.BackgroundTransparency = 1
	page.BorderSizePixel = 0
	page.ScrollBarThickness = 3
	page.CanvasSize = UDim2.new(0,0,0,700)
	page.Visible = false
	page.ZIndex = 6
	page.Parent = content

	pages[name] = page
	tabs[name] = tab

	tab.MouseButton1Click:Connect(function()

		for _,p in pairs(pages) do
			p.Visible = false
		end

		for _,t in pairs(tabs) do
			t.BackgroundTransparency = 1
			t.TextColor3 = Color3.fromRGB(150,155,175)
		end

		page.Visible = true
		tab.BackgroundTransparency = 0
		tab.BackgroundColor3 = Accent
		tab.TextColor3 = Color3.new(1,1,1)
	end)

	return page
end

local combatPage = createPage("Combat","◉   C O M B A T",0)
local espPage = createPage("ESP","◈   E S P",40)
local crossPage = createPage("Crosshair","⊕   C R O S S",80)
local configPage = createPage("Config","⚙   C O N F I G",120)

--========================================================
-- TOGGLE
--========================================================

local function createToggle(parent,name,description,y,callback)

	local button = Instance.new("TextButton")
	button.Size = UDim2.new(1,-8,0,48)
	button.Position = UDim2.fromOffset(0,y)
	button.BackgroundColor3 = Color3.fromRGB(28,33,49)
	button.BackgroundTransparency = 0.12
	button.Text = ""
	button.AutoButtonColor = false
	button.ZIndex = 8
	button.Parent = parent

	local corner = Instance.new("UICorner")
	corner.CornerRadius = UDim.new(0,8)
	corner.Parent = button

	local label = Instance.new("TextLabel")
	label.Size = UDim2.new(1,-60,0,18)
	label.Position = UDim2.fromOffset(10,4)
	label.BackgroundTransparency = 1
	label.Text = name
	label.TextColor3 = Color3.fromRGB(240,242,250)
	label.TextSize = 10
	label.Font = Enum.Font.GothamBold
	label.TextXAlignment = Enum.TextXAlignment.Left
	label.ZIndex = 9
	label.Parent = button

	local desc = Instance.new("TextLabel")
	desc.Size = UDim2.new(1,-60,0,16)
	desc.Position = UDim2.fromOffset(10,25)
	desc.BackgroundTransparency = 1
	desc.Text = description
	desc.TextColor3 = Color3.fromRGB(125,130,145)
	desc.TextSize = 7
	desc.Font = Enum.Font.Gotham
	desc.TextXAlignment = Enum.TextXAlignment.Left
	desc.ZIndex = 9
	desc.Parent = button

	local indicator = Instance.new("Frame")
	indicator.Size = UDim2.fromOffset(32,18)
	indicator.Position = UDim2.new(1,-42,0.5,-9)
	indicator.BackgroundColor3 = Color3.fromRGB(65,68,80)
	indicator.ZIndex = 9
	indicator.Parent = button

	local ic = Instance.new("UICorner")
	ic.CornerRadius = UDim.new(1,0)
	ic.Parent = indicator

	local knob = Instance.new("Frame")
	knob.Size = UDim2.fromOffset(12,12)
	knob.Position = UDim2.fromOffset(3,3)
	knob.BackgroundColor3 = Color3.fromRGB(240,240,245)
	knob.ZIndex = 10
	knob.Parent = indicator

	local kc = Instance.new("UICorner")
	kc.CornerRadius = UDim.new(1,0)
	kc.Parent = knob

	local state = false

	button.MouseButton1Click:Connect(function()

		state = not state

		if state then
			indicator.BackgroundColor3 = Accent
			knob.Position = UDim2.new(1,-15,0,3)
		else
			indicator.BackgroundColor3 = Color3.fromRGB(65,68,80)
			knob.Position = UDim2.fromOffset(3,3)
		end

		callback(state)
	end)

	return button
end

--========================================================
-- SLIDER
--========================================================

local function createSlider(parent,text,y,minValue,maxValue,current,callback)

	local box = Instance.new("Frame")
	box.Size = UDim2.new(1,-8,0,58)
	box.Position = UDim2.fromOffset(0,y)
	box.BackgroundColor3 = Color3.fromRGB(28,33,49)
	box.BackgroundTransparency = 0.12
	box.BorderSizePixel = 0
	box.ZIndex = 8
	box.Parent = parent

	local corner = Instance.new("UICorner")
	corner.CornerRadius = UDim.new(0,8)
	corner.Parent = box

	local label = Instance.new("TextLabel")
	label.Size = UDim2.new(1,0,0,20)
	label.Position = UDim2.fromOffset(10,3)
	label.BackgroundTransparency = 1
	label.TextColor3 = Color3.new(1,1,1)
	label.TextSize = 9
	label.Font = Enum.Font.GothamBold
	label.TextXAlignment = Enum.TextXAlignment.Left
	label.ZIndex = 9
	label.Parent = box

	local bar = Instance.new("Frame")
	bar.Size = UDim2.new(1,-20,0,6)
	bar.Position = UDim2.fromOffset(10,40)
	bar.BackgroundColor3 = Color3.fromRGB(60,64,76)
	bar.BorderSizePixel = 0
	bar.ZIndex = 9
	bar.Parent = box

	local fill = Instance.new("Frame")
	fill.BackgroundColor3 = Accent
	fill.BorderSizePixel = 0
	fill.ZIndex = 10
	fill.Parent = bar

	local fc = Instance.new("UICorner")
	fc.CornerRadius = UDim.new(1,0)
	fc.Parent = fill

	local dragging = false

	local function update(value)

		value = math.clamp(value,minValue,maxValue)

		local alpha =
			(value-minValue)/(maxValue-minValue)

		fill.Size = UDim2.new(alpha,0,1,0)

		label.Text =
			text..": "..string.format("%.2f",value)

		callback(value)
	end

	update(current)

	bar.InputBegan:Connect(function(input)

		if input.UserInputType == Enum.UserInputType.MouseButton1
			or input.UserInputType == Enum.UserInputType.Touch then

			dragging = true

			local alpha = math.clamp(
				(input.Position.X-bar.AbsolutePosition.X)/
				bar.AbsoluteSize.X,
				0,1
			)

			update(minValue+alpha*(maxValue-minValue))
		end
	end)

	UserInputService.InputChanged:Connect(function(input)

		if not dragging then return end

		if input.UserInputType == Enum.UserInputType.MouseMovement
			or input.UserInputType == Enum.UserInputType.Touch then

			local alpha = math.clamp(
				(input.Position.X-bar.AbsolutePosition.X)/
				bar.AbsoluteSize.X,
				0,1
			)

			update(minValue+alpha*(maxValue-minValue))
		end
	end)

	UserInputService.InputEnded:Connect(function(input)

		if input.UserInputType == Enum.UserInputType.MouseButton1
			or input.UserInputType == Enum.UserInputType.Touch then

			dragging = false
		end
	end)
end

--========================================================
-- FOV
--========================================================

local fovCircle = Instance.new("Frame")
fovCircle.AnchorPoint = Vector2.new(0.5,0.5)
fovCircle.Position = UDim2.fromScale(0.5,0.5)
fovCircle.Size = UDim2.fromOffset(FOV*2,FOV*2)
fovCircle.BackgroundTransparency = 1
fovCircle.Visible = false
fovCircle.ZIndex = 2
fovCircle.Parent = gui

local fovCorner = Instance.new("UICorner")
fovCorner.CornerRadius = UDim.new(1,0)
fovCorner.Parent = fovCircle

local fovStroke = Instance.new("UIStroke")
fovStroke.Thickness = 2
fovStroke.Color = Accent
fovStroke.Parent = fovCircle

--========================================================
-- CROSSHAIR
--========================================================

local crosshair = Instance.new("TextLabel")
crosshair.Size = UDim2.fromOffset(60,60)
crosshair.AnchorPoint = Vector2.new(0.5,0.5)
crosshair.Position = UDim2.fromScale(0.5,0.5)
crosshair.BackgroundTransparency = 1
crosshair.Text = "+"
crosshair.TextColor3 = Accent
crosshair.TextSize = 30
crosshair.Font = Enum.Font.GothamBlack
crosshair.Visible = true
crosshair.ZIndex = 50
crosshair.Parent = gui

--========================================================
-- AIM
-- SOLO JUGADORES
-- CABEZA MÁS CERCANA AL CENTRO DEL FOV
--========================================================

local function getClosestPlayerToCenter()

	local camera = workspace.CurrentCamera

	if not camera then
		return nil
	end

	local viewport = camera.ViewportSize

	local center = Vector2.new(
		viewport.X / 2,
		viewport.Y / 2
	)

	local closestPlayer = nil
	local closestDistance = FOV

	for _,target in ipairs(Players:GetPlayers()) do

		if target ~= player and target.Character then

			local humanoid =
				target.Character:FindFirstChildOfClass("Humanoid")

			local head =
				target.Character:FindFirstChild("Head")

			if humanoid and humanoid.Health > 0 and head then

				local screenPosition,onScreen =
					camera:WorldToViewportPoint(head.Position)

				if onScreen and screenPosition.Z > 0 then

					local screenPoint =
						Vector2.new(
							screenPosition.X,
							screenPosition.Y
						)

					local distance =
						(screenPoint-center).Magnitude

					if distance <= closestDistance then

						closestDistance = distance
						closestPlayer = target

					end
				end
			end
		end
	end

	return closestPlayer
end

local function updateAim()

	if not AimEnabled then
		currentTarget = nil
		return
	end

	local target = getClosestPlayerToCenter()

	if not target or not target.Character then
		currentTarget = nil
		return
	end

	local head =
		target.Character:FindFirstChild("Head")

	if not head then
		currentTarget = nil
		return
	end

	local humanoid =
		target.Character:FindFirstChildOfClass("Humanoid")

	if not humanoid or humanoid.Health <= 0 then
		currentTarget = nil
		return
	end

	currentTarget = target

	local camera = workspace.CurrentCamera

	if not camera then
		return
	end

	local desired =
		CFrame.lookAt(
			camera.CFrame.Position,
			head.Position
		)

	camera.CFrame =
		camera.CFrame:Lerp(
			desired,
			math.clamp(Smoothness,0.01,1)
		)
end

--========================================================
-- COMBAT
--========================================================

createToggle(
	combatPage,
	"A I M",
	"Selecciona jugadores por la cabeza",
	0,
	function(value)

		AimEnabled = value

		if not value then
			currentTarget = nil
		end
	end
)

createToggle(
	combatPage,
	"F O V",
	"Mostrar el círculo del FOV",
	53,
	function(value)

		fovCircle.Visible = value

	end
)

createSlider(
	combatPage,
	"F O V",
	106,
	40,
	400,
	FOV,
	function(value)

		FOV = math.floor(value)

		fovCircle.Size =
			UDim2.fromOffset(
				FOV*2,
				FOV*2
			)
	end
)

createSlider(
	combatPage,
	"S M O O T H N E S S",
	172,
	0.01,
	1,
	Smoothness,
	function(value)

		Smoothness = value

	end
)

--========================================================
-- ESP
--========================================================

local function removeVisual(plr)

	local data = visuals[plr]

	if not data then
		return
	end

	for _,obj in pairs(data) do

		if typeof(obj) == "Instance" and obj.Parent then
			obj:Destroy()
		end

	end

	visuals[plr] = nil
end

local function createVisual(plr)

	if plr == player then
		return
	end

	if not plr.Character then
		return
	end

	removeVisual(plr)

	local character = plr.Character

	local root =
		character:FindFirstChild("HumanoidRootPart")

	if not root then
		return
	end

	local data = {}

	visuals[plr] = data

	local highlight = Instance.new("Highlight")
	highlight.Name = "MX4_ESP"
	highlight.Adornee = character
	highlight.FillColor = Accent
	highlight.OutlineColor = Accent
	highlight.FillTransparency = 0.65
	highlight.OutlineTransparency = 0
	highlight.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop
	highlight.Enabled = ESPEnabled
	highlight.Parent = character

	data.highlight = highlight

	local box = Instance.new("BoxHandleAdornment")
	box.Name = "MX4_BOX"
	box.Adornee = root
	box.Size = Vector3.new(4.5,7,3)
	box.Color3 = Accent
	box.Transparency = 0.35
	box.AlwaysOnTop = true
	box.Visible = ESPBoxEnabled
	box.Parent = character

	data.box = box

	local billboard = Instance.new("BillboardGui")
	billboard.Name = "MX4_INFO"
	billboard.Adornee = root
	billboard.Size = UDim2.fromOffset(180,70)
	billboard.StudsOffset = Vector3.new(0,4.5,0)
	billboard.AlwaysOnTop = true
	billboard.Enabled = false
	billboard.Parent = character

	data.billboard = billboard

	local info = Instance.new("TextLabel")
	info.Size = UDim2.fromScale(1,1)
	info.BackgroundTransparency = 1
	info.TextColor3 = Accent
	info.TextStrokeTransparency = 0.25
	info.TextSize = 11
	info.Font = Enum.Font.GothamBold
	info.Parent = billboard

	data.info = info
end

local function updateVisuals()

	for _,plr in ipairs(Players:GetPlayers()) do

		if plr ~= player then

			if plr.Character then

				if not visuals[plr] then
					createVisual(plr)
				end

				local data = visuals[plr]

				if data then

					local root =
						plr.Character:FindFirstChild("HumanoidRootPart")

					local humanoid =
						plr.Character:FindFirstChildOfClass("Humanoid")

					if root then

						data.highlight.Enabled = ESPEnabled
						data.box.Visible = ESPBoxEnabled

						local text = ""

						if ESPNameEnabled then
							text = plr.Name
						end

						if ESPDistanceEnabled then

							local myCharacter =
								player.Character

							local myRoot =
								myCharacter and
								myCharacter:FindFirstChild("HumanoidRootPart")

							if myRoot then

								local distance =
									(root.Position-myRoot.Position).Magnitude

								if text ~= "" then
									text = text.."\n"
								end

								text =
									text..
									math.floor(distance)..
									" studs"
							end
						end

						if ESPHealthEnabled and humanoid then

							if text ~= "" then
								text = text.."\n"
							end

							text =
								text..
								"HP: "..
								math.floor(humanoid.Health)
						end

						data.billboard.Enabled = text ~= ""
						data.info.Text = text
					end
				end

			else
				removeVisual(plr)
			end
		end
	end
end

createToggle(
	espPage,
	"E S P",
	"Resalta los jugadores",
	0,
	function(value)

		ESPEnabled = value
		updateVisuals()

	end
)

createToggle(
	espPage,
	"B O D Y   B O X",
	"Muestra una caja alrededor",
	53,
	function(value)

		ESPBoxEnabled = value
		updateVisuals()

	end
)

createToggle(
	espPage,
	"N O M B R E",
	"Muestra el nombre",
	106,
	function(value)

		ESPNameEnabled = value
		updateVisuals()

	end
)

createToggle(
	espPage,
	"D I S T A N C I A",
	"Muestra la distancia",
	159,
	function(value)

		ESPDistanceEnabled = value
		updateVisuals()

	end
)

createToggle(
	espPage,
	"H E A L T H",
	"Muestra la vida",
	212,
	function(value)

		ESPHealthEnabled = value
		updateVisuals()

	end
)

createToggle(
	espPage,
	"E S P   R G B",
	"Cambia automáticamente el color",
	265,
	function(value)

		ESPRGBEnabled = value

	end
)

--========================================================
-- CROSSHAIR
--========================================================

createToggle(
	crossPage,
	"C R O S S H A I R",
	"Mostrar u ocultar la mira",
	0,
	function(value)

		CrosshairEnabled = value
		crosshair.Visible = value

	end
)

--========================================================
-- NOCLIP
--========================================================

createToggle(
	configPage,
	"N O   C L I P",
	"Desactiva colisiones localmente",
	0,
	function(value)

		NoClipEnabled = value

		if not value then

			local character =
				player.Character

			if character then

				for _,part in ipairs(
					character:GetDescendants()
				) do

					if part:IsA("BasePart") then
						part.CanCollide = true
					end
				end
			end
		end
	end
)

--========================================================
-- FLY
--========================================================

local flyVelocity = nil

local function stopFly()

	if flyVelocity then
		flyVelocity:Destroy()
		flyVelocity = nil
	end
end

local function startFly()

	stopFly()

	local character =
		player.Character

	if not character then
		return
	end

	local root =
		character:FindFirstChild("HumanoidRootPart")

	if not root then
		return
	end

	flyVelocity =
		Instance.new("BodyVelocity")

	flyVelocity.MaxForce =
		Vector3.new(100000,100000,100000)

	flyVelocity.Velocity =
		Vector3.zero

	flyVelocity.Parent = root
end

createToggle(
	configPage,
	"F L Y",
	"Vuelo para pruebas",
	53,
	function(value)

		FlyEnabled = value

		if value then
			startFly()
		else
			stopFly()
		end
	end
)

createSlider(
	configPage,
	"F L Y   S P E E D",
	106,
	10,
	100,
	FlySpeed,
	function(value)

		FlySpeed = math.floor(value)

	end
)

--========================================================
-- TEMAS
--========================================================

local function setTheme(color)

	Accent = color

	mainStroke.Color = Accent
	reopenStroke.Color = Accent
	fovStroke.Color = Accent
	crosshair.TextColor3 = Accent

	for _,data in pairs(visuals) do

		if data.highlight then
			data.highlight.FillColor = Accent
			data.highlight.OutlineColor = Accent
		end

		if data.box then
			data.box.Color3 = Accent
		end

		if data.info then
			data.info.TextColor3 = Accent
		end
	end

	for _,tab in pairs(tabs) do

		if tab.BackgroundTransparency < 1 then
			tab.BackgroundColor3 = Accent
		end
	end
end

local colorNames = {
	"Purple",
	"White",
	"Blue",
	"Red",
	"Green",
	"Cyan",
	"Pink",
	"Orange",
	"Yellow"
}

for i,name in ipairs(colorNames) do

	local button = Instance.new("TextButton")

	button.Size =
		UDim2.new(1,-8,0,34)

	button.Position =
		UDim2.fromOffset(0,(i-1)*38)

	button.BackgroundColor3 =
		Themes[name]

	button.Text = name

	button.TextColor3 =
		name == "White"
		and Color3.fromRGB(20,20,25)
		or Color3.new(1,1,1)

	button.TextSize = 9
	button.Font = Enum.Font.GothamBold
	button.AutoButtonColor = false
	button.Parent = configPage

	local corner = Instance.new("UICorner")
	corner.CornerRadius = UDim.new(0,8)
	corner.Parent = button

	button.MouseButton1Click:Connect(function()
		setTheme(Themes[name])
	end)
end

--========================================================
-- DISCORD EN EL MENÚ
--========================================================

local discordPanel = Instance.new("TextButton")

discordPanel.Size =
	UDim2.new(1,-8,0,40)

discordPanel.Position =
	UDim2.fromOffset(0,350)

discordPanel.BackgroundColor3 =
	Color3.fromRGB(45,50,70)

discordPanel.BorderSizePixel = 0
discordPanel.Text = "D I S C O R D"
discordPanel.TextColor3 = Color3.new(1,1,1)
discordPanel.TextSize = 10
discordPanel.Font = Enum.Font.GothamBold
discordPanel.Parent = configPage

local discordPanelCorner =
	Instance.new("UICorner")

discordPanelCorner.CornerRadius =
	UDim.new(0,8)

discordPanelCorner.Parent =
	discordPanel

discordPanel.MouseButton1Click:Connect(function()

	discordPanel.Text = DISCORD

	task.delay(4,function()

		if discordPanel and discordPanel.Parent then
			discordPanel.Text = "D I S C O R D"
		end
	end)
end)

--========================================================
-- JUGADORES
--========================================================

Players.PlayerAdded:Connect(function(plr)

	plr.CharacterAdded:Connect(function()

		task.wait(0.5)
		updateVisuals()

	end)
end)

Players.PlayerRemoving:Connect(function(plr)

	removeVisual(plr)

	if currentTarget == plr then
		currentTarget = nil
	end
end)

--========================================================
-- LOOP
--========================================================

local timer = 0
local hue = 0

RunService.RenderStepped:Connect(function(delta)

	updateAim()

	-- NOCLIP
	if NoClipEnabled then

		local character =
			player.Character

		if character then

			for _,part in ipairs(
				character:GetDescendants()
			) do

				if part:IsA("BasePart") then
					part.CanCollide = false
				end
			end
		end
	end

	-- FLY
	if FlyEnabled and flyVelocity then

		local camera =
			workspace.CurrentCamera

		if camera then

			local direction =
				Vector3.zero

			if UserInputService:IsKeyDown(Enum.KeyCode.W) then
				direction += camera.CFrame.LookVector
			end

			if UserInputService:IsKeyDown(Enum.KeyCode.S) then
				direction -= camera.CFrame.LookVector
			end

			if UserInputService:IsKeyDown(Enum.KeyCode.A) then
				direction -= camera.CFrame.RightVector
			end

			if UserInputService:IsKeyDown(Enum.KeyCode.D) then
				direction += camera.CFrame.RightVector
			end

			if direction.Magnitude > 0 then
				direction = direction.Unit * FlySpeed
			end

			flyVelocity.Velocity = direction
		end
	end

	-- ESP RGB
	if ESPEnabled and ESPRGBEnabled then

		hue = (hue + delta*0.5)%1

		local color =
			Color3.fromHSV(hue,1,1)

		for _,data in pairs(visuals) do

			if data.highlight then
				data.highlight.FillColor = color
				data.highlight.OutlineColor = color
			end

			if data.box then
				data.box.Color3 = color
			end

			if data.info then
				data.info.TextColor3 = color
			end
		end
	end

	timer += delta

	if timer >= 0.15 then
		timer = 0
		updateVisuals()
	end
end)

--========================================================
-- ARRASTRAR MENÚ
--========================================================

local dragging = false
local dragStart
local startPosition

header.InputBegan:Connect(function(input)

	if input.UserInputType == Enum.UserInputType.MouseButton1
		or input.UserInputType == Enum.UserInputType.Touch then

		dragging = true
		dragStart = input.Position
		startPosition = main.Position
	end
end)

UserInputService.InputChanged:Connect(function(input)

	if not dragging then
		return
	end

	if input.UserInputType == Enum.UserInputType.MouseMovement
		or input.UserInputType == Enum.UserInputType.Touch then

		local delta =
			input.Position - dragStart

		main.Position =
			UDim2.new(
				startPosition.X.Scale,
				startPosition.X.Offset + delta.X,
				startPosition.Y.Scale,
				startPosition.Y.Offset + delta.Y
			)
	end
end)

UserInputService.InputEnded:Connect(function(input)

	if input.UserInputType == Enum.UserInputType.MouseButton1
		or input.UserInputType == Enum.UserInputType.Touch then

		dragging = false
	end
end)

--========================================================
-- RIGHT SHIFT
--========================================================

UserInputService.InputBegan:Connect(function(input,processed)

	if processed then
		return
	end

	if input.KeyCode == Enum.KeyCode.RightShift then

		main.Visible = not main.Visible
		reopen.Visible = not main.Visible

	end
end)

--========================================================
-- PÁGINA INICIAL
--========================================================

combatPage.Visible = true

tabs["Combat"].BackgroundTransparency = 0
tabs["Combat"].BackgroundColor3 = Accent
tabs["Combat"].TextColor3 =
	Color3.new(1,1,1)

updateVisuals()

print("================================")
print("P A N E L   M x 4")
print("KEY: free2026")
print("DISCORD: "..DISCORD)
print("AIM / FOV / ESP")
print("NOCLIP / FLY")
print("MENU CARGADO")
print("================================")
