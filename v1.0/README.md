# Trajectory_Generation_No_Wind

This is the companion code for [Flight Trajectory Planning for Fixed-Wing Aircraft in Loss of Thrust Emergencies](http://wcl.cs.rpi.edu/papers/trajectory_tech_report_oct_17.pdf "Research Paper")

This is an open source project.

The instructions for using the trajectory generation software are given below:

* Create a configuration file with the name `config.txt` in the following format: 
		`initial_longitude,initial_latitude,initial_heading,final_longitude,final_latitude,final_heading,initial_altitude,baseline_glide_ratio,dirty_configuration_glide_ratio`


* For generating trajectories, create a `config.txt` file in the above format, put `generate` and `visualize.py` (for viewing the trajectories in 2D and 3D) in the same folder along with the `config.txt` file and type:


	`$./generate` (To generate trajectories with 20, 30 and 45 degree bank angles)


	`$python visualize.py` (To visualize the generated trajectory)


* The zip file contains a file named '1549_data' that contains the parameters for the runways and the parameters for the various time instances that can be used to recreate the experiments in section VII-B of the paper.

##### Known bugs:
The spirals for the high altitude trajectories come out wrong in certain cases. 
This usually has to be manually dealt with in the function `generate_circles()` in `helper.c` where the angle needs to be adjusted for each specific airport. 
Once fixed, however, all trajectories to that airport can be generated smoothly.

##### Note: 
{dubins.c, dubins.h} - Copyright (c) 2008-2014, [Andrew Walker](https://github.com/AndrewWalker "Github Link")

##### DISCLAIMER: 
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.