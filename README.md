# Description
Efficient translator for RPG Maker VX Ace games, fully written in Ruby, that can decompile all .rvdata2 files that are text-related to a readable text files and vice-versa.

# How To Use
Call the VXAceTranslator.exe file with the following arguments:-

```Decompiler Usage: RPGMakerVXAceTranslator.exe -d GAME_DIR -o OUTPUT_DIR [Optional]```

```Compiler Usage: RPGMakerVXAceTranslator.exe -c GAME_DIR -i INPUT_DIR [Optional] -o OUTPUT_DIR [Optional]```

You can optionally add (-t TARGET_FILENAME) in case you want to decompile/compile spacific files, only files that include that target filename in it's basename will be proccessed.

# Examples
Example 1:-

```Decompiling: VXAceTranslator.exe -d path/to/game```
  
```Compiling: VXAceTranslator.exe -c path/to/game```

Example 2:-

```Decompiling: VXAceTranslator.exe -d path/to/game -t Map```
  
```Compiling: VXAceTranslator.exe -c path/to/game -t Map```

Example 3:-

```Decompiling: VXAceTranslator.exe -d path/to/game -t Map001```
  
```Compiling: VXAceTranslator.exe -c path/to/game -t Map001```

# Supported Event Commands
It supports all event commands excluding only two, 505 (Unnammed) and 205 (SetMoveRoute).

`["Empty", "ShowTextAttributes", "ShowChoices", "InputNumber", "SelectKeyItem", "ShowScrollingTextAttributes", "Comment", "ConditionalBranch", "Loop", "BreakLoop", "ExitEventProcessing", "CallCommonEvent", "Label", "JumpToLabel", "ControlSwitches", "ControlVariables", "ControlSelfSwitch", "ControlTimer", "ChangeGold", "ChangeItems", "ChangeWeapons", "ChangeArmor", "ChangePartyMember", "ChangeBattleBGM", "ChangeBattleEndME", "ChangeSaveAccess", "ChangeMenuAccess", "ChangeEncounter", "ChangeFormationAccess", "ChangeWindowColor", "TransferPlayer", "SetVehicleLocation", "SetEventLocation", "ScrollMap", "GetSwitchVehicle", "ChangeTransparency", "ShowAnimation", "ShotBalloonIcon", "EraseEvent", "ChangePlayerFollowers", "GatherFollowers", "FadeoutScreen", "FadeinScreen", "TintScreen", "FlashScreen", "ShakeScreen", "Wait", "ShowPicture", "MovePicture", "RotatePicture", "TintPicture", "ErasePicture", "SetWeatherEffects", "PlayBGM", "FadeoutBGM", "SaveBGM", "ReplayBGM", "PlayBGS", "FadeoutBGS", "PlayME", "PlaySE", "StopSE", "PlayMovie", "ChangeMapDisplay", "ChangeTileset", "ChangeBattleBack", "ChangeParallaxBack", "GetLocationInfo", "BattleProcessing", "ShopProcessing", "NameInputProcessing", "ChangeHP", "ChangeMP", "ChangeState", "RecoverAll", "ChangeEXP", "ChangeLevel", "ChangeParameters", "ChangeSkills", "ChangeEquipment", "ChangeActorName", "ChangeActorClass", "ChangeActorGraphic", "ChangeVehicleGraphic", "ChangeActorNickname", "ChangeEnemyHP", "ChangeEnemyMP", "ChangeEnemyState", "EnemyRecoverAll", "EnemyAppear", "EnemyTransform", "ShowBattleAnimation", "ForceAction", "AbortBattle", "OpenMenuScreen", "OpenSaveScreen", "GameOver", "ReturnToTitleScreen", "Script", "ShowText", "When", "WhenCancel", "ChoicesEnd", "ShowScrollingText", "CommentMore", "Else", "BranchEnd", "RepeatAbove", "IfWin", "IfEscape", "IfLose", "BattleProcessingEnd", "ShopItem", "ScriptMore"]`

# How To Add Event Commands
The decompiler format for event comments in general is as follows:-

`Index-CommandEventName([Parameters])`

To manually add an event commands, you will write them in this same format, but at the end of the line, you will add a plus sign, like this:-

`Index-CommandEventName([Parameters])+`

Surly the indentation level you will add behind the event command will be accounted for.
This will make the compiler insert that command in the index you have written, also you don't have to account for the future indexes of the event commands that follows the one you are adding, this will be automaticlly handled by the compiler.

# How To Build
1- Make sure you have Ruby v2.7.8, any version higher than that have a different formate for marshaled files, and it's not compatible with the engine.

2- Make sure RubyGems is not installed at all, as it causes crashes with executables generated by Ocra library, a verion of Ocra ripped from the official gem is included in the project.

3- Simply run Builder.rb and done.

> **_NOTE:_** As the newest version of RubyGems causes crashes with executables generated by Ocra library, and the source code in the official Ocra github is outdated, and the updated working code is available only in the gem version of Ocra, I installed Ocra gem, copied Ocra folder from RubyGems directory, reinstalled Ruby, and used the copied Ocra library manually, and it worked perfectly.
