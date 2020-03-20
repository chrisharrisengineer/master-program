Project Title
Loma Linda BRISK and Soluble Fibrin machine

This code is for a novel blood analysis machine.  The blood is put in a test tube, inserted into the machine (which includes a PLC, operator interface, control algorithms for the blood rocking mechanisms, lighting and heating controls, data storage and more), a cam\era captures video of the blood, and deep learning algorithms are used to perform two tests.


Table of Contents


1.  Bleeding Risk.  This analyzes the time it takes for the blood to clot, for platelets to activate, and for platelets to collect into clumps.  These results are then printed out on a graph and this information can be used in many applications, such as major surgeries, and for prescribing blood thinners.  It gives information that will allow a physician to determine what to target so as to prevent excess clotting, and excess blood thinning.  Handling these problems could reduce stroke, coronary thrombosis, incorrect prescriptions of many types of blood thinners, etc.  Clotting detection uses image classification, and platelet detection uses object detection.

2.  Rapid Soluble Fibrin test.  This test shows the presence of Soluble Fibrin, which has been reported to be one of the most sensitive and early predictors of ongoing thrombosis (DIC, pre-DIC, deep vein thrombosis), multiple organ failure (MOF), and outcome in ICU patients.  The time it takes for soluble firbin clumps to form is converted into a Soluble Fibrin Unit number, which is used to determine the levels.  Soluble fibrin detection uses object detection.




Getting Started


Clone this repo from Github
Install fastai from conda
Tensorflow from conda


Running the tests



Deployment

To run on a standalone computer, use brisk_run_test.py or soluble_fibrin_run_test.py to run these tests.

To run on an actual machine, run 01_26_subprocess.py.


Authors
Christopher Harris


parent directory master program-git
keep all filepaths relative

master program

    01_26_subprocess.py



    cropped_pics
    	pictures written from machine





	brisk_and_sf_tests
    	__init__.py
    	brisk_package
        	__init__.py
            clotting_classification.py
			clotting_image_classification_model.pkl
            brisk_run_test.py

    	soluble_fibrin_package
        	soluble_fibrin_run_test.py
        	activate_tf_gpu.txt
 

    	Tensorflow
        	models->research->object_detection->
            	object_detection_platelet
                	object_detection_image.py 
                	platelet_inf_graph.pkl
                	platelet_label_map.pbtxt
            
            	object_detection_soluble_fibrin
                	object_detection_image_soluble_fibrin.py
                	SF_inf_graph.pkl
                	SF_label_map.pbtxt
    
    	tube_ready_not_ready_classification.py

	__init__.py

		

README.MD
.gitignore

_________________________________________________________________________



git instructions:
	create a github account
        install git on your computer
        setup:  git --version to make sure installed correctly
                git config --global user.name "github username"
                git config --global user.email "your email" 
                check worked correctly:  git config --list
        go to directory want to track
        git init
        git status  (check if any modified or uncommited files, will be red)
        git add -A  (add modifified files to staging area)
        git status (should all be green now)
        git commit -m "your message here"
        git status    
        git push (url for github repository)
         
