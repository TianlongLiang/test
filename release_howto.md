# Github Actions
## 1. Component
### 1.1 Workflows
A workflow is a `configurable automated process` that will run `one or more jobs`. Workflows are defined by a YAML file checked in to your repository and will run when `triggered` by an `event` in your repository, or they can be `triggered manually`, or at a defined schedule.

Workflows are defined in the .github/workflows directory in a repository, and a repository can have multiple workflows, each of which can perform a different set of tasks. For example, you can have one workflow to build and test pull requests, another workflow to deploy your application every time a release is created, and still another workflow that adds a label every time someone opens a new issue.

You can reference a workflow within another workflow, see "[Reusing workflows.](https://docs.github.com/en/actions/using-workflows/reusing-workflows)"

For more information about workflows, see "[Using workflows.](https://docs.github.com/en/actions/using-workflows)"

### 1.2 Events
An event is a specific `activity` in a repository that `triggers a workflow` run. For example, activity can originate from GitHub when someone creates a pull request, opens an issue, or pushes a commit to a repository. You can also trigger a workflow run on a schedule, by [posting to a REST API](https://docs.github.com/en/rest/repos/repos#create-a-repository-dispatch-event), or manually.

For a complete list of events that can be used to trigger workflows, see [Events that trigger workflows](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows).

### 1.3 Jobs
A job is `a set of steps` in a workflow that `execute on the same runner`. `Each step` is either a shell script that will be `executed`, or an action that will be run. Steps are executed in order and are dependent on each other. Since each step is executed on the same runner, you can share data from one step to another. For example, you can have a step that builds your application followed by a step that tests the application that was built.

You can configure a job's dependencies with other jobs; by default, jobs have no dependencies and run in parallel with each other. When a job takes a dependency on another job, it will wait for the dependent job to complete before it can run. For example, you may have multiple build jobs for different architectures that have no dependencies, and a packaging job that is dependent on those jobs. The build jobs will run in parallel, and when they have all completed successfully, the packaging job will run.

For more information about jobs, see ["Using jobs."](https://docs.github.com/en/actions/using-jobs)

### 1.4 Actions
An action is a `custom application for the GitHub Actions` platform that performs a complex but frequently repeated task. Use an action to help reduce the amount of repetitive code that you write in your workflow files. An action can pull your git repository from GitHub, set up the correct toolchain for your build environment, or set up the authentication to your cloud provider.

You can write your own actions, or you can find actions to use in your workflows in the GitHub Marketplace.

For more information, see "[Creating actions.](https://docs.github.com/en/actions/creating-actions)"

### 1.5 Runners
A runner is a `server that runs your workflows` when they're triggered. Each runner can run a single job at a time. GitHub provides Ubuntu Linux, Microsoft Windows, and macOS runners to run your workflows; each workflow run executes in a fresh, newly-provisioned virtual machine. GitHub also offers larger runners, which are available in larger configurations. For more information, see "[Using larger runners.](https://docs.github.com/en/actions/using-github-hosted-runners/using-larger-runners)" If you need a different operating system or require a specific hardware configuration, you can host your own runners. For more information about self-hosted runners, see "[Hosting your own runners.](https://docs.github.com/en/actions/hosting-your-own-runners)"