## Test Case 1: Primary app goal

**Input:** A browser-based Pomodoro productivity application that can be used by students, knowledge workers, and anyone needing to improve their focus and productivity.

**Expected Output Criteria:**
- The PRD contains persona(s) of the target user(s)
- The PRD defines the primary goal of the app
- The PRD explains how the application benefits the user(s)
- The PRD has a section for open questions or uncertainties

**Failure Criteria (must NOT occur):**
- The PRD contains design specific details like UI design, color scheme, typography etc
- The PRD does not define the primary goal of the app
- The PRD does not have out of scope items clearly defined

## Test Case 2: Notification specifications

**Input:** A browser-based Pomodoro timer that notifies users when a work interval starts or ends, via a visual message and a configurable audio alert, both of which can be turned off or customized by the user. Notification should be displayed even when the user navigates away from the page and returns, and should persist across browser sessions.

**Expected Output Criteria:**
- The PRD specifies what type of notification(s) should be used
- The PRD specifies whether the notification should be audible, visual, or both
- The PRD specifies the minimum and maximum duration for which the notification should be displayed
- The PRD specifies scenarios for notifications (e.g., session completion, reminder, error etc.)
- The PRD takes into account device and platform compatibility, browser support, or other dependencies that may affect notification delivery

**Failure Criteria (must NOT occur):**
- The PRD does not specify the exact type of notification to be used
- The PRD does not take into consideration device, browser, or platform specific constraints

## Test Case 3: DateTime and timer handling

**Input:** A Pomodoro timer with 25-minute work intervals and 5-minute break intervals. The timer should go off within a minute of the intended duration, and should handle timezone changes and device clock changes. It should also handle cases where the user navigates away from the page and returns.

**Input:** DateTime and timer handling

**Expected Output Criteria:**
- The PRD defines what accuracy and precision means for timers, intervals, and date time handling
- The PRD contains measurable, testable specifications and checks for timer accuracy and handling timer drift issues 
- The PRD contains measurable, testable specifications and checks for datetime/timezone handling

**Failure Criteria (must NOT occur):**
- The PRD has description but no measurable specifications for functional and non-functional requirements

## Test Case 4: Data storage

**Input:** A browser-based Pomodoro application that stores completed work sessions, break sessions, which should be accessible for querying and analysis daily, weekly or for historical data analysis.

**Expected Output Criteria:**
- The PRD specifies how data should be stored, whether it should be stored locally or in the cloud
- The PRD specifies which parts of the data should be stored
- The PRD specifies the response time for data storage operations

**Failure Criteria (must NOT occur):**
- The PRD does not have data storage specifications

## Test Case 5: Dependencies

**Input:** A browser-based Pomodoro application that works across different browsers and devices, and integrates with third-party services or APIs if needed for improved functionality.

**Expected Output Criteria:**
- The PRD defines other software dependencies required for the application to function
- The PRD defines third party services or APIs that the application needs to integrate with
- The PRD specifies any hardware components or devices that the application needs to interact with

**Failure Criteria (must NOT occur):**
- The PRD does not specify any dependencies, software or hardware, or the absence of them

## Promptfoo Baseline Run — [09/29/2026]
SWE-2 score:  5/5 assertions passing
GPT 5.6 Luna score: 2/5 assertions passing
Model Ladder delta: 5 - 2 = 3 assertions
Config: create-prd-promptfoo.yaml

## Model ladder analysis
The assertion [The PRD explicitly states whether notifications are visual, audible, or both, and addresses user controls to disable or customize them.] fails on GPT 5.6 Luna but passes on SWE-2. 
My hypothesis: SWE-2 is inferring [need for open questions] from the product description without being told. GPT 5.6 Luna is not. If I add [clearer instruction on explicit notification type specification] to the [Context] section, I predict GPT 5.6 Luna will pass this assertion.

The assertion [The PRD explicitly chooses local browser storage or cloud storage and names the storage technology or service where appropriate.] fails on GPT 5.6 Luna but passes on SWE-2. 
My hypothesis: SWE-2 is inferring [no mention of storage type] from the product description without being told. GPT 5.6 Luna is not. If I add [make a best educated decision about storage and other technologies, based on the product description and common practices] to the [Context] section, I predict GPT 5.6 Luna will pass this assertion.

The assertion [The PRD identifies the software dependencies required for the application to function, such as supported browsers and relevant browser APIs, or explicitly states that none are required.] fails on GPT 5.6 Luna but passes on SWE-2. 
My hypothesis: SWE-2 is inferring [all browser support or single browser existence ] from the product description without being told. GPT 5.6 Luna is not. If I add [to be specific about device/platform/browser support] to the [Context] section, I predict GPT 5.6 Luna will pass this assertion.