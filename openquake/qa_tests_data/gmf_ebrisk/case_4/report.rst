event based two source models
=============================

============== ===================
checksum32     2,633,907,336      
date           2018-06-05T06:39:34
engine_version 3.2.0-git65c4735   
============== ===================

num_sites = 1, num_levels = 11

Parameters
----------
=============================== ==================
calculation_mode                'event_based'     
number_of_logic_tree_samples    0                 
maximum_distance                {'default': 200.0}
investigation_time              1.0               
ses_per_logic_tree_path         2                 
truncation_level                3.0               
rupture_mesh_spacing            2.0               
complex_fault_mesh_spacing      2.0               
width_of_mfd_bin                0.1               
area_source_discretization      10.0              
ground_motion_correlation_model 'JB2009'          
minimum_intensity               {}                
random_seed                     24                
master_seed                     0                 
ses_seed                        42                
=============================== ==================

Input files
-----------
======================== ==========================================================================
Name                     File                                                                      
======================== ==========================================================================
exposure                 `exposure_model.xml <exposure_model.xml>`_                                
gsim_logic_tree          `gsim_logic_tree.xml <gsim_logic_tree.xml>`_                              
job_ini                  `job_haz.ini <job_haz.ini>`_                                              
source                   `source_model_1.xml <source_model_1.xml>`_                                
source                   `source_model_2.xml <source_model_2.xml>`_                                
source_model_logic_tree  `source_model_logic_tree.xml <source_model_logic_tree.xml>`_              
structural_vulnerability `structural_vulnerability_model.xml <structural_vulnerability_model.xml>`_
======================== ==========================================================================

Composite source model
----------------------
========= ======= =============== ================
smlt_path weight  gsim_logic_tree num_realizations
========= ======= =============== ================
b1        0.25000 trivial(1,1)    1/1             
b2        0.75000 trivial(1,1)    1/1             
========= ======= =============== ================

Required parameters per tectonic region type
--------------------------------------------
====== =================== ========= ========== ==========
grp_id gsims               distances siteparams ruptparams
====== =================== ========= ========== ==========
0      BooreAtkinson2008() rjb       vs30       mag rake  
1      AkkarBommer2010()   rjb       vs30       mag rake  
2      BooreAtkinson2008() rjb       vs30       mag rake  
3      AkkarBommer2010()   rjb       vs30       mag rake  
====== =================== ========= ========== ==========

Realizations per (TRT, GSIM)
----------------------------

::

  <RlzsAssoc(size=4, rlzs=2)
  0,BooreAtkinson2008(): [0]
  1,AkkarBommer2010(): [0]
  2,BooreAtkinson2008(): [1]
  3,AkkarBommer2010(): [1]>

Number of ruptures per tectonic region type
-------------------------------------------
================== ====== ==================== ============ ============
source_model       grp_id trt                  eff_ruptures tot_ruptures
================== ====== ==================== ============ ============
source_model_1.xml 0      Active Shallow Crust 482          482         
source_model_1.xml 1      Stable Shallow Crust 4            4           
source_model_2.xml 2      Active Shallow Crust 482          482         
source_model_2.xml 3      Stable Shallow Crust 1            1           
================== ====== ==================== ============ ============

============= ===
#TRT models   4  
#eff_ruptures 969
#tot_ruptures 969
#tot_weight   0  
============= ===

Exposure model
--------------
=============== ========
#assets         1       
#taxonomies     1       
deductibile     absolute
insurance_limit absolute
=============== ========

======== ======= ====== === === ========= ==========
taxonomy mean    stddev min max num_sites num_assets
tax1     1.00000 NaN    1   1   1         1         
======== ======= ====== === === ========= ==========

Slowest sources
---------------
========= ========================= ============ ========= ========== ========= ========= ======
source_id source_class              num_ruptures calc_time split_time num_sites num_split events
========= ========================= ============ ========= ========== ========= ========= ======
1         SimpleFaultSource         482          0.41282   1.690E-04  1.00000   30        1     
2         CharacteristicFaultSource 1            0.00841   2.384E-06  1.00000   2         2     
========= ========================= ============ ========= ========== ========= ========= ======

Computation times by source typology
------------------------------------
========================= ========= ======
source_class              calc_time counts
========================= ========= ======
CharacteristicFaultSource 0.00841   1     
SimpleFaultSource         0.41282   1     
========================= ========= ======

Duplicated sources
------------------
There are no duplicated sources

Information about the tasks
---------------------------
================== ======= ======= ======= ======= =========
operation-duration mean    stddev  min     max     num_tasks
RtreeFilter        0.00574 0.00290 0.00131 0.01362 32       
compute_ruptures   0.03817 0.01666 0.00863 0.05955 14       
================== ======= ======= ======= ======= =========

Data transfer
-------------
================ ============================================================================ ========
task             sent                                                                         received
RtreeFilter      srcs=50.76 KB monitor=10.81 KB srcfilter=8.72 KB                             52.05 KB
compute_ruptures sources=39.54 KB param=9 KB monitor=4.83 KB src_filter=3.19 KB gsims=1.78 KB 7.84 KB 
================ ============================================================================ ========

Slowest operations
------------------
=============================== ========= ========= ======
operation                       time_sec  memory_mb counts
=============================== ========= ========= ======
EventBasedRuptureCalculator.run 0.59498   0.0       1     
total compute_ruptures          0.53443   8.66016   14    
managing sources                0.34606   0.0       1     
total prefilter                 0.18377   5.19141   32    
reading composite source model  0.02436   0.0       1     
saving ruptures                 0.01375   0.0       14    
unpickling prefilter            0.01272   0.0       32    
store source_info               0.00578   0.0       1     
making contexts                 0.00507   0.0       2     
unpickling compute_ruptures     0.00488   0.0       14    
reading site collection         0.00180   0.0       1     
setting event years             0.00147   0.0       1     
reading exposure                0.00129   0.0       1     
splitting sources               7.610E-04 0.0       1     
=============================== ========= ========= ======