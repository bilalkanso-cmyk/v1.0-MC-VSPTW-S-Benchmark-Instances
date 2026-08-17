# v1.0-MC-VSPTW-S-Benchmark-Instances
Benchmark instances for MC-VSpTW-S problem

MC-VSPTW-S Benchmark Instances

Description

This repository contains the benchmark instances used for the
experimental evaluation of the Multi-Center Vaccination Scheduling
Problem with Time Windows and Synchronization (MC-VSPTW-S).

A total of 98 instances are provided. Each instance is stored in a
separate text file (for example, vsp1.txt, vsp2.txt, …, vsp98.txt).

The instances are provided in the same format used by the proposed
algorithm so that the computational experiments can be reproduced.

Instance File Format

Each instance is stored as a plain-text file. The data are given in the
following order.

1.  Number of patients
2.  Number of vaccination centers
3.  Patient time windows
4.  Vaccination-center time windows
5.  Service times
6.  Center capacities
7.  Patient-to-patient distance matrix
8.  Number of synchronization groups
9.  Members of each synchronization group

More precisely, the structure is:

    N
    NC
    pTW_1_start pTW_1_end
    ...
    pTW_N_start pTW_N_end
    cTW_1_start cTW_1_end
    ...
    cTW_NC_start cTW_NC_end
    service_1 service_2 ... service_N
    capacity_1 capacity_2 ... capacity_NC
    d_11 d_12 ... d_1N
    d_21 d_22 ... d_2N
    ...
    d_N1 d_N2 ... d_NN
    NS
    group_1_member_1 group_1_member_2 ...
    ...
    group_NS_member_1 group_NS_member_2 ...

where:

    N   = number of patients
    NC  = number of vaccination centers
    pTW = time window of a patient
    cTW = time window of a vaccination center
    service_i = service time associated with patient i
    capacity_j = capacity of vaccination center j
    d_ij = distance between patients i and j
    NS  = number of synchronization groups

Patient and Center Indexing

Patients and vaccination centers are indexed starting from 0.

Therefore, a patient numbered 0 corresponds to the first patient, and a
center numbered 0 corresponds to the first vaccination center.

Time Windows

Each patient has a predefined time window represented by two values:

    start end

For example:

    192 192

represents a time window whose start and end are both 192.

The same representation is used for vaccination-center time windows.

Service Times

After the center time windows, the service times of the patients are
provided as a single sequence containing N values.

For an instance with 20 patients, the sequence therefore contains 20
service-time values.

Center Capacities

The capacity values of the vaccination centers are provided as a
sequence containing NC values.

For an instance with 2 vaccination centers, two capacity values are
provided.

Distance Matrix

The distance matrix contains N rows and N columns.

The value at position (i,j) represents the distance between patient i
and patient j.

For an instance with N patients, the matrix therefore contains N*N
distance values.

Synchronization Groups

The number of synchronization groups is given after the distance matrix.

For example:

    2

means that the instance contains two synchronization groups.

The following lines specify the members of each synchronization group.
Patient indices are used to identify the members.

For example:

    0 1
    2 3

defines two synchronization groups:

    Group 1: patients 0 and 1
    Group 2: patients 2 and 3

The synchronization constraint requires the members of a group to
satisfy the synchronization conditions defined in the MC-VSPTW-S problem
formulation.

Example

The following example begins with:

    20
    2

This means that the instance contains 20 patients and 2 vaccination
centers.

The next 20 lines describe the time windows of the 20 patients, followed
by 2 lines describing the time windows of the vaccination centers.

The following sequence contains the service times of the 20 patients,
followed by the capacities of the 2 vaccination centers.

The next 20 rows form the 20 x 20 distance matrix.

Finally, the value:

    2

indicates two synchronization groups, followed by:

    0 1
    2 3

which specifies their members.

Reproducibility

The complete set of benchmark instances used in the computational
experiments is provided in this repository. The files should be used
directly as input to the proposed algorithm.

The reported experimental results can be reproduced by using the
corresponding instance files together with the algorithm and parameters
described in the paper.

Instance Naming

The instances are named:

    vsp1.txt
    vsp2.txt
    ...
    vsp98.txt

The instance name is used consistently in the paper, the result tables,
and the corresponding input file.

Data Availability

The complete set of 98 MC-VSPTW-S instances is made publicly available
to facilitate independent verification and reproduction of the
computational experiments reported in the paper.

If the repository is archived through Zenodo, the permanent DOI assigned
to the dataset should be cited in the paper.

Citation

Please cite the associated research paper when using these benchmark
instances.

A citation file (CITATION.cff) may also be included in the repository to
facilitate citation of the dataset and software.
