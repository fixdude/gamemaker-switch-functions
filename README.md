# Description
Every gamemaker switch function listed.
MASSIVE WIP: Some functions don't have arguments listed. You can, however, find the count by abusing the argument count error.
Feel free to dm me in discord (@pixelatedphosphorous) If there is anything switch-gamemaker related thing i should include. Although the name is gamemaker switch functions, this repo is a general wiki for the switch.

# The wiki

#### How to compile
To compile to the nintendo switch Legally, you will need a Gamemaker Enterprise subscription and the Switch SDK which you get for being a verified developer for the switch. But obviously, if you were, you wouldn't need this wiki because you would probably know the functions from some sort of developer exclusive document or wiki.
To "Legally" compile for the switch, you will need cracked Gamemaker if you don't want to pay for Enterprise, which i will not send a link to but you should be able to find it by searching online. But it will usually be older versions (EG. LTS 2022), or you can make a crack yourself somehow. You will also need a leaked Switch SDK which can be found the same way, but keep in mind it is very large (30-40 GB). After obtaining both, you will go in Gamemaker, then, go to File > Preferences > Platform Settings > Switch and put in the Switch SDK path there, and then you should be able to compile for the switch, but you will need a pirated/maybe devkit (I don't know how a NX devkit is, so i'm not sure) to run it.

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
switch_language_get_desired_language(); // Returns: Language code - Appears to be os_get_language for switch, https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes
switch_accounts_open_user(switch_login); // Returns: N/A

switch_error_show_os_code

switch_save_data_mount
switch_save_data_unmount
switch_save_data_commit(); // Returns: N/A Saving/loading uses a committing system

switch_show_store(appid); // Returns: N/A - Deltarune is 72199087622348800, for example
switch_show_store_product_details
switch_show_store_aoc_list

switch_set_performance_config
switch_get_performance_config
switch_get_operation_mode
switch_screenshot_disable
switch_screenshot_enable
switch_screenshot_set_orientation
switch_recording_enable
switch_recording_disable
switch_theme_set

```

##### IR (Infrared) sensor
```gml
switch_irsensor_get_mode
switch_irsensor_set_mode
switch_irsensor_common_config_set_all
switch_irsensor_common_config_set_exposure_time
switch_irsensor_common_config_set_light_target
switch_irsensor_common_config_set_gain
switch_irsensor_common_config_is_negative_image_used
switch_irsensor_cluster_config_set_defaults
switch_irsensor_cluster_config_set_window_of_interest
switch_irsensor_cluster_config_set_object_pixel_count_min
switch_irsensor_cluster_config_set_object_pixel_count_max
switch_irsensor_cluster_config_set_object_intensity_min
switch_irsensor_cluster_config_set_external_light_filtering
switch_irsensor_cluster_create_state_buffer
switch_irsensor_moment_config_set_defaults
switch_irsensor_moment_config_set_window_of_interest
switch_irsensor_moment_config_set_preprocess
switch_irsensor_moment_config_set_preprocess_intensity_threshold
switch_irsensor_moment_create_state_buffer
switch_irsensor_image_config_set_defaults
switch_irsensor_image_config_set_format
switch_irsensor_image_config_set_orig_format
switch_irsensor_image_config_set_trimming_format
switch_irsensor_image_config_set_trimming_start
switch_irsensor_image_config_set_external_light_filtering
switch_irsensor_image_create_state_buffers
switch_irsensor_hand_config_set_mode
switch_irsensor_hand_create_state_buffers
```

##### BNVIB (Binary NX Vibration) - This is for the HD Rumble feature
```gml
switch_bnvib_load(file_path);  // Returns: BNVIB Handle - Loads a .bnvib file and returns a handle.
switch_bnvib_unload(handle); // Returns: N/A
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
switch_controller_is_at_rest
switch_controller_show_strap_guide

switch_controller_get_default_joycon_assignment
switch_controller_set_default_joycon_assignment
switch_controller_start_lr_assignment
switch_controller_stop_lr_assignment

switch_controller_support_set_defaults(); // Returns: N/A
switch_controller_support_set_singleplayer_only(bool); // Returns: N/A
switch_controller_support_set_player_min(real);  // Returns: N/A
switch_controller_support_set_player_max(real);  // Returns: N/A
switch_controller_support_get_player_count(); // Returns: Real
switch_controller_support_set_singleplayer_only(bool); // Returns: N/A
switch_controller_support_set_maintain_connections(bool); // Returns: N/A
switch_controller_support_set_permit_joycon_dual(bool); // Returns: N/A
switch_controller_support_set_left_justify(bool); // Returns: N/A - Shifts pad slots to the left.
switch_controller_support_get_selected_id(); // Returns: Real - Selected joycon ID
switch_controller_support_set_all
switch_controller_support_set_identification_color
switch_controller_support_set_identification_colour
switch_controller_support_set_show_identification_colors
switch_controller_support_set_show_identification_colours
switch_controller_support_set_explain_text
switch_controller_support_set_show_explain_text
switch_controller_support_show();  // Returns: Real (Result) - What the values mean: 0: Okay | -1: Failed | -2: Cancelled | -3: Unsupported style | Other values below: Unknown error

switch_controller_get_sixaxis_handle_count
switch_controller_set_gyro_zero_drift_mode
switch_controller_get_gyro_zero_drift_mode
switch_controller_is_sensor_fusion_enabled
switch_controller_enable_sensor_fusion
switch_controller_set_sensor_fusion_params
switch_controller_get_sensor_fusion_params
switch_controller_reset_sensor_fusion_params

switch_controller_joycon_set_holdtype(number);  // Returns: N/A - Assumptions: 0 is TV mode, 1 is handheld mode, 2 is tabletop mode (Unconfirmed)
switch_controller_joycon_get_holdtype
switch_controller_joycon_left_connected
switch_controller_joycon_right_connected
switch_controller_set_supported_styles(real); // Returns : N/A  - deltarune uses 7, pizza tower uses 31 - i don't know what style is
switch_controller_get_supported_styles
switch_controller_set_handheld_activation_mode
switch_controller_get_handheld_activation_mode
switch_controller_vibrate_hd(target_slot, target_motor, bnvib_values[@ 0], bnvib_values[@ 1], bnvib_values[@ 2], bnvib_values[@ 3]); // Returns: N/A - See BNVIB above, uses the values returned by switch_bnvib_get_value
switch_controller_acceleration
switch_controller_angular_velocity
switch_controller_direction
switch_controller_angle
```

##### Networking & account related
```gml
 // Some returned -1 in testing, so i'll assume most of these return the statuses.
switch_set_local_network_mode(arg1);
switch_add_ssl_certificate
switch_set_net_autoconnect

switch_gameserver_login_user
switch_gameserver_logout_user

switch_matchmaking_start(arg1);
switch_matchmaking_stop(arg1);
switch_matchmaking_session_create(arg1, arg2, arg3, arg4, arg5, arg6, arg7);
switch_matchmaking_session_leave(arg1, arg2);
switch_matchmaking_session_find(arg1, arg2, arg3);
switch_matchmaking_session_join(arg1, arg2);
switch_matchmaking_session_autojoin(arg1, arg2, arg3, arg4, arg5, arg6, arg7);
switch_matchmaking_session_close_participation(arg1, arg2);
switch_matchmaking_session_open_participation(arg1, arg2);
switch_matchmaking_session_update_description(arg1, arg2, arg3);

switch_leaderboard_get_scores
switch_leaderboard_post_score
switch_leaderboard_post_common_data
switch_npln_login_prearranged_user
switch_npln_leaderboard_set_user_data
switch_npln_leaderboard_get_user_data
switch_npln_leaderboard_set_score
switch_npln_leaderboard_delete_score
switch_npln_leaderboard_get_scores_range
switch_npln_leaderboard_get_scores_near
switch_npln_session_create
switch_npln_session_join
switch_npln_session_join_alias
switch_npln_session_find
switch_npln_session_matchmake
switch_npln_session_destroy
switch_npln_session_update
switch_npln_session_create_alias
switch_npln_session_send_data
```









