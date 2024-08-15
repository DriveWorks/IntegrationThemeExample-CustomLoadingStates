# DriveWorks Live - Integration Theme Example - Custom Loading States
### Version: 1.0.0
#### DriveWorks Versions: 17.x - 20.x

A distributable example that demonstrates how to customize various loading states shown in DriveWorks Forms using CSS.

---

Please note: DriveWorks are not accepting pull requests for this example.  
Join our [online community](https://my.driveworks.co.uk) for discussion, resources and to suggest other examples.

---

### In this example:

`index.html`
- Renders multiple examples of custom loading state styles.
    - **Force Loading States**
        - Force loading states to display. Useful during development.
        - See `styles/force-loading-states.css`.
    - **Specifications**
        - **Inline Loading States**
            - Shown before the Form is rendered into a container.
            - See `styles/inline-loading-states.css`.
        - **Form Loading States**
            - Shown when a rendered Form is loading.
            - See `styles/form-loading-states.css`.
    - **3D Preview Controls**
        - Shown when a 3D Preview Box Control is loading.
        - See `styles/preview-loading-states.css`.

`custom-loading-element.html`
- Demonstrates how to set a custom HTML element to be shown when Forms rendered by a specific Client are in a loading state.
- [Debug] The duration that the example custom element is shown for can be modified within the included Project.
    - This example includes an intentionally slow running `TriggerLoading` Macro to emulate a long 'loading' period - during which the custom element is displayed.
    - The duration of this period can be modified by increasing/decreasing the `Limit Value` of the included "Run Macro in a Loop" task.

`styles/*.css`
- Styles used - see above.

Note: styles in `_structure.css` are used only to layout the example, and do not apply to loading states. These should not be referenced.

### To use:
1. Clone this repository, or download as a .zip file.

2. Extract the supplied .drivepkg file using the DriveWorks Package Wizard to access the included Project files.

3. Open the extracted Group in DriveWorks Administrator. You can use 'Form Design' to view each Control and its Properties.

4. In `DriveWorksLiveConfigUser.xml`, add a new Group Alias for the included example Group e.g. `name="CustomLoadingStates"`.
    * See [Integration Theme Connection Settings](https://docs.driveworkspro.com/Topic/IntegrationThemeSettings#Connection-Settings) for additional guidance.

5. Enter your Integration Theme details into `config.js`.
    * `serverUrl` - The URL that hosts your Integration Theme, including any ports.
    * `groupAlias` - The public alias created for the Group containing the DriveApps to render - as configured in `DriveWorksConfigUser.xml`.
        * This *must* be specified for each Group you wish to use.
        * This allows you to mask the true Group name publicly, if desired.
        * See [Integration Theme Connection Settings](https://docs.driveworkspro.com/Topic/IntegrationThemeSettings#Connection-Settings) for additional guidance.
    * `projectName` - The name of the Project to render in the main example.
        * This is pre-filled with the name of a supplied Project, but can be changed if required.
    * `projectNameCustomLoadingElement` - The name of the Project to render in the "Custom Loading Element" example.
        * This is pre-filled with the name of a supplied Project, but can be changed if required.

6. Ensure that the Integration Theme server is running, using any of the available methods (e.g. Personal Web Edition, DriveWorks Live, IIS)
    * For more information, see [Selecting the Integration Theme](https://docs.driveworkspro.com/Topic/IntegrationThemeSelect).

7. Open the example HTML files locally (localhost) or on a remote server.
    * Ensure `<corsOrigins>` in `DriveWorksConfigUser.xml` permits requests from this location.
    * See [Integration Theme Configuration Settings](https://docs.driveworkspro.com/Topic/IntegrationThemeSettings#Configuration-Settings) for additional guidance.

8. If encountering any issues, check the browser's console for error messages (F12).

### Potential Issues:
* When serving this example for a domain different to your DriveWorks Live server, e.g. api.my-site.com from company.com, 'SameSite' cookie warnings may be thrown when the Client SDK attempts to store the current session id.
    * This appears as "Error: 401 Unauthorized" in the browser console, even with the correct configuration set. 
    * To resolve:
        * Ensure you are running DriveWorks 18.2 or above, HTTPS is enabled in DriveWorks Live's settings and a valid SSL certificate has been configured via `DriveWorksConfigUser.xml`.
        * See [Integration Theme Settings](https://docs.driveworkspro.com/Topic/IntegrationThemeSettings) for additional guidance.

---

This source code has been made available to demonstrate how you can integrate with DriveWorks using the DriveWorks Live API.
This code is provided under the MIT license. For more details, see the included LICENSE file.

The example requires that you have the latest DriveWorks Live SDK installed, operational and remotely accessible.
