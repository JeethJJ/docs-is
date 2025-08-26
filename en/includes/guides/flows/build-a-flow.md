# Get Started

A **flow** defines a guided user journey, such as registration or recovery. The **Flow Builder** provides administrators with a visual environment to create and manage these journeys. From simple single step forms to complex, multi stage sequences, you can design flows that meet both security requirements and user experience goals.

## Enabling a Flow

To enable a flow, please follow the steps below.

### Steps to Enable a Flow

1. Navigate to **Home → Flows**.
2. Select the flow **card** you want to enable.
3. Select a **Template** or **Design Your Flow** <br>
    - You can either choose a **starter template**, or
    - Build your own flow using the **drag-and-drop** flow designer.
4. Save and enable the flow <br>
    - If you want to save your work and continue later, click **Save Draft**.
    - To make the flow live, turn on the **Enable** toggle. This saves and publishes your flow.

!!! Note
    Enabling a flow overrides the existing experience for that flow in your organization. You can always revert to the previous experience by disabling the toggle.

## Building a Flow

The Flow Builder supports multiple approaches so you can create user journeys in the way that best fits your needs.

### Generate with AI

Describe your ideal flow in plain language, and the builder will generate it automatically. This is ideal for quickly creating complex flows without manually placing every component.

![Flow builder AI]({{base_path}}/assets/img/guides/flows/flow-builder-generate-with-ai.png){: width="auto" style="display: block; margin: 0;"}

### Use Starter Templates

Starter templates give you a quick start with predefined flows that are easily customizable. Click the `+` button next to a template to add it to the flow.

![Starter Templates]({{base_path}}/assets/img/guides/flows/flow-builder-starter-templates.png){: width="auto" style="display: block; margin: 0;"}

### Build from Scratch

Begin with a blank canvas and use the drag-and-drop interface to add steps, widgets, and components. This option gives you full control over the sequence, UI elements, and logic in the flow.

![Custom Flow]({{base_path}}/assets/img/guides/flows/flow-builder-custom-flow.png){: width="auto" style="display: block; margin: 0;"}

## Flow Elements

Flows are made up of different types of elements that work together to create the user journey. These elements let you control the structure, functionality, and appearance of each step in the flow.

### Widgets

Widgets are reusable components that enhance the flow. Drag and drop widgets into your desired `view` to build a flow.

![Widgets]({{base_path}}/assets/img/guides/flows/flow-builder-widgets.gif){: width="auto" style="display: block; margin: 0;"}

### Steps

Steps are the core building blocks of a flow. Drag and drop steps to create a multi‑step user journeys.

![Steps]({{base_path}}/assets/img/guides/flows/flow-builder-steps.gif){: width="auto" style="display: block; margin: 0;"}

### Components

Components are atomic UI elements added to steps. Drag and drop components inside a step.

!!! Note
    Field components such as **Text Inputs**, **Email Inputs**, etc. have the following constraints:
    - They must be added inside a **Form** component.
    - They must be mapped to a user attribute. Do this by clicking the pencil icon on the element action panel and selecting the relevant attribute from the `Attribute` dropdown. Only attributes set to display on the respective user profile in the [Attribute Configurations]({{base_path}}/guides/users/attributes/manage-attributes) will be available for mapping.

![Components]({{base_path}}/assets/img/guides/flows/flow-builder-components.gif){: width="auto" style="display: block; margin: 0;"}
