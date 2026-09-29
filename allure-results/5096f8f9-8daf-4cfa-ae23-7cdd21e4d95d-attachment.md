# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: Testsuite.spec.ts >> Test Suite for Hybrid >> TC001_Login_Logout
- Location: tests\Testsuite.spec.ts:5:9

# Error details

```
Error: page.goto: net::ERR_NAME_NOT_RESOLVED at https://ctcorphyd.com/SureshIT/login.php
Call log:
  - navigating to "https://ctcorphyd.com/SureshIT/login.php", waiting until "load"

```

# Test source

```ts
  1  | //To Provide all Reusable methods / functions related to whole application
  2  | import {global} from './Global';
  3  | 
  4  | export class general extends global {
  5  | //user-defined functions
  6  | //open application
  7  | public async openApplication() {
> 8  |     await this.page.goto(this.url);
     |                     ^ Error: page.goto: net::ERR_NAME_NOT_RESOLVED at https://ctcorphyd.com/SureshIT/login.php
  9  |     console.log("Application opened");
  10 | }
  11 | //login to application
  12 | public async login() {
  13 |     await this.page.locator(this.textbox_loginname).fill(this.username);
  14 |     await this.page.locator(this.textbox_password).fill(this.password);
  15 |     await this.page.locator(this.button_login).click();
  16 |     console.log("Login Completed");
  17 | }
  18 | //logout from application
  19 | public async logout() {
  20 |     await this.page.locator(this.link_logout).click();
  21 |     console.log("Logout completed");
  22 | }
  23 | //add employee
  24 | public async addNewEmployee() {
  25 |    const frame = this.page.frameLocator(this.frame_empinfo);
  26 |    await frame.locator(this.button_add).click();
  27 |    await frame.locator(this.textbox_empfirstname).fill(this.empfirstname);
  28 |    await frame.locator(this.textbox_emplastname).fill(this.emplastname);
  29 |    await frame.locator(this.button_save).click();
  30 |    console.log("New Employee Added");
  31 | }
  32 | public async waitTime(){
  33 |     await this.page.waitForTimeout(3000);
  34 | }
  35 | }
  36 | 
  37 | 
  38 | 
  39 | 
```