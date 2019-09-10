# CS_ConnectionWar
Game created for ludum dare 30 (theme: Connected Worlds).

<p align="center">
    <img src="https://img.itch.zone/aW1hZ2UvMTA5ODIvMzM1OTMucG5n/original/DSOL30.png" width="900">
</p>

Site web du jeu: https://antarka.itch.io/connection-war

## Requirements
- [CraftStudio](https://sparklinlabs.itch.io/craftstudio)

## Getting Started
Clone the repository at: **AppData\Roaming\CraftStudio\CraftStudioServer\Projects**.
```
$ git clone https://github.com/AntarkaGame/CS_ConnectionWar.git c81276da-40bb-4ef7-9540-4c1b6b56f5d3
```

> ⚠️ Please be sure to keep the uuid.

## Team

- [Fraxken](https://github.com/fraxken) - GENTILHOMME Thomas &lt;gentilhomme.thomas@gmail.com&gt;
- [Aleksander](https://github.com/AlexandreMalaj) - MALAJ Alexandre &lt;alexandre.malaj@gmail.com&gt;
- [Captainfive](https://github.com/Captainfive) - MONTES Irvin &lt;irvin_montes@outlook.fr&gt;
- [Demogia](https://www.deviantart.com/demogia?offset=60) - VENNET Adrien
- [Adrazaelle](https://www.linkedin.com/in/helenejuandemendoza/?originalSubdomain=fr) - JUAN DE MENDOZA Hélène

## Models

| command line terminal |
| --- |
| <img src="https://i.imgur.com/8fmsS5y.png" width="300"> |

Created and designed by demogia.

## Memory code

<details><summary>IA Class by Aleksander</summary>

```lua
AK.AI = {}
AK.AI_Ennemy = {}
AK.AI_Friend = {}
AK.AI_All    = {}
AK.AI_Die    = {}

do
    local AI = AK.AI
    AI.__index = AI
    AI.__call = function(mt)
        --mt:Update() --> Update le comportement de l'ia
    end
    
    local id = 0
    
    local AI_action = {
        ["Facebook"] = function(self)
            if self.focus ~= nil then
                if self.timer >= self.attackSpeed then
                    self.focus:TakeDomage(self.domage)
                    self.modelRndr:SetAnimation(self.animation.attack)
                    self.modelRndr:StartAnimationPlayback(false)
                    self.timer = 1
                end
            else
                self:Move()
                if not self.modelRndr:IsAnimationPlaying() then
                    self.modelRndr:SetAnimation(self.animation.move)
                    self.modelRndr:StartAnimationPlayback(false)
                end
            end
        end,
        ["BonjourMadame"] = function(self)
            if self.focus ~= nil then
                if self.timer >= self.attackSpeed then
                    self.focus:TakeDomage(self.domage)
                    self.modelRndr:SetAnimation(self.animation.attack)
                    self.modelRndr:StartAnimationPlayback(false)
                    self.timer = 1
                end
            else
                self:Move()
                if not self.modelRndr:IsAnimationPlaying() then
                    self.modelRndr:SetAnimation(self.animation.move)
                    self.modelRndr:StartAnimationPlayback(false)
                end
            end
        end,
        ["Youtube"] = function(self)
            if self.focus ~= nil then
                if self.timer >= self.attackSpeed then
                    self.focus:TakeDomage(self.domage)
                    self.modelRndr:SetAnimation(self.animation.attack)
                    self.modelRndr:StartAnimationPlayback(false)
                    self.timer = 1
                end
            else
                self:Move()
                if not self.modelRndr:IsAnimationPlaying() then
                    self.modelRndr:SetAnimation(self.animation.move)
                    self.modelRndr:StartAnimationPlayback(false)
                end
            end
        end,
        ["Deezer"] = function(self)
            if self.focus ~= nil then
                if self.timer >= self.attackSpeed then
                    self.focus:TakeDomage(self.domage)
                    self.modelRndr:SetAnimation(self.animation.attack)
                    self.modelRndr:StartAnimationPlayback(false)
                    self.timer = 1
                end
            else
                self:Move()
                if not self.modelRndr:IsAnimationPlaying() then
                    self.modelRndr:SetAnimation(self.animation.move)
                    self.modelRndr:StartAnimationPlayback(false)
                end
            end
        end,
        
        ["Doctissimo"] = function(self)
            if self.focus ~= nil then
                if self.timer >= self.attackSpeed then
                    self.focus:Heal(self.domage)
                    self.modelRndr:SetAnimation(self.animation.attack)
                    self.modelRndr:StartAnimationPlayback(false)
                    self.timer = 1
                end
            else
                self:Move()
                if not self.modelRndr:IsAnimationPlaying() then
                    self.modelRndr:SetAnimation(self.animation.move)
                    self.modelRndr:StartAnimationPlayback(false)
                end
            end
        end,
        
        -- ENNEMY
        ["Register"] = function(self)
            if self.focus ~= nil then
                if self.timer >= self.attackSpeed then
                    self.focus:TakeDomage(self.domage)
                    self.modelRndr:SetAnimation(self.animation.attack)
                    self.modelRndr:StartAnimationPlayback(false)
                    self.timer = 1
                end
            else
                self:Move()
                if not self.modelRndr:IsAnimationPlaying() then
                    self.modelRndr:SetAnimation(self.animation.move)
                    self.modelRndr:StartAnimationPlayback(false)
                end
            end
        end,
        ["Vers"] = function(self)
            if self.focus ~= nil then
                if self.timer >= self.attackSpeed then
                    self.focus:TakeDomage(self.domage)
                    self.modelRndr:SetAnimation(self.animation.attack)
                    self.modelRndr:StartAnimationPlayback(false)
                    self.timer = 1
                end
            else
                self:Move()
                if not self.modelRndr:IsAnimationPlaying() then
                    self.modelRndr:SetAnimation(self.animation.move)
                    self.modelRndr:StartAnimationPlayback(false)
                end
            end
        end,
        ["Spybot"] = function(self)
            if self.focus ~= nil then
                if self.timer >= self.attackSpeed then
                    self.focus:TakeDomage(self.domage)
                    self.modelRndr:SetAnimation(self.animation.attack)
                    self.modelRndr:StartAnimationPlayback(false)
                    self.timer = 1
                end
            else
                self:Move()
                if not self.modelRndr:IsAnimationPlaying() then
                    self.modelRndr:SetAnimation(self.animation.move)
                    self.modelRndr:StartAnimationPlayback(false)
                end
            end
        end,
        ["Boss hadopi"] = function(self)
            if self.focus ~= nil then
                if self.timer >= self.attackSpeed then
                    self.focus:TakeDomage(self.domage)
                    self.modelRndr:SetAnimation(self.animation.attack)
                    self.modelRndr:StartAnimationPlayback(false)
                    self.timer = 1
                end
            else
                self:Move()
                if not self.modelRndr:IsAnimationPlaying() then
                    self.modelRndr:SetAnimation(self.animation.move)
                    self.modelRndr:StartAnimationPlayback(false)
                end
            end
        end,
    }
    
    local AI_Animation = {
        -- FRIEND
        ["Facebook"] = {
            move    = CS.FindAsset("Characters/Walk-Facebook", "ModelAnimation"),
            attack  = CS.FindAsset("Characters/Att-Facebook", "ModelAnimation")
        },
        ["BonjourMadame"] = {
            move    = CS.FindAsset("Characters/Walk-BonjourMadame", "ModelAnimation"),
            attack  = CS.FindAsset("Characters/Att-BonjourMadame", "ModelAnimation")
        },
        ["Youtube"] = {
            move    = CS.FindAsset("Characters/Walk-Youtube", "ModelAnimation"),
            attack  = CS.FindAsset("Characters/Att-Youtube", "ModelAnimation")
        },
        ["Deezer"] = {
            move    = CS.FindAsset("Characters/Walk-Deezer", "ModelAnimation"),
            attack  = CS.FindAsset("Characters/Att-Deezer", "ModelAnimation")
        },
        ["Doctissimo"] = {
            move    = CS.FindAsset("Characters/Walk-Doctissimo", "ModelAnimation"),
            attack  = CS.FindAsset("Characters/Att-Doctissimo", "ModelAnimation")
        },
        
        -- ENNEMY
        ["Register"] = {
            move    = CS.FindAsset("Ennemi/Walk-Register", "ModelAnimation"),
            attack  = CS.FindAsset("Ennemi/Att-Register", "ModelAnimation")
        },
        ["Vers"] = {
            move    = CS.FindAsset("Ennemi/Walk-Vers", "ModelAnimation"),
            attack  = CS.FindAsset("Ennemi/Att-Vers", "ModelAnimation")
        },
        ["Spybot"] = {
            move    = CS.FindAsset("Ennemi/Walk-Spybot", "ModelAnimation"),
            attack  = CS.FindAsset("Ennemi/Att-Spybot", "ModelAnimation")
        },
        ["Boss hadopi"] = {
            move    = CS.FindAsset("Ennemi/Walk-Hadopi", "ModelAnimation"),
            attack  = CS.FindAsset("Ennemi/Att-Hadopi", "ModelAnimation")
        }
    }
    
    function AI:New( side, type, priority, life, domage, range, debit, pos, speed, attackSpeed)
        id = id + 1
        
            --print(attackSpeed)
        local Craft = CS
        local gameObject = Craft.CreateGameObject("AI_"..id)
        local script =  Craft.FindAsset("Class AI/AI check","Script")
        
        local gameObjectB = Craft.CreateGameObject("LifeBar_"..id,gameObject)
        
        local mt = setmetatable({
            id          = id,
            gameObject  = gameObject,
            gameObjectB = gameObjectB,
            
            side        = side or "ennemy",
            type        = type or "soldat",
            
            priority    = priority,
            focus       = nil,
            
            life        = life or 100,
            maxlife     = life or 100,
            
            domage      = domage or 10,
            range       = range or 100,
            
            debit       = debit or 56000,
            
            modelRndr   = gameObject:CreateComponent("ModelRenderer"),
            animation   = AI_Animation[type] or nil,
            
            pos         = pos,
            
            speed       = speed or 0.01,
            -- pour faire des seconde on mult par 60
            attackSpeed = attackSpeed * 60,
            timer       = attackSpeed,
            toFar       = nil
            
        },self)
        
        if side == "ennemy" then
            AK.AI_Ennemy[id] = mt
            mt.toFar = Craft.FindGameObject("Friend").transform:GetPosition().x
        else
            AK.AI_Friend[id] = mt
            mt.toFar = Craft.FindGameObject("Ennemy").transform:GetPosition().x
        end
        AK.AI_All[id] = mt
        
        
        
        
        gameObject.transform:SetPosition(pos)
        -- FRIEND
        if type == "Facebook" then
            mt.modelRndr:SetModel(Craft.FindAsset("Game/Characters/Facebook"))
        elseif type == "BonjourMadame" then
            mt.modelRndr:SetModel(Craft.FindAsset("Game/Characters/BonjourMadame"))
        elseif type == "Youtube" then
            mt.modelRndr:SetModel(Craft.FindAsset("Game/Characters/Youtube"))
        elseif type == "Deezer" then
            mt.modelRndr:SetModel(Craft.FindAsset("Game/Characters/Deezer"))
        elseif type == "Doctissimo" then
            mt.modelRndr:SetModel(Craft.FindAsset("Game/Characters/Doctissimo"))
            
        -- ENNEMY
        elseif type == "Register" then
            mt.modelRndr:SetModel(Craft.FindAsset("Game/Ennemi/Register"))
        elseif type == "Vers" then
            mt.modelRndr:SetModel(Craft.FindAsset("Game/Ennemi/Vers"))
        elseif type == "Spybot" then
            mt.modelRndr:SetModel(Craft.FindAsset("Game/Ennemi/Spybot"))
        elseif type == "Boss hadopi" then
            mt.modelRndr:SetModel(Craft.FindAsset("Game/Ennemi/Boss hadopi"))
        end
        gameObject:CreateScriptedBehavior(script,{id = id})
        
        local posLifeBar = mt.modelRndr:GetBlockTransform("life_bar")
        gameObjectB.transform:SetPosition(posLifeBar.position)
        
        return mt
    end
    
    function AI:Check()
        local V3 = Vector3
        if self.type ~= "Doctissimo" then
            if self.side == "ennemy" then
                local focus = nil
                local focusPrio = nil
                if self.priority == nil then
                    for k,v in pairs( AK.AI_Friend ) do
                        local distanceV = V3.Distance( self.pos,v.pos )
                        if distanceV < self.range then
                            if focus == nil then
                                focus = v
                            else
                                local distanceFocus = V3.Distance( self.pos, focus.pos )
                                if distanceV < distanceFocus then
                                    focus = v
                                end
                            end
                        end
                    end
                    self.focus = focus
                -- else priority
                else
                    for k,v in pairs( AK.AI_Friend ) do
                        local distanceV = V3.Distance( self.pos,v.pos )
                        if distanceV < self.range then
                            if focusPrio == nil then
                                if v.type == self.priority then
                                    focusPrio = v
                                else
                                    if focus == nil then
                                        focus = v 
                                    end
                                end
                            else
                                local distanceFocus = V3.Distance( self.pos, focusPrio.pos )
                                if distanceV < distanceFocus then
                                    if v.type == self.priority then
                                        focusPrio = v
                                    end
                                end
                            end
                            if focus ~= nil and focusPrio == nil then
                                local distanceFocus = V3.Distance( self.pos, focus.pos )
                                if distanceV < distanceFocus then
                                    focus = v
                                end
                            end
                        end
                    end
                    if focusPrio ~= nil then
                        self.focus = focusPrio
                    else
                        self.focus = focus
                    end
                end
            -- else side
            else
                local focus = nil
                local focusPrio = nil
                if self.priority == nil then
                    for k,v in pairs( AK.AI_Ennemy ) do
                        local distanceV = V3.Distance( self.pos,v.pos )
                        if distanceV < self.range then
                            if focus == nil then
                                focus = v
                            else
                                local distanceFocus = V3.Distance( self.pos, focus.pos )
                                if distanceV < distanceFocus then
                                    focus = v
                                end
                            end
                        end
                    end
                    self.focus = focus
                -- else priority
                else
                    for k,v in pairs( AK.AI_Ennemy ) do
                        local distanceV = V3.Distance( self.pos,v.pos )
                        if distanceV < self.range then
                            if focusPrio == nil then
                                if v.type == self.priority then
                                    focusPrio = v
                                else
                                    if focus == nil then
                                        focus = v 
                                    end
                                end
                            else
                                local distanceFocus = V3.Distance( self.pos, focusPrio.pos )
                                if distanceV < distanceFocus then
                                    if v.type == self.priority then
                                        focusPrio = v
                                    end
                                end
                            end
                            if focus ~= nil and focusPrio == nil then
                                local distanceFocus = V3.Distance( self.pos, focus.pos )
                                if distanceV < distanceFocus then
                                    focus = v
                                end
                            end
                        end
                    end
                    if focusPrio ~= nil then
                        self.focus = focusPrio
                    else
                        self.focus = focus
                    end
                end
            end
        -- else healer
        else
            if self.side == "ennemy" then
                local focus = nil
                local focusPrio = nil
                if self.priority == nil then
                    for k,v in pairs( AK.AI_Ennemy ) do
                        local distanceV = V3.Distance( self.pos,v.pos )
                        if distanceV < self.range then
                            if focus == nil then
                                if v.life < v.maxlife then
                                    focus = v
                                end
                            else
                                local distanceFocus = V3.Distance( self.pos, focus.pos )
                                if distanceV < distanceFocus then
                                    if v.life < v.maxlife then
                                        focus = v
                                    end
                                end
                            end
                        end
                    end
                    self.focus = focus
                -- else priority
                else
                    for k,v in pairs( AK.AI_Ennemy ) do
                        local distanceV = V3.Distance( self.pos,v.pos )
                        if distanceV < self.range then
                            if focusPrio == nil then
                                if v.type == self.priority then
                                    if v.life < v.maxlife then
                                        focusPrio = v
                                    end
                                else
                                    if focus == nil then
                                        if v.life < v.maxlife then
                                            focus = v 
                                        end
                                    end
                                end
                            else
                                local distanceFocus = V3.Distance( self.pos, focusPrio.pos )
                                if distanceV < distanceFocus then
                                    if v.type == self.priority then
                                        if v.life < v.maxlife then
                                            focusPrio = v
                                        end
                                    end
                                end
                            end
                            if focus ~= nil and focusPrio == nil then
                                local distanceFocus = V3.Distance( self.pos, focus.pos )
                                if distanceV < distanceFocus then
                                    if v.life < v.maxlife and v.type ~= "Doctissimo" then
                                        focus = v
                                    end
                                end
                            end
                        end
                    end
                    if focusPrio ~= nil then
                        self.focus = focusPrio
                    else
                        self.focus = focus
                    end
                end
            -- else side
            else
                local focus = nil
                local focusPrio = nil
                if self.priority == nil then
                    for k,v in pairs( AK.AI_Friend ) do
                        local distanceV = V3.Distance( self.pos,v.pos )
                        if distanceV < self.range then
                            if focus == nil then
                                if v.life < v.maxlife and v.type ~= "Doctissimo" then
                                    focus = v
                                end
                            else
                                local distanceFocus = V3.Distance( self.pos, focus.pos )
                                if distanceV < distanceFocus then
                                    if v.life < v.maxlife and v.type ~= "Doctissimo" then
                                        focus = v
                                    end
                                end
                            end
                        end
                    end
                    self.focus = focus
                -- else priority
                else
                    for k,v in pairs( AK.AI_Friend ) do
                        local distanceV = V3.Distance( self.pos,v.pos )
                        if distanceV < self.range then
                            if focusPrio == nil then
                                if v.type == self.priority then
                                    if v.life < v.maxlife and v.type ~= "Doctissimo" then
                                        focusPrio = v
                                    end
                                else
                                    if focus == nil then
                                        if v.life < v.maxlife and v.type ~= "Doctissimo" then
                                            focus = v
                                        end
                                    end
                                end
                            else
                                local distanceFocus = V3.Distance( self.pos, focusPrio.pos )
                                if distanceV < distanceFocus then
                                    if v.type == self.priority then
                                        if v.life < v.maxlife and v.type ~= "Doctissimo" then
                                            focusPrio = v
                                        end
                                    end
                                end
                            end
                            if focus ~= nil and focusPrio == nil then
                                local distanceFocus = V3.Distance( self.pos, focus.pos )
                                if distanceV < distanceFocus then
                                    if v.life < v.maxlife and v.type ~= "Doctissimo" then
                                        focus = v
                                    end
                                end
                            end
                        end
                    end
                    if focusPrio ~= nil then
                        self.focus = focusPrio
                    else
                        self.focus = focus
                    end
                end
            end
        end
        
        AI_action[self.type](self)
        
        self:LifeBarUpdate()
        self:CheckToFar()
        
        self.timer = self.timer + 1
    end
    
    function AI:CheckToFar()
        if self.side == "ennemy" then
            if self.pos.x <= self.toFar then
                self:Die()
                AK.LifeBar:SendMessage("Life",{1})
            end
        else
            if self.pos.x >= self.toFar then
                self:Die()
            end
        end
    end
    
    function AI:Heal(heal)
        self.life = self.life + heal
        if self.life > self.maxlife then
            self.life = self.maxlife
        end
    end
    
    
    function AI:Move()
        local V3 = Vector3
        if self.side == "ennemy" then
            self.gameObject.transform:Move( V3:New( -self.speed, 0, 0 ) )
        else
            self.gameObject.transform:Move( V3:New( self.speed, 0, 0 ) )
        end
        self.pos = self.gameObject.transform:GetPosition()
    end
    
    function AI:LifeBarUpdate()
        local posLifeBar = self.modelRndr:GetBlockTransform("life_bar")
        self.gameObjectB.transform:SetPosition(posLifeBar.position)
        
        if self.gameObjectB.modelRenderer == nil then
            self.gameObjectB:CreateComponent("ModelRenderer"):SetModel( CS.FindAsset( "Game/Fx/lifebar" , "Model" ) ) 
            self.gameObjectB.modelRenderer:SetAnimation( CS.FindAsset( "LifeMobs" ) ) 
            self.gameObjectB.modelRenderer:StopAnimationPlayback() 
        end
        
        self.gameObjectB.modelRenderer:SetAnimationTime( 30 - ( ( 1000 / self.maxlife * self.life ) ) / 30  )
        
        
    end
    
    function AI:TakeDomage(domage)
        self.life = self.life - domage
        if self.life <= 0 then
            self:Die()
        end
    end
    
    function AI:Die()
        AK.AI_Die[self.id] = self
    end
end
```

</details>
