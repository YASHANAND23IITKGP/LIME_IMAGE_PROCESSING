# LIME: Low-Light Image Enhancement via Illumination Map Estimation

This is a MATLAB implementation of the paper, "LIME: Low-Light Image Enhancement via Illumination Map Estimation". It has been done as a course Capstone project for Digital Image Processing (EE60062), under the guidance of Prof. Debdoot Sheet.

* The project report can be found [here](https://drive.google.com/file/d/1RZk386iDRkE_KJBXhzf-fqDofLo6PBYf/view?usp=drive_link).
* The IEEE reference paper can be found [here](https://ieeexplore.ieee.org/document/7782813)

## How to Use 
### Clone the repository:
```
git clone https://github.com/YASHANAND23IITKGP/LIME_IMAGE-_PROCESSING
```

&nbsp; Open MATLAB, go to the git repository folder.

### Add paths
&nbsp; Run the following to the MATLAB command window:
```
addpath('./imgs');
```
### Load images and run

&nbsp; Run the following commands in the MATLAB command window:
```
img_in = imread('x.bmp'); 
[Ti, Tout, img_out, Iout] = lime_main_module(img_in, mu, rho, ds, ss, flag);
```

* `x` is some image from `imgs`
* `flag = 1` to view the results. 
* `Ti` and `Tout` are initial and refined illumination maps, `img_out` and `Iout` are enhanced and denoised results.
* Use the table mentioned below for selecting optimum values of `mu`, `rho`, `ds`, `ss` for each image.

### Table for optimized hyperparameters

|	Name	| `mu`	| `rho`	| `ds`	| `ss` | 
| --- | --- | --- | --- | --- |
|	building | 0.01	| 1.188	| 10	| 1.5 |
|	cars	 | 0.045	| 1.134	| 5	| 0.75 |
|	lamp	 | 0.8	| 1.07	| 0.1	| 1 |
|	land	 | 0.5	| 1.09 |	0.3 |	4 |
|	moon	 | 0.01	| 1.2	| 1	| 0.5 |
|	paint	 | 0.3	| 1.15	| 1 	| 0.5|
|	robot	 | 0.01	| 1.25	| 10	| 1 |
|	table	 | 0.002	| 1.035	| 100	| 1 |
|	wires	 | 0.01	| 1.165	| 1	| 0.6 |


### Information regarding other files: 

* `lime_loop.m` is the file for tuning the parameters for the solver, i. e. `alpha`, `mu`, `rho`.

* `lime_bf_loop.m` is the file for tuning the parameters for the bilateral filter, i. e. `ds`, `ss`. By default, `lime_bf_loop.m` is used for post-processing.
  
* `initial_map.m` is the file for obtaining initial illumination map.
  
* `gamma_corr.m` is the file for applying gamma correction.
  
* `make_weight_matrix.m` is the file for making the weight matrix.
  
* `shrinkage.m` is the file for performing shrinkage operation.
  
* `updateT.m` is the file for updating the value of illumination map.
  
* `maked_alt.m` is the file for creating the matrix D for calculating gradient using matrix multiplication.


## Results
<!-- Using alt attribute for accessibility and debugging -->
<img width="100%" src="Images/8_combined.png" alt="Combined Image Not Found" />

> **First column**: Low-light images, **second column**: heat map of initial illumination map, **third column**: heat map of estimated illumination map, **fourth column**: enhanced results, **fifth column**: denoised results via bilateral filtering.  



## Citation
If you find this code helpful and use it in your research, please cite the following work:
```
@ARTICLE{guo_lime,
  author={X. {Guo} and Y. {Li} and H. {Ling}},
  journal={IEEE Transactions on Image Processing}, 
  title={LIME: Low-Light Image Enhancement via Illumination Map Estimation}, 
  year={2017},
  volume={26},
  number={2},
  pages={982-993},}
```
## Contributors

- @KAUSHALKISHOR9939
- @atulsaurabh1995



