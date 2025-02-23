# SOAR-EDR

## Objective

This Project creates a SOAR EDR Playbook. Tines is used to create the interactive playbook. LimaCharlie is used as the EDR. Slack is used to generate alerts. Windows Server 2022 VM is used with LimaCharlie agent. LaZagne password recovery tool used on VM to generate telemetry viewed in LimaCharlie. Tines used Webhook to link into LimaCharlie under Outputs.

## Skills Learned

- How to create a SOAR EDR playbook.
- How to add LimaCharlie endpoint onto Windows Server.
- How to inspect events generated from the server in LimaCharlie.
- How to install LaZagne and then creating a specific rule to check processes relating to LaZagne.
- Using Tines to create links between LimaCharlie and Slack.
- How to generate alerts on Slack.
- Setting up trigger links on Tines.
  
## Tools Used

- LimaCharlie
- Virtual Box with Windows Server 2022
- LaZagne
- Slack
- Tines

## Steps

![SOAR-EDR-Playbook](https://github.com/user-attachments/assets/24a936b4-9eae-4efc-87b2-d0769b3de649)

Ref 1: SOAR EDR Playbook diagram

![LC-InstallationKey](https://github.com/user-attachments/assets/a63f9f21-fbac-4b99-920a-b72b83abc110)

Ref 2: Installation Key on LimaCharlie

![LC-AgentInstalled](https://github.com/user-attachments/assets/7b386d9c-3a6c-450c-ab49-7b55ace674b0)

Ref 3: LimaCharlie agent installed on Windows Server

![LC-ServerSensor](https://github.com/user-attachments/assets/c6f1061c-3407-459d-90de-ecdc134fb59c)

Ref 4: Server reporting in to LimaCharlie

![LC-SensorDetails](https://github.com/user-attachments/assets/c61d903a-2021-4c3c-8f31-e9cac76a1bad)

Ref 5: Details pulled in about Server from endpoint agent

![LC-DetectRule](https://github.com/user-attachments/assets/90a03e10-52f6-4ea7-8eb2-6ab1d404832e)

Ref 6: Detection Rule

![LC-RespondRule](https://github.com/user-attachments/assets/ef47df89-42cd-4c51-9da3-28f11e3b924b)

Ref 7: Response Rule

![LC-CopyNewProcess](https://github.com/user-attachments/assets/1933b6fa-ba94-4f5d-9540-689f1154a530)

Ref 8: New Process event for Lazagne.exe all

![LC-TargetEvent1](https://github.com/user-attachments/assets/a689cf9b-1aae-42b1-b2d4-09659bfa3747)

Ref 9: Target event

![LC-EventTestResults1](https://github.com/user-attachments/assets/ddd60c78-a006-46fd-b2d2-6b531af04535)

Ref 10: Event test results

![LC-NewProcessLazagne](https://github.com/user-attachments/assets/ec5a6c32-5ef0-40a2-8cad-49c07934666d)

Ref 11: New process event ID

![LC-LaZagneDetections](https://github.com/user-attachments/assets/98f0f7b9-49b4-4134-aec7-84193a375e61)

Ref 12: LaZagne detections

![LC-LaZagneDetectionEvent1](https://github.com/user-attachments/assets/97e28eb1-bcac-41c9-905a-9ec20779c119)

Ref 13: LaZagne detection event (1)

![LC-LaZagneDetectionEvent2](https://github.com/user-attachments/assets/b64b53bc-df4b-4a5d-a318-6707736d007b)

Ref 14: LaZagne detection event (2)

![TinesWebhook](https://github.com/user-attachments/assets/a0408d9a-f36b-459f-99d1-fe84d972fdaa)

Ref 15: Tines webhook creation

![LC-AddingTinesWebhook](https://github.com/user-attachments/assets/a7c9c12d-25b4-4c32-bece-93b0b861a835)

Ref 16: Linking Tines webhook into LimaCharlie

![LC-TinesOutput](https://github.com/user-attachments/assets/c94e5ea4-1948-47e5-83a2-314aeec10f53)

Ref 17: Tines output

![LinkfromLCtoTines1](https://github.com/user-attachments/assets/5b124ff4-c38c-4a42-88d0-a3f418ec5d2a)

Ref 18: Example output from LimaCharlie to Tines (1)

![LinktoLCtoTines3](https://github.com/user-attachments/assets/16f719d0-4e44-4bc0-bc52-b80c1e5ec818)

Ref 19: Example output from LimaCharlie to Tines (2)

![LinkbetweenSlack Tines](https://github.com/user-attachments/assets/43674f9e-806b-4e5b-862f-38f5c924012c)

Ref 20: Slack credentials added to Tines

![Slack-Webhook-Test](https://github.com/user-attachments/assets/ab99b7d9-3ebc-47a8-b4fd-2fbf85e34779)

Ref 21: Testing Slack webhook (1)

![MessagefromTines-Slack](https://github.com/user-attachments/assets/cc1555fe-c5ba-42af-b46f-a774aa64ca7a)

Ref 22: Testing Slack webhook (2)

![SendTestEmail](https://github.com/user-attachments/assets/d6a21317-1d2d-4248-aebb-62e3af0743e9)

Ref 23: Test email setup

![TinesTestEmail](https://github.com/user-attachments/assets/f94747ed-c480-444e-9be3-c30d4ca04cb9)

Ref 24: Test email received

![TinestoSlack-AllInfo](https://github.com/user-attachments/assets/6d6bfe74-934e-4ccc-9e22-f1edc7f5bc98)

Ref 25: Edited Slack message to include all Playbook details

![Slack-Receieved-UserFriendly](https://github.com/user-attachments/assets/4932322b-0091-4077-a41b-4adfccb3054e)

Ref 26: Slack message received

![EditedEmail-NewLine](https://github.com/user-attachments/assets/1215518f-421a-4c3e-9504-81f23892ebd2)

Ref 27: Email edited to include all Playbook details

![InfoEmailReceived](https://github.com/user-attachments/assets/6755fb47-a26a-47a1-a0c0-71edd1c0f01d)

Ref 28: Information email received

![UserPromptSetup](https://github.com/user-attachments/assets/dd0ddbd7-c8de-429b-9732-7315fcffbdd6)

Ref 29: Webpage added in for User Prompt

![UpdatedUserPrompt](https://github.com/user-attachments/assets/0ee77064-f367-4197-8008-6ebc7d1375f2)

Ref 30: User Prompt config

![UpdateUserPromptWebpage](https://github.com/user-attachments/assets/de7c9b31-995c-48e4-97c2-3ab67ddba381)

Ref 31: User Prompt Webpage

![TinesNoTrigger](https://github.com/user-attachments/assets/956e7d38-e0d4-45ba-9761-eea957f64b41)

Ref 32: Trigger added to Tines for 'No' action

![Slack-ComputerNotIsolated](https://github.com/user-attachments/assets/36d8e0c6-f6ff-4328-bd38-9118a2abc779)

Ref 33: Slack message setup linking with 'No' action

![Slack-NotIsolated](https://github.com/user-attachments/assets/c7c451a8-fe0b-4d5d-9e46-f4fb8824b969)

Ref 34: Slack message received to not isolate computer

![Tines-LimaCharlieSIDLink](https://github.com/user-attachments/assets/a497d562-3b0c-4c00-b8f9-0d557257d869)

Ref 35: Tines to LimaCharlie Sensor ID link

![Tines-LimaCharlie-Yes-SensorID](https://github.com/user-attachments/assets/d3708cd4-b82c-400c-979d-b50e15c555c6)

Ref 36: Sensor ID result for clicking 'Yes' as the response

![Tines-AddingLimaCharlieAPI](https://github.com/user-attachments/assets/22878491-94b2-4fb2-a48e-681027ad3322)

Ref 37: Using REST API from LimaCharlie to link credentials into Tines

![LimaCharlie-Isolated](https://github.com/user-attachments/assets/9eeb1446-b9d6-4a6b-8cbf-3fcfda3303eb)

Ref 38: After clicking 'Yes' response on User Prompt the Server gets isolated from the network

![Yes-LimaCharlie](https://github.com/user-attachments/assets/08a55fa1-114f-4441-a56b-1670c1a250bc)

Ref 39: Event ID from 'Yes' response

![AfterIsolationPingTest](https://github.com/user-attachments/assets/56bb84b4-7889-44bf-ac21-8476f98f1e33)

Ref 40: Pinging from Server after its been isolated from the network

![NoLongerIsolatedPingTest](https://github.com/user-attachments/assets/852c7016-c443-4783-a6b1-6554f73caea0)

Ref 41: Pinging from Server after it has been removed from isolation

![Tines-LimaCharlie-GetIsolationStatus](https://github.com/user-attachments/assets/47a6ad92-e5f0-44c6-8913-5217ac6f5542)

Ref 42: Tines HTTP request to get isolation status

![Tines-SlackGetIsolationStatus](https://github.com/user-attachments/assets/eed50821-3a2c-42e0-b083-c79e2c24d4f7)

Ref 43: Slack message created to send isolation status message

![Slack-IsolationStatusMessage](https://github.com/user-attachments/assets/6485e5cc-d5e5-408c-af15-f639469a771a)

Ref 44: Slack isolation status message

![Tines-FullPlaybook](https://github.com/user-attachments/assets/8485e01a-25da-402e-b648-ad19fd56a9b4)

Ref 45: Tines full Playbook
