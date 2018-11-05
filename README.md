# Kijiji Auto Reposter

## Information:

This python script can be used to manage the automatic reposting of Kjiji ads.

## Usage:

1. Clone the entire repo so that the script is contained in a directory with the following structure:
```
	~./cloned_dir
		|
		|----kjj_auto.py
		|----description.txt
		|----environvars
		|----images
			|
			|-image_1.jpg
			|-image_2.jpg
			|- ...
			|-image_n.jpg
			
```
2. Install pip if you do not already have it. Install the dependencies with `pip install -r requirements` or `pip install selenium`. 

3. Edit `description.txt` with the description you would like for your ad. Place the images for you ad into the `images` folder. Edit `titles.txt` with your title name on one line, or variations of a title on multiple lines. If there are multiple lines in `titles.txt` the script will randomly choose one when posting an ad. 

4. Open the file `environvars` in textedit and enter your kijiji email and password. In terminal run `$ source environvars` to create environment variables with your email and password. 

5. Run the script from terminal `python kjj_auto.py` You will be asked to input an upper and lower price bound. The program reposts every 24hrs. Each time it reposts, it lowers the price by $10. The initial price is the upper bound. If the lower bound is reached, it reposts at the price of the lower bound.

The program will run a loop that:
	- Opens a chrome window and posts the ad, the closes
	- Waits 24hrs
	- Deletes the ad and then waits 10 minutes before repeating

If there are replies to the ad, the program will not delete it and will instead print that it has detected messages.



