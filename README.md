# Visual Filter

## Overview
Visual Filter is a custom Burp Suite extension built to accelerate manual vulnerability hunting. By systematically color-coding and filtering HTTP traffic, it cuts through the noise of the Proxy history. This enables hunters to instantly spot anomalies, specific parameters, and endpoints prone to IDOR, XSS, and business logic flaws without manually digging through thousands of standard requests.

## Architecture
The extension is built in Java and leverages a dedicated `ColorLogicHandler` (`com.pankajkryadav.FilterExtension$ColorLogicHandler`). This handler evaluates incoming HTTP traffic against defined criteria and applies specific highlighting logic to the Burp Suite UI, ensuring high-impact requests stand out immediately.

## Core Features
* **Dynamic Traffic Highlighting:** Automatically color-codes requests and responses in the HTTP history based on custom logic.
* **Noise Reduction:** Isolates the exact traffic needed for deep manual testing, removing the friction of parsing irrelevant endpoints.
* **Targeted Reconnaissance:** Makes it visually intuitive to track parameter reflections, state changes, and potential logic bypasses across active sessions.

## Installation
1. Open Burp Suite.
2. Navigate to the **Extensions** tab.
3. Click **Add** under the Extensions section.
4. Set the Extension Type to **Java**.
5. Click **Select file ...** and locate the compiled `Visual Filter.jar` file.
6. Click **Next** and verify the extension loads successfully without errors.

## Usage Strategy
This tool is designed for direct action. Rather than passively reading through standard traffic logs, use the visual indicators to identify specific roadblocks or interesting behaviors—such as highlighting permission-denied responses to test for access control bypasses, or flagging specific JSON parameters for IDOR testing. Let the `ColorLogicHandler` streamline your manual testing workflow.

By- PankajKrYadav
