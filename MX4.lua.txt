--========================================================
-- CONFIGURACIÓN MX4
--========================================================

local REQUIRED_KEY = "free2026"

-- Menú blanco/transparente
main.BackgroundColor3 = Color3.fromRGB(255,255,255)
main.BackgroundTransparency = 0.25

background.BackgroundColor3 = Color3.fromRGB(255,255,255)
background.BackgroundTransparency = 0.35

-- Quitar completamente el gradiente
if gradient then
    gradient:Destroy()
end

-- Texto oscuro para que se vea sobre el fondo blanco
title.TextColor3 = Color3.fromRGB(20,20,25)
subtitle.TextColor3 = Color3.fromRGB(80,80,90)

-- Color principal
Accent = Color3.fromRGB(255,255,255)

mainStroke.Color = Color3.fromRGB(255,255,255)
reopenStroke.Color = Color3.fromRGB(255,255,255)
fovStroke.Color = Color3.fromRGB(255,255,255)
crosshair.TextColor3 = Color3.fromRGB(255,255,255)
