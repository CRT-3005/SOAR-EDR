# SOAR-EDR

## Objective

This project demonstrates the creation of a Security Orchestration, Automation, and Response (SOAR) playbook integrated with an Endpoint Detection and Response (EDR) solution.

- Tines is used to build the interactive playbook.
- LimaCharlie serves as the EDR platform.
- Slack is used for alerting and user interaction.
- A Windows Server 2022 VM hosts the LimaCharlie agent.
- LaZagne, a password recovery tool, is used to generate telemetry for detection.

## Skills Learned

- Deploying LimaCharlie agents on Windows Server.
- Creating detection rules for suspicious activity (LaZagne).
- Building a SOAR playbook in Tines.
- Integrating Slack with Tines for alerting and decision-making.
- Using REST APIs to automate endpoint isolation.
- Understanding EDR telemetry and event flow.
  
## Tools Used

- VirtualBox for VM setup.
- Windows Server 2022 for endpoint simulation.
- LimaCharlie for EDR.
- Tines for SOAR playbook creation.
- Slack for alerting and interaction.
- LaZagne for simulating credential dumping activity.

## Workflow Overview

1. Install LimaCharlie Agent on Windows Server.
2. Run LaZagne to simulate suspicious activity.
3. Create Detection Rules in LimaCharlie for LaZagne processes.
4. Trigger Events and forward them to Tines via Webhook.
5. Tines Playbook processes the event and sends alerts to Slack.
6. Slack User Prompt allows manual decision (e.g., isolate endpoint).
7. Tines uses REST API to isolate the endpoint via LimaCharlie.
8. Status Updates are sent back to Slack.

## Steps

![SOAR-EDR-Playbook](https://github.com/user-attachments/assets/24a936b4-9eae-4efc-87b2-d0769b3de649)

**Figure 1 – SOAR/EDR Playbook Diagram:** - Visual overview of the playbook flow between LimaCharlie, Tines, and Slack.

![LC-InstallationKey](https://github.com/user-attachments/assets/a63f9f21-fbac-4b99-920a-b72b83abc110)

**Figure 2 – LimaCharlie Installation Key:** - Key used to deploy the LimaCharlie agent on the Windows Server.  

![LC-AgentInstalled](https://github.com/user-attachments/assets/7b386d9c-3a6c-450c-ab49-7b55ace674b0)

**Figure 3 – Agent Installed on Windows Server:** - Confirmation of successful agent deployment.

![LC-ServerSensor](https://github.com/user-attachments/assets/c6f1061c-3407-459d-90de-ecdc134fb59c)

**Figure 4 – Server Reporting to LimaCharlie:** - Endpoint telemetry visible in the LimaCharlie dashboard. 

![LC-SensorDetails](https://github.com/user-attachments/assets/c61d903a-2021-4c3c-8f31-e9cac76a1bad)

**Figure 5 – Endpoint Sensor Details:** - Metadata and system info pulled from the agent.

![LC-DetectRule](https://github.com/user-attachments/assets/90a03e10-52f6-4ea7-8eb2-6ab1d404832e)

**Figure 6 – Detection Rule for LaZagne:** - Rule created to detect suspicious LaZagne activity.

![LC-RespondRule](https://github.com/user-attachments/assets/ef47df89-42cd-4c51-9da3-28f11e3b924b)

**Figure 7 – Response Rule Configuration:** - Automated response logic tied to detection events.

![LC-CopyNewProcess](https://github.com/user-attachments/assets/1933b6fa-ba94-4f5d-9540-689f1154a530)

**Figure 8 – New Process Event for LaZagne.exe:** - Event triggered by LaZagne execution.

![LC-TargetEvent1](https://github.com/user-attachments/assets/a689cf9b-1aae-42b1-b2d4-09659bfa3747)

**Figure 9 – Target Event Details:** - Specific telemetry captured from the LaZagne process.

![LC-EventTestResults1](https://github.com/user-attachments/assets/ddd60c78-a006-46fd-b2d2-6b531af04535)

**Figure 10 – Event Test Results:** - Output from testing the detection rule.

![LC-NewProcessLazagne](https://github.com/user-attachments/assets/ec5a6c32-5ef0-40a2-8cad-49c07934666d)

**Figure 11 – LaZagne Process Event ID:** - Unique identifier for the triggered event.

![LC-LaZagneDetections](https://github.com/user-attachments/assets/98f0f7b9-49b4-4134-aec7-84193a375e61)

**Figure 12 – LaZagne Detection Summary:** - Overview of detection events related to LaZagne.

![LC-LaZagneDetectionEvent1](https://github.com/user-attachments/assets/97e28eb1-bcac-41c9-905a-9ec20779c119)

**Figure 13 – LaZagne Detection Event (1):** - First instance of LaZagne detection.

![LC-LaZagneDetectionEvent2](https://github.com/user-attachments/assets/b64b53bc-df4b-4a5d-a318-6707736d007b)

**Figure 14 – LaZagne Detection Event (2):** - Second instance of LaZagne detection.

![TinesWebhook](https://github.com/user-attachments/assets/a0408d9a-f36b-459f-99d1-fe84d972fdaa)

**Figure 15 – Tines Webhook Creation:** - Webhook setup in Tines to receive LimaCharlie alerts.

![LC-AddingTinesWebhook](https://github.com/user-attachments/assets/a7c9c12d-25b4-4c32-bece-93b0b861a835)

**Figure 16 – Linking Webhook to LimaCharlie:** - Integration of Tines webhook into LimaCharlie.

![LC-TinesOutput](https://github.com/user-attachments/assets/c94e5ea4-1948-47e5-83a2-314aeec10f53)

**Figure 17 – Tines Output Example:** - Sample output from Tines after receiving an alert.  

![LinkfromLCtoTines1](https://github.com/user-attachments/assets/5b124ff4-c38c-4a42-88d0-a3f418ec5d2a)

**Figure 18 – LimaCharlie to Tines Output (1):** - Alert data forwarded from LimaCharlie to Tines. 

![LinktoLCtoTines3](https://github.com/user-attachments/assets/16f719d0-4e44-4bc0-bc52-b80c1e5ec818)

**Figure 19 – LimaCharlie to Tines Output (2):** - Additional alert data forwarded.

![LinkbetweenSlack Tines](https://github.com/user-attachments/assets/43674f9e-806b-4e5b-862f-38f5c924012c)

**Figure 20 – Slack Credentials in Tines:** - Slack integration setup for alerting.

![Slack-Webhook-Test](https://github.com/user-attachments/assets/ab99b7d9-3ebc-47a8-b4fd-2fbf85e34779)

**Figure 21 – Slack Webhook Test (1):** - Initial test of Slack alert delivery.

![MessagefromTines-Slack](https://github.com/user-attachments/assets/cc1555fe-c5ba-42af-b46f-a774aa64ca7a)

**Figure 22 – Slack Webhook Test (2):** - Confirmation of Slack message delivery.

![SendTestEmail](https://github.com/user-attachments/assets/d6a21317-1d2d-4248-aebb-62e3af0743e9)

**Figure 23 – Test Email Setup in Tines:** - Email alert configuration for playbook output.

![TinesTestEmail](https://github.com/user-attachments/assets/f94747ed-c480-444e-9be3-c30d4ca04cb9)

**Figure 24 – Test Email Received:** - Confirmation of email delivery.

![TinestoSlack-AllInfo](https://github.com/user-attachments/assets/6d6bfe74-934e-4ccc-9e22-f1edc7f5bc98)

**Figure 25 – Slack Message with Playbook Details:** - Edited Slack alert with full context. 

![Slack-Receieved-UserFriendly](https://github.com/user-attachments/assets/4932322b-0091-4077-a41b-4adfccb3054e)

**Figure 26 – Slack Message Received:** - Final Slack alert received by user.

![EditedEmail-NewLine](https://github.com/user-attachments/assets/1215518f-421a-4c3e-9504-81f23892ebd2)

**Figure 27 – Edited Email with Playbook Details:** - Email alert with full playbook context.

![InfoEmailReceived](https://github.com/user-attachments/assets/6755fb47-a26a-47a1-a0c0-71edd1c0f01d)

**Figure 28 – Information Email Received:** - Final email alert received.

![UserPromptSetup](https://github.com/user-attachments/assets/dd0ddbd7-c8de-429b-9732-7315fcffbdd6)

**Figure 29 – User Prompt Webpage Setup:** - Web interface for analyst decision-making.

![UpdatedUserPrompt](https://github.com/user-attachments/assets/0ee77064-f367-4197-8008-6ebc7d1375f2)

**Figure 30 – User Prompt Configuration:** - Tines setup for Slack-based user prompt.

![UpdateUserPromptWebpage](https://github.com/user-attachments/assets/de7c9b31-995c-48e4-97c2-3ab67ddba381)

**Figure 31 – User Prompt Webpage:** - Web interface for endpoint isolation decision.

![TinesNoTrigger](https://github.com/user-attachments/assets/956e7d38-e0d4-45ba-9761-eea957f64b41)

**Figure 32 – Tines Trigger for 'No' Action:** - Logic for handling a 'No' response.

![Slack-ComputerNotIsolated](https://github.com/user-attachments/assets/36d8e0c6-f6ff-4328-bd38-9118a2abc779)

**Figure 33 – Slack Message for 'No' Action:** - Alert confirming endpoint was not isolated.

![Slack-NotIsolated](https://github.com/user-attachments/assets/c7c451a8-fe0b-4d5d-9e46-f4fb8824b969)

**Figure 34 – Slack Message Received for 'No':** - Final Slack message for non-isolation.

![Tines-LimaCharlieSIDLink](https://github.com/user-attachments/assets/a497d562-3b0c-4c00-b8f9-0d557257d869)

**Figure 35 – Tines to LimaCharlie Sensor ID Link:** - Linking sensor ID for isolation action.

![Tines-LimaCharlie-Yes-SensorID](https://github.com/user-attachments/assets/d3708cd4-b82c-400c-979d-b50e15c555c6)

**Figure 36 – Sensor ID Result for 'Yes' Action:** - Output confirming endpoint selection.

![Tines-AddingLimaCharlieAPI](https://github.com/user-attachments/assets/22878491-94b2-4fb2-a48e-681027ad3322)

**Figure 37 – REST API Credentials in Tines:** - API integration for LimaCharlie actions.

![LimaCharlie-Isolated](https://github.com/user-attachments/assets/9eeb1446-b9d6-4a6b-8cbf-3fcfda3303eb)

**Figure 38 – Endpoint Isolated via LimaCharlie:** - Confirmation of successful isolation.

![Yes-LimaCharlie](https://github.com/user-attachments/assets/08a55fa1-114f-4441-a56b-1670c1a250bc)

**Figure 39 – Event ID for 'Yes' Response:** - Event ID tied to isolation action.

![AfterIsolationPingTest](https://github.com/user-attachments/assets/56bb84b4-7889-44bf-ac21-8476f98f1e33)

**Figure 40 – Ping Test After Isolation:** - Network test confirming isolation.

![NoLongerIsolatedPingTest](https://github.com/user-attachments/assets/852c7016-c443-4783-a6b1-6554f73caea0)

**Figure 41 – Ping Test After Reconnection:** - Network test confirming endpoint restored.

![Tines-LimaCharlie-GetIsolationStatus](https://github.com/user-attachments/assets/47a6ad92-e5f0-44c6-8913-5217ac6f5542)

**Figure 42 – Tines HTTP Request for Isolation Status:** - API call to check endpoint status.

![Tines-SlackGetIsolationStatus](https://github.com/user-attachments/assets/eed50821-3a2c-42e0-b083-c79e2c24d4f7)

**Figure 43 – Slack Message for Isolation Status:** - Alert showing current isolation state.

![Slack-IsolationStatusMessage](https://github.com/user-attachments/assets/6485e5cc-d5e5-408c-af15-f639469a771a)

**Figure 44 – Slack Isolation Status Message:** - Final Slack message with endpoint status.

![Tines-FullPlaybook](https://github.com/user-attachments/assets/8485e01a-25da-402e-b648-ad19fd56a9b4)

**Figure 45 – Full Tines Playbook View:** - Complete playbook showing all steps and integrations.

Outcomes
- Successfully detected and responded to simulated credential dumping
- Automated alerting and endpoint isolation via API
- Demonstrated full SOAR workflow from detection to analyst decision and remediation
- Strengthened understanding of how SOAR and EDR platforms integrate in real-world SOC environments
