Scenario Risk Maule Mw 8.8 reduced
==================================

============== ===================
checksum32     3,260,969,674      
date           2018-06-05T06:40:08
engine_version 3.2.0-git65c4735   
============== ===================

num_sites = 29, num_levels = 78

Parameters
----------
=============================== ===============
calculation_mode                'scenario_risk'
number_of_logic_tree_samples    0              
maximum_distance                None           
investigation_time              None           
ses_per_logic_tree_path         1              
truncation_level                None           
rupture_mesh_spacing            None           
complex_fault_mesh_spacing      None           
width_of_mfd_bin                None           
area_source_discretization      None           
ground_motion_correlation_model None           
minimum_intensity               {}             
random_seed                     113            
master_seed                     0              
ses_seed                        42             
avg_losses                      True           
=============================== ===============

Input files
-----------
======================== ==================================================================================
Name                     File                                                                              
======================== ==================================================================================
exposure                 `exposure_model.xml <exposure_model.xml>`_                                        
gmfs                     `GMFs_Mabe.xml <GMFs_Mabe.xml>`_                                                  
job_ini                  `job.ini <job.ini>`_                                                              
occupants_vulnerability  `occupants_vulnerabilityRes.xml <occupants_vulnerabilityRes.xml>`_                
structural_vulnerability `structural_vulnerability_model_Res.xml <structural_vulnerability_model_Res.xml>`_
======================== ==================================================================================

Composite source model
----------------------
========= ======= =============== ================
smlt_path weight  gsim_logic_tree num_realizations
========= ======= =============== ================
b_1       1.00000 trivial(1)      1/1             
========= ======= =============== ================

Realizations per (TRT, GSIM)
----------------------------

::

  <RlzsAssoc(size=1, rlzs=1)
  0,FromFile: [0]>

Exposure model
--------------
=============== ========
#assets         56      
#taxonomies     31      
deductibile     absolute
insurance_limit absolute
=============== ========

============= ======= ======= === === ========= ==========
taxonomy      mean    stddev  min max num_sites num_assets
LWAL_H1       1.00000 0.0     1   1   2         2         
LWAL_H8       1.00000 NaN     1   1   1         1         
W+WLI_H1      1.00000 0.0     1   1   3         3         
MR_H2_DNO     1.00000 0.0     1   1   3         3         
MR_H1_DNO     1.00000 0.0     1   1   3         3         
CR+PC_LWAL_H1 1.00000 0.0     1   1   2         2         
LWAL_H1_DNO   1.00000 0.0     1   1   2         2         
MCF_H2        1.00000 NaN     1   1   1         1         
MR_H3_DNO     1.00000 0.0     1   1   2         2         
MCF_H3        1.00000 0.0     1   1   3         3         
LWAL_H2       2.00000 NaN     2   2   1         2         
LWAL_H2_DNO   1.00000 NaN     1   1   1         1         
LWAL_H7       1.00000 0.0     1   1   2         2         
MCF_H1        1.00000 0.0     1   1   2         2         
MR_H1         1.00000 0.0     1   1   3         3         
MUR+ADO_H1    1.00000 NaN     1   1   1         1         
MUR_H2        1.00000 0.0     1   1   4         4         
LWAL_H5       1.50000 0.70711 1   2   2         3         
MCF_H2_DNO    1.00000 NaN     1   1   1         1         
UNK           1.00000 0.0     1   1   2         2         
LWAL_H6       1.00000 NaN     1   1   1         1         
W+WS          1.00000 0.0     1   1   2         2         
CR+PC_LWAL_H2 1.00000 NaN     1   1   1         1         
MCF_H3_DNO    1.00000 NaN     1   1   1         1         
MUR_H3        1.00000 0.0     1   1   2         2         
MUR+ST_H1     1.00000 NaN     1   1   1         1         
CR+PC_LWAL_H3 1.00000 NaN     1   1   1         1         
ER+ETR_H2     1.00000 NaN     1   1   1         1         
MUR_H1        1.00000 NaN     1   1   1         1         
MUR+ADO_H2    1.00000 NaN     1   1   1         1         
W+WLI_H2      1.00000 NaN     1   1   1         1         
*ALL*         0.21705 0.74292 0   6   258       56        
============= ======= ======= === === ========= ==========

Slowest operations
------------------
======================= ======== ========= ======
operation               time_sec memory_mb counts
======================= ======== ========= ======
building riskinputs     0.08404  0.0       1     
reading site collection 0.06329  0.0       1     
reading exposure        0.00914  0.0       1     
building epsilons       0.00251  0.0       1     
======================= ======== ========= ======