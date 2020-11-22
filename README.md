# Reading-Task-4

### Objectives

The "twelve-factor app" is a name of methodology for building modern software services and applications.

It can be seen as a quality-standard set of recommendations for developers.

Your task is to

- research Internet sources discussing these recommendations
- based on your findings, try to re-order (re-number) the known factors according selected priority criteria
- be ready to argument these criteria in class
- Submit here the updated list of twelve factors, as well as a bibliography of the sources you have used to create it.

---

### Task

I found this assignment very difficult to solve as all twelve steps make sense to use and I believe the steps have remained in the same position for so long for a reason. All of the steps are important when writing an application, however not all of the factors need to be in the specific order.
If I could I wouldn't change anything about the twelve factor app but because the assignment says to re-order the factors I have tried to do so. But as just stated, I only reordered some of the factors that I believe can be done in more than one specific order.

### Original vs Re-ordered twelve factor app

| Original                                                                                      | Re-ordered                                                                                    |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **1. Codebase** <br/>One codebase tracked in revision control, many deploys                   | **1. Codebase** <br/>One codebase tracked in revision control, many deploys                   |
| **2. Dependencies** <br/>Explicitly declare and isolate dependencies                          | **2. Dependencies** <br/>Explicitly declare and isolate dependencies                          |
| **3. Config** <br/>Store config in the environment                                            | **3. Config** <br/>Store config in the environment                                            |
| **4. Backing services** <br/>Treat backing services as attached resources                     | **4. Processes** <br/>Execute the app as one or more stateless                                |
| **5. Build, release, run** <br/>Strictly separate build and run stages                        | **5. Port binding** <br/>Export services via port binding                                     |
| **6. Processes** <br/>Execute the app as one or more stateless processes                      | **6. Backing services** <br/>Treat backing services as attached resources                     |
| **7. Port binding** <br/>Export services via port binding                                     | **7. Build, release, run** <br/>Strictly separate build and run stages                        |
| **8. Concurrency** <br/>Scale out via the process model                                       | **8. Concurrency** <br/>Scale out via the process model                                       |
| **9. Disposability** <br/>Maximize robustness with fast startup and graceful shutdown         | **9. Disposability** <br/>Maximize robustness with fast startup and graceful shutdown         |
| **10. Dev/prod parity** <br/>Keep development, staging, and production as similar as possible | **10. Dev/prod parity** <br/>Keep development, staging, and production as similar as possible |
| **11. Logs** <br/>Treat logs as event streams                                                 | **11. Logs** <br/>Treat logs as event streams                                                 |
| **12. Admin processes** <br/>Run admin/management tasks as one-off processes                  | **12. Admin processes** <br/>Run admin/management tasks as one-off processes                  |

---

#### Explanation of the original twelve factor app

**1. Codebase**
Every deployment should have its own code repository that can be deployed to multiple environments. Avoid housing multiple applications in the same repository.

**2. Dependencies**
A 12-factor app must be self-containing. The application should be isolated sufficiently to avoid interactions with conflicting libraries that are installed on the host machine.

**3. Config**
A separate config file makes it easy to update the config values without touching the actual code base, eliminating the need for re-deployment of your applications when you change certain config values.

**4. Backing services**
Any services that don’t support the core app must be accessed as a service. They should be accessed as a service via HTTP or similar request, then specified in the config. This way, the service’s source can be changed without affecting the app’s core code.

**5. Build, release, run**
Store the app in source control in the build process. Then build out its dependences. Separate the config information so you can combine it with the build for the release stage — then it’s ready for the run stage. Each release should have a unique ID.

**6. Processes**
Store any data that is required to persist in a stateful backing service, such as databases. The idea is that the process is stateless and shares absolutely nothing.

**7. Port binding**
Twelve-factor apps must always be independent from additional applications. Every function should be its own process—in full isolation. Add a web server library or similar to the core app so it can wait requests on a defined port, whether that’s HTTP or a different protocol.

**8. Concurrency**
Build your applications so that scaling them in the cloud is seamless. When you develop the app to be concurrent, you can spin up new instances to the cloud effortlessly. In order to add more capacity (start additional processes on additional machines), your app should be able to add more instances instead of more memory or CPU on the local machine.

**9. Disposability**
The concept of disposable processes means that an application can die at any time, but it won’t affect the user. The app can be replaced by other apps, or it can start right up again.

**10. Dev/prod parity**
Applications deployed to development and production should have parity. Essentially, there should be only the slightest difference between both deployments. A vast difference may lead to unintended compatibility issues between dev and production code.

**11. Logs**
You should stream logs to a chosen location—not simply dump them into a log file. As new processes start or your app crashes, the logs should be distributed across several cloud machines so they won’t sit on a single machine or host.

**12. Admin processes**
Separate the administrative tasks from the rest of your application (migrating database, inspecting records, etc.). You must continue to run admin processes in the same environment and against the base code and config of the app itself. Shipping the admin tasks code alongside the application prevents drift.

#### References

[The 12-Factor App Methodology Explained](https://www.bmc.com/blogs/twelve-factor-app/)  
[Is the Twelve-Factor App methodology correct?](https://www.quora.com/Is-the-Twelve-Factor-App-methodology-correct)  
[The Twelve-Factor App: Is this still relevant in today's world, or just something to aspire to?](https://www.reddit.com/r/programming/comments/4lo4kv/the_twelvefactor_app_is_this_still_relevant_in/)  
[The Twelve-Factor App — A Successful Microservices Guideline](https://dev.to/simon_sugob/the-twelve-factor-appa-successful-microservices-guideline-3a1h)
