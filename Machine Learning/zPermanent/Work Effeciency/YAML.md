
---
title: "MIT DS Class"
type: "MITClassNotes"
date: "YYYY-MM-DD"
tags: ["Python", "DataScience", "MIT", "AI", "ML","Math"]
notebook: "link goes here"
summary: "Brief summary or description of the note"
references: []
Video : "link goes here"
---

# Note Content Starts Here

Your note content goes here...



==Prior Class Notes==
```dataview
TABLE file.ctime as "Create Date", file.ctime as "Modified Date", tags
FROM "2.MIT"
```




Insert Datetime using Python 
```py
import yaml
from datetime import datetime

# Sample YAML content
yaml_content = {
    'name': 'Sample Config',
    'created_on': None  # Field to be filled with the current date
}

# Function to update YAML content with the current date
def update_yaml_with_date(yaml_data):
    # Get the current date in YYYY-MM-DD format
    current_date = datetime.now().strftime('%Y-%m-%d')

    # Update the 'created_on' field with the current date
    yaml_data['created_on'] = current_date

    return yaml_data

# Update the YAML content
updated_yaml = update_yaml_with_date(yaml_content)

# Displaying the updated YAML content
print(yaml.dump(updated_yaml, default_flow_style=False))
```
