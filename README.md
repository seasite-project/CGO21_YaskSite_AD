# CGO21_YaskSite_AD

* Requires: singularity v 3.6.4 or higher. If singularity is not installed use
```
  ./install_singularity.sh
```

## Step 1
Clone the repo and go to the cloned directory.
```
git clone https://github.com/seasite-project/CGO21_YaskSite_AD.git 
cd CGO21_YaskSite_AD
```

## Step 2
Download the singularity container. 

The pre-build container is available under the following link https://doi.org/10.5281/zenodo.4283337
and can be installed using:
```
wget https://zenodo.org/record/4283337/files/YS_CGO.sif?download=1 -O YS_CGO.sif
```

## Step 3
Once singularity image is downloaded on the benchmarking system the first step is to run the app called build.
This installs YaskSite. It should be done at runtime since the YaskSite does machine specific configuration
at build time. Run the following to do this:
```
singularity run --app build YS_CGO.sif 
```

## Step 4
Run the apps corresponding to YaskSite and Offsite. There are also pre-configured apps that helps to 
reproduce data in figures of the paper. To see the list of available apps use: 
```
singularity run-help YS_CGO.sif
```
The method to run each apps are described in corresponding app's help. For example help on how to run Fig3 app 
(reproduces results in Fig3 of the paper) can be obtained using:
```
singularity run-help --app Fig3 YS_CGO.sif
```
