# ------------------------------------------------------------------------------#
#              FEARLESS STEPS CHALLENGE 2020 (PHASE-02)
# ------------------------------------------------------------------------------#
#
# Authors: John H.L. Hansen, Aditya Joglekar, Meena Chandra Shekhar, Abhijeet Sangwan
# Latest Update: Feb 01, 2020
# Contact: FearlessSteps@utdallas.edu
# Robust Speech Systems Lab (RSTL), Center for Robust Speech Systems (CRSS)
# The University of Texas at Dallas, Texas, USA


--- Disclaimer ---

The Fearless Steps corpus is derived from a five-year NSF CISE funded project awarded to CRSS at the University of Texas at Dallas. UTDallas-CRSS established the hardware/software solutions to digitize and diarize 19,000 hrs of NASA Apollo data. All core Apollo data released as part of this challenge has been approved for public release by NASA Export Control. The full audio corpus is also available through UTDallas-CRSS. Any reference to or listing of organizations other than UTD is for information only; it does not imply recommendation or endorsement by UTDallas-CRSS nor does it imply that the products mentioned are necessarily the best available for that purpose. 


----------------------------------------------------------------------------------------------
Fearless Steps Challenge Train, Dev, and Eval sets (Fearless_Steps_Challenge_Phase02)
----------------------------------------------------------------------------------------------



--- About Fearless Steps Challenge ---

The Fearless Steps Initiative by UTDallas-CRSS led to the digitization, recovery, and diarization of 19,000 hours of original analog audio data, as well as the development of algorithms to extract meaningful information from this multichannel naturalistic data resource. As an initial step to motivate a stream-lined and collaborative effort from the speech and language community, UTDallas-CRSS is hosting a series of progressively complex tasks to promote advanced research on naturalistic “Big Data” corpora. This began with ISCA INTERSPEECH-2019: "The FEARLESS STEPS Challenge: Massive Naturalistic Audio (FS-#1)". This first edition of this challenge encouraged the development of core unsupervised/semi-supervised speech and language systems for single-channel data with low resource availability, serving as the “First Step” towards extracting high-level information from such massive unlabeled corpora.
As a natural progression following the successful Inaugural Challenge FS#1, the FEARLESS STEPS Challenge Phase-#2 focuses on the development of single-channel supervised learning strategies. This FS#2 provides 80 hours of ground-truth data through Training and Development sets, with an additional 20 hours of blind-set Evaluation data. Based on feedback from the Fearless Steps participants, additional Tracks for streamlined speech recognition and speaker diarization have been included in the FS#2. The results for this Challenge will be presented at the ISCA INTERSPEECH-2020 Special Session. We encourage participants to explore any and all research tasks of interest with the Fearless Steps Corpus – with suggested Task Domains listed below. Research participants can, however, also utilize the FS#2 corpus to explore additional problems dealing with naturalistic data, which we welcome as part of the special session. 


--- Official Challenge Website---

The Official Website for The Fearless Steps Challenge Phase-02 is:
https://fearless-steps.github.io/ChallengePhase2/
All updates regarding the Phase-02 Challenge Data, and Challenge will be posted here.


The website for The Fearless Steps Challenge Phase-01: http://fearlesssteps.exploreapollo.org/
has updates regarding the Entire 19,000 hour Corpus.



--- This (FS-02) edition of the FEARLESS STEPS Challenge includes the following 6 tasks ---

## TASK 1: Speech Activity Detection							(SAD)
## TASK 2: Speaker Identification (using Speaker Segments)		(SID)
## TASK 3: Speaker Diarization
## 		├── (3.a.) Track 1: Diarization using system SAD		(SD_track1)
## 		└── (3.b.) Track 2: Diarization using reference SAD		(SD_track2)
## TASK 4: Automatic Speech Recognition
## 		├── (4.a.) Track 1: ASR using system Diarization/SAD	(ASR_track1)
## 		└── (4.b.) Track 2: ASR using Diarized Segments			(ASR_track2)


----------------------------------------------------------------------------------------------


--- Fearless Steps Challenge data is organized as shown below ---

# # ./Fearless_Steps_Challenge_Phase02/
# # ├── FS02_Challenge_Data		-- a tar.gz File (unzip to see the folder contents)
# # │   ├── Audio				-- the audio as 8kHz wav files
# # │   │   ├── Segments		-- short duration audio segments 
# # │   │   │   ├── ASR_track2	   (used for: ASR_track2, and SID)
# # │   │   │   │   ├── Dev
# # │   │   │   │   ├── Eval
# # │   │   │   │   └── Train
# # │   │   │   └── SID
# # │   │   │       ├── Dev
# # │   │   │       ├── Eval
# # │   │   │       └── Train
# # │   │   └── Streams			-- 30 min Audio Streams
# # │   │       ├── Dev			   (used for Tasks: ASR_track1,)
# # │   │       ├── Eval		   (SAD, SD_track1, and SD_track2)
# # │   │       └── Train
# # │   └── Transcripts			-- file (stream) level transcriptions
# # │       ├── ASR_track1 			(JSON Files)
# # │       │   ├── Dev			-- ".json" files to specify transcriptions 
# # │       │   └── Train			for Audio Streams
# # │       ├── ASR_track2		-- utterance (segment) level transcriptions
# # │       │   ├── Dev 
# # │       │   └── Train
# # │       ├── SAD					(TXT Files)
# # │       │   ├── Dev
# # │       │   └── Train
# # │       ├── SD_track1			(RTTM and UEM Files)
# # │       │   ├── Dev
# # │       │   │   ├── RTTM
# # │       │   │   └── UEM		-- ".uem" files to specify scoring segments 
# # │       │   └── Train
# # │       │       ├── RTTM
# # │       │       └── UEM
# # │       ├── SD_track2			(RTTM, UEM, and SAD Files)
# # │       │   ├── Dev
# # │       │   │   ├── refSAD	-- ".sad" files to specify 
# # │       │   │   ├── RTTM		ground-truth SAD segments
# # │       │   │   └── UEM
# # │       │   ├── Eval
# # │       │   │   └── refSAD
# # │       │   └── Train
# # │       │       ├── refSAD
# # │       │       ├── RTTM
# # │       │       └── UEM
# # │       └── SID
# # ├── checksum.md5			-- md5 checksum file for Data.tar.gz
# # └── README.txt				-- this readme file 




----------------------------------------------------------------------------------------------


--- Data format and naming conventions ---

Audio files are available in WAV format with 8kHz sample rate and 16-bit precision. All files begin with the corpus name 'FS_P02'.

For each Utterance in the "Segments" section, the file naming format sample for "SID" and "ASR Track 2" tasks are shown below:
    FS02_< Task and Track Name >_< Dataset_Type >_< Utterance_ID >.wav

For each 30 minute excerpt in the "Streams" section, the file naming format sample for all other tasks is shown below:
    FS_P02_< Dataset_Type >_< File_ID >.wav


----------------------------------------------------------------------------------------------


--- md5sum ---

Please use md5sums for 'FS02_Challenge_Data' archive below:

-- 55cb67066cf1555df4c5d14fa58c51fa --  ./FS02_Challenge_Data.tar.gz


--- Updates ---

Participants Registered will receive an email from FearlessSteps@utdallas.edu regarding any further updates 



----------------------------------------------------------------------------------------------



----------------------------------------------------------------------------------------------
CHALLENGE RULES AND CONDITIONS
----------------------------------------------------------------------------------------------


1. Participants can choose to take part in any one or more tasks from Fearless Steps challenge.

2. This Challenge follows Open training conditions. Participants are allowed to use any available data in addition to the provided Challenge Data to train and tune their systems. Participants are however not allowed to use The Fearless Steps Challenge Phase-1 data (and labels).

3. Ground Truth Labels provided for a specific Task/Track should only be used for its corresponding task. Participants are not allowed to use the labels provided for a given task to improve system performance on any other task.
	example 1: The refSAD ground truth labels in the Speaker Diarization Task 2 are prohibited from being used to benefit the performance of any other Tasks except "SD Track-2". 
	example 2: The "SAD" (Task 1) ground truth labels are prohibited from being used to benefit the performance of any other Tasks such as "ASR_track1" and "SD_track_1".

4. All ground truth labels and system submisions follow similar protocols as described in FEARLESS STEPS CHALLENGE PHASE-1 EVALUATION PLAN (https://go.aws/2Ha5mVq). Until further notice from the organisers (which shall be made available on the challenge website: https://fearless-steps.github.io/ChallengePhase2/), Participants are requested to use the information provided in the Evaluation plan and the Phase-1 Challenge website (http://fearlesssteps.exploreapollo.org/) to develop and evaluate their systems. 

5. All Challenge participants are required to submit a conference paper(s) describing their systems (and reporting performance on Dev and Eval sets) to the "FEARLESS STEPS CHALLENGE PHASE-2" special sessions section at ISCA INTERSPEECH-2020.

7. Researchers who intend to use FEARLESS STEPS corpus for other speech and language tasks outside the scope of Phase-2 Challenge are must also submit their paper(s) with system descriptions to the Special Sessions section for INTERSPEECH-2020.


----------------------------------------------------------------------------------------------


--- References ---
For the FEARLESS STEPS Corpus and Challenge:

@inproceedings{Hansen2019,
  author={John H.L. Hansen and Aditya Joglekar and Meena Chandra Shekhar and Vinay Kothapally and Chengzhu Yu and Lakshmish Kaushik and Abhijeet Sangwan},
  title={{The 2019 Inaugural Fearless Steps Challenge: A Giant Leap for Naturalistic Audio}},
  year=2019,
  booktitle={Proc. Interspeech 2019},
  pages={1851--1855},
  doi={10.21437/Interspeech.2019-2301},
  url={http://dx.doi.org/10.21437/Interspeech.2019-2301}
}

@inproceedings{Hansen2018,
  author={John H.L. Hansen and Abhijeet Sangwan and Aditya Joglekar and Ahmet E. Bulut and Lakshmish Kaushik and Chengzhu Yu},
  title={Fearless Steps: Apollo-11 Corpus Advancements for Speech Technologies from Earth to the Moon},
  year=2018,
  booktitle={Proc. Interspeech 2018},
  pages={2758--2762},
  doi={10.21437/Interspeech.2018-1942},
  url={http://dx.doi.org/10.21437/Interspeech.2018-1942}
}



--- Acknowledgments ---
This project was supported in part by  AFRL  under  contractFA8750-15-1-0205, NSF-CISE Project 1219130, and partially by the University of Texas at Dallas from the Distinguished University Chair in Telecommunications Engineering held by J.H. L. Hansen. We would also like to thank Tatiana Korelsky and the National Science Foundation (NSF) for their support on this scientific and historical project.
A special Thanks to Katelyn Foxworth for leading the ground-truth development efforts for the FS-02 Challenge Corpus.





----------------------------------------------------------------------------------------------



--- Creative Commons License (CC BY-SA 4.0) --- 
FEARLESS STEPS CHALLENGE by Aditya Joglekar, John H.L. Hansen is licensed under a Creative Commons Attribution-ShareAlike 4.0 International License. 
Based on a work at https://www.nasa.gov/mission_pages/apollo/apollo-11.html.
Permissions beyond the scope of this license may be available at https://www.nasa.gov/multimedia/guidelines/index.html.



--- Licensing Details --- 
All the conversations between Astronauts and and Mission Control Personnel during the Apollo-11 Mission were recorded by NASA. The tireless efforts of CRSS-UTD transcribers and researchers contributed to the shaping of this enormous amounts of data into a well-defined corpus to address various speech and language tasks for naturalistic audio, a portion of which is now made publicly available to the speech community through this Challenge via a creative commons license.

Note: The Creative Commons License is restricted to the efforts made by CRSS-UTD, which involves 100 hours of Challenge Corpus (audio) data sampled from 8Khz, along with its meta-data generated separately. The license also covers all the scripts which were used in the preparation of the corpus and systems built to support the tasks in this Challenge, along with the webpages developed to host the Challenge. 



The Entire Fearless Steps Corpus consisting of over 11,000 hours of audio from the Apollo-11 Mission is publicly available under the 'NASA Media Usage Guidelines'. Researchers interested in acquiring the entire corpus can directly contact us at FearlessSteps@utdallas.edu. 

--- NASA Media Usage Guidelines --- 
	Still Images, Audio Recordings, Video, and Related Computer Files for Non-Commercial Use:
		NASA content - images, audio, video, and computer files used in the rendition of 3-dimensional models, such as texture maps and polygon data in any format - generally are not copyrighted. You may use this material for educational or informational purposes, including photo collections, textbooks, public exhibits, computer graphical simulations and Internet Web pages. This general permission extends to personal Web pages.
		News outlets, schools, and text-book authors may use NASA content without needing explicit permission. NASA content used in a factual manner that does not imply endorsement may be used without needing explicit permission. NASA should be acknowledged as the source of the material. NASA occasionally uses copyrighted material by permission on its website. Those images will be marked copyright with the name of the copyright holder. NASA's use does not convey any rights to others to use the same material. Those wishing to use copyrighted material must contact the copyright holder directly.
	
	For Additional Information regarding Commercial and Non-Commercial Use:
		Please visit: https://www.nasa.gov/multimedia/guidelines/index.html




----------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------