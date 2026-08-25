# EXPERIMENT 5

## AUDITING CLOUD ACTIVITY USING AWS CLOUDTRAIL

### Objective

To audit and monitor cloud activity in AWS using **AWS CloudTrail** by viewing and analyzing recorded AWS events and identifying important audit information such as:

- User identity
- Event name
- Event time
- AWS service
- Region
- Operation status

---

# 1. Requirements

- AWS Account
- Web Browser
- Internet Connection
- Amazon S3 Access
- AWS CloudTrail

---

# PART A — ACCESS AWS CLOUDTRAIL

## Step 1: Login to AWS

1. Open the **AWS Management Console**.
2. Sign in using your AWS account.
3. In the AWS search bar, type **CloudTrail**.
4. Select **AWS CloudTrail**.

### Screenshot 1: AWS CloudTrail Dashboard

<img width="1910" height="722" alt="image" src="https://github.com/user-attachments/assets/ba202075-56db-4a41-b154-d8fc37969d4b" />




## Step 2: Open Event History

1. In the CloudTrail navigation menu, select **Event history**.
2. CloudTrail displays recent AWS activity.
3. Review the available events.

The Event History page may display information such as:

- Event Time
- Username
- Event Name
- Event Source
- Resource Type
- Resource Name

### Screenshot 2: CloudTrail Event History

<img width="1902" height="911" alt="image" src="https://github.com/user-attachments/assets/1433a9ab-826b-4621-a3b9-e9f76427f208" />



# PART B — ANALYZE A CLOUDTRAIL EVENT

## Step 3: Select an Event

1. From the Event History list, select an S3-related event.
2. Click the event to open its details.
3. Examine the event information and the event record/JSON.

For this experiment, a **CreateKeyPair** event can be used.

---

## Step 4: Analyze the CreateKeyPair Event

The `CreateKeyPair` event indicates that an **Amazon EC2 bucket creation operation** occurred.

### CreateKeyPair Event Observation


### Meaning of Important Fields

<table border="1">
  <tr>
    <th>Field</th>
    <th>Meaning / Observation</th>
  </tr>

  <tr>
    <td>Event Time</td>
    <td>August 04, 2026, 13:55:44 (UTC+05:30) — Time at which the activity occurred</td>
  </tr>

  <tr>
    <td>User Name</td>
    <td>root — User/identity associated with the activity</td>
  </tr>

  <tr>
    <td>Event Name</td>
    <td>CreateKeyPair — AWS operation that was performed</td>
  </tr>

  <tr>
    <td>Event Source</td>
    <td>ec2.amazonaws.com — AWS service that generated the event</td>
  </tr>

  <tr>
    <td>AWS Region</td>
    <td>eu-north-1 — Region where the activity occurred</td>
  </tr>

  <tr>
    <td>Read-only</td>
    <td>false — The event involved a change/creation operation</td>
  </tr>

  <tr>
    <td>Error Code</td>
    <td>- — No error code was reported</td>
  </tr>
</table>

### Screenshot 3: CreateKeyPair Event Details

<img width="1915" height="712" alt="image" src="https://github.com/user-attachments/assets/65ff2603-27e2-4d84-a86b-144224f46ba0" />

---

# PART C — IDENTIFY ANOTHER CLOUDTRAIL EVENT

## Step 5: Select Another Event

1. Return to **CloudTrail → Event history**.
2. Select another event.
3. Open its details.
4. Record the important fields.

For example, an event such as:

`s3.amazonaws.com`

may be present.

This event is associated with **Amazon S3**.

---

## Step 6: Analyze the Second Event


### Screenshot 4: Second CloudTrail Event Details

<img width="1917" height="861" alt="image" src="https://github.com/user-attachments/assets/5a94d8fd-0835-41c4-842c-950993ca4034" />




# PART D — COMPARE THE EVENTS

## Step 7: Prepare the Audit Comparison

<h3>Compare the two CloudTrail events</h3>

<table border="1" cellpadding="8" cellspacing="0">
  <tr>
    <th>Parameter</th>
    <th>Event 1</th>
    <th>Event 2</th>
  </tr>

  <tr>
    <td>Event Time</td>
    <td>August 04, 2026, 13:55:44 (UTC+05:30)</td>
    <td>August 04, 2026, 13:43:59 (UTC+05:30)</td>
  </tr>

  <tr>
    <td>User Name</td>
    <td>root</td>
    <td>root</td>
  </tr>

  <tr>
    <td>Event Name</td>
    <td>CreateKeyPair</td>
    <td>CreateBucket</td>
  </tr>

  <tr>
    <td>Event Source</td>
    <td>ec2.amazonaws.com</td>
    <td>s3.amazonaws.com</td>
  </tr>

  <tr>
    <td>AWS Region</td>
    <td>eu-north-1</td>
    <td>eu-north-1</td>
  </tr>

  <tr>
    <td>Read-only</td>
    <td>false</td>
    <td>false</td>
  </tr>

  <tr>
    <td>Error Code</td>
    <td>-</td>
    <td>-</td>
  </tr>

  <tr>
    <td>Activity</td>
    <td>EC2 key pair creation</td>
    <td>S3 bucket creation</td>
  </tr>
</table>
---

# PART E — SECURITY AUDIT ANALYSIS


### RESULT?

Was the operation successful or did it generate an error?

---


## Step 8: Prepare the Final Audit Table

The final audit table summarizes the important details of both CloudTrail events:

<table border="1" cellpadding="8" cellspacing="0">
  <tr>
    <th>Event Time</th>
    <th>User</th>
    <th>Event Name</th>
    <th>Service</th>
    <th>Region</th>
    <th>Read-only</th>
    <th>Result</th>
    <th>Activity</th>
  </tr>

  <tr>
    <td>August 04, 2026, 13:55:44 (UTC+05:30)</td>
    <td>root</td>
    <td>CreateKeyPair</td>
    <td>Amazon EC2</td>
    <td>eu-north-1</td>
    <td>false</td>
    <td>Successful</td>
    <td>EC2 key pair creation</td>
  </tr>

  <tr>
    <td>August 04, 2026, 13:43:59 (UTC+05:30)</td>
    <td>root</td>
    <td>CreateBucket</td>
    <td>Amazon S3</td>
    <td>eu-north-1</td>
    <td>false</td>
    <td>Successful</td>
    <td>S3 bucket creation</td>
  </tr>
</table>

# RESULT

The cloud activities in AWS were successfully audited using **AWS CloudTrail Event History**.

Different AWS events were examined based on:

- Event time
- User identity
- Event name
- Event source
- AWS Region
- Read-only status
- Error status

The experiment demonstrated how **AWS CloudTrail** provides an audit trail for monitoring, accountability, and investigation of cloud activities.
