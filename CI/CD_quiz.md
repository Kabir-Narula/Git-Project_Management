
# GitHub & CI/CD Quiz

## Multiple Choice Questions:

1. **What is the primary purpose of a pull request in GitHub?**
   - a) To commit code to the main branch directly
   - b) To propose changes to a repository and request a review
   - c) To deploy changes to production
   - d) To reset the repository to a previous state

2. **What is GitHub Actions used for?**
   - a) Deploying code to production manually
   - b) Managing team permissions
   - c) Automating workflows like testing, building, and deploying code
   - d) Writing code reviews

3. **In a CI/CD pipeline, what does CI stand for?**
   - a) Continuous Integrity
   - b) Continuous Integration
   - c) Controlled Implementation
   - d) Code Inspection

4. **What is the purpose of a `.yml` or `.yaml` file in GitHub Actions?**
   - a) To configure workflow automation
   - b) To write code documentation
   - c) To store environment variables
   - d) To manage user roles

5. **Which of the following CI/CD tools integrates directly with GitHub repositories?**
   - a) Jenkins
   - b) Travis CI
   - c) CircleCI
   - d) All of the above

6. **What is the purpose of the `on` field in a GitHub Actions YAML file?**
   - a) To define the job environment
   - b) To trigger workflows based on events like push or pull requests
   - c) To define secrets for deployment
   - d) To configure the output directory for builds

7. **What command is used to clone a GitHub repository?**
   - a) `git fetch`
   - b) `git pull`
   - c) `git clone`
   - d) `git branch`

8. **What does the `jobs` section define in a GitHub Actions YAML file?**
   - a) A list of user roles in the project
   - b) The steps to be executed in the workflow
   - c) The environment for testing
   - d) All the secrets for deployment

9. **In CI/CD, what does CD stand for?**
   - a) Continuous Deployment
   - b) Code Delivery
   - c) Controlled Deployment
   - d) Continuous Development

10. **Which GitHub Action would you use to run unit tests on a Node.js application?**
   - a) `actions/checkout`
   - b) `setup-node`
   - c) `actions/upload-artifact`
   - d) `actions/cache`

---

## Fill in the Blanks:

1. In GitHub Actions, workflows are defined in ______ format.
2. The `______` file in a Git repository defines which files or directories should be ignored by Git.
3. CI/CD stands for Continuous Integration and Continuous ________.
4. In a pull request workflow, code must be ________ before it is merged into the main branch.
5. The `______` directory is where GitHub Actions looks for YAML configuration files.

---

## Short Answer Questions:

1. Explain the concept of Continuous Integration in the context of software development.
2. What are the benefits of using GitHub Actions for automating workflows?
3. Describe the difference between Continuous Delivery and Continuous Deployment.
4. How does the `jobs` section in a GitHub Actions YAML file help in structuring a CI/CD pipeline?
5. Why is it important to use pull requests for deploying code in collaborative projects?

---

## True/False Questions:

1. **YAML files are used in GitHub Actions to configure workflows.** (True/False)
2. **GitHub Actions workflows can only be triggered by manual events.** (True/False)
3. **Continuous Deployment ensures that every change that passes automated tests is deployed to production automatically.** (True/False)
4. **The `.gitignore` file specifies which files Git should automatically commit.** (True/False)
5. **CI/CD pipelines are only useful for large teams and projects.** (True/False)

---

## Advanced Questions:

1. **Explain how GitHub Actions can be integrated with other CI/CD tools like Jenkins or CircleCI in larger pipelines.**
2. **Describe how you would configure a GitHub Actions workflow to automatically build and test a Python project.**
3. **In YAML-based CI/CD workflows, how do you define environment variables and how can they be securely passed during deployment?**
4. **How do pull requests enhance code quality and collaboration in a GitHub-based development workflow?**
5. **What are the advantages of using a dedicated CI/CD tool (like Travis CI or CircleCI) compared to GitHub Actions?**

---

## **Answer Key**:

### Multiple Choice:
1. b) To propose changes to a repository and request a review
2. c) Automating workflows like testing, building, and deploying code
3. b) Continuous Integration
4. a) To configure workflow automation
5. d) All of the above
6. b) To trigger workflows based on events like push or pull requests
7. c) `git clone`
8. b) The steps to be executed in the workflow
9. a) Continuous Deployment
10. b) `setup-node`

### Fill in the Blanks:
1. YAML
2. `.gitignore`
3. Deployment
4. Reviewed
5. `.github/workflows`

### Short Answer:
1. **Continuous Integration**: CI refers to the practice of merging all developer working copies to a shared mainline frequently to detect issues early.
2. **Benefits of GitHub Actions**: GitHub Actions simplifies automation, offers native integration with GitHub, and allows workflows to be triggered by events such as pushes or pull requests.
3. **Continuous Delivery vs. Deployment**: Continuous Delivery requires manual approval before deployment, while Continuous Deployment automates the release after passing tests.
4. **Jobs Section**: The `jobs` section allows the definition of multiple tasks (jobs) to be executed, which can run sequentially or in parallel.
5. **Pull Requests for Collaboration**: They provide an organized review process, enabling team members to comment, test, and ensure code quality before merging.

### True/False:
1. True
2. False
3. True
4. False
5. False
