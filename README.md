megaclisas-status
=================

Python script that prints out some useful information parsing the output of
MegaCli.  
Nagios mode is supported by passing `—nagios` at the command line.  
This is a complete rewrite of [the original megaclisas-status]
(https://github.com/npinto/megaclisas-status).  
The output is compatible with the original version except for the additional
'Drives' column in the arrays information.

Sample output:

    $ sudo megaclisas-status
    -- Controller info --
    -- ID | Model
    c0 | MegaRAID SAS 8708EM2

    -- Arrays info --
    -- ID | Drives | Type | Size | Status | InProgress
    c0u0 | 2 | RAID1 | 465G | Optimal | None
    c0u1 | 2 | RAID1 | 465G | Optimal | None

    -- Disks info --
    -- ID | Model | Status
    c0u0p0 | 9VM5QJ3AST3500418AS CC37 | Online, Spun Up
    c0u0p1 | 9VM5QQ6DST3500418AS CC37 | Online, Spun Up
    c0u1p0 | 9VM5QJ4AST3500418AS CC37 | Online, Spun Up
    c0u1p1 | 9VM5QR1NST3500418AS CC37 | Online, Spun Up

    $ sudo megaclisas-status  --nagios
    RAID OK - Arrays: OK:2 Bad:0 - Disks: OK:4 Bad:0
