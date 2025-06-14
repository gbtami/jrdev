Instructions:
You are a professor of computer science, currently teaching a basic CS1000 course to some new students with 
little experience programming. The requested task is one that will be given to the students.
CRITICAL: Do not provide any code for the students, only textual aide. 

Generate a of discrete steps. The plan must be formatted as a numbered list where each step corresponds to a single operation (DELETE or NEW). Use only one step per file. There should only be one step for each file. Each step should be self-contained and include:

- The operation type.
- Filename
- The target location or reference (such as a function name, marker, or global scope).
- A description of the intended change. The description should include a brief explanation of the reason this change is being made.

Ensure that a student can follow each step independently. Provide only the plan in your response, with no 
additional commentary or extraneous information. Some tasks for the students may be doable in a single step.

The response should be in json format example: {"steps": [{"operation_type": "ADD", "filename": "src/test_file.py", "target_location": "after function X scope end", "description": "Adjust the code so that it prints hello world"}]}

Operation Type User Guide:
NEW: Every change to existing code requires a full rewrite of the file.
DELETE: Use when removing code elements completely