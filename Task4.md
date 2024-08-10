# Automate a pipline to trigger every last Saturday of the month

References :-
1. https://learn.microsoft.com/en-us/answers/questions/371452/trigger-adf-pipeline-on-second-friday-from-end-of

2. https://stackoverflow.com/questions/67253915/trigger-azure-data-factory-pipeline-on-second-friday-from-end-of-month-and-on-tu

We can use a combination of ADF triggers and custom logic to determine the appropriate date.

Azure Data Factory does not natively support complex date-based triggers like "last Saturday of the month." However, you can achieve this by creating a **Custom trigger**

1. Go to the Manage tab in your Data Factory.

2. Click on Triggers and then click + New.

3. Set up the trigger to run every Saturday:

    - Trigger type: Schedule
    Recurrence: Weekly
    - Days: Saturday
    - Start time: Set the start time according to your preference.
    - Time zone: Set the appropriate time zone.
    - Advanced recurrence settings: Leave default.

Attach this trigger to your pipeline. In the pipeline, click `Add trigger > New/Edit`.
    Select the trigger you just created and save.

Just use Occurrance as -1(reverse indexing of day) and day as Saturday in the Scheduled trigger and add to a pipeline to trigger,
```json
"schedule": {
    "monthlyOccurrences": [
        {
            "day": "Saturday",
            "occurrence": -1
        }
    ]
}
```