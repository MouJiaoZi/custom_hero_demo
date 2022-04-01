# Dota2第三方地图斧王岛面板
# Hero Demo Control Panel For Custom Dota 2 Map

![image](https://github.com/MouJiaoZi/custom_hero_demo/blob/main/screenshot.jpg)
- 实现斧王岛面板核心功能 / Main functions in Valve's offical hero demo mode
- 导入简单，快速为你的第三方地图添加方便的调试功能 / Easy to intall to your own custom game
- 自动在作弊模式开启下启用 / Auto load in CHEAT MODE

# 安装方法 / How To Use

- STEP 1
  - 下载本项目，将`content`和`game`文件夹内的文件分别放入你的文件夹中
  - Download this project, put the `content` and the `game` folders to your own game folder
- STEP 2
  - 修改你的`custom_net_tables.txt`，在其中添加新表`game_global`
  - Edit your `custom_net_tables.txt`, add a new table `game_global`
- STEP 3
  - 在你的`addon_game_mode.lua`中添加以下代码：
  - Add following code to your `addon_game_mode.lua`
    ```lua
    require( "hero_demo/demo_core" )
    if GameRules:IsCheatMode() then
        HeroDemo:Init()
    end
    ```
- STEP 4
  - 在你的监听事件`game_rules_state_change`函数中添加`HeroDemo:OnGameRulesStateChange(YOUR PARAM)`
  - 在你的监听事件`npc_spawned`函数中添加`HeroDemo:OnNPCSpawned(YOUR PARAM)`
  - 在你的监听事件`dota_item_purchased`函数中添加`HeroDemo:OnItemPurchased(YOUR PARAM)`
  - 在你的监听事件`npc_replaced`函数中添加`HeroDemo:OnNPCReplaced(YOUR PARAM)`
  - Add `HeroDemo:OnGameRulesStateChange(YOUR PARAM)` to your listened `game_rules_state_change` event function 
  - Add `HeroDemo:OnNPCSpawned(YOUR PARAM)` to your listened `npc_spawned` event function 
  - Add `HeroDemo:OnItemPurchased(YOUR PARAM)` to your listened `dota_item_purchased` event function 
  - Add `HeroDemo:OnNPCReplaced(YOUR PARAM)` to your listened `npc_replaced` event function 
- STEP 5
  - 在`https://github.com/SteamDatabase/GameTracking-Dota2/tree/master/game/dota_addons/hero_demo/resource`中获取你的语言的本地化文件
  - Get your localization file here: `https://github.com/SteamDatabase/GameTracking-Dota2/tree/master/game/dota_addons/hero_demo/resource`
