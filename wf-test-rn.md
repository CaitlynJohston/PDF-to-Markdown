###### Submitted by Caitlyn Johnston - 22 Jan 2022.

# Version 10.2

#### <font color="#00CCFF">**RELEASE DATE**</font>

October 30, 2020

The new Intelligent Automation Cloud v.10.2 provides you with a set of innovations to increase productivity and simplify your routine work. The release includes but is not limited to the following features:

- **WorkSpace 2.0** is a human-in-the-loop tool designed to tackle various issues with the exception-handling process that allows faster completion and improves compliance. Compared to the previous version, WorkSpace 2.0 has stronger features that enable you to manipulate and adjust the workflow. 
- With the new **A/B testing** feature, validate automation variations, review Analytics dashboards for test results, and choose the most confident automation version, thus improving the performance of the pre-trained bots. 
- Start **Automated Retraining** with a collected training set. This includes the estimated duration, and Analytics for validating models. The bot retraining workflow is even friendlier to business users, and is now available in the Control Tower UI.
- New **centralized user management and role-based access control** rule all the ecosystem components, including Analytics dashboards and WorkSpace. 
- **Analytics** introduces 20 new data points, drill-down capability, improved navigation, and simplified, user-friendly analysis. 
- **Intelligent Automation Cloud Developer** improvements include the new Launcher application for components management and more to your local development environment. 
- **ML SDK** extensions address complex problems, including but not limited to hybrid models, grouping, and classification cascade training. 
- **Optimized orchestration** of services allows you to reduce hardware requirements to 11 servers for a high-availability environment. 
- Additional bug fixes, improvements, and deprecations address user requests and solve earlier flaws.

For more information on each improvement, see detailed descriptions below.


### A/B-Testing of Use Cases

This functionality enables you to easily test adjustments or new versions of automation and gather key metrics to determine whether or not to implement these changes in the production environment.

The intuitive workflow makes the whole procedure easy to run, with data available for comparison after actual testing.

A/B tests facilitate the following:

- Safely run either historical or live data through a new version without impacting the original version.
- Manage variations of business processes to be tested.
- Test updated manual task efficiency and routing.
- Automatically gather data to measure and compare two different versions.
- Analyze business metrics and compare versions.

## Bug fixes

### Infrastructure

- Fixed Logstash startup failures and secrets not taken from Secrets Vault.
- Fixed a bug with not working jobs when cloning from the current directory. <font color="#a569bd"> NOTE: I would ask for clarification and rewrite it.</font>
- Fixed a Logstash certificate error that prevented startup.
- Fixed an issue on the "Run postmigrate SQL script" step. <font color="#a569bd"> NOTE: I'd like this to be more specific so I would ask for clarification and rewrite it.</font>
- Ports prechecker is now working when the FirewallD service blocks
  ports.
- The update_artifacts task now works when running on the HA
  environment.
- Fixed a Liquibase error when upgrading. <font color="#a569bd"> NOTE: Upgrading or updating?. I'd clarify and get more specific information. Check against the Release Notes?</font>


