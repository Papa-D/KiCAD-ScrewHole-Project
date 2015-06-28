

                  Readme File for KiCAD ScrewHole Support

This project allows the card designer to place Screws on the Schematic and have KiCAD track them through the process, and provide Screwhole Footprints at the board layout phase. It supports Non-Plated Through Holes, Plated Through Holes, and, Plated Through Holes that attach to any NET as defined in the Schematic. 

 Since the designer will most likely be thinking in terms of the screws that would be used and not the screwholes, per se, as required by those screws, it was decided to use an image of a screw when placing a screwhole on the schematic.  Since KiCAD allows the designer to associate a schematic representation with any 'footprint' desired, the designer could associate a particular screw with any particular footprint.  However, since, in this case, there is a one-to-one relationship between a particular screw and its footprint, a nameing convention was chosen that makes this association obvious.  A spreadsheet was developed to assist in determining the dimensions for the screwholes based on the standard dimensions of the different screws.  This makes it reasonably easy to add additional screw sizes to the libraries by expanding the spreadsheet to include them. 

-The screw holes supported in the initial release are as follows:

Screw Sizes:  Imperial: 4, 6, 8, 10.
              Metric:   3, 3.5, 4, 5.

Screw Type: Pan Head Screws.

  Other screw sizes/head types can be added. Only the screw shaft size
  and head diameter are required as input to the spread sheet.

Drill Sizes Used: Standard Sizes #32 (0.116) through 7/32 (0.2188).

  Other sizes can be added depending on the user requirements to get
  closer to the Screw-hole clearance desired. This may also depend on what
  the panel shop can support. The final hole size may vary depending
  on how closely the panel shop can match your requirements.


The following additional parameters are assumed:

Minimum Screw/Screw-Hole Clearance:    0.010 inches.
Minimum Global Net-to-Pad Clearance:   0.010 inches.
Maximum Plating Thickness for PTHs:    0.002 inches.

  Any change to the above parameters will also produce new calculated values
  and will require that additional entries be made to the screwhole Library.
  These entries will need an additional naming convention to denote the differencies
  from this 'standard'. (Perhaps a separate spread sheet should be used so as
  to not introduce confusion later on as the new values will no longer match
  the existing screwhole footprints.)


Screw Hole Types Supported:

PTH:     Plated Through Holes.
NPTH:    Non-Plated Through Holes.
NET:     PTH Holes that connect to a Network.



  A spread sheet is included to assist in determining the dimensional data required by KiCAD.
  Notes are included within the spread sheet itself making it self explanatory.

  Here is one of the notes that explains the the difference between a PTH screw (plated 
  through hole) and a NET screw. (One whose footprint attaches to NET on the card).
  It also exposes the naming convention used.

  "ScrewNET Footprints have the same dimensions as the ScrewPTH Footprints.
   The difference is that the ScrewNET Component has an Electrical Pin and
   Pin Number attached, and the matching ScrewNET Footprint PAD has a 
   PAD number assigned to match the PIN number of the ScrewNET Component in
   the schematic. This forces KiCAD to wire the ScrewNET Footprint PAD to the
   network specified in the Schematic.  The ScrewNET/ScrewNET Footprint pair 
   can be thought of as a One Pin Connector where the Footprint/PAD is the 
   Receptacle and the Screw is a Threaded PIN that only come together during
   final board assembly, completing the circuit.
   KiCAD takes care of all the housekeeping."

  This design defines a screw component that has an electrical pin attached which allows
  the card designer to wire that screw into a net on the card.  This screw then becomes 
  part of the netlist and is checked by the ERC.  KIcad passes the wiring requirement to
  the board layout phase.  This way, the card designer cannot forget to wire that connection. 
