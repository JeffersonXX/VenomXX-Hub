
---JeffersonXX Hub

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

---Temas

local Window = Library.CreateLib("JeffersonXX Hub", "BloodTheme")

---Abas

local Tab = Window:NewTab("Script hub")

---botão 

Section:NewButton("ButtonText", "ButtonInfo", function()
    print("Clicked")
end)

button:UpdateButton("⚙️ Menu")

----Toggle

getgenv().Toggled = false

local toggle = Section:NewToggle("Toggle", "Info", (state)
    getgenv().Toggled = state
end)

game:GetService("PegarFruta").RenderStepped:Connect(function()
	if getgenv().Toggled then
		toggle:UpdateToggle("Fruta On")
	else
		toggle:UpdateToggle("Fruta Off")
	end
end)

----Fruta

Section:NewSlider("Fruta hub", "SliderInfo", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)

---Cores

Section:NewColorPicker("Color Text", "Color Info", Color3.fromRGB(0,0,0), function(color)
    print(color)
    -- Second argument is the default color
end)

---Local windows

local Window = Library.CreateLib("JeffersonXX", colors)

---interface e cores

for theme, color in pairs(themes) do
    Section:NewColorPicker(Vermelho, "Change your "..BloodTheme, color, function(color3)
        Library:ChangeColor(Amarelo, color3)
    end)
end

---Cores personalizadas

local colors = {
    SchemeColor = Color3.fromRGB(0,255,255),
    Background = Color3.fromRGB(0, 0, 0),
    Header = Color3.fromRGB(0, 0, 0),
    TextColor = Color3.fromRGB(255,255,255),
    ElementColor = Color3.fromRGB(20, 20, 20)
}

---interface personalizada

for theme, color in pairs(themes) do
    Section:NewColorPicker(theme, "Change your "..theme, color, function(color3)
        Library:ChangeColor(theme, color3)
    end)
end



