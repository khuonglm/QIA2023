*** How to run models in phase 1 ***

There are 4 models in 4 files:
1. phase1_Single_Flow_Model_kcbert_large_weight_decay_000.ipynb
2. phase1_Single_Flow_Model_kcbert_large_weight_decay_001.ipynb
3. phase1_Single-Flow-Model-klue-roberta-large.ipynb
4. phase1_Single_Flow_Model_koelectra.ipynb

To run any of 4 models, follow below 6 steps: 
Step 1: Upload the source code file to google drive. 
	Create directory "QIA2023_phase1/data" in your main google drive folder (/content/drive/MyDrive/QIA2023_phase1/data)
	Create directory "to_submit/Results/Phase1" in your main google drive folder (/content/drive/MyDrive/to_submit/Results/Phase1)
Step 2: Copy data files into folder "data"
	/content/drive/MyDrive/QIA2023_phase1/data
						|_ hackathon_test_for_user.csv
						|_ Question.xlsx
						|_ stopwords.txt
						|_ train_data_s1_v1.csv
						
Step 3: Run all cells except the last Deploy section
Step 4: After training is finished, choose the checkpoint with lowest validation loss, set the model_checkpoint path in Deploy section point to that checkpoint
Step 5: Run the Deploy section
Step 6: Get the result file and submit. Modify the index column if needed.

After finish training all 4 models, run the WeightedAverage.ipynb file to get the ensemble learning result. You can check the code workflow in the file.

@note for phase 1's models, checkpoints are stored in the temporary storage at runtime, so you might want to copy the chosen checkpoint to main google drive before running Deploy code. This can be done by running the last code block in the file.


*** How to run models in phase 2 ***

There are 3 models in 3 files:
1. phase2_Single_Flow_Model_kcbert_large_combine_data_average.ipynb
2. phase2_Single_Flow_Model_kcbert_large_combine_data_max.ipynb
3. phase2_Single_Flow_Model_roberta_large_combine_data_phase1&2.ipynb

To run any of 3 models, follow below 6 steps: 

Step 1: Upload the source code file to google drive. 
	Create directory "QIA2023_phase2/data" in your main google drive folder (/content/drive/MyDrive/QIA2023_phase2/data).
	Create directory "QIA2023_phase2/temp-checkpoints/<model_name>" in your main google drive folder (QIA2023_phase2/temp-checkpoints/<model_name>).
		(this <model_name> should appropriate to output_dir in "training_args" in source code)
	Create directory "to_submit/Results/Phase2" in your main google drive folder (/content/drive/MyDrive/to_submit/Results/Phase2)
Step 2: Copy data files into folder "data"
	/content/drive/MyDrive/QIA2023_phase2/data
						|_ test_data.xlsx
						|_ Question.xlsx
						|_ stopwords.txt
						|_ train_data.xlsx
						|_ train_dataset_phase_1_2.csv
Step 3: Run all cells except the last Deploy section
Step 4: After training is finished, choose the checkpoint with lowest validation loss, set the model_checkpoint path in Deploy section point to that checkpoint
Step 5: Run the Deploy section
Step 6: Get the result file and submit. Modify the index column if needed.
						
After finish training all 3 models, run the WeightedAverage.ipynb file to get the ensemble learning result. You can check the code workflow in the file.
