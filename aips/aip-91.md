---
aip: 91
title: Aptos SDK E2E Test Suite
authors: var-meta
status: Draft
type: Informational
created: 19/06/2024
---

## AIP-91 - Aptos SDK E2E Test Suite 

### Summary

The Aptos ecosystem currently has multiple SDKs available for developers to interact with the Aptos blockchain. However, there is a noticeable discrepancy in the frequency of updates and the comprehensiveness of test cases among these SDKs. The TypeScript SDK stands out as the most actively maintained and thoroughly tested, while other SDKs lag behind in terms of new feature updates and test coverage. This inconsistency can lead to reduced reliability and correctness of the less frequently updated SDKs.

To address this issue, this proposal suggests the development of a centralized end-to-end (E2E) test suite for all Aptos SDKs. The primary objective is to ensure that all SDKs are consistently tested against a common set of test cases, thereby improving their overall quality and reliability.

By implementing this unified E2E test suite, the Aptos community can ensure that all SDKs are held to the same high standard of quality and reliability, regardless of the language or platform they target. This will ultimately benefit developers building applications on the Aptos blockchain, as they can have greater confidence in the SDKs they choose to use.

### High-level Overview

The proposed solution involves the following key steps:

- Extract E2E test cases from the TypeScript SDK and convert them into a structured format, such as a Markdown table, which will include test data, test steps, and expected output.
- Utilize a combination of AI-assisted tools and manual developer review to generate test scripts for each Aptos SDK based on the common test case table.
- Create a new dedicated repository to host the Aptos SDK E2E test suite. This repository will include submodules for each SDK repo, Markdown files containing the test cases, and test reports for each SDK indicating pass/fail results and any unimplemented features.
- Implement an automated testing process using GitHub Actions, which will trigger the execution of test scripts whenever a new version of an SDK is released. The test results will be automatically updated in the corresponding Markdown files within the repository.

This approach will ensure that all Aptos SDKs are consistently tested against the same set of E2E test cases, improving their correctness and reliability.

### Impact

This proposal will impact the following audiences:

- Aptos SDK developers: They will need to review and implement the generated test scripts for their respective SDKs.
- Aptos users: They will benefit from more reliable and consistently tested SDKs across different languages.

If this proposal is not accepted, the inconsistency in testing and updating of Aptos SDKs may persist, potentially leading to issues and reduced confidence in the SDKs.

### Specification and Implementation Details

1. Extract E2E test cases from the TypeScript SDK and convert them into a Markdown table format.
   - Use AI and manual review to identify and extract relevant test cases.
   - Create a Markdown table with columns for test data, test steps, and expected output.
  
| \#  | TEST DATA | TEST STEPS | EXPECTED OUTPUT |
| --- | --------- | ----- | ---------------- |
| 1   |           |       |                  |

2. Generate test scripts for each Aptos SDK using AI and developer review.
   - Utilize AI to generate initial test script templates based on the test case table.
   - Engage SDK developers to review and refine the generated test scripts.

3. Create a new repository for the Aptos SDK E2E test suite.
   - Set up submodules for each SDK repo.
   - Include Markdown files containing all test cases and test reports for each SDK.
   - Establish a clear directory structure for test scripts and related files.

4. Implement GitHub Actions for automated testing and reporting.
   - Create workflows to trigger test script execution whenever a new SDK version is released.
   - Update the test report Markdown files with pass/fail results and any unimplemented features.

| \#  | TEST DATA | TEST STEPS | EXPECTED OUTPUT | RESULT |
| --- | --------- | ----- | ---------------- | ---------- |
| 1   |           |       |                  | :+1: PASS |
| 2   |           |       |                  | :x: FAIL |
| 3   |           |       |                  | :x: UNIMPL |

### Timeline

- Implementation effort: Approximately 3 months
  - Month 1: Extract test cases and generate test scripts for python SDK
  - Month 2: Set up the new repository and integrate test scripts for other SDKs
  - Month 2: Implement GitHub Actions and finalize the test suite
