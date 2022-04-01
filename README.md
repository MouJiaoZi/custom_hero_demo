# Dota2第三方地图斧王岛面板
# Hero Demo Control Panel For Custom Dota 2 Map

- 实现斧王岛面板核心功能 / Main functions in Valve's offical hero demo mode
- 导入简单，快速为你的第三方地图添加方便的调试功能 / Easy to intall to your own custom game
- 自动在作弊模式开启下启用 / Auto load in CHEAT MODE

# 安装方法 / How To Use

- STEP 1
  - 下载本项目，将content和game文件夹内的文件分别放入你的文件夹中
  - Download this project, put the 'content' and the 'game' folders to your own game folder
- STEP 2
  - 修改你的custom_net_tables.txt，在其中添加新表“game_global”
  - Edit your 'custom_net_tables.txt', add a new table 'game_global'
- STEP 3
  - 在你的addon_game_mode.lua中添加以下代码：
  - Add following code to your 'addon_game_mode.lua'
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
  - Add `HeroDemo:OnGameRulesStateChange(YOUR PARAM)` to your listened event function `game_rules_state_change`
  - Add `HeroDemo:OnNPCSpawned(YOUR PARAM)` to your listened event function `npc_spawned`
  - Add `HeroDemo:OnItemPurchased(YOUR PARAM)` to your listened event function `dota_item_purchased`
  - Add `HeroDemo:OnNPCReplaced(YOUR PARAM)` to your listened event function `npc_replaced`
