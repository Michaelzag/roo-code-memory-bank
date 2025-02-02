# Roo Code Memory Bank: User Guide and Instruction Modules
  2 |
  3 | **Maintain Project Context Across Sessions and Memory Resets**
  4 |
  5 | This guide will walk you through using the Roo Code Memory Bank system, enhanced by Roo Code's built-in context-preserving features. This combination provides a robust solution for managing project context across sessions and handling Roo's periodic memory resets.
  6 |
  7 | ## Before You Begin
  8 |
  9 | The Roo Code Memory Bank is your project's persistent memory. It helps Roo Code remember important project details across sessions and memory resets, enabling more effective and consistent assistance.
 10 |
 11 | By using the Memory Bank, you ensure Roo Code has the necessary context to understand your project, provide relevant suggestions, and maintain continuity in your development workflow.
 12 |
 13 | ## Getting Started
 14 |
 15 | Follow these steps to set up and begin using the Memory Bank system:
 16 |
 17 | ### Prerequisites
 18 | - VS Code with Roo Code extension installed (v1.2.0 or newer)
 19 | - Basic understanding of Markdown syntax
 20 | - Project folder setup in VS Code workspace
 21 |
 ### First-Time Setup Checklist
  1. **Create or Open** a project directory in VS Code. (This is your project directory in VS Code where you want to use the Memory Bank.)
  2. **Install** the Roo Code extension from the VS Code Marketplace. (Ensure you have the Roo Code extension installed from the VS Code Marketplace.)
  3. **Configure** custom instructions via Roo Code settings. (Refer to the Roo Code settings to paste the custom instructions for optimal Memory Bank functionality. This is a one-time setup.)
  4. **Switch to Architect Mode:** Switch to Architect mode in the Roo Code chat interface. (In the Roo Code chat, switch to Architect mode to begin Memory Bank initialization.)
  5. **Experience "Wakeup" Functionality:** In Architect mode, send any initial prompt to Roo Code (even a simple greeting or single character). Roo Code will automatically:
    - **Scan** your workspace for `memory-bank/` directories.
    - **Detect Multiple Projects (if applicable):** If multiple Memory Banks are found, Roo Code will prompt you to select the project for the session.
    - **Initialize/Load Memory Bank:** Roo Code will initialize or load the Memory Bank for the selected (or single) project.
    - **Respond with Greeting & Next Steps:** Roo Code will respond with a greeting and suggest a starting point for your architectural tasks.
  6. **(Optional but Recommended) Create `projectBrief.md`:**  Consider creating a `projectBrief.md` file at the root of your project. This file should briefly describe your project's goals, target audience, and key technologies. Providing a `projectBrief.md` enriches the initial context for Roo Code, leading to more relevant assistance.
  7. **Initiate Memory Bank Initialization in Architect Mode:** In Architect mode, ask 'Initialize Memory Bank' or 'Setup Memory Bank' if you want to explicitly re-initialize or review the Memory Bank setup. Otherwise, the "wakeup" functionality handles initial loading.
  8. **Switch to Code Mode:** Follow Roo Code's instructions and switch to Code mode as prompted. (Follow Roo Code's instructions and switch to Code mode as prompted.)
  9. **Create Memory Bank Files in Code Mode (Following Roo's Plan):** In Code mode, Roo Code will provide a detailed plan listing the `memory-bank/` directory and the necessary files to create. Use Roo Code's file creation tools to create these files exactly as outlined in the plan. Ensure the `memory-bank/` directory is at the root of your VS Code workspace.
  10. **Start Documenting:** Begin populating the newly created Memory Bank files with essential project information. Start with `productContext.md` to document the project overview and key technologies, and then update `activeContext.md` to reflect your current tasks and next steps.

 To further illustrate this process, refer to the workflow diagram below:
 34 |
 35 |
 36 | ### Memory Bank Initialization Workflow (Automatic)
 37 |
 38 | 1. **Start:** New Project in VS Code & Switch to Architect Mode
 39 | 2. **Step 1:** Roo Code (Architect Mode) detects missing `memory-bank/`
 40 | 3. **Step 2:** Roo Code (Architect Mode) presents Memory Bank Initialization Plan
 41 | 4. **Step 3:** User switches to Code Mode
 42 | 5. **Step 4:** User creates `memory-bank/` directory and files in Code Mode (following Roo's plan)
 43 | 6. **End:** Memory Bank Initialized & Active
 44 |
 45 |
 46 | ```
 47 |
 48 | ## Handling Multiple Projects in a Workspace
 49 |
 50 | If you have multiple projects with their own Memory Banks within your VS Code workspace, Roo Code can automatically detect them and prompt you to select the target project for the current chat session.
 51 |
 52 | **Automatic Project Detection and Selection:**
 53 |
 54 | 1.  **New Chat Session:** When you start a new chat session in Architect or Code mode, Roo Code scans your workspace for `memory-bank/` directories.
 55 |  2. **Multiple Memory Banks Found:** If multiple `memory-bank/` directories are detected, Roo Code will display a prompt in the chat asking you to choose the project you want to work on.
 56 |  3. **Project Selection Prompt:** The prompt will list the detected projects with their directory paths, like this:
 57 |
 58 |     ```
 59 |     Multiple Memory Banks detected in your workspace. Please specify which project you would like to work on for this session:
 60 |
 61 |     1.  Project: poptools-app (Directory: /var/www/poptools-app)
 62 |     2.  Project: Roo-Code (Directory: /var/www/Roo-Code)
 63 |     3.  Project: roo-code-memory-bank (Directory: /var/www/roo-code-memory-bank)
 64 |
 65 |     Please enter the number corresponding to your desired project.
 66 |     ```
 67 |
 68 |  4. **Select Your Project:** Enter the number corresponding to the project you want to work with and press Enter.
 69 |  5. **Context Loaded:** Roo Code will then load the Memory Bank for the selected project and use it for the current chat session.
 70 |
 71 | **Example Scenario:**
 72 |
 73 | Imagine you have a workspace with two projects: `webapp` and `mobile-app`, each with its own `memory-bank/` directory. When you start a new chat in Architect mode, Roo Code will detect both Memory Banks and ask you:
 74 |
 75 | ```
 76 | Multiple Memory Banks detected in your workspace. Please specify which project you would like to work on for this session:
 77 |
 78 | 1.  Project: webapp (Directory: /var/www/webapp)
 79 | 2.  Project: mobile-app (Directory: /var/www/mobile-app)
 80 |
 81 | Please enter the number corresponding to your desired project.
 82 | ```
 83 |
 84 | By selecting '1', you ensure that Roo Code uses the Memory Bank from your `webapp` project for this session.
 85 |
 86 | **Organizing Multi-Project Workspaces:**
 87 |
 88 | To effectively manage multiple projects with Memory Banks:
 89 |
 90 | *   **Keep Memory Banks at Project Roots:** Ensure each project has its `memory-bank/` directory at the root level of its project directory.
 91 | *   **Clear Project Names:** Use descriptive names for your project directories to easily identify them in the project selection prompt.
 92 | *   **Workspace Structure:** Organize your workspace so that project directories are clearly separated.
 93 |
 94 | This automatic project detection and selection feature simplifies working with multiple projects and ensures Roo Code always has the correct project context for each session.
 95 |
 96 | ## Understanding Memory Bank Files
 97 |
 98 | Initializing the Memory Bank creates a `memory-bank/` folder containing three essential files: `productContext.md`, `activeContext.md`, and `progress.md`. Here's a breakdown of each file's purpose:
 99 |
100 | ### `memory-bank/productContext.md`
101 |
102 | **Purpose:** Document the **stable, long-term project context.** Captures foundational knowledge consistent throughout the project.
103 |
104 | **Think of it as:** Project's "North Star" document. Provides enduring context.
105 |
106 | **Content Examples:**
107 | * **Project Vision/Goals:** Overall project aims and objectives.
108 | * **Target Audience:** Intended user base.
109 | * **Key Technologies:** Primary technologies, frameworks, libraries.
110 | * **High-Level Architecture:** Project's architectural design, main components.
111 | * **Domain-Specific Knowledge:** Relevant background info, domain expertise.
112 |
113 | **Update Frequency:** Infrequent. Update on significant shifts in project direction, target audience, or core tech stack.
114 |
115 | ### `memory-bank/activeContext.md`
116 |
117 | **Purpose:** Tracks **dynamic, short-term context** of your *current work & next steps*. Daily scratchpad for Roo Code.
118 |
119 | **Think of it as:** Your "Daily Task Log" for Roo. Keeps Roo focused on immediate priorities.
120 |
121 | **Content Examples:**
122 | * **Current Task/Feature:** Specific feature, bug fix, or task you're actively working on *now*.
123 | * **Immediate Next Steps:** Very next actions to progress on current task.
124 | * **Open Questions/Decisions:** Pending questions, decisions, roadblocks.
125 | * **Technical Details (Short-Term):** Temporary notes, code snippets, commands for current task.
126 | * **Session-Specific Notes:** Anything for Roo to remember *this session*.
127 |
128 | **Update Frequency:** Very frequent. Update at session start/end, and when focus shifts.
129 |
130 | ### `memory-bank/progress.md`
131 |
132 | **Purpose:** Provides **high-level project progress & status overview.** Tracks accomplishments and remaining tasks.
133 |
134 | **Think of it as:** Project's "Executive Summary". Quick snapshot of project status.
135 |
136 | **Content Examples:**
137 | * **Work Done:** Completed features, tasks, milestones (bullet points, short descriptions).
138 | * **To Do:** Concise list of remaining tasks/features.
139 | * **Current Status Summary:** Project's overall stage (e.g., "Alpha", "Beta", "Ready for release").
140 | * **Completion Metrics (Optional):** Simple metrics to track progress (e.g., "% core features complete").
141 | * **Milestones/Deadlines (Optional):** Key project milestones, target deadlines.
142 |
143 | **Update Frequency:** Regular. Update weekly or after significant progress.
144 |
145 | ## Advanced Usage Examples
146 |
147 | ### Memory Bank for Feature Development
148 |
149 | **Scenario:** Implementing User Authentication
150 |
151 | **Initial State:**
152 |
153 | You are starting to develop a new feature: user authentication for your application. The Memory Bank has already been initialized for your project, and you are ready to document the development process for this new feature within the Memory Bank. Currently, the application is publicly accessible without user accounts. You want to add user registration, login, and secure session management to enhance security and personalize the user experience.
154 |
155 | **Memory Bank Updates:**
156 |
157 | Throughout the feature development process, you would update your Memory Bank files as follows:
158 |
159 | *   **`memory-bank/productContext.md`**: Update this file to reflect the addition of the new feature and any relevant technology choices.
160 |
161 |     ```markdown
162 |     # memory-bank/productContext.md
163 |
164 |     ## Project Overview
165 |     This project is a [briefly describe your application - e.g., "task management web application"].
166 |     **We are adding user authentication to enhance security and personalize user experience.**
167 |
168 |     ## Key Technologies
169 |     - [List existing technologies]
170 |     - **OAuth 2.0 (for social login - *Decision needed: which provider?*)**
171 |     - **JWT (JSON Web Tokens) for session management**
172 |     - **bcrypt (for password hashing)**
173 |     ```
174 |
175 | *   **`memory-bank/activeContext.md`**:  Use this file to track the current tasks, next steps, and open questions related to the user authentication feature.
176 |
177 |     ```markdown
178 |     # memory-bank/activeContext.md
179 |
180 |     ## Current Task
181 |     Developing user authentication feature.
182 |
183 |     ## Next Steps
184 |     - 1. Plan database schema for user credentials.
185 |     - 2. Implement user registration API endpoint.
186 |     - 3. Implement user login API endpoint.
187 |     - 4. Implement JWT-based authentication middleware.
188 |
189 |     ## Open Questions
190 |     - Which OAuth 2.0 provider to use (Google, GitHub, etc.)?
191 |     - Password complexity requirements?
192 |     - Session management strategy (e.g., refresh tokens)?
193 |     ```
194 |
195 | *   **`memory-bank/progress.md`**: Update this file regularly to track the progress of the user authentication feature.
196 |
197 |     ```markdown
198 |     # memory-bank/progress.md
199 |
200 |     ## Work Done
201 |     - [Initially empty]
202 |     - **[After completing database schema design]:** - Database schema for user credentials designed and documented.
203 |     - **[After implementing registration API]:** - User registration API endpoint implemented and tested (basic functionality).
204 |     - **[Continue updating as tasks are completed]**
205 |
206 |     ## To Do
207 |     - [Initially, list all planned tasks]
208 |     - Plan database schema for user credentials.
209 |     - Implement user registration API endpoint.
210 |     - Implement user login API endpoint.
211 |     - Implement JWT-based authentication middleware.
212 |     - Implement frontend integration for login/registration.
213 |     - Implement session management.
214 |     - Implement password reset functionality.
215 |     - Write unit and integration tests for authentication.
216 |     - **[Update as tasks are completed and new tasks emerge]**
217 |
218 |     ## Current Status
219 |     User authentication feature - **In development** - Database schema design in progress.
220 |     - **[Update status as development progresses]** - User authentication feature - **In development** - User registration API implemented, working on login API.
221 |     - **[Upon completion]** - User authentication feature - **Completed and integrated.**
222 |     ```
223 |
224 | *   **`.clinerules-code` (Optional - Feature Specific Rules)**:  You could add rules to `.clinerules-code` to enforce specific code style or security practices for authentication-related code.  For example, you might add linting rules to ensure proper password handling or API security best practices are followed.  *(Example `.clinerules-code` content not shown for brevity, but mentioned as a possibility)*
225 |
226 | **Benefits:**
227 |
228 | Using the Memory Bank in this way helps you:
229 |
230 | *   **Plan and document the feature comprehensively.**
231 | *   **Track tasks, progress, and open questions systematically.**
232 | *   **Maintain context across development sessions.**
233 | *   **Communicate feature status and details effectively with team members (if applicable).**
234 |
235 | ### Memory Bank for Refactoring Existing Codebase
236 |
237 | **Scenario:** Refactoring a Complex Code Module
238 |
239 | **Initial State:**
240 |
241 | You have identified a complex code module (e.g., a large utility class or a tightly coupled function) in your existing codebase that has become difficult to understand and maintain. The Memory Bank has already been initialized for your project, and you are ready to document the refactoring process within the Memory Bank. You want to refactor this module to improve its readability, modularity, and overall maintainability.
242 |
243 | **Memory Bank Updates:**
244 |
245 | Throughout the refactoring process, you would update your Memory Bank files as follows:
246 |
247 | *   **`memory-bank/productContext.md`**:  You might optionally update this file to reflect the ongoing refactoring effort, especially if it's a significant project-wide refactoring. In most cases, it might not be necessary to update `productContext.md` for individual module refactoring.
248 |
249 | *   **`memory-bank/activeContext.md`**: Use this file to plan and track the refactoring process, document the refactoring strategy, and list files to be refactored.
250 |
251 |     ```markdown
252 |     # memory-bank/activeContext.md
253 |
254 |     ## Current Task
255 |     Refactoring complex `utils/legacy_module.py` module.
256 |
257 |     ## Refactoring Strategy
258 |     - 1. **Analyze `utils/legacy_module.py`:** Understand its functionality, identify areas of complexity, and potential refactoring targets (e.g., large functions, code duplication, tight coupling).
259 |     - 2. **Break down into smaller modules/functions:** Decompose the monolithic module into smaller, more focused modules or functions with clear responsibilities.
260 |     - 3. **Improve naming and documentation:**  Rename variables, functions, and classes for clarity. Add docstrings and comments to explain complex logic.
261 |     - 4. **Write unit tests:**  Write unit tests for the refactored modules/functions to ensure functionality is preserved and to prevent regressions.
262 |     - 5. **Gradually refactor and test:** Refactor piece by piece, running unit tests after each step to validate changes.
263 |
264 |     ## Files to Refactor
265 |     - `utils/legacy_module.py`
266 |     - [Potentially list specific functions or classes within the module]
267 |
268 |     ## Refactoring Progress
269 |     - [Initially empty]
270 |     - **[After analysis]:** - Analysis of `utils/legacy_module.py` completed. Refactoring strategy documented.
271 |     - **[After decomposition]:** - Core functions decomposed into smaller modules in `utils/refactored_module/`.
272 |     - **[Continue updating as refactoring progresses]**
273 |
274 |     ## Open Questions
275 |     -  Are there any dependencies on `utils/legacy_module.py` that need to be considered during refactoring? (Need to investigate codebase)
276 |     -  What is the estimated time for refactoring this module? (Need to estimate based on complexity)
277 |     ```
278 |
279 | *   **`memory-bank/decisionLog.md`**: Use `decisionLog.md` to record significant decisions made during the refactoring process, especially if there are trade-offs or alternative approaches considered.
280 |
281 |     ```markdown
282 |     # memory-bank/decisionLog.md
283 |
284 |     ## Refactoring `utils/legacy_module.py` - Decisions
285 |
286 |     - **[Date]: Decision:** To decompose `legacy_module.py` into smaller modules based on functional areas (e.g., input validation, data processing, output formatting).
287 |         - **Rationale:** Improves modularity, testability, and maintainability compared to keeping it as a single monolithic module.
288 |         - **Alternatives Considered:**  Refactoring in-place without decomposition (Rejected - less impactful for long-term maintainability).
289 |
290 |     - **[Date]: Decision:** To use descriptive naming conventions and add comprehensive docstrings to all refactored functions and classes.
291 |         - **Rationale:**  Significantly improves code readability and understandability for future developers.
292 |         - **Alternatives Considered:** Minimal documentation (Rejected - insufficient for complex legacy code).
293 |
294 |     - **[Continue adding decisions as refactoring progresses]**
295 |     ```
296 |
297 |
298 | *   **`memory-bank/progress.md`**: Update `progress.md` to track the overall progress of the refactoring effort.
299 |
300 |     ```markdown
301 |     # memory-bank/progress.md
302 |
303 |     ## Work Done
304 |     - [Initially empty]
305 |     - **[After analysis and planning]:** - Refactoring plan for `utils/legacy_module.py` documented in `activeContext.md` and `decisionLog.md`.
306 |     - **[After decomposition]:** - Core functions of `legacy_module.py` decomposed into smaller modules in `utils/refactored_module/`.
307 |     - **[Continue updating as refactoring progresses]**
308 |
309 |     ## To Do
310 |     - [Initially, list all refactoring tasks]
311 |     - Analyze `utils/legacy_module.py`.
312 |     - Decompose into smaller modules/functions.
313 |     - Improve naming and documentation.
314 |     - Write unit tests for refactored modules.
315 |     - Gradually refactor and test each module.
316 |     - Integrate refactored modules into the existing codebase.
317 |     - Verify overall application functionality after refactoring.
318 |     - **[Update as tasks are completed and new tasks emerge]**
319 |
320 |     ## Current Status
321 |     Refactoring `utils/legacy_module.py` - **Planning phase complete.** - Analysis and refactoring strategy documented.
322 |     - **[Update status as refactoring progresses]** - Refactoring `utils/legacy_module.py` - **In progress** - Core functions decomposition completed. Working on improving naming and documentation.
323 |     - **[Upon completion]** - Refactoring `utils/legacy_module.py` - **Completed and verified.**
324 |     ```
325 |
326 | **Benefits:**
327 |
328 | Using the Memory Bank in this way helps you:
329 |
330 | *   **Plan and manage complex refactoring efforts systematically.**
331 | *   **Document refactoring strategy, decisions, and progress.**
332 | *   **Maintain context and track open questions throughout the refactoring process.**
333 | *   **Improve team collaboration and knowledge sharing during refactoring.**
334 |
335 | ### Memory Bank for Bug Fixing
336 |
337 | **Scenario:** Debugging and Fixing User Login Bug
338 |
339 | **Initial State:**
340 |
341 | Users are reporting that they are unable to log in to the application. Initial investigation suggests a potential bug in the user login functionality. You need to investigate, identify the root cause, and implement a fix.
342 |
343 | **Memory Bank Updates:**
344 |
345 | Throughout the bug fixing process, you would update your Memory Bank files as follows:
346 |
347 | *   **`memory-bank/activeContext.md`**: Use this file to document bug details, reproduction steps, investigation progress, debugging steps, and potential solutions.
348 |
349 |     ```markdown
350 |     # memory-bank/activeContext.md
351 |
352 |     ## Current Task
353 |     Debugging and fixing user login bug.
354 |
355 |     ## Bug Details
356 |     - **Symptom:** Users cannot log in; login form submits but redirects back to login page with "Invalid credentials" error (even with correct credentials).
357 |     - **Reported by:** Multiple users (see support tickets #123, #124, #125).
358 |     - **Affected users:**  Seems to affect all users.
359 |     - **Environment:**  Reported across all browsers and platforms.
360 |     - **Last known working version:** v1.2.0 (suspect regression in v1.2.1).
361 |
362 |     ## Reproduction Steps
363 |     1. Go to login page.
364 |     2. Enter valid username and password.
365 |     3. Submit login form.
366 |     4. Observe redirect back to login page with "Invalid credentials" error.
367 |
368 |     ## Investigation Progress
369 |     - [Initially empty]
370 |     - **[After initial investigation]:** - Checked server logs - no errors related to authentication.
371 |     - **[Checked authentication code]:** - Reviewed `auth/login.py` - no obvious code errors, but need to step through debugger.
372 |     - **[Next step]:** - Set up debugging environment and step through login process to identify where authentication fails.
373 |
374 |     ## Potential Solutions
375 |     - [Initially empty]
376 |     - **[After initial debugging]:** - Potential issue with password hashing logic after recent library update? Need to verify password hashing process.
377 |     - **[List potential fixes as they are identified]**
378 |     ```
379 |
380 | *   **`memory-bank/decisionLog.md`**: Use `decisionLog.md` to record debugging steps, findings, and fix implementation decisions, especially if you try multiple approaches or need to make trade-offs.
381 |
382 |     ```markdown
383 |     # memory-bank/decisionLog.md
384 |
385 |     ## Bug Fix - User Login Bug - Decisions
386 |
387 |     - **[Date]: Debugging Step:** Stepped through `auth/login.py` in debugger, focusing on password hashing logic.
388 |         - **Findings:**  Password hashing logic seems correct, but noticed that the password comparison function is returning False even for valid passwords.
389 |
390 |     - **[Date]: Decision:** Investigate password comparison function and bcrypt library version.
391 |         - **Rationale:** Suspect incompatibility issue with bcrypt library after recent update, potentially causing incorrect password comparison.
392 |         - **Alternatives Considered:** Reverting bcrypt library version (Chosen - quickest way to verify if bcrypt version is the issue).
393 |
394 |     - **[Date]: Decision:** Reverted bcrypt library version to previous version (vX.X.X). Tested login - login now working.
395 |         - **Findings:** Reverting bcrypt version fixed the login bug. Confirms bcrypt version incompatibility.
396 |         - **Next Steps:**  Document bcrypt version incompatibility issue. Investigate root cause of incompatibility and potential long-term solution (e.g., update bcrypt version and adjust code if needed, or pin bcrypt version).
397 |
398 |     - **[Continue adding decisions and findings as debugging and fixing progresses]**
399 |     ```
400 |
401 |
402 | *   **`memory-bank/progress.md`**: Update `progress.md` to track the bug fix status and verification.
403 |
404 |     ```markdown
405 |     # memory-bank/progress.md
406 |
407 |     ## Work Done
408 |     - [Initially empty]
409 |     - **[After initial investigation]:** - User login bug reported and documented in `activeContext.md`. Initial investigation and debugging started.
410 |     - **[After identifying bcrypt issue]:** - Root cause identified - bcrypt library version incompatibility. Temporary fix implemented by reverting bcrypt version.
411 |     - **[Continue updating as bug fix progresses]**
412 |
413 |     ## To Do
414 |     - [Initially, list all bug fixing tasks]
415 |     - Investigate user login bug.
416 |     - Identify root cause of login failure.
417 |     - Implement temporary fix (bcrypt version revert).
418 |     - Verify temporary fix (login functionality working).
419 |     - Investigate long-term solution for bcrypt incompatibility.
420 |     - Implement long-term fix (if needed).
421 |     - Write unit/integration tests to prevent regression.
422 |     - Deploy bug fix to production.
423 |     - Monitor login functionality after deployment.
424 |     - **[Update as tasks are completed and new tasks emerge]**
425 |
426 |     ## Current Status
427 |     User login bug - **Investigating** - Root cause identified (bcrypt version incompatibility). Temporary fix implemented and verified.
428 |     - **[Update status as bug fix progresses]** - User login bug - **Fix implemented and verified.** - Temporary fix deployed to production. Monitoring login functionality.
429 |     - **[Upon completion of long-term fix]** - User login bug - **Fixed (long-term solution implemented).** - Long-term fix implemented and deployed. Regression tests added.
430 |     ```
431 |
432 | **Benefits:**
433 |
434 | Using the Memory Bank in this way helps you:
435 |
436 | *   **Systematically debug and troubleshoot complex issues.**
437 | *   **Document bug details, investigation steps, and decisions.**
438 | *   **Track bug fix progress and status.**
439 | *   **Maintain context and ensure thoroughness in the bug fixing process.**
440 | *   **Facilitate knowledge sharing and collaboration on bug fixes.**
441 |
442 | ## Troubleshooting
443 |
444 | `[MEMORY BANK: ACTIVE]` Prefix Not Working
445 |
446 | **Solution:**
447 | 1. **Check Custom Instructions:** Ensure all custom instruction modules are correctly pasted into Roo Code "Prompts" settings in VS Code, especially "Mode-specific Custom Instructions/Code".
448 | 2. **Save Settings:** Verify that VS Code settings were saved after pasting instructions.
449 | 3. **Confirm Code Mode:** Ensure you are in "Code" mode when using `[MEMORY BANK: ACTIVE]` prefix (check Roo Code chat interface).
450 | 4. **Check Prefix Syntax:** Verify exact syntax: `[MEMORY BANK: ACTIVE]` (case-sensitive, spacing).
451 |
452 | Memory Bank Not Persisting After VS Code Restart
453 |
454 | **Solution:**
455 | 1. **Verify Memory Bank Initialization:** Confirm that you have initiated the Memory Bank initialization process by switching to Architect mode in a new project (see "Getting Started" section). Check if the `memory-bank/` folder and essential files were created at the project root after following the initialization plan provided by Roo Code in Architect mode.
456 | 2. **Initial Mode Switch:** After VS Code restart, switch to "Ask" or "Architect" mode *first* to trigger Memory Bank loading.
457 | 3. **Use `update memory bank` Command:**  Use `update memory bank` at session end to explicitly save and prepare Memory Bank.
458 | 4. **Check File Paths:** Verify `memory-bank/` folder is at project root; incorrect paths prevent Memory Bank access.
459 |
460 | `.clinerules` Rules Not Applied
461 |
462 | **Solution:**
463 | 1. **File Location:** Ensure `.clinerules` files (`.clinerules`, `.clinerules-code`, etc.) are at project root, alongside `memory-bank/` folder.
464 | 2. **Syntax Check:** Verify `.clinerules` file syntax; incorrect syntax may cause rules to be ignored.
465 | 3. **Mode Relevance:** Note that `.clinerules-code`, `.clinerules-architect`, `.clinerules-ask` are mode-specific.
466 | 4. **Restart Roo Code (Rare):**  Restart Roo Code in VS Code after major `.clinerules` changes to reload rules.
467 |
468 | Memory Bank Files Not Updating/Saving
469 |
470 | **Solution:**
471 | 1. **File Permissions:** Check write permissions for `memory-bank/` folder and files.
472 | 2. **VS Code Errors:** Check VS Code console for file saving errors.
473 | 3. **Conflicting Extensions:** Temporarily disable extensions that might interfere with saving.
474 | 4. **Disk Space:** Ensure sufficient free disk space is available.
475 |
476 | If issues persist, consult the Roo Code documentation or community support channels for further assistance.
477 |
478 | ## Revised Guidance on "Update Memory Bank" Command:
479 |
480 | While not strictly *required* after every break, the `update memory bank` command is a **best practice** for session management and long-term project context preservation.
481 |
482 | To visualize this session management process, refer to the workflow diagram below:
483 |
484 | ```
485 | ### Session Management Workflow (`update memory bank` Command)
486 |
487 | ```
488 | Start: Working on Project (Any Mode) -->
489 |   Step 1: User makes changes to Memory Bank files (`productContext.md`, `activeContext.md`, `progress.md`, etc.) -->
490 |   Step 2: Session End or Break?
491 |     Yes: User initiates `update memory bank` command in chat -->
492 |     No: Continue Working (Loop back to Step 1)
493 |   Step 3: Roo Code **saves** current state of Memory Bank files -->
494 |   Step 4: Memory Bank is **prepared** for next session -->
495 |   End: Session Managed & Memory Bank Updated
496 | ```
497 | ```
498 |
499 | **Think of it as:**
500 | * **`[MEMORY BANK: ACTIVE]` Prefix:**  Ensures Roo uses *documented, reliable* project context in Code mode (important for memory resets).
501 | * **`update memory bank` Command:** "Save project knowledge" command. Use it to:
502 |   * Update Memory Bank at session end/breaks.
503 |   * Prepare for VS Code closure/workspace switch.
504 |   * Create project history checkpoints.
505 |
506 | **Key Takeaway:**
507 |
508 | Roo Code's new context features are a welcome enhancement. However, the Memory Bank system remains the cornerstone of persistent, structured project knowledge management for Roo. By using both effectively – leveraging Roo Code's features for in-session convenience and the Memory Bank for long-term reliability and structured documentation – you create a powerful and robust development workflow with Roo. Continue to prioritize maintaining your Memory Bank as your project's long-term memory and use `update memory bank` strategically to ensure its accuracy and completeness across sessions.