# JMenus

Advanced Menu Creation:

```# JMenus Configuration
# Advanced example with all features

settings:
  debug: false
  update-check: true
  use-placeholders: true

# Define your menus here
menus:
  # Main menu example with all features
  main:
    title: "&8&l✦ &d&lJMenus &5&lShowcase &8&l✦"
    size: 6  # 6 rows
    open-sound: "BLOCK_CHEST_OPEN:1:1"
    close-sound: "BLOCK_CHEST_CLOSE:1:1"
    
    # Menu fill item
    fill-item:
      material: "BLACK_STAINED_GLASS_PANE"
      name: " "
      glow: false
    
    # Menu items
    items:
      # Message action example
      message_action:
        material: "PAPER"
        slot: 10
        name: "&e&lMessage Action"
        lore:
          - "&8════════════════"
          - "&7Sends a message to the player"
          - "&7when clicked."
          - " "
          - "&e➤ Left-Click: &7Send normal message"
          - "&e➤ Right-Click: &7Send fancy message"
          - "&8════════════════"
        actions:
          left:
            - "[message] &aYou've clicked the message action item!"
          right:
            - "[message] &d&l✦ &5&lThis is a fancy message with colors! &d&l✦"
      
      # Command action example
      command_action:
        material: "COMMAND_BLOCK"
        slot: 12
        name: "&b&lCommand Action"
        lore:
          - "&8════════════════"
          - "&7Executes a command as the player"
          - "&7when clicked."
          - " "
          - "&b➤ Left-Click: &7Run player command"
          - "&b➤ Right-Click: &7Run another command"
          - "&8════════════════"
        actions:
          left:
            - "[command] say I clicked a command action!"
          right:
            - "[command] me used the JMenus plugin"
      
      # Console action example
      console_action:
        material: "REDSTONE_BLOCK"
        slot: 14
        name: "&c&lConsole Action"
        lore:
          - "&8════════════════"
          - "&7Executes a command as the console"
          - "&7when clicked."
          - " "
          - "&c➤ Left-Click: &7Run console command"
          - "&8════════════════"
        actions:
          left:
            - "[console] say %player_name% clicked a console action!"
      
      # Sound action example
      sound_action:
        material: "NOTE_BLOCK"
        slot: 16
        name: "&d&lSound Action"
        lore:
          - "&8════════════════"
          - "&7Plays a sound for the player"
          - "&7when clicked."
          - " "
          - "&d➤ Left-Click: &7Play note sound"
          - "&d➤ Right-Click: &7Play level-up sound"
          - "&d➤ Shift-Click: &7Play ender dragon sound"
          - "&8════════════════"
        actions:
          left:
            - "[sound] BLOCK_NOTE_BLOCK_PLING:1:1"
          right:
            - "[sound] ENTITY_PLAYER_LEVELUP:1:1"
          shift_left:
            - "[sound] ENTITY_ENDER_DRAGON_AMBIENT:1:0.5"
      
      # Broadcast action example
      broadcast_action:
        material: "END_CRYSTAL"
        slot: 20
        name: "&6&lBroadcast Action"
        lore:
          - "&8════════════════"
          - "&7Broadcasts a message to all players"
          - "&7when clicked."
          - " "
          - "&6➤ Left-Click: &7Send broadcast"
          - "&8════════════════"
        actions:
          left:
            - "[broadcast] &d&l✦ &5&l%player_name% &dused the broadcast action! &d&l✦"
      
      # Teleport action example
      teleport_action:
        material: "ENDER_PEARL"
        slot: 22
        name: "&a&lTeleport Action"
        lore:
          - "&8════════════════"
          - "&7Teleports the player"
          - "&7when clicked."
          - " "
          - "&a➤ Left-Click: &7Teleport to spawn"
          - "&a➤ Right-Click: &7Teleport to coordinates"
          - "&8════════════════"
        actions:
          left:
            - "[teleport] spawn"
            - "[message] &aTeleporting to spawn..."
          right:
            - "[teleport] 0,100,0"
            - "[message] &aTeleporting to coordinates..."
      
      # Permission action example
      permission_action:
        material: "GOLDEN_HELMET"
        slot: 24
        name: "&e&lPermission Action"
        lore:
          - "&8════════════════"
          - "&7Checks if the player has a permission"
          - "&7before executing actions."
          - " "
          - "&e➤ Left-Click: &7Check permission"
          - "&8════════════════"
        actions:
          left:
            - "[permission] jmenus.admin:[message] &aYou have admin permissions!"
            - "[permission] !jmenus.admin:[message] &cYou don't have admin permissions!"
      
      # Economy action example
      economy_action:
        material: "GOLD_INGOT"
        slot: 30
        name: "&6&lEconomy Action"
        lore:
          - "&8════════════════"
          - "&7Interacts with the player's economy"
          - "&7when clicked."
          - " "
          - "&6➤ Left-Click: &7Give 100 money"
          - "&6➤ Right-Click: &7Take 50 money"
          - "&6➤ Shift-Click: &7Check if has 1000 money"
          - "&8════════════════"
        actions:
          left:
            - "[money] give:100"
            - "[message] &aYou received 100 money!"
          right:
            - "[money] take:50"
            - "[message] &cYou lost 50 money!"
          shift_left:
            - "[money] has:1000:[message] &aYou have at least 1000 money!"
            - "[money] !has:1000:[message] &cYou don't have 1000 money!"
      
      # Combo action example
      combo_action:
        material: "NETHER_STAR"
        slot: 32
        name: "&5&lCombo Action"
        lore:
          - "&8════════════════"
          - "&7Executes multiple actions"
          - "&7in sequence when clicked."
          - " "
          - "&5➤ Left-Click: &7Run combo"
          - "&8════════════════"
        glow: true
        actions:
          left:
            - "[sound] ENTITY_FIREWORK_ROCKET_BLAST:1:1"
            - "[message] &d&l✦ &5&lRunning combo actions! &d&l✦"
            - "[broadcast] &e%player_name% is testing combo actions!"
            - "[console] title %player_name% title {\"text\":\"Combo Action\",\"color\":\"light_purple\",\"bold\":true}"
      
      # Sub-menu action example
      submenu_action:
        material: "BOOK"
        slot: 40
        name: "&b&lSub-Menu Action"
        lore:
          - "&8════════════════"
          - "&7Opens another menu"
          - "&7when clicked."
          - " "
          - "&b➤ Left-Click: &7Open sub-menu"
          - "&8════════════════"
        actions:
          left:
            - "[menu] submenu"
      
      # Close action example
      close_action:
        material: "BARRIER"
        slot: 49
        name: "&c&lClose Menu"
        lore:
          - "&8════════════════"
          - "&7Closes the current menu"
          - "&7when clicked."
          - " "
          - "&c➤ Left-Click: &7Close menu"
          - "&8════════════════"
        actions:
          left:
            - "[close]"
            - "[sound] BLOCK_CHEST_CLOSE:1:2"
            - "[message] &cMenu closed!"

  # Sub-menu example
  submenu:
    title: "&8&l✦ &b&lJMenus &3&lSub-Menu &8&l✦"
    size: 3  # 3 rows
    open-sound: "BLOCK_CHEST_OPEN:1:2"
    
    # Menu fill item
    fill-item:
      material: "LIGHT_BLUE_STAINED_GLASS_PANE"
      name: " "
    
    # Menu items
    items:
      # Player info example
      player_info:
        material: "PLAYER_HEAD"
        slot: 4
        name: "&b&lPlayer Info"
        lore:
          - "&8════════════════"
          - "&7Name: &f%player_name%"
          - "&7Health: &f%player_health%/%player_max_health%"
          - "&7Food: &f%player_food%"
          - "&7Gamemode: &f%player_gamemode%"
          - "&7World: &f%player_world%"
          - "&7Location: &f%player_x%, %player_y%, %player_z%"
          - "&8════════════════"
      
      # Server info example
      server_info:
        material: "COMPASS"
        slot: 13
        name: "&3&lServer Info"
        lore:
          - "&8════════════════"
          - "&7Name: &f%server_name%"
          - "&7Online: &f%server_online%/%server_max_players%"
          - "&7Version: &f%server_version%"
          - "&8════════════════"
      
      # Back button example
      back_button:
        material: "ARROW"
        slot: 22
        name: "&c&lBack to Main Menu"
        lore:
          - "&8════════════════"
          - "&7Returns to the main menu"
          - "&7when clicked."
          - " "
          - "&c➤ Left-Click: &7Go back"
          - "&8════════════════"
        actions:
          left:
            - "[menu] main"
            - "[sound] UI_BUTTON_CLICK:1:1"```
