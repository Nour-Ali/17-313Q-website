# Project 3: Continuous Integration + Deployment

## Learning Goals

- Learn how to deploy a full-stack application
- Gain hands-on experience with analysis tools, including setting up, customizing, and using them
- Practically assess and compare the costs and benefits of existing static and dynamic bug-finding tools
- Integrate CI/CD tools into development practice


## Project Context

Adding continuous integration for quality assurance is a critical part of software development. Although you have been testing your new system this whole time, you are now setting out to establish sustained practices that can be used moving forward as you iterate over and continue to improve your system.

Your manager has assigned you two major tasks. Firstly, establishing a deployment pipeline to create a test version of the website that can be sent to beta testers who have little to no experience with code development (and therefore can not set up the developer environment by themselves). 

Secondly, evaluating existing tools and practices beyond simple linting or unit testing, then producing a report on the cost/benefit tradeoffs and risks of them. You will also select and integrate one (or more!) of these tools into your development process.


## Deliverables and Deadlines
There are two (2) deliverables and two (2) deadlines. This project is worth a total of 120 points.

**Checkpoint Deliverables** – 35 points – due Thursday, March 16th, 11:59pm

- [Deployed Application (25 pts)](#deployed-application-25-pts)
- [Tools Checkpoint (10 pts)](#tools-checkpoint-10-pts)

**Final Deliverables** – 85 points – due Thursday, March 23rd, 11:59pm

- [CD Implementation (10 pts)](#cd-implementation-10-pts)
- [Tool Analysis Design Doc (60 pts)](#tool-analysis-design-doc-60-pts)
- [Tool Integration (15 pts)](#tool-integration-15-pts)

**Extra Credit (Individual) ** - 6 points - due Thursday, March 23rd, 11:59pm

- [Feature Review (6 pts)](#feature-review-6-pts)

!!! info "Work Distribution"
    There are two main focuses in this project: deployment and static/dynamic analysis. For the purposes of equitable distribution of labor, we recommend that you nominate one of your members to act as the SRE for this assignment who will be primarily responsible for deployment, and have all other teammates focus on tool research and integration. 


## Checkpoint Deliverables

### Deployed Application (25 pts)

Your team will be using the website fly.io for the deployment of the NodeBB application. Further instructions on how to deploy can be found [here](/projects/P3/deployment).

Once you have successfully deployed your website, make sure to test within your team to ensure that your added feature(s) from Project 2 are properly integrated. 

By the checkpoint deadline you should

- Submit a link to the deployed site onto Gradescope
- Add your deployed site to this [public spreadsheet](https://docs.google.com/spreadsheets/d/1MjR3MC6kRoXZCfIKmrR-SAiZCXOYRsug6NzAoIhFm8Q/), alongside your team name & UserGuide.md that your team submitted for Project 2. This will be used in [Feature Review](#feature-review-6-pts) for extra credit.

### Tools Checkpoint (10 pts)

Before jumping into tool integration, your manager would like you to research what existing analysis tools are out there that can be used with NodeBB. You will evaluate the tools, and eventually document your findings in a design document for your final deliverable.

First, identify and experiment with **at least N-1 potential static and dynamic analysis tools** that are applicable to your system, where N is the number of people in your team. We provide a [starter list of tools](#starter-list-of-tools) in the resources section below to help you get started, but you are not limited to these tools.

In your selection of tools, you should

- have **at least one** static analysis tool
- have **at least one** dynamic analysis tool
- have **at least one** tool that is not from our starter list
- **not use** any of the existing tools within NodeBB as part of your analysis (mocha/ESLint/TSLint)

For each tool that you assess

1. Create a separate testing branch in your repository (named appropriately for the tool you’re testing) to integrate the tool into your project and test out its capabilities
2. Create a pull request to the main branch from each of these testing branches. The PR should have
   
      - **Concrete evidence that you had successfully installed the tool** through trackable file changes demonstrating that extra files/NPM packages were installed.
      - **Artifacts that demonstrate that you have successfully run the tool on your repository.** Acceptable artifacts include output files generated by the tool, or a text file containing the terminal output from the tool; you may also attach screenshots as additional pieces of evidence. They can be attached to the Pull Request in either the description or follow-up comments.

!!! note "Grading Note"
    We will not be grading the quality or quantity of any code you put into these testing branches/PRs, just the evidence that you have successfully installed and run the tool.
    
In your evaluations, consider & experiment with the types of customization that are appropriate or necessary for this tool, both a priori (before they can be used in your project) and over time. Assess the strengths and weaknesses of each tool/technique, both quantitatively and qualitatively.

Consider some of the following questions: 

- What types of problems are you hoping your tooling will catch?  What types of problems does this particular tool catch? 
- What types of customization are possible or necessary? 
- How can/should this tool be integrated into a development process?
- Are there many false positives? False negatives? True positive reports about things you don’t care about?

!!! info "Tool Evaluation"
    There are a lot of different factors to consider when evaluating a tool. We recommend discussing with your teammates and deciding on a group of metrics to focus on when performing evaluations.

!!! note "Time Management"
    Don’t spend too long for this checkpoint. Set deadlines within your team to ensure that you have enough time for both the design document and integration deliverables described below for the final deadline.

By the checkpoint deadline, your team will submit 

- your **initial list of the N-1 tools** that your team plans on exploring, and 
- links to the **PRs that demonstrate that you have successfully installed and run each of these tools**

## Final Deliverables

### CD Implementation (10 pts)
Now that you have successfully deployed your application manually for the checkpoint deadline, add a workflow to your team repository that will automatically deploy your application. In doing so, consider how often you would want to deploy, and if you would need to make changes to your repository to ensure best development practices.

!!! warning "GitHub Secrets"
    You may have sensitive or secret values that will be required by your workflow in order to successfully deploy your application. As your team repository is public, be sure to follow best GitHub practice in [creating secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets) to prevent such values from being leaked.

Submit a link to a successful deployment GitHub Action run along with a brief description/justification of how you set up the workflow to Gradescope.


### Tool Analysis Design Doc (60 pts)

Create a Design Document/RFC that includes:

- A **tools evaluations section** detailing your team’s analysis on each of the tools you experimented with
- A **justification section** explaining which tool(s) you think the project should use moving forward
- An **integration section** describing how the selected tool(s) shall be integrated into your process
- A **conclusion section** summarizing your work

Below, we provide more detailed instructions and page limit recommendations for each of the sections.

#### Tool Evaluations (~N pages)

For each of the N-1 tools explored by your team, you must provide:

- Name and high-level description of what the tool does and a link to its documentation/source
- Whether the tool is used for static or dynamic analysis
- A link to the pull request made from the testing branch for this tool
- A pro/con analysis of the tool and appropriate evidence in the form of screenshots to support your claims. You can use the questions provided in the research you did for the checkpoint to shape your analysis.

Each of these sections should take up approximately 1 page (including screenshots) and no more than 2 pages.

#### Justification (~Half a page)

After going through each of the tools, you should explicitly state the tool(s) you are choosing to integrate for this project and provide a justification for why you are selecting this tool. You should refer to the pro/con analysis done in the prior sections and how they align with the goals of your team and the project overall.

You **must recommend at least one tool**, even if it’s with reservations.

#### Integration (<1 page)

This section should address the different factors to take into consideration when integrating a new tool. At minimum, you should address the following:

- **Technical Questions**
    - How are you integrating the tool (high-level)? At what point in the development/deployment process shall it be integrated? What sorts of customization or configuration will you be using?
    - If you added any specific configuration to allow the main branch of your repository to pass its status checks, add the justification for those decisions in this section.
- **Social Integration Questions** 
    - How do you foresee the team using the tool during their development process? Consider the incentives & deterrents to the developers when it comes to using the tool, and their personal motivation to use it.

Your answers should be based on your experiences running the tools on your team repository and be grounded in data from your research on different factors such as tool usability, output, and customizability.

Keep this section updated as you work on implementing the integration.

#### Conclusion (<1 page)

In this section, provide a brief summary of your findings along with items that were not addressed in the previous sections.

- Are there any open questions?
- Are there any issues you consider to be out of scope?
- What drawbacks of the proposed process/tooling are you accepting for some (good) reason? 

This section should be used to wrap everything up and ensure you have a good/complete design document!

Submit the Design Document as a single PDF to Gradescope.

### Tool Integration (15 pts)

Once you have a tool selected along with a general integration plan, you should fully integrate one of the tools into your project’s workflow. For your checkpoint research, you should have successfully run this tool locally; you should then create a new workflow within the project to run it as part of the development cycle.

Your team should discuss:

- How often should this new integration be run (on each pull request? on commits to main?)
- What level of customization is needed for this tool?
- How should the integration of this tool be enforced?

This configuration must have been justified in your design document under the Integration section.

To be considered successfully integrated, the tool must:

- Be **merged into your main branch**
- **Have been run at least once in the Git flow cycle** (i.e. either during the pull request, merge, or commit stage). 
- **Pass** when run on your codebase. This is indicated by having a green checkmark.

!!! note "Ensuring Passing Checks"
    In order to ensure your checks pass successfully, you may have to make additional changes to your repository, such as fixing reported issues or tweaking tool configuration.
    
    These changes should be documented and addressed in your design document. Continually failing builds show you have *not* completely integrated the tool into your workflow.

On Gradescope, submit a link to your repository and a link to one of the successful GitHub Action runs.

## Extra Credit

Now that you and your classmates have deployed your applications, you will be able to test out each other’s features and provide constructive feedback on your experience and how to improve them! Take this as an opportunity to learn about what your classmates have been working on for the past few weeks. 

Note that this is an **individual** task, unlike the rest of project.

### Feature Review (6 pts)

For extra credit, you will conduct reviews of features developed by three other teams' project. Pick **three** teams's deployment from the [public spreadsheet](https://docs.google.com/spreadsheets/d/1MjR3MC6kRoXZCfIKmrR-SAiZCXOYRsug6NzAoIhFm8Q/) to review, 1 from your own section, and 2 from other sections. 

For each team, you will submit a review of their feature(s). You will need to test the feature(s) as described in their UserGuide and provide feedback on the following:

1. How was the experience of using the feature(s), would this be something you think would help enable better communication between faculty and students and why?
2. How do you think the feature can be improved? and/or What do you think the feature did well in?
3. Did you discover any bugs using the feature(s)?

To qualify for extra credit, you will have to submit your review:

- on Gradescope
- in the appropriate sheet in the [public spreadsheet](https://docs.google.com/spreadsheets/d/1MjR3MC6kRoXZCfIKmrR-SAiZCXOYRsug6NzAoIhFm8Q/). There should be one sheet per team, and you should add your review to the sheet for the team you are reviewing.

## Grading
To receive full credit for the checkpoint, we expect:

- [ ] A link to your successfully deployed web application for your team repository
- [ ] A list of N-1 different static and dynamic analysis tools, where N is the number of members on your team. This list must satisfy all the following criteria:
    - Contain at least one static analysis tool
    - Contain at least one dynamic analysis tool
    - Contain at least one tool not on our starter list of tools
- [ ] Links to N-1 pull requests for each of the selected tools containing evidence of the tool being run at least once on your repository

To receive full credit for the final deadline, we expect:

- [ ] A link to your successfully run CD GitHub action that deploys the website while following proper GitHub practices in handling deployment secrets
- [ ] A design document describing your research into each of the potential tools, justification for your selection of integrated tool(s), and your final integration plan
- [ ] A link to a succuessful run of a GitHub Action that demonstrates your integration of your selected tool(s) into your team workflow

To receive full credit for the extra credit, we expect:

- [ ] Your review of three different teams' features on Gradescope and on the [public spreadsheet](https://docs.google.com/spreadsheets/d/1MjR3MC6kRoXZCfIKmrR-SAiZCXOYRsug6NzAoIhFm8Q/), addressing the three questions described.
## Resources & Documentation

### Starter List of Tools

NodeBB is built in Javascript/Typescript using Node.js and uses Benchpress for its frontend templating. Below are non-exhaustive lists of analysis tools that are available. 

For other resources, [Awesome Static Analysis page](https://github.com/david-a-wheeler/awesome-static-analysis) and [Awesome Dynamic Analysis page](https://github.com/analysis-tools-dev/dynamic-analysis) have extensive listings of available static and dynamic analysis tools for a pretty hefty list of programming languages.

Some of the tools already have existing GitHub Actions workflows on GitHub Marketplace; use your Googling skills, and see what you find!

#### Static Tools

- [flow](https://flow.org/): Static type checker for JavaScript
- [JScent](https://github.com/moskirathe/JScent): Program analyzer for detecting “code smells”
- [JSHint](https://jshint.com/docs/): Used to flag suspicious usage in JavaScript programs
- [StandardJS](https://standardjs.com/)/[ts-standard](https://github.com/standard/ts-standard): Static analysis tool for code quality within JavaScript/TypeScript projects
- [Retire.js](https://retirejs.github.io/retire.js/): Finds library/node module vulnerabilities within your project

#### Dynamic Tools

- [Iroh](https://maierfelix.github.io/Iroh/): Runtime code tracking and visualization
- [Jalangi](https://github.com/Samsung/jalangi2): Framework for dynamic analyses in JavaScript
- [Fast-Fuzz](https://www.npmjs.com/package/fast-fuzz): Fuzzing framework for TypeScript
- [Stryker Mutator](https://stryker-mutator.io/): Mutation testing tool for JavaScript