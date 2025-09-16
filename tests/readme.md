
# 🌪️ Testing the Orixás: A Guide to Quality

> "A storm tests the strength of the trees. A test suite ensures the resilience of our code."

---

## Our Philosophy

Welcome to the testing grounds for the Orixás Copilot Agents. In this project, quality is not an afterthought; it is a core principle. Our goal is to ensure that every agent and every piece of generated code is robust, reliable, and secure.

This directory contains all the necessary tools and configurations to validate the divine work of our agents. The spirit of **Iansã**, the Orixá of winds and storms, guides our efforts here, as she is the force that clears the way and reveals true strength.

---

### Our Arsenal of Tools

To conduct our tests effectively, we use a modern, powerful tech stack:

* **🧪 Vitest:** For fast and efficient unit & integration testing.
* **🎭 Playwright:** For robust end-to-end (E2E) testing that simulates real user flows in a browser environment.
* **📦 MSW (Mock Service Worker):** For intercepting and mocking API requests, ensuring our tests are isolated and deterministic.

---

### 🚀 How to Run Tests

Execute the test suites using the following commands from the project's root directory.

**Run Unit & Integration Tests:**
```sh
# Run the entire suite once
npm test

# Run tests in watch mode during development
npm run test:watch
````

**Run End-to-End Tests:**

```sh
# Run the E2E suite (requires a running dev server)
npm run test:e2e
```

-----

### 📂 Directory Structure

Our tests are organized to be clear and scalable. Here is the anatomy of our testing grounds:

<pre>
tests/
├── e2e/
│   └── example.spec.ts   \# End-to-end tests simulating user journeys.
├── integration/
│   └── agent-handoff.spec.ts \# Tests for interactions between agents or modules.
├── unit/
│   └── utils.spec.ts     \# Tests for individual, isolated functions.
└── mocks/
└── handlers.ts       \# Mock handlers for API requests.
</pre>

-----

### ✍️ Writing New Tests

Contributions are highly encouraged, and they are strongest when accompanied by tests. Please adhere to the following guidelines:

  * **Follow the Structure:** Place your test files in the appropriate directory (`unit`, `integration`, `e2e`).
  * **Cover Your Code:** All new features or bug fixes should include corresponding tests.
  * **Write Clear Descriptions:** A test should clearly explain what it is validating.

-----

## ✨ The Vision: The Coming of Iansã

> Currently, our testing process is a manual discipline, executed by our developers. However, this entire framework is being built in preparation for the arrival of **Iansã (The QA Agent)**.
>
> Her future domain will be to automate this process: running test suites on new contributions, performing security audits, and generating reports. Every test we write today sharpens the tools she will one day wield.


