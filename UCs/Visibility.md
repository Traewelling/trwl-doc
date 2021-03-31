# 1 Use-Case Name
Visibility
## 1.1 Brief Description
Setting the visibility for your Check-Ins (private, public, unlisted, etc.)

Users want to be able to restrict the visibility of posts

# 2 Flow of Events
## 2.1 Basic Flow
- User is in the "check in" modal
- User selects from one of multiple visibility types (private, public, unlisted)
- User clicks "check in"

### 2.1.1 Activity Diagram
![Visibility work flow](../images/VisibilityDiagram.png)

### 2.1.2 Mock-up
![Visibility for your Travel](../images/visibility.png)

### 2.1.3 Narrative
```gherkin
Feature: user search

  As a signed in user
  i want to search for another user.

  Background:
    And I am on the check in modal

  Scenario: search user
    Given I am signed in with username "USER" and password "PASSWORD"
    And I am on the check in modal
    When I click the Visibility-Dropdown
    And I select any choice out of the mentioned
    And I click "EINCHECKEN!"
    Then I am on the "dashboard" page with a checkin report
```

## 2.2 Alternative Flows
(n/a)

# 3 Special Requirements
(n/a)

# 4 Preconditions
## 4.1 Login
The user has to be logged in to the system.

# 5 Postconditions
(n/a)
 
# 6 Extension Points
(n/a)