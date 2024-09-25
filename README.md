README: DICOM Image Processing and Vertebra Segmentation with B-Splines
Overview
This Python script processes DICOM image files from a CT scan, allowing the user to visualize coronal slices and perform manual segmentation of vertebrae using B-spline interpolation. The main features include:

Loading and sorting DICOM files.
Creating a 3D image from the DICOM slices.
Interactive visualization of coronal slices.
Manual selection of points for vertebrae segmentation.
Interpolation of vertebrae outlines using periodic B-splines.
Mask creation from B-splines and measurement of vertebra height projections.
Requirements
Python 3.x
Required libraries: pydicom, numpy, matplotlib
To install the required libraries, you can run:

bash
Copiar código
pip install pydicom numpy matplotlib
Features
Load and Sort DICOM Files:

The script loads all .dcm files from a specified folder, sorts the slices based on SliceLocation or ImagePositionPatient, and constructs a 3D image array.
Interactive Slice Navigation:

Coronal slices of the CT scan are displayed with a slider to navigate through the different slices.
Manual Vertebrae Segmentation:

Users can fix a coronal slice, select points on vertebrae, and interpolate the points using cubic or quadratic B-splines.
B-Spline Masking and Vertebra Height Measurement:

After selecting vertebra points, the script can generate a mask from the B-spline curve to isolate the region of interest and measure vertebral height projections along the x-axis.
Usage
Load DICOM Files:

Place your DICOM files in a folder, and update the folder_path variable in the main() function to point to this folder.
Run the Script:

Execute the script in your Python environment:
bash
Copiar código
python script_name.py
Keyboard Controls:

Slider to navigate slices: Use the slider to navigate through coronal slices.
Press x to fix the current slice for segmentation.
Press n to start a new vertebra segmentation.
Click on the image to select points for the vertebrae.
Press r to interpolate the selected points using a B-spline. You will be prompted to enter the B-spline degree.
Press c to apply a mask to the region defined by the B-spline.
Press q to finalize the segmentation and display the vertebra height projection plot.
Example Workflow
Open the script and navigate through coronal slices.
Fix a slice by pressing x.
Select vertebra points by clicking on the slice.
Press r to interpolate the points using a B-spline.
Press c to apply a mask to the region enclosed by the B-spline.
Measure vertebra heights and display the plot by pressing q.
Additional Notes
The script supports selecting multiple vertebrae on the same fixed slice. Each vertebra can be processed individually.
B-spline interpolation degree can be adjusted (usually set to 2 or 3 for medical imaging).
The height plot shows the projected height of each vertebra along the x-axis, useful for analyzing vertebral compression or deformation.
