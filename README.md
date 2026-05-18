# Muhamad Hariyanto's Quality Assurance Portfolio
## Profile
Aspiring QA Engineer with experience in manual testing, game testing, API testing, and gameplay balancing.

This portfolio contains selected QA case studies demonstrating:
- Bug investigation & documentation
- Test case design
- Gameplay balancing analysis
- QA communication workflow
- Analytical thinking in game systems.

## QA Skills

- Manual Testing
- Black-box Testing
- Regression Testing
- API Testing (Postman)
- Bug Documentation
- Test Case Design
- Gameplay Balancing
- Jira & Notion
- Unity Game Understanding

# Featured QA Case Studies

| Case Study | Focus Area | Skills Demonstrated |
|---|---|---|
| Bug Report Investigation | Functional Testing | Reproduction, Severity Analysis, Documentation |
| Feature Test Suite | Test Design | Positive/Negative Cases, Coverage Thinking |
| Gameplay Balancing Feedback | Game QA | System Analysis, Economy Balancing |

# Case Study 1 — Item Drop System Bug

## Bug Information
- Bug ID: UH-069
- Category: Gameplay / Item System
- Severity: High
- Priority: Medium
- Frequency: 100% Reproducible

## Project Context
Unrivaled Heroes: 2.5D Brawler is a 2.5D side-scrolling beat-'em-up game where players control multiple heroes with unique abilities and combat styles.

The tested feature was the Item Drop System, where players can recover HP/MP by collecting items dropped from defeated enemies or destructible objects such as barrels.

## Bug Summary
Players are able to recover HP/MP multiple times from a single dropped item by repeatedly moving left and right while colliding with the item before it disappears.

## Environmnet
- Build Version: 2021.3.45.63631
- Platform: Windows Desktop
- Test Date: 06 February 2026
- Tester: Muhamad Hariyanto

## Reproduction Steps
1. Reduce the player's HP.
2. Consume HP Item, until it reaches approximately 8/10 or lower.
3. Locate a destructible barrel.
4. Destroy the barrel to trigger an HP item drop.
5. Move the character into the dropped HP item to collect it.
6. Continue moving left and right while maintaining collision with the item before it disappears.

## Expected Result
The player should only recover HP/MP item once from a single dropped item.

## Actual Result
The player is able to recover HP/MP item multiple times from the same item depending on movement speed and collision timing before the item disappears.


## Root Cause Analysis
Based on initial analysis, the issue may occur because the HP/MP pickup system uses OnTriggerEnter for item collection, while the dropped item remains active for a short duration after the first collision. This allows multiple collision triggers to occur before the object is removed or disabled.

## Evidence
<img width="400" height="225" alt="Bug-069" src="https://github.com/user-attachments/assets/b4bbce6a-00ca-4b2f-a1ba-3d5b6151dbaf" />

## Impact
This issue can significantly affect gameplay balance and player behavior.

Since players can repeatedly gain multiple HP/MP item from a single item drop, the bug may:
1. Reduce combat difficulty
2. Invalidate resource management mechanics
3. Encourage reckless gameplay
4. Negatively impact intended progression balance

If exploited consistently, players may become nearly unkillable during combat encounters, reducing the overall challenge and gameplay experience.

# Case Study 2 - Audio & Settings System Test Suite

## Feature Overview
This test suite focuses on the Audio & Settings System in Unirvaled Heroes: 2.5D Brawler. The tested features include:
1. Music volume settings
2. SFX volume settings
3. Pause menu interaction
4. Audio persistence after restarting the game
5. Audio playback validation

The purpose of this testing activity was to verify that the audio settings functioned correctly across gameplay sessions while maintaining consisten user experience and expected game behavior.

## Testing Scope

### Included Scope
1. Music volume adjustment
2. SFX volume adjustment
3. Pause menu functionality
4. Audio mute behavior
5. Audio persistence after restarting the game
6. UI button mapping visibility
7. Tutorial information consistency
8. Achievement validation

### Excluded Scope
1. Multiplayer audio synchronization
2. Hardware-specific audio driver issues
3. Voice chat systems
4. External audio devices

## Test Strategy
The testing process focused on validating both functional behavior and edge cases related toi the game's audio system and settings persistence.
The strategy included:
1. Functional Testing
2. Regression Testing
3. UI Validation
4. Settings Persistence Validation
5. Negative Testing
6. Gameplay Consistency Validation

Special attention was given to:
1. Audio behavior when values are set to zero
2. Persistence of player settigns after restarting the game
3. Consistency between UI information and actual gameplay behavior
4. Pause menu interaction reliability

## Test Cases
| ID | Scenario | Expected Result | Status |
| --- | --- | --- | --- |
| TC-001 | Change Music volume then cancel using ESC | Value should revert to previous setting | Fail |
| TC-002 | Set Music volume between 5%-40% | Music should still be audible | Fail |
| TC-003 | Restart game after changing audio settings | Settings should persist after restart | Fail |
| TC-004 | Set SFX volume to 0% | NO SFX sound should be generated | Fail |
| TC-005 | Open Pause menu | All movement contrrol mappings should be displayed correctly | Fail |
| TC-006 | Set Music volume between 50%-90% | Music volume changed | Success |

## Coverage Considerations
The testing process intentionally covered:

### Functional Validation
1. Audio settings adjusment

### Edge Cases
1. Audi value set to zero
2. Low audio percentage values
3. Restarting the game after settings changes

## Findings Summary
| Metric | Result |
| --- | --- |
| Total Bugs Reported | 6 |
| High Severity Issues | 2 |
| Medium Severity Issues | 3 |
| Low Severity Issues | 1 |
| Systems Tested | Audio, UI, Gameplay, Achievement, Collision |
| Testing Type | Functional & Regression |

## Key Findings

### 1. Audio Settings Persistence Issues
Several issues were identified where audio settings failed to save or apply correctly after restarting the game.

#### Impact
1. Reduces user experience consistency
2. Causes player frustration
3. Makes customization unreliable

### 2. Audio Mute Validation Failure
SFX and music systems continued generating audio under certain conditions despite volume being set to zero.

### Impact
1. Audio settings become unreliable
2. Reduces accessibility for players preferring muted gameplay

## QA Skills Demonstrated
1. Manual Testing
2. Functional Testing
3. Regression Testing
4. Edge Case Validation
5. Bug Documentation
6. Gameplay Analysis
7. Test coverage Planning
8. Severity & Priority Classification

## Tools Used
1. Notion
2. Microsoft Excel
3. GitHub
4. Windows Desktop Environment
