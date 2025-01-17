<h1 id="general_options">general options <a href="#general_options" title="Permalink to this location">¶</a></h1>


<h2 id="window_updates">window updates <a href="#window_updates" title="Permalink to this location">¶</a></h2>


<h3 id="pgstar_interval">pgstar_interval <a href="#pgstar_interval" title="Permalink to this location">¶</a></h3>


update windows when `mod(model_number,pgstar_interval) == 0`
note: this replaces the obsolete control `pgstar_cnt`.
better performance for star with this > 1.
make it as large as you can while still getting adequate plot updates. 
Does not alter the rate at which pgplots are saved to disk, use the
`*_file_interval` options instead.

{% highlight fortran %}
pgstar_interval = 2
{% endhighlight %}


<h3 id="pause">pause <a href="#pause" title="Permalink to this location">¶</a></h3>


if true, then after refresh windows, wait for user to hit RETURN

{% highlight fortran %}
pause = .false.
{% endhighlight %}


<h3 id="pause_interval">pause_interval <a href="#pause_interval" title="Permalink to this location">¶</a></h3>


if > 0, then pause when `mod(model_number, pause_interval) = 0`.

{% highlight fortran %}
pause_interval = -1
{% endhighlight %}


<h3 id="pgstar_sleep">pgstar_sleep <a href="#pgstar_sleep" title="Permalink to this location">¶</a></h3>


after refresh windows, sleep this long (in seconds; can be noninteger)

{% highlight fortran %}
pgstar_sleep = 0.0
{% endhighlight %}


<h3 id="clear_history">clear_history <a href="#clear_history" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
clear_history = .false.
{% endhighlight %}


<h2 id="white_on_black_flags">white_on_black flags <a href="#white_on_black_flags" title="Permalink to this location">¶</a></h2>


true means white foreground color on black background

<h3 id="file_white_on_black_flag">file_white_on_black_flag <a href="#file_white_on_black_flag" title="Permalink to this location">¶</a></h3>


<h3 id="win_white_on_black_flag">win_white_on_black_flag <a href="#win_white_on_black_flag" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
file_white_on_black_flag = .true.
win_white_on_black_flag = .true.
{% endhighlight %}


<h2 id="file_output">file output <a href="#file_output" title="Permalink to this location">¶</a></h2>


<h3 id="file_device">file_device <a href="#file_device" title="Permalink to this location">¶</a></h3>


<h3 id="file_extension">file_extension <a href="#file_extension" title="Permalink to this location">¶</a></h3>


'png' is Portable Network Graphics format; can also use 'pdf'

{% highlight fortran %}
file_device = 'png'
file_extension = 'png'
{% endhighlight %}


<h3 id="file_digits">file_digits <a href="#file_digits" title="Permalink to this location">¶</a></h3>


number of digits for `model_number` in filenames

{% highlight fortran %}
file_digits = 6
{% endhighlight %}


<h3 id="delta_HR_limit_for_file_output">delta_HR_limit_for_file_output <a href="#delta_HR_limit_for_file_output" title="Permalink to this location">¶</a></h3>


trigger file output by distance travelled on HR diagram
negative means no limit
HR distance since last file output = sum of dHR
where per step dHR = same definition as used for timestep limits

    dHR = sqrt((delta_HR_ds_L*dlgL)**2 + (delta_HR_ds_Teff*dlgTeff)**2)
    dlgL = log10(L/L_prev)
    dlgTeff = log10(Teff/Teff_prev)

{% highlight fortran %}
delta_HR_limit_for_file_output = -1
{% endhighlight %}


{% highlight fortran %}
pgstar_report_writing_files = .true.
{% endhighlight %}


for terminal output report when write plot file

<h2 id="title_age_and_model_number">title, age, and model number <a href="#title_age_and_model_number" title="Permalink to this location">¶</a></h2>


placement details
scale is for character size
disp, coord, fjust are args for PGMTXT

+ DISP :
the displacement of the character string from the
specified edge of the viewport, measured outwards
from the viewport in units of the character
height. Use a negative value to write inside the
viewport, a positive value to write outside.
+ COORD :
the location of the character string along the
specified edge of the viewport, as a fraction of
the length of the edge.
+ FJUST :
controls justification of the string parallel to
the specified edge of the viewport. If
FJUST = 0.0, the left-hand end of the string will
be placed at COORD; if JUST = 0.5, the center of
the string will be placed at COORD; if JUST = 1.0,
the right-hand end of the string will be placed at
at COORD.

### model_number

{% highlight fortran %}
pgstar_show_model_number = .true.
{% endhighlight %}


only shown for full window, not for subplots

{% highlight fortran %}
pgstar_model_scale = 0.8
pgstar_model_lw = 3
pgstar_model_disp = 3.0
pgstar_model_coord = 1.01
pgstar_model_fjust = 1.0
{% endhighlight %}


<h3 id="age">age <a href="#age" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
pgstar_show_age = .true.
{% endhighlight %}


if all of those are false, then picks units based on magnitude of age

{% highlight fortran %}
pgstar_show_age_in_seconds = .false.
pgstar_show_age_in_minutes = .false.
pgstar_show_age_in_hours = .false.
pgstar_show_age_in_days = .false.
pgstar_show_age_in_years = .false.
pgstar_show_log_age_in_years = .false.
{% endhighlight %}


only shown for full window, not for subplots

{% highlight fortran %}
pgstar_age_scale = 0.8
pgstar_age_lw = 3
pgstar_age_disp = 3.0
pgstar_age_coord = -0.04
pgstar_age_fjust = 0.0
{% endhighlight %}


### axes line weight

{% highlight fortran %}
pgstar_box_lw = 3
{% endhighlight %}


<h3 id="titles">titles <a href="#titles" title="Permalink to this location">¶</a></h3>


these apply to all plots except grids.

{% highlight fortran %}
pgstar_show_title = .true.
pgstar_title_scale = 1.3
pgstar_title_lw = 3
pgstar_title_disp = 1.1
pgstar_title_coord = 0.5
pgstar_title_fjust = 0.5
{% endhighlight %}


<h3 id="grid_titles">grid titles <a href="#grid_titles" title="Permalink to this location">¶</a></h3>


these apply to the top of the grid, not to the subplots within the grid.

{% highlight fortran %}
pgstar_grid_show_title = .true.
pgstar_grid_title_scale = 1.2
pgstar_grid_title_lw = 3
pgstar_grid_title_disp = 1.8
pgstar_grid_title_coord = 0.5
pgstar_grid_title_fjust = 0.5
{% endhighlight %}


<h3 id="scale_for_axis_labels">scale for axis labels <a href="#scale_for_axis_labels" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
pgstar_xaxis_label_scale = 1.5
pgstar_left_yaxis_label_scale = 1.5
pgstar_right_yaxis_label_scale = 1.5
pgstar_xaxis_label_lw = 4
pgstar_left_yaxis_label_lw = 4
pgstar_right_yaxis_label_lw = 4
{% endhighlight %}


<h3 id="displacements_for_axis_labels">displacements for axis labels <a href="#displacements_for_axis_labels" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
pgstar_xaxis_label_disp = 2.2
pgstar_left_yaxis_label_disp = 3.1
pgstar_right_yaxis_label_disp = 4.1
{% endhighlight %}


<h3 id="relative_scale_of_axis_numbers">relative scale of axis numbers <a href="#relative_scale_of_axis_numbers" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
pgstar_num_scale = 1.2
{% endhighlight %}


<h3 id="line_width_for_data">line width for data <a href="#line_width_for_data" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
pgstar_lw = 8
{% endhighlight %}

<h1 id="TRho_Profile_window">TRho Profile window <a href="#TRho_Profile_window" title="Permalink to this location">¶</a></h1>


current model in T-Rho plane

{% highlight fortran %}
TRho_Profile_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
TRho_Profile_win_width = 6
TRho_Profile_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
TRho_Profile_xleft = 0.15
TRho_Profile_xright = 0.85
TRho_Profile_ybot = 0.15
TRho_Profile_ytop = 0.85
TRho_Profile_txt_scale = 1.0
TRho_Profile_title = 'TRho_Profile'
{% endhighlight %}


{% highlight fortran %}
TRho_switch_to_Column_Depth = .false.
{% endhighlight %}


if true, replace logRho for xaxis by log column depth (g/cm^2)

{% highlight fortran %}
TRho_switch_to_mass = .false.
{% endhighlight %}


if true, replaces logRho for xaxis by log mass coordinate M-m(k) (Msun)

{% highlight fortran %}
show_TRho_Profile_legend = .false.
TRho_Profile_legend_coord = 0.05
TRho_Profile_legend_fjust = 0.0
TRho_Profile_legend_disp1 = -2.0
TRho_Profile_legend_del_disp = -1.3
{% endhighlight %}


{% highlight fortran %}
show_TRho_Profile_text_info = .false.
TRho_Profile_text_info_xfac = 0.77
TRho_Profile_text_info_dxfac = 0.02
TRho_Profile_text_info_yfac = 0.6
TRho_Profile_text_info_dyfac = -0.04
{% endhighlight %}


{% highlight fortran %}
show_TRho_Profile_mass_locs = .false.
show_TRho_accretion_mesh_borders = .false.
{% endhighlight %}


If true, plots the borders of the mesh and newly accreted material in the appropriate xcoord

{% highlight fortran %}
show_TRho_Profile_kap_regions = .false.
show_TRho_Profile_eos_regions = .false.
show_TRho_Profile_gamma1_4_3rd = .false.
show_TRho_Profile_degeneracy_line = .true.
show_TRho_Profile_Pgas_Prad_line = .true.
show_TRho_Profile_burn_lines = .true.
show_TRho_Profile_burn_labels = .true.
show_TRho_Profile_logQ_limit = .false.
{% endhighlight %}


{% highlight fortran %}
show_TRho_Profile_annotation1 = .false.
show_TRho_Profile_annotation2 = .false.
show_TRho_Profile_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
TRho_Profile_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
TRho_Profile_use_decorator = .false.
{% endhighlight %}


axis limits

{% highlight fortran %}
TRho_Profile_xmin = -11.1
TRho_Profile_xmax = 10.2
TRho_Profile_ymin = 2.6
TRho_Profile_ymax = 10.2
{% endhighlight %}


file output

{% highlight fortran %}
TRho_Profile_file_flag = .false.
TRho_Profile_file_dir = 'png'
TRho_Profile_file_prefix = 'trho_profile_'
TRho_Profile_file_interval = 5
TRho_Profile_file_width = -1
TRho_Profile_file_aspect_ratio = -1
{% endhighlight %}


mass location markers

    profile_mass_point_color_index
    1 = foreground color
    2 = red
    3 = green
    4 = blue
    etc. the full range is defined in Set_Colours in pgstar_support.f
    profile_mass_point_symbol
    code number of the symbol to be drawn:
          -1, -2  : a single dot (diameter = current
                    line width).
          -3..-31 : a regular polygon with ABS(SYMBOL)
                    edges (style set by current fill style).
          0..31   : standard marker symbols.
          32..127 : ASCII characters (in current font).
                    e.g. to use letter F as a marker, let
                    SYMBOL = ICHAR('F').
          > 127  :  a Hershey symbol number.
    for info about codes, http://www.astro.caltech.edu/~tjp/pgplot/hershey.html
    profile_mass_point_str
    text to show with the marker
    profile_mass_point_str_clr
    color index for the string

set all the entries

{% highlight fortran %}
profile_mass_point_q = -1
profile_mass_point_color_index = 1
profile_mass_point_symbol = -6
profile_mass_point_symbol_scale = 1.7
profile_mass_point_str = ''
profile_mass_point_str_clr = 1
profile_mass_point_str_scale = 1.0
{% endhighlight %}


set defaults

{% highlight fortran %}
num_profile_mass_points = 3
{% endhighlight %}


{% highlight fortran %}
profile_mass_point_q(1) = 0.5
profile_mass_point_color_index(1) = 1
profile_mass_point_symbol(1) = -6
profile_mass_point_str(1) = '  0.5 M\d\(0844)\u'
profile_mass_point_str_clr(1) = 1
{% endhighlight %}


{% highlight fortran %}
profile_mass_point_q(2) = 0.95
profile_mass_point_color_index(2) = 1
profile_mass_point_symbol(2) = -6
profile_mass_point_str(2) = '  0.95 M\d\(0844)\u'
profile_mass_point_str_clr(3) = 1
{% endhighlight %}


{% highlight fortran %}
profile_mass_point_q(3) = 0.999
profile_mass_point_color_index(3) = 1
profile_mass_point_symbol(3) = -6
profile_mass_point_str(3) = '  0.999 M\d\(0844)\u'
profile_mass_point_str_clr(3) = 1
{% endhighlight %}

<h1 id="Abundance_window">Abundance window <a href="#Abundance_window" title="Permalink to this location">¶</a></h1>


current model abundance profiles

{% highlight fortran %}
Abundance_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Abundance_win_width = 6
Abundance_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Abundance_xleft = 0.15
Abundance_xright = 0.85
Abundance_ybot = 0.15
Abundance_ytop = 0.85
Abundance_txt_scale = 1.0
Abundance_title = 'Abundance'
{% endhighlight %}


{% highlight fortran %}
Abundance_num_isos_to_show = -1
Abundance_which_isos_to_show(1) = 'h1'
Abundance_which_isos_to_show(2) = 'he3'
Abundance_which_isos_to_show(3) = 'he4'
Abundance_which_isos_to_show(4) = 'c12'
Abundance_which_isos_to_show(5) = 'n14'
Abundance_which_isos_to_show(6) = 'o16'
{% endhighlight %}


{% highlight fortran %}
num_abundance_line_labels = 5
Abundance_line_txt_scale_factor = 0.8
{% endhighlight %}


{% highlight fortran %}
Abundance_legend_max_cnt = 16
Abundance_legend_txt_scale_factor = 0.8
{% endhighlight %}


{% highlight fortran %}
Abundance_xaxis_name = 'mass'
Abundance_xaxis_reversed = .false.
{% endhighlight %}


power xaxis limits -- to override system default selections

{% highlight fortran %}
Abundance_xmin = -101d0
Abundance_xmax = -101d0
{% endhighlight %}


abundance yaxis limits -- to override system default selections

{% highlight fortran %}
Abundance_log_mass_frac_min = 101
Abundance_log_mass_frac_max = 0.3
{% endhighlight %}


{% highlight fortran %}
Abundance_show_photosphere_location = .false.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Abundance_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Abundance_file_flag = .false.
Abundance_file_dir = 'png'
Abundance_file_prefix = 'abund_'
Abundance_file_interval = 5
Abundance_file_width = -1
Abundance_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Power_window">Power window <a href="#Power_window" title="Permalink to this location">¶</a></h1>


current model nuclear power profiles

{% highlight fortran %}
Power_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Power_win_width = 6
Power_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Power_xleft = 0.15
Power_xright = 0.85
Power_ybot = 0.15
Power_ytop = 0.85
Power_txt_scale = 1.0
Power_title = 'Power'
{% endhighlight %}


{% highlight fortran %}
Power_xaxis_name = 'mass'
Power_xaxis_reversed = .false.
{% endhighlight %}


{% highlight fortran %}
Power_legend_max_cnt = 16
Power_legend_txt_scale_factor = 0.7
{% endhighlight %}


power xaxis limits -- to override system default selections

{% highlight fortran %}
Power_xmin = -101d0
Power_xmax = -101d0
{% endhighlight %}


power yaxis limits -- to override system default selections

{% highlight fortran %}
Power_ymin = -101d0
Power_ymax = -101d0
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Power_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Power_file_flag = .false.
Power_file_dir = 'png'
Power_file_prefix = 'power_'
Power_file_interval = 5
Power_file_width = -1
Power_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Mixing_window">Mixing window <a href="#Mixing_window" title="Permalink to this location">¶</a></h1>


current model profile of mixing diffusion coefficients

{% highlight fortran %}
Mixing_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Mixing_win_width = 6
Mixing_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Mixing_xleft = 0.15
Mixing_xright = 0.85
Mixing_ybot = 0.15
Mixing_ytop = 0.85
Mixing_txt_scale = 1.0
Mixing_title = 'Mixing'
{% endhighlight %}


{% highlight fortran %}
Mixing_legend_txt_scale_factor = 1
{% endhighlight %}


{% highlight fortran %}
show_Mixing_annotation1 = .false.
show_Mixing_annotation2 = .false.
show_Mixing_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
Mixing_show_rotation_details = .true.
{% endhighlight %}


{% highlight fortran %}
Mixing_xaxis_name = 'mass'
Mixing_xaxis_reversed = .false.
{% endhighlight %}


{% highlight fortran %}
Mixing_xmin = -101d0
Mixing_xmax = -101d0
{% endhighlight %}


{% highlight fortran %}
Mixing_ymin = -101d0
Mixing_ymax = -101d0
Mixing_dymin = -101d0
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Mixing_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Mixing_file_flag = .false.
Mixing_file_dir = 'png'
Mixing_file_prefix = 'mixing_'
Mixing_file_interval = 5
Mixing_file_width = -1
Mixing_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Dynamo_window">Dynamo window <a href="#Dynamo_window" title="Permalink to this location">¶</a></h1>


current model dynamo info

{% highlight fortran %}
Dynamo_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Dynamo_win_width = 6
Dynamo_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Dynamo_xleft = 0.15
Dynamo_xright = 0.85
Dynamo_ybot = 0.15
Dynamo_ytop = 0.85
Dynamo_txt_scale = 1.0
Dynamo_title = 'Dynamo'
{% endhighlight %}


{% highlight fortran %}
Dynamo_legend_txt_scale_factor = 0.7
{% endhighlight %}


{% highlight fortran %}
show_Dynamo_annotation1 = .false.
show_Dynamo_annotation2 = .false.
show_Dynamo_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
Dynamo_xaxis_name = 'mass'
Dynamo_xmin = -101d0
Dynamo_xmax = -101d0
Dynamo_xaxis_reversed = .false.
{% endhighlight %}


{% highlight fortran %}
Dynamo_ymin_left = -101d0
Dynamo_ymax_left = -101d0
Dynamo_dymin_left = -101d0
{% endhighlight %}


{% highlight fortran %}
Dynamo_ymin_right = -101d0
Dynamo_ymax_right = -101d0
Dynamo_dymin_right = -101d0
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Dynamo_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Dynamo_file_flag = .false.
Dynamo_file_dir = 'png'
Dynamo_file_prefix = 'dynamo_'
Dynamo_file_interval = 5
Dynamo_file_width = -1
Dynamo_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Mode_Propagation_window">Mode Propagation window <a href="#Mode_Propagation_window" title="Permalink to this location">¶</a></h1>


for asterseismology

{% highlight fortran %}
Mode_Prop_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Mode_Prop_win_width = 6
Mode_Prop_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Mode_Prop_xleft = 0.15
Mode_Prop_xright = 0.85
Mode_Prop_ybot = 0.15
Mode_Prop_ytop = 0.85
Mode_Prop_txt_scale = 1.0
Mode_Prop_title = 'Mode_Prop'
{% endhighlight %}


{% highlight fortran %}
Mode_Prop_nu_max_obs = -999
{% endhighlight %}


{% highlight fortran %}
Mode_Prop_xaxis_name = 'mass'
Mode_Prop_xaxis_reversed = .false.
{% endhighlight %}


power xaxis limits -- to override system default selections

{% highlight fortran %}
Mode_Prop_xmin = -101d0
Mode_Prop_xmax = -101d0
{% endhighlight %}


power yaxis limits -- to override system default selections

{% highlight fortran %}
Mode_Prop_ymin = -101d0
Mode_Prop_ymax = -101d0
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Mode_Prop_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Mode_Prop_file_flag = .false.
Mode_Prop_file_dir = 'png'
Mode_Prop_file_prefix = 'mode_prop_'
Mode_Prop_file_interval = 5
Mode_Prop_file_width = -1
Mode_Prop_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Summary_Burn_window">Summary Burn window <a href="#Summary_Burn_window" title="Permalink to this location">¶</a></h1>


{% highlight fortran %}
Summary_Burn_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Summary_Burn_win_width = 6
Summary_Burn_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Summary_Burn_xleft = 0.15
Summary_Burn_xright = 0.85
Summary_Burn_ybot = 0.15
Summary_Burn_ytop = 0.80
Summary_Burn_txt_scale = 1.0
Summary_Burn_title = 'Summary_Burn'
Summary_Burn_title_shift = 2.5
{% endhighlight %}


{% highlight fortran %}
Summary_Burn_xaxis_name = 'mass'
Summary_Burn_xaxis_reversed = .false.
{% endhighlight %}


{% highlight fortran %}
Summary_Burn_xmin = -101d0
Summary_Burn_xmax = -101d0
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Summary_Burn_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Summary_Burn_file_flag = .false.
Summary_Burn_file_dir = 'png'
Summary_Burn_file_prefix = 'Summary_Burn_'
Summary_Burn_file_interval = 5
Summary_Burn_file_width = -1
Summary_Burn_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Summary_Profile_window">Summary Profile window <a href="#Summary_Profile_window" title="Permalink to this location">¶</a></h1>


{% highlight fortran %}
Summary_Profile_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_win_width = 6
Summary_Profile_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_xleft = 0.15
Summary_Profile_xright = 0.85
Summary_Profile_ybot = 0.15
Summary_Profile_ytop = 0.85
Summary_Profile_txt_scale = 1.0
Summary_Profile_title = 'Summary_Profile'
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_xaxis_name = 'mass'
Summary_Profile_xaxis_reversed = .false.
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_xmin = -101d0
Summary_Profile_xmax = -101d0
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(:) = ''
{% endhighlight %}


if name len=0, then skip this one

{% highlight fortran %}
Summary_Profile_legend(:) = ''
Summary_Profile_scaled_value(:) = .true.
{% endhighlight %}


if true, show values scaled max to 1.0 and min to 0.0
if false, show the unmapped values (which should be in range 0.0 to 1.0)
typically set .false. for mass fractions; .true. for everything else.

{% highlight fortran %}
Summary_Profile_num_lines = 11
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(1) = 'x'
Summary_Profile_legend(1) = 'X'
Summary_Profile_scaled_value(1) = .false.
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(2) = 'y'
Summary_Profile_legend(2) = 'Y'
Summary_Profile_scaled_value(2) = .false.
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(3) = 'log_j_rot'
Summary_Profile_legend(3) = 'log j rel'
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(4) = 'log_omega'
Summary_Profile_legend(4) = 'log \(0650) rel'
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(5) = 'mass'
Summary_Profile_legend(5) = 'm rel'
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(6) = 'radius'
Summary_Profile_legend(6) = 'r rel'
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(7) = 'eps_nuc'
Summary_Profile_legend(7) = 'eps nuc rel'
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(8) = 'entropy'
Summary_Profile_legend(8) = 'entropy rel'
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(9) = 'opacity'
Summary_Profile_legend(9) = 'opacity rel'
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(10) = 'luminosity'
Summary_Profile_legend(10) = 'L rel'
{% endhighlight %}


{% highlight fortran %}
Summary_Profile_name(11) = 'temperature'
Summary_Profile_legend(11) = 'T rel'
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Summary_Profile_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Summary_Profile_file_flag = .false.
Summary_Profile_file_dir = 'png'
Summary_Profile_file_prefix = 'Summary_Profile_'
Summary_Profile_file_interval = 5
Summary_Profile_file_width = -1
Summary_Profile_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Summary_History_window">Summary History window <a href="#Summary_History_window" title="Permalink to this location">¶</a></h1>


{% highlight fortran %}
Summary_History_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Summary_History_win_width = 6
Summary_History_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Summary_History_xleft = 0.15
Summary_History_xright = 0.85
Summary_History_ybot = 0.15
Summary_History_ytop = 0.85
Summary_History_txt_scale = 1.0
Summary_History_title = 'Summary_History'
{% endhighlight %}


{% highlight fortran %}
Summary_History_xmax = -1
Summary_History_xmin = -1
Summary_History_max_width = -1
{% endhighlight %}


{% highlight fortran %}
Summary_History_name(:) = ''
{% endhighlight %}


if name len=0, then skip this one

{% highlight fortran %}
Summary_History_legend(:) = ''
Summary_History_scaled_value(:) = .true.
{% endhighlight %}


if true, show values scaled max to 1.0 and min to 0.0
if false, show the unmapped values (which should be in range 0.0 to 1.0)
typically set .false. for mass fractions; .true. for everything else.

{% highlight fortran %}
Summary_History_num_lines = 7
{% endhighlight %}


{% highlight fortran %}
Summary_History_name(1) = 'log_center_T'
Summary_History_legend(1) = 'log T\dc\u rel'
{% endhighlight %}


{% highlight fortran %}
Summary_History_name(2) = 'log_center_Rho'
Summary_History_legend(2) = 'log Rho\dc\u rel'
{% endhighlight %}


{% highlight fortran %}
Summary_History_name(3) = 'log_L'
Summary_History_legend(3) = 'log L rel'
{% endhighlight %}


{% highlight fortran %}
Summary_History_name(4) = 'log_Teff'
Summary_History_legend(4) = 'log Teff rel'
{% endhighlight %}


{% highlight fortran %}
Summary_History_name(5) = 'log_R'
Summary_History_legend(5) = 'log R rel'
{% endhighlight %}


{% highlight fortran %}
Summary_History_name(6) = 'center_h1'
Summary_History_legend(6) = 'h1\dc\u'
Summary_History_scaled_value(6) = .false.
{% endhighlight %}


{% highlight fortran %}
Summary_History_name(7) = 'center_he4'
Summary_History_legend(7) = 'he4\dc\u'
Summary_History_scaled_value(7) = .false.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Summary_History_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Summary_History_file_flag = .false.
Summary_History_file_dir = 'png'
Summary_History_file_prefix = 'Summary_History_'
Summary_History_file_interval = 5
Summary_History_file_width = -1
Summary_History_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Kippenhahn_window">"Kippenhahn" window <a href="#Kippenhahn_window" title="Permalink to this location">¶</a></h1>


history of convection and more.

    your history_columns.list needs to include
           star_mass
           mixing_regions 40    -- 40 can be changed if you wish
           burning_regions 80    -- 80 can be changed if you wish
    and if you have set M_center > 0, then also include
           log_xmstar
    if you want to show luminosities, include some or all of
           log_L, log_Lneu, log_LH, log_LHe
    if you want to show mass boundaries, then include some or all of
           he_core_mass, c_core_mass, o_core_mass, si_core_mass, fe_core_mass

{% highlight fortran %}
Kipp_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Kipp_win_width = 7
Kipp_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Kipp_xleft = 0.15
Kipp_xright = 0.85
Kipp_ybot = 0.15
Kipp_ytop = 0.85
Kipp_txt_scale = 1.0
Kipp_title = 'Kipp'
{% endhighlight %}


Set xaxis

{% highlight fortran %}
Kipp_step_xmin = -1
Kipp_step_xmax = -1
{% endhighlight %}


These can be combined with Kipp_{xmin,xmax} options

{% highlight fortran %}
Kipp_max_width = -1
{% endhighlight %}


Negative implies show all steps. This overrides `Kipp_step_xmin`

{% highlight fortran %}
Kipp_xaxis_name = 'model_number'
{% endhighlight %}


are `model_number` or `star_age`

{% highlight fortran %}
Kipp_xaxis_log = .false.
Kipp_xmin = -101d0
Kipp_xmax = -101d0
Kipp_xmargin = 0.0
Kipp_xaxis_reversed = .false.
Kipp_xaxis_in_seconds = .false.
{% endhighlight %}


Requires `Kipp_xaxis_name='star_age'`

{% highlight fortran %}
Kipp_xaxis_in_Myr = .false.
{% endhighlight %}


Requires `Kipp_xaxis_name='star_age'`

{% highlight fortran %}
Kipp_xaxis_time_from_present = .false.
{% endhighlight %}


plots `star_age-max(star_age)`
Requires `Kipp_xaxis_name='star_age'`

bounds for mass yaxis

{% highlight fortran %}
Kipp_mass_max = -1
Kipp_mass_min = -1
Kipp_mass_margin = 0.01
{% endhighlight %}


bounds for luminosity yaxis

{% highlight fortran %}
Kipp_lgL_max = -101d0
Kipp_lgL_min = -101d0
Kipp_lgL_margin = 0.1
{% endhighlight %}


{% highlight fortran %}
Kipp_show_mixing = .true.
{% endhighlight %}


this uses the `mixing_regions` specified in your `history_columns.list`

{% highlight fortran %}
Kipp_show_burn = .true.
{% endhighlight %}


this uses the `burning_regions` specified in your `history_columns.list`

{% highlight fortran %}
Kipp_show_luminosities = .false.
{% endhighlight %}


to use this option, include the following in your `history_columns.list`
`log_L`, `log_Lneu`, `log_LH`, `log_LHe`

{% highlight fortran %}
Kipp_show_mass_boundaries = .true.
{% endhighlight %}


to use this option, include the following in your `history_columns.list`
`he_core_mass`, `c_core_mass`, `o_core_mass`, `si_core_mass`, `fe_core_mass`

{% highlight fortran %}
Kipp_mix_line_weight = 10
Kipp_mix_interval = 4
{% endhighlight %}


show mixing for steps with `mod(model_number, Kipp_mix_interval) = 0.`

{% highlight fortran %}
Kipp_burn_line_weight = 14
{% endhighlight %}


{% highlight fortran %}
Kipp_burn_type_cutoff = 0d0
{% endhighlight %}


show burn lines only for abs(log(eps)) > Kipp_burn_type_cutoff

{% highlight fortran %}
Kipp_luminosities_line_weight = 8
Kipp_masses_line_weight = 8
{% endhighlight %}


{% highlight fortran %}
show_Kipp_annotation1 = .false.
show_Kipp_annotation2 = .false.
show_Kipp_annotation3 = .false.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Kipp_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Kipp_file_flag = .false.
Kipp_file_dir = 'png'
Kipp_file_prefix = 'conv_'
Kipp_file_interval = 5
Kipp_file_width = -1
Kipp_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="rti_window">"rti" window <a href="#rti_window" title="Permalink to this location">¶</a></h1>


history of Rayleigh Taylor instabilities.

    your history_columns.list needs to include
           star_mass
           rti_regions 40    -- 40 can be changed if you wish
    and if you have set M_center > 0, then also include
           log_xmstar

{% highlight fortran %}
rti_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
rti_win_width = 7
rti_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
rti_xleft = 0.15
rti_xright = 0.85
rti_ybot = 0.15
rti_ytop = 0.85
rti_txt_scale = 1.0
rti_title = 'Rayleigh Taylor Instability'
{% endhighlight %}


Set xaxis

{% highlight fortran %}
rti_step_xmin = -1
rti_step_xmax = -1
{% endhighlight %}


These can be combined with `rti_{xmin,xmax}` options

{% highlight fortran %}
rti_max_width = -1
{% endhighlight %}


Negative implies show all steps. This overrides `rti_step_xmin`

{% highlight fortran %}
rti_xaxis_name = 'model_number'
{% endhighlight %}


are `model_number` or `star_age`

{% highlight fortran %}
rti_xaxis_log = .false.
rti_xmin = -101d0
rti_xmax = -101d0
rti_xmargin = 0.0
rti_xaxis_reversed = .false.
rti_xaxis_in_seconds = .false.
{% endhighlight %}


Requires `rti_xaxis_name='star_age'`

{% highlight fortran %}
rti_xaxis_in_Myr = .false.
{% endhighlight %}


Requires `rti_xaxis_name='star_age'`

{% highlight fortran %}
rti_xaxis_time_from_present = .false.
{% endhighlight %}


plots `star_age-max(star_age)`
Requires `rti_xaxis_name='star_age'`

bounds for mass yaxis

{% highlight fortran %}
rti_mass_max = -1
rti_mass_min = -1
rti_mass_margin = 0.01
{% endhighlight %}


{% highlight fortran %}
rti_line_weight = 10
rti_interval = 4
{% endhighlight %}


show rti for steps with `mod(model_number, rti_interval) = 0.`

{% highlight fortran %}
show_rti_annotation1 = .false.
show_rti_annotation2 = .false.
show_rti_annotation3 = .false.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
rti_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
rti_file_flag = .false.
rti_file_dir = 'png'
rti_file_prefix = 'rti_'
rti_file_interval = 5
rti_file_width = -1
rti_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="TRho_window">TRho window <a href="#TRho_window" title="Permalink to this location">¶</a></h1>


history of central temperature vs. density

{% highlight fortran %}
TRho_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
TRho_win_width = 6
TRho_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
TRho_xleft = 0.15
TRho_xright = 0.85
TRho_ybot = 0.15
TRho_ytop = 0.85
TRho_txt_scale = 1.0
TRho_title = 'TRho'
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
TRho_logT_min = -101d0
TRho_logT_max = -101d0
TRho_logRho_min = -101d0
TRho_logRho_max = -101d0
{% endhighlight %}


{% highlight fortran %}
TRho_logT_margin = 0.1
TRho_logRho_margin = 0.1
TRho_logRho_dlogRho_min = -1
TRho_logT_dlogT_min = -1
{% endhighlight %}


{% highlight fortran %}
TRho_step_min = -1
TRho_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_TRho_degeneracy_line = .true.
{% endhighlight %}


{% highlight fortran %}
show_TRho_annotation1 = .false.
show_TRho_annotation2 = .false.
show_TRho_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
TRho_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
TRho_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
TRho_file_flag = .false.
TRho_file_dir = 'png'
TRho_file_prefix = 'trho_'
TRho_file_interval = 5
TRho_file_width = -1
TRho_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="HR_window">HR window <a href="#HR_window" title="Permalink to this location">¶</a></h1>


history of `lg_L` vs. `lg_Teff`

{% highlight fortran %}
HR_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
HR_win_width = 6
HR_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
HR_xleft = 0.15
HR_xright = 0.85
HR_ybot = 0.15
HR_ytop = 0.85
HR_txt_scale = 1.0
HR_title = 'HR'
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
HR_logT_min = -101d0
HR_logT_max = -101d0
HR_logL_min = -101d0
HR_logL_max = -101d0
{% endhighlight %}


{% highlight fortran %}
HR_logL_margin = 0.1
HR_logT_margin = 0.1
HR_dlogT_min = -1
HR_dlogL_min = -1
{% endhighlight %}


{% highlight fortran %}
HR_step_min = -1
HR_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_HR_classical_instability_strip = .false.
show_HR_Mira_instability_region = .false.
show_HR_WD_instabilities = .false.
{% endhighlight %}


{% highlight fortran %}
show_HR_target_box = .false.
HR_target_n_sigma = -3
HR_target_logL = 0
HR_target_logL_sigma = 0
HR_target_logT = 0
HR_target_logT_sigma = 0
{% endhighlight %}


{% highlight fortran %}
show_HR_annotation1 = .false.
show_HR_annotation2 = .false.
show_HR_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
HR_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
HR_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
HR_file_flag = .false.
HR_file_dir = 'png'
HR_file_prefix = 'hr_'
HR_file_interval = 5
HR_file_width = -1
HR_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="logL_Teff_window">logL_Teff window <a href="#logL_Teff_window" title="Permalink to this location">¶</a></h1>


history of logL vs. Teff

{% highlight fortran %}
logL_Teff_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
logL_Teff_win_width = 6
logL_Teff_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
logL_Teff_xleft = 0.15
logL_Teff_xright = 0.85
logL_Teff_ybot = 0.15
logL_Teff_ytop = 0.85
logL_Teff_txt_scale = 1.0
logL_Teff_title = 'logL_Teff'
{% endhighlight %}


{% highlight fortran %}
show_logL_Teff_target_box = .false.
logL_Teff_target_n_sigma = -3
logL_Teff_target_logL = 4.00d0
logL_Teff_target_logL_sigma = 0.06d0
logL_Teff_target_Teff = 6095d0
logL_Teff_target_Teff_sigma = 65
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
logL_Teff_logL_min = -101d0
logL_Teff_logL_max = -101d0
logL_Teff_Teff_min = -101d0
logL_Teff_Teff_max = -101d0
{% endhighlight %}


{% highlight fortran %}
logL_Teff_Teff_margin = 0.1
logL_Teff_logL_margin = 0.1
logL_Teff_dTeff_min = -1
logL_Teff_dlogL_min = -1
{% endhighlight %}


{% highlight fortran %}
logL_Teff_step_min = -1
logL_Teff_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_logL_Teff_annotation1 = .false.
show_logL_Teff_annotation2 = .false.
show_logL_Teff_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
logL_Teff_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
logL_Teff_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
logL_Teff_file_flag = .false.
logL_Teff_file_dir = 'png'
logL_Teff_file_prefix = 'logL_Teff_'
logL_Teff_file_interval = 5
logL_Teff_file_width = -1
logL_Teff_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="logL_R_window">logL_R window <a href="#logL_R_window" title="Permalink to this location">¶</a></h1>


history of logL vs. R

{% highlight fortran %}
logL_R_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
logL_R_win_width = 6
logL_R_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
logL_R_xleft = 0.15
logL_R_xright = 0.85
logL_R_ybot = 0.15
logL_R_ytop = 0.85
logL_R_txt_scale = 1.0
logL_R_title = 'logL_R'
{% endhighlight %}


{% highlight fortran %}
show_logL_photosphere_r = .false.
{% endhighlight %}


{% highlight fortran %}
show_logL_R_target_box = .false.
logL_R_target_n_sigma = -3
logL_R_target_logL = 4.00d0
logL_R_target_logL_sigma = 0.06d0
logL_R_target_R = 6095d0
logL_R_target_R_sigma = 65
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
logL_R_logL_min = -101d0
logL_R_logL_max = -101d0
logL_R_R_min = -101d0
logL_R_R_max = -101d0
{% endhighlight %}


{% highlight fortran %}
logL_R_R_margin = 0.1
logL_R_logL_margin = 0.1
logL_R_dR_min = -1
logL_R_dlogL_min = -1
{% endhighlight %}


{% highlight fortran %}
logL_R_step_min = -1
logL_R_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_logL_R_annotation1 = .false.
show_logL_R_annotation2 = .false.
show_logL_R_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
logL_R_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
logL_R_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
logL_R_file_flag = .false.
logL_R_file_dir = 'png'
logL_R_file_prefix = 'logL_R_'
logL_R_file_interval = 5
logL_R_file_width = -1
logL_R_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="logL_v_window">logL_v window <a href="#logL_v_window" title="Permalink to this location">¶</a></h1>


history of logL vs. v surface or photosphere

{% highlight fortran %}
logL_v_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
logL_v_win_width = 6
logL_v_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
logL_v_xleft = 0.15
logL_v_xright = 0.85
logL_v_ybot = 0.15
logL_v_ytop = 0.85
logL_v_txt_scale = 1.0
logL_v_title = 'logL_v'
{% endhighlight %}


{% highlight fortran %}
show_logL_photosphere_v = .false.
{% endhighlight %}


{% highlight fortran %}
show_logL_v_target_box = .false.
logL_v_target_n_sigma = -3
logL_v_target_logL = 4.00d0
logL_v_target_logL_sigma = 0.06d0
logL_v_target_v = 6095d0
logL_v_target_v_sigma = 65
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
logL_v_logL_min = -101d0
logL_v_logL_max = -101d0
logL_v_v_min = -101d0
logL_v_v_max = -101d0
{% endhighlight %}


{% highlight fortran %}
logL_v_v_margin = 0.1
logL_v_logL_margin = 0.1
logL_v_dv_min = -1
logL_v_dlogL_min = -1
{% endhighlight %}


{% highlight fortran %}
logL_v_step_min = -1
logL_v_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_logL_v_annotation1 = .false.
show_logL_v_annotation2 = .false.
show_logL_v_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
logL_v_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
logl_v_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
logL_v_file_flag = .false.
logL_v_file_dir = 'png'
logL_v_file_prefix = 'logL_v_'
logL_v_file_interval = 5
logL_v_file_width = -1
logL_v_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="L_Teff_window">L_Teff window <a href="#L_Teff_window" title="Permalink to this location">¶</a></h1>


history of L vs. Teff

{% highlight fortran %}
L_Teff_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
L_Teff_win_width = 6
L_Teff_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
L_Teff_xleft = 0.15
L_Teff_xright = 0.85
L_Teff_ybot = 0.15
L_Teff_ytop = 0.85
L_Teff_txt_scale = 1.0
L_Teff_title = 'L_Teff'
{% endhighlight %}


{% highlight fortran %}
show_L_Teff_target_box = .false.
L_Teff_target_n_sigma = -3
L_Teff_target_L = 4.00d0
L_Teff_target_L_sigma = 0.06d0
L_Teff_target_Teff = 6095d0
L_Teff_target_Teff_sigma = 65
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
L_Teff_L_min = -101d0
L_Teff_L_max = -101d0
L_Teff_Teff_min = -101d0
L_Teff_Teff_max = -101d0
{% endhighlight %}


{% highlight fortran %}
L_Teff_Teff_margin = 0.1
L_Teff_L_margin = 0.1
L_Teff_dTeff_min = -1
L_Teff_dL_min = -1
{% endhighlight %}


{% highlight fortran %}
L_Teff_step_min = -1
L_Teff_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_L_Teff_annotation1 = .false.
show_L_Teff_annotation2 = .false.
show_L_Teff_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
L_Teff_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
L_Teff_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
L_Teff_file_flag = .false.
L_Teff_file_dir = 'png'
L_Teff_file_prefix = 'L_Teff_'
L_Teff_file_interval = 5
L_Teff_file_width = -1
L_Teff_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="L_v_window">L_v window <a href="#L_v_window" title="Permalink to this location">¶</a></h1>


history of L vs. surface velocity

{% highlight fortran %}
L_v_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
L_v_win_width = 6
L_v_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
L_v_xleft = 0.15
L_v_xright = 0.85
L_v_ybot = 0.15
L_v_ytop = 0.85
L_v_txt_scale = 1.0
L_v_title = 'L_v'
{% endhighlight %}


{% highlight fortran %}
show_L_v_target_box = .false.
L_v_target_n_sigma = -3
L_v_target_L = 4.00d0
L_v_target_L_sigma = 0.06d0
L_v_target_v = 6095d0
L_v_target_v_sigma = 65
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
L_v_L_min = -101d0
L_v_L_max = -101d0
L_v_v_min = -101d0
L_v_v_max = -101d0
{% endhighlight %}


{% highlight fortran %}
L_v_v_margin = 0.1
L_v_L_margin = 0.1
L_v_dv_min = -1
L_v_dL_min = -1
{% endhighlight %}


{% highlight fortran %}
L_v_step_min = -1
L_v_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_L_v_annotation1 = .false.
show_L_v_annotation2 = .false.
show_L_v_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
L_v_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
L_v_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
L_v_file_flag = .false.
L_v_file_dir = 'png'
L_v_file_prefix = 'L_v_'
L_v_file_interval = 5
L_v_file_width = -1
L_v_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="L_R_window">L_R window <a href="#L_R_window" title="Permalink to this location">¶</a></h1>


history of L vs. R

{% highlight fortran %}
L_R_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
L_R_win_width = 6
L_R_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
L_R_xleft = 0.15
L_R_xright = 0.85
L_R_ybot = 0.15
L_R_ytop = 0.85
L_R_txt_scale = 1.0
L_R_title = 'L_R'
{% endhighlight %}


{% highlight fortran %}
show_L_R_target_box = .false.
L_R_target_n_sigma = -3
L_R_target_L = 4.00d0
L_R_target_L_sigma = 0.06d0
L_R_target_R = 6095d0
L_R_target_R_sigma = 65
{% endhighlight %}


axis limits -- to oRerride system default selections

{% highlight fortran %}
L_R_L_min = -101d0
L_R_L_max = -101d0
L_R_R_min = -101d0
L_R_R_max = -101d0
{% endhighlight %}


{% highlight fortran %}
L_R_R_margin = 0.1
L_R_L_margin = 0.1
L_R_dR_min = -1
L_R_dL_min = -1
{% endhighlight %}


{% highlight fortran %}
L_R_step_min = -1
L_R_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_L_R_annotation1 = .false.
show_L_R_annotation2 = .false.
show_L_R_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
L_R_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
L_R_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
L_R_file_flag = .false.
L_R_file_dir = 'png'
L_R_file_prefix = 'L_R_'
L_R_file_interval = 5
L_R_file_width = -1
L_R_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="R_Teff_window">R_Teff window <a href="#R_Teff_window" title="Permalink to this location">¶</a></h1>


history of R vs. Teff

{% highlight fortran %}
R_Teff_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
R_Teff_win_width = 6
R_Teff_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
R_Teff_xleft = 0.15
R_Teff_xright = 0.85
R_Teff_ybot = 0.15
R_Teff_ytop = 0.85
R_Teff_txt_scale = 1.0
R_Teff_title = 'R_Teff'
{% endhighlight %}


{% highlight fortran %}
show_R_Teff_target_box = .false.
R_Teff_target_n_sigma = -3
R_Teff_target_R = 4.00d0
R_Teff_target_R_sigma = 0.06d0
R_Teff_target_Teff = 6095d0
R_Teff_target_Teff_sigma = 65
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
R_Teff_R_min = -101d0
R_Teff_R_max = -101d0
R_Teff_Teff_min = -101d0
R_Teff_Teff_max = -101d0
{% endhighlight %}


{% highlight fortran %}
R_Teff_Teff_margin = 0.1
R_Teff_R_margin = 0.1
R_Teff_dTeff_min = -1
R_Teff_dR_min = -1
{% endhighlight %}


{% highlight fortran %}
R_Teff_step_min = -1
R_Teff_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_R_Teff_annotation1 = .false.
show_R_Teff_annotation2 = .false.
show_R_Teff_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
R_Teff_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
R_Teff_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
R_Teff_file_flag = .false.
R_Teff_file_dir = 'png'
R_Teff_file_prefix = 'R_Teff_'
R_Teff_file_interval = 5
R_Teff_file_width = -1
R_Teff_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="R_L_window">R_L window <a href="#R_L_window" title="Permalink to this location">¶</a></h1>


history of R vs. L

{% highlight fortran %}
R_L_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
R_L_win_width = 6
R_L_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
R_L_xleft = 0.15
R_L_xright = 0.85
R_L_ybot = 0.15
R_L_ytop = 0.85
R_L_txt_scale = 1.0
R_L_title = 'R_L'
{% endhighlight %}


{% highlight fortran %}
show_R_L_target_box = .false.
R_L_target_n_sigma = -3
R_L_target_R = 4.00d0
R_L_target_R_sigma = 0.06d0
R_L_target_L = 6095d0
R_L_target_L_sigma = 65
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
R_L_R_min = -101d0
R_L_R_max = -101d0
R_L_L_min = -101d0
R_L_L_max = -101d0
{% endhighlight %}


{% highlight fortran %}
R_L_L_margin = 0.1
R_L_R_margin = 0.1
R_L_dL_min = -1
R_L_dR_min = -1
{% endhighlight %}


{% highlight fortran %}
R_L_step_min = -1
R_L_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_R_L_annotation1 = .false.
show_R_L_annotation2 = .false.
show_R_L_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
R_L_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
R_L_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
R_L_file_flag = .false.
R_L_file_dir = 'png'
R_L_file_prefix = 'R_L_'
R_L_file_interval = 5
R_L_file_width = -1
R_L_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="logg_Teff_window">logg_Teff window <a href="#logg_Teff_window" title="Permalink to this location">¶</a></h1>


history of logg vs. Teff

{% highlight fortran %}
logg_Teff_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
logg_Teff_win_width = 6
logg_Teff_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
logg_Teff_xleft = 0.15
logg_Teff_xright = 0.85
logg_Teff_ybot = 0.15
logg_Teff_ytop = 0.85
logg_Teff_txt_scale = 1.0
logg_Teff_title = 'logg_Teff'
{% endhighlight %}


{% highlight fortran %}
show_logg_Teff_target_box = .false.
logg_Teff_target_n_sigma = -3
logg_Teff_target_logg = 4.00d0
logg_Teff_target_logg_sigma = 0.06d0
logg_Teff_target_Teff = 6095d0
logg_Teff_target_Teff_sigma = 65
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
logg_Teff_logg_min = -101d0
logg_Teff_logg_max = -101d0
logg_Teff_Teff_min = -101d0
logg_Teff_Teff_max = -101d0
{% endhighlight %}


{% highlight fortran %}
logg_Teff_Teff_margin = 0.1
logg_Teff_logg_margin = 0.1
logg_Teff_dTeff_min = -1
logg_Teff_dlogg_min = -1
{% endhighlight %}


{% highlight fortran %}
logg_Teff_step_min = -1
logg_Teff_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_logg_Teff_annotation1 = .false.
show_logg_Teff_annotation2 = .false.
show_logg_Teff_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
logg_Teff_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
logg_Teff_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
logg_Teff_file_flag = .false.
logg_Teff_file_dir = 'png'
logg_Teff_file_prefix = 'logg_Teff_'
logg_Teff_file_interval = 5
logg_Teff_file_width = -1
logg_Teff_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="logg_logT_window">logg_logT window <a href="#logg_logT_window" title="Permalink to this location">¶</a></h1>


history of logg vs. log Teff

{% highlight fortran %}
logg_logT_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
logg_logT_win_width = 6
logg_logT_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
logg_logT_xleft = 0.15
logg_logT_xright = 0.85
logg_logT_ybot = 0.15
logg_logT_ytop = 0.85
logg_logT_txt_scale = 1.0
logg_logT_title = 'logg_logT'
{% endhighlight %}


{% highlight fortran %}
show_logg_logT_target_box = .false.
logg_logT_target_n_sigma = -3
logg_logT_target_logg = 4.00d0
logg_logT_target_logg_sigma = 0.06d0
logg_logT_target_logT = 3.785d0
logg_logT_target_logT_sigma = 0.00461d0
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
logg_logT_logg_min = -101d0
logg_logT_logg_max = -101d0
logg_logT_logT_min = -101d0
logg_logT_logT_max = -101d0
{% endhighlight %}


{% highlight fortran %}
logg_logT_logg_margin = 0.1
logg_logT_logT_margin = 0.1
logg_logT_dlogT_min = -1
logg_logT_dlogg_min = -1
{% endhighlight %}


{% highlight fortran %}
logg_logT_step_min = -1
logg_logT_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_logg_logT_annotation1 = .false.
show_logg_logT_annotation2 = .false.
show_logg_logT_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
logg_logT_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
logg_logT_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
logg_logT_file_flag = .false.
logg_logT_file_dir = 'png'
logg_logT_file_prefix = 'logg_logT_'
logg_logT_file_interval = 5
logg_logT_file_width = -1
logg_logT_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="dPg_dnu_window">dPg_dnu window <a href="#dPg_dnu_window" title="Permalink to this location">¶</a></h1>


`delta_Pg` vs. `delta_nu` (for asteroseismology)

{% highlight fortran %}
dPg_dnu_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
dPg_dnu_win_width = 6
dPg_dnu_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
dPg_dnu_xleft = 0.15
dPg_dnu_xright = 0.85
dPg_dnu_ybot = 0.15
dPg_dnu_ytop = 0.85
dPg_dnu_txt_scale = 1.0
dPg_dnu_title = 'dPg_dnu'
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
dPg_dnu_delta_nu_min = -101d0
dPg_dnu_delta_nu_max = -101d0
dPg_dnu_delta_Pg_min = -101d0
dPg_dnu_delta_Pg_max = -101d0
{% endhighlight %}


{% highlight fortran %}
dPg_dnu_delta_nu_margin = 0.1
dPg_dnu_delta_Pg_margin = 0.1
dPg_dnu_d_delta_nu_min = -1
dPg_dnu_d_delta_Pg_min = -1
{% endhighlight %}


{% highlight fortran %}
dPg_dnu_step_min = -1
dPg_dnu_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_dPg_dnu_annotation1 = .false.
show_dPg_dnu_annotation2 = .false.
show_dPg_dnu_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
dPg_dnu_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
dPg_dnu_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
dPg_dnu_file_flag = .false.
dPg_dnu_file_dir = 'png'
dPg_dnu_file_prefix = 'dPg_dnu_'
dPg_dnu_file_interval = 5
dPg_dnu_file_width = -1
dPg_dnu_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Network_window">Network window <a href="#Network_window" title="Permalink to this location">¶</a></h1>


Shows N vs Z for isotopes in current net

{% highlight fortran %}
Network_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Network_win_width = 6
Network_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Network_xleft = 0.15
Network_xright = 0.85
Network_ybot = 0.15
Network_ytop = 0.85
Network_txt_scale = 1.0
Network_title = 'Network'
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
Network_nmin = -101d0
Network_nmax = -101d0
Network_zmin = -101d0
Network_zmax = -101d0
{% endhighlight %}


Show mass fraction as a coloured square

{% highlight fortran %}
Network_show_mass_fraction = .true.
{% endhighlight %}


Limits on mass fractions to show

{% highlight fortran %}
Network_log_mass_frac_min = -5.0d0
Network_log_mass_frac_max = 0.0d0
{% endhighlight %}


Label Y axis with element name

{% highlight fortran %}
Network_show_element_names = .true.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Network_use_decorator = .false.
{% endhighlight %}


Add colorbar 

{% highlight fortran %}
Network_show_colorbar = .true.
{% endhighlight %}


file output

{% highlight fortran %}
Network_file_flag = .false.
Network_file_dir = 'png'
Network_file_prefix = 'Network_'
Network_file_interval = 5
Network_file_width = -1
Network_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Production_window">Production window <a href="#Production_window" title="Permalink to this location">¶</a></h1>


Plots the abundance for each stable isotope divided by the initial stable composition

{% highlight fortran %}
Production_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Production_win_width = 6
Production_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Production_xleft = 0.15
Production_xright = 0.85
Production_ybot = 0.15
Production_ytop = 0.85
Production_txt_scale = 1.0
Production_title = 'Production'
{% endhighlight %}


axis limits -- to override system default selections

{% highlight fortran %}
Production_amin = -101d0
Production_amax = -101d0
Production_ymin = -101d0
Production_ymax = -101d0
{% endhighlight %}


Mass range of star to show

{% highlight fortran %}
Production_min_mass = -101d0
Production_max_mass = -101d0
{% endhighlight %}


Min log mass fraction an isotope must have to be shown

{% highlight fortran %}
Production_min_mass_frac = -5.0d0
{% endhighlight %}


Add labels with element names

{% highlight fortran %}
Production_show_element_names = .true.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Production_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Production_file_flag = .false.
Production_file_dir = 'png'
Production_file_prefix = 'Production_'
Production_file_interval = 5
Production_file_width = -1
Production_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Profile_Panels">Profile Panels <a href="#Profile_Panels" title="Permalink to this location">¶</a></h1>


for tracking shocks

{% highlight fortran %}
Profile_Panels_show_Mach_1_location = .false.
Profile_Panels_show_photosphere_location = .false.
Profile_Panels_xwidth_left_of_shock = -1
Profile_Panels_xwidth_right_of_shock = -1
Profile_Panels_xwidth_left_div_shock_value = -1
Profile_Panels_xwidth_right_div_shock_value = -1
{% endhighlight %}


these apply to all Profile Panels plots
don't use if value is <= 0
else put location of shock at center of xaxis, and
set xmin and xmax so that (xmax - xmin)/center_value = this.

<h3 id="Profile_Panels1">Profile_Panels1 <a href="#Profile_Panels1" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Profile_Panels1_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels1_win_width = 6
Profile_Panels1_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Profile_Panels1_xleft = 0.15
Profile_Panels1_xright = 0.85
Profile_Panels1_ybot = 0.15
Profile_Panels1_ytop = 0.85
Profile_Panels1_txt_scale = 1.0
Profile_Panels1_title = 'Profile Panels1'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels1_xaxis_name = 'mass'
Profile_Panels1_xaxis_reversed = .false.
Profile_Panels1_xmin = -101d0
Profile_Panels1_xmax = -101d0
Profile_Panels1_xmargin = 0d0
Profile_Panels1_show_mix_regions_on_xaxis = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels1_yaxis_name(:) = ''
Profile_Panels1_yaxis_reversed(:) = .false.
Profile_Panels1_yaxis_log(:) = .false.
Profile_Panels1_ymin(:) = -101d0
Profile_Panels1_ymax(:) = -101d0
Profile_Panels1_ycenter(:) = -101d0
Profile_Panels1_ymargin(:) = 0.1
Profile_Panels1_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels1_other_yaxis_name(:) = ''
Profile_Panels1_other_yaxis_reversed(:) = .false.
Profile_Panels1_other_yaxis_log(:) = .false.
Profile_Panels1_other_ymin(:) = -101d0
Profile_Panels1_other_ymax(:) = -101d0
Profile_Panels1_other_ycenter(:) = -101d0
Profile_Panels1_other_ymargin(:) = 0.1
Profile_Panels1_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels1_show_grid = .false.
{% endhighlight %}


setup default plot

{% highlight fortran %}
Profile_Panels1_num_panels = 2
Profile_Panels1_yaxis_name(1) = 'logT'
Profile_Panels1_other_yaxis_name(1) = 'entropy'
Profile_Panels1_yaxis_name(2) = 'logRho'
Profile_Panels1_other_yaxis_name(2) = 'logP'
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Profile_Panels1_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Profile_Panels1_file_flag = .false.
Profile_Panels1_file_dir = 'png'
Profile_Panels1_file_prefix = 'profile_panels1_'
Profile_Panels1_file_interval = 5
Profile_Panels1_file_width = -1
Profile_Panels1_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Profile_Panels2">Profile_Panels2 <a href="#Profile_Panels2" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Profile_Panels2_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels2_win_width = 6
Profile_Panels2_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Profile_Panels2_xleft = 0.15
Profile_Panels2_xright = 0.85
Profile_Panels2_ybot = 0.15
Profile_Panels2_ytop = 0.85
Profile_Panels2_txt_scale = 1.0
Profile_Panels2_title = 'Profile Panels2'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels2_xaxis_name = ''
Profile_Panels2_xaxis_reversed = .false.
Profile_Panels2_xmin = -101d0
Profile_Panels2_xmax = -101d0
Profile_Panels2_xmargin = 0d0
Profile_Panels2_show_mix_regions_on_xaxis = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels2_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
Profile_Panels2_yaxis_name(:) = ''
Profile_Panels2_yaxis_reversed(:) = .false.
Profile_Panels2_yaxis_log(:) = .false.
Profile_Panels2_ymin(:) = -101d0
Profile_Panels2_ymax(:) = -101d0
Profile_Panels2_ycenter(:) = -101d0
Profile_Panels2_ymargin(:) = 0.1
Profile_Panels2_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels2_other_yaxis_name(:) = ''
Profile_Panels2_other_yaxis_reversed(:) = .false.
Profile_Panels2_other_yaxis_log(:) = .false.
Profile_Panels2_other_ymin(:) = -101d0
Profile_Panels2_other_ymax(:) = -101d0
Profile_Panels2_other_ycenter(:) = -101d0
Profile_Panels2_other_ymargin(:) = 0.1
Profile_Panels2_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels2_show_grid = .false.
{% endhighlight %}


setup default plot

{% highlight fortran %}
Profile_Panels2_win_aspect_ratio = 1.25
Profile_Panels2_txt_scale = 0.9
Profile_Panels2_ybot = 0.1
Profile_Panels2_ytop = 0.9
Profile_Panels2_title = 'Abundance-Power'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels2_xaxis_name = 'logP'
Profile_Panels2_xaxis_reversed = .true.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels2_num_panels = 2
Profile_Panels2_yaxis_name(1) = 'Abundance'
Profile_Panels2_yaxis_name(2) = 'Power'
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Profile_Panels2_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Profile_Panels2_file_flag = .false.
Profile_Panels2_file_dir = 'png'
Profile_Panels2_file_prefix = 'profile_Panels2_'
Profile_Panels2_file_interval = 5
Profile_Panels2_file_width = -1
Profile_Panels2_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Profile_Panels3">Profile_Panels3 <a href="#Profile_Panels3" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Profile_Panels3_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels3_win_width = 6
Profile_Panels3_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Profile_Panels3_xleft = 0.15
Profile_Panels3_xright = 0.85
Profile_Panels3_ybot = 0.15
Profile_Panels3_ytop = 0.85
Profile_Panels3_txt_scale = 1.0
Profile_Panels3_title = 'Profile Panels3'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels3_xaxis_name = ''
Profile_Panels3_xaxis_reversed = .false.
Profile_Panels3_xmin = -101d0
Profile_Panels3_xmax = -101d0
Profile_Panels3_xmargin = 0d0
Profile_Panels3_show_mix_regions_on_xaxis = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels3_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
Profile_Panels3_yaxis_name(:) = ''
Profile_Panels3_yaxis_reversed(:) = .false.
Profile_Panels3_yaxis_log(:) = .false.
Profile_Panels3_ymin(:) = -101d0
Profile_Panels3_ymax(:) = -101d0
Profile_Panels3_ycenter(:) = -101d0
Profile_Panels3_ymargin(:) = 0.1
Profile_Panels3_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels3_other_yaxis_name(:) = ''
Profile_Panels3_other_yaxis_reversed(:) = .false.
Profile_Panels3_other_yaxis_log(:) = .false.
Profile_Panels3_other_ymin(:) = -101d0
Profile_Panels3_other_ymax(:) = -101d0
Profile_Panels3_other_ycenter(:) = -101d0
Profile_Panels3_other_ymargin(:) = 0.1
Profile_Panels3_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels3_show_grid = .false.
{% endhighlight %}


setup default plot

{% highlight fortran %}
Profile_Panels3_win_aspect_ratio = 1.25
Profile_Panels3_txt_scale = 0.9
Profile_Panels3_ybot = 0.1
Profile_Panels3_ytop = 0.9
Profile_Panels3_title = 'Abundance-Power-Mixing'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels3_xaxis_name = 'logP'
Profile_Panels3_xaxis_reversed = .true.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels3_num_panels = 3
Profile_Panels3_yaxis_name(1) = 'Abundance'
Profile_Panels3_yaxis_name(2) = 'Power'
Profile_Panels3_yaxis_name(3) = 'Mixing'
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Profile_Panels3_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Profile_Panels3_file_flag = .false.
Profile_Panels3_file_dir = 'png'
Profile_Panels3_file_prefix = 'profile_Panels3_'
Profile_Panels3_file_interval = 5
Profile_Panels3_file_width = -1
Profile_Panels3_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Profile_Panels4">Profile_Panels4 <a href="#Profile_Panels4" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Profile_Panels4_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels4_win_width = 6
Profile_Panels4_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Profile_Panels4_xleft = 0.15
Profile_Panels4_xright = 0.85
Profile_Panels4_ybot = 0.15
Profile_Panels4_ytop = 0.85
Profile_Panels4_txt_scale = 1.0
Profile_Panels4_title = 'Profile Panels4'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels4_xaxis_name = ''
Profile_Panels4_xaxis_reversed = .false.
Profile_Panels4_xmin = -101d0
Profile_Panels4_xmax = -101d0
Profile_Panels4_xmargin = 0d0
Profile_Panels4_show_mix_regions_on_xaxis = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels4_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
Profile_Panels4_yaxis_name(:) = ''
Profile_Panels4_yaxis_reversed(:) = .false.
Profile_Panels4_yaxis_log(:) = .false.
Profile_Panels4_ymin(:) = -101d0
Profile_Panels4_ymax(:) = -101d0
Profile_Panels4_ycenter(:) = -101d0
Profile_Panels4_ymargin(:) = 0.1
Profile_Panels4_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels4_other_yaxis_name(:) = ''
Profile_Panels4_other_yaxis_reversed(:) = .false.
Profile_Panels4_other_yaxis_log(:) = .false.
Profile_Panels4_other_ymin(:) = -101d0
Profile_Panels4_other_ymax(:) = -101d0
Profile_Panels4_other_ycenter(:) = -101d0
Profile_Panels4_other_ymargin(:) = 0.1
Profile_Panels4_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels4_show_grid = .false.
{% endhighlight %}


setup default plot

{% highlight fortran %}
Profile_Panels4_win_aspect_ratio = 1.25
Profile_Panels4_txt_scale = 0.9
Profile_Panels4_ybot = 0.1
Profile_Panels4_ytop = 0.9
Profile_Panels4_title = 'Abundance-Power-Mixing-Dynamo'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels4_xaxis_name = 'logP'
Profile_Panels4_xaxis_reversed = .true.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels4_num_panels = 4
Profile_Panels4_yaxis_name(1) = 'Abundance'
Profile_Panels4_yaxis_name(2) = 'Power'
Profile_Panels4_yaxis_name(3) = 'Mixing'
Profile_Panels4_yaxis_name(4) = 'Dynamo'
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Profile_Panels4_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Profile_Panels4_file_flag = .false.
Profile_Panels4_file_dir = 'png'
Profile_Panels4_file_prefix = 'profile_Panels4_'
Profile_Panels4_file_interval = 5
Profile_Panels4_file_width = -1
Profile_Panels4_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Profile_Panels5">Profile_Panels5 <a href="#Profile_Panels5" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Profile_Panels5_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels5_win_width = 5
Profile_Panels5_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Profile_Panels5_xleft = 0.15
Profile_Panels5_xright = 0.85
Profile_Panels5_ybot = 0.15
Profile_Panels5_ytop = 0.85
Profile_Panels5_txt_scale = 1.0
Profile_Panels5_title = 'Profile Panels5'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels5_xaxis_name = ''
Profile_Panels5_xaxis_reversed = .false.
Profile_Panels5_xmin = -101d0
Profile_Panels5_xmax = -101d0
Profile_Panels5_xmargin = 0d0
Profile_Panels5_show_mix_regions_on_xaxis = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels5_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
Profile_Panels5_yaxis_name(:) = ''
Profile_Panels5_yaxis_reversed(:) = .false.
Profile_Panels5_yaxis_log(:) = .false.
Profile_Panels5_ymin(:) = -101d0
Profile_Panels5_ymax(:) = -101d0
Profile_Panels5_ycenter(:) = -101d0
Profile_Panels5_ymargin(:) = 0.1
Profile_Panels5_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels5_other_yaxis_name(:) = ''
Profile_Panels5_other_yaxis_reversed(:) = .false.
Profile_Panels5_other_yaxis_log(:) = .false.
Profile_Panels5_other_ymin(:) = -101d0
Profile_Panels5_other_ymax(:) = -101d0
Profile_Panels5_other_ycenter(:) = -101d0
Profile_Panels5_other_ymargin(:) = 0.1
Profile_Panels5_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels5_show_grid = .false.
{% endhighlight %}


setup default plot

{% highlight fortran %}
Profile_Panels5_win_aspect_ratio = 1.25
Profile_Panels5_txt_scale = 0.9
Profile_Panels5_ybot = 0.1
Profile_Panels5_ytop = 0.9
Profile_Panels5_title = 'Summary Profile-Mode Prop-Mixing'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels5_xaxis_name = 'logP'
Profile_Panels5_xaxis_reversed = .true.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels5_num_panels = 3
Profile_Panels5_yaxis_name(1) = 'Summary_Profile'
Profile_Panels5_yaxis_name(2) = 'Mode_Prop'
Profile_Panels5_yaxis_name(3) = 'Mixing'
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Profile_Panels5_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Profile_Panels5_file_flag = .false.
Profile_Panels5_file_dir = 'png'
Profile_Panels5_file_prefix = 'profile_Panels5_'
Profile_Panels5_file_interval = 5
Profile_Panels5_file_width = -1
Profile_Panels5_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Profile_Panels6">Profile_Panels6 <a href="#Profile_Panels6" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Profile_Panels6_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels6_win_width = 6
Profile_Panels6_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Profile_Panels6_xleft = 0.15
Profile_Panels6_xright = 0.85
Profile_Panels6_ybot = 0.15
Profile_Panels6_ytop = 0.85
Profile_Panels6_txt_scale = 1.0
Profile_Panels6_title = 'Profile Panels6'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels6_xaxis_name = ''
Profile_Panels6_xaxis_reversed = .false.
Profile_Panels6_xmin = -101d0
Profile_Panels6_xmax = -101d0
Profile_Panels6_xmargin = 0d0
Profile_Panels6_show_mix_regions_on_xaxis = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels6_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
Profile_Panels6_yaxis_name(:) = ''
Profile_Panels6_yaxis_reversed(:) = .false.
Profile_Panels6_yaxis_log(:) = .false.
Profile_Panels6_ymin(:) = -101d0
Profile_Panels6_ymax(:) = -101d0
Profile_Panels6_ycenter(:) = -101d0
Profile_Panels6_ymargin(:) = 0.1
Profile_Panels6_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels6_other_yaxis_name(:) = ''
Profile_Panels6_other_yaxis_reversed(:) = .false.
Profile_Panels6_other_yaxis_log(:) = .false.
Profile_Panels6_other_ymin(:) = -101d0
Profile_Panels6_other_ymax(:) = -101d0
Profile_Panels6_other_ycenter(:) = -101d0
Profile_Panels6_other_ymargin(:) = 0.1
Profile_Panels6_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels6_show_grid = .false.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Profile_Panels6_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Profile_Panels6_file_flag = .false.
Profile_Panels6_file_dir = 'png'
Profile_Panels6_file_prefix = 'profile_Panels6_'
Profile_Panels6_file_interval = 5
Profile_Panels6_file_width = -1
Profile_Panels6_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Profile_Panels7">Profile_Panels7 <a href="#Profile_Panels7" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Profile_Panels7_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels7_win_width = 6
Profile_Panels7_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Profile_Panels7_xleft = 0.15
Profile_Panels7_xright = 0.85
Profile_Panels7_ybot = 0.15
Profile_Panels7_ytop = 0.85
Profile_Panels7_txt_scale = 1.0
Profile_Panels7_title = 'Profile Panels4'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels7_xaxis_name = ''
Profile_Panels7_xaxis_reversed = .false.
Profile_Panels7_xmin = -101d0
Profile_Panels7_xmax = -101d0
Profile_Panels7_xmargin = 0d0
Profile_Panels7_show_mix_regions_on_xaxis = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels7_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
Profile_Panels7_yaxis_name(:) = ''
Profile_Panels7_yaxis_reversed(:) = .false.
Profile_Panels7_yaxis_log(:) = .false.
Profile_Panels7_ymin(:) = -101d0
Profile_Panels7_ymax(:) = -101d0
Profile_Panels7_ycenter(:) = -101d0
Profile_Panels7_ymargin(:) = 0.1
Profile_Panels7_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels7_other_yaxis_name(:) = ''
Profile_Panels7_other_yaxis_reversed(:) = .false.
Profile_Panels7_other_yaxis_log(:) = .false.
Profile_Panels7_other_ymin(:) = -101d0
Profile_Panels7_other_ymax(:) = -101d0
Profile_Panels7_other_ycenter(:) = -101d0
Profile_Panels7_other_ymargin(:) = 0.1
Profile_Panels7_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels7_show_grid = .false.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Profile_Panels7_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Profile_Panels7_file_flag = .false.
Profile_Panels7_file_dir = 'png'
Profile_Panels7_file_prefix = 'profile_Panels7_'
Profile_Panels7_file_interval = 5
Profile_Panels7_file_width = -1
Profile_Panels7_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Profile_Panels8">Profile_Panels8 <a href="#Profile_Panels8" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Profile_Panels8_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels8_win_width = 6
Profile_Panels8_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Profile_Panels8_xleft = 0.15
Profile_Panels8_xright = 0.85
Profile_Panels8_ybot = 0.15
Profile_Panels8_ytop = 0.85
Profile_Panels8_txt_scale = 1.0
Profile_Panels8_title = 'Profile Panels8'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels8_xaxis_name = ''
Profile_Panels8_xaxis_reversed = .false.
Profile_Panels8_xmin = -101d0
Profile_Panels8_xmax = -101d0
Profile_Panels8_xmargin = 0d0
Profile_Panels8_show_mix_regions_on_xaxis = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels8_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
Profile_Panels8_yaxis_name(:) = ''
Profile_Panels8_yaxis_reversed(:) = .false.
Profile_Panels8_yaxis_log(:) = .false.
Profile_Panels8_ymin(:) = -101d0
Profile_Panels8_ymax(:) = -101d0
Profile_Panels8_ycenter(:) = -101d0
Profile_Panels8_ymargin(:) = 0.1
Profile_Panels8_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels8_other_yaxis_name(:) = ''
Profile_Panels8_other_yaxis_reversed(:) = .false.
Profile_Panels8_other_yaxis_log(:) = .false.
Profile_Panels8_other_ymin(:) = -101d0
Profile_Panels8_other_ymax(:) = -101d0
Profile_Panels8_other_ycenter(:) = -101d0
Profile_Panels8_other_ymargin(:) = 0.1
Profile_Panels8_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels8_show_grid = .false.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Profile_Panels8_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Profile_Panels8_file_flag = .false.
Profile_Panels8_file_dir = 'png'
Profile_Panels8_file_prefix = 'profile_Panels8_'
Profile_Panels8_file_interval = 5
Profile_Panels8_file_width = -1
Profile_Panels8_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Profile_Panels9">Profile_Panels9 <a href="#Profile_Panels9" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Profile_Panels9_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels9_win_width = 6
Profile_Panels9_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Profile_Panels9_xleft = 0.15
Profile_Panels9_xright = 0.85
Profile_Panels9_ybot = 0.15
Profile_Panels9_ytop = 0.85
Profile_Panels9_txt_scale = 1.0
Profile_Panels9_title = 'Profile Panels9'
{% endhighlight %}


{% highlight fortran %}
Profile_Panels9_xaxis_name = ''
Profile_Panels9_xaxis_reversed = .false.
Profile_Panels9_xmin = -101d0
Profile_Panels9_xmax = -101d0
Profile_Panels9_xmargin = 0d0
Profile_Panels9_show_mix_regions_on_xaxis = .false.
{% endhighlight %}


{% highlight fortran %}
Profile_Panels9_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
Profile_Panels9_yaxis_name(:) = ''
Profile_Panels9_yaxis_reversed(:) = .false.
Profile_Panels9_yaxis_log(:) = .false.
Profile_Panels9_ymin(:) = -101d0
Profile_Panels9_ymax(:) = -101d0
Profile_Panels9_ycenter(:) = -101d0
Profile_Panels9_ymargin(:) = 0.1
Profile_Panels9_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels9_other_yaxis_name(:) = ''
Profile_Panels9_other_yaxis_reversed(:) = .false.
Profile_Panels9_other_yaxis_log(:) = .false.
Profile_Panels9_other_ymin(:) = -101d0
Profile_Panels9_other_ymax(:) = -101d0
Profile_Panels9_other_ycenter(:) = -101d0
Profile_Panels9_other_ymargin(:) = 0.1
Profile_Panels9_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
Profile_Panels9_show_grid = .false.
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Profile_Panels9_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Profile_Panels9_file_flag = .false.
Profile_Panels9_file_dir = 'png'
Profile_Panels9_file_prefix = 'profile_Panels9_'
Profile_Panels9_file_interval = 5
Profile_Panels9_file_width = -1
Profile_Panels9_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="History_Tracks">History Tracks <a href="#History_Tracks" title="Permalink to this location">¶</a></h1>


<h3 id="History_Track1">History_Track1 <a href="#History_Track1" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Track1_win_flag = .false.
History_Track1_win_width = 6
History_Track1_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Track1_xleft = 0.15
History_Track1_xright = 0.85
History_Track1_ybot = 0.15
History_Track1_ytop = 0.85
History_Track1_txt_scale = 1.0
History_Track1_title = 'History_Track1'
{% endhighlight %}


set default

{% highlight fortran %}
History_Track1_xname = 'log_center_T'
History_Track1_yname = 'log_L'
History_Track1_xaxis_label = 'log T\dcenter'
History_Track1_yaxis_label = 'log L/L\d\(2281)'
History_Track1_reverse_xaxis = .true.
History_Track1_reverse_yaxis = .false.
History_Track1_log_xaxis = .false.
History_Track1_log_yaxis = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track1_xmin = -101d0
History_Track1_xmax = -101d0
History_Track1_ymin = -101d0
History_Track1_ymax = -101d0
{% endhighlight %}


{% highlight fortran %}
History_Track1_xmargin = 0.1
History_Track1_ymargin = 0.1
History_Track1_dxmin = -1
History_Track1_dymin = -1
{% endhighlight %}


{% highlight fortran %}
History_Track1_step_min = -1
History_Track1_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_History_Track1_target_box = .false.
History_Track1_n_sigma = -3
History_Track1_xtarget = 0
History_Track1_xsigma = 0
History_Track1_ytarget = 0
History_Track1_ysigma = 0
{% endhighlight %}


{% highlight fortran %}
show_History_Track1_annotation1 = .false.
show_History_Track1_annotation2 = .false.
show_History_Track1_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track1_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Track1_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Track1_file_flag = .false.
History_Track1_file_dir = 'png'
History_Track1_file_prefix = 'track1_'
History_Track1_file_interval = 5
History_Track1_file_width = -1
History_Track1_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Track2">History_Track2 <a href="#History_Track2" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Track2_win_flag = .false.
History_Track2_win_width = 6
History_Track2_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Track2_xleft = 0.15
History_Track2_xright = 0.85
History_Track2_ybot = 0.15
History_Track2_ytop = 0.85
History_Track2_txt_scale = 1.0
History_Track2_title = 'History_Track2'
{% endhighlight %}


{% highlight fortran %}
History_Track2_xname = ''
History_Track2_yname = ''
History_Track2_xaxis_label = ''
History_Track2_yaxis_label = ''
History_Track2_reverse_xaxis = .false.
History_Track2_reverse_yaxis = .false.
History_Track2_log_xaxis = .false.
History_Track2_log_yaxis = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track2_xmin = -101d0
History_Track2_xmax = -101d0
History_Track2_ymin = -101d0
History_Track2_ymax = -101d0
{% endhighlight %}


{% highlight fortran %}
History_Track2_xmargin = 0.1
History_Track2_ymargin = 0.1
History_Track2_dxmin = -1
History_Track2_dymin = -1
{% endhighlight %}


{% highlight fortran %}
History_Track2_step_min = -1
History_Track2_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_History_Track2_target_box = .false.
History_Track2_n_sigma = -3
History_Track2_xtarget = 0
History_Track2_xsigma = 0
History_Track2_ytarget = 0
History_Track2_ysigma = 0
{% endhighlight %}


{% highlight fortran %}
show_History_Track2_annotation1 = .false.
show_History_Track2_annotation2 = .false.
show_History_Track2_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track2_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Track2_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Track2_file_flag = .false.
History_Track2_file_dir = 'png'
History_Track2_file_prefix = 'track2_'
History_Track2_file_interval = 5
History_Track2_file_width = -1
History_Track2_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Track3">History_Track3 <a href="#History_Track3" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Track3_win_flag = .false.
History_Track3_win_width = 6
History_Track3_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Track3_xleft = 0.15
History_Track3_xright = 0.85
History_Track3_ybot = 0.15
History_Track3_ytop = 0.85
History_Track3_txt_scale = 1.0
History_Track3_title = 'History_Track3'
{% endhighlight %}


{% highlight fortran %}
History_Track3_xname = ''
History_Track3_yname = ''
History_Track3_xaxis_label = ''
History_Track3_yaxis_label = ''
History_Track3_reverse_xaxis = .false.
History_Track3_reverse_yaxis = .false.
History_Track3_log_xaxis = .false.
History_Track3_log_yaxis = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track3_xmin = -101d0
History_Track3_xmax = -101d0
History_Track3_ymin = -101d0
History_Track3_ymax = -101d0
{% endhighlight %}


{% highlight fortran %}
History_Track3_xmargin = 0.1
History_Track3_ymargin = 0.1
History_Track3_dxmin = -1
History_Track3_dymin = -1
{% endhighlight %}


{% highlight fortran %}
History_Track3_step_min = -1
History_Track3_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_History_Track3_target_box = .false.
History_Track3_n_sigma = -3
History_Track3_xtarget = 0
History_Track3_xsigma = 0
History_Track3_ytarget = 0
History_Track3_ysigma = 0
{% endhighlight %}


{% highlight fortran %}
show_History_Track3_annotation1 = .false.
show_History_Track3_annotation2 = .false.
show_History_Track3_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track3_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Track3_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Track3_file_flag = .false.
History_Track3_file_dir = 'png'
History_Track3_file_prefix = 'track3_'
History_Track3_file_interval = 5
History_Track3_file_width = -1
History_Track3_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Track4">History_Track4 <a href="#History_Track4" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Track4_win_flag = .false.
History_Track4_win_width = 6
History_Track4_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Track4_xleft = 0.15
History_Track4_xright = 0.85
History_Track4_ybot = 0.15
History_Track4_ytop = 0.85
History_Track4_txt_scale = 1.0
History_Track4_title = 'History_Track4'
{% endhighlight %}


{% highlight fortran %}
History_Track4_xname = ''
History_Track4_yname = ''
History_Track4_xaxis_label = ''
History_Track4_yaxis_label = ''
History_Track4_reverse_xaxis = .false.
History_Track4_reverse_yaxis = .false.
History_Track4_log_xaxis = .false.
History_Track4_log_yaxis = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track4_xmin = -101d0
History_Track4_xmax = -101d0
History_Track4_ymin = -101d0
History_Track4_ymax = -101d0
{% endhighlight %}


{% highlight fortran %}
History_Track4_xmargin = 0.1
History_Track4_ymargin = 0.1
History_Track4_dxmin = -1
History_Track4_dymin = -1
{% endhighlight %}


{% highlight fortran %}
History_Track4_step_min = -1
History_Track4_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_History_Track4_target_box = .false.
History_Track4_n_sigma = -3
History_Track4_xtarget = 0
History_Track4_xsigma = 0
History_Track4_ytarget = 0
History_Track4_ysigma = 0
{% endhighlight %}


{% highlight fortran %}
show_History_Track4_annotation1 = .false.
show_History_Track4_annotation2 = .false.
show_History_Track4_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track4_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Track4_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Track4_file_flag = .false.
History_Track4_file_dir = 'png'
History_Track4_file_prefix = 'track4_'
History_Track4_file_interval = 5
History_Track4_file_width = -1
History_Track4_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Track5">History_Track5 <a href="#History_Track5" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Track5_win_flag = .false.
History_Track5_win_width = 6
History_Track5_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Track5_xleft = 0.15
History_Track5_xright = 0.85
History_Track5_ybot = 0.15
History_Track5_ytop = 0.85
History_Track5_txt_scale = 1.0
History_Track5_title = 'History_Track5'
{% endhighlight %}


{% highlight fortran %}
History_Track5_xname = ''
History_Track5_yname = ''
History_Track5_xaxis_label = ''
History_Track5_yaxis_label = ''
History_Track5_reverse_xaxis = .false.
History_Track5_reverse_yaxis = .false.
History_Track5_log_xaxis = .false.
History_Track5_log_yaxis = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track5_xmin = -101d0
History_Track5_xmax = -101d0
History_Track5_ymin = -101d0
History_Track5_ymax = -101d0
{% endhighlight %}


{% highlight fortran %}
History_Track5_xmargin = 0.1
History_Track5_ymargin = 0.1
History_Track5_dxmin = -1
History_Track5_dymin = -1
{% endhighlight %}


{% highlight fortran %}
History_Track5_step_min = -1
History_Track5_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_History_Track5_target_box = .false.
History_Track5_n_sigma = -3
History_Track5_xtarget = 0
History_Track5_xsigma = 0
History_Track5_ytarget = 0
History_Track5_ysigma = 0
{% endhighlight %}


{% highlight fortran %}
show_History_Track5_annotation1 = .false.
show_History_Track5_annotation2 = .false.
show_History_Track5_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track5_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Track5_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Track5_file_flag = .false.
History_Track5_file_dir = 'png'
History_Track5_file_prefix = 'track5_'
History_Track5_file_interval = 5
History_Track5_file_width = -1
History_Track5_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Track6">History_Track6 <a href="#History_Track6" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Track6_win_flag = .false.
History_Track6_win_width = 6
History_Track6_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Track6_xleft = 0.15
History_Track6_xright = 0.85
History_Track6_ybot = 0.15
History_Track6_ytop = 0.85
History_Track6_txt_scale = 1.0
History_Track6_title = 'History_Track6'
{% endhighlight %}


{% highlight fortran %}
History_Track6_xname = ''
History_Track6_yname = ''
History_Track6_xaxis_label = ''
History_Track6_yaxis_label = ''
History_Track6_reverse_xaxis = .false.
History_Track6_reverse_yaxis = .false.
History_Track6_log_xaxis = .false.
History_Track6_log_yaxis = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track6_xmin = -101d0
History_Track6_xmax = -101d0
History_Track6_ymin = -101d0
History_Track6_ymax = -101d0
{% endhighlight %}


{% highlight fortran %}
History_Track6_xmargin = 0.1
History_Track6_ymargin = 0.1
History_Track6_dxmin = -1
History_Track6_dymin = -1
{% endhighlight %}


{% highlight fortran %}
History_Track6_step_min = -1
History_Track6_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_History_Track6_target_box = .false.
History_Track6_n_sigma = -3
History_Track6_xtarget = 0
History_Track6_xsigma = 0
History_Track6_ytarget = 0
History_Track6_ysigma = 0
{% endhighlight %}


{% highlight fortran %}
show_History_Track6_annotation1 = .false.
show_History_Track6_annotation2 = .false.
show_History_Track6_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track6_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Track6_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Track6_file_flag = .false.
History_Track6_file_dir = 'png'
History_Track6_file_prefix = 'track6_'
History_Track6_file_interval = 5
History_Track6_file_width = -1
History_Track6_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Track7">History_Track7 <a href="#History_Track7" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Track7_win_flag = .false.
History_Track7_win_width = 6
History_Track7_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Track7_xleft = 0.15
History_Track7_xright = 0.85
History_Track7_ybot = 0.15
History_Track7_ytop = 0.85
History_Track7_txt_scale = 1.0
History_Track7_title = 'History_Track7'
{% endhighlight %}


{% highlight fortran %}
History_Track7_xname = ''
History_Track7_yname = ''
History_Track7_xaxis_label = ''
History_Track7_yaxis_label = ''
History_Track7_reverse_xaxis = .false.
History_Track7_reverse_yaxis = .false.
History_Track7_log_xaxis = .false.
History_Track7_log_yaxis = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track7_xmin = -101d0
History_Track7_xmax = -101d0
History_Track7_ymin = -101d0
History_Track7_ymax = -101d0
{% endhighlight %}


{% highlight fortran %}
History_Track7_xmargin = 0.1
History_Track7_ymargin = 0.1
History_Track7_dxmin = -1
History_Track7_dymin = -1
{% endhighlight %}


{% highlight fortran %}
History_Track7_step_min = -1
History_Track7_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_History_Track7_target_box = .false.
History_Track7_n_sigma = -3
History_Track7_xtarget = 0
History_Track7_xsigma = 0
History_Track7_ytarget = 0
History_Track7_ysigma = 0
{% endhighlight %}


{% highlight fortran %}
show_History_Track7_annotation1 = .false.
show_History_Track7_annotation2 = .false.
show_History_Track7_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track7_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Track7_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Track7_file_flag = .false.
History_Track7_file_dir = 'png'
History_Track7_file_prefix = 'track7_'
History_Track7_file_interval = 5
History_Track7_file_width = -1
History_Track7_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Track8">History_Track8 <a href="#History_Track8" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Track8_win_flag = .false.
History_Track8_win_width = 6
History_Track8_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Track8_xleft = 0.15
History_Track8_xright = 0.85
History_Track8_ybot = 0.15
History_Track8_ytop = 0.85
History_Track8_txt_scale = 1.0
History_Track8_title = 'History_Track8'
{% endhighlight %}


{% highlight fortran %}
History_Track8_xname = ''
History_Track8_yname = ''
History_Track8_xaxis_label = ''
History_Track8_yaxis_label = ''
History_Track8_reverse_xaxis = .false.
History_Track8_reverse_yaxis = .false.
History_Track8_log_xaxis = .false.
History_Track8_log_yaxis = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track8_xmin = -101d0
History_Track8_xmax = -101d0
History_Track8_ymin = -101d0
History_Track8_ymax = -101d0
{% endhighlight %}


{% highlight fortran %}
History_Track8_xmargin = 0.1
History_Track8_ymargin = 0.1
History_Track8_dxmin = -1
History_Track8_dymin = -1
{% endhighlight %}


{% highlight fortran %}
History_Track8_step_min = -1
History_Track8_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_History_Track8_target_box = .false.
History_Track8_n_sigma = -3
History_Track8_xtarget = 0
History_Track8_xsigma = 0
History_Track8_ytarget = 0
History_Track8_ysigma = 0
{% endhighlight %}


{% highlight fortran %}
show_History_Track8_annotation1 = .false.
show_History_Track8_annotation2 = .false.
show_History_Track8_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track8_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Track8_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Track8_file_flag = .false.
History_Track8_file_dir = 'png'
History_Track8_file_prefix = 'track8_'
History_Track8_file_interval = 5
History_Track8_file_width = -1
History_Track8_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Track9">History_Track9 <a href="#History_Track9" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Track9_win_flag = .false.
History_Track9_win_width = 6
History_Track9_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Track9_xleft = 0.15
History_Track9_xright = 0.85
History_Track9_ybot = 0.15
History_Track9_ytop = 0.85
History_Track9_txt_scale = 1.0
History_Track9_title = 'History_Track9'
{% endhighlight %}


{% highlight fortran %}
History_Track9_xname = ''
History_Track9_yname = ''
History_Track9_xaxis_label = ''
History_Track9_yaxis_label = ''
History_Track9_reverse_xaxis = .false.
History_Track9_reverse_yaxis = .false.
History_Track9_log_xaxis = .false.
History_Track9_log_yaxis = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track9_xmin = -101d0
History_Track9_xmax = -101d0
History_Track9_ymin = -101d0
History_Track9_ymax = -101d0
{% endhighlight %}


{% highlight fortran %}
History_Track9_xmargin = 0.1
History_Track9_ymargin = 0.1
History_Track9_dxmin = -1
History_Track9_dymin = -1
{% endhighlight %}


{% highlight fortran %}
History_Track9_step_min = -1
History_Track9_step_max = -1
{% endhighlight %}


{% highlight fortran %}
show_History_Track9_target_box = .false.
History_Track9_n_sigma = -3
History_Track9_xtarget = 0
History_Track9_xsigma = 0
History_Track9_ytarget = 0
History_Track9_ysigma = 0
{% endhighlight %}


{% highlight fortran %}
show_History_Track9_annotation1 = .false.
show_History_Track9_annotation2 = .false.
show_History_Track9_annotation3 = .false.
{% endhighlight %}


{% highlight fortran %}
History_Track9_fname = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Track9_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Track9_file_flag = .false.
History_Track9_file_dir = 'png'
History_Track9_file_prefix = 'track9_'
History_Track9_file_interval = 5
History_Track9_file_width = -1
History_Track9_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="History_Panels">History Panels <a href="#History_Panels" title="Permalink to this location">¶</a></h1>


<h3 id="History_Panels1">History_Panels1 <a href="#History_Panels1" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Panels1_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels1_win_width = 6
History_Panels1_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Panels1_xleft = 0.15
History_Panels1_xright = 0.85
History_Panels1_ybot = 0.15
History_Panels1_ytop = 0.85
History_Panels1_txt_scale = 1.0
History_Panels1_title = 'History_Panels1'
{% endhighlight %}


{% highlight fortran %}
History_Panels1_xaxis_name = 'model_number'
History_Panels1_xmin = -101d0
History_Panels1_xmax = -101d0
History_Panels1_max_width = 100
History_Panels1_dxmin = -1
History_Panels1_xaxis_reversed = .false.
History_Panels1_xaxis_log = .false.
History_Panels1_xmargin = 0.0
{% endhighlight %}


{% highlight fortran %}
History_Panels1_yaxis_name(:) = ''
History_Panels1_yaxis_reversed(:) = .false.
History_Panels1_yaxis_log(:) = .false.
History_Panels1_ymin(:) = -101d0
History_Panels1_ymax(:) = -101d0
History_Panels1_ymargin(:) = 0.1
History_Panels1_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels1_other_yaxis_name(:) = ''
History_Panels1_other_yaxis_reversed(:) = .false.
History_Panels1_other_yaxis_log(:) = .false.
History_Panels1_other_ymin(:) = -101d0
History_Panels1_other_ymax(:) = -101d0
History_Panels1_other_ymargin(:) = 0.1
History_Panels1_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels1_points_name(:) = ''
{% endhighlight %}


setup default

{% highlight fortran %}
History_Panels1_num_panels = 3
{% endhighlight %}


{% highlight fortran %}
History_Panels1_yaxis_name(1) = 'log_center_T'
History_Panels1_yaxis_reversed(1) = .false.
History_Panels1_ymin(1) = -101d0
History_Panels1_ymax(1) = -101d0
History_Panels1_dymin(1) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels1_other_yaxis_name(1) = 'log_center_Rho'
History_Panels1_other_yaxis_reversed(1) = .false.
History_Panels1_other_ymin(1) = -101d0
History_Panels1_other_ymax(1) = -101d0
History_Panels1_other_dymin(1) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels1_yaxis_name(2) = 'log_L'
History_Panels1_yaxis_reversed(2) = .false.
History_Panels1_ymin(2) = -101d0
History_Panels1_ymax(2) = -101d0
History_Panels1_dymin(2) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels1_other_yaxis_name(2) = 'log_Teff'
History_Panels1_other_yaxis_reversed(2) = .false.
History_Panels1_other_ymin(2) = -101d0
History_Panels1_other_ymax(2) = -101d0
History_Panels1_other_dymin(2) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels1_yaxis_name(3) = 'star_mass'
History_Panels1_yaxis_reversed(3) = .false.
History_Panels1_ymin(3) = -101d0
History_Panels1_ymax(3) = -101d0
History_Panels1_dymin(3) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels1_other_yaxis_name(3) = 'log_abs_mdot'
History_Panels1_other_yaxis_reversed(3) = .false.
History_Panels1_other_ymin(3) = -101d0
History_Panels1_other_ymax(3) = -101d0
History_Panels1_other_dymin(3) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Panels1_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Panels1_file_flag = .false.
History_Panels1_file_dir = 'png'
History_Panels1_file_prefix = 'History_Panels1_'
History_Panels1_file_interval = 5
History_Panels1_file_width = -1
History_Panels1_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Panels2">History_Panels2 <a href="#History_Panels2" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Panels2_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels2_win_width = 6
History_Panels2_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Panels2_xleft = 0.15
History_Panels2_xright = 0.85
History_Panels2_ybot = 0.15
History_Panels2_ytop = 0.85
History_Panels2_txt_scale = 1.0
History_Panels2_title = 'History_Panels2'
{% endhighlight %}


{% highlight fortran %}
History_Panels2_xaxis_name = 'model_number'
History_Panels2_xmin = -101d0
History_Panels2_xmax = -101d0
History_Panels2_max_width = 100
History_Panels2_dxmin = -1
History_Panels2_xaxis_reversed = .false.
History_Panels2_xaxis_log = .false.
History_Panels2_xmargin = 0.0
{% endhighlight %}


{% highlight fortran %}
History_Panels2_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
History_Panels2_yaxis_name(:) = ''
History_Panels2_yaxis_reversed(:) = .false.
History_Panels2_yaxis_log(:) = .false.
History_Panels2_ymin(:) = -101d0
History_Panels2_ymax(:) = -101d0
History_Panels2_ymargin(:) = 0.1
History_Panels2_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels2_other_yaxis_name(:) = ''
History_Panels2_other_yaxis_reversed(:) = .false.
History_Panels2_other_yaxis_log(:) = .false.
History_Panels2_other_ymin(:) = -101d0
History_Panels2_other_ymax(:) = -101d0
History_Panels2_other_ymargin(:) = 0.1
History_Panels2_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels2_points_name(:) = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Panels2_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Panels2_file_flag = .false.
History_Panels2_file_dir = 'png'
History_Panels2_file_prefix = 'History_Panels2_'
History_Panels2_file_interval = 5
History_Panels2_file_width = -1
History_Panels2_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Panels3">History_Panels3 <a href="#History_Panels3" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Panels3_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels3_win_width = 6
History_Panels3_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Panels3_xleft = 0.15
History_Panels3_xright = 0.85
History_Panels3_ybot = 0.15
History_Panels3_ytop = 0.85
History_Panels3_txt_scale = 1.0
History_Panels3_title = 'History_Panels3'
{% endhighlight %}


{% highlight fortran %}
History_Panels3_xaxis_name = 'model_number'
History_Panels3_xmin = -101d0
History_Panels3_xmax = -101d0
History_Panels3_max_width = 100
History_Panels3_dxmin = -1
History_Panels3_xaxis_reversed = .false.
History_Panels3_xaxis_log = .false.
History_Panels3_xmargin = 0.0
{% endhighlight %}


{% highlight fortran %}
History_Panels3_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
History_Panels3_yaxis_name(:) = ''
History_Panels3_yaxis_reversed(:) = .false.
History_Panels3_yaxis_log(:) = .false.
History_Panels3_ymin(:) = -101d0
History_Panels3_ymax(:) = -101d0
History_Panels3_ymargin(:) = 0.1
History_Panels3_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels3_other_yaxis_name(:) = ''
History_Panels3_other_yaxis_reversed(:) = .false.
History_Panels3_other_yaxis_log(:) = .false.
History_Panels3_other_ymin(:) = -101d0
History_Panels3_other_ymax(:) = -101d0
History_Panels3_other_ymargin(:) = 0.1
History_Panels3_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels3_points_name(:) = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Panels3_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Panels3_file_flag = .false.
History_Panels3_file_dir = 'png'
History_Panels3_file_prefix = 'History_Panels3_'
History_Panels3_file_interval = 5
History_Panels3_file_width = -1
History_Panels3_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Panels4">History_Panels4 <a href="#History_Panels4" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Panels4_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels4_win_width = 6
History_Panels4_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Panels4_xleft = 0.15
History_Panels4_xright = 0.85
History_Panels4_ybot = 0.15
History_Panels4_ytop = 0.85
History_Panels4_txt_scale = 1.0
History_Panels4_title = 'History_Panels4'
{% endhighlight %}


{% highlight fortran %}
History_Panels4_xaxis_name = 'model_number'
History_Panels4_xmin = -101d0
History_Panels4_xmax = -101d0
History_Panels4_max_width = 100
History_Panels4_dxmin = -1
History_Panels4_xaxis_reversed = .false.
History_Panels4_xaxis_log = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels4_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
History_Panels4_yaxis_name(:) = ''
History_Panels4_yaxis_reversed(:) = .false.
History_Panels4_yaxis_log(:) = .false.
History_Panels4_ymin(:) = -101d0
History_Panels4_ymax(:) = -101d0
History_Panels4_ymargin(:) = 0.1
History_Panels4_dymin(:) = -1
History_Panels4_xmargin = 0.0
{% endhighlight %}


{% highlight fortran %}
History_Panels4_other_yaxis_name(:) = ''
History_Panels4_other_yaxis_reversed(:) = .false.
History_Panels4_other_yaxis_log(:) = .false.
History_Panels4_other_ymin(:) = -101d0
History_Panels4_other_ymax(:) = -101d0
History_Panels4_other_ymargin(:) = 0.1
History_Panels4_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels4_points_name(:) = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Panels4_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Panels4_file_flag = .false.
History_Panels4_file_dir = 'png'
History_Panels4_file_prefix = 'History_Panels4_'
History_Panels4_file_interval = 5
History_Panels4_file_width = -1
History_Panels4_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Panels5">History_Panels5 <a href="#History_Panels5" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Panels5_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels5_win_width = 6
History_Panels5_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Panels5_xleft = 0.15
History_Panels5_xright = 0.85
History_Panels5_ybot = 0.15
History_Panels5_ytop = 0.85
History_Panels5_txt_scale = 1.0
History_Panels5_title = 'History_Panels5'
{% endhighlight %}


{% highlight fortran %}
History_Panels5_xaxis_name = 'model_number'
History_Panels5_xmin = -101d0
History_Panels5_xmax = -101d0
History_Panels5_max_width = 100
History_Panels5_dxmin = -1
History_Panels5_xaxis_reversed = .false.
History_Panels5_xaxis_log = .false.
History_Panels5_xmargin = 0.0
{% endhighlight %}


{% highlight fortran %}
History_Panels5_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
History_Panels5_yaxis_name(1) = 'num_zones'
History_Panels5_yaxis_reversed(1) = .false.
History_Panels5_ymin(1) = -101d0
History_Panels5_ymax(1) = -101d0
History_Panels5_dymin(1) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels5_yaxis_name(:) = ''
History_Panels5_yaxis_reversed(:) = .false.
History_Panels5_yaxis_log(:) = .false.
History_Panels5_ymin(:) = -101d0
History_Panels5_ymax(:) = -101d0
History_Panels5_ymargin(:) = 0.1
History_Panels5_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels5_other_yaxis_name(:) = ''
History_Panels5_other_yaxis_reversed(:) = .false.
History_Panels6_other_yaxis_log(:) = .false.
History_Panels5_other_ymin(:) = -101d0
History_Panels5_other_ymax(:) = -101d0
History_Panels5_other_ymargin(:) = 0.1
History_Panels5_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels5_points_name(:) = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Panels5_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Panels5_file_flag = .false.
History_Panels5_file_dir = 'png'
History_Panels5_file_prefix = 'History_Panels5_'
History_Panels5_file_interval = 5
History_Panels5_file_width = -1
History_Panels5_file_aspect_ratio = -1
{% endhighlight %}


History_Panels6

{% highlight fortran %}
History_Panels6_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels6_win_width = 6
History_Panels6_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Panels6_xleft = 0.15
History_Panels6_xright = 0.85
History_Panels6_ybot = 0.15
History_Panels6_ytop = 0.85
History_Panels6_txt_scale = 1.0
History_Panels6_title = 'History_Panels6'
{% endhighlight %}


{% highlight fortran %}
History_Panels6_xaxis_name = 'model_number'
History_Panels6_xmin = -101d0
History_Panels6_xmax = -101d0
History_Panels6_max_width = 100
History_Panels6_dxmin = -1
History_Panels6_xaxis_reversed = .false.
History_Panels6_xaxis_log = .false.
History_Panels6_xmargin = 0.0
{% endhighlight %}


{% highlight fortran %}
History_Panels6_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
History_Panels6_yaxis_name(:) = ''
History_Panels6_yaxis_reversed(:) = .false.
History_Panels6_yaxis_log(:) = .false.
History_Panels6_ymin(:) = -101d0
History_Panels6_ymax(:) = -101d0
History_Panels6_ymargin(:) = 0.1
History_Panels6_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels6_other_yaxis_name(:) = ''
History_Panels6_other_yaxis_reversed(:) = .false.
History_Panels6_other_yaxis_log(:) = .false.
History_Panels6_other_ymin(:) = -101d0
History_Panels6_other_ymax(:) = -101d0
History_Panels6_other_ymargin(:) = 0.1
History_Panels6_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels6_points_name(:) = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Panels6_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Panels6_file_flag = .false.
History_Panels6_file_dir = 'png'
History_Panels6_file_prefix = 'History_Panels6_'
History_Panels6_file_interval = 5
History_Panels6_file_width = -1
History_Panels6_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Panels7">History_Panels7 <a href="#History_Panels7" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Panels7_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels7_win_width = 6
History_Panels7_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Panels7_xleft = 0.15
History_Panels7_xright = 0.85
History_Panels7_ybot = 0.15
History_Panels7_ytop = 0.85
History_Panels7_txt_scale = 1.0
History_Panels7_title = 'History_Panels7'
{% endhighlight %}


{% highlight fortran %}
History_Panels7_xaxis_name = 'model_number'
History_Panels7_xmin = -101d0
History_Panels7_xmax = -101d0
History_Panels7_max_width = 100
History_Panels7_dxmin = -1
History_Panels7_xaxis_reversed = .false.
History_Panels7_xaxis_log = .false.
History_Panels7_xmargin = 0.0
{% endhighlight %}


{% highlight fortran %}
History_Panels7_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
History_Panels7_yaxis_name(:) = ''
History_Panels7_yaxis_reversed(:) = .false.
History_Panels7_yaxis_log(:) = .false.
History_Panels7_ymin(:) = -101d0
History_Panels7_ymax(:) = -101d0
History_Panels7_ymargin(:) = 0.1
History_Panels7_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels7_other_yaxis_name(:) = ''
History_Panels7_other_yaxis_reversed(:) = .false.
History_Panels7_other_yaxis_log(:) = .false.
History_Panels7_other_ymin(:) = -101d0
History_Panels7_other_ymax(:) = -101d0
History_Panels7_other_ymargin(:) = 0.1
History_Panels7_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels7_points_name(:) = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Panels7_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Panels7_file_flag = .false.
History_Panels7_file_dir = 'png'
History_Panels7_file_prefix = 'History_Panels7_'
History_Panels7_file_interval = 5
History_Panels7_file_width = -1
History_Panels7_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Panels8">History_Panels8 <a href="#History_Panels8" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Panels8_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels8_win_width = 6
History_Panels8_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Panels8_xleft = 0.15
History_Panels8_xright = 0.85
History_Panels8_ybot = 0.15
History_Panels8_ytop = 0.85
History_Panels8_txt_scale = 1.0
History_Panels8_title = 'History_Panels8'
{% endhighlight %}


{% highlight fortran %}
History_Panels8_xaxis_name = 'model_number'
History_Panels8_xmin = -101d0
History_Panels8_xmax = -101d0
History_Panels8_max_width = 100
History_Panels8_dxmin = -1
History_Panels8_xaxis_reversed = .false.
History_Panels8_xaxis_log = .false.
History_Panels8_xmargin = 0.0
{% endhighlight %}


{% highlight fortran %}
History_Panels8_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
History_Panels8_yaxis_name(:) = ''
History_Panels8_yaxis_reversed(:) = .false.
History_Panels8_yaxis_log(:) = .false.
History_Panels8_ymin(:) = -101d0
History_Panels8_ymax(:) = -101d0
History_Panels8_ymargin(:) = 0.1
History_Panels8_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels8_other_yaxis_name(:) = ''
History_Panels8_other_yaxis_reversed(:) = .false.
History_Panels8_other_yaxis_log(:) = .false.
History_Panels8_other_ymin(:) = -101d0
History_Panels8_other_ymax(:) = -101d0
History_Panels8_other_ymargin(:) = 0.1
History_Panels8_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels8_points_name(:) = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Panels8_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Panels8_file_flag = .false.
History_Panels8_file_dir = 'png'
History_Panels8_file_prefix = 'History_Panels8_'
History_Panels8_file_interval = 5
History_Panels8_file_width = -1
History_Panels8_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Panels9">History_Panels9 <a href="#History_Panels9" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Panels9_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
History_Panels9_win_width = 6
History_Panels9_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
History_Panels9_xleft = 0.15
History_Panels9_xright = 0.85
History_Panels9_ybot = 0.15
History_Panels9_ytop = 0.85
History_Panels9_txt_scale = 1.0
History_Panels9_title = 'History_Panels9'
{% endhighlight %}


{% highlight fortran %}
History_Panels9_xaxis_name = 'model_number'
History_Panels9_xmin = -101d0
History_Panels9_xmax = -101d0
History_Panels9_max_width = 100
History_Panels9_dxmin = -1
History_Panels9_xaxis_reversed = .false.
History_Panels9_xaxis_log = .false.
History_Panels9_xmargin = 0.0
{% endhighlight %}


{% highlight fortran %}
History_Panels9_num_panels = 0
{% endhighlight %}


{% highlight fortran %}
History_Panels9_yaxis_name(1) = 'num_zones'
History_Panels9_yaxis_reversed(1) = .false.
History_Panels9_ymin(1) = -101d0
History_Panels9_ymax(1) = -101d0
History_Panels9_dymin(1) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels9_yaxis_name(:) = ''
History_Panels9_yaxis_reversed(:) = .false.
History_Panels9_yaxis_log(:) = .false.
History_Panels9_ymin(:) = -101d0
History_Panels9_ymax(:) = -101d0
History_Panels9_ymargin(:) = 0.1
History_Panels9_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels9_other_yaxis_name(:) = ''
History_Panels9_other_yaxis_reversed(:) = .false.
History_Panels9_other_yaxis_log(:) = .false.
History_Panels9_other_ymin(:) = -101d0
History_Panels9_other_ymax(:) = -101d0
History_Panels9_other_ymargin(:) = 0.1
History_Panels9_other_dymin(:) = -1
{% endhighlight %}


{% highlight fortran %}
History_Panels9_points_name(:) = ''
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
History_Panels9_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
History_Panels9_file_flag = .false.
History_Panels9_file_dir = 'png'
History_Panels9_file_prefix = 'History_Panels9_'
History_Panels9_file_interval = 5
History_Panels9_file_width = -1
History_Panels9_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="History_Panel_points_error_bars">History_Panel_points_error_bars <a href="#History_Panel_points_error_bars" title="Permalink to this location">¶</a></h3>


<h3 id="History_Panel_points_interval">History_Panel_points_interval <a href="#History_Panel_points_interval" title="Permalink to this location">¶</a></h3>


<h3 id="History_Panel_points_marker">History_Panel_points_marker <a href="#History_Panel_points_marker" title="Permalink to this location">¶</a></h3>


<h3 id="History_Panel_points_ci">History_Panel_points_ci <a href="#History_Panel_points_ci" title="Permalink to this location">¶</a></h3>


<h3 id="History_Panel_points_lw">History_Panel_points_lw <a href="#History_Panel_points_lw" title="Permalink to this location">¶</a></h3>


<h3 id="History_Panel_points_ch">History_Panel_points_ch <a href="#History_Panel_points_ch" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
History_Panel_points_error_bars = .true.
History_Panel_points_interval = 1
History_Panel_points_marker = 5
History_Panel_points_ci = 1
History_Panel_points_lw = 1
History_Panel_points_ch = 1.0
{% endhighlight %}

<h1 id="Color_Magnitude_Panels">Color Magnitude Panels <a href="#Color_Magnitude_Panels" title="Permalink to this location">¶</a></h1>


Plots either color-color, color-magnitude, magnitude-color or magnitude-magnitude

<h3 id="Color_magnitude1">Color_magnitude1 <a href="#Color_magnitude1" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Color_magnitude1_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Color_magnitude1_win_width = 6
Color_magnitude1_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Color_magnitude1_xleft = 0.15
Color_magnitude1_xright = 0.85
Color_magnitude1_ybot = 0.15
Color_magnitude1_ytop = 0.85
Color_magnitude1_txt_scale = 1.0
Color_magnitude1_title = 'Color_magnitude1'
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude1_xaxis1_name = ''
Color_magnitude1_xaxis2_name = ''
Color_magnitude1_xmin = -101d0
Color_magnitude1_xmax = -101d0
Color_magnitude1_max_width = 100
Color_magnitude1_dxmin = -1
Color_magnitude1_xaxis_reversed = .false.
Color_magnitude1_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude1_yaxis1_name(:) = ''
Color_magnitude1_yaxis2_name(:) = ''
Color_magnitude1_yaxis_reversed(:) = .false.
Color_magnitude1_yaxis_log(:) = .false.
Color_magnitude1_ymin(:) = -101d0
Color_magnitude1_ymax(:) = -101d0
Color_magnitude1_ymargin(:) = 0.1
Color_magnitude1_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude1_other_yaxis1_name(:) = ''
Color_magnitude1_other_yaxis2_name(:) = ''
Color_magnitude1_other_yaxis_reversed(:) = .false.
Color_magnitude1_other_yaxis_log(:) = .false.
Color_magnitude1_other_ymin(:) = -101d0
Color_magnitude1_other_ymax(:) = -101d0
Color_magnitude1_other_ymargin(:) = 0.1
Color_magnitude1_other_dymin(:) = -1
{% endhighlight %}


setup default

{% highlight fortran %}
Color_magnitude1_num_panels = 0
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude1_xaxis1_name = ''
Color_magnitude1_xaxis2_name = ''
Color_magnitude1_xmin = -101d0
Color_magnitude1_xmax = -101d0
Color_magnitude1_max_width = 100
Color_magnitude1_dxmin = -1
Color_magnitude1_xaxis_reversed = .false.
Color_magnitude1_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude1_yaxis1_name(:) = ''
Color_magnitude1_yaxis2_name(:) = ''
Color_magnitude1_yaxis_reversed(:) = .false.
Color_magnitude1_yaxis_log(:) = .false.
Color_magnitude1_ymin(:) = -101d0
Color_magnitude1_ymax(:) = -101d0
Color_magnitude1_ymargin(:) = 0.1
Color_magnitude1_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude1_other_yaxis1_name(:) = ''
Color_magnitude1_other_yaxis2_name(:) = ''
Color_magnitude1_other_yaxis_reversed(:) = .false.
Color_magnitude1_other_yaxis_log(:) = .false.
Color_magnitude1_other_ymin(:) = -101d0
Color_magnitude1_other_ymax(:) = -101d0
Color_magnitude1_other_ymargin(:) = 0.1
Color_magnitude1_other_dymin(:) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Color_magnitude1_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Color_magnitude1_file_flag = .false.
Color_magnitude1_file_dir = 'png'
Color_magnitude1_file_prefix = 'Color_magnitude1_'
Color_magnitude1_file_interval = 5
Color_magnitude1_file_width = -1
Color_magnitude1_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Color_magnitude2">Color_magnitude2 <a href="#Color_magnitude2" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Color_magnitude2_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Color_magnitude2_win_width = 6
Color_magnitude2_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Color_magnitude2_xleft = 0.15
Color_magnitude2_xright = 0.85
Color_magnitude2_ybot = 0.15
Color_magnitude2_ytop = 0.85
Color_magnitude2_txt_scale = 1.0
Color_magnitude2_title = 'Color_magnitude2'
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude2_xaxis1_name = ''
Color_magnitude2_xaxis2_name = ''
Color_magnitude2_xmin = -101d0
Color_magnitude2_xmax = -101d0
Color_magnitude2_max_width = 100
Color_magnitude2_dxmin = -1
Color_magnitude2_xaxis_reversed = .false.
Color_magnitude2_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude2_yaxis1_name(:) = ''
Color_magnitude2_yaxis2_name(:) = ''
Color_magnitude2_yaxis_reversed(:) = .false.
Color_magnitude2_yaxis_log(:) = .false.
Color_magnitude2_ymin(:) = -101d0
Color_magnitude2_ymax(:) = -101d0
Color_magnitude2_ymargin(:) = 0.1
Color_magnitude2_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude2_other_yaxis1_name(:) = ''
Color_magnitude2_other_yaxis2_name(:) = ''
Color_magnitude2_other_yaxis_reversed(:) = .false.
Color_magnitude2_other_yaxis_log(:) = .false.
Color_magnitude2_other_ymin(:) = -101d0
Color_magnitude2_other_ymax(:) = -101d0
Color_magnitude2_other_ymargin(:) = 0.1
Color_magnitude2_other_dymin(:) = -1
{% endhighlight %}


setup default

{% highlight fortran %}
Color_magnitude2_num_panels = 0
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude2_xaxis1_name = ''
Color_magnitude2_xaxis2_name = ''
Color_magnitude2_xmin = -101d0
Color_magnitude2_xmax = -101d0
Color_magnitude2_max_width = 100
Color_magnitude2_dxmin = -1
Color_magnitude2_xaxis_reversed = .false.
Color_magnitude2_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude2_yaxis1_name(:) = ''
Color_magnitude2_yaxis2_name(:) = ''
Color_magnitude2_yaxis_reversed(:) = .false.
Color_magnitude2_yaxis_log(:) = .false.
Color_magnitude2_ymin(:) = -101d0
Color_magnitude2_ymax(:) = -101d0
Color_magnitude2_ymargin(:) = 0.1
Color_magnitude2_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude2_other_yaxis1_name(:) = ''
Color_magnitude2_other_yaxis2_name(:) = ''
Color_magnitude2_other_yaxis_reversed(:) = .false.
Color_magnitude2_other_yaxis_log(:) = .false.
Color_magnitude2_other_ymin(:) = -101d0
Color_magnitude2_other_ymax(:) = -101d0
Color_magnitude2_other_ymargin(:) = 0.1
Color_magnitude2_other_dymin(:) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Color_magnitude2_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Color_magnitude2_file_flag = .false.
Color_magnitude2_file_dir = 'png'
Color_magnitude2_file_prefix = 'Color_magnitude2_'
Color_magnitude2_file_interval = 5
Color_magnitude2_file_width = -1
Color_magnitude2_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Color_magnitude3">Color_magnitude3 <a href="#Color_magnitude3" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Color_magnitude3_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Color_magnitude3_win_width = 6
Color_magnitude3_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Color_magnitude3_xleft = 0.15
Color_magnitude3_xright = 0.85
Color_magnitude3_ybot = 0.15
Color_magnitude3_ytop = 0.85
Color_magnitude3_txt_scale = 1.0
Color_magnitude3_title = 'Color_magnitude3'
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude3_xaxis1_name = ''
Color_magnitude3_xaxis2_name = ''
Color_magnitude3_xmin = -101d0
Color_magnitude3_xmax = -101d0
Color_magnitude3_max_width = 100
Color_magnitude3_dxmin = -1
Color_magnitude3_xaxis_reversed = .false.
Color_magnitude3_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude3_yaxis1_name(:) = ''
Color_magnitude3_yaxis2_name(:) = ''
Color_magnitude3_yaxis_reversed(:) = .false.
Color_magnitude3_yaxis_log(:) = .false.
Color_magnitude3_ymin(:) = -101d0
Color_magnitude3_ymax(:) = -101d0
Color_magnitude3_ymargin(:) = 0.1
Color_magnitude3_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude3_other_yaxis1_name(:) = ''
Color_magnitude3_other_yaxis2_name(:) = ''
Color_magnitude3_other_yaxis_reversed(:) = .false.
Color_magnitude3_other_yaxis_log(:) = .false.
Color_magnitude3_other_ymin(:) = -101d0
Color_magnitude3_other_ymax(:) = -101d0
Color_magnitude3_other_ymargin(:) = 0.1
Color_magnitude3_other_dymin(:) = -1
{% endhighlight %}


setup default

{% highlight fortran %}
Color_magnitude3_num_panels = 0
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude3_xaxis1_name = ''
Color_magnitude3_xaxis2_name = ''
Color_magnitude3_xmin = -101d0
Color_magnitude3_xmax = -101d0
Color_magnitude3_max_width = 100
Color_magnitude3_dxmin = -1
Color_magnitude3_xaxis_reversed = .false.
Color_magnitude3_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude3_yaxis1_name(:) = ''
Color_magnitude3_yaxis2_name(:) = ''
Color_magnitude3_yaxis_reversed(:) = .false.
Color_magnitude3_yaxis_log(:) = .false.
Color_magnitude3_ymin(:) = -101d0
Color_magnitude3_ymax(:) = -101d0
Color_magnitude3_ymargin(:) = 0.1
Color_magnitude3_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude3_other_yaxis1_name(:) = ''
Color_magnitude3_other_yaxis2_name(:) = ''
Color_magnitude3_other_yaxis_reversed(:) = .false.
Color_magnitude3_other_yaxis_log(:) = .false.
Color_magnitude3_other_ymin(:) = -101d0
Color_magnitude3_other_ymax(:) = -101d0
Color_magnitude3_other_ymargin(:) = 0.1
Color_magnitude3_other_dymin(:) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Color_magnitude3_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Color_magnitude3_file_flag = .false.
Color_magnitude3_file_dir = 'png'
Color_magnitude3_file_prefix = 'Color_magnitude3_'
Color_magnitude3_file_interval = 5
Color_magnitude3_file_width = -1
Color_magnitude3_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Color_magnitude4">Color_magnitude4 <a href="#Color_magnitude4" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Color_magnitude4_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Color_magnitude4_win_width = 6
Color_magnitude4_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Color_magnitude4_xleft = 0.15
Color_magnitude4_xright = 0.85
Color_magnitude4_ybot = 0.15
Color_magnitude4_ytop = 0.85
Color_magnitude4_txt_scale = 1.0
Color_magnitude4_title = 'Color_magnitude4'
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude4_xaxis1_name = ''
Color_magnitude4_xaxis2_name = ''
Color_magnitude4_xmin = -101d0
Color_magnitude4_xmax = -101d0
Color_magnitude4_max_width = 100
Color_magnitude4_dxmin = -1
Color_magnitude4_xaxis_reversed = .false.
Color_magnitude4_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude4_yaxis1_name(:) = ''
Color_magnitude4_yaxis2_name(:) = ''
Color_magnitude4_yaxis_reversed(:) = .false.
Color_magnitude4_yaxis_log(:) = .false.
Color_magnitude4_ymin(:) = -101d0
Color_magnitude4_ymax(:) = -101d0
Color_magnitude4_ymargin(:) = 0.1
Color_magnitude4_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude4_other_yaxis1_name(:) = ''
Color_magnitude4_other_yaxis2_name(:) = ''
Color_magnitude4_other_yaxis_reversed(:) = .false.
Color_magnitude4_other_yaxis_log(:) = .false.
Color_magnitude4_other_ymin(:) = -101d0
Color_magnitude4_other_ymax(:) = -101d0
Color_magnitude4_other_ymargin(:) = 0.1
Color_magnitude4_other_dymin(:) = -1
{% endhighlight %}


setup default

{% highlight fortran %}
Color_magnitude4_num_panels = 0
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude4_xaxis1_name = ''
Color_magnitude4_xaxis2_name = ''
Color_magnitude4_xmin = -101d0
Color_magnitude4_xmax = -101d0
Color_magnitude4_max_width = 100
Color_magnitude4_dxmin = -1
Color_magnitude4_xaxis_reversed = .false.
Color_magnitude4_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude4_yaxis1_name(:) = ''
Color_magnitude4_yaxis2_name(:) = ''
Color_magnitude4_yaxis_reversed(:) = .false.
Color_magnitude4_yaxis_log(:) = .false.
Color_magnitude4_ymin(:) = -101d0
Color_magnitude4_ymax(:) = -101d0
Color_magnitude4_ymargin(:) = 0.1
Color_magnitude4_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude4_other_yaxis1_name(:) = ''
Color_magnitude4_other_yaxis2_name(:) = ''
Color_magnitude4_other_yaxis_reversed(:) = .false.
Color_magnitude4_other_yaxis_log(:) = .false.
Color_magnitude4_other_ymin(:) = -101d0
Color_magnitude4_other_ymax(:) = -101d0
Color_magnitude4_other_ymargin(:) = 0.1
Color_magnitude4_other_dymin(:) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Color_magnitude4_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Color_magnitude4_file_flag = .false.
Color_magnitude4_file_dir = 'png'
Color_magnitude4_file_prefix = 'Color_magnitude4_'
Color_magnitude4_file_interval = 5
Color_magnitude4_file_width = -1
Color_magnitude4_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Color_magnitude5">Color_magnitude5 <a href="#Color_magnitude5" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Color_magnitude5_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Color_magnitude5_win_width = 6
Color_magnitude5_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Color_magnitude5_xleft = 0.15
Color_magnitude5_xright = 0.85
Color_magnitude5_ybot = 0.15
Color_magnitude5_ytop = 0.85
Color_magnitude5_txt_scale = 1.0
Color_magnitude5_title = 'Color_magnitude5'
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude5_xaxis1_name = ''
Color_magnitude5_xaxis2_name = ''
Color_magnitude5_xmin = -101d0
Color_magnitude5_xmax = -101d0
Color_magnitude5_max_width = 100
Color_magnitude5_dxmin = -1
Color_magnitude5_xaxis_reversed = .false.
Color_magnitude5_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude5_yaxis1_name(:) = ''
Color_magnitude5_yaxis2_name(:) = ''
Color_magnitude5_yaxis_reversed(:) = .false.
Color_magnitude5_yaxis_log(:) = .false.
Color_magnitude5_ymin(:) = -101d0
Color_magnitude5_ymax(:) = -101d0
Color_magnitude5_ymargin(:) = 0.1
Color_magnitude5_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude5_other_yaxis1_name(:) = ''
Color_magnitude5_other_yaxis2_name(:) = ''
Color_magnitude5_other_yaxis_reversed(:) = .false.
Color_magnitude5_other_yaxis_log(:) = .false.
Color_magnitude5_other_ymin(:) = -101d0
Color_magnitude5_other_ymax(:) = -101d0
Color_magnitude5_other_ymargin(:) = 0.1
Color_magnitude5_other_dymin(:) = -1
{% endhighlight %}


setup default

{% highlight fortran %}
Color_magnitude5_num_panels = 0
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude5_xaxis1_name = ''
Color_magnitude5_xaxis2_name = ''
Color_magnitude5_xmin = -101d0
Color_magnitude5_xmax = -101d0
Color_magnitude5_max_width = 100
Color_magnitude5_dxmin = -1
Color_magnitude5_xaxis_reversed = .false.
Color_magnitude5_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude5_yaxis1_name(:) = ''
Color_magnitude5_yaxis2_name(:) = ''
Color_magnitude5_yaxis_reversed(:) = .false.
Color_magnitude5_yaxis_log(:) = .false.
Color_magnitude5_ymin(:) = -101d0
Color_magnitude5_ymax(:) = -101d0
Color_magnitude5_ymargin(:) = 0.1
Color_magnitude5_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude5_other_yaxis1_name(:) = ''
Color_magnitude5_other_yaxis2_name(:) = ''
Color_magnitude5_other_yaxis_reversed(:) = .false.
Color_magnitude5_other_yaxis_log(:) = .false.
Color_magnitude5_other_ymin(:) = -101d0
Color_magnitude5_other_ymax(:) = -101d0
Color_magnitude5_other_ymargin(:) = 0.1
Color_magnitude5_other_dymin(:) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Color_magnitude5_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Color_magnitude5_file_flag = .false.
Color_magnitude5_file_dir = 'png'
Color_magnitude5_file_prefix = 'Color_magnitude5_'
Color_magnitude5_file_interval = 5
Color_magnitude5_file_width = -1
Color_magnitude5_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Color_magnitude6">Color_magnitude6 <a href="#Color_magnitude6" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Color_magnitude6_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Color_magnitude6_win_width = 6
Color_magnitude6_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Color_magnitude6_xleft = 0.15
Color_magnitude6_xright = 0.85
Color_magnitude6_ybot = 0.15
Color_magnitude6_ytop = 0.85
Color_magnitude6_txt_scale = 1.0
Color_magnitude6_title = 'Color_magnitude6'
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude6_xaxis1_name = ''
Color_magnitude6_xaxis2_name = ''
Color_magnitude6_xmin = -101d0
Color_magnitude6_xmax = -101d0
Color_magnitude6_max_width = 100
Color_magnitude6_dxmin = -1
Color_magnitude6_xaxis_reversed = .false.
Color_magnitude6_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude6_yaxis1_name(:) = ''
Color_magnitude6_yaxis2_name(:) = ''
Color_magnitude6_yaxis_reversed(:) = .false.
Color_magnitude6_yaxis_log(:) = .false.
Color_magnitude6_ymin(:) = -101d0
Color_magnitude6_ymax(:) = -101d0
Color_magnitude6_ymargin(:) = 0.1
Color_magnitude6_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude6_other_yaxis1_name(:) = ''
Color_magnitude6_other_yaxis2_name(:) = ''
Color_magnitude6_other_yaxis_reversed(:) = .false.
Color_magnitude6_other_yaxis_log(:) = .false.
Color_magnitude6_other_ymin(:) = -101d0
Color_magnitude6_other_ymax(:) = -101d0
Color_magnitude6_other_ymargin(:) = 0.1
Color_magnitude6_other_dymin(:) = -1
{% endhighlight %}


setup default

{% highlight fortran %}
Color_magnitude6_num_panels = 0
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude6_xaxis1_name = ''
Color_magnitude6_xaxis2_name = ''
Color_magnitude6_xmin = -101d0
Color_magnitude6_xmax = -101d0
Color_magnitude6_max_width = 100
Color_magnitude6_dxmin = -1
Color_magnitude6_xaxis_reversed = .false.
Color_magnitude6_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude6_yaxis1_name(:) = ''
Color_magnitude6_yaxis2_name(:) = ''
Color_magnitude6_yaxis_reversed(:) = .false.
Color_magnitude6_yaxis_log(:) = .false.
Color_magnitude6_ymin(:) = -101d0
Color_magnitude6_ymax(:) = -101d0
Color_magnitude6_ymargin(:) = 0.1
Color_magnitude6_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude6_other_yaxis1_name(:) = ''
Color_magnitude6_other_yaxis2_name(:) = ''
Color_magnitude6_other_yaxis_reversed(:) = .false.
Color_magnitude6_other_yaxis_log(:) = .false.
Color_magnitude6_other_ymin(:) = -101d0
Color_magnitude6_other_ymax(:) = -101d0
Color_magnitude6_other_ymargin(:) = 0.1
Color_magnitude6_other_dymin(:) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Color_magnitude6_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Color_magnitude6_file_flag = .false.
Color_magnitude6_file_dir = 'png'
Color_magnitude6_file_prefix = 'Color_magnitude6_'
Color_magnitude6_file_interval = 5
Color_magnitude6_file_width = -1
Color_magnitude6_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Color_magnitude7">Color_magnitude7 <a href="#Color_magnitude7" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Color_magnitude7_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Color_magnitude7_win_width = 6
Color_magnitude7_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Color_magnitude7_xleft = 0.15
Color_magnitude7_xright = 0.85
Color_magnitude7_ybot = 0.15
Color_magnitude7_ytop = 0.85
Color_magnitude7_txt_scale = 1.0
Color_magnitude7_title = 'Color_magnitude7'
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude7_xaxis1_name = ''
Color_magnitude7_xaxis2_name = ''
Color_magnitude7_xmin = -101d0
Color_magnitude7_xmax = -101d0
Color_magnitude7_max_width = 100
Color_magnitude7_dxmin = -1
Color_magnitude7_xaxis_reversed = .false.
Color_magnitude7_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude7_yaxis1_name(:) = ''
Color_magnitude7_yaxis2_name(:) = ''
Color_magnitude7_yaxis_reversed(:) = .false.
Color_magnitude7_yaxis_log(:) = .false.
Color_magnitude7_ymin(:) = -101d0
Color_magnitude7_ymax(:) = -101d0
Color_magnitude7_ymargin(:) = 0.1
Color_magnitude7_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude7_other_yaxis1_name(:) = ''
Color_magnitude7_other_yaxis2_name(:) = ''
Color_magnitude7_other_yaxis_reversed(:) = .false.
Color_magnitude7_other_yaxis_log(:) = .false.
Color_magnitude7_other_ymin(:) = -101d0
Color_magnitude7_other_ymax(:) = -101d0
Color_magnitude7_other_ymargin(:) = 0.1
Color_magnitude7_other_dymin(:) = -1
{% endhighlight %}


setup default

{% highlight fortran %}
Color_magnitude7_num_panels = 0
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude7_xaxis1_name = ''
Color_magnitude7_xaxis2_name = ''
Color_magnitude7_xmin = -101d0
Color_magnitude7_xmax = -101d0
Color_magnitude7_max_width = 100
Color_magnitude7_dxmin = -1
Color_magnitude7_xaxis_reversed = .false.
Color_magnitude7_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude7_yaxis1_name(:) = ''
Color_magnitude7_yaxis2_name(:) = ''
Color_magnitude7_yaxis_reversed(:) = .false.
Color_magnitude7_yaxis_log(:) = .false.
Color_magnitude7_ymin(:) = -101d0
Color_magnitude7_ymax(:) = -101d0
Color_magnitude7_ymargin(:) = 0.1
Color_magnitude7_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude7_other_yaxis1_name(:) = ''
Color_magnitude7_other_yaxis2_name(:) = ''
Color_magnitude7_other_yaxis_reversed(:) = .false.
Color_magnitude7_other_yaxis_log(:) = .false.
Color_magnitude7_other_ymin(:) = -101d0
Color_magnitude7_other_ymax(:) = -101d0
Color_magnitude7_other_ymargin(:) = 0.1
Color_magnitude7_other_dymin(:) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Color_magnitude7_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Color_magnitude7_file_flag = .false.
Color_magnitude7_file_dir = 'png'
Color_magnitude7_file_prefix = 'Color_magnitude7_'
Color_magnitude7_file_interval = 5
Color_magnitude7_file_width = -1
Color_magnitude7_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Color_magnitude8">Color_magnitude8 <a href="#Color_magnitude8" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Color_magnitude8_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Color_magnitude8_win_width = 6
Color_magnitude8_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Color_magnitude8_xleft = 0.15
Color_magnitude8_xright = 0.85
Color_magnitude8_ybot = 0.15
Color_magnitude8_ytop = 0.85
Color_magnitude8_txt_scale = 1.0
Color_magnitude8_title = 'Color_magnitude8'
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude8_xaxis1_name = ''
Color_magnitude8_xaxis2_name = ''
Color_magnitude8_xmin = -101d0
Color_magnitude8_xmax = -101d0
Color_magnitude8_max_width = 100
Color_magnitude8_dxmin = -1
Color_magnitude8_xaxis_reversed = .false.
Color_magnitude8_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude8_yaxis1_name(:) = ''
Color_magnitude8_yaxis2_name(:) = ''
Color_magnitude8_yaxis_reversed(:) = .false.
Color_magnitude8_yaxis_log(:) = .false.
Color_magnitude8_ymin(:) = -101d0
Color_magnitude8_ymax(:) = -101d0
Color_magnitude8_ymargin(:) = 0.1
Color_magnitude8_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude8_other_yaxis1_name(:) = ''
Color_magnitude8_other_yaxis2_name(:) = ''
Color_magnitude8_other_yaxis_reversed(:) = .false.
Color_magnitude8_other_yaxis_log(:) = .false.
Color_magnitude8_other_ymin(:) = -101d0
Color_magnitude8_other_ymax(:) = -101d0
Color_magnitude8_other_ymargin(:) = 0.1
Color_magnitude8_other_dymin(:) = -1
{% endhighlight %}


setup default

{% highlight fortran %}
Color_magnitude8_num_panels = 0
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude8_xaxis1_name = ''
Color_magnitude8_xaxis2_name = ''
Color_magnitude8_xmin = -101d0
Color_magnitude8_xmax = -101d0
Color_magnitude8_max_width = 100
Color_magnitude8_dxmin = -1
Color_magnitude8_xaxis_reversed = .false.
Color_magnitude8_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude8_yaxis1_name(:) = ''
Color_magnitude8_yaxis2_name(:) = ''
Color_magnitude8_yaxis_reversed(:) = .false.
Color_magnitude8_yaxis_log(:) = .false.
Color_magnitude8_ymin(:) = -101d0
Color_magnitude8_ymax(:) = -101d0
Color_magnitude8_ymargin(:) = 0.1
Color_magnitude8_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude8_other_yaxis1_name(:) = ''
Color_magnitude8_other_yaxis2_name(:) = ''
Color_magnitude8_other_yaxis_reversed(:) = .false.
Color_magnitude8_other_yaxis_log(:) = .false.
Color_magnitude8_other_ymin(:) = -101d0
Color_magnitude8_other_ymax(:) = -101d0
Color_magnitude8_other_ymargin(:) = 0.1
Color_magnitude8_other_dymin(:) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Color_magnitude8_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Color_magnitude8_file_flag = .false.
Color_magnitude8_file_dir = 'png'
Color_magnitude8_file_prefix = 'Color_magnitude8_'
Color_magnitude8_file_interval = 5
Color_magnitude8_file_width = -1
Color_magnitude8_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Color_magnitude9">Color_magnitude9 <a href="#Color_magnitude9" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Color_magnitude9_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Color_magnitude9_win_width = 6
Color_magnitude9_win_aspect_ratio = 0.75
{% endhighlight %}


{% highlight fortran %}
Color_magnitude9_xleft = 0.15
Color_magnitude9_xright = 0.85
Color_magnitude9_ybot = 0.15
Color_magnitude9_ytop = 0.85
Color_magnitude9_txt_scale = 1.0
Color_magnitude9_title = 'Color_magnitude9'
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude9_xaxis1_name = ''
Color_magnitude9_xaxis2_name = ''
Color_magnitude9_xmin = -101d0
Color_magnitude9_xmax = -101d0
Color_magnitude9_max_width = 100
Color_magnitude9_dxmin = -1
Color_magnitude9_xaxis_reversed = .false.
Color_magnitude9_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude9_yaxis1_name(:) = ''
Color_magnitude9_yaxis2_name(:) = ''
Color_magnitude9_yaxis_reversed(:) = .false.
Color_magnitude9_yaxis_log(:) = .false.
Color_magnitude9_ymin(:) = -101d0
Color_magnitude9_ymax(:) = -101d0
Color_magnitude9_ymargin(:) = 0.1
Color_magnitude9_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude9_other_yaxis1_name(:) = ''
Color_magnitude9_other_yaxis2_name(:) = ''
Color_magnitude9_other_yaxis_reversed(:) = .false.
Color_magnitude9_other_yaxis_log(:) = .false.
Color_magnitude9_other_ymin(:) = -101d0
Color_magnitude9_other_ymax(:) = -101d0
Color_magnitude9_other_ymargin(:) = 0.1
Color_magnitude9_other_dymin(:) = -1
{% endhighlight %}


setup default

{% highlight fortran %}
Color_magnitude9_num_panels = 0
{% endhighlight %}


Plots xaxis1-xaxis2 leave xaxis2 blank if you only want to plot xaxis1.

{% highlight fortran %}
Color_magnitude9_xaxis1_name = ''
Color_magnitude9_xaxis2_name = ''
Color_magnitude9_xmin = -101d0
Color_magnitude9_xmax = -101d0
Color_magnitude9_max_width = 100
Color_magnitude9_dxmin = -1
Color_magnitude9_xaxis_reversed = .false.
Color_magnitude9_xaxis_log = .false.
{% endhighlight %}


Plots yaxis1-yaxis2 leave yaxis2 blank if you only want to plot yaxis1.

{% highlight fortran %}
Color_magnitude9_yaxis1_name(:) = ''
Color_magnitude9_yaxis2_name(:) = ''
Color_magnitude9_yaxis_reversed(:) = .false.
Color_magnitude9_yaxis_log(:) = .false.
Color_magnitude9_ymin(:) = -101d0
Color_magnitude9_ymax(:) = -101d0
Color_magnitude9_ymargin(:) = 0.1
Color_magnitude9_dymin(:) = -1
{% endhighlight %}


Plots `other_yaxis1-other_yaxis2` leave `other_yaxis2` blank if you only want to plot `other_yaxis1`.

{% highlight fortran %}
Color_magnitude9_other_yaxis1_name(:) = ''
Color_magnitude9_other_yaxis2_name(:) = ''
Color_magnitude9_other_yaxis_reversed(:) = .false.
Color_magnitude9_other_yaxis_log(:) = .false.
Color_magnitude9_other_ymin(:) = -101d0
Color_magnitude9_other_ymax(:) = -101d0
Color_magnitude9_other_ymargin(:) = 0.1
Color_magnitude9_other_dymin(:) = -1
{% endhighlight %}


Enables calling a subroutine to add extra information to a plot
see `$MESA_DIR/star/other/pgstar_decorator.f90`

{% highlight fortran %}
Color_magnitude9_use_decorator = .false.
{% endhighlight %}


file output

{% highlight fortran %}
Color_magnitude9_file_flag = .false.
Color_magnitude9_file_dir = 'png'
Color_magnitude9_file_prefix = 'Color_magnitude9_'
Color_magnitude9_file_interval = 5
Color_magnitude9_file_width = -1
Color_magnitude9_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Text_Summary">Text Summary <a href="#Text_Summary" title="Permalink to this location">¶</a></h1>


<h3 id="Text_Summary_1">Text_Summary 1 <a href="#Text_Summary_1" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Text_Summary1_win_flag = .false.
Text_Summary1_win_width = 10
Text_Summary1_win_aspect_ratio = 0.15
{% endhighlight %}


{% highlight fortran %}
Text_Summary1_xleft = 0.02
Text_Summary1_xright = 0.98
Text_Summary1_ybot = 0.08
Text_Summary1_ytop = 0.98
Text_Summary1_txt_scale = 4.5
Text_Summary1_title = ''
{% endhighlight %}


setup default

{% highlight fortran %}
Text_Summary1_num_rows = 8
Text_Summary1_num_cols = 4
Text_Summary1_name(:,:) = ''
{% endhighlight %}


{% highlight fortran %}
Text_Summary1_name(1,1) = 'model_number'
Text_Summary1_name(2,1) = 'log_star_age'
Text_Summary1_name(3,1) = 'log_dt'
Text_Summary1_name(4,1) = 'log_L'
Text_Summary1_name(5,1) = 'log_Teff'
Text_Summary1_name(6,1) = 'log_R'
Text_Summary1_name(7,1) = 'log_g'
Text_Summary1_name(8,1) = 'log_surf_cell_P'
{% endhighlight %}


{% highlight fortran %}
Text_Summary1_name(1,2) = 'star_mass'
Text_Summary1_name(2,2) = 'log_abs_mdot'
Text_Summary1_name(3,2) = 'he_core_mass'
Text_Summary1_name(4,2) = 'c_core_mass'
Text_Summary1_name(5,2) = 'cz_bot_mass'
Text_Summary1_name(6,2) = 'cz_top_mass'
Text_Summary1_name(7,2) = 'cz_bot_radius'
Text_Summary1_name(8,2) = 'cz_top_radius'
{% endhighlight %}


{% highlight fortran %}
Text_Summary1_name(1,3) = 'log_cntr_T'
Text_Summary1_name(2,3) = 'log_cntr_Rho'
Text_Summary1_name(3,3) = 'log_center_P'
Text_Summary1_name(4,3) = 'center h1'
Text_Summary1_name(5,3) = 'center he4'
Text_Summary1_name(6,3) = 'center c12'
Text_Summary1_name(7,3) = 'center n14'
Text_Summary1_name(8,3) = 'center o16'
{% endhighlight %}


{% highlight fortran %}
Text_Summary1_name(1,4) = 'log_Lnuc'
Text_Summary1_name(2,4) = 'log_Lneu'
Text_Summary1_name(3,4) = 'log_LH'
Text_Summary1_name(4,4) = 'log_LHe'
Text_Summary1_name(5,4) = 'log_LZ'
Text_Summary1_name(6,4) = 'num_zones'
Text_Summary1_name(7,4) = 'num_retries'
Text_Summary1_name(8,4) = 'num_backups'
{% endhighlight %}


file output

{% highlight fortran %}
Text_Summary1_file_flag = .false.
Text_Summary1_file_dir = 'png'
Text_Summary1_file_prefix = 'Text_Summary1_'
Text_Summary1_file_interval = 5
Text_Summary1_file_width = -1
Text_Summary1_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Text_Summary2">Text_Summary2 <a href="#Text_Summary2" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Text_Summary2_win_flag = .false.
Text_Summary2_win_width = 6
Text_Summary2_win_aspect_ratio = 1.5
{% endhighlight %}


{% highlight fortran %}
Text_Summary2_xleft = 0.02
Text_Summary2_xright = 0.98
Text_Summary2_ybot = 0.08
Text_Summary2_ytop = 0.98
Text_Summary2_txt_scale = 4.5
Text_Summary2_title = ''
{% endhighlight %}


{% highlight fortran %}
Text_Summary2_num_rows = 0
Text_Summary2_num_cols = 0
Text_Summary2_name(:,:) = ''
{% endhighlight %}


file output

{% highlight fortran %}
Text_Summary2_file_flag = .false.
Text_Summary2_file_dir = 'png'
Text_Summary2_file_prefix = 'Text_Summary2_'
Text_Summary2_file_interval = 5
Text_Summary2_file_width = -1
Text_Summary2_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Text_Summary3">Text_Summary3 <a href="#Text_Summary3" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Text_Summary3_win_flag = .false.
Text_Summary3_win_width = 6
Text_Summary3_win_aspect_ratio = 1.5
{% endhighlight %}


{% highlight fortran %}
Text_Summary3_xleft = 0.02
Text_Summary3_xright = 0.98
Text_Summary3_ybot = 0.08
Text_Summary3_ytop = 0.98
Text_Summary3_txt_scale = 4.5
Text_Summary3_title = ''
{% endhighlight %}


{% highlight fortran %}
Text_Summary3_num_rows = 0
Text_Summary3_num_cols = 0
Text_Summary3_name(:,:) = ''
{% endhighlight %}


file output

{% highlight fortran %}
Text_Summary3_file_flag = .false.
Text_Summary3_file_dir = 'png'
Text_Summary3_file_prefix = 'Text_Summary3_'
Text_Summary3_file_interval = 5
Text_Summary3_file_width = -1
Text_Summary3_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Text_Summary4">Text_Summary4 <a href="#Text_Summary4" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Text_Summary4_win_flag = .false.
Text_Summary4_win_width = 6
Text_Summary4_win_aspect_ratio = 1.5
{% endhighlight %}


{% highlight fortran %}
Text_Summary4_xleft = 0.02
Text_Summary4_xright = 0.98
Text_Summary4_ybot = 0.08
Text_Summary4_ytop = 0.98
Text_Summary4_txt_scale = 4.5
Text_Summary4_title = ''
{% endhighlight %}


{% highlight fortran %}
Text_Summary4_num_rows = 0
Text_Summary4_num_cols = 0
Text_Summary4_name(:,:) = ''
{% endhighlight %}


file output

{% highlight fortran %}
Text_Summary4_file_flag = .false.
Text_Summary4_file_dir = 'png'
Text_Summary4_file_prefix = 'Text_Summary4_'
Text_Summary4_file_interval = 5
Text_Summary4_file_width = -1
Text_Summary4_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Text_Summary5">Text_Summary5 <a href="#Text_Summary5" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Text_Summary5_win_flag = .false.
Text_Summary5_win_width = 6
Text_Summary5_win_aspect_ratio = 1.5
{% endhighlight %}


{% highlight fortran %}
Text_Summary5_xleft = 0.02
Text_Summary5_xright = 0.98
Text_Summary5_ybot = 0.08
Text_Summary5_ytop = 0.98
Text_Summary5_txt_scale = 4.5
Text_Summary5_title = ''
{% endhighlight %}


{% highlight fortran %}
Text_Summary5_num_rows = 0
Text_Summary5_num_cols = 0
Text_Summary5_name(:,:) = ''
{% endhighlight %}


file output

{% highlight fortran %}
Text_Summary5_file_flag = .false.
Text_Summary5_file_dir = 'png'
Text_Summary5_file_prefix = 'Text_Summary5_'
Text_Summary5_file_interval = 5
Text_Summary5_file_width = -1
Text_Summary5_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Text_Summary6">Text_Summary6 <a href="#Text_Summary6" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Text_Summary6_win_flag = .false.
Text_Summary6_win_width = 6
Text_Summary6_win_aspect_ratio = 1.5
{% endhighlight %}


{% highlight fortran %}
Text_Summary6_xleft = 0.02
Text_Summary6_xright = 0.98
Text_Summary6_ybot = 0.08
Text_Summary6_ytop = 0.98
Text_Summary6_txt_scale = 4.5
Text_Summary6_title = ''
{% endhighlight %}


{% highlight fortran %}
Text_Summary6_num_rows = 0
Text_Summary6_num_cols = 0
Text_Summary6_name(:,:) = ''
{% endhighlight %}


file output

{% highlight fortran %}
Text_Summary6_file_flag = .false.
Text_Summary6_file_dir = 'png'
Text_Summary6_file_prefix = 'Text_Summary6_'
Text_Summary6_file_interval = 5
Text_Summary6_file_width = -1
Text_Summary6_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Text_Summary7">Text_Summary7 <a href="#Text_Summary7" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Text_Summary7_win_flag = .false.
Text_Summary7_win_width = 6
Text_Summary7_win_aspect_ratio = 1.5
{% endhighlight %}


{% highlight fortran %}
Text_Summary7_xleft = 0.02
Text_Summary7_xright = 0.98
Text_Summary7_ybot = 0.08
Text_Summary7_ytop = 0.98
Text_Summary7_txt_scale = 4.5
Text_Summary7_title = ''
{% endhighlight %}


{% highlight fortran %}
Text_Summary7_num_rows = 0
Text_Summary7_num_cols = 0
Text_Summary7_name(:,:) = ''
{% endhighlight %}


file output

{% highlight fortran %}
Text_Summary7_file_flag = .false.
Text_Summary7_file_dir = 'png'
Text_Summary7_file_prefix = 'Text_Summary7_'
Text_Summary7_file_interval = 5
Text_Summary7_file_width = -1
Text_Summary7_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Text_Summary8">Text_Summary8 <a href="#Text_Summary8" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Text_Summary8_win_flag = .false.
Text_Summary8_win_width = 6
Text_Summary8_win_aspect_ratio = 1.5
{% endhighlight %}


{% highlight fortran %}
Text_Summary8_xleft = 0.02
Text_Summary8_xright = 0.98
Text_Summary8_ybot = 0.08
Text_Summary8_ytop = 0.98
Text_Summary8_txt_scale = 4.5
Text_Summary8_title = ''
{% endhighlight %}


{% highlight fortran %}
Text_Summary8_num_rows = 0
Text_Summary8_num_cols = 0
Text_Summary8_name(:,:) = ''
{% endhighlight %}


file output

{% highlight fortran %}
Text_Summary8_file_flag = .false.
Text_Summary8_file_dir = 'png'
Text_Summary8_file_prefix = 'Text_Summary8_'
Text_Summary8_file_interval = 5
Text_Summary8_file_width = -1
Text_Summary8_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Text_Summary9">Text_Summary9 <a href="#Text_Summary9" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Text_Summary9_win_flag = .false.
Text_Summary9_win_width = 6
Text_Summary9_win_aspect_ratio = 1.5
{% endhighlight %}


{% highlight fortran %}
Text_Summary9_xleft = 0.02
Text_Summary9_xright = 0.98
Text_Summary9_ybot = 0.08
Text_Summary9_ytop = 0.98
Text_Summary9_txt_scale = 4.5
Text_Summary9_title = ''
{% endhighlight %}


{% highlight fortran %}
Text_Summary9_num_rows = 0
Text_Summary9_num_cols = 0
Text_Summary9_name(:,:) = ''
{% endhighlight %}


file output

{% highlight fortran %}
Text_Summary9_file_flag = .false.
Text_Summary9_file_dir = 'png'
Text_Summary9_file_prefix = 'Text_Summary9_'
Text_Summary9_file_interval = 5
Text_Summary9_file_width = -1
Text_Summary9_file_aspect_ratio = -1
{% endhighlight %}

<h1 id="Grid">Grid <a href="#Grid" title="Permalink to this location">¶</a></h1>


<h3 id="Grid1">Grid1 <a href="#Grid1" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Grid1_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Grid1_win_width = 6
Grid1_win_aspect_ratio = 1
{% endhighlight %}


{% highlight fortran %}
Grid1_xleft = 0.12
Grid1_xright = 0.95
Grid1_ybot = 0.08
Grid1_ytop = 0.92
Grid1_title = ''
{% endhighlight %}


{% highlight fortran %}
Grid1_plot_name(:) = ''
Grid1_plot_row(:) = 1
Grid1_plot_rowspan(:) = 1
Grid1_plot_col(:) = 1
Grid1_plot_colspan(:) = 1
Grid1_plot_pad_left(:) = 0.0
Grid1_plot_pad_right(:) = 0.0
Grid1_plot_pad_top(:) = 0.0
Grid1_plot_pad_bot(:) = 0.0
Grid1_txt_scale_factor(:) = 0.7
{% endhighlight %}


set default

{% highlight fortran %}
Grid1_num_cols = 2
Grid1_num_rows = 8
Grid1_num_plots = 4
{% endhighlight %}


{% highlight fortran %}
Grid1_plot_name(1) = 'TRho_Profile'
Grid1_plot_row(1) = 1
Grid1_plot_rowspan(1) = 4
Grid1_plot_col(1) = 1
Grid1_plot_colspan(1) = 2
Grid1_plot_pad_left(1) = 0.0
Grid1_plot_pad_right(1) = 0.0
Grid1_plot_pad_top(1) = 0.0
Grid1_plot_pad_bot(1) = 0.1
Grid1_txt_scale_factor(1) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid1_plot_name(2) = 'HR'
Grid1_plot_row(2) = 5
Grid1_plot_rowspan(2) = 2
Grid1_plot_col(2) = 1
Grid1_plot_colspan(2) = 1
Grid1_plot_pad_left(2) = 0.03
Grid1_plot_pad_right(2) = 0.07
Grid1_plot_pad_top(2) = 0.03
Grid1_plot_pad_bot(2) = 0.0
Grid1_txt_scale_factor(2) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid1_plot_name(3) = 'TRho'
Grid1_plot_row(3) = 5
Grid1_plot_rowspan(3) = 2
Grid1_plot_col(3) = 2
Grid1_plot_colspan(3) = 1
Grid1_plot_pad_left(3) = 0.07
Grid1_plot_pad_right(3) = 0.03
Grid1_plot_pad_top(3) = 0.03
Grid1_plot_pad_bot(3) = 0.0
Grid1_txt_scale_factor(3) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid1_plot_name(4) = 'Text_Summary1'
Grid1_plot_row(4) = 7
Grid1_plot_rowspan(4) = 2
Grid1_plot_col(4) = 1
Grid1_plot_colspan(4) = 2
Grid1_plot_pad_left(4) = -0.08
Grid1_plot_pad_right(4) = 0.0
Grid1_plot_pad_top(4) = 0.08
Grid1_plot_pad_bot(4) = -0.05
Grid1_txt_scale_factor(4) = 0.2
{% endhighlight %}


file output

{% highlight fortran %}
Grid1_file_flag = .false.
Grid1_file_dir = 'png'
Grid1_file_prefix = 'grid1'
Grid1_file_interval = 5
Grid1_file_width = 9
Grid1_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Grid2">Grid2 <a href="#Grid2" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Grid2_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Grid2_win_width = 6
Grid2_win_aspect_ratio = 1
{% endhighlight %}


{% highlight fortran %}
Grid2_xleft = 0.12
Grid2_xright = 0.95
Grid2_ybot = 0.08
Grid2_ytop = 0.92
Grid2_title = ''
{% endhighlight %}


{% highlight fortran %}
Grid2_plot_name(:) = ''
Grid2_plot_row(:) = 1
Grid2_plot_rowspan(:) = 1
Grid2_plot_col(:) = 1
Grid2_plot_colspan(:) = 1
Grid2_plot_pad_left(:) = 0.0
Grid2_plot_pad_right(:) = 0.0
Grid2_plot_pad_top(:) = 0.0
Grid2_plot_pad_bot(:) = 0.0
Grid2_txt_scale_factor(:) = 0.7
{% endhighlight %}


set default

{% highlight fortran %}
Grid2_win_width = 9
Grid2_win_aspect_ratio = 0.6
{% endhighlight %}


{% highlight fortran %}
Grid2_num_cols = 4
Grid2_num_rows = 8
Grid2_num_plots = 5
{% endhighlight %}


{% highlight fortran %}
Grid2_plot_name(1) = 'TRho_Profile'
Grid2_plot_row(1) = 1
Grid2_plot_rowspan(1) = 4
Grid2_plot_col(1) = 1
Grid2_plot_colspan(1) = 2
Grid2_plot_pad_left(1) = 0.0
Grid2_plot_pad_right(1) = 0.0
Grid2_plot_pad_top(1) = 0.0
Grid2_plot_pad_bot(1) = 0.1
Grid2_txt_scale_factor(1) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid2_plot_name(2) = 'HR'
Grid2_plot_row(2) = 5
Grid2_plot_rowspan(2) = 2
Grid2_plot_col(2) = 1
Grid2_plot_colspan(2) = 1
Grid2_plot_pad_left(2) = 0.00
Grid2_plot_pad_right(2) = 0.04
Grid2_plot_pad_top(2) = 0.03
Grid2_plot_pad_bot(2) = 0.0
Grid2_txt_scale_factor(2) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid2_plot_name(3) = 'TRho'
Grid2_plot_row(3) = 5
Grid2_plot_rowspan(3) = 2
Grid2_plot_col(3) = 2
Grid2_plot_colspan(3) = 1
Grid2_plot_pad_left(3) = 0.04
Grid2_plot_pad_right(3) = 0.00
Grid2_plot_pad_top(3) = 0.03
Grid2_plot_pad_bot(3) = 0.0
Grid2_txt_scale_factor(3) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid2_plot_name(4) = 'Text_Summary1'
Grid2_plot_row(4) = 7
Grid2_plot_rowspan(4) = 2
Grid2_plot_col(4) = 1
Grid2_plot_colspan(4) = 4
Grid2_plot_pad_left(4) = -0.08
Grid2_plot_pad_right(4) = 0.0
Grid2_plot_pad_top(4) = 0.08
Grid2_plot_pad_bot(4) = -0.04
Grid2_txt_scale_factor(4) = 0.19
{% endhighlight %}


{% highlight fortran %}
Grid2_plot_name(5) = 'Abundance'
Grid2_plot_row(5) = 1
Grid2_plot_rowspan(5) = 6
Grid2_plot_col(5) = 3
Grid2_plot_colspan(5) = 2
Grid2_plot_pad_left(5) = 0.07
Grid2_plot_pad_right(5) = 0.03
Grid2_plot_pad_top(5) = 0.0
Grid2_plot_pad_bot(5) = 0.0
Grid2_txt_scale_factor(5) = 0.65
{% endhighlight %}


file output

{% highlight fortran %}
Grid2_file_flag = .false.
Grid2_file_dir = 'png'
Grid2_file_prefix = 'Grid2'
Grid2_file_interval = 5
Grid2_file_width = 9
Grid2_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Grid3">Grid3 <a href="#Grid3" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Grid3_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Grid3_win_width = 6
Grid3_win_aspect_ratio = 1.2
{% endhighlight %}


{% highlight fortran %}
Grid3_xleft = 0.10
Grid3_xright = 0.89
Grid3_ybot = 0.08
Grid3_ytop = 0.92
Grid3_title = ''
{% endhighlight %}


{% highlight fortran %}
Grid3_num_cols = 1
Grid3_num_rows = 1
Grid3_num_plots = 1
{% endhighlight %}


{% highlight fortran %}
Grid3_plot_name(:) = ''
Grid3_plot_row(:) = 1
Grid3_plot_rowspan(:) = 1
Grid3_plot_col(:) = 1
Grid3_plot_colspan(:) = 1
Grid3_plot_pad_left(:) = 0.0
Grid3_plot_pad_right(:) = 0.0
Grid3_plot_pad_top(:) = 0.0
Grid3_plot_pad_bot(:) = 0.0
Grid3_txt_scale_factor(:) = 0.7
{% endhighlight %}


set default

{% highlight fortran %}
Grid3_num_cols = 1
Grid3_num_rows = 7
Grid3_num_plots = 3
{% endhighlight %}


{% highlight fortran %}
Grid3_plot_name(1) = 'TRho_Profile'
Grid3_plot_row(1) = 1
Grid3_plot_rowspan(1) = 3
Grid3_plot_col(1) = 1
Grid3_plot_colspan(1) = 1
Grid3_plot_pad_left(1) = 0.03
Grid3_plot_pad_right(1) = 0.03
Grid3_plot_pad_top(1) = 0.04
Grid3_plot_pad_bot(1) = 0.07
Grid3_txt_scale_factor(1) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid3_plot_name(2) = 'Summary_Profile'
Grid3_plot_row(2) = 4
Grid3_plot_rowspan(2) = 2
Grid3_plot_col(2) = 1
Grid3_plot_colspan(2) = 1
Grid3_plot_pad_left(2) = 0.03
Grid3_plot_pad_right(2) = 0.03
Grid3_plot_pad_top(2) = 0.04
Grid3_plot_pad_bot(2) = 0.07
Grid3_txt_scale_factor(2) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid3_plot_name(3) = 'Kipp'
Grid3_plot_row(3) = 6
Grid3_plot_rowspan(3) = 2
Grid3_plot_col(3) = 1
Grid3_plot_colspan(3) = 1
Grid3_plot_pad_left(3) = 0.03
Grid3_plot_pad_right(3) = 0.03
Grid3_plot_pad_top(3) = 0.04
Grid3_plot_pad_bot(3) = 0.07
Grid3_txt_scale_factor(3) = 0.7
{% endhighlight %}


file output

{% highlight fortran %}
Grid3_file_flag = .false.
Grid3_file_dir = 'png'
Grid3_file_prefix = 'grid3_'
Grid3_file_interval = 5
Grid3_file_width = -1
Grid3_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Grid4">Grid4 <a href="#Grid4" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Grid4_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Grid4_win_width = 7
Grid4_win_aspect_ratio = 1
{% endhighlight %}


{% highlight fortran %}
Grid4_xleft = 0.12
Grid4_xright = 0.95
Grid4_ybot = 0.08
Grid4_ytop = 0.92
Grid4_title = ''
{% endhighlight %}


{% highlight fortran %}
Grid4_plot_name(:) = ''
Grid4_plot_row(:) = 1
Grid4_plot_rowspan(:) = 1
Grid4_plot_col(:) = 1
Grid4_plot_colspan(:) = 1
Grid4_plot_pad_left(:) = 0.0
Grid4_plot_pad_right(:) = 0.0
Grid4_plot_pad_top(:) = 0.0
Grid4_plot_pad_bot(:) = 0.0
Grid4_txt_scale_factor(:) = 0.7
{% endhighlight %}


set default

{% highlight fortran %}
Grid4_num_cols = 10
Grid4_num_rows = 9
Grid4_num_plots = 6
{% endhighlight %}


{% highlight fortran %}
Grid4_plot_name(1) = 'TRho_Profile'
Grid4_plot_row(1) = 1
Grid4_plot_rowspan(1) = 3
Grid4_plot_col(1) = 1
Grid4_plot_colspan(1) = 5
Grid4_plot_pad_left(1) = 0.0
Grid4_plot_pad_right(1) = 0.09
Grid4_plot_pad_top(1) = 0.0
Grid4_plot_pad_bot(1) = 0.1
Grid4_txt_scale_factor(1) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid4_plot_name(2) = 'Summary_Profile'
Grid4_plot_row(2) = 1
Grid4_plot_rowspan(2) = 3
Grid4_plot_col(2) = 6
Grid4_plot_colspan(2) = 5
Grid4_plot_pad_left(2) = 0.00
Grid4_plot_pad_right(2) = 0.09
Grid4_plot_pad_top(2) = 0.0
Grid4_plot_pad_bot(2) = 0.1
Grid4_txt_scale_factor(2) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid4_plot_name(3) = 'HR'
Grid4_plot_row(3) = 4
Grid4_plot_rowspan(3) = 2
Grid4_plot_col(3) = 1
Grid4_plot_colspan(3) = 2
Grid4_plot_pad_left(3) = 0.0
Grid4_plot_pad_right(3) = 0.01
Grid4_plot_pad_top(3) = 0.03
Grid4_plot_pad_bot(3) = 0.07
Grid4_txt_scale_factor(3) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid4_plot_name(4) = 'TRho'
Grid4_plot_row(4) = 6
Grid4_plot_rowspan(4) = 2
Grid4_plot_col(4) = 1
Grid4_plot_colspan(4) = 2
Grid4_plot_pad_left(4) = 0.0
Grid4_plot_pad_right(4) = 0.01
Grid4_plot_pad_top(4) = 0.04
Grid4_plot_pad_bot(4) = 0.06
Grid4_txt_scale_factor(4) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid4_plot_name(5) = 'Kipp'
Grid4_plot_row(5) = 4
Grid4_plot_rowspan(5) = 4
Grid4_plot_col(5) = 3
Grid4_plot_colspan(5) = 7
Grid4_plot_pad_left(5) = 0.09
Grid4_plot_pad_right(5) = 0.0
Grid4_plot_pad_top(5) = 0.03
Grid4_plot_pad_bot(5) = 0.06
Grid4_txt_scale_factor(5) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid4_plot_name(6) = 'Text_Summary1'
Grid4_plot_row(6) = 8
Grid4_plot_rowspan(6) = 2
Grid4_plot_col(6) = 1
Grid4_plot_colspan(6) = 10
Grid4_plot_pad_left(6) = -0.08
Grid4_plot_pad_right(6) = 0.0
Grid4_plot_pad_top(6) = 0.03
Grid4_plot_pad_bot(6) = 0.0
Grid4_txt_scale_factor(6) = 0.17
{% endhighlight %}


file output

{% highlight fortran %}
Grid4_file_flag = .false.
Grid4_file_dir = 'png'
Grid4_file_prefix = 'grid4_'
Grid4_file_interval = 5
Grid4_file_width = -1
Grid4_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Grid5">Grid5 <a href="#Grid5" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Grid5_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Grid5_win_width = 7
Grid5_win_aspect_ratio = 1
{% endhighlight %}


{% highlight fortran %}
Grid5_xleft = 0.12
Grid5_xright = 0.95
Grid5_ybot = 0.08
Grid5_ytop = 0.92
Grid5_title = ''
{% endhighlight %}


{% highlight fortran %}
Grid5_plot_name(:) = ''
Grid5_plot_row(:) = 1
Grid5_plot_rowspan(:) = 1
Grid5_plot_col(:) = 1
Grid5_plot_colspan(:) = 1
Grid5_plot_pad_left(:) = 0.0
Grid5_plot_pad_right(:) = 0.0
Grid5_plot_pad_top(:) = 0.0
Grid5_plot_pad_bot(:) = 0.0
Grid5_txt_scale_factor(:) = 0.7
{% endhighlight %}


set default

{% highlight fortran %}
Grid5_num_cols = 10
Grid5_num_rows = 7
Grid5_num_plots = 5
{% endhighlight %}


{% highlight fortran %}
Grid5_plot_name(1) = 'TRho_Profile'
Grid5_plot_row(1) = 1
Grid5_plot_rowspan(1) = 3
Grid5_plot_col(1) = 1
Grid5_plot_colspan(1) = 5
Grid5_plot_pad_left(1) = 0.0
Grid5_plot_pad_right(1) = 0.09
Grid5_plot_pad_top(1) = 0.0
Grid5_plot_pad_bot(1) = 0.1
Grid5_txt_scale_factor(1) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid5_plot_name(2) = 'Summary_Profile'
Grid5_plot_row(2) = 1
Grid5_plot_rowspan(2) = 3
Grid5_plot_col(2) = 6
Grid5_plot_colspan(2) = 5
Grid5_plot_pad_left(2) = 0.00
Grid5_plot_pad_right(2) = 0.09
Grid5_plot_pad_top(2) = 0.0
Grid5_plot_pad_bot(2) = 0.1
Grid5_txt_scale_factor(2) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid5_plot_name(3) = 'HR'
Grid5_plot_row(3) = 4
Grid5_plot_rowspan(3) = 2
Grid5_plot_col(3) = 1
Grid5_plot_colspan(3) = 2
Grid5_plot_pad_left(3) = 0.0
Grid5_plot_pad_right(3) = 0.01
Grid5_plot_pad_top(3) = 0.03
Grid5_plot_pad_bot(3) = 0.07
Grid5_txt_scale_factor(3) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid5_plot_name(4) = 'TRho'
Grid5_plot_row(4) = 6
Grid5_plot_rowspan(4) = 2
Grid5_plot_col(4) = 1
Grid5_plot_colspan(4) = 2
Grid5_plot_pad_left(4) = 0.0
Grid5_plot_pad_right(4) = 0.01
Grid5_plot_pad_top(4) = 0.04
Grid5_plot_pad_bot(4) = 0.06
Grid5_txt_scale_factor(4) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid5_plot_name(5) = 'Kipp'
Grid5_plot_row(5) = 4
Grid5_plot_rowspan(5) = 4
Grid5_plot_col(5) = 3
Grid5_plot_colspan(5) = 7
Grid5_plot_pad_left(5) = 0.09
Grid5_plot_pad_right(5) = 0.0
Grid5_plot_pad_top(5) = 0.03
Grid5_plot_pad_bot(5) = 0.06
Grid5_txt_scale_factor(5) = 0.7
{% endhighlight %}


file output

{% highlight fortran %}
Grid5_file_flag = .false.
Grid5_file_dir = 'png'
Grid5_file_prefix = 'grid5_'
Grid5_file_interval = 5
Grid5_file_width = -1
Grid5_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Grid6">Grid6 <a href="#Grid6" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Grid6_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Grid6_win_width = 9
Grid6_win_aspect_ratio = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid6_xleft = 0.12
Grid6_xright = 0.95
Grid6_ybot = 0.08
Grid6_ytop = 0.89
Grid6_title = ''
{% endhighlight %}


{% highlight fortran %}
Grid6_num_cols = 1
Grid6_num_rows = 1
Grid6_num_plots = 1
{% endhighlight %}


{% highlight fortran %}
Grid6_plot_name(:) = ''
Grid6_plot_row(:) = 1
Grid6_plot_rowspan(:) = 1
Grid6_plot_col(:) = 1
Grid6_plot_colspan(:) = 1
Grid6_plot_pad_left(:) = 0.0
Grid6_plot_pad_right(:) = 0.03
Grid6_plot_pad_top(:) = 0.0
Grid6_plot_pad_bot(:) = 0.09
Grid6_txt_scale_factor(:) = 0.7
{% endhighlight %}


set default

{% highlight fortran %}
Grid6_num_cols = 3
Grid6_num_rows = 3
Grid6_num_plots = 5
{% endhighlight %}


{% highlight fortran %}
Grid6_plot_name(1) = 'Summary_Burn'
Grid6_plot_row(1) = 1
Grid6_plot_rowspan(1) = 1
Grid6_plot_col(1) = 2
Grid6_plot_colspan(1) = 2
Grid6_plot_pad_left(1) = 0.03
Grid6_plot_pad_right(1) = 0.06
Grid6_plot_pad_top(1) = 0.0
Grid6_plot_pad_bot(1) = 0.06
Grid6_txt_scale_factor(1) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid6_plot_name(2) = 'Abundance'
Grid6_plot_row(2) = 2
Grid6_plot_rowspan(2) = 1
Grid6_plot_col(2) = 2
Grid6_plot_colspan(2) = 2
Grid6_plot_pad_left(2) = 0.03
Grid6_plot_pad_right(2) = 0.06
Grid6_plot_pad_top(2) = 0.06
Grid6_plot_pad_bot(2) = 0.00
Grid6_txt_scale_factor(2) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid6_plot_name(3) = 'HR'
Grid6_plot_row(3) = 1
Grid6_plot_rowspan(3) = 1
Grid6_plot_col(3) = 1
Grid6_plot_colspan(3) = 1
Grid6_plot_pad_left(3) = 0.00
Grid6_plot_pad_right(3) = 0.09
Grid6_plot_pad_top(3) = 0.00
Grid6_plot_pad_bot(3) = 0.06
Grid6_txt_scale_factor(3) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid6_plot_name(4) = 'TRho'
Grid6_plot_row(4) = 2
Grid6_plot_rowspan(4) = 1
Grid6_plot_col(4) = 1
Grid6_plot_colspan(4) = 1
Grid6_plot_pad_left(4) = 0.00
Grid6_plot_pad_right(4) = 0.09
Grid6_plot_pad_top(4) = 0.06
Grid6_plot_pad_bot(4) = 0.00
Grid6_txt_scale_factor(4) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid6_plot_name(5) = 'Text_Summary1'
Grid6_plot_row(5) = 3
Grid6_plot_rowspan(5) = 1
Grid6_plot_col(5) = 1
Grid6_plot_colspan(5) = 3
Grid6_plot_pad_left(5) = -0.07
Grid6_plot_pad_right(5) = -0.02
Grid6_plot_pad_top(5) = 0.1
Grid6_plot_pad_bot(5) = 0.00
Grid6_txt_scale_factor(5) = 0.21
{% endhighlight %}


file output

{% highlight fortran %}
Grid6_file_flag = .false.
Grid6_file_dir = 'png'
Grid6_file_prefix = 'grid6_'
Grid6_file_interval = 5
Grid6_file_width = -1
Grid6_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Grid7">Grid7 <a href="#Grid7" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Grid7_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Grid7_win_width = 6
Grid7_win_aspect_ratio = 1.5
{% endhighlight %}


{% highlight fortran %}
Grid7_xleft = 0.12
Grid7_xright = 0.95
Grid7_ybot = 0.08
Grid7_ytop = 0.91
Grid7_title = ''
{% endhighlight %}


{% highlight fortran %}
Grid7_num_cols = 1
Grid7_num_rows = 1
Grid7_num_plots = 1
{% endhighlight %}


{% highlight fortran %}
Grid7_plot_name(:) = ''
Grid7_plot_row(:) = 1
Grid7_plot_rowspan(:) = 1
Grid7_plot_col(:) = 1
Grid7_plot_colspan(:) = 1
Grid7_plot_pad_left(:) = 0.0
Grid7_plot_pad_right(:) = 0.0
Grid7_plot_pad_top(:) = 0.0
Grid7_plot_pad_bot(:) = 0.0
Grid7_txt_scale_factor(:) = 0.9
{% endhighlight %}


set default

{% highlight fortran %}
Grid7_num_cols = 1
Grid7_num_rows = 3
Grid7_num_plots = 3
{% endhighlight %}


{% highlight fortran %}
Grid7_plot_name(1) = 'Abundance'
Grid7_plot_row(1) = 1
Grid7_plot_rowspan(1) = 1
Grid7_plot_col(1) = 1
Grid7_plot_colspan(1) = 1
Grid7_plot_pad_left(1) = 0.03
Grid7_plot_pad_right(1) = 0.08
Grid7_plot_pad_top(1) = 0.00
Grid7_plot_pad_bot(1) = 0.06
Grid7_txt_scale_factor(1) = 0.9
{% endhighlight %}


{% highlight fortran %}
Grid7_plot_name(2) = 'TRho'
Grid7_plot_row(2) = 2
Grid7_plot_rowspan(2) = 1
Grid7_plot_col(2) = 1
Grid7_plot_colspan(2) = 1
Grid7_plot_pad_left(2) = 0.03
Grid7_plot_pad_right(2) = 0.08
Grid7_plot_pad_top(2) = 0.06
Grid7_plot_pad_bot(2) = 0.00
Grid7_txt_scale_factor(2) = 0.9
{% endhighlight %}


{% highlight fortran %}
Grid7_plot_name(3) = 'Text_Summary1'
Grid7_plot_row(3) = 3
Grid7_plot_rowspan(3) = 1
Grid7_plot_col(3) = 1
Grid7_plot_colspan(3) = 1
Grid7_plot_pad_left(3) = -0.08
Grid7_plot_pad_right(3) = 0.0
Grid7_plot_pad_top(3) = 0.1
Grid7_plot_pad_bot(3) = 0.0
Grid7_txt_scale_factor(3) = 0.16
{% endhighlight %}


file output

{% highlight fortran %}
Grid7_file_flag = .false.
Grid7_file_dir = 'png'
Grid7_file_prefix = 'grid7_'
Grid7_file_interval = 5
Grid7_file_width = -1
Grid7_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Grid8">Grid8 <a href="#Grid8" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Grid8_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Grid8_win_width = 7
Grid8_win_aspect_ratio = 1.2
{% endhighlight %}


{% highlight fortran %}
Grid8_xleft = 0.12
Grid8_xright = 0.95
Grid8_ybot = 0.08
Grid8_ytop = 0.91
Grid8_title = ''
{% endhighlight %}


{% highlight fortran %}
Grid8_num_cols = 1
Grid8_num_rows = 1
Grid8_num_plots = 1
{% endhighlight %}


{% highlight fortran %}
Grid8_plot_name(:) = ''
Grid8_plot_row(:) = 1
Grid8_plot_rowspan(:) = 1
Grid8_plot_col(:) = 1
Grid8_plot_colspan(:) = 1
Grid8_plot_pad_left(:) = 0.0
Grid8_plot_pad_right(:) = 0.03
Grid8_plot_pad_top(:) = 0.0
Grid8_plot_pad_bot(:) = 0.09
Grid8_txt_scale_factor(:) = 0.7
{% endhighlight %}


set default

{% highlight fortran %}
Grid8_num_cols = 3
Grid8_num_rows = 14
Grid8_num_plots = 6
{% endhighlight %}


{% highlight fortran %}
Grid8_plot_name(1) = 'Summary_Burn'
Grid8_plot_row(1) = 1
Grid8_plot_rowspan(1) = 4
Grid8_plot_col(1) = 1
Grid8_plot_colspan(1) = 3
Grid8_plot_pad_left(1) = 0.0
Grid8_plot_pad_right(1) = 0.06
Grid8_plot_pad_top(1) = 0.0
Grid8_plot_pad_bot(1) = 0.09
Grid8_txt_scale_factor(1) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid8_plot_name(2) = 'Abundance'
Grid8_plot_row(2) = 5
Grid8_plot_rowspan(2) = 4
Grid8_plot_col(2) = 1
Grid8_plot_colspan(2) = 3
Grid8_plot_pad_left(2) = 0.0
Grid8_plot_pad_right(2) = 0.06
Grid8_plot_pad_top(2) = 0.0
Grid8_plot_pad_bot(2) = 0.05
Grid8_txt_scale_factor(2) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid8_plot_name(3) = 'HR'
Grid8_plot_row(3) = 9
Grid8_plot_rowspan(3) = 3
Grid8_plot_col(3) = 1
Grid8_plot_colspan(3) = 1
Grid8_plot_pad_left(3) = 0.00
Grid8_plot_pad_right(3) = 0.1133
Grid8_plot_pad_top(3) = 0.05
Grid8_plot_pad_bot(3) = 0.0
Grid8_txt_scale_factor(3) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid8_plot_name(4) = 'TRho'
Grid8_plot_row(4) = 9
Grid8_plot_rowspan(4) = 3
Grid8_plot_col(4) = 2
Grid8_plot_colspan(4) = 1
Grid8_plot_pad_left(4) = 0.0267
Grid8_plot_pad_right(4) = 0.0867
Grid8_plot_pad_top(4) = 0.05
Grid8_plot_pad_bot(4) = 0.0
Grid8_txt_scale_factor(4) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid8_plot_name(5) = 'TRho_Profile'
Grid8_plot_row(5) = 9
Grid8_plot_rowspan(5) = 3
Grid8_plot_col(5) = 3
Grid8_plot_colspan(5) = 1
Grid8_plot_pad_left(5) = 0.0533
Grid8_plot_pad_right(5) = 0.06
Grid8_plot_pad_top(5) = 0.05
Grid8_plot_pad_bot(5) = 0.0
Grid8_txt_scale_factor(5) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid8_plot_name(6) = 'Text_Summary1'
Grid8_plot_row(6) = 12
Grid8_plot_rowspan(6) = 3
Grid8_plot_col(6) = 1
Grid8_plot_colspan(6) = 3
Grid8_plot_pad_left(6) = -0.08
Grid8_plot_pad_right(6) = 0.0
Grid8_plot_pad_top(6) = 0.06
Grid8_plot_pad_bot(6) = 0.0
Grid8_txt_scale_factor(6) = 0.16
{% endhighlight %}


file output

{% highlight fortran %}
Grid8_file_flag = .false.
Grid8_file_dir = 'png'
Grid8_file_prefix = 'grid8_'
Grid8_file_interval = 5
Grid8_file_width = -1
Grid8_file_aspect_ratio = -1
{% endhighlight %}


<h3 id="Grid9">Grid9 <a href="#Grid9" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
Grid9_win_flag = .false.
{% endhighlight %}


{% highlight fortran %}
Grid9_win_width = 7
Grid9_win_aspect_ratio = 0.8
{% endhighlight %}


{% highlight fortran %}
Grid9_xleft = 0.15
Grid9_xright = 0.85
Grid9_ybot = 0.12
Grid9_ytop = 0.91
Grid9_title = ''
{% endhighlight %}


{% highlight fortran %}
Grid9_num_cols = 1
Grid9_num_rows = 1
Grid9_num_plots = 1
{% endhighlight %}


{% highlight fortran %}
Grid9_plot_name(:) = ''
Grid9_plot_row(:) = 1
Grid9_plot_rowspan(:) = 1
Grid9_plot_col(:) = 1
Grid9_plot_colspan(:) = 1
Grid9_plot_pad_left(:) = 0.0
Grid9_plot_pad_right(:) = 0.0
Grid9_plot_pad_top(:) = 0.0
Grid9_plot_pad_bot(:) = 0.0
Grid9_txt_scale_factor(:) = 0.7
{% endhighlight %}


set default

{% highlight fortran %}
Grid9_num_cols = 3
Grid9_num_rows = 11
Grid9_num_plots = 5
{% endhighlight %}


{% highlight fortran %}
Grid9_plot_name(1) = 'Abundance'
Grid9_plot_row(1) = 1
Grid9_plot_rowspan(1) = 5
Grid9_plot_col(1) = 1
Grid9_plot_colspan(1) = 3
Grid9_plot_pad_left(1) = 0.0
Grid9_plot_pad_right(1) = 0.06
Grid9_plot_pad_top(1) = 0.0
Grid9_plot_pad_bot(1) = 0.09
Grid9_txt_scale_factor(1) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid9_plot_name(2) = 'HR'
Grid9_plot_row(2) = 6
Grid9_plot_rowspan(2) = 3
Grid9_plot_col(2) = 1
Grid9_plot_colspan(2) = 1
Grid9_plot_pad_left(2) = 0.00
Grid9_plot_pad_right(2) = 0.1133
Grid9_plot_pad_top(2) = 0.05
Grid9_plot_pad_bot(2) = 0.01
Grid9_txt_scale_factor(2) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid9_plot_name(3) = 'TRho'
Grid9_plot_row(3) = 6
Grid9_plot_rowspan(3) = 3
Grid9_plot_col(3) = 2
Grid9_plot_colspan(3) = 1
Grid9_plot_pad_left(3) = 0.0267
Grid9_plot_pad_right(3) = 0.0867
Grid9_plot_pad_top(3) = 0.05
Grid9_plot_pad_bot(3) = 0.01
Grid9_txt_scale_factor(3) = 0.65
{% endhighlight %}


{% highlight fortran %}
Grid9_plot_name(4) = 'TRho_Profile'
Grid9_plot_row(4) = 6
Grid9_plot_rowspan(4) = 3
Grid9_plot_col(4) = 3
Grid9_plot_colspan(4) = 1
Grid9_plot_pad_left(4) = 0.0533
Grid9_plot_pad_right(4) = 0.06
Grid9_plot_pad_top(4) = 0.05
Grid9_plot_pad_bot(4) = 0.01
Grid9_txt_scale_factor(4) = 0.7
{% endhighlight %}


{% highlight fortran %}
Grid9_plot_name(5) = 'Text_Summary1'
Grid9_plot_row(5) = 9
Grid9_plot_rowspan(5) = 3
Grid9_plot_col(5) = 1
Grid9_plot_colspan(5) = 3
Grid9_plot_pad_left(5) = -0.08
Grid9_plot_pad_right(5) = 0.0
Grid9_plot_pad_top(5) = 0.08
Grid9_plot_pad_bot(5) = 0.0
Grid9_txt_scale_factor(5) = 0.14
{% endhighlight %}


file output

{% highlight fortran %}
Grid9_file_flag = .false.
Grid9_file_dir = 'png'
Grid9_file_prefix = 'grid9_'
Grid9_file_interval = 5
Grid9_file_width = -1
Grid9_file_aspect_ratio = -1
{% endhighlight %}


"annotation" strings -- provide args for PGMTXT

         Write text at a position specified relative to the viewport (outside
         or inside).  The text is written using the current values of
         attributes color-index, line-width, character-height, and
         character-font.

          SIDE            : must include one of the characters 'B', 'L', 'T',
                            or 'R' signifying the Bottom, Left, Top, or Right
                            margin of the viewport. If it includes 'LV' or
                            'RV', the string is written perpendicular to the
                            frame rather than parallel to it.
          DISP            : the displacement of the character string from the
                            specified edge of the viewport, measured outwards
                            from the viewport in units of the character
                            height. Use a negative value to write inside the
                            viewport, a positive value to write outside.
          COORD           : the location of the character string along the
                            specified edge of the viewport, as a fraction of
                            the length of the edge.
          FJUST           : controls justification of the string parallel to
                            the specified edge of the viewport. If
                            FJUST = 0.0, the left-hand end of the string will
                            be placed at COORD; if JUST = 0.5, the center of
                            the string will be placed at COORD; if JUST = 1.0,
                            the right-hand end of the string will be placed at
                            at COORD. Other values between 0 and 1 give inter-
                            mediate placing, but they are not very useful.
          TEXT           :  the text string to be plotted. Trailing spaces are
                            ignored when justifying the string, but leading
                            spaces are significant.

{% highlight fortran %}
annotation1_ci = 1
annotation1_ch = 1
annotation1_lw = 1
annotation1_cf = 1
annotation1_side = 'T'
annotation1_disp = 0
annotation1_coord = 0
annotation1_fjust = 0.0
annotation1_text = ''
{% endhighlight %}


{% highlight fortran %}
annotation2_ci = 1
annotation2_ch = 1
annotation2_lw = 1
annotation2_cf = 1
annotation2_side = 'T'
annotation2_disp = 0
annotation2_coord = 0
annotation2_fjust = 0.0
annotation2_text = ''
{% endhighlight %}


{% highlight fortran %}
annotation3_ci = 1
annotation3_ch = 1
annotation3_lw = 1
annotation3_cf = 1
annotation3_side = 'T'
annotation3_disp = 0
annotation3_coord = 0
annotation3_fjust = 0.0
annotation3_text = ''
{% endhighlight %}

<h1 id="pgstar_extras">pgstar_extras <a href="#pgstar_extras" title="Permalink to this location">¶</a></h1>


the PGSTAR extra's work the same as for the star controls

{% highlight fortran %}
read_extra_pgstar_inlist1 = .false.
extra_pgstar_inlist1_name = 'undefined'
{% endhighlight %}


if `read_extra_pgstar_inlist1` is true, then read &pgstar from this namelist file

{% highlight fortran %}
read_extra_pgstar_inlist2 = .false.
extra_pgstar_inlist2_name = 'undefined'
{% endhighlight %}


if `read_extra_pgstar_inlist2` is true, then read &pgstar from this namelist file

{% highlight fortran %}
read_extra_pgstar_inlist3 = .false.
extra_pgstar_inlist3_name = 'undefined'
{% endhighlight %}


if `read_extra_pgstar_inlist3` is true, then read &pgstar from this namelist file

{% highlight fortran %}
read_extra_pgstar_inlist4 = .false.
extra_pgstar_inlist4_name = 'undefined'
{% endhighlight %}


if `read_extra_pgstar_inlist4` is true, then read &pgstar from this namelist file

{% highlight fortran %}
read_extra_pgstar_inlist5 = .false.
extra_pgstar_inlist5_name = 'undefined'
{% endhighlight %}


if `read_extra_pgstar_inlist5` is true, then read &pgstar from this namelist file