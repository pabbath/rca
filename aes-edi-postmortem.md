
## AES CIS Root Cause Analysis (Jira Issue No: AESEDI-53447)

## Date
2020-04-20

## Authors
Abhilash Pabbath

## Status
Done, Resolved

## Summary
1) The customer data was not sent from AES EDI - Jira issue (AESEDI-53447).
2) The file with the data was sent but, it did not get processed due to an issue with the AES CIS service.

## Business Impact
About 486,000 records were affected.

## Root Causes
1) Because of an issue with AES CIS (AESCIS-38263) the data didn't get processed on time.
2) As the server itself is down because of server patching. After the server patching operations team has forgotten to start the server and during that time the data didn’t get processed.
3) As the server was down this affected EDI to CIS monitoring service working on the CIS side

## Trigger
A large number of files were not processed.

## Resolution
1) After successfully staring the server EDI to CIS monitoring service alerted that the data was not sent.
2) Data was sent again to resolve the issue.

## Detection
A Jira issue is created by customer (AESEDI-53447)

## Action Items
| Action Item | Type | Owner | Bug |
| ----------- | ---- | ----- | --- |
| Alert teams about patching and other server related information | prevent | Abhilash Pabbath | **DONE** |
| Set up alerts when a server is down | prevent | Abhilash Pabbath| (Jira Issue No: AESCIS-38263) **TODO** |

## Lessons Learned
1) To Make sure to communicate teams by sending email notifications or Mattermost notifications.
2) Add monitoring scripts when a server goes down.

## Timeline
2020-04-11 (*all times UTC*)

| Time  | Description |
| ----- | ----------- |
| 11:56 | Discovering of the missing files |
| 12:00 | Restarting of the server |
| 12:15 | CIS monitoring service alerted that the files were not processed |
| 12:30 | Data processing was started |
| 13:00 | Missing records were processed |
