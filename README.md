local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/ionlyusegithubformcmods/1-Line-Scripts/main/Mobile%20Friendly%20Orion')))() --This Will Load The Script Code
local Player = game.Players.LocalPlayer --This Will Reveal The Player Name
  local Window = OrionLib:MakeWindow({
		Name = "GALAXIAN STORE KEY BYPASS",
		HidePremium = false,
		SaveConfig = true,
		ConfigFolder = "OrionTest",
        IntroText = "CARREGANDO GALAXIAN HUB"       
}) --This Will Load The Script Hub

function MakeScriptHub()
         loadstring(game:HttpGet("https://raw.githubusercontent.com/Ninjascrips/Galaxian-hub/refs/heads/main/Galaxian%20Hub"))() --Put The Script That Will Load If The Key Is Correct Here
end

OrionLib:MakeNotification({
	Name = "CARREGOU",
	Content = "COLOQUE SUA KEY! "..Player.Name..".",
	Image = "rbxassetid://4483345998",
	Time = 5
}) --Notification

getgenv().Key = "galaxian78l" --Put The Correct Key Here
getgenv().KeyInput = "string" --Require For The Key To Work

local Tab = Window:MakeTab({
	Name = "COLOQUE A KEY AQUI",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
}) --Making A Tab

Tab:AddTextbox({
	Name = "COLOQUE A KEY AQUI",
	Default = "SELECIONE",
	TextDisappear = true,
	Callback = function(Value)
		getgenv().KeyInput = Value
	end	  
}) --You Will Enter The Key Here

Tab:AddButton({
    Name = "ATIVA KEY",
    Callback = function()
        if getgenv().KeyInput == getgenv().Key then
            OrionLib:MakeNotification({
                Name = "Checking Key",
                Content = "Checking The Key You Entered",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
            wait(2)
            OrionLib:MakeNotification({
                Name = "CARREGANDO GALAXIAN HUB",
                Content = "The key you entered is Correct.",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
            wait(1)
            OrionLib:Destroy()
            wait(.3)
            MakeScriptHub()
        else
           OrionLib:MakeNotification({
                Name = "CARREGANDO",
                Content = "Checking The Key You Entered",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
            wait(2)
            OrionLib:MakeNotification({
                Name = "KEY INVALIDA!!",
                Content = "ENTRE NO SERVER DO DISCORD PRA PEGAR A KEY!",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
}) --This Will Check The Key You Entered

Tab:AddButton({
	Name = "COPIAR KEY",
	Callback = function()
      		setclipboard("Put The Link Here") --This Will Copy The Link Of The Key
  	end    
}) 
    
OrionLib:Init() --Require If The Script Is Done
