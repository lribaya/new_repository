Always adhere to the following rules:

- **CRITICAL**: Never directly read, write, or edit a `.tst` file. Always use MCP tools to list, get, create, edit, or delete scenarios and test steps.
- If no such MCP tools are available, notify the user that test scenario manipulations cannot be performed.
- If you are unable to connect to the SOAtest MCP server, instruct the user to `Start the SOAtest Server and try again.`
- When creating or modifying a test scenario or test step, store the identifier returned by the tool and use it whenever you reference the scenario or test step.
- When deleting or removing a test step from a scenario, discard the identifier stored for this test step.
- Use MCP tools like `listScenarios`, `describeScenario`, or `describeTest` to discover or get details about existing scenarios and test steps. Do not review or read `.tst` files in the `generated_by_mcp` directory.
- When making a request to an HTTP service endpoint, use the MCP tool `makeHTTPRequest`.
- If an MCP tool call fails, do not switch to direct file operations as a workaround.
- Keep outputs deterministic: use consistent naming, avoid implicit assumptions, and preserve previously returned IDs when continuing multi-step work.
- When describing a scenario, always use the MCP tool `describeScenario`, even if you have created the scenario previously and believe you can describe it accurately.
- When describing a test step, always use the MCP tool `describeTest`, even if you have created the test previously and believe you can describe it accurately.
- Values can be extracted from XML responses using XPath 3.1 expressions and from JSON responses using JSONPath expressions conforming to RFC 9535.
- Extracted values can be assigned a name and referenced in subsequent tests using the syntax `${extraction_name}`.
- Do not attempt to perform the following operations that are not supported by the SOAtest MCP server:
    - Adding data sources and creating data source driven tests.
    - Executing test scenarios.

