Contributing to Revmate
Thank you for your interest in contributing to Revmate! This document will guide you through the process of contributing.
Getting Started
Prerequisites
[List any necessary software/tools, like specific versions of Git, Node.js, etc.]
Access to the  https://gitlab.com/doyield-projects.
Jira account for issue tracking and sprint planning.
Setup
Install Dependencies:
    npm install

Set Up Environment:
Copy the example environment configuration:
    cp .env.example .env

Modify .env as needed for your local setup.
How to Contribute
Using Jira for Task Management
Create a Jira Ticket:
Before starting any work, create a Jira ticket under the appropriate project. Ensure the ticket is well-detailed, including acceptance criteria, to facilitate proper tracking and review.
Assigning Yourself to a Jira Ticket:
If a ticket is already created and unassigned, assign it to yourself before beginning work.
Reporting Bugs
Report bugs by creating a Jira issue. Use the "Bug" issue type and include:
A clear and descriptive title.
Steps to reproduce the issue.
Expected vs. actual behaviour.
Any relevant logs or screenshots.
Suggesting Features
Suggest new features by creating a Jira issue under the "Feature" or "Improvement" issue type. Describe the feature's purpose and the value it will add to the project.

Commit Message Guidelines
To maintain a clear and consistent history, please follow these guidelines when writing commit messages:
Commit Message Format
Each commit message should be structured as follows:


Submitting Code Changes
Create a New Branch:
Name the branch using the Jira ticket ID for clarity:
    git checkout -b RMS-386-commenter-backend

Make Your Changes:
Ensure your code adheres to the project’s coding standards.
Commit Messages:
Write clear, descriptive commit messages, including the Jira ticket ID:
    git commit -m "RMS-384: [ADD] headers on controller functions"

Push and Merge Request:
Push your branch to GitLab:
    git push origin RMS-386-commenter-backend

Create a Merge Request (MR) in GitLab. The merge requests should be into branch Dev
Coding Standards
Follow the project's coding standards as defined in our style.md.
Ensure your code has header following https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html and includes unit tests where applicable.
Testing
Run tests locally before submitting your changes:
    npm test

Ensure that your changes do not break existing tests, and that all new functionality is covered by tests.
Documentation
Update or add to the documentation if your changes introduce new features, alter existing behaviour, or fix bugs.
Review Process
Code Review:
Once your Merge Request is submitted, it will be reviewed by at least one other team member.
Address any feedback and make necessary changes.
Approval:
After the review process, the MR will be approved and merged into the main branch.
Jira Updates:
Update the Jira ticket status to "Test" once the MR is merged.
Community and Communication
For any questions or discussions, use the dedicated project Teams channel.
