WELCOME!


//------------------------------------------------------------------------------------------------------------------------------------
CONTROLS

The controls for the game are WASD on keyboard, and include the SPACE-BAR key for jumping and double jumping. 
There are some extra features around wall climbing on the edges of ledges (W (up) key when jumping / falling).

There is crouching but functionally (press down "S" key to crouch) does not affect gameplay 
(sneaking is a mechanic that could be used with patrolling enemies with further development)

The player can RUN in conjunction with A or D for movement while holding the LEFT-SHIFT KEY. 

The INTERACTION key is "E". You must use this at terminals with keycards, in order to open access doors!


//------------------------------------------------------------------------------------------------------------------------------------
TILEMAP MANAGEMENT

you will see that there is a .csv for each one of the layers of the visual and gameplay elements in the game's level. 
These form a map, with each numerical value, corresponding to either a purely visual element (backplate layer),
a wall/solid structure element (wall layer), and a layer for gameplay elements and objects (game map layer). 

Each of these files is loaded into the game, and then used to build the level that you encounter, when you press
"play" from the main menu! 

Each cell in the texture/sprite file you can find in the game's data folder forms a 'tilemap' / map of tiles. 
the numerical values for each tile piece corresponds to its position as a ONE dimensional array. 
Don't worry if this seems really confusing, if you count the squares from left to right & top to bottom in order
the tile in question matches up with the number you get to! Also, the map is only 10 tiles wide (starting from 0), 
so if you jump down one row, you are jumping down exactly 10 places. ie. if you start at the top-left, and 
progress vertically down the left-hand column, you will go through 0, 10, 20, 30, 40, 50 etc.

//--------------------------------------------------------------------------------------------------------------------------------
// In addition to the above, the following are a the 'cases' for a switch statement for the spawning of gameplay objects on the "Game_Map_Palette" layer
// they indicate what numerical value in the csv for that file! 
case "1":
{
	obj_to_spawn = obj_player_spawn;	// This is the position on the map where the player will spawn in
} break;
case "2":
{
	obj_to_spawn = obj_storage_box;     // This is a treasure box that can be opened with 1 keycard
} break;
case "3":
{
	obj_to_spawn = obj_transporter_end_left;    // this is the left-hand end-piece for a moving walkway
} break;
case "4":
{
	obj_to_spawn = obj_transporter_middle;       // this is the middle piece for a moving walkway
} break;
case "5":
{
	obj_to_spawn = obj_transporter_end_right;     // this is the right-hand end-piece for a moving walkway
} break;
case "6":
{
	obj_to_spawn = obj_card;       // this is a collectable keycard that can be used at a terminal to open a door, or a treasure box
} break;
case "7":
{
	obj_to_spawn = obj_cash;       // this is a collectable that can simply represent points a player can gain in the level by reaching difficult areas. Perhaps one objective is to attain as much cash as possible?
} break;
case "8":
{
	obj_to_spawn = obj_lift;       // this is a small walkway piece that is animated but ultimately serve only a decorative purpose
} break;
case "9":
{
	obj_to_spawn = obj_ceiling_terminal;    // this is a decorative terminal screen that hangs from the ceiling
} break;
case "11":
{
	obj_to_spawn = obj_teleporter;    // this is the end-goal location. if the player reaches this, they finish the level!
} break;
case "13":
{
	obj_to_spawn = obj_access_door;    // this is a door that blocks the player's progression. It can be opened by a nearby terminal (the nearest one to it)
} break;
case "14":
{
	obj_to_spawn = obj_access_terminal;     // this is an interactable terminal (with the 'E' key), that consumes 1 keycard, and opens the nearest access door in return
} break;
case "15":
{
	obj_to_spawn = obj_hammer_piston    // this is a dangerous obstacle that will deal damage to the player if they collide with it (or it slams down on them)
} break;
case "16":
{
	obj_to_spawn = obj_ladder;    // this allows more easily vertical transportation of the player between platforms in-lieu of jumping and climbing
} break;
case "17":
{
	obj_to_spawn = obj_ladder_backing;   // same as the above ladder but with slightly different visuals
} break;
case "18":
{
	obj_to_spawn = obj_ladder_top;  // this represents the top of a ladder system and should be placed on the top of the ladder
} break;
default:
{
	
} break;
