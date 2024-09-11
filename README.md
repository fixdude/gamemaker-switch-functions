# Description
Every gamemaker switch function listed.
These functions cannot be found in fnames, they must be found through looking in games or code, they are considered variables and cannot be seen in gamemaker.
NDA stuff i guess.
I am not a nintendo switch developer, so this list will likely not be full.

Sources:
### [DELTARUNE](https://www.nintendo.com/us/store/products/deltarune-chapter-1-and-2-switch/ "Nintendo page")
### [Pizza Tower](https://www.nintendo.com/us/store/products/pizza-tower-switch/ "Nintendo page")
### By nkrapivin
### [BnvibCrap](https://gist.github.com/nkrapivin/6ae530e8b017bb48d78511f7514c1f09)
### [Input Switch applet bindings](https://gist.github.com/nkrapivin/f4db99ccf62c04a9923b34cc16a93f98)

# The wiki
#### Constants
![List of gamepad constants:](https://github.com/user-attachments/assets/0958ac40-3285-4dcc-a162-910d4f4f18b2)
```gml
switch_controller_motor_left
switch_controller_motor_right
switch_controller_motor_single = switch_controller_motor_left
```


#### Functions
The structure:
function(arguments); // Returns: type - Additional notes if necessary, like usage if it is not obvious by function name.

##### Miscellaneous
```gml
switch_controller_support_set_defaults();
switch_controller_support_set_singleplayer_only(bool);
switch_language_get_desired_language();  Returns: Language code // appears to be os_get_language for switch, https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes
```

##### BNVIB (Binary NX Vibration) - This is for the HD Rumble feature
```gml
switch_bnvib_load(file_path);  // Returns: BNVIB Handle // Loads a .bnvib file and returns a handle.
switch_bnvib_get_length(handle); // Returns: Real 
switch_bnvib_get_sampling_rate(handle); // Returns: Real
switch_bnvib_get_is_looping(handle); // Returns: Real
switch_bnvib_get_loop_start_position(handle); // Returns: Real
switch_bnvib_get_loop_interval(handle); // Returns: Real
switch_bnvib_get_loop_end_position(handle); // Returns: Real
switch_bnvib_get_value(handle, position); // Returns: Array
```

##### Controller related
```gml
switch_controller_joycon_set_holdtype(number);  // Returns: N/A - pizza tower uses 1 - i don't know what holdtype is
switch_controller_set_supported_styles(real); // Returns : N/A  - deltarune uses 7, pizza tower uses 31 - i don't know what style is
switch_controller_vibrate_hd(target_slot, target_motor, bnvib_values[@ 0], bnvib_values[@ 1], bnvib_values[@ 2], bnvib_values[@ 3]); // Returns: N/A - See BNVIB above, uses the values returned by switch_bnvib_get_value
switch_controller_support_set_player_min(real);  // Returns: N/A
switch_controller_support_set_player_max(real);  // Returns: N/A
switch_controller_support_set_singleplayer_only(bool); // Returns: N/A
switch_controller_support_set_maintain_connections(bool); // Returns: N/A
switch_controller_support_set_permit_joycon_dual(bool); // Returns: N/A
switch_controller_support_set_left_justify(bool); // Returns: N/A - Shifts pad slots to the left.
switch_controller_support_get_selected_id(); // Returns: Real - Selected joycon ID
switch_controller_support_get_player_count(); // Returns: Real

switch_controller_support_show();  // Returns: Real (Result)
/*
What the values mean:
0: Okay
-1: Failed
-2: Cancelled
-3: Unsupported style
Other values below 0: Unknown
*/
```

##### Save/Loading - Switch's saving/loading uses a committing system.
```gml
switch_save_data_commit();
```
