the content saved to the files is: 

labelvalue x y w h 
where labelvalue is which label in the set it is (see below chart), x is the center point on the x axis, y is centerpoint on y axis, w is width and h is height



I think I need to check if y is higher for dog label than for couch label 

I think I need to calculate the relative coordinates of the couch and the dog - then if I get:
	left side of couch < left side of dog &&
	right side of couch > right side of dog &&
	top of couch > top of dog &&
	bottom of couch < bottom of dog
		then have sound play to get dog off the couch
		
		
Also worth noting - I think the y axis is the reverse of what I think it would be - and I think I can just go off of if dog y-axis < couch y-axis means the dog is on the couch


0 - is person for default label set 

65 - is remote for default label set

16 - is dog

57 - is couch

I think what I want to change is in 168-173 of detect.py - grab 16 and 57 and use that 

command to run (next need to generate a .pt file with Jenny and the couch later with infrared and normal light for better detection): 
python3 detect.py --source 0 --weights yolov5s.pt --conf 0.25


training command:
python3 train.py --img 640 --batch 2 --epochs 60 --data data/coco128.yaml --weights yolov5s.pt

