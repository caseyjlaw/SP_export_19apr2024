DSA-2000 Document No. 00021

DAT Requirements

Casey Law, Gregg Hallinan

Caltech

+-----------------------------------------------------------------------+
| +--------------------------------+--------------------------------+   |
| | Version:                       | 1                              |   |
| +--------------------------------+--------------------------------+   |
| | Version date:                  | 8/25/23                        |   |
| +--------------------------------+--------------------------------+   |
| | Original date:                 | 2023-08-25                     |   |
| +--------------------------------+--------------------------------+   |
| | Controlled document:           | No                             |   |
| +--------------------------------+--------------------------------+   |
| | WBS Level 2:                   | DAT--Data Management           |   |
| +--------------------------------+--------------------------------+   |
| | Document type:                 | REQ--Requirements              |   |
| |                                |                                |   |
| |                                | Requirements                   |   |
| +--------------------------------+--------------------------------+   |
+=======================================================================+
|                                                                       |
+-----------------------------------------------------------------------+

: Table 1. Requirements table

Revision History

  --------------------------------------------------------------------------------
  **Ver.**   **Date**     **Sections   **Reasons / Remarks** **Author(s)**
                          Affected**                         
  ---------- ------------ ------------ --------------------- ---------------------
  1          2023-08-25   All          Original              Casey Law

  --------------------------------------------------------------------------------

#   {#section .TOC-Heading}

# Table of Contents {#table-of-contents .TOC-Heading .unnumbered}

[1 Introduction [4](#introduction)](#introduction)

[2 Requirements [4](#requirements)](#requirements)

Abstract

We summarize the WBS L2 Data Management subsystem (DAT) requirements.
This includes performance of the post-processing system, size of on- and
off-site storage systems, performance of a metadata database, and
interfaces requirements.

# Introduction

The Data Management subsystem (DAT) is responsible for receiving data
from the Radio Camera Processor (RCP) and converting it into science
ready data products served to the public archive (ARC). DAT is composed
of a post-processing computing system, an on-site storage system, a
database to store metadata, and an off-site redundant data store.

The post-processing system is co-located with the RCP computing system
will run a set of pipelines on a compute cluster to generate the output
science-ready products. RCP and the post-processing system share a data
storage system and both have access to the metadata database. The
off-site storage system is in a physically distinct location to ensure
reliable backup. ARC holds and processes another off-site copy of a
subset of data products to be served to the public.

Here, we define the requirements for the DAT subsystem, as motivated by
the science requirements and science reference document.

# Requirements

+---------+-------+--------+------+------+--------+-------+----------+
| System  | Bas   | Ba     | Des  | Des  | Desi   | Desir | Science  |
| Requ    | eline | seline | cope | cope | rement | ement | Req      |
| irement |       | notes  |      | n    |        | notes | R        |
|         |       |        |      | otes |        |       | eference |
+=========+=======+========+======+======+========+=======+==========+
| Su      | R     | Rec    |      |      |        |       | S        |
| stained | ecord | eiving |      |      |        |       | cR-0013, |
| re      | \>98% | h      |      |      |        |       | S        |
| ceiving | of    | appens |      |      |        |       | cR-0026, |
| of      | 14290 | within |      |      |        |       |          |
| output  | image | RCP    |      |      |        |       | S        |
| of RCP  | cha   | node   |      |      |        |       | cR-0027, |
|         | nnels | in     |      |      |        |       |          |
|         | per   | bas    |      |      |        |       | ScR-0028 |
|         | 10.3  | eline. |      |      |        |       |          |
|         | min = |        |      |      |        |       |          |
|         | 23    |        |      |      |        |       |          |
|         | GB/s  |        |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| Dist    | Save  | DAT    |      |      |        |       | S        |
| ributed | 3     | proc   |      |      |        |       | cR-0013, |
| storage | days  | essing |      |      |        |       | S        |
| on RCP  | of    | before |      |      |        |       | cR-0026, |
| nodes   | field | mosa   |      |      |        |       | S        |
|         | i     | icking |      |      |        |       | cR-0027, |
|         | mages | re     |      |      |        |       | ScR-0028 |
|         | on    | quires |      |      |        |       |          |
|         | RCP   | some   |      |      |        |       |          |
|         | node  | l      |      |      |        |       |          |
|         |       | atency |      |      |        |       |          |
|         |       | and    |      |      |        |       |          |
|         |       | tol    |      |      |        |       |          |
|         |       | erance |      |      |        |       |          |
|         |       | to     |      |      |        |       |          |
|         |       | field  |      |      |        |       |          |
|         |       | -based |      |      |        |       |          |
|         |       | failu  |      |      |        |       |          |
|         |       | res/re |      |      |        |       |          |
|         |       | observ |      |      |        |       |          |
|         |       | ations |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| On-site | 2.8   | Centr  |      |      |        |       | S        |
| storage | GB/s  | alized |      |      |        |       | cR-0002, |
| system  | write | s      |      |      |        |       | ScR-0014 |
| rea     | and   | torage |      |      |        |       |          |
| d/write | read  | can    |      |      |        |       |          |
| speed   | simul | r      |      |      |        |       |          |
|         | taneo | eceive |      |      |        |       |          |
|         | usly. | comp   |      |      |        |       |          |
|         |       | ressed |      |      |        |       |          |
|         |       | m      |      |      |        |       |          |
|         |       | osaics |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| On-site | 30 PB | Able   |      |      |        |       | S        |
| cent    |       | to     |      |      |        |       | cR-0014, |
| ralized |       | hold a |      |      |        |       | S        |
| storage |       | 4      |      |      |        |       | cR-0015, |
| system  |       | -month |      |      |        |       | S        |
| size    |       | epoch  |      |      |        |       | cR-0026, |
|         |       | of     |      |      |        |       |          |
|         |       | comp   |      |      |        |       | S        |
|         |       | ressed |      |      |        |       | cR-0027, |
|         |       | m      |      |      |        |       |          |
|         |       | osaics |      |      |        |       | ScR-0028 |
|         |       | for    |      |      |        |       |          |
|         |       | all    |      |      |        |       |          |
|         |       | cha    |      |      |        |       |          |
|         |       | nnels. |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| O       | 30 PB | Able   |      |      |        |       | S        |
| ff-site |       | to     |      |      |        |       | cR-0014, |
| storage |       | hold a |      |      |        |       | S        |
| system  |       | 4      |      |      |        |       | cR-0015, |
| size    |       | -month |      |      |        |       | S        |
|         |       | epoch  |      |      |        |       | cR-0026, |
|         |       | of     |      |      |        |       |          |
|         |       | comp   |      |      |        |       | S        |
|         |       | ressed |      |      |        |       | cR-0027, |
|         |       | m      |      |      |        |       |          |
|         |       | osaics |      |      |        |       | ScR-0028 |
|         |       | for    |      |      |        |       |          |
|         |       | all    |      |      |        |       |          |
|         |       | cha    |      |      |        |       |          |
|         |       | nnels. |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| P       | For   | Str    |      |      |        |       | S        |
| ost-pro | reco  | eaming |      |      |        |       | cR-0008, |
| cessing | rding | pos    |      |      |        |       | S        |
| cluster | rate  | t-proc |      |      |        |       | cR-0011, |
| no      | of    | essing |      |      |        |       | S        |
| de/core | 2.8   | 5x     |      |      |        |       | cR-0013, |
| count   | GB/s, | faster |      |      |        |       | S        |
|         | 5\*2  | than a |      |      |        |       | cR-0017, |
|         | .8=14 | r      |      |      |        |       |          |
|         | nodes | ate-li |      |      |        |       | S        |
|         | req   | miting |      |      |        |       | cR-0018, |
|         | uired | step   |      |      |        |       |          |
|         | for   | of 1   |      |      |        |       | S        |
|         | s     | GB/s   |      |      |        |       | cR-0019, |
|         | tream |        |      |      |        |       |          |
|         | proce |        |      |      |        |       | S        |
|         | ssing |        |      |      |        |       | cR-0020, |
|         |       |        |      |      |        |       |          |
|         |       |        |      |      |        |       | S        |
|         |       |        |      |      |        |       | cR-0021, |
|         |       |        |      |      |        |       |          |
|         |       |        |      |      |        |       | S        |
|         |       |        |      |      |        |       | cR-0022, |
|         |       |        |      |      |        |       |          |
|         |       |        |      |      |        |       | S        |
|         |       |        |      |      |        |       | cR-0023, |
|         |       |        |      |      |        |       | ScR-0024 |
+---------+-------+--------+------+------+--------+-------+----------+
| P       | Rea   | For    |      |      |        |       | S        |
| ost-pro | d/pro | st     |      |      |        |       | cR-0008, |
| cessing | cess/ | acking |      |      |        |       | S        |
| server  | write | and    |      |      |        |       | cR-0011, |
| memory  | 2x2.2 | source |      |      |        |       | S        |
|         | GB    | de     |      |      |        |       | cR-0013, |
|         | /mosa | tectio |      |      |        |       | S        |
|         | ic-ch | n/extr |      |      |        |       | cR-0017, |
|         | annel | action |      |      |        |       |          |
|         |       |        |      |      |        |       | S        |
|         |       |        |      |      |        |       | cR-0018, |
|         |       |        |      |      |        |       |          |
|         |       |        |      |      |        |       | S        |
|         |       |        |      |      |        |       | cR-0019, |
|         |       |        |      |      |        |       |          |
|         |       |        |      |      |        |       | S        |
|         |       |        |      |      |        |       | cR-0020, |
|         |       |        |      |      |        |       |          |
|         |       |        |      |      |        |       | S        |
|         |       |        |      |      |        |       | cR-0021, |
|         |       |        |      |      |        |       |          |
|         |       |        |      |      |        |       | S        |
|         |       |        |      |      |        |       | cR-0022, |
|         |       |        |      |      |        |       |          |
|         |       |        |      |      |        |       | S        |
|         |       |        |      |      |        |       | cR-0023, |
|         |       |        |      |      |        |       | ScR-0024 |
+---------+-------+--------+------+------+--------+-------+----------+
| Data    | 3     | Number |      |      |        |       | S        |
| state   | Gi    | of     |      |      |        |       | cR-0013, |
| d       | garow | image  |      |      |        |       |          |
| atabase | data  | cha    |      |      |        |       | ScR-0014 |
| speed,  | base, | n-pols |      |      |        |       |          |
| relia   | \>99% | plus   |      |      |        |       |          |
| bility, | up    | other  |      |      |        |       |          |
| and     | time, | o      |      |      |        |       |          |
| size    | peak  | utputs |      |      |        |       |          |
|         | write |        |      |      |        |       |          |
|         | rate  |        |      |      |        |       |          |
|         | of    |        |      |      |        |       |          |
|         | 1000  |        |      |      |        |       |          |
|         | r     |        |      |      |        |       |          |
|         | ows/s |        |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| Ast     | ScR   |        | ScR- |      |        |       | S        |
| rometri | -0008 |        | 0008 |      |        |       | cR-0001, |
| cally-c | req   |        | requ |      |        |       |          |
| orrect, | uires |        | ires |      |        |       | S        |
| artifa  | 95%   |        | 90%  |      |        |       | cR-0008, |
| ct-free | sky   |        | sky  |      |        |       |          |
| mos     | co    |        | cov  |      |        |       | S        |
| aicking | vered |        | ered |      |        |       | cR-0023, |
| of      | w     |        | wi   |      |        |       |          |
| images  | ithin |        | thin |      |        |       | ScR-0024 |
|         | 1.1x  |        | 1.1x |      |        |       |          |
|         | th    |        | the  |      |        |       |          |
|         | ermal |        | rmal |      |        |       |          |
|         | noise |        | n    |      |        |       |          |
|         | limit |        | oise |      |        |       |          |
|         |       |        | l    |      |        |       |          |
|         |       |        | imit |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| Bright  | Dec   |        |      |      | D      |       | ScR-0001 |
| source  | onvol |        |      |      | econvo |       |          |
| si      | ution |        |      |      | lution |       |          |
| delobes | of    |        |      |      | of     |       |          |
| below   | S     |        |      |      | Stokes |       |          |
| noise   | tokes |        |      |      | I MP   |       |          |
| in      | I MP  |        |      |      | and NL |       |          |
| ind     | i     |        |      |      | images |       |          |
| ividual | mages |        |      |      |        |       |          |
| channel |       |        |      |      |        |       |          |
| images  |       |        |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| Ast     | ScR   |        | ScR- |      |        |       | S        |
| rometri | -0008 |        | 0008 |      |        |       | cR-0001, |
| cally-c | req   |        | requ |      |        |       |          |
| orrect, | uires |        | ires |      |        |       | S        |
| artifa  | 95%   |        | 90%  |      |        |       | cR-0008, |
| ct-free | sky   |        | sky  |      |        |       |          |
| s       | co    |        | cov  |      |        |       | S        |
| tacking | vered |        | ered |      |        |       | cR-0023, |
| of      | w     |        | wi   |      |        |       |          |
| images  | ithin |        | thin |      |        |       | ScR-0024 |
|         | 1.1x  |        | 1.1x |      |        |       |          |
|         | th    |        | the  |      |        |       |          |
|         | ermal |        | rmal |      |        |       |          |
|         | noise |        | n    |      |        |       |          |
|         | limit |        | oise |      |        |       |          |
|         |       |        | l    |      |        |       |          |
|         |       |        | imit |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| Slow    | Fewer |        |      |      | Deep,  |       | S        |
| radio   | rel   |        |      |      | first  |       | cR-0005, |
| tr      | eases |        |      |      | epoch  |       |          |
| ansient | or no |        |      |      | will   |       | S        |
| di      | sp    |        |      |      | be     |       | cR-0014, |
| scovery | ecial |        |      |      | used   |       |          |
|         | trea  |        |      |      | in     |       | ScR-0015 |
|         | tment |        |      |      | quic   |       |          |
|         | for   |        |      |      | k-look |       |          |
|         | tran  |        |      |      | image  |       |          |
|         | sient |        |      |      | subtr  |       |          |
|         | iden  |        |      |      | action |       |          |
|         | tific |        |      |      | alg    |       |          |
|         | ation |        |      |      | orithm |       |          |
|         | ou    |        |      |      | via    |       |          |
|         | tside |        |      |      | o      |       |          |
|         | of 3  |        |      |      | n-site |       |          |
|         | p     |        |      |      | pip    |       |          |
|         | ublic |        |      |      | eline. |       |          |
|         | data  |        |      |      | Pr     |       |          |
|         | rel   |        |      |      | eserve |       |          |
|         | eases |        |      |      | Stokes |       |          |
|         |       |        |      |      | I      |       |          |
|         |       |        |      |      | field  |       |          |
|         |       |        |      |      | images |       |          |
|         |       |        |      |      | for    |       |          |
|         |       |        |      |      | intra  |       |          |
|         |       |        |      |      | -field |       |          |
|         |       |        |      |      | tra    |       |          |
|         |       |        |      |      | nsient |       |          |
|         |       |        |      |      | dete   |       |          |
|         |       |        |      |      | ction. |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| Ext     | 1e7   | Using  |      |      | Detect | Big   | ScR-0035 |
| raction | gal   | a      |      |      | HI on  | c     |          |
| of HI   | axies | priori |      |      | full,  | hange |          |
| image   | cov   | c      |      |      | s      | in    |          |
| cubes   | ering | atalog |      |      | tacked | st    |          |
| from    | 1     | of     |      |      | m      | orage |          |
| stacks  | 0,000 | s      |      |      | osaics | v     |          |
|         | sp    | ources |      |      |        | olume |          |
|         | axels |        |      |      |        | to    |          |
|         | each  |        |      |      |        | find  |          |
|         |       |        |      |      |        | "     |          |
|         |       |        |      |      |        | dark" |          |
|         |       |        |      |      |        | HI    |          |
|         |       |        |      |      |        | so    |          |
|         |       |        |      |      |        | urces |          |
+---------+-------+--------+------+------+--------+-------+----------+
| Ext     | 1e7   | 20     | 1x1  |      | Ex     |       | S        |
| raction | so    | m      |      |      | tended |       | cR-0033, |
| of      | urces | icroJy |      |      | source |       |          |
| po      | cov   | Stokes |      |      | det    |       | ScR-0034 |
| larized | ering | I      |      |      | ection |       |          |
| image   | 3x    |        |      |      | and    |       |          |
| cubes   | 3x605 |        |      |      | extr   |       |          |
| from    | p     |        |      |      | action |       |          |
| image   | oxels |        |      |      |        |       |          |
| stacks  |       |        |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| Fiber   | 100   |        | No   |      | 1 Gb/s |       | S        |
| ba      | Mb/s  |        | f    |      | a      |       | cR-0014, |
| ndwidth | av    |        | iber |      | verage |       | S        |
| from    | erage |        | b    |      |        |       | cR-0015, |
| site to |       |        | ackh |      |        |       | S        |
| o       |       |        | aul; |      |        |       | cR-0026, |
| ff-site |       |        | d    |      |        |       |          |
| data    |       |        | isks |      |        |       | S        |
| store   |       |        | shi  |      |        |       | cR-0027, |
|         |       |        | pped |      |        |       |          |
|         |       |        | off  |      |        |       | ScR-0028 |
|         |       |        | site |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| PSF     | PSF   | PSF    | One  |      | PSF    |       | S        |
| calc    | calcu | should | PSF  |      | calc   |       | cR-0033, |
| ulation | lated | id     | per  |      | ulable |       |          |
| for     | and   | entify | f    |      | on     |       | S        |
| s       | pro   | sid    | ield |      | demand |       | cR-0034, |
| idelobe | vided | elobes |      |      | at any |       |          |
| identif | at    | of 100 |      |      | point  |       | ScR-0035 |
| ication | fixed | mJy    |      |      | in     |       |          |
| in      | grid  | s      |      |      | field  |       |          |
| public  | of    | ources |      |      | or     |       |          |
| archive | p     | that   |      |      | mosaic |       |          |
| pro     | oints | are    |      |      | image  |       |          |
| cessing | in    | \>     |      |      |        |       |          |
|         | m     | 5sigma |      |      |        |       |          |
|         | osaic | in     |      |      |        |       |          |
|         |       | Stokes |      |      |        |       |          |
|         |       | I      |      |      |        |       |          |
|         |       | con    |      |      |        |       |          |
|         |       | tinuum |      |      |        |       |          |
|         |       | image  |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
| Scales  | PSF,  |        |      |      |        |       | ScR-0031 |
| for     | 10",  |        |      |      |        |       |          |
| source  | 30",  |        |      |      |        |       |          |
| r       | 1',   |        |      |      |        |       |          |
| ecovery | 3',   |        |      |      |        |       |          |
| (via    | 10'   |        |      |      |        |       |          |
| conv    |       |        |      |      |        |       |          |
| olution |       |        |      |      |        |       |          |
| in the  |       |        |      |      |        |       |          |
| image   |       |        |      |      |        |       |          |
| plane)  |       |        |      |      |        |       |          |
+---------+-------+--------+------+------+--------+-------+----------+
