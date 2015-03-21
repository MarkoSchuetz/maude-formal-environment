# MFE - The Maude Formal Environment #


The _Maude Formal Environment_ (MFE) is an executable and highly extensible
software infrastructure within which a user can interact with several
tools to mechanically verify properties of [Maude](http://maude.cs.uiuc.edu) specifications. In
MFE, tools can interoperate to discharge proof obligations of different
nature without switching between different tool environments. The
integration of different tools inside MFE's common environment presents
the user with a consistent user interface, a mechanism to keep track of
pending proof obligations, and allows the execution of several
instances of each tool, among other features.

MFE is naturally modeled in Maude as an object-based system in which the
tools are objects and their communication mechanism is message passing.
User interaction is available through [Full Maude](http://maude.lcc.uma.es/FullMaude), an
extension of Maude that has become a common
base on top of which tools can be built, offering a modular design for easily
integrating other tools written in Maude.

## License ##

This software is licensed under the terms of the GPL 3.0 license. Additional information can be found at the GNU Project [http://www.gnu.org/licenses/old-licenses/gpl-3.0.html website](.md).

## Where to Start? ##

The project's documentation is maintained in the Wiki section. Please visit:

  * [Installation](http://code.google.com/p/maude-formal-environment/wiki/Installation) for installation and configuration instructions

  * [Use](http://code.google.com/p/maude-formal-environment/wiki/Use) for use instructions

  * [Tools](http://code.google.com/p/maude-formal-environment/wiki/Tools) for a list of tools available in MFE's latest release

  * [Maude++](http://code.google.com/p/maude-formal-environment/wiki/Maude_plus_plus) for a brief explanation on how the Maude system has been extended with new operators to handle calls to the CETA library and termination back-ends.

## Papers on the MFE ##

  * F. Durán, C. Rocha, J. M. Álvarez: Tool Interoperability in the Maude Formal Environment. CALCO 2011. Lecture Notes in Computer Science, 2011, Volume 6859/2011, 400-406, DOI: 10.1007/978-3-642-22944-2\_30

  * F. Durán, C. Rocha, J. M. Álvarez: Towards a Maude Formal Environment. Formal Modeling: Actors, Open Systems, Biological Systems. Lecture Notes in Computer Science, 2011, Volume 7000/2011, 329-351, DOI: 10.1007/978-3-642-24933-4\_17.