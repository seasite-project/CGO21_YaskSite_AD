# CGO21_YaskSite_AD

* Requires: singularity

## Step 1
Clone the repo
```git clone https://github.com/seasite-project/CGO21_YaskSite_AD.git```

## Step 2
Build/Download the singularity container. 
### Alternative 1: Singularity build (need fakeroot right)
```build --fakeroot YS_CGO.sif Singularity```

### Alternative 2: Download the pre-build container (approximately 2 GB in size)
```wget TODO```

## Step 3
Once singularity image is build on the benchmarking system the first step is to run the app called build.
This installs YaskSite. It should be done at runtime since the YaskSite does machine specific configuration
at build time. Run the following to do this
```
singularity run --app build YS_CGO.sif 
```

## Step 4
Run the apps corresponding to YaskSite and Offsite. There are also pre-configured apps that helps to 
reproduce data in figures of the paper. To see the app list use `singularity run-help YS_CGO.sif`.
The method to run each apps are described in its corresponding help i.e. for example
`singularity run-help --app Fig3 YS_CGO.sif` gives help on how to run Fig3 app, that reproduces
results corresponding to Figure 3.
