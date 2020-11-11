README file for

Allocations Awards and Usage for the NSF Cyberfrastructure Portfolio, 2004-2019


This data set comprises two comma-separated values (CSV) files. This document describes and defines the fields in each file.

=======================================================================

VERSION 2.0 -- The data set encompasses projects and allocations with an end date of 31 December 2019 or earlier.

v2.0 checksums -- calculated via: shasum -a 1
	* allocation_award_history -- a4784d1560c2ce1f6278739dae65cc9f8583a9cc
	* allocation_usage_history -- bf95742cc71e54b5fdaab912fc54c53697c89a82

=======================================================================

allocation_award_history_2004-2019.csv 

This file includes information about the project awards made. Each row in the file represents a project award for a particular start date; each award may encompass multiple resource allocations.

** Proposal_Number -- The identifier associated with the allocation request in the submission system. Early in the period covered by the data, roughly up to 2008, it was possible for a single proposal to spawn two projects (with two grant numbers). Since 2008, most proposals have spawned a single project and the proposal number is the same as the grant number. Some older projects may not have a Proposal_Number.

* Grant_Number -- The grant number is the identifier for a project that remains constant over time, even as the project spans multiple allocation periods, as the nature of the work (described in the abstract) changes, or as principal investigators change over time. The Grant_Number is the value that should be used for connecting data across the two files. 

The Grant Number is an abbreviation of the project's Field of Science Division (see below), or Field of Science Directorate abbreviation if the directorate-level field of science was selected, followed by the two-digit year and four-digit serial number within the FOS abbreviation.

* PI_ID -- The MD5 hash of an internal ID field for the PI. Provided as a convenient way to uniquely identify a PI. 

* PI_First_Name, PI_Last_Name -- The first and last name for the project's principal investigator (PI) for the allocation award.

* Organization -- The organizational affiliation for the project PI.

* Field of Science, Field of Science Division, Field of Science Directorate -- The field of science (FOS) is described in three fields. The FOS values are selected by the users at time of submission and chosen from a controlled vocabulary organized into a three-level hierarchy. Field of Science is the lowest level of the hierarchy with the finest granularity. Related Fields of Science are grouped into a Field of Science Division, and related Field of Science Divisions are grouped into a Field of Science Directorate. The FOS hierarchy is based on a programmatic structure at the National Science Foundation from the late 1990s. Because projects may persist for many years, the field of science associated with a given project may change over time as different submitters choose different fields of science for a given submission.

* Project Type -- The type of project applied for, defined by the allocation policies at the time of the award. For some older projects, this value was not recorded in the accounting system and may be blank.

	* Campus Champions -- Projects awarded as part of the TeraGrid and XSEDE Campus Champions programs. Only designated Campus Champions could request such projects.
	* DAC -- The various types of Development Allocations Committee (DAC) projects were typically associated with the resources of a single resource provider or resource. These were later superseded by the portfolio-wide "Startup" project type.
	* Discretionary -- Awards made at the discretion of a resource provider. Only users invited by the resource provider could submit such awards. Discretionary awards were not required to be submitted centrally, so not all discretionary activity is captured by the awards in this data set.
	* Educational -- Awards made for classroom, training, or similar educational purposes.
	* LRAC, MRAC, TRAC, XRAC, Research -- All of these types represent projects reviewed by a volunteer Resource Allocation Committee (RAC) of computational experts. Large (LRAC) and Medium (MRAC) projects were considered during the NSF Partnerships for Advance Computational Infrastructure (PACI) program, TeraGrid (TRAC) projects were considered during the TeraGrid program, and XSEDE (XRAC) and Research projects were considered during the XSEDE program.
	* Software Testbeds -- This type of award was made for the FutureGrid resource.
	* Staff, XSEDE2 Staff Allocations -- These types of awards were made for the use of staff in the TeraGrid and XSEDE program or for the use of staff at the resource provider sites.
	* XSEDE Campus SSO Integration -- This type of award was made to allow campus resources to take advantage of XSEDE's Single Sign-On (SSO) Hub service. One award was made to each campus being integrated.
	
* Transaction Type -- The type of transaction represented by each project entry. Most awards began as New or Renewal requests, but some allocations can be initiated by advances, supplements, or transfers; for example, if a researcher requests a transfer to a new resource in the middle of an ongoing allocation period.

* Project Title -- The title of the project, as submitted by the user.

* Start Date, End Date -- The start and end dates for an allocation period. In general, the END DATE represents the most consistent demarcation of a single allocation period since by policy all allocations tended to be create so that they had a common end point. For various reasons, allocations may have different start dates (e.g., a transfer or supplement to a new resource in the middle of an ongoing allocation period would start on the day of the transaction), but would be set to the project's current end date.

* Abstract -- The abstract for the project, as submitted by the user.

=======================================================================

allocation_usage_history_2004-2019.csv 

This file includes more detailed, resource-level information about the awarded projects. Each row in the file represents a resource allocation for a particular project spanning a non-overlapping allocation period; a single project award may encompass multiple resource allocations. This file contains only completed allocations, i.e., those with a complete set of reported usage.

* Grant_Number -- The grant number is the identifier for a project that remains constant over time, even as the project spans multiple allocation periods, as the nature of the work (described in the abstract) changes, or as principal investigators change over time. The Grant_Number is the value that should be used for connecting data across the two files. 

* Resource_Name -- A unique internal resource designation associated with the allocation. Note that some allocated resources may encompass multiple physical resources; that is, an allocation made to such a resource "grid" could be used on any of the constituent resources. For example, the "teragrid" resource encompassed four similar clusters at NCSA, SDSC, Caltech, and Argonne National Lab. Each resource name is unique for the life of the resource; e.g., "maverick.tacc.teragrid" and "maverick.tacc.xsede" refer to two different resources named Maverick.

* Transaction Type -- The type of transaction represented by each allocation entry. Projects and allocation periods begin as New or Renewal requests. During the allocation period, some allocations might be initiated by advances, supplements, or transfers; for example, if a researcher requests a transfer to a new resource in the middle of an ongoing allocation period.

* Initial_Allocation -- The amount initially allocated on the resource by the initial Transaction Type.

* Final_Allocation -- The final amount allocated on the resource -- the initial amount along with any supplements or transfers.

* Used_Amount -- The aggregate amount of allocation units used on the resource by the project. The Used_Amount may be greater than the Final_Allocation (i.e., an overspent or negative balance) for a variety of reasons, usually related to the delays that are typical in HPC job charges appearing in the accounting system. In some cases, resource operators may also permit a project to overspend an allocation amount.

* Billable_Unit -- The unit used by the resource for its allocations. The "SU", or Service Unit, was commonly used by most compute resources and was usually defined as a "core-hour."

* Start_Date, Initial_End_Date, End_Date -- The date range for the award. The initial end date was the end date when the allocation was created. The final end date reflects any extensions made to that original end date. Typically, projects could requests extension for up to six months; but in exceptional cases, extensions could be granted beyond six months. 