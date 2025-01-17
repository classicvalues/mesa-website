<h1 id="directories">directories <a href="#directories" title="Permalink to this location">¶</a></h1>


<h3 id="mesa_dir">mesa_dir <a href="#mesa_dir" title="Permalink to this location">¶</a></h3>


if set to the empty string, '', then it defaults to using
environment variable `$(MESA_DIR)`

{% highlight fortran %}
mesa_dir = ''
{% endhighlight %}


<h3 id="chem_isotopes_filename">chem_isotopes_filename <a href="#chem_isotopes_filename" title="Permalink to this location">¶</a></h3>


this file is in `chem_data` in `mesa_data_dir`

{% highlight fortran %}
chem_isotopes_filename = 'isotopes.data '
{% endhighlight %}


<h3 id="pause_before_terminate">pause_before_terminate <a href="#pause_before_terminate" title="Permalink to this location">¶</a></h3>


if true, then will pause before terminate run.
this can be useful if you'd like a chance to look at
the final model pgstar windows before they go away.

{% highlight fortran %}
pause_before_terminate = .false.
{% endhighlight %}


<h2 id="cache_directories">cache directories <a href="#cache_directories" title="Permalink to this location">¶</a></h2>


<h3 id="eosDT_cache_dir">eosDT_cache_dir <a href="#eosDT_cache_dir" title="Permalink to this location">¶</a></h3>


<h3 id="eosPT_cache_dir">eosPT_cache_dir <a href="#eosPT_cache_dir" title="Permalink to this location">¶</a></h3>


<h3 id="eosDE_cache_dir">eosDE_cache_dir <a href="#eosDE_cache_dir" title="Permalink to this location">¶</a></h3>


<h3 id="ionization_cache_dir">ionization_cache_dir <a href="#ionization_cache_dir" title="Permalink to this location">¶</a></h3>


<h3 id="kap_cache_dir">kap_cache_dir <a href="#kap_cache_dir" title="Permalink to this location">¶</a></h3>


<h3 id="rates_cache_dir">rates_cache_dir <a href="#rates_cache_dir" title="Permalink to this location">¶</a></h3>


mesa uses caches to improve performance.
the default location for these is in the mesa/data directory,
but in some situations it is useful to keep the caches
separately so, for example, multiple users can share the code
and each can have a separate set of caches.
'' means use default location for cache.

The need for separate caches arises in cases where we need
to put the main mesa directory in a location that is "read only"
for a group of users (such as in a system directory that requires
"root" or "superuser" to write).  In that case the caches must
be moved out of the main directory to locations that the user
can write.

if you specify cache directories, use a separate one for each.
e.g., something like this

    eosDT_cache_dir = '/Users/bpaxton/mesa_caches/eosDT_cache'
    eosPT_cache_dir = '/Users/bpaxton/mesa_caches/eosPT_cache'
    eosDE_cache_dir = '/Users/bpaxton/mesa_caches/eosDE_cache'
    ionization_cache_dir = '/Users/bpaxton/mesa_caches/ionization_cache'
    kap_cache_dir = '/Users/bpaxton/mesa_caches/kap_cache'
    rates_cache_dir = '/Users/bpaxton/mesa_caches/rates_cache'

If you give an empty string for the `cache_dir`, then
if you have set the environment variable `MESA_CACHES_DIR`, then
the cache is a subdirectory of that with one of the following names:
`eosDT_cache`, `eosPT_cache`, `kap_cache`, `ionization_cache`, `rates_cache`
if `MESA_CACHES_DIR` is not set or is the empty string, then
the cache is a subdirectory of the corresponding data subdirectory,
such as `data/rates_data/cache` for the rates cache.

{% highlight fortran %}
eosDT_cache_dir = ''
eosPT_cache_dir = ''
eosDE_cache_dir = ''
ionization_cache_dir = ''
kap_cache_dir = ''
rates_cache_dir = ''
{% endhighlight %}

<h1 id="output">output <a href="#output" title="Permalink to this location">¶</a></h1>


<h3 id="echo_at_start">echo_at_start <a href="#echo_at_start" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
echo_at_start = ''
{% endhighlight %}


<h3 id="echo_at_end">echo_at_end <a href="#echo_at_end" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
echo_at_end = ''
{% endhighlight %}


<h3 id="save_star_job_namelist">save_star_job_namelist <a href="#save_star_job_namelist" title="Permalink to this location">¶</a></h3>


dumps all values for &star_job controls to file

{% highlight fortran %}
save_star_job_namelist = .false.
{% endhighlight %}


<h3 id="star_job_namelist_name">star_job_namelist_name <a href="#star_job_namelist_name" title="Permalink to this location">¶</a></h3>


if empty, uses a default name

{% highlight fortran %}
star_job_namelist_name = ''
{% endhighlight %}


<h3 id="show_log_description_at_start">show_log_description_at_start <a href="#show_log_description_at_start" title="Permalink to this location">¶</a></h3>


set this false if you want to skip the initial terminal output

{% highlight fortran %}
show_log_description_at_start = .true.
{% endhighlight %}


<h3 id="show_net_species_info">show_net_species_info <a href="#show_net_species_info" title="Permalink to this location">¶</a></h3>


if true, then output a list of the species in the current net

{% highlight fortran %}
show_net_species_info = .false.
{% endhighlight %}


<h3 id="show_net_reactions_info">show_net_reactions_info <a href="#show_net_reactions_info" title="Permalink to this location">¶</a></h3>


if true, then output information about the reactions in the current net

{% highlight fortran %}
show_net_reactions_info = .false.
{% endhighlight %}


<h3 id="list_net_reactions">list_net_reactions <a href="#list_net_reactions" title="Permalink to this location">¶</a></h3>


if true, then output a simple list of the reactions in the current net

{% highlight fortran %}
list_net_reactions = .false.
{% endhighlight %}


<h3 id="show_kap_info">show_kap_info <a href="#show_kap_info" title="Permalink to this location">¶</a></h3>


if true, then output additional information as the opacities are loaded
this is particularly useful to see the detailed composition coverage of
the AESOPUS opacity files

{% highlight fortran %}
show_kap_info = .false.
{% endhighlight %}


<h3 id="show_eqns_and_vars_names">show_eqns_and_vars_names <a href="#show_eqns_and_vars_names" title="Permalink to this location">¶</a></h3>


if true, then output a list of the names of the equations and variables

{% highlight fortran %}
show_eqns_and_vars_names = .false.
{% endhighlight %}


<h3 id="pgstar_flag">pgstar_flag <a href="#pgstar_flag" title="Permalink to this location">¶</a></h3>


if true, activates pgplot output

{% highlight fortran %}
pgstar_flag = .false.
{% endhighlight %}


<h3 id="disable_pgstar_for_relax">disable_pgstar_for_relax <a href="#disable_pgstar_for_relax" title="Permalink to this location">¶</a></h3>


if true, turn off pgstar during relax operations

{% highlight fortran %}
disable_pgstar_for_relax = .false.
{% endhighlight %}


<h3 id="save_pgstar_files_when_terminate">save_pgstar_files_when_terminate <a href="#save_pgstar_files_when_terminate" title="Permalink to this location">¶</a></h3>


if true, then when the run terminates,
pgstar outputs files for plots that have `file_flag = .true.`
independently of the corresponding `file_interval`.

{% highlight fortran %}
save_pgstar_files_when_terminate = .false.
{% endhighlight %}


<h3 id="history_columns_file">history_columns_file <a href="#history_columns_file" title="Permalink to this location">¶</a></h3>


if null string, use default.

{% highlight fortran %}
history_columns_file = ''
{% endhighlight %}


<h3 id="profile_columns_file">profile_columns_file <a href="#profile_columns_file" title="Permalink to this location">¶</a></h3>


if null string, use default.

{% highlight fortran %}
profile_columns_file = ''
{% endhighlight %}


<h3 id="save_model_number">save_model_number <a href="#save_model_number" title="Permalink to this location">¶</a></h3>


at any point during the run, you can save a model for later use

{% highlight fortran %}
save_model_number = -111
{% endhighlight %}


<h3 id="save_model_when_terminate">save_model_when_terminate <a href="#save_model_when_terminate" title="Permalink to this location">¶</a></h3>


<h3 id="required_termination_code_string">required_termination_code_string <a href="#required_termination_code_string" title="Permalink to this location">¶</a></h3>


save final model when a run terminates
only happens if satisfy required termination code
if string is empty, then this matches all termination codes

{% highlight fortran %}
save_model_when_terminate = .false.
required_termination_code_string = ''
{% endhighlight %}


<h3 id="save_model_filename">save_model_filename <a href="#save_model_filename" title="Permalink to this location">¶</a></h3>


saved model root filename

{% highlight fortran %}
save_model_filename = 'undefined'
{% endhighlight %}


<h3 id="save_photo_when_terminate">save_photo_when_terminate <a href="#save_photo_when_terminate" title="Permalink to this location">¶</a></h3>


if true, then save photo for last model before terminate the run

{% highlight fortran %}
save_photo_when_terminate = .true.
{% endhighlight %}


<h3 id="profile_starting_model">profile_starting_model <a href="#profile_starting_model" title="Permalink to this location">¶</a></h3>


<h3 id="profile_model_number">profile_model_number <a href="#profile_model_number" title="Permalink to this location">¶</a></h3>


write profile for a specific model number

{% highlight fortran %}
profile_starting_model = .false.
profile_model_number = -1111
{% endhighlight %}


<h3 id="write_profile_when_terminate">write_profile_when_terminate <a href="#write_profile_when_terminate" title="Permalink to this location">¶</a></h3>


<h3 id="filename_for_profile_when_terminate">filename_for_profile_when_terminate <a href="#filename_for_profile_when_terminate" title="Permalink to this location">¶</a></h3>


write profile to a given name upon termination

{% highlight fortran %}
write_profile_when_terminate = .false.
filename_for_profile_when_terminate = ''
{% endhighlight %}


<h3 id="save_pulse_data_for_model_number">save_pulse_data_for_model_number <a href="#save_pulse_data_for_model_number" title="Permalink to this location">¶</a></h3>


<h3 id="save_pulse_data_when_terminate">save_pulse_data_when_terminate <a href="#save_pulse_data_when_terminate" title="Permalink to this location">¶</a></h3>


<h3 id="save_pulse_data_filename">save_pulse_data_filename <a href="#save_pulse_data_filename" title="Permalink to this location">¶</a></h3>


write pulsation data for the model (format given by `s% pulse_data_format`)

{% highlight fortran %}
save_pulse_data_for_model_number = -111
save_pulse_data_when_terminate = .false.
save_pulse_data_filename = 'undefined'
{% endhighlight %}


<h3 id="save_stella_data_for_model_number">save_stella_data_for_model_number <a href="#save_stella_data_for_model_number" title="Permalink to this location">¶</a></h3>


<h3 id="save_stella_data_when_terminate">save_stella_data_when_terminate <a href="#save_stella_data_when_terminate" title="Permalink to this location">¶</a></h3>


<h3 id="save_stella_data_filename">save_stella_data_filename <a href="#save_stella_data_filename" title="Permalink to this location">¶</a></h3>


<h3 id="stella_min_surf_logRho">stella_min_surf_logRho <a href="#stella_min_surf_logRho" title="Permalink to this location">¶</a></h3>


<h3 id="stella_min_velocity">stella_min_velocity <a href="#stella_min_velocity" title="Permalink to this location">¶</a></h3>


<h3 id="stella_skip_inner_dm">stella_skip_inner_dm <a href="#stella_skip_inner_dm" title="Permalink to this location">¶</a></h3>


<h3 id="stella_skip_inner_v_limit">stella_skip_inner_v_limit <a href="#stella_skip_inner_v_limit" title="Permalink to this location">¶</a></h3>


<h3 id="stella_num_points">stella_num_points <a href="#stella_num_points" title="Permalink to this location">¶</a></h3>


<h3 id="stella_nz_extra">stella_nz_extra <a href="#stella_nz_extra" title="Permalink to this location">¶</a></h3>


<h3 id="stella_mdot_years_for_wind">stella_mdot_years_for_wind <a href="#stella_mdot_years_for_wind" title="Permalink to this location">¶</a></h3>


<h3 id="stella_mdot_for_wind">stella_mdot_for_wind <a href="#stella_mdot_for_wind" title="Permalink to this location">¶</a></h3>


<h3 id="stella_v_wind">stella_v_wind <a href="#stella_v_wind" title="Permalink to this location">¶</a></h3>


<h3 id="stella_show_headers">stella_show_headers <a href="#stella_show_headers" title="Permalink to this location">¶</a></h3>


write stella info for the model

the mesa/star routine for creating stella files knows about the following species:
   h1, he3, he4, c12, n14, o16, ne20, na23, mg24, al27, si28,
   s32, ar36, ca40, ti44, cr48, cr60, fe52, fe54, fe56, co56, ni56
if your net includes other species, they will be ignored when creating the stella file.
on the other hand, any species missing from this list will simply be given 0 abundance.
see mesa/stella/README for details.

{% highlight fortran %}
save_stella_data_for_model_number = -111
save_stella_data_when_terminate = .false.
save_stella_data_filename = 'undefined'
stella_num_points = 300
stella_nz_extra = 30
stella_min_surf_logRho = -1d2
stella_min_velocity = 0d0
stella_skip_inner_dm = 0.1
stella_skip_inner_v_limit = 1d5
stella_mdot_years_for_wind = 1.2
stella_mdot_for_wind = 0.30
stella_v_wind = 12
stella_show_headers = .false.
{% endhighlight %}


<h3 id="internals_num">internals_num <a href="#internals_num" title="Permalink to this location">¶</a></h3>


write internals -- for debugging
only write if >= 0

{% highlight fortran %}
internals_num = -1
{% endhighlight %}


<h3 id="report_retries">report_retries <a href="#report_retries" title="Permalink to this location">¶</a></h3>


<h3 id="report_backups">report_backups <a href="#report_backups" title="Permalink to this location">¶</a></h3>


in case you want some extra info about retries or backups

{% highlight fortran %}
report_retries = .false.
report_backups = .false.
{% endhighlight %}

<h1 id="starting_model">starting model <a href="#starting_model" title="Permalink to this location">¶</a></h1>


By default at the start of a run a zams starting model is loaded,
and then the `initial_mass`, `initial_z`, and `initial_y` are adjusted as necessary.
However, there are alternatives.  you can use a model you saved previously,
or you can request the system to create a pre-main-sequence model.

BTW: the system finds the zams file by using the control called `zams_filename`
the default zams file is for Z=0.02 and lives in `data/star_data/zams_models`.
You can create your own zams file and use it instead -- see `test_suite/create_zams`.

<h3 id="load_saved_model">load_saved_model <a href="#load_saved_model" title="Permalink to this location">¶</a></h3>


<h3 id="saved_model_name">saved_model_name <a href="#saved_model_name" title="Permalink to this location">¶</a></h3>


If `load_saved_model` is true, then use the specified initial model.

{% highlight fortran %}
load_saved_model = .false.
saved_model_name = 'undefined'
{% endhighlight %}


<h3 id="create_pre_main_sequence_model">create_pre_main_sequence_model <a href="#create_pre_main_sequence_model" title="Permalink to this location">¶</a></h3>


If true, the code will create a starting model with uniform composition,
a core temperature below 10^6 so no nuclear burning,
and uniform contraction for enough luminosity to make it fully convective.

The mass is `initial_mass` from the controls namelist.

if `initial_y` is < 0 in the controls,
then code uses `0.24 + 2*initial_z` for `initial_y`.

The h1 mass fraction is set to `1 - (initial_y + initial_z)`.
The he3 and he4 mass fractions are set according to `initial_y`
with relative amounts set according to the AG89 solar mass fractions (from `chem_def`).

The metallicity is `initial_z` from the controls namelist
with the metals fractions set according to the GS98 values (from `chem_def`).

to set the metals fractions, use `initial_zfracs` (described below)

{% highlight fortran %}
create_pre_main_sequence_model = .false.
{% endhighlight %}


<h3 id="create_merger_model__EXPERIMENTAL">create_merger_model !!! EXPERIMENTAL <a href="#create_merger_model__EXPERIMENTAL" title="Permalink to this location">¶</a></h3>


<h3 id="saved_model_for_merger_1">saved_model_for_merger_1 <a href="#saved_model_for_merger_1" title="Permalink to this location">¶</a></h3>


<h3 id="saved_model_for_merger_2">saved_model_for_merger_2 <a href="#saved_model_for_merger_2" title="Permalink to this location">¶</a></h3>


If `create_merger_model` is true, then create a star by merging the two models provided.

{% highlight fortran %}
create_merger_model = .false.
saved_model_for_merger_1 = 'undefined'
saved_model_for_merger_2 = 'undefined'
{% endhighlight %}


<h3 id="pre_ms_T_c">pre_ms_T_c <a href="#pre_ms_T_c" title="Permalink to this location">¶</a></h3>


Initial center temperature (must be below 1d6).
If you have initial convergence problems creating a pre-ms model,
you might try different values for `pre_ms_T_c` -- that sometimes helps.

{% highlight fortran %}
pre_ms_T_c = 3e5
{% endhighlight %}


<h3 id="pre_ms_guess_rho_c">pre_ms_guess_rho_c <a href="#pre_ms_guess_rho_c" title="Permalink to this location">¶</a></h3>


Guess for initial center density; set to 0 to let the code pick.

{% highlight fortran %}
pre_ms_guess_rho_c = 0
{% endhighlight %}


<h3 id="pre_ms_d_log10_P">pre_ms_d_log10_P <a href="#pre_ms_d_log10_P" title="Permalink to this location">¶</a></h3>


Suggested spacing in pressure between points; set to 0 to let the code pick.

{% highlight fortran %}
pre_ms_d_log10_P = 0
{% endhighlight %}


<h3 id="pre_ms_logT_surf_limit">pre_ms_logT_surf_limit <a href="#pre_ms_logT_surf_limit" title="Permalink to this location">¶</a></h3>


<h3 id="pre_ms_logP_surf_limit">pre_ms_logP_surf_limit <a href="#pre_ms_logP_surf_limit" title="Permalink to this location">¶</a></h3>


Model contruction is from inside out
and stops when reaches either of the following limits.

{% highlight fortran %}
pre_ms_logT_surf_limit = 3.7d0
pre_ms_logP_surf_limit = 3.5d0
{% endhighlight %}


<h3 id="pre_ms_relax_num_steps">pre_ms_relax_num_steps <a href="#pre_ms_relax_num_steps" title="Permalink to this location">¶</a></h3>


Let pre-ms model settle in for this many steps before changing anything else.

{% highlight fortran %}
pre_ms_relax_num_steps = 100
{% endhighlight %}


<h3 id="create_initial_model">create_initial_model <a href="#create_initial_model" title="Permalink to this location">¶</a></h3>


This is an alternative to `create_pre_main_sequence_model`.
If true, creates an adiabatic, contracting model for given mass and radius.
Assumes no nuclear burning and constant entropy. Ignores radiation pressure.
Uses star controls `initial_y` and `initial_z` to set X, Y, and Z.
Uses `initial_zfracs` to set abundances of metals.

Note: if you'd like to do-it-yourself, then you can use `other_build_initial_model`.
In that case, in addition to setting `create_initial_model`, also set
star controls `use_other_build_initial_model`.
Then your `run_star_extras` routine will be called instead of the standard one.

{% highlight fortran %}
create_initial_model = .false.
{% endhighlight %}


<h3 id="create_RSP_model">create_RSP_model <a href="#create_RSP_model" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
create_RSP_model = .false.
{% endhighlight %}


<h3 id="radius_in_cm_for_create_initial_model">radius_in_cm_for_create_initial_model <a href="#radius_in_cm_for_create_initial_model" title="Permalink to this location">¶</a></h3>


<h3 id="mass_in_gm_for_create_initial_model">mass_in_gm_for_create_initial_model <a href="#mass_in_gm_for_create_initial_model" title="Permalink to this location">¶</a></h3>


Radius in cm and mass in grams.

{% highlight fortran %}
radius_in_cm_for_create_initial_model = 0
mass_in_gm_for_create_initial_model = 0
{% endhighlight %}


<h3 id="center_logP_1st_try_for_create_initial_model">center_logP_1st_try_for_create_initial_model <a href="#center_logP_1st_try_for_create_initial_model" title="Permalink to this location">¶</a></h3>


<h3 id="entropy_1st_try_for_create_initial_model">entropy_1st_try_for_create_initial_model <a href="#entropy_1st_try_for_create_initial_model" title="Permalink to this location">¶</a></h3>


<h3 id="max_tries_for_create_initial_model">max_tries_for_create_initial_model <a href="#max_tries_for_create_initial_model" title="Permalink to this location">¶</a></h3>


<h3 id="abs_e01_tolerance_for_create_initial_model">abs_e01_tolerance_for_create_initial_model <a href="#abs_e01_tolerance_for_create_initial_model" title="Permalink to this location">¶</a></h3>


<h3 id="abs_e02_tolerance_for_create_initial_model">abs_e02_tolerance_for_create_initial_model <a href="#abs_e02_tolerance_for_create_initial_model" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
center_logP_1st_try_for_create_initial_model = 10.9d0
entropy_1st_try_for_create_initial_model = 11.5d0
max_tries_for_create_initial_model = 100
abs_e01_tolerance_for_create_initial_model = 1d-4
abs_e02_tolerance_for_create_initial_model = 1d-4
{% endhighlight %}


<h3 id="initial_model_relax_num_steps">initial_model_relax_num_steps <a href="#initial_model_relax_num_steps" title="Permalink to this location">¶</a></h3>


Let initial model settle in for this many steps before changing anything else.

{% highlight fortran %}
initial_model_relax_num_steps = 10
{% endhighlight %}


<h3 id="initial_model_eps">initial_model_eps <a href="#initial_model_eps" title="Permalink to this location">¶</a></h3>


Integration accuracy.

{% highlight fortran %}
initial_model_eps = 0.05d0
{% endhighlight %}

<h1 id="when_to_stop">when to stop <a href="#when_to_stop" title="Permalink to this location">¶</a></h1>


<h3 id="steps_to_take_before_terminate">steps_to_take_before_terminate <a href="#steps_to_take_before_terminate" title="Permalink to this location">¶</a></h3>


If > 0, stop after taking this many steps.
Sets `max_model_number` = `model_number` + `steps_to_take_before_terminate`.
Ignore if <= 0.

{% highlight fortran %}
steps_to_take_before_terminate = -1
{% endhighlight %}


<h3 id="stop_if_this_file_exists">stop_if_this_file_exists <a href="#stop_if_this_file_exists" title="Permalink to this location">¶</a></h3>


At each step, the code will try to open this file.
If the file exists, it will terminate the run.
If the file doesn't exist, it will keep going.

{% highlight fortran %}
stop_if_this_file_exists = ''
{% endhighlight %}

<h1 id="modifications_to_model">modifications to model <a href="#modifications_to_model" title="Permalink to this location">¶</a></h1>


These controls enable one to alter the MESA model at the
start of a run (`./rn`) or after a restart (`./re`).  Controls
that only apply to the first model have 'initial' in their
names, and are ignored for restarts.

<h3 id="set_initial_age">set_initial_age <a href="#set_initial_age" title="Permalink to this location">¶</a></h3>


<h3 id="initial_age">initial_age <a href="#initial_age" title="Permalink to this location">¶</a></h3>


if true, set initial age in years

{% highlight fortran %}
set_initial_age = .false.
initial_age = 0
{% endhighlight %}


<h3 id="set_initial_model_number">set_initial_model_number <a href="#set_initial_model_number" title="Permalink to this location">¶</a></h3>


<h3 id="initial_model_number">initial_model_number <a href="#initial_model_number" title="Permalink to this location">¶</a></h3>


if true, set initial model number

{% highlight fortran %}
set_initial_model_number = .false.
initial_model_number = 0
{% endhighlight %}


<h3 id="set_initial_dt">set_initial_dt <a href="#set_initial_dt" title="Permalink to this location">¶</a></h3>


<h3 id="years_for_initial_dt">years_for_initial_dt <a href="#years_for_initial_dt" title="Permalink to this location">¶</a></h3>


<h3 id="seconds_for_initial_dt">seconds_for_initial_dt <a href="#seconds_for_initial_dt" title="Permalink to this location">¶</a></h3>


if true, set initial timestep, dt, in years

{% highlight fortran %}
set_initial_dt = .false.
years_for_initial_dt = -1
seconds_for_initial_dt = -1
{% endhighlight %}


<h3 id="limit_initial_dt">limit_initial_dt <a href="#limit_initial_dt" title="Permalink to this location">¶</a></h3>


Like `set_initial_dt`, but does not increase current value for `dt_next`.
Used in conjunction with `years_for_initial_dt` and `seconds_for_initial_dt.`

    dt_next = min(dt_next, years_for_initial_dt*secyer)

{% highlight fortran %}
limit_initial_dt = .false.
{% endhighlight %}


<h3 id="set_uniform_initial_composition">set_uniform_initial_composition <a href="#set_uniform_initial_composition" title="Permalink to this location">¶</a></h3>


Set uniform composition.
This is useful with `create_pre_main_sequence_model`.

{% highlight fortran %}
set_uniform_initial_composition = .false.
{% endhighlight %}


<h3 id="initial_h1">initial_h1 <a href="#initial_h1" title="Permalink to this location">¶</a></h3>


<h3 id="initial_h2">initial_h2 <a href="#initial_h2" title="Permalink to this location">¶</a></h3>


<h3 id="initial_he3">initial_he3 <a href="#initial_he3" title="Permalink to this location">¶</a></h3>


<h3 id="initial_he4">initial_he4 <a href="#initial_he4" title="Permalink to this location">¶</a></h3>


if `set_uniform_initial_composition` is true, then
set hydrogen and helium mass fractions according to the following:
If no h2 in current net, then this will be added to h1.
If no he3 in current net, then this will be added to he4.

{% highlight fortran %}
initial_h1 = -1
initial_h2 = -1
initial_he3 = -1
initial_he4 = -1
{% endhighlight %}


<h3 id="initial_zfracs">initial_zfracs <a href="#initial_zfracs" title="Permalink to this location">¶</a></h3>


if `set_uniform_initial_composition` is true, then set metal fractions
z fractions -- select one of the options defined in `chem/public/chem_def` :

+ `AG89_zfracs = 1`
+ `GN93_zfracs = 2`
+ `GS98_zfracs = 3`
+ `L03_zfracs = 4`
+ `AGS05_zfracs = 5`
+ `AGSS09_zfracs = 6`
+ `L09_zfracs = 7`
+ `A09_Prz_zfracs = 8`

for example, `initial_zfracs = 3` for `GS98_zfracs`
or set `initial_zfracs = 0` to use the special list of z fractions specified in controls
(i.e., `z_fraction_li`, `z_fraction_be`, `z_fraction_b`, etc.)

{% highlight fortran %}
initial_zfracs = 3
{% endhighlight %}


<h3 id="dump_missing_metals_into_heaviest">dump_missing_metals_into_heaviest <a href="#dump_missing_metals_into_heaviest" title="Permalink to this location">¶</a></h3>


this controls the treatment metals that are not included in the current net.
if this flag is true, then the mass fractions of missing metals are added
to the mass fraction of the most massive metal included in the net.
if this flag is false, then the mass fractions of the metals in the net
are renormalized to make up for the total mass fraction of missing metals.

{% highlight fortran %}
dump_missing_metals_into_heaviest = .true.
{% endhighlight %}


<h3 id="file_for_uniform_xa">file_for_uniform_xa <a href="#file_for_uniform_xa" title="Permalink to this location">¶</a></h3>


<h3 id="set_uniform_initial_xa_from_file">set_uniform_initial_xa_from_file <a href="#set_uniform_initial_xa_from_file" title="Permalink to this location">¶</a></h3>


<h3 id="set_uniform_xa_from_file">set_uniform_xa_from_file <a href="#set_uniform_xa_from_file" title="Permalink to this location">¶</a></h3>


an alternative to the above `set_uniform_initial_composition` method.
if `set_uniform_initial_xa_from_file` is .true.,
read list of iso name and mass fraction pairs from file `file_for_uniform_xa`
and use them to set uniform composition.
E.g., to convert the star to pure fe56,
a file with just the following line will work.

    fe56   1.0

{% highlight fortran %}
file_for_uniform_xa = ''
set_uniform_initial_xa_from_file = .false.
set_uniform_xa_from_file = .false.
{% endhighlight %}


<h3 id="mix_section">mix_section <a href="#mix_section" title="Permalink to this location">¶</a></h3>


<h3 id="mix_initial_section">mix_initial_section <a href="#mix_initial_section" title="Permalink to this location">¶</a></h3>


<h3 id="mix_section_nzlo">mix_section_nzlo <a href="#mix_section_nzlo" title="Permalink to this location">¶</a></h3>


<h3 id="mix_section_nzhi">mix_section_nzhi <a href="#mix_section_nzhi" title="Permalink to this location">¶</a></h3>


fully mix section of model

{% highlight fortran %}
mix_section = .false.
mix_initial_section = .false.
mix_section_nzlo = -1
mix_section_nzhi = -1
{% endhighlight %}


<h3 id="mix_envelope_down_to_T">mix_envelope_down_to_T <a href="#mix_envelope_down_to_T" title="Permalink to this location">¶</a></h3>


<h3 id="mix_initial_envelope_down_to_T">mix_initial_envelope_down_to_T <a href="#mix_initial_envelope_down_to_T" title="Permalink to this location">¶</a></h3>


fully mix envelope from surface down to given temperature

{% highlight fortran %}
mix_envelope_down_to_T = 0
mix_initial_envelope_down_to_T = 0
{% endhighlight %}


<h3 id="set_abundance">set_abundance <a href="#set_abundance" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_abundance">set_initial_abundance <a href="#set_initial_abundance" title="Permalink to this location">¶</a></h3>


<h3 id="chem_name">chem_name <a href="#chem_name" title="Permalink to this location">¶</a></h3>


<h3 id="new_frac">new_frac <a href="#new_frac" title="Permalink to this location">¶</a></h3>


<h3 id="set_abundance_nzlo">set_abundance_nzlo <a href="#set_abundance_nzlo" title="Permalink to this location">¶</a></h3>


<h3 id="set_abundance_nzhi">set_abundance_nzhi <a href="#set_abundance_nzhi" title="Permalink to this location">¶</a></h3>


given a `chem_name` from `chem_def`,
set its abundance to be `new_frac`
in a given range of cells, from `set_abundance_nzlo` to `set_abundance_nzhi`

{% highlight fortran %}
set_abundance = .false.
set_initial_abundance = .false.
chem_name = 'he3'
new_frac = 0
set_abundance_nzlo = -1
set_abundance_nzhi = -1
{% endhighlight %}


<h3 id="replace_element">replace_element <a href="#replace_element" title="Permalink to this location">¶</a></h3>


<h3 id="replace_initial_element">replace_initial_element <a href="#replace_initial_element" title="Permalink to this location">¶</a></h3>


<h3 id="chem_name1">chem_name1 <a href="#chem_name1" title="Permalink to this location">¶</a></h3>


<h3 id="chem_name2">chem_name2 <a href="#chem_name2" title="Permalink to this location">¶</a></h3>


<h3 id="replace_element_nzlo">replace_element_nzlo <a href="#replace_element_nzlo" title="Permalink to this location">¶</a></h3>


<h3 id="replace_element_nzhi">replace_element_nzhi <a href="#replace_element_nzhi" title="Permalink to this location">¶</a></h3>


replace one iso by another in a given range of cells
`chem_name1` and `chem_name2` from `chem_def`

{% highlight fortran %}
replace_element = .false.
replace_initial_element = .false.
chem_name1 = 'he3'
chem_name2 = 'he4'
replace_element_nzlo = -1
replace_element_nzhi = -1
{% endhighlight %}


<h3 id="relax_initial_composition">relax_initial_composition <a href="#relax_initial_composition" title="Permalink to this location">¶</a></h3>


<h3 id="num_steps_to_relax_composition">num_steps_to_relax_composition <a href="#num_steps_to_relax_composition" title="Permalink to this location">¶</a></h3>


<h3 id="relax_composition_filename">relax_composition_filename <a href="#relax_composition_filename" title="Permalink to this location">¶</a></h3>


relax composition from current to specified over number of steps.
`relax_composition_filename` holds the desired composition profile information
file format for relax composition

    1st line: num_points num_species
    then 1 line for for each point where define desired composition
    xq xa(1) ... xa(num_species)
    xq = fraction of xmstar exterior to the point
    where xmstar = mstar - M_center
    the interpolation routines require that the xq values which
    appear in your file must be monotonically increasing
    xa(i) = mass fraction of i'th species

NOTE: it is up to you to ensure that the current net isotopes match
the species in the composition file.
You can set `show_net_species_info = .true.` to check the isotopes in the net.

If timescale_for_relax_composition is negative, then the model will be adjusted
such that in num_steps_to_relax_composition the desired composition is obtained.
Otherwise, the abundance of each element will be updated each step as
    new_xa = lambda*target_xa + (1-lambda)*current_xa
where lambda = dt/timescale_for_relax_composition. In this way, the target composition
is reached when dt>=timescale_for_relax_composition.

{% highlight fortran %}
relax_initial_composition = .false.
num_steps_to_relax_composition = 100
relax_composition_filename = ''
timescale_for_relax_composition = -1d0
{% endhighlight %}


<h3 id="relax_initial_to_xaccrete">relax_initial_to_xaccrete <a href="#relax_initial_to_xaccrete" title="Permalink to this location">¶</a></h3>


Like `relax_initial_composition` (and uses `num_steps_to_relax_composition`),
but new composition is set by current specification of accretion abundances.

{% highlight fortran %}
relax_initial_to_xaccrete = .false.
{% endhighlight %}


some modifications must be done gradually over several steps in "pseudo" evolution
these operations have "relax" in their names.
many have an alternative, with "set" in name, that simply make the change all at once.
the "set" version is fine if star can manage to converge the modified model.
but for larger changes where that's not possible, you'll need to "relax" instead.

<h3 id="relax_Y">relax_Y <a href="#relax_Y" title="Permalink to this location">¶</a></h3>


<h3 id="change_Y">change_Y <a href="#change_Y" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_Y">relax_initial_Y <a href="#relax_initial_Y" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_Y">change_initial_Y <a href="#change_initial_Y" title="Permalink to this location">¶</a></h3>


<h3 id="relax_Y_minq">relax_Y_minq <a href="#relax_Y_minq" title="Permalink to this location">¶</a></h3>


<h3 id="relax_Y_maxq">relax_Y_maxq <a href="#relax_Y_maxq" title="Permalink to this location">¶</a></h3>


<h3 id="new_Y">new_Y <a href="#new_Y" title="Permalink to this location">¶</a></h3>


`relax_Y = .true.` gradually changes average Y, reconverging at each step.
`change_Y = .true.` changes abundances; doesn't reconverge the model.
note: `relax_dY` in the controls inlist determines the rate of change

{% highlight fortran %}
relax_Y = .false.
change_Y = .false.
relax_initial_Y = .false.
change_initial_Y = .false.
relax_Y_minq = 0d0
relax_Y_maxq = 1d0
new_Y = -1
{% endhighlight %}


<h3 id="relax_Z">relax_Z <a href="#relax_Z" title="Permalink to this location">¶</a></h3>


<h3 id="change_Z">change_Z <a href="#change_Z" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_Z">relax_initial_Z <a href="#relax_initial_Z" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_Z">change_initial_Z <a href="#change_initial_Z" title="Permalink to this location">¶</a></h3>


<h3 id="relax_Z_minq">relax_Z_minq <a href="#relax_Z_minq" title="Permalink to this location">¶</a></h3>


<h3 id="relax_Z_maxq">relax_Z_maxq <a href="#relax_Z_maxq" title="Permalink to this location">¶</a></h3>


<h3 id="new_Z">new_Z <a href="#new_Z" title="Permalink to this location">¶</a></h3>


`relax_Z = .true.` gradually changes average Z, reconverging at each step.
`change_Z = .true.` simply changes abundances; doesn't reconverge the model.
note: `relax_dlnZ` in the controls inlist determines the rate of change

{% highlight fortran %}
relax_Z = .false.
change_Z = .false.
relax_initial_Z = .false.
change_initial_Z = .false.
relax_Z_minq = 0d0
relax_Z_maxq = 1d0
new_Z = -1
{% endhighlight %}


<h3 id="relax_mass">relax_mass <a href="#relax_mass" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_mass">relax_initial_mass <a href="#relax_initial_mass" title="Permalink to this location">¶</a></h3>


<h3 id="new_mass">new_mass <a href="#new_mass" title="Permalink to this location">¶</a></h3>


<h3 id="lg_max_abs_mdot">lg_max_abs_mdot <a href="#lg_max_abs_mdot" title="Permalink to this location">¶</a></h3>


Gradually change total mass by a wind to `new_mass`.
`lg_max_abs_mdot = -4` means max abs mdot 1d-4 msun/year;
Set <= -100 to let code pick.

{% highlight fortran %}
relax_mass = .false.
relax_initial_mass = .false.
new_mass = -1
lg_max_abs_mdot = -100
{% endhighlight %}


<h3 id="relax_mass_scale">relax_mass_scale <a href="#relax_mass_scale" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_mass_scale">relax_initial_mass_scale <a href="#relax_initial_mass_scale" title="Permalink to this location">¶</a></h3>


<h3 id="dlgm_per_step">dlgm_per_step <a href="#dlgm_per_step" title="Permalink to this location">¶</a></h3>


<h3 id="change_mass_years_for_dt">change_mass_years_for_dt <a href="#change_mass_years_for_dt" title="Permalink to this location">¶</a></h3>


Gradually rescale mass of star to `new_mass`.
Rescales star mass without changing composition as function of m/mstar.

{% highlight fortran %}
relax_mass_scale = .false.
relax_initial_mass_scale = .false.
dlgm_per_step = 1d-3
change_mass_years_for_dt = 1
{% endhighlight %}


<h3 id="relax_initial_angular_momentum">relax_initial_angular_momentum <a href="#relax_initial_angular_momentum" title="Permalink to this location">¶</a></h3>


<h3 id="max_steps_to_relax_angular_momentum">max_steps_to_relax_angular_momentum <a href="#max_steps_to_relax_angular_momentum" title="Permalink to this location">¶</a></h3>


<h3 id="timescale_for_relax_angular_momentum">timescale_for_relax_angular_momentum <a href="#timescale_for_relax_angular_momentum" title="Permalink to this location">¶</a></h3>


<h3 id="max_dt_for_relax_angular_momentum">max_dt_for_relax_angular_momentum <a href="#max_dt_for_relax_angular_momentum" title="Permalink to this location">¶</a></h3>


<h3 id="num_timescales_for_relax_angular_momentum">num_timescales_for_relax_angular_momentum <a href="#num_timescales_for_relax_angular_momentum" title="Permalink to this location">¶</a></h3>


<h3 id="relax_angular_momentum_filename">relax_angular_momentum_filename <a href="#relax_angular_momentum_filename" title="Permalink to this location">¶</a></h3>


relax angular momentum from current to specified over a certain amount of relaxation timescales.
This is done by adding an extra torque term of the form

    s% extra_jdot(k) =  &
        (1d0 - exp_cr(-s% dt/(s% job% timescale_for_relax_angular_momentum*secyer))) * &
        (desired_angular_momentum(k) - s% j_rot(k))/s% dt

and evolving the star without changing the composition for `num_timescales_for_relax_angular_momentum` times
`timescale_for_relax_angular_momentum`. To circumvent convection we limit the acceleration of convective velocities
using `min_T_for_acceleration_limited_conv_velocity = 0` (see controls.defaults), and the timescale
for relaxation should be very short (less than a second).

`relax_angular_momentum_filename` holds the desired angular momentum profile information
file format for relax angular momentum

    1st line: num_points
    then 1 line for for each point where define desired angular momentum
    xq angular_momentum
    xq = fraction of xmstar exterior to the point
    where xmstar = mstar - M_center
    angular_momentum = specific angular momentum in units of cm^2/s

{% highlight fortran %}
relax_initial_angular_momentum = .false.
max_steps_to_relax_angular_momentum = 1000
timescale_for_relax_angular_momentum = 1d-10
max_dt_for_relax_angular_momentum = 1d-9
num_timescales_for_relax_angular_momentum = 1000
relax_angular_momentum_filename = ''
{% endhighlight %}


<h3 id="relax_initial_entropy">relax_initial_entropy <a href="#relax_initial_entropy" title="Permalink to this location">¶</a></h3>


<h3 id="max_steps_to_relax_entropy">max_steps_to_relax_entropy <a href="#max_steps_to_relax_entropy" title="Permalink to this location">¶</a></h3>


<h3 id="timescale_for_relax_entropy">timescale_for_relax_entropy <a href="#timescale_for_relax_entropy" title="Permalink to this location">¶</a></h3>


<h3 id="max_dt_for_relax_entropy">max_dt_for_relax_entropy <a href="#max_dt_for_relax_entropy" title="Permalink to this location">¶</a></h3>


<h3 id="num_timescales_for_relax_entropy">num_timescales_for_relax_entropy <a href="#num_timescales_for_relax_entropy" title="Permalink to this location">¶</a></h3>


<h3 id="relax_entropy_filename">relax_entropy_filename <a href="#relax_entropy_filename" title="Permalink to this location">¶</a></h3>


<h3 id="get_entropy_for_relax_from_eos">get_entropy_for_relax_from_eos <a href="#get_entropy_for_relax_from_eos" title="Permalink to this location">¶</a></h3>


relax entropy from current to specified over a certain amount of relaxation timescales.
This is done by adding an extra heating term of the form

    s% extra_heat(k) =  &
        (1d0 - exp_cr(s%lnS(k))/desired_entropy(k))*exp_cr(s%lnE(k))/(timescale_for_relax_entropy*secyer)

and evolving the star without changing the composition for `num_timescales_for_relax_entropy` times
`timescale_for_relax_entropy`. To circumvent convection we limit the acceleration of convective velocities
using `min_T_for_acceleration_limited_conv_velocity = 0` (see controls.defaults), and the timescale
for relaxation should be very short (less than a second).

`relax_entropy_filename` holds the desired entropy profile information
file format for relax entropy

    1st line: num_points
    then 1 line for for each point where define desired entropy
    xq entropy
    xq = fraction of xmstar exterior to the point
    where xmstar = mstar - M_center
    entropy = specific entropy in units of erg/gr/K

the interpolation routines require that the xq values which
appear in your file must be monotonically increasing.

In case the entropy is not readily available, pairs of values of
two other thermodynamic variables can be provided. The entropy is
then computed using the eos module, and the composition of
the stellar model (which can be set using `relax_initial_composition`).
This is set by the option `get_entropy_for_relax_from_eos which`
can take the values

+ '': if empty, then input file directly specifies the entropy
+ 'eosDT': input file includes density and temperature
+ 'eosPT': input file includes gas pressure and temperature
+ 'eosDE': input file includes density and specific internal energy

when any of the eos* options is used, then each line in the input
file must contain three columns instead of two, specifying the
values of the two thermodinamic variables used in the order
specified above. So, for example, when using 'eosDT' the format of
the input file is

    1st line: num_points
    then 1 line for for each point where define desired entropy
    xq density temperature
    xq = fraction of xmstar exterior to the point
    where xmstar = mstar - M_center
    density and temperature in cgs units

{% highlight fortran %}
relax_initial_entropy = .false.
max_steps_to_relax_entropy = 1000
timescale_for_relax_entropy = 1d-9
max_dt_for_relax_entropy = 1d-9
num_timescales_for_relax_entropy = 100
relax_entropy_filename = ''
get_entropy_for_relax_from_eos = ''
{% endhighlight %}


<h3 id="relax_dxdt_nuc_factor">relax_dxdt_nuc_factor <a href="#relax_dxdt_nuc_factor" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_dxdt_nuc_factor">relax_initial_dxdt_nuc_factor <a href="#relax_initial_dxdt_nuc_factor" title="Permalink to this location">¶</a></h3>


<h3 id="new_dxdt_nuc_factor">new_dxdt_nuc_factor <a href="#new_dxdt_nuc_factor" title="Permalink to this location">¶</a></h3>


<h3 id="dxdt_nuc_factor_multiplier">dxdt_nuc_factor_multiplier <a href="#dxdt_nuc_factor_multiplier" title="Permalink to this location">¶</a></h3>


Gradually rescale `dxdt_nuc_factor`.
At each step, multiply `dxdt_nuc_factor` by `dxdt_nuc_factor_multiplier`,
until reach `new_dxdt_nuc_factor`.

{% highlight fortran %}
relax_dxdt_nuc_factor = .false.
relax_initial_dxdt_nuc_factor = .false.
new_dxdt_nuc_factor = 0
dxdt_nuc_factor_multiplier = 0
{% endhighlight %}


<h3 id="relax_eps_nuc_factor">relax_eps_nuc_factor <a href="#relax_eps_nuc_factor" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_eps_nuc_factor">relax_initial_eps_nuc_factor <a href="#relax_initial_eps_nuc_factor" title="Permalink to this location">¶</a></h3>


<h3 id="new_eps_nuc_factor">new_eps_nuc_factor <a href="#new_eps_nuc_factor" title="Permalink to this location">¶</a></h3>


<h3 id="eps_nuc_factor_multiplier">eps_nuc_factor_multiplier <a href="#eps_nuc_factor_multiplier" title="Permalink to this location">¶</a></h3>


Gradually rescale `eps_nuc_factor`.
At each step, multiply `eps_nuc_factor` by `eps_nuc_factor_multiplier`
until reach `new_eps_nuc_factor`.

{% highlight fortran %}
relax_eps_nuc_factor = .false.
relax_initial_eps_nuc_factor = .false.
new_eps_nuc_factor = 0
eps_nuc_factor_multiplier = 0
{% endhighlight %}


<h3 id="relax_opacity_max">relax_opacity_max <a href="#relax_opacity_max" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_opacity_max">relax_initial_opacity_max <a href="#relax_initial_opacity_max" title="Permalink to this location">¶</a></h3>


<h3 id="new_opacity_max">new_opacity_max <a href="#new_opacity_max" title="Permalink to this location">¶</a></h3>


<h3 id="opacity_max_multiplier">opacity_max_multiplier <a href="#opacity_max_multiplier" title="Permalink to this location">¶</a></h3>


Gradually rescale `opacity_max`.
At each step, multiply `opacity_max` by `opacity_max_multiplier`
until reach `new_opacity_max`.

{% highlight fortran %}
relax_opacity_max = .false.
relax_initial_opacity_max = .false.
new_opacity_max = 0
opacity_max_multiplier = 0
{% endhighlight %}


<h3 id="relax_fixed_L_for_BB_outer_BC">relax_fixed_L_for_BB_outer_BC <a href="#relax_fixed_L_for_BB_outer_BC" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_fixed_L_for_BB_outer_BC">relax_initial_fixed_L_for_BB_outer_BC <a href="#relax_initial_fixed_L_for_BB_outer_BC" title="Permalink to this location">¶</a></h3>


<h3 id="steps_for_relax_fixed_L">steps_for_relax_fixed_L <a href="#steps_for_relax_fixed_L" title="Permalink to this location">¶</a></h3>


Gradually modify `fixed_L_for_BB_outer_BC`.

{% highlight fortran %}
relax_fixed_L_for_BB_outer_BC = .false.
relax_initial_fixed_L_for_BB_outer_BC = .false.
steps_for_relax_fixed_L = 0
{% endhighlight %}


<h3 id="relax_max_surf_dq">relax_max_surf_dq <a href="#relax_max_surf_dq" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_max_surf_dq">relax_initial_max_surf_dq <a href="#relax_initial_max_surf_dq" title="Permalink to this location">¶</a></h3>


<h3 id="new_max_surf_dq">new_max_surf_dq <a href="#new_max_surf_dq" title="Permalink to this location">¶</a></h3>


<h3 id="max_surf_dq_multiplier">max_surf_dq_multiplier <a href="#max_surf_dq_multiplier" title="Permalink to this location">¶</a></h3>


Gradually rescale `max_surface_cell_dq`.
At each step, multiply `max_surface_cell_dq` by `opacity_max_multiplier`
until reach `new_max_surf_dq`.

{% highlight fortran %}
relax_max_surf_dq = .false.
relax_initial_max_surf_dq = .false.
new_max_surf_dq = 0
max_surf_dq_multiplier = 0
{% endhighlight %}


<h3 id="relax_to_this_tau_factor">relax_to_this_tau_factor <a href="#relax_to_this_tau_factor" title="Permalink to this location">¶</a></h3>


<h3 id="dlogtau_factor">dlogtau_factor <a href="#dlogtau_factor" title="Permalink to this location">¶</a></h3>


<h3 id="relax_tau_factor">relax_tau_factor <a href="#relax_tau_factor" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_tau_factor">relax_initial_tau_factor <a href="#relax_initial_tau_factor" title="Permalink to this location">¶</a></h3>


<h3 id="relax_tau_factor_after_core_He_burn">relax_tau_factor_after_core_He_burn <a href="#relax_tau_factor_after_core_He_burn" title="Permalink to this location">¶</a></h3>


<h3 id="relax_tau_factor_after_core_C_burn">relax_tau_factor_after_core_C_burn <a href="#relax_tau_factor_after_core_C_burn" title="Permalink to this location">¶</a></h3>


`relax_to_this_tau_factor = 1` puts outer cell at photosphere;
can go much larger or much smaller to move surface in or out from photosphere.

`dlogtau_factor` changes `log10(tau_factor)` by at most this amount per step

`relax_tau_factor` true gradually changes `tau_factor`, reconverging at each step.

`relax_tau_factor_after_core_He_burn` ignored if <= 0;
change `tau_factor` when center H1 < 1e-4 and
center He4 < `relax_tau_factor_after_core_He_burn`.

`relax_tau_factor_after_core_C_burn` ignored if <= 0;
change `tau_factor` when center H1 < 1e-4,
He4 < 1e-4, and center C12 < `relax_tau_factor_after_core_C_burn`.

{% highlight fortran %}
relax_to_this_tau_factor = -1
dlogtau_factor = 0.1d0
relax_tau_factor = .false.
relax_initial_tau_factor = .false.
relax_tau_factor_after_core_He_burn = -1
relax_tau_factor_after_core_C_burn = -1
{% endhighlight %}


<h3 id="set_to_this_tau_factor">set_to_this_tau_factor <a href="#set_to_this_tau_factor" title="Permalink to this location">¶</a></h3>


<h3 id="set_tau_factor">set_tau_factor <a href="#set_tau_factor" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_tau_factor">set_initial_tau_factor <a href="#set_initial_tau_factor" title="Permalink to this location">¶</a></h3>


<h3 id="set_tau_factor_after_core_He_burn">set_tau_factor_after_core_He_burn <a href="#set_tau_factor_after_core_He_burn" title="Permalink to this location">¶</a></h3>


<h3 id="set_tau_factor_after_core_C_burn">set_tau_factor_after_core_C_burn <a href="#set_tau_factor_after_core_C_burn" title="Permalink to this location">¶</a></h3>


As for `relax_to_this_tau_factor`, but changes `tau_factor` without reconverging.

{% highlight fortran %}
set_to_this_tau_factor = -1
set_tau_factor = .false.
set_initial_tau_factor = .false.
set_tau_factor_after_core_He_burn = -1
set_tau_factor_after_core_C_burn = -1
{% endhighlight %}


<h3 id="adjust_tau_factor_to_surf_density">adjust_tau_factor_to_surf_density <a href="#adjust_tau_factor_to_surf_density" title="Permalink to this location">¶</a></h3>


<h3 id="base_for_adjust_tau_factor_to_surf_density">base_for_adjust_tau_factor_to_surf_density <a href="#base_for_adjust_tau_factor_to_surf_density" title="Permalink to this location">¶</a></h3>


if `adjust_tau_factor_to_surf_density`, then at start of each step
set `tau_factor` to current Rho(1) divided by `base_for_adjust_tau_factor_to_surf_density`

{% highlight fortran %}
adjust_tau_factor_to_surf_density = .false.
base_for_adjust_tau_factor_to_surf_density = 0d0
{% endhighlight %}


<h3 id="relax_to_this_opacity_factor">relax_to_this_opacity_factor <a href="#relax_to_this_opacity_factor" title="Permalink to this location">¶</a></h3>


<h3 id="d_opacity_factor">d_opacity_factor <a href="#d_opacity_factor" title="Permalink to this location">¶</a></h3>


<h3 id="relax_opacity_factor">relax_opacity_factor <a href="#relax_opacity_factor" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_opacity_factor">relax_initial_opacity_factor <a href="#relax_initial_opacity_factor" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
relax_to_this_opacity_factor = -1
d_opacity_factor = 0.1d0
relax_opacity_factor = .false.
relax_initial_opacity_factor = .false.
{% endhighlight %}


<h3 id="relax_to_this_Tsurf_factor">relax_to_this_Tsurf_factor <a href="#relax_to_this_Tsurf_factor" title="Permalink to this location">¶</a></h3>


<h3 id="dlogTsurf_factor">dlogTsurf_factor <a href="#dlogTsurf_factor" title="Permalink to this location">¶</a></h3>


<h3 id="relax_Tsurf_factor">relax_Tsurf_factor <a href="#relax_Tsurf_factor" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_Tsurf_factor">relax_initial_Tsurf_factor <a href="#relax_initial_Tsurf_factor" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
relax_to_this_Tsurf_factor = -1
dlogTsurf_factor = 0.1d0
relax_Tsurf_factor = .false.
relax_initial_Tsurf_factor = .false.
{% endhighlight %}


<h3 id="set_to_this_Tsurf_factor">set_to_this_Tsurf_factor <a href="#set_to_this_Tsurf_factor" title="Permalink to this location">¶</a></h3>


<h3 id="set_Tsurf_factor">set_Tsurf_factor <a href="#set_Tsurf_factor" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_Tsurf_factor">set_initial_Tsurf_factor <a href="#set_initial_Tsurf_factor" title="Permalink to this location">¶</a></h3>


As for `relax_to_this_Tsurf_factor`, but changes `Tsurf_factor` without reconverging.

{% highlight fortran %}
set_to_this_Tsurf_factor = -1
set_Tsurf_factor = .false.
set_initial_Tsurf_factor = .false.
{% endhighlight %}


<h3 id="relax_mass_change">relax_mass_change <a href="#relax_mass_change" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_mass_change">relax_initial_mass_change <a href="#relax_initial_mass_change" title="Permalink to this location">¶</a></h3>


<h3 id="relax_mass_change_min_steps">relax_mass_change_min_steps <a href="#relax_mass_change_min_steps" title="Permalink to this location">¶</a></h3>


<h3 id="relax_mass_change_max_yrs_dt">relax_mass_change_max_yrs_dt <a href="#relax_mass_change_max_yrs_dt" title="Permalink to this location">¶</a></h3>


<h3 id="relax_mass_change_init_mdot">relax_mass_change_init_mdot <a href="#relax_mass_change_init_mdot" title="Permalink to this location">¶</a></h3>


<h3 id="relax_mass_change_final_mdot">relax_mass_change_final_mdot <a href="#relax_mass_change_final_mdot" title="Permalink to this location">¶</a></h3>


`relax_mass_change_max_yrs_dt` in years
`relax_mass_change_init_mdot` in Msun/year

{% highlight fortran %}
relax_mass_change = .false.
relax_initial_mass_change = .false.
relax_mass_change_min_steps = 10
relax_mass_change_max_yrs_dt = 10
relax_mass_change_init_mdot = 0
relax_mass_change_final_mdot = 0
{% endhighlight %}


<h3 id="relax_irradiation">relax_irradiation <a href="#relax_irradiation" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_irradiation">relax_initial_irradiation <a href="#relax_initial_irradiation" title="Permalink to this location">¶</a></h3>


<h3 id="relax_to_this_irrad_flux">relax_to_this_irrad_flux <a href="#relax_to_this_irrad_flux" title="Permalink to this location">¶</a></h3>


<h3 id="relax_irradiation_min_steps">relax_irradiation_min_steps <a href="#relax_irradiation_min_steps" title="Permalink to this location">¶</a></h3>


<h3 id="relax_irradiation_max_yrs_dt">relax_irradiation_max_yrs_dt <a href="#relax_irradiation_max_yrs_dt" title="Permalink to this location">¶</a></h3>


<h3 id="irrad_col_depth">irrad_col_depth <a href="#irrad_col_depth" title="Permalink to this location">¶</a></h3>


extra heat near surface to model irradiation.
`relax_to_this_irrad_flux` is flux in erg s^-1 cm^-2 from companion.
we capture `Pi*R^2` of that flux  and distribute it uniformly
in the outer `4*Pi*R^2*irrad_col_depth` grams of the star,
where `irrad_col_depth` is in g cm^-2.

{% highlight fortran %}
relax_irradiation = .false.
relax_initial_irradiation = .false.
relax_to_this_irrad_flux = 0
relax_irradiation_min_steps = 0
relax_irradiation_max_yrs_dt = -1
irrad_col_depth = -1
{% endhighlight %}


<h3 id="set_irradiation">set_irradiation <a href="#set_irradiation" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_irradiation">set_initial_irradiation <a href="#set_initial_irradiation" title="Permalink to this location">¶</a></h3>


<h3 id="set_to_this_irrad_flux">set_to_this_irrad_flux <a href="#set_to_this_irrad_flux" title="Permalink to this location">¶</a></h3>


as for `relax_irradiation` but sets values and does not reconverge

{% highlight fortran %}
set_irradiation = .false.
set_initial_irradiation = .false.
set_to_this_irrad_flux = 0
{% endhighlight %}


<h3 id="change_lnPgas_flag">change_lnPgas_flag <a href="#change_lnPgas_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_lnPgas_flag">change_initial_lnPgas_flag <a href="#change_initial_lnPgas_flag" title="Permalink to this location">¶</a></h3>


<h3 id="new_lnPgas_flag">new_lnPgas_flag <a href="#new_lnPgas_flag" title="Permalink to this location">¶</a></h3>


lnPgas variables
`lnPgas_flag` is true if we are using lnPgas variables in place of lnd

{% highlight fortran %}
change_lnPgas_flag = .false.
change_initial_lnPgas_flag = .false.
new_lnPgas_flag = .false.
{% endhighlight %}


<h3 id="change_RTI_flag">change_RTI_flag <a href="#change_RTI_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_RTI_flag">change_initial_RTI_flag <a href="#change_initial_RTI_flag" title="Permalink to this location">¶</a></h3>


<h3 id="new_RTI_flag">new_RTI_flag <a href="#new_RTI_flag" title="Permalink to this location">¶</a></h3>


RTI variables
`RTI_flag` is true if we are doing Rayleigh Taylor Instabilities

{% highlight fortran %}
change_RTI_flag = .false.
change_initial_RTI_flag = .false.
new_RTI_flag = .false.
{% endhighlight %}


<h3 id="change_RSP_flag">change_RSP_flag <a href="#change_RSP_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_RSP_flag">change_initial_RSP_flag <a href="#change_initial_RSP_flag" title="Permalink to this location">¶</a></h3>


<h3 id="new_RSP_flag">new_RSP_flag <a href="#new_RSP_flag" title="Permalink to this location">¶</a></h3>


RSP variables
`RSP_flag` is true if we are doing radial stellar pulsations

{% highlight fortran %}
change_RSP_flag = .false.
change_initial_RSP_flag = .false.
new_RSP_flag = .false.
{% endhighlight %}


<h3 id="change_conv_vel_flag">change_conv_vel_flag <a href="#change_conv_vel_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_conv_vel_flag">change_initial_conv_vel_flag <a href="#change_initial_conv_vel_flag" title="Permalink to this location">¶</a></h3>


<h3 id="new_conv_vel_flag">new_conv_vel_flag <a href="#new_conv_vel_flag" title="Permalink to this location">¶</a></h3>


conv_vel variables
`conv_vel_flag` is true if we are using convection velocity as a solver variable

{% highlight fortran %}
change_conv_vel_flag = .false.
change_initial_conv_vel_flag = .false.
new_conv_vel_flag = .false.
{% endhighlight %}


<h3 id="change_mass_flag">change_mass_flag <a href="#change_mass_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_mass_flag">change_initial_mass_flag <a href="#change_initial_mass_flag" title="Permalink to this location">¶</a></h3>


<h3 id="new_mass_flag">new_mass_flag <a href="#new_mass_flag" title="Permalink to this location">¶</a></h3>


mass variables
`mass_flag` is true if we are using mass as a solver variable

{% highlight fortran %}
change_mass_flag = .false.
change_initial_mass_flag = .false.
new_mass_flag = .false.
{% endhighlight %}


<h2 id="velocity_variables">velocity variables <a href="#velocity_variables" title="Permalink to this location">¶</a></h2>


<h3 id="change_v_flag">change_v_flag <a href="#change_v_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_v_flag">change_initial_v_flag <a href="#change_initial_v_flag" title="Permalink to this location">¶</a></h3>


<h3 id="new_v_flag">new_v_flag <a href="#new_v_flag" title="Permalink to this location">¶</a></h3>


change whether MESA evolves a (radial) velocity variable, v,
defined at cell boundaries

{% highlight fortran %}
change_v_flag = .false.
change_initial_v_flag = .false.
new_v_flag = .false.
{% endhighlight %}


<h3 id="center_ye_limit_for_v_flag">center_ye_limit_for_v_flag <a href="#center_ye_limit_for_v_flag" title="Permalink to this location">¶</a></h3>


automatically turn on velocities if `center_ye` drops below this limit.
this is useful for evolution leading up to core collapse.

{% highlight fortran %}
center_ye_limit_for_v_flag = 0.45d0
{% endhighlight %}


<h3 id="gamma1_integral_for_v_flag">gamma1_integral_for_v_flag <a href="#gamma1_integral_for_v_flag" title="Permalink to this location">¶</a></h3>


automatically turn on velocities if `center_gamma1_integral` drops below this limit.
this is useful for evolution leading up to pair instability core collapse.
integral is sum over all cells of `(gamma1-4d0/3d0)` weighted by `dm*P/rho`

{% highlight fortran %}
gamma1_integral_for_v_flag = 0d0
{% endhighlight %}


<h3 id="logT_for_conv_vel_flag">logT_for_conv_vel_flag <a href="#logT_for_conv_vel_flag" title="Permalink to this location">¶</a></h3>


automatically turn on conv_vel_flag if temperature goes above this limit anywhere in the star.
This is useful to control flip-flops in gradT due to turning on and off of convection,
and allows the equations to be solved with small residuals.

{% highlight fortran %}
logT_for_conv_vel_flag = 50d0
{% endhighlight %}


<h3 id="change_u_flag">change_u_flag <a href="#change_u_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_u_flag">change_initial_u_flag <a href="#change_initial_u_flag" title="Permalink to this location">¶</a></h3>


<h3 id="new_u_flag">new_u_flag <a href="#new_u_flag" title="Permalink to this location">¶</a></h3>


change whether MESA evolves a (radial) velocity variable, u,
defined at cell centers.
this is an alternative to v at cell boundaries.
can use one or the other, but not both.

{% highlight fortran %}
change_u_flag = .false.
change_initial_u_flag = .false.
new_u_flag = .false.
{% endhighlight %}


<h3 id="change_reconstruction_flag">change_reconstruction_flag <a href="#change_reconstruction_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_reconstruction_flag">change_initial_reconstruction_flag <a href="#change_initial_reconstruction_flag" title="Permalink to this location">¶</a></h3>


<h3 id="new_reconstruction_flag">new_reconstruction_flag <a href="#new_reconstruction_flag" title="Permalink to this location">¶</a></h3>


change whether MESA reconstruction variables with Riemann.
only applies when u_flag is true.

{% highlight fortran %}
change_reconstruction_flag = .false.
change_initial_reconstruction_flag = .false.
new_reconstruction_flag = .false.
{% endhighlight %}


<h2 id="rotation_controls">rotation controls <a href="#rotation_controls" title="Permalink to this location">¶</a></h2>


<h3 id="new_rotation_flag">new_rotation_flag <a href="#new_rotation_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_rotation_flag">change_rotation_flag <a href="#change_rotation_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_rotation_flag">change_initial_rotation_flag <a href="#change_initial_rotation_flag" title="Permalink to this location">¶</a></h3>


rotation is enabled only if `rotation_flag` is true
`new_rotation_flag` is only used if `change_rotation_flag` is true
if `change_rotation_flag` true, then change `rotation_flag` to `new_rotation_flag`

NOTE: why 2 flags?
because I want 3 options: set true, set false, and leave it alone.
there are of course other ways to get 3 options, but this is what we have.

{% highlight fortran %}
new_rotation_flag = .false.
change_rotation_flag = .false.
change_initial_rotation_flag = .false.
{% endhighlight %}


the following only apply when rotation is already on (i.e., when `rotation_flag` is true),
including when you have just done `change_rotation_flag` true.
all of these initialize the model to uniform omega (i.e. "solid body")

<h3 id="new_omega">new_omega <a href="#new_omega" title="Permalink to this location">¶</a></h3>


<h3 id="set_omega">set_omega <a href="#set_omega" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_omega">set_initial_omega <a href="#set_initial_omega" title="Permalink to this location">¶</a></h3>


`new_omega` in rad/sec
`set_omega` applies when do ./rn or ./re; if true, sets uniform omega = `new_omega`
`set_initial_omega` only applies at start of run, not for restarts
if true, sets uniform omega = `new_omega`

{% highlight fortran %}
new_omega = 0
set_omega = .false.
set_initial_omega = .false.
{% endhighlight %}


<h3 id="new_omega_div_omega_crit">new_omega_div_omega_crit <a href="#new_omega_div_omega_crit" title="Permalink to this location">¶</a></h3>


<h3 id="set_omega_div_omega_crit">set_omega_div_omega_crit <a href="#set_omega_div_omega_crit" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_omega_div_omega_crit">set_initial_omega_div_omega_crit <a href="#set_initial_omega_div_omega_crit" title="Permalink to this location">¶</a></h3>


as above, but sets `omega/omega_crit`
`omega_crit` is defined as:

    gamma_factor = 1d0 - min(L_div_Ledd, 0.9999d0)
    omega_crit = sqrt(gamma_factor*s% cgrav(k)*s% m_grav(k)/pow3(s% r(k)))

{% highlight fortran %}
new_omega_div_omega_crit = 0
set_omega_div_omega_crit = .false.
set_initial_omega_div_omega_crit = .false.
{% endhighlight %}


<h3 id="new_surface_rotation_v__0__km_sec1">new_surface_rotation_v = 0 ! (km sec^1) <a href="#new_surface_rotation_v__0__km_sec1" title="Permalink to this location">¶</a></h3>


<h3 id="set_surface_rotation_v__false">set_surface_rotation_v = .false. <a href="#set_surface_rotation_v__false" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_surface_rotation_v__false">set_initial_surface_rotation_v = .false. <a href="#set_initial_surface_rotation_v__false" title="Permalink to this location">¶</a></h3>


as above, but sets surface velocity in km/sec

{% highlight fortran %}
new_surface_rotation_v = 0
set_surface_rotation_v = .false.
set_initial_surface_rotation_v = .false.
{% endhighlight %}


the previous controls are "one shot" -- they set omega once and are done.
however you might need to set omega for several models in a row
in order to give things a chance to adjust to the change.
the following controls let you do that.

<h3 id="set_omega_step_limit">set_omega_step_limit <a href="#set_omega_step_limit" title="Permalink to this location">¶</a></h3>


if `model_number` is <= this, then do `set_omega`

{% highlight fortran %}
set_omega_step_limit = -1
{% endhighlight %}


<h3 id="set_omega_div_omega_crit_step_limit">set_omega_div_omega_crit_step_limit <a href="#set_omega_div_omega_crit_step_limit" title="Permalink to this location">¶</a></h3>


if `model_number` is <= this, then do `set_omega_div_omega_crit`

{% highlight fortran %}
set_omega_div_omega_crit_step_limit = -1
{% endhighlight %}


<h3 id="set_surf_rotation_v_step_limit">set_surf_rotation_v_step_limit <a href="#set_surf_rotation_v_step_limit" title="Permalink to this location">¶</a></h3>


if `model_number` is <= this, then do `set_surface_rotation_v`

{% highlight fortran %}
set_surf_rotation_v_step_limit = -1
{% endhighlight %}


<h3 id="set_near_zams_omega_steps">set_near_zams_omega_steps <a href="#set_near_zams_omega_steps" title="Permalink to this location">¶</a></h3>


<h3 id="set_near_zams_omega_div_omega_crit_steps">set_near_zams_omega_div_omega_crit_steps <a href="#set_near_zams_omega_div_omega_crit_steps" title="Permalink to this location">¶</a></h3>


<h3 id="set_near_zams_surface_rotation_v_steps">set_near_zams_surface_rotation_v_steps <a href="#set_near_zams_surface_rotation_v_steps" title="Permalink to this location">¶</a></h3>


You might want to start a run at pre-ms but only turn on rotation when near zams
rather than force you to stop the run near zams, change the inlist, and restart.
The following will turn on rotation automatically.
The working definition of "near zams" is
`L_nuc_burn_total/L_phot >= Lnuc_div_L_upper_limit`
`Lnuc_div_L_upper_limit` is in the controls part of the inlist.

The following apply when rotation is off and model satisfies the "near zams" test.
Each turns on rotation and sets a step limit

only applies if > 0

    set_omega_step_limit = model_number + set_near_zams_omega_steps - 1

{% highlight fortran %}
set_near_zams_omega_steps = -1
{% endhighlight %}


only applies if > 0

    set_omega_div_omega_crit_step_limit =
        model_number + set_near_zams_omega_div_omega_crit_steps - 1

{% highlight fortran %}
set_near_zams_omega_div_omega_crit_steps = -1
{% endhighlight %}


only applies if > 0

    set_surf_rotation_v_step_limit =  model_number + set_surf_rotation_v_step_limit - 1

{% highlight fortran %}
set_near_zams_surface_rotation_v_steps = -1
{% endhighlight %}


<h3 id="num_steps_to_relax_rotation">num_steps_to_relax_rotation <a href="#num_steps_to_relax_rotation" title="Permalink to this location">¶</a></h3>


use `num_steps_to_relax_rotation` steps to relax omega to new value

{% highlight fortran %}
num_steps_to_relax_rotation = 100
{% endhighlight %}


<h3 id="relax_omega_max_yrs_dt">relax_omega_max_yrs_dt <a href="#relax_omega_max_yrs_dt" title="Permalink to this location">¶</a></h3>


`relax_omega_max_yrs_dt` sets a maximum time step used during the relaxation process
< 0 implies MESA chooses the step. Useful number is 1d4 if
`num_steps_to_relax_rotation` > ~150

{% highlight fortran %}
relax_omega_max_yrs_dt = -1
{% endhighlight %}


<h3 id="relax_omega">relax_omega <a href="#relax_omega" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_omega">relax_initial_omega <a href="#relax_initial_omega" title="Permalink to this location">¶</a></h3>


<h3 id="near_zams_relax_omega">near_zams_relax_omega <a href="#near_zams_relax_omega" title="Permalink to this location">¶</a></h3>


if `relax_omega` true, relax to value of `new_omega`. applies when do ./rn or ./re
`relax_initial_omega` only applies at start of run, not for restarts.
`near_zams_relax`+omega applies when "near zams".
The working definition of "near zams" is
`L_nuc_burn_total/L_phot >= Lnuc_div_L_upper_limit`
`Lnuc_div_L_upper_limit` is in the controls part of the inlist.

{% highlight fortran %}
relax_omega = .false.
relax_initial_omega = .false.
near_zams_relax_omega = .false.
{% endhighlight %}


<h3 id="relax_omega_div_omega_crit">relax_omega_div_omega_crit <a href="#relax_omega_div_omega_crit" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_omega_div_omega_crit">relax_initial_omega_div_omega_crit <a href="#relax_initial_omega_div_omega_crit" title="Permalink to this location">¶</a></h3>


<h3 id="near_zams_relax_omega_div_omega_crit">near_zams_relax_omega_div_omega_crit <a href="#near_zams_relax_omega_div_omega_crit" title="Permalink to this location">¶</a></h3>


as above for `relax_omega`, but for `omega`/`omega_crit`

{% highlight fortran %}
relax_omega_div_omega_crit = .false.
relax_initial_omega_div_omega_crit = .false.
near_zams_relax_omega_div_omega_crit = .false.
{% endhighlight %}


<h3 id="relax_surface_rotation_v">relax_surface_rotation_v <a href="#relax_surface_rotation_v" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_surface_rotation_v">relax_initial_surface_rotation_v <a href="#relax_initial_surface_rotation_v" title="Permalink to this location">¶</a></h3>


<h3 id="near_zams_relax_initial_surface_rotation_v">near_zams_relax_initial_surface_rotation_v <a href="#near_zams_relax_initial_surface_rotation_v" title="Permalink to this location">¶</a></h3>


as above for `relax_omega`, but for surface speed

{% highlight fortran %}
relax_surface_rotation_v = .false.
relax_initial_surface_rotation_v = .false.
near_zams_relax_initial_surface_rotation_v = .false.
{% endhighlight %}


<h3 id="new_D_omega_flag">new_D_omega_flag <a href="#new_D_omega_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_D_omega_flag">change_D_omega_flag <a href="#change_D_omega_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_D_omega_flag">change_initial_D_omega_flag <a href="#change_initial_D_omega_flag" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
new_D_omega_flag = .false.
change_D_omega_flag = .false.
change_initial_D_omega_flag = .false.
{% endhighlight %}


<h3 id="new_am_nu_rot_flag">new_am_nu_rot_flag <a href="#new_am_nu_rot_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_am_nu_rot_flag">change_am_nu_rot_flag <a href="#change_am_nu_rot_flag" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_am_nu_rot_flag">change_initial_am_nu_rot_flag <a href="#change_initial_am_nu_rot_flag" title="Permalink to this location">¶</a></h3>


<h3 id="use_D_omega_for_am_nu_rot">use_D_omega_for_am_nu_rot <a href="#use_D_omega_for_am_nu_rot" title="Permalink to this location">¶</a></h3>


if `am_nu_rot_flag` is true, use time and space smoothed `am_nu_rot` like `D_omega`
else if `D_omega_flag` and `use_D_omega_for_am_nu_rot`, use `D_omega` for `am_nu_rot`
else use `am_nu_rot` from current model with no smoothing

{% highlight fortran %}
new_am_nu_rot_flag = .false.
change_am_nu_rot_flag = .false.
change_initial_am_nu_rot_flag = .false.
use_D_omega_for_am_nu_rot = .true.
{% endhighlight %}


<h3 id="relax_core">relax_core <a href="#relax_core" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_core">relax_initial_core <a href="#relax_initial_core" title="Permalink to this location">¶</a></h3>


<h3 id="new_core_mass">new_core_mass <a href="#new_core_mass" title="Permalink to this location">¶</a></h3>


<h3 id="dlg_core_mass_per_step">dlg_core_mass_per_step <a href="#dlg_core_mass_per_step" title="Permalink to this location">¶</a></h3>


<h3 id="relax_core_years_for_dt">relax_core_years_for_dt <a href="#relax_core_years_for_dt" title="Permalink to this location">¶</a></h3>


<h3 id="core_avg_rho">core_avg_rho <a href="#core_avg_rho" title="Permalink to this location">¶</a></h3>


<h3 id="core_avg_eps">core_avg_eps <a href="#core_avg_eps" title="Permalink to this location">¶</a></h3>


controls for nonzero center M (mass), R (radius), L (luminosity)
(e.g., to model neutron star envelope or rocky core planet)
`new_core_mass` in Msun units.
If you have convergence problems,
you'll need to reduce the mass/step `dlg_core_mass_per_step`
and timestep `relax_core_years_for_dt` values.
`core_avg_rho` in g/cm^3 and `core_avg_eps` in ergs/g/sec are just examples.
Adjust them to values appropriate for your application.

{% highlight fortran %}
relax_core = .false.
relax_initial_core = .false.
new_core_mass = 0
dlg_core_mass_per_step = 1d-3
relax_core_years_for_dt = 1
core_avg_rho = 10
core_avg_eps = 1d-6
{% endhighlight %}


<h3 id="relax_M_center">relax_M_center <a href="#relax_M_center" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_M_center">relax_initial_M_center <a href="#relax_initial_M_center" title="Permalink to this location">¶</a></h3>


<h3 id="relax_M_center_dt">relax_M_center_dt <a href="#relax_M_center_dt" title="Permalink to this location">¶</a></h3>


Like `relax_mass_scale`, but all change in mass goes into `M_center`.
NOTE: `new_mass` is new total mass for star, not the new `M_center` value.
uses `dlgm_per_step` in same way as `relax_mass_scale`.
`relax_M_center_dt` in seconds

Example: If you want to end up with total mass = 1.4 and `M_center` = 1.3,
start with `star_mass` = total - center = 0.1 = mass exterior to center.
Then `relax_M_center` with `new_mass` = 1.4.
That will give a new total mass of 1.4 by changing `M_center`.
The mass exterior to the center will stay = 0.1,
so the final `M_center` will be 1.3.

{% highlight fortran %}
relax_M_center = .false.
relax_initial_M_center = .false.
relax_M_center_dt = 3.1558149984d1
{% endhighlight %}


<h3 id="relax_R_center">relax_R_center <a href="#relax_R_center" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_R_center">relax_initial_R_center <a href="#relax_initial_R_center" title="Permalink to this location">¶</a></h3>


<h3 id="new_R_center">new_R_center <a href="#new_R_center" title="Permalink to this location">¶</a></h3>


<h3 id="dlgR_per_step">dlgR_per_step <a href="#dlgR_per_step" title="Permalink to this location">¶</a></h3>


<h3 id="relax_R_center_dt">relax_R_center_dt <a href="#relax_R_center_dt" title="Permalink to this location">¶</a></h3>


as above for the mass, but for the radius.
`new_R_center` in cm.
`relax_R_center_dt` in seconds.

{% highlight fortran %}
relax_R_center = .false.
relax_initial_R_center = .false.
new_R_center = 0
dlgR_per_step = 3d-3
relax_R_center_dt = 3.1558149984d1
{% endhighlight %}


<h3 id="zero_alpha_RTI">zero_alpha_RTI <a href="#zero_alpha_RTI" title="Permalink to this location">¶</a></h3>


<h3 id="zero_initial_alpha_RTI">zero_initial_alpha_RTI <a href="#zero_initial_alpha_RTI" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
zero_alpha_RTI = .false.
zero_initial_alpha_RTI = .false.
{% endhighlight %}


<h3 id="set_v_center">set_v_center <a href="#set_v_center" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_v_center">set_initial_v_center <a href="#set_initial_v_center" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
set_v_center = .false.
set_initial_v_center = .false.
{% endhighlight %}


<h3 id="relax_v_center">relax_v_center <a href="#relax_v_center" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_v_center">relax_initial_v_center <a href="#relax_initial_v_center" title="Permalink to this location">¶</a></h3>


<h3 id="new_v_center">new_v_center <a href="#new_v_center" title="Permalink to this location">¶</a></h3>


<h3 id="dv_per_step">dv_per_step <a href="#dv_per_step" title="Permalink to this location">¶</a></h3>


<h3 id="relax_v_center_dt">relax_v_center_dt <a href="#relax_v_center_dt" title="Permalink to this location">¶</a></h3>


`new_v_center` in cm/s.
`relax_v_center_dt` in seconds.

{% highlight fortran %}
relax_v_center = .false.
relax_initial_v_center = .false.
new_v_center = 0
dv_per_step = 0
relax_v_center_dt = 0
{% endhighlight %}


<h3 id="set_L_center">set_L_center <a href="#set_L_center" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_L_center">set_initial_L_center <a href="#set_initial_L_center" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
set_L_center = .false.
set_initial_L_center = .false.
{% endhighlight %}


<h3 id="relax_L_center">relax_L_center <a href="#relax_L_center" title="Permalink to this location">¶</a></h3>


<h3 id="relax_initial_L_center">relax_initial_L_center <a href="#relax_initial_L_center" title="Permalink to this location">¶</a></h3>


<h3 id="new_L_center">new_L_center <a href="#new_L_center" title="Permalink to this location">¶</a></h3>


<h3 id="dlgL_per_step">dlgL_per_step <a href="#dlgL_per_step" title="Permalink to this location">¶</a></h3>


<h3 id="relax_L_center_dt">relax_L_center_dt <a href="#relax_L_center_dt" title="Permalink to this location">¶</a></h3>


as above for the mass, but for the luminosity.
`new_L_center` in Lsun.
`relax_L_center_dt` in seconds.

{% highlight fortran %}
relax_L_center = .false.
relax_initial_L_center = .false.
new_L_center = 0
dlgL_per_step = 5d-2
relax_L_center_dt = 3.1558149984d1
{% endhighlight %}


<h3 id="remove_initial_center_at_cell_k">remove_initial_center_at_cell_k <a href="#remove_initial_center_at_cell_k" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_temperature">remove_initial_center_by_temperature <a href="#remove_initial_center_by_temperature" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_mass_fraction_q">remove_initial_center_by_mass_fraction_q <a href="#remove_initial_center_by_mass_fraction_q" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_delta_mass_gm">remove_initial_center_by_delta_mass_gm <a href="#remove_initial_center_by_delta_mass_gm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_delta_mass_msun">remove_initial_center_by_delta_mass_msun <a href="#remove_initial_center_by_delta_mass_msun" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_mass_gm">remove_initial_center_by_mass_gm <a href="#remove_initial_center_by_mass_gm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_mass_msun">remove_initial_center_by_mass_msun <a href="#remove_initial_center_by_mass_msun" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_radius_cm">remove_initial_center_by_radius_cm <a href="#remove_initial_center_by_radius_cm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_radius_Rsun">remove_initial_center_by_radius_Rsun <a href="#remove_initial_center_by_radius_Rsun" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_he4">remove_initial_center_by_he4 <a href="#remove_initial_center_by_he4" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_si28">remove_initial_center_by_si28 <a href="#remove_initial_center_by_si28" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_to_reduce_co56_ni56">remove_initial_center_to_reduce_co56_ni56 <a href="#remove_initial_center_to_reduce_co56_ni56" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_ye">remove_initial_center_by_ye <a href="#remove_initial_center_by_ye" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_entropy">remove_initial_center_by_entropy <a href="#remove_initial_center_by_entropy" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_center_by_infall_kms">remove_initial_center_by_infall_kms <a href="#remove_initial_center_by_infall_kms" title="Permalink to this location">¶</a></h3>


allows the core to be removed. ignored if <= 0
value for si28 is mass fraction at which to make mass cut
i.e. cut at first location going inward where mass fraction of si28 >= this limit
value for ye is electron per baryon number for cut
value for infall_kms is infall speed in km per sec to make the cut

{% highlight fortran %}
remove_initial_center_at_cell_k = 0
remove_initial_center_by_temperature = 0
remove_initial_center_by_mass_fraction_q = 0
remove_initial_center_by_delta_mass_gm = 0
remove_initial_center_by_delta_mass_Msun = 0
remove_initial_center_by_mass_gm = 0
remove_initial_center_by_mass_Msun = 0
remove_initial_center_by_radius_cm = 0
remove_initial_center_by_radius_Rsun = 0
remove_initial_center_by_he4 = 0
remove_initial_center_by_si28 = 0
remove_initial_center_to_reduce_co56_ni56 = 0
remove_initial_center_by_ye = 0
remove_initial_center_by_entropy = 0
remove_initial_center_by_infall_kms = 0
{% endhighlight %}


<h3 id="remove_center_at_cell_k">remove_center_at_cell_k <a href="#remove_center_at_cell_k" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_temperature">remove_center_by_temperature <a href="#remove_center_by_temperature" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_mass_fraction_q">remove_center_by_mass_fraction_q <a href="#remove_center_by_mass_fraction_q" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_delta_mass_gm">remove_center_by_delta_mass_gm <a href="#remove_center_by_delta_mass_gm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_delta_mass_Msun">remove_center_by_delta_mass_Msun <a href="#remove_center_by_delta_mass_Msun" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_mass_gm">remove_center_by_mass_gm <a href="#remove_center_by_mass_gm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_mass_Msun">remove_center_by_mass_Msun <a href="#remove_center_by_mass_Msun" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_radius_cm">remove_center_by_radius_cm <a href="#remove_center_by_radius_cm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_radius_Rsun">remove_center_by_radius_Rsun <a href="#remove_center_by_radius_Rsun" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_he4">remove_center_by_he4 <a href="#remove_center_by_he4" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_si28">remove_center_by_si28 <a href="#remove_center_by_si28" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_to_reduce_co56_ni56">remove_center_to_reduce_co56_ni56 <a href="#remove_center_to_reduce_co56_ni56" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_ye">remove_center_by_ye <a href="#remove_center_by_ye" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_entropy">remove_center_by_entropy <a href="#remove_center_by_entropy" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_by_infall_kms">remove_center_by_infall_kms <a href="#remove_center_by_infall_kms" title="Permalink to this location">¶</a></h3>


allows the core to be removed. ignored if <= 0

{% highlight fortran %}
remove_center_at_cell_k = 0
remove_center_by_temperature = 0
remove_center_by_mass_fraction_q = 0
remove_center_by_delta_mass_gm = 0
remove_center_by_delta_mass_Msun = 0
remove_center_by_mass_gm = 0
remove_center_by_mass_Msun = 0
remove_center_by_radius_cm = 0
remove_center_by_radius_Rsun = 0
remove_center_by_he4 = 0
remove_center_by_si28 = 0
remove_center_to_reduce_co56_ni56 = 0
remove_center_by_ye = 0
remove_center_by_entropy = 0
remove_center_by_infall_kms = 0
{% endhighlight %}


<h3 id="remove_initial_fe_core">remove_initial_fe_core <a href="#remove_initial_fe_core" title="Permalink to this location">¶</a></h3>


<h3 id="remove_fe_core">remove_fe_core <a href="#remove_fe_core" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
remove_initial_fe_core = .false.
remove_fe_core = .false.
{% endhighlight %}


<h3 id="remove_initial_center_at_inner_max_abs_v">remove_initial_center_at_inner_max_abs_v <a href="#remove_initial_center_at_inner_max_abs_v" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_at_inner_max_abs_v">remove_center_at_inner_max_abs_v <a href="#remove_center_at_inner_max_abs_v" title="Permalink to this location">¶</a></h3>


<h3 id="remove_center_set_zero_v_center">remove_center_set_zero_v_center <a href="#remove_center_set_zero_v_center" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
remove_initial_center_at_inner_max_abs_v = .false.
remove_center_at_inner_max_abs_v = .false.
remove_center_set_zero_v_center = .false.
{% endhighlight %}


<h3 id="remove_fallback_at_each_step">remove_fallback_at_each_step <a href="#remove_fallback_at_each_step" title="Permalink to this location">¶</a></h3>


<h3 id="fallback_check_total_energy">fallback_check_total_energy <a href="#fallback_check_total_energy" title="Permalink to this location">¶</a></h3>


<h3 id="remove_fallback_speed_limit">remove_fallback_speed_limit <a href="#remove_fallback_speed_limit" title="Permalink to this location">¶</a></h3>


if fallback_check_total_energy is false,
starting at innermost cell, remove the region of cells 
that all have infall speed greater than
remove_fallback_speed_limit in units of sound speed.

if fallback_check_total_energy is true,
integrate total energy outward from innermost cell.
if integral goes negative, then have bound inner region.
continue outward until reach a cell that has local pe+ke+ie > 0.
delete everything inward of that cell.

{% highlight fortran %}
remove_fallback_at_each_step = .false.
fallback_check_total_energy = .false.
remove_fallback_speed_limit = 0.1d0
{% endhighlight %}


<h3 id="remove_center_adjust_L_center">remove_center_adjust_L_center <a href="#remove_center_adjust_L_center" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
remove_center_adjust_L_center = .true.
{% endhighlight %}


<h3 id="limit_center_logP_at_each_step">limit_center_logP_at_each_step <a href="#limit_center_logP_at_each_step" title="Permalink to this location">¶</a></h3>


at start of each step
remove center cells if necessary to keep logP at innermost cell >= this limit.

{% highlight fortran %}
limit_center_logP_at_each_step = -1d99
{% endhighlight %}


<h3 id="zero_initial_inner_v_by_mass_msun">zero_initial_inner_v_by_mass_msun <a href="#zero_initial_inner_v_by_mass_msun" title="Permalink to this location">¶</a></h3>


<h3 id="zero_inner_v_by_mass_Msun">zero_inner_v_by_mass_Msun <a href="#zero_inner_v_by_mass_Msun" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
zero_initial_inner_v_by_mass_Msun = 0
zero_inner_v_by_mass_Msun = 0
{% endhighlight %}


<h3 id="remove_center_logRho_limit">remove_center_logRho_limit <a href="#remove_center_logRho_limit" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
remove_center_logRho_limit = -1d99
{% endhighlight %}


<h3 id="remove_initial_surface_at_cell_k">remove_initial_surface_at_cell_k <a href="#remove_initial_surface_at_cell_k" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_optical_depth">remove_initial_surface_by_optical_depth <a href="#remove_initial_surface_by_optical_depth" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_temperature">remove_initial_surface_by_temperature <a href="#remove_initial_surface_by_temperature" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_density">remove_initial_surface_by_density <a href="#remove_initial_surface_by_density" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_pressure">remove_initial_surface_by_pressure <a href="#remove_initial_surface_by_pressure" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_mass_fraction_q">remove_initial_surface_by_mass_fraction_q <a href="#remove_initial_surface_by_mass_fraction_q" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_mass_gm">remove_initial_surface_by_mass_gm <a href="#remove_initial_surface_by_mass_gm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_mass_msun">remove_initial_surface_by_mass_msun <a href="#remove_initial_surface_by_mass_msun" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_radius_cm">remove_initial_surface_by_radius_cm <a href="#remove_initial_surface_by_radius_cm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_radius_Rsun">remove_initial_surface_by_radius_Rsun <a href="#remove_initial_surface_by_radius_Rsun" title="Permalink to this location">¶</a></h3>


<h3 id="remove_initial_surface_by_v_surf_km_s">remove_initial_surface_by_v_surf_km_s <a href="#remove_initial_surface_by_v_surf_km_s" title="Permalink to this location">¶</a></h3>


allows the outer envelope to be removed. ignored if <= 0

{% highlight fortran %}
remove_initial_surface_at_cell_k = 0
remove_initial_surface_by_optical_depth = 0
remove_initial_surface_by_temperature = 0
remove_initial_surface_by_density = 0
remove_initial_surface_by_pressure = 0
remove_initial_surface_by_mass_fraction_q = 0
remove_initial_surface_by_mass_gm = 0
remove_initial_surface_by_mass_Msun = 0
remove_initial_surface_by_radius_cm = 0
remove_initial_surface_by_radius_Rsun = 0
remove_initial_surface_by_v_surf_km_s = 0
remove_initial_surface_by_v_surf_div_cs = 0
remove_initial_surface_by_v_surf_div_v_escape = 0
{% endhighlight %}


<h3 id="remove_surface_at_cell_k">remove_surface_at_cell_k <a href="#remove_surface_at_cell_k" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_optical_depth">remove_surface_by_optical_depth <a href="#remove_surface_by_optical_depth" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_temperature">remove_surface_by_temperature <a href="#remove_surface_by_temperature" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_density">remove_surface_by_density <a href="#remove_surface_by_density" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_pressure">remove_surface_by_pressure <a href="#remove_surface_by_pressure" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_mass_fraction_q">remove_surface_by_mass_fraction_q <a href="#remove_surface_by_mass_fraction_q" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_mass_gm">remove_surface_by_mass_gm <a href="#remove_surface_by_mass_gm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_mass_Msun_______remove_enough_to_reduce_mstar_to_this_value">remove_surface_by_mass_Msun       remove enough to reduce mstar to this value <a href="#remove_surface_by_mass_Msun_______remove_enough_to_reduce_mstar_to_this_value" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_radius_cm">remove_surface_by_radius_cm <a href="#remove_surface_by_radius_cm" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_radius_Rsun">remove_surface_by_radius_Rsun <a href="#remove_surface_by_radius_Rsun" title="Permalink to this location">¶</a></h3>


<h3 id="remove_surface_by_v_surf_km_s">remove_surface_by_v_surf_km_s <a href="#remove_surface_by_v_surf_km_s" title="Permalink to this location">¶</a></h3>


allows the outer envelope to be removed. ignored if <= 0

{% highlight fortran %}
remove_surface_at_cell_k = 0
remove_surface_by_optical_depth = 0
remove_surface_by_temperature = 0
remove_surface_by_density = 0
remove_surface_by_pressure = 0
remove_surface_by_mass_fraction_q = 0
remove_surface_by_mass_gm = 0
remove_surface_by_mass_Msun = 0
remove_surface_by_radius_cm = 0
remove_surface_by_radius_Rsun = 0
remove_surface_by_v_surf_km_s = 0
remove_surface_by_v_surf_div_cs = 0
remove_surface_by_v_surf_div_v_escape = 0
{% endhighlight %}


<h3 id="repeat_remove_surface_for_each_step">repeat_remove_surface_for_each_step <a href="#repeat_remove_surface_for_each_step" title="Permalink to this location">¶</a></h3>


if true, then at each step removes surface as specified.
e.g., if doing remove at specific density and
expansion has lowered the surface density to below the limit,
then remove surface mass down to the limit.

{% highlight fortran %}
repeat_remove_surface_for_each_step = .false.
{% endhighlight %}


<h3 id="report_mass_not_fe56">report_mass_not_fe56 <a href="#report_mass_not_fe56" title="Permalink to this location">¶</a></h3>


reports mass that is not fe56

{% highlight fortran %}
report_mass_not_fe56 = .false.
{% endhighlight %}


<h3 id="report_cell_for_xm">report_cell_for_xm <a href="#report_cell_for_xm" title="Permalink to this location">¶</a></h3>


in grams. if > 0 then write smallest k s.t.
mass in cells 1 to k is >= `report_cell_for_xm`

{% highlight fortran %}
report_cell_for_xm = -1
{% endhighlight %}


<h3 id="set_to_xa_for_accretion">set_to_xa_for_accretion <a href="#set_to_xa_for_accretion" title="Permalink to this location">¶</a></h3>


<h3 id="set_initial_to_xa_for_accretion">set_initial_to_xa_for_accretion <a href="#set_initial_to_xa_for_accretion" title="Permalink to this location">¶</a></h3>


<h3 id="set_nzlo">set_nzlo <a href="#set_nzlo" title="Permalink to this location">¶</a></h3>


<h3 id="set_nzhi">set_nzhi <a href="#set_nzhi" title="Permalink to this location">¶</a></h3>


changes the composition to the mass fractions `xa_for_accretion`.
useful for creating a model with specific uniform composition.
`set_to_xa_for_accretion` true, means do when start or restart.
`set_initial_to_xa_for_accretion` true, means do for start but not for restarts.
nzlo and nzhi determine the range of cells that will be changed.
nzlo < 0 means change out to surface.
nzhi < 0 or nzhi > number of cells means change to center.

{% highlight fortran %}
set_to_xa_for_accretion = .false.
set_initial_to_xa_for_accretion = .false.
set_nzlo = -1
set_nzhi = -1
{% endhighlight %}


<h3 id="set_initial_cumulative_energy_error">set_initial_cumulative_energy_error <a href="#set_initial_cumulative_energy_error" title="Permalink to this location">¶</a></h3>


<h3 id="initial_cumulative_energy_error">initial_cumulative_energy_error <a href="#initial_cumulative_energy_error" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
set_initial_cumulative_energy_error = .false.
set_cumulative_energy_error = .false.
new_cumulative_energy_error = 0d0
{% endhighlight %}

<h1 id="eos_controls">eos controls <a href="#eos_controls" title="Permalink to this location">¶</a></h1>


<h3 id="eos_file_prefix">eos_file_prefix <a href="#eos_file_prefix" title="Permalink to this location">¶</a></h3>


<h3 id="eosDT_Z1_suffix">eosDT_Z1_suffix <a href="#eosDT_Z1_suffix" title="Permalink to this location">¶</a></h3>


<h3 id="eosPT_Z1_suffix">eosPT_Z1_suffix <a href="#eosPT_Z1_suffix" title="Permalink to this location">¶</a></h3>


Modify this to select a different set of EoS tables.

{% highlight fortran %}
eos_file_prefix = 'mesa'
eosDT_Z1_suffix = '_CO_1'
eosPT_Z1_suffix = '_CO_1'
{% endhighlight %}


<h3 id="set_HELM_OPAL_Zs">set_HELM_OPAL_Zs <a href="#set_HELM_OPAL_Zs" title="Permalink to this location">¶</a></h3>


<h3 id="Z_all_HELM">Z_all_HELM <a href="#Z_all_HELM" title="Permalink to this location">¶</a></h3>


<h3 id="Z_all_OPAL">Z_all_OPAL <a href="#Z_all_OPAL" title="Permalink to this location">¶</a></h3>


Max Z for using OPAL data instead of switching to HELM.
If `set_HELM_OPAL_Zs` false, just use the eos default.
Use HELM for Z > `Z_all_HELM`.
Use OPAL for Z < `Z_all_OPAL`.
Blend in the region `Z_all_OPAL < Z < Z_all_HELM`.
The highest Z OPAL table in MESA is Z = 0.04;
for Z > 0.04, the EOS will simply use the Z = 0.04 table for OPAL data.

{% highlight fortran %}
set_HELM_OPAL_Zs = .false.
Z_all_HELM = 0.06d0
Z_all_OPAL = 0.05d0
{% endhighlight %}


<h3 id="set_HELM_SCVH_lgTs">set_HELM_SCVH_lgTs <a href="#set_HELM_SCVH_lgTs" title="Permalink to this location">¶</a></h3>


<h3 id="logT_low_all_HELM">logT_low_all_HELM <a href="#logT_low_all_HELM" title="Permalink to this location">¶</a></h3>


<h3 id="logT_low_all_SCVH">logT_low_all_SCVH <a href="#logT_low_all_SCVH" title="Permalink to this location">¶</a></h3>


Transition temperature zone for SCVH to HELM at low T.
If `set_HELM_SCVH_lgTs` true, change limits.

+ `logT_low_all_HELM` : use HELM for lgT <= this
+ `logT_low_all_SCVH` : use SCVH for lgT >= this

{% highlight fortran %}
set_HELM_SCVH_lgTs = .false.
logT_low_all_HELM = 2.2d0
logT_low_all_SCVH = 2.3d0
{% endhighlight %}


<h3 id="set_HELM_OPAL_lgTs">set_HELM_OPAL_lgTs <a href="#set_HELM_OPAL_lgTs" title="Permalink to this location">¶</a></h3>


<h3 id="logT_all_HELM">logT_all_HELM <a href="#logT_all_HELM" title="Permalink to this location">¶</a></h3>


<h3 id="logT_all_OPAL">logT_all_OPAL <a href="#logT_all_OPAL" title="Permalink to this location">¶</a></h3>


Transition temperature zone for OPAL to HELM at high T.
If `set_HELM_OPAL_lgTs` true, change limits.

+ `logT_all_HELM` :  use HELM for lgT >= this
+ `logT_all_OPAL` : use OPAL/SCVH for lgT <= this

{% highlight fortran %}
set_HELM_OPAL_lgTs = .false.
logT_all_HELM = 7.7d0
logT_all_OPAL = 7.6d0
{% endhighlight %}


<h3 id="set_logRho_OPAL_SCVH_limits">set_logRho_OPAL_SCVH_limits <a href="#set_logRho_OPAL_SCVH_limits" title="Permalink to this location">¶</a></h3>


<h3 id="logRho1_OPAL_SCVH_limit">logRho1_OPAL_SCVH_limit <a href="#logRho1_OPAL_SCVH_limit" title="Permalink to this location">¶</a></h3>


<h3 id="logRho2_OPAL_SCVH_limit">logRho2_OPAL_SCVH_limit <a href="#logRho2_OPAL_SCVH_limit" title="Permalink to this location">¶</a></h3>


<h3 id="logRho_min_OPAL_SCVH_limit">logRho_min_OPAL_SCVH_limit <a href="#logRho_min_OPAL_SCVH_limit" title="Permalink to this location">¶</a></h3>


Transition density zones for OPAL/SCVH to HELM/PC.
If `set_logRho_OPAL_SCVH_limits` true, change limits.

+ `logRho1_OPAL_SCVH_limit` : don't use `OPAL_SCVH` for logRho > this
+ `logRho2_OPAL_SCVH_limit` : full `OPAL_SCVH` okay for logRho < this
+ `logRho_min_OPAL_SCVH_limit` : full `HELM` for logRho < this

Blend OPAL/SCVH with HELM/PC for logRho between these.

{% highlight fortran %}
set_logRho_OPAL_SCVH_limits = .false.
logRho1_OPAL_SCVH_limit = 2.7d0
logRho2_OPAL_SCVH_limit = 2.5d0
logRho_min_OPAL_SCVH_limit = -14.299d0
{% endhighlight %}


<h3 id="set_eos_PC_parameters">set_eos_PC_parameters <a href="#set_eos_PC_parameters" title="Permalink to this location">¶</a></h3>


<h3 id="mass_fraction_limit_for_PC">mass_fraction_limit_for_PC <a href="#mass_fraction_limit_for_PC" title="Permalink to this location">¶</a></h3>


<h3 id="logRho1_PC_limit">logRho1_PC_limit <a href="#logRho1_PC_limit" title="Permalink to this location">¶</a></h3>


<h3 id="logRho2_PC_limit">logRho2_PC_limit <a href="#logRho2_PC_limit" title="Permalink to this location">¶</a></h3>


<h3 id="log_Gamma_all_HELM">log_Gamma_all_HELM <a href="#log_Gamma_all_HELM" title="Permalink to this location">¶</a></h3>


<h3 id="log_Gamma_all_PC">log_Gamma_all_PC <a href="#log_Gamma_all_PC" title="Permalink to this location">¶</a></h3>


<h3 id="PC_Gamma_start_crystal">PC_Gamma_start_crystal <a href="#PC_Gamma_start_crystal" title="Permalink to this location">¶</a></h3>


<h3 id="PC_Gamma_full_crystal">PC_Gamma_full_crystal <a href="#PC_Gamma_full_crystal" title="Permalink to this location">¶</a></h3>


<h3 id="PC_min_Z">PC_min_Z <a href="#PC_min_Z" title="Permalink to this location">¶</a></h3>


Change HELM PC limits.
If `set_eos_PC_parameters` true, change limits.

+ `mass_fraction_limit_for_PC` : skips species if abundance < this
+ `logRho1_PC_limit` : use pure PC for logRho > this
+ `logRho2_PC_limit` : don't use PC for logRho < this (>= 2.8 or so because of PPT)
+ `log_Gamma_all_HELM` : HELM for `log_Gamma` <= this (1.0d0 = log10(10))
+ `log_Gamma_all_PC` : PC for `log_Gamma` >= this (1.3010299956d0 = log10(20))
+ `PC_Gamma_start_crystal` : start releasing crystallization heat at Gamma > this
+ `PC_Gamma_full_crystal` : finish releasing latent heat. Fully solid for Gamma > this
+ `PC_min_Z` : don't use PC for Z < this

Need `PC_Gamma_start_crystal` > `Gamma_lnS_eps_grav_full_on` for latent heat
to be included in eps_grav properly.

{% highlight fortran %}
set_eos_PC_parameters = .false.
mass_fraction_limit_for_PC = 1d-3
logRho1_PC_limit = 2.999d0
logRho2_PC_limit = 2.8d0
log_Gamma_all_HELM = 1.0d0
log_Gamma_all_PC = 1.3010299956d0
PC_Gamma_start_crystal = 150d0
PC_Gamma_full_crystal = 175d0
PC_min_Z = 0.999d0
{% endhighlight %}


<h3 id="set_HELM_ion_neutral_blends">set_HELM_ion_neutral_blends <a href="#set_HELM_ion_neutral_blends" title="Permalink to this location">¶</a></h3>


<h3 id="max_logRho_neutral_HELM">max_logRho_neutral_HELM <a href="#max_logRho_neutral_HELM" title="Permalink to this location">¶</a></h3>


<h3 id="logT_neutral_HELM">logT_neutral_HELM <a href="#logT_neutral_HELM" title="Permalink to this location">¶</a></h3>


<h3 id="logT_ion_HELM">logT_ion_HELM <a href="#logT_ion_HELM" title="Permalink to this location">¶</a></h3>


HELM does not explicitly include ionization.
Therefore these transitions are imposed manually.

{% highlight fortran %}
set_HELM_ion_neutral_blends = .false.
{% endhighlight %}


Transition between neutral and ionized at some density
Fully neutral for `logRho <= max_logRho_neutral_HELM`
Fully ionized for `logRho >= max_logRho_neutral_HELM`

{% highlight fortran %}
max_logRho_neutral_HELM = -1.5d0
{% endhighlight %}


Transition between neutral and ionized over some temperature range
Fully ionized for `logT >= logT_ion_HELM`
Fully neutral for `logT <= logT_neutral_HELM`

{% highlight fortran %}
logT_ion_HELM = 5.0d0
logT_neutral_HELM = 4.5d0
{% endhighlight %}


<h3 id="set_other_HELM_flags">set_other_HELM_flags <a href="#set_other_HELM_flags" title="Permalink to this location">¶</a></h3>


<h3 id="HELM_include_radiation">HELM_include_radiation <a href="#HELM_include_radiation" title="Permalink to this location">¶</a></h3>


<h3 id="HELM_always_skip_elec_pos">HELM_always_skip_elec_pos <a href="#HELM_always_skip_elec_pos" title="Permalink to this location">¶</a></h3>


<h3 id="HELM_always_include_elec_pos">HELM_always_include_elec_pos <a href="#HELM_always_include_elec_pos" title="Permalink to this location">¶</a></h3>


Flags for controlling parts of HELM.
If HELM skips electron-positron, it also skips coulomb.
Together, this reduces HELM to doing an ideal gas eos.
If you'd like to see what happens using an ideal gas for all cases, then
set these controls:

    set_other_HELM_flags = .true.
    HELM_always_skip_elec_pos = .true.
    HELM_always_include_elec_pos = .false.
    HELM_include_radiation = .true. or .false. depending on what you want
    set_HELM_OPAL_Zs = .true.
    Z_all_HELM = -0.1 ! switch to HELM for Z > this
    PC_min_Z = 1.1 ! don't use PC for Z < this

{% highlight fortran %}
set_other_HELM_flags = .false.
HELM_include_radiation = .true.
HELM_always_skip_elec_pos = .false.
HELM_always_include_elec_pos = .false.
{% endhighlight %}


<h3 id="eosDT_use_linear_interp_for_X">eosDT_use_linear_interp_for_X <a href="#eosDT_use_linear_interp_for_X" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
eosDT_use_linear_interp_for_X = .false.
{% endhighlight %}


<h3 id="eosDT_use_linear_interp_to_HELM">eosDT_use_linear_interp_to_HELM <a href="#eosDT_use_linear_interp_to_HELM" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
eosDT_use_linear_interp_to_HELM = .false.
{% endhighlight %}


<h3 id="eosDT2PTEH_use_linear_interp_for_X">eosDT2PTEH_use_linear_interp_for_X <a href="#eosDT2PTEH_use_linear_interp_for_X" title="Permalink to this location">¶</a></h3>


{% highlight fortran %}
eosDT2PTEH_use_linear_interp_for_X = .false.
{% endhighlight %}

<h1 id="nuclear_reactions">nuclear reactions <a href="#nuclear_reactions" title="Permalink to this location">¶</a></h1>


<h3 id="change_net">change_net <a href="#change_net" title="Permalink to this location">¶</a></h3>


<h3 id="new_net_name">new_net_name <a href="#new_net_name" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_net">change_initial_net <a href="#change_initial_net" title="Permalink to this location">¶</a></h3>


For switching reaction networks.
`new_net_name` only used if `change_net` if true.

{% highlight fortran %}
change_net = .false.
new_net_name = ''
change_initial_net = .false.
{% endhighlight %}


<h3 id="adjust_abundances_for_new_isos">adjust_abundances_for_new_isos <a href="#adjust_abundances_for_new_isos" title="Permalink to this location">¶</a></h3>


If false, new isos initial abundance set to 0.

{% highlight fortran %}
adjust_abundances_for_new_isos = .true.
{% endhighlight %}


<h3 id="set_rates_preference">set_rates_preference <a href="#set_rates_preference" title="Permalink to this location">¶</a></h3>


<h3 id="new_rates_preference">new_rates_preference <a href="#new_rates_preference" title="Permalink to this location">¶</a></h3>


+ 1 = NACRE rates
+ 2 = jina reaclib rates

{% highlight fortran %}
set_rates_preference = .false.
new_rates_preference = 2
{% endhighlight %}


<h3 id="set_rate_c12ag">set_rate_c12ag <a href="#set_rate_c12ag" title="Permalink to this location">¶</a></h3>


Empty string means ignore this control.
Can be one of:

+ 'NACRE'
+ 'jina reaclib'
+ 'Kunz'
+ 'CF88'

(note: our CF88 is larger than the original by a factor of 1.7)

{% highlight fortran %}
set_rate_c12ag = ''
{% endhighlight %}


<h3 id="set_rate_n14pg">set_rate_n14pg <a href="#set_rate_n14pg" title="Permalink to this location">¶</a></h3>


Empty string means ignore this control.
Can be one of

+ 'NACRE'
+ 'jina reaclib'
+ 'CF88'

{% highlight fortran %}
set_rate_n14pg = ''
{% endhighlight %}


<h3 id="set_rate_3a">set_rate_3a <a href="#set_rate_3a" title="Permalink to this location">¶</a></h3>


Empty string means ignore this control.
Can be one of

+ 'NACRE'
+ 'jina reaclib'
+ 'CF88'
+ 'FL87'

FL87 is Fushiki and Lamb, Apj, 317, 368-388, 1987
and includes both strong screening and pyconuclear

{% highlight fortran %}
set_rate_3a = ''
{% endhighlight %}


<h3 id="set_rate_1212">set_rate_1212 <a href="#set_rate_1212" title="Permalink to this location">¶</a></h3>


Empty string means ignore this control.
Can be one of:

+ `'CF88_basic_1212'` : the single rate approximation from CF88.
+ `'CF88_multi_1212'` : combines the rates for the n, p, and a channels.
c12(c12,n)mg23, c12(c12,p)na23, and c12(c12,a)ne20 and
uses neutron branching from dayras, switkowski, and woosley, 1976.

{% highlight fortran %}
set_rate_1212 = ''
{% endhighlight %}


Users can also provide tabulated rates for any of the reactions.
Tabulated rates automatically take priority over any other options for the reaction.
e.g., if you provide a rate table for c12ag, those rates will be used
if preference to the other options given in `set_rate_c12ag`.

To provide tabulated rates:
create a file of (T8, rate) pairs as in `data/rates_data/rate_tables`
You can give as many pairs as you want with any spacing in T8.
The first uncommented line of the file should be a number giving the
total number of (T8, rate) pairs in the subsequent lines.
The following lines are your specified values of T8 and rate separated
by a single space, one pair per line.
Add the filename to `rate_list.txt` along with the name of the rate you
want it to govern, either in `data/rates_data/rate_tables` or in a local
directory specified with the `rate_tables_dir` control.
Be aware that if you choose to put the modified `rate_list.txt` in
`data/rates_data/rate_tables` rather than a local directory,
your custom tabulated rate will override the rate for that reaction
for all future MESA runs.

If the reaction you wish to control does not already have a
name that MESA will recognize, you will also need to add it to
the file speficed by `net_reaction_filename` (defaults to reactions.list).  
The default version of this file is located
in `data/rates_data`.  If you place a modified copy of this file
in your work directory, it will take precedence.

<h3 id="num_special_rate_factors">num_special_rate_factors <a href="#num_special_rate_factors" title="Permalink to this location">¶</a></h3>


<h3 id="reaction_for_special_factor">reaction_for_special_factor <a href="#reaction_for_special_factor" title="Permalink to this location">¶</a></h3>


<h3 id="special_rate_factor">special_rate_factor <a href="#special_rate_factor" title="Permalink to this location">¶</a></h3>


For using other special rate factors.
`num_special_rate_factors` must be <= `max_num_special_rate_factors`.

{% highlight fortran %}
num_special_rate_factors = 0
reaction_for_special_factor(:) = ''
special_rate_factor(:) = 1
{% endhighlight %}


<h3 id="auto_extend_net">auto_extend_net <a href="#auto_extend_net" title="Permalink to this location">¶</a></h3>


<h3 id="h_he_net">h_he_net <a href="#h_he_net" title="Permalink to this location">¶</a></h3>


<h3 id="co_net">co_net <a href="#co_net" title="Permalink to this location">¶</a></h3>


<h3 id="adv_net">adv_net <a href="#adv_net" title="Permalink to this location">¶</a></h3>


If `auto_extend_net` true, then automatically extend the net as needed
from `h_he_net` to `co_net` and then to `adv_net`.

{% highlight fortran %}
auto_extend_net = .true.
h_he_net = 'basic.net'
co_net = 'co_burn.net'
adv_net = 'approx21.net'
{% endhighlight %}


<h3 id="enable_adaptive_network">enable_adaptive_network <a href="#enable_adaptive_network" title="Permalink to this location">¶</a></h3>


<h3 id="min_x_for_keep">min_x_for_keep <a href="#min_x_for_keep" title="Permalink to this location">¶</a></h3>


<h3 id="min_x_for_n">min_x_for_n <a href="#min_x_for_n" title="Permalink to this location">¶</a></h3>


<h3 id="min_x_for_add">min_x_for_add <a href="#min_x_for_add" title="Permalink to this location">¶</a></h3>


<h3 id="max_Z_for_add">max_Z_for_add <a href="#max_Z_for_add" title="Permalink to this location">¶</a></h3>


<h3 id="max_N_for_add">max_N_for_add <a href="#max_N_for_add" title="Permalink to this location">¶</a></h3>


<h3 id="max_A_for_add">max_A_for_add <a href="#max_A_for_add" title="Permalink to this location">¶</a></h3>


Heger-style adaptive network (Woosley, Heger, et al, ApJSS, 151:75-102, 2004).
If `enable_adaptive_network` is true, then
at each step, the system calculates a new set of isos according to the following rules:

    for each iso in the current net:
      let Z = number of protons in the iso and N = number of neutrons.
      let x = max mass fraction for the iso in any cell in the model.
      if x >= `min_x_for_keep` then include the iso in new net.
      if x >= `min_x_for_n` then include following related isos:
        (Z,N+1)   (Z,N-1)     -- add or remove neutron
      if x >= min_x_for_add then include following related isos:
        (Z+1,N)   (Z-1,N)     -- add or remove proton
        (Z+2,N+2) (Z-2,N-2)   -- add or remove alpha
        (Z+2,N+1) (Z-2,N-1)   -- exchange neutron/alpha
        (Z+1,N+2) (Z-1,N-2)   -- exchange proton/alpha
        (Z+1,N-1) (Z-1,N+1)   -- exchange proton/neutron
        (Z+4,N+4) (Z+3,N+4)   -- extend alpha chain

Isos in the previous net can be dropped if they have x < `min_x_for_keep` and
no other iso in the previous net causes them to be included in the new net.
The new net has the included isos and all relevant reactions.
The definition for the new net is saved to a text file in your local "nets" directory.
The file name is composed of the model number and the number of species.

{% highlight fortran %}
enable_adaptive_network = .false.
min_x_for_keep = 1d-5
min_x_for_n = 1d-4
min_x_for_add = 1d-4
max_Z_for_add = 999
max_N_for_add = 999
max_A_for_add = 999
{% endhighlight %}


<h3 id="net_reaction_filename">net_reaction_filename <a href="#net_reaction_filename" title="Permalink to this location">¶</a></h3>


Looks first in current directory, then in `mesa_data_dir/rates_data`.

{% highlight fortran %}
net_reaction_filename = 'reactions.list'
{% endhighlight %}


<h3 id="jina_reaclib_filename">jina_reaclib_filename <a href="#jina_reaclib_filename" title="Permalink to this location">¶</a></h3>


Empty string means use current standard version.
Which is defined in rates/public/rates_def.f90  as reaclib_filename
and is currently 'jina_reaclib_results_20171020_default'

Else give name of file in directory `mesa/data/rates_data`,
e.g., `jina_reaclib_results_20130213default2`
(which is an 18.8 MB file of rates data).
To use previous version, set to `jina_reaclib_results_v2.2`.

If you change reaclib version, you should clear the cache
after making the change in order to ensure that cached
rates from the default reaclib version are not being
read. (You can use the script `empty_caches` in
`$MESA_DIR`.)

In order to avoid this caching issue, one can also specify
a local rates cache directory via the control
`rates_cache_dir`.

{% highlight fortran %}
jina_reaclib_filename = ''
{% endhighlight %}


<h3 id="jina_reaclib_min_T9">jina_reaclib_min_T9 <a href="#jina_reaclib_min_T9" title="Permalink to this location">¶</a></h3>


set jina reaclib rates to zero for T9 <= this.
if this control is <= 0, then use the standard default from rates.
need <= 3d-3 for pre-ms li7 burning
if change this, must remove old cached rates from data/rates_data/cache

{% highlight fortran %}
jina_reaclib_min_T9 = -1
{% endhighlight %}


<h3 id="rate_tables_dir">rate_tables_dir <a href="#rate_tables_dir" title="Permalink to this location">¶</a></h3>


When MESA looks for the files `rate_list.txt` and `weak_rate_list.txt`,
it will look in a local directory with this name first.
If doesn't find one, it will use the one in `data/rates_data/rate_tables`.

{% highlight fortran %}
rate_tables_dir = 'rate_tables'
{% endhighlight %}


<h3 id="rate_cache_suffix">rate_cache_suffix <a href="#rate_cache_suffix" title="Permalink to this location">¶</a></h3>


If this not empty, then use it when creating names
for cache files for reaction rates from `rate_tables_dir`.
If empty, the suffix will be '0'.

{% highlight fortran %}
rate_cache_suffix = ''
{% endhighlight %}


<h3 id="T9_weaklib_full_off">T9_weaklib_full_off <a href="#T9_weaklib_full_off" title="Permalink to this location">¶</a></h3>


<h3 id="T9_weaklib_full_on">T9_weaklib_full_on <a href="#T9_weaklib_full_on" title="Permalink to this location">¶</a></h3>


Weak rates blend weaklib and reaclib according to temperature.
These can be used to overwrite the defaults in `mesa/rates/public/rates_def`

+ `T9_weaklib_full_off` : use pure reaclib for T <= this (ignore if <= 0)
+ `T9_weaklib_full_on` : use pure weaklib for T >= this (ignore if <= 0)

{% highlight fortran %}
T9_weaklib_full_off = 0.01d0
T9_weaklib_full_on = 0.02d0
{% endhighlight %}


<h3 id="weaklib_blend_hi_Z">weaklib_blend_hi_Z <a href="#weaklib_blend_hi_Z" title="Permalink to this location">¶</a></h3>


Ignore if <= 0.
Blend for intermediate temperatures.
For high Z elements, switch to reaclib at temp where no longer fully ionized.
As rough approximation for this, we switch at Fe to higher values of T9.

{% highlight fortran %}
weaklib_blend_hi_Z = 26
{% endhighlight %}


<h3 id="T9_weaklib_full_off_hi_Z">T9_weaklib_full_off_hi_Z <a href="#T9_weaklib_full_off_hi_Z" title="Permalink to this location">¶</a></h3>


<h3 id="T9_weaklib_full_on_hi_Z">T9_weaklib_full_on_hi_Z <a href="#T9_weaklib_full_on_hi_Z" title="Permalink to this location">¶</a></h3>


If input element has Z >= `weaklib_blend_hi_Z`, then use the following T9 limits:

+ `T9_weaklib_full_off_hi_Z` : use pure reaclib for T <= this (ignore if <= 0)
+ `T9_weaklib_full_on_hi_Z` : use pure weaklib for T >= this (ignore if <= 0)

{% highlight fortran %}
T9_weaklib_full_off_hi_Z = 0.063d0
T9_weaklib_full_on_hi_Z = 0.073d0
{% endhighlight %}


<h2 id="use_small_net_for_newton_iterations_only">use small net for newton iterations only <a href="#use_small_net_for_newton_iterations_only" title="Permalink to this location">¶</a></h2>


<h3 id="change_small_net">change_small_net <a href="#change_small_net" title="Permalink to this location">¶</a></h3>


<h3 id="new_small_net_name">new_small_net_name <a href="#new_small_net_name" title="Permalink to this location">¶</a></h3>


<h3 id="change_initial_small_net">change_initial_small_net <a href="#change_initial_small_net" title="Permalink to this location">¶</a></h3>


For switching reaction networks for use as small net in newton iterations.
small net is only used when also doing split mixing.
if `small_net_name` is empty string, then newton uses the standard net rather than the small one.
`new_small_net_name` only used if `change_small_net` if true.

{% highlight fortran %}
change_small_net = .false.
new_small_net_name = ''
change_initial_small_net = .false.
{% endhighlight %}


<h2 id="controls_for_other_weak_rate_sources">controls for other weak rate sources <a href="#controls_for_other_weak_rate_sources" title="Permalink to this location">¶</a></h2>


<h3 id="use_suzuki_weak_rates">use_suzuki_weak_rates <a href="#use_suzuki_weak_rates" title="Permalink to this location">¶</a></h3>


If this is true, use the A=17-28 weak reaction rates from

    Suzuki, Toki, and Nomoto (2016)
    Electron-capture and $\beta$-decay rates for sd-shell nuclei in stellar environments relevant to high-density O-Ne-Mg cores
    http://adsabs.harvard.edu/abs/2016ApJ...817..163S

If you make use of these rates, please cite the above paper.

{% highlight fortran %}
use_suzuki_weak_rates = .false.
{% endhighlight %}


<h3 id="use_special_weak_rates">use_special_weak_rates <a href="#use_special_weak_rates" title="Permalink to this location">¶</a></h3>


If this is true, calculate special weak rates using the
approach described in Section 8 of Paxton et al. (2015).

{% highlight fortran %}
use_special_weak_rates = .false.
{% endhighlight %}


<h3 id="special_weak_states_file">special_weak_states_file <a href="#special_weak_states_file" title="Permalink to this location">¶</a></h3>


File specifiying which states to include

Provide the low-lying energy levels of a given nucleus.
These are needed to calcuate the partition function
and to indicate which states have allowed transitions.
Each isotope should have an entry of the form

    <name> <nlevels>
    <E_1> <J_1>
    ...
    <E_n> <J_n>

where E = energy, J = spin.

{% highlight fortran %}
special_weak_states_file = 'special_weak_rates.states'
{% endhighlight %}


<h3 id="special_weak_transitions_file">special_weak_transitions_file <a href="#special_weak_transitions_file" title="Permalink to this location">¶</a></h3>


File specifying to include

These are the transitions for electron capture / beta decay
reactions that should be used.

Each reaction should have and entry of the form

    <iso1> <iso2> <ntrans>
    <si_1> <sf_1> <logft_1>
    ...
    <si_n> <sf_n> <logft_n>

where si / sf are the n-th parent / daughter state, counting
in the order that you specified in the states file.  logft is
the comparative half-life of that transition.

{% highlight fortran %}
special_weak_transitions_file = 'special_weak_rates.transitions'
{% endhighlight %}


<h3 id="ion_coulomb_corrections">ion_coulomb_corrections <a href="#ion_coulomb_corrections" title="Permalink to this location">¶</a></h3>


select which expression for the ion chemical potential to use
to calculate the energy shift associated with changing ion charge

+ 'none': no corrections
+ 'DGC1973': Dewitt, Graboske, & Cooper, M. S. 1973, ApJ, 181, 439
+ 'I1993': Ichimaru, 1993, Reviews of Modern Physics, 65, 255
+ 'PCR2009': Potekhin, Chabrier, & Rogers, 2009, Phys. Rev. E, 79, 016411

{% highlight fortran %}
ion_coulomb_corrections = 'none'
{% endhighlight %}


<h3 id="electron_coulomb_corrections">electron_coulomb_corrections <a href="#electron_coulomb_corrections" title="Permalink to this location">¶</a></h3>


select which expression to use to calculate the shift in the
electron chemical potential at the location of the nucleus

+ 'none': no corrections
+ 'ThomasFermi': Thomas-Fermi theory
+ 'Itoh2002': Itoh et al., 2002, ApJ, 579, 380

{% highlight fortran %}
electron_coulomb_corrections = 'none'
{% endhighlight %}

<h1 id="kap_controls">kap controls <a href="#kap_controls" title="Permalink to this location">¶</a></h1>


<h3 id="kappa_config_file">kappa_config_file <a href="#kappa_config_file" title="Permalink to this location">¶</a></h3>


Modify this to provide alternative set of X,Z tables
For Type1 high- and low-T opacities. This file is a namelist.
Leave blank to use the defaults.

{% highlight fortran %}
kappa_config_file = ''
{% endhighlight %}


<h3 id="kappa_file_prefix">kappa_file_prefix <a href="#kappa_file_prefix" title="Permalink to this location">¶</a></h3>


Modify this to select a different set of opacity tables.
alternatives:

+ `'gn93'`
+ `'gs98'`
+ `'a09'`
+ `'OP_gs98'`
+ `'OP_a09'`

{% highlight fortran %}
kappa_file_prefix = 'gs98'
{% endhighlight %}


<h3 id="kappa_lowT_prefix">kappa_lowT_prefix <a href="#kappa_lowT_prefix" title="Permalink to this location">¶</a></h3>


For lower temperatures.
alternatives:

traditional tables (X,Z)
+ `'lowT_Freedman11'`
+ `'lowT_fa05_gs98'`
+ `'lowT_fa05_gn93'`
+ `'lowT_fa05_a09p'`
+ `'lowT_af94_gn93'`

tables with additional composition dependence
+ `kapCN`
use tables from

    Lederer, M. T.; Aringer, B. (2009)
    Low temperature Rosseland opacities with varied abundances of carbon and nitrogen
    http://adsabs.harvard.edu/abs/2009A%26A...494..403L

these tables use the value of `Zbase` as the base metallicity

+ `AESOPUS`
use tables from AESOPUS

    Marigo, P.; Aringer, B. (2009)
    Low-temperature gas opacity. ÆSOPUS: a versatile and quick computational tool
    http://adsabs.harvard.edu/abs/2009A%26A...508.1539M

these tables use the value of `Zbase` as the base metallicity

the only provided tables have a limited coverage in Z [0.01, 0.04] and use GS98 abundances

you can generate your own tables with their web interface
http://stev.oapd.inaf.it/cgi-bin/aesopus
see kap/preprocessor/README_AESOPUS for information on preparing the tables for MESA

specify which file using `kappa_lowT_prefix`
to use provided tables set `kappa_lowT_prefix = 'AESOPUS_GS98'`
this will load the file `AESOPUS_GS98.h5`
the file is first looked for in the work directory
if not found, then data/kap_data is searched
the h5 suffix is assumed

to see more detail about the composition details of the tables
set `show_kap_info = .true.

{% highlight fortran %}
kappa_lowT_prefix = 'lowT_fa05_gs98'
{% endhighlight %}


<h3 id="kappa_blend_logT_upper_bdy">kappa_blend_logT_upper_bdy <a href="#kappa_blend_logT_upper_bdy" title="Permalink to this location">¶</a></h3>


<= 0 means use default.
Actual upper boundary will be min of this and max logT for lowT tables.
it is probably a good idea to keep the blend away from H ionization.
logT upper of about 3.9 or a bit less will do that.
older version had default of 4.1 for `kappa_blend_logT_upper_bdy`.

{% highlight fortran %}
kappa_blend_logT_upper_bdy = 3.88d0
{% endhighlight %}


<h3 id="kappa_blend_logT_lower_bdy">kappa_blend_logT_lower_bdy <a href="#kappa_blend_logT_lower_bdy" title="Permalink to this location">¶</a></h3>


<= 0 means use default
Actual lower boundary will be max of this and min logT for highT tables.
typical `logT_min` for tables is 3.75.  check your tables to be sure.
older version had default of 4.0 for `kappa_blend_logT_lower_bdy`.

{% highlight fortran %}
kappa_blend_logT_lower_bdy = 3.80d0
{% endhighlight %}


<h3 id="kappa_CO_prefix">kappa_CO_prefix <a href="#kappa_CO_prefix" title="Permalink to this location">¶</a></h3>


For C/O enhanced (Type 2 OPAL opacities).
alternatives:

+ 'gn93_co'
+ 'gs98_co'
+ 'a09_co'

{% highlight fortran %}
kappa_CO_prefix = 'gs98_co'
{% endhighlight %}


<h3 id="kappa_min_logRho">kappa_min_logRho <a href="#kappa_min_logRho" title="Permalink to this location">¶</a></h3>


>= 100 means use default in mesa/kap
otherwise if actual logRho < this, clip and set partial wrt logRho to zero 

{% highlight fortran %}
kappa_min_logRho = 1d99
{% endhighlight %}

<h1 id="ionization_controls">ionization controls <a href="#ionization_controls" title="Permalink to this location">¶</a></h1>


<h3 id="ionization_file_prefix">ionization_file_prefix <a href="#ionization_file_prefix" title="Permalink to this location">¶</a></h3>


<h3 id="ionization_Z1_suffix">ionization_Z1_suffix <a href="#ionization_Z1_suffix" title="Permalink to this location">¶</a></h3>


Prefix and suffix of ionization files.

{% highlight fortran %}
ionization_file_prefix = 'ion'
ionization_Z1_suffix = ''
{% endhighlight %}

<h1 id="extra_parameters">"extra" parameters <a href="#extra_parameters" title="Permalink to this location">¶</a></h1>


For use by your `run_star_extras` routines.

<h3 id="extras_lipar">extras_lipar <a href="#extras_lipar" title="Permalink to this location">¶</a></h3>


<h3 id="extras_ipar">extras_ipar <a href="#extras_ipar" title="Permalink to this location">¶</a></h3>


`extras_lipar` number of integer parameters in `extras_ipar`.
Must be <= `max_extras_params` (defined in `run_star_support`)

{% highlight fortran %}
extras_lipar = 0
extras_ipar(:) = 0
{% endhighlight %}


<h3 id="extras_lrpar">extras_lrpar <a href="#extras_lrpar" title="Permalink to this location">¶</a></h3>


<h3 id="extras_rpar">extras_rpar <a href="#extras_rpar" title="Permalink to this location">¶</a></h3>


`extras_lrpar` number of real(dp) parameters in `extras_rpar`.
Must be <= `max_extras_params` (defined in `run_star_support`)

{% highlight fortran %}
extras_lrpar = 0
extras_rpar(:) = 0d0
{% endhighlight %}


<h3 id="extras_lcpar">extras_lcpar <a href="#extras_lcpar" title="Permalink to this location">¶</a></h3>


<h3 id="extras_cpar">extras_cpar <a href="#extras_cpar" title="Permalink to this location">¶</a></h3>


`extras_lcpar` number of string parameters in `extras_cpar`.
Must be <= `max_extras_params` (defined in `run_star_support`).

{% highlight fortran %}
extras_lcpar = 0
extras_cpar(:) = ''
{% endhighlight %}


<h3 id="extras_llpar">extras_llpar <a href="#extras_llpar" title="Permalink to this location">¶</a></h3>


<h3 id="extras_lpar">extras_lpar <a href="#extras_lpar" title="Permalink to this location">¶</a></h3>


`extras_llpar`  number of logical parameters in `extras_lpar`.
Must be <= `max_extras_params` (defined in `run_star_support`).

{% highlight fortran %}
extras_llpar = 0
extras_lpar(:) = .false.
{% endhighlight %}

<h1 id="Color_Files">Color Files <a href="#Color_Files" title="Permalink to this location">¶</a></h1>


<h3 id="color_num_files">color_num_files <a href="#color_num_files" title="Permalink to this location">¶</a></h3>


<h3 id="color_file_names">color_file_names <a href="#color_file_names" title="Permalink to this location">¶</a></h3>


<h3 id="color_num_colors">color_num_colors <a href="#color_num_colors" title="Permalink to this location">¶</a></h3>


    Filenames for each bolometric correction (BC) table to load
    Must set the number of files to load
    Must be <= `max_num_color_files` (defined in `colors_def.f90`).
    Must set the number of BC's in each file (May be different for each file).
    Must be <= `max_num_bcs_per_file` (defined in `colors_def.f90`).
    Files should be structed as:
    Teff log_g M_div_h filter1 filter2 ....
    where filter1 is the name of the filter (No spaces allowed in name)
    Names must be unique accross all files loaded and are case sensitive.
    For a filter named filter1 history output will be bc_filter1 for bolometric corrections
    and abs_mag_filter1 for absolute magnitude

{% highlight fortran %}
color_num_files = -1
color_file_names(:) = ''
color_num_colors(:) = -1
{% endhighlight %}


Default file from Lejeune, Cuisinier, Buser (1998) A&AS 130, 65-75
Can be replaced if need be.
The filter names are U B V R I J H K L Lprime M (case senistive)

{% highlight fortran %}
color_num_files = 1
color_file_names(1) = 'lcb98cor.dat'
color_num_colors(1) = 11
{% endhighlight %}


Set of blackbody bolometric corrections in UBVRI
Can be used at the same time as the lcb98cor.dat file
Filter names bb_U bb_b bb_V bb_R bb_I
color_num_files=2
color_file_names(2)='blackbody_johnson.dat'
color_num_colors(2)=5
<h1 id="misc">misc <a href="#misc" title="Permalink to this location">¶</a></h1>


<h3 id="first_model_for_timing">first_model_for_timing <a href="#first_model_for_timing" title="Permalink to this location">¶</a></h3>


To get a breakdown of where the time is going
set `first_model_for_timing` to determine when the clocks start.
At the end of the run, there will be some output to the terminal showing times.

{% highlight fortran %}
first_model_for_timing = -1
{% endhighlight %}


<h3 id="set_max_dt_to_frac_lifetime">set_max_dt_to_frac_lifetime <a href="#set_max_dt_to_frac_lifetime" title="Permalink to this location">¶</a></h3>


<h3 id="max_frac_of_lifetime_per_step">max_frac_of_lifetime_per_step <a href="#max_frac_of_lifetime_per_step" title="Permalink to this location">¶</a></h3>


limit max timestep.
If true, set `max_timestep` and `max_years_for_timestep`
according to expected lifetime as a function of mass.
Use the Iben & Laughlin (1989) formula to estimate lifetime.
Multiply that times the value of `max_frac_of_lifetime_per_step` to get `max_timestep`.

{% highlight fortran %}
set_max_dt_to_frac_lifetime = .false.
max_frac_of_lifetime_per_step = -1
{% endhighlight %}


<h3 id="astero_just_call_my_extras_check_model">astero_just_call_my_extras_check_model <a href="#astero_just_call_my_extras_check_model" title="Permalink to this location">¶</a></h3>


Communications flag for astero and star.

{% highlight fortran %}
astero_just_call_my_extras_check_model = .false.
{% endhighlight %}


<h3 id="num_steps_for_garbage_collection">num_steps_for_garbage_collection <a href="#num_steps_for_garbage_collection" title="Permalink to this location">¶</a></h3>


If > 0 then every `num_steps_for_garbage_collection` steps we call the garbage collector
This will try to free some memory from data structures that are no longer needed but have
not been deallocated yet. There is no guarantee though that this will save memory and may
slow your code down with additional deallocations/allocations.

For now this primarily targets the EOS data structures.

{% highlight fortran %}
num_steps_for_garbage_collection = 1000
{% endhighlight %}


<h3 id="report_garbage_collection">report_garbage_collection <a href="#report_garbage_collection" title="Permalink to this location">¶</a></h3>


Whether to print debug information about the garbage collector, output is printed both
when mod(model_number,num_steps_for_garbage_collection)==0 and when 
mod(model_number-1,num_steps_for_garbage_collection)==0  (the next step)
only runs if `num_steps_for_garbage_collection` > 0

{% highlight fortran %}
report_garbage_collection = .false.
{% endhighlight %}

<h1 id="include_other_inlists">include other inlists <a href="#include_other_inlists" title="Permalink to this location">¶</a></h1>


You can split your `star_job` inlist into pieces using the following controls.
BTW: it works recursively, so the extras can read extras too.

<h3 id="read_extra_star_job_inlist15">read_extra_star_job_inlist{1..5} <a href="#read_extra_star_job_inlist15" title="Permalink to this location">¶</a></h3>


<h3 id="extra_star_job_inlist15_name">extra_star_job_inlist{1..5}_name <a href="#extra_star_job_inlist15_name" title="Permalink to this location">¶</a></h3>


if `read_extra_star_job_inlist{1..5}` is true,
then read &star_job from this namelist file

{% highlight fortran %}
read_extra_star_job_inlist1 = .false.
extra_star_job_inlist1_name = 'undefined'
read_extra_star_job_inlist2 = .false.
extra_star_job_inlist2_name = 'undefined'
read_extra_star_job_inlist3 = .false.
extra_star_job_inlist3_name = 'undefined'
read_extra_star_job_inlist4 = .false.
extra_star_job_inlist4_name = 'undefined'
read_extra_star_job_inlist5 = .false.
extra_star_job_inlist5_name = 'undefined'
{% endhighlight %}

<h1 id="private_or_experimental">private or experimental <a href="#private_or_experimental" title="Permalink to this location">¶</a></h1>


<h3 id="warn_run_star_extras">warn_run_star_extras <a href="#warn_run_star_extras" title="Permalink to this location">¶</a></h3>


Due to changing the `run_star_extras` functions to hooks, we break existing
`run_star_extras` files. This flag sets a warning message and stops the MESA run
until it is set to `.false.`.  This way people will hopefully not be
confused as to why their `run_star_extras` functions are not being called.

{% highlight fortran %}
warn_run_star_extras = .true.
{% endhighlight %}
