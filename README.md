# Main_Challenge_Unit8
2022 Data Science Hackathon by Unit8. 

Our client GAM Pharm wants to reduce the overall processing time of each individual line by finding the optimal order the given jobs should be processed.
Each line has multiple unique modules and a single job has to pass through all modules of the line in chronological order. There are two buffers between two modules to temporarily store products. Each job travels through each module and can NOT overtake another, preceding job. However, the job can rest in one of the two buffer zones if the subsequent module is still processing another job.
In the beginning of each day, GAM Pharm knows exactly which jobs have to be processed by which production line until the end of the day.

Keep in mind:
Have a consultant mindset! Beside solving the problem also think of how to sell/present your ideas, compensate the lack of CS knowledge of your client, come up with further ideas, insights and hypotheses and present these in your final presentation.
The data you get in the first place is the log file of one day of manufacturing with the following Columns:

- line: the line from which this row stems
- module: the module inside the line from which this row stems
- state: what the module does at this point:     
     - processing: processing a job     
     - idle: finished up all jobs     
     - waiting_on_precedent: can’t continue because the next job has not yet arrived     
     - waiting_on_next: can’t continue because the job has been processed and can’t be given to the buffer, since the buffer is full     
     - fetching_job: fetch the next job     
     - storing_job: store the job that the module just finished processing in the next buffer (there is no buffer after the last module)
- time: the timestamp the event/state occured
Every time you call the API you will get:
- submission_id: the id of your submission
- avg_score: an average of the processing time of the four lines
- score_line_A: the processing time of line A
- score_line_B: the processing time of line B
- score_line_C: the processing time of line C
- score_line_D: the processing time of line D
- log: a log file containing all information of the processing of all modules (as dictionary) with the same content as the first log file you received

Submission Format is the usual /submit endpoint formatting, with:
data={"job_order": A dictionary of string keys (the letter of the line in capitals) and a list of integers (the order of jobs)}
An example data is {"job_order": {"A": [1, 5, 3], "B": [2, 7, 15], "C": [8, 11, 4], …}}

Data:
Data of first log can be found in the initial archive file you received.
