# pmls4matlab - Surface reconstruction for 3D cave surveying
![](teaser.gif)

**pmls4matlab** is the proof of concept implementation of the applied surface reconstruction technique in our novel 3D cave surveying method: [Poor Man's Laserscanner (PMLS): a simple method of 3D cave surveying](http://cave3d.org/cmssimple). Our method is based on sparse measurements performed with Beat Heeb's  [DistoX](https://paperless.bheeb.ch) or similar laser distance meter equipped with compass and inclinometer. We can capture very few samples with the Disto compared to point clouds resulting from Terrestrial Laser Scanners (TLS) or [GeoSlam’s ZEB1/ZEB REVO](https://geoslam.com/) handheld laser scanners. In addition, the distribution of the sampled points can be extremely uneven, while caves usually have layouts with lots of features at all scales. To overcome these difficulties a robust and reliable surface reconstruction algorithm had to be developed. The proposed sofware, **pmls4matlab** interpolates the measured points with a watertight surface, which is free of self-intersections. We have found that even complicated geometric layouts can be recovered with good detail from as few as 50 to 150 splay shots per station. More technical details can be found in our [paper](https://poormanslaserscanner.github.io/pmls4blender/paper.pdf). 

## Installation
### Prerequisites
- A 64-bit version of Microsoft Windows (We provide precompiled binaries of the used 3rd party software only for windows, but these could also be compiled on Linux.)
- Matlab version 2015b or later
- Hardware requirements: 8GB Ram, but 16 or more is recommended for large surveys

### Obtain the packages using git:
Change to a directory in which the PMLS system will be installed. A new directory called "pmls4matlab" will be created in which pmls4matlab will be set up.

1. Download pmls4matlab:
```
git clone https://github.com/poormanslaserscanner/pmls4matlab.git
cd pmls4matlab
```
2. Dependencies are incorporated as submodules, you can obtain them by:
```
git submodule update --init
cd ..
```
3. Alternatively you can also download these files from releases
4. Download precompiled binaries from releases
5. Copy the bin directory into pmls4matlab

### Setup
1. Set PMLS_INSTALL_DIR environmental variable to the pmls installation folder, eg.: "d:\pmls4matlab"
1. Start Matlab
1. Setup the Matlab path by typing in the Matlab command line: 
```matlab
cd(getenv('PMLS_INSTALL_DIR'))
setup
```

## Contact
PMLS is a group endeavor of a few cavers from Hungary. You can [contact us](mailto:pmls-hu@cave3d.org) if you have questions or comments.
If you're using our work, please drop us a note to justify spending time maintaining this.

#### The members of our team:
- Attila G&#XE1;ti
- Zsombor Fekete
- Nikolett Reh&#XE1;ny
- P&#XE9;ter S&#X171;r&#X171;
- Bal&#XE1;zs Holl

#### Contributors:
- Imre Balogh
- Kamilla Borzs&#XE1;k
- Edit Harangozó
- Beat Heeb
- Richard Kov&#XE1;cs
- Fanni Matuszka
- József Mészáros
- Magdolna Novák
- Andr&#XE1;s Rántó
- Eszter Szabó
- Réka Veres


## Copyright
Copyright 2014-2017  [Attila G&#XE1;ti](mailto:poormanslaserscanner@gmail.com).
If you publish a work, in which you have used PMLS you could cite:

Attila G&#XE1;ti, Nikolett Reh&#XE1;ny, Bal&#XE1;zs Holl, Zsombor Fekete and P&#XE9;ter S&#X171;r&#X171;: 
"The Poor Man's Laser Scanner: a Simple Method of 3D Cave Surveying"
[CREG-Journal 96](http://bcra.org.uk/pub/cregj/index.html?j=96), pp. 8—14, 2016

## License
pmls4matlab is licensed under the [GNU GENERAL PUBLIC LICENSE version 3](https://www.gnu.org/licenses/gpl-3.0.en.html).

## Acknowledgement
Our software is heavily based on other's work:
1. [Alec Jacobson](https://github.com/alecjacobson), [Daniele Panozzo](https://github.com/danielepanozzo), et al.: [libigl](https://github.com/libigl/libigl) - A simple C++ geometry processing library
1. [Qianqian Fang](https://github.com/fangq): [Iso2mesh](http://iso2mesh.sourceforge.net/cgi-bin/index.cgi): an image-based 3D surface and volumetric mesh generator (Fang 2009)
1. [Jonathan Shewchuk](https://people.eecs.berkeley.edu/~jrs): [Triangle](https://www.cs.cmu.edu/~quake/triangle.html): A Two-Dimensional Quality Mesh Generator and Delaunay Triangulator
1. [Hang Si](http://www.wias-berlin.de/~si): [Tetgen](http://wias-berlin.de/software/index.jsp?id=TetGen&lang=1): A Quality Tetrahedral Mesh Generator and a 3D Delaunay Triangulator (Hang Si 2015)
1. [Marco Attene](http://pers.ge.imati.cnr.it/attene/PersonalPage/attene.html): [MeshFix](https://github.com/MarcoAttene/MeshFix-V2.1): A lightweight approach to repairing digitized polygon meshes (Attene 2010)
1. [Alec Jacobson](https://github.com/alecjacobson): [gptoolbox](https://github.com/alecjacobson/gptoolbox): Matlab toolbox for Geometry Processing
1. [Pierre Terdiman](http://codercorner.com/Pierre.htm): [OPCODE](http://www.codercorner.com/Opcode.htm): Optimized Collision Detection
1. [Vipin Vijayan](https://uk.mathworks.com/matlabcentral/profile/authors/3188385-vipin-vijayan): [opcodemesh](https://uk.mathworks.com/matlabcentral/fileexchange/41504-ray-casting-for-deformable-triangular-3d-meshes): Ray casting for deformable triangular 3D meshes
1. [Jeroen Baert](https://people.cs.kuleuven.be/~jeroen.baert), PhD student at [Katholieke Universiteit te Leuven](https://www.kuleuven.be/kuleuven): [cuda_voxeizer](https://github.com/Forceflow/cuda_voxelizer) Experimental CUDA voxelizer, to convert polygon meshes to annotated voxel grids
1. [Blender foundation](https://www.blender.org/foundation): Blender: Open Source 3D creation. Free to use for any purpose, forever.
1. [Beat Heeb](https://bheeb.ch): [DistoX](https://paperless.bheeb.ch): An All-in-One Electronic Cave Surveying Device (Heeb 2009, 2014)
1. [Marco Corvi](https://github.com/marcocorvi): [topodroid](https://play.google.com/store/apps/details?id=com.topodroid.DistoX&hl=en): Cave surveying on Android


## References
Fang, Qianqian, and David A Boas. 2009. “Tetrahedral Mesh Generation
from Volumetric Binary and Grayscale Images.” In *2009 Ieee
International Symposium on Biomedical Imaging: From Nano to Macro*,
1142–5. IEEE. <http://iso2mesh.sourceforge.net/cgi-bin/index.cgi>.

Hang Si. 2015. ”TetGen, a Delaunay-Based Quality Tetrahedral Mesh Generator”. *ACM Trans. on Mathematical Software*. 41 (2), Article 11 (February 2015), 36 pages. <http://doi.acm.org/10.1145/2629697>.

M. Attene. 2010. ”A lightweight approach to repairing digitized polygon meshes”. The Visual Computer, (c) Springer. DOI: 10.1007/s00371-010-0416-3

Heeb, Beat. 2009. “An All-in-One Electronic Cave Surveying Device.”
*CREG-Journal*, no. 72. BCRA:8–10.
<http://bcra.org.uk/pub/cregj/index.html?j=72>.

———. 2014. “The Next Generation of the DistoX Cave Surveying
Instrument.” *CREG-Journal*, no. 88. BCRA:5–8.
<http://bcra.org.uk/pub/cregj/index.html?j=88>.
