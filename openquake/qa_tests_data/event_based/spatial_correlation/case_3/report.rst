Probabilistic Event-Based QA Test with No Spatial Correlation, case 3
=====================================================================

============== ===================
checksum32     1,911,936,118      
date           2018-06-05T06:39:48
engine_version 3.2.0-git65c4735   
============== ===================

num_sites = 2, num_levels = 1

Parameters
----------
=============================== ==================
calculation_mode                'event_based'     
number_of_logic_tree_samples    0                 
maximum_distance                {'default': 200.0}
investigation_time              50.0              
ses_per_logic_tree_path         300               
truncation_level                None              
rupture_mesh_spacing            2.0               
complex_fault_mesh_spacing      2.0               
width_of_mfd_bin                0.1               
area_source_discretization      20.0              
ground_motion_correlation_model None              
minimum_intensity               {}                
random_seed                     42                
master_seed                     0                 
ses_seed                        123456789         
=============================== ==================

Input files
-----------
======================= ============================================================
Name                    File                                                        
======================= ============================================================
gsim_logic_tree         `gmpe_logic_tree.xml <gmpe_logic_tree.xml>`_                
job_ini                 `job.ini <job.ini>`_                                        
source                  `source_model.xml <source_model.xml>`_                      
source_model_logic_tree `source_model_logic_tree.xml <source_model_logic_tree.xml>`_
======================= ============================================================

Composite source model
----------------------
========= ======= =============== ================
smlt_path weight  gsim_logic_tree num_realizations
========= ======= =============== ================
b1        1.00000 trivial(1)      1/1             
========= ======= =============== ================

Required parameters per tectonic region type
--------------------------------------------
====== =================== ========= ========== ==========
grp_id gsims               distances siteparams ruptparams
====== =================== ========= ========== ==========
0      BooreAtkinson2008() rjb       vs30       mag rake  
====== =================== ========= ========== ==========

Realizations per (TRT, GSIM)
----------------------------

::

  <RlzsAssoc(size=1, rlzs=1)
  0,BooreAtkinson2008(): [0]>

Number of ruptures per tectonic region type
-------------------------------------------
================ ====== ==================== ============ ============
source_model     grp_id trt                  eff_ruptures tot_ruptures
================ ====== ==================== ============ ============
source_model.xml 0      Active Shallow Crust 1            1           
================ ====== ==================== ============ ============

Slowest sources
---------------
========= ============ ============ ========= ========== ========= ========= ======
source_id source_class num_ruptures calc_time split_time num_sites num_split events
========= ============ ============ ========= ========== ========= ========= ======
1         PointSource  1            0.04202   7.153E-06  2.00000   1         45,319
========= ============ ============ ========= ========== ========= ========= ======

Computation times by source typology
------------------------------------
============ ========= ======
source_class calc_time counts
============ ========= ======
PointSource  0.04202   1     
============ ========= ======

Duplicated sources
------------------
There are no duplicated sources

Information about the tasks
---------------------------
================== ======= ====== ======= ======= =========
operation-duration mean    stddev min     max     num_tasks
RtreeFilter        0.00146 NaN    0.00146 0.00146 1        
compute_ruptures   0.05050 NaN    0.05050 0.05050 1        
================== ======= ====== ======= ======= =========

Data transfer
-------------
================ ====================================================================== ========
task             sent                                                                   received
RtreeFilter      srcs=0 B srcfilter=0 B monitor=0 B                                     1.28 KB 
compute_ruptures sources=1.34 KB param=572 B monitor=353 B src_filter=233 B gsims=131 B 1.13 MB 
================ ====================================================================== ========

Slowest operations
------------------
=============================== ========= ========= ======
operation                       time_sec  memory_mb counts
=============================== ========= ========= ======
EventBasedRuptureCalculator.run 0.83267   1.20703   1     
managing sources                0.51435   1.14062   1     
saving ruptures                 0.23675   0.0       1     
setting event years             0.08681   0.02734   1     
total compute_ruptures          0.05050   8.58203   1     
store source_info               0.00512   0.0       1     
reading composite source model  0.00344   0.0       1     
unpickling compute_ruptures     0.00203   0.0       1     
total prefilter                 0.00146   0.0       1     
making contexts                 9.711E-04 0.0       1     
reading site collection         9.246E-04 0.0       1     
splitting sources               3.603E-04 0.0       1     
unpickling prefilter            3.192E-04 0.0       1     
=============================== ========= ========= ======