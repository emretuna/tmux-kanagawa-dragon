<p align="center">
    <h2 align="center">Kanagawa Dragon for tmux</h2>
</p>

<p align="center">All natural pine, faux fur and a bit of soho vibes for the classy minimalist</p>

## Usage

> NOTE: It uses a [Nerdfont](https://www.nerdfonts.com/font-downloads) by default for the icons, so it is recommended to have a Nerdfont set as your terminal font

1. Install [TPM](https://github.com/tmux-plugins/tpm)
   <br>

2. Add the Rosé Pine plugin with the following lines:

```bash
set -g @plugin 'emretuna/tmux-kanagawa-dragon'
# ... alongside
set -g @plugin 'tmux-plugins/tpm'
# To update plugin for future revisions or bug fixes, do the "Prefix + U" keycombo
```

<br>

3. Set your preferred variant:

```bash
set -g @kanagawa_dragon_variant 'main' # Options are 'main', 'moon' or 'dawn'
```

<br>

4. After adding TPM and the Rosé Pine theme to `.tmux.conf`, restart tmux and use the <kbd>Prefix + I</kbd> (capital I) combo to source your configuration.
   For updating the plugin, the key combination is <kbd>Prefix + U</kbd> (which TPM sets by default).
   <br>

5. Optional but recommended: Activate the extra modules, they are enabled by writing 'on' after the option name

```bash
set -g @kanagawa_dragon_host 'on' # Enables hostname in the status bar
set -g @kanagawa_dragon_date_time '' # It accepts the date UNIX command format (man date for info)
set -g @kanagawa_dragon_user 'on' # Turn on the username component in the statusbar
set -g @kanagawa_dragon_directory 'on' # Turn on the current folder component in the status bar
set -g @kanagawa_dragon_bar_bg_disable 'on' # Disables background color, for transparent terminal emulators
# If @kanagawa_dragon_bar_bg_disable is set to 'on', uses the provided value to set the background color
# It can be any of the on tmux (named colors, 256-color set, `default` or hex colors)
# See more on http://man.openbsd.org/OpenBSD-current/man1/tmux.1#STYLES
set -g @kanagawa_dragon_bar_bg_disabled_color_option 'default'

set -g @kanagawa_dragon_only_windows 'on' # Leaves only the window module, for max focus and space
set -g @kanagawa_dragon_disable_active_window_menu 'on' # Disables the menu that shows the active window on the left

set -g @kanagawa_dragon_default_window_behavior 'on' # Forces tmux default window list behaviour
set -g @kanagawa_dragon_show_current_program 'on' # Forces tmux to show the current running program as window name
set -g @kanagawa_dragon_show_pane_directory 'on' # Forces tmux to show the current directory as window name
# Previously set -g @kanagawa_dragon_window_tabs_enabled

# Example values for these can be:
set -g @kanagawa_dragon_left_separator ' > ' # The strings to use as separators are 1-space padded
set -g @kanagawa_dragon_right_separator ' < ' # Accepts both normal chars & nerdfont icons
set -g @kanagawa_dragon_field_separator ' | ' # Again, 1-space padding, it updates with prefix + I
set -g @kanagawa_dragon_window_separator ' - ' # Replaces the default `:` between the window number and name

# These are not padded
set -g @kanagawa_dragon_session_icon '' # Changes the default icon to the left of the session name
set -g @kanagawa_dragon_current_window_icon '' # Changes the default icon to the left of the active window name
set -g @kanagawa_dragon_folder_icon '' # Changes the default icon to the left of the current directory folder
set -g @kanagawa_dragon_username_icon '' # Changes the default icon to the right of the hostname
set -g @kanagawa_dragon_hostname_icon '󰒋' # Changes the default icon to the right of the hostname
set -g @kanagawa_dragon_date_time_icon '󰃰' # Changes the default icon to the right of the date module
set -g @kanagawa_dragon_window_status_separator "  " # Changes the default icon that appears between window names

# Very beta and specific opt-in settings, tested on v3.2a, look at issue #10
set -g @kanagawa_dragon_prioritize_windows 'on' # Disables the right side functionality in a certain window count / terminal width
set -g @kanagawa_dragon_width_to_hide '80' # Specify a terminal width to toggle off most of the right side functionality
set -g @kanagawa_dragon_window_count '5' # Specify a number of windows, if there are more than the number, do the same as width_to_hide
```

- The separator options should go back to the defaults ( →, ← and | NerdFont characters) if the options are unset and you close all tmux sessions (a full restart)
- The `@kanagawa_dragon_width_to_hide` and `rose_pine_window_count` settings do not refresh automatically. They need to be refreshed manually, their current state is discussed [here](https://github.com/emretuna/tmux-kanagawa-dragon/issues/10).
- For `@kanagawa_dragon_window_tabs_enabled` and any further naming changes / notices, see issue #14.

<br>

6. Integration with other status-bar plugins

- You can add, for example, the [tmux-mode-indicator](https://github.com/MunifTanjim/tmux-mode-indicator) plugin:

```bash
# Add to the beginning / end of the left and right sections your own.
set -g @kanagawa_dragon_status_left_prepend_section '#{tmux_mode_indicator}'
set -g @kanagawa_dragon_status_left_append_section 'It works'
set -g @kanagawa_dragon_status_right_prepend_section 'with normal text'
set -g @kanagawa_dragon_status_right_append_section 'too'
```

> This plugin is being developed and tested on tmux v3.2a on Pop_OS! (Ubuntu). If there are problems with other versions, do let me know.

## Gallery

- Main

![image](https://github.com/emretuna/tmux-kanagawa-dragon/assets/121260905/184514d9-08fe-453b-a664-3cd6ccab0d4a)

- Moon

![image](https://github.com/emretuna/tmux-kanagawa-dragon/assets/121260905/e2665eb6-280b-48a2-ab45-163d2eb21050)

- Dawn

![image](https://github.com/emretuna/tmux-kanagawa-dragon/assets/121260905/b194e552-cb15-4296-b459-e1da521aad8c)

## Thanks to

- [MrSandman](https://github.com/mrs4ndman)

- [Catppuccin for tmux](https://github.com/catppuccin/tmux) ([license](https://github.com/catppuccin/tmux/blob/4e48b09a76829edc7b55fbb15467cf0411f07931/LICENSE))

- [mcanueste](https://github.com/mcanueste/rose-pine-tmux) ([license](https://github.com/mcanueste/rose-pine-tmux/blob/715de6925992ab9f7162fcfefc1d3ba1510d187a/LICENSE))
