# Shiny_Geyser_App

This app is the default Geyser app demo-ing the Shiny framework.

## Deployments

Changes are deployed to the testing or sandbox branches on the hosting server (Connect) prior to deploying to Production.

| Version    | Name                        | Link                                                                  |
|------------------|------------------------------|------------------------|
| Production | Shiny_Geyser_App_Production | [link](https://colorado.rstudio.com/rsc/Shiny_Geyser_App_Production/) |
| Testing    | Shiny_Geyser_App_Testing    | [link](https://colorado.rstudio.com/rsc/Shiny_Geyser_App_Testing/)    |
| Sandbox    | Shiny_Geyser_App_Sandbox    | [link](https://colorado.rstudio.com/rsc/Shiny_Geyser_App_Sandbox/)    |

Developers landing page is through [ConnectWidgets](https://docs.rstudio.com/how-to-guides/users/pro-tips/widgets/#:~:text=connectwidgets%20is%20an%20RStudio%2Dmaintained,Markdown%20document%20or%20Shiny%20application.) and can be accessed here (upcoming).

Push button deployment, git-backed deployment, and deployment through git actions is integrated and preferred. However publishing manually through the API is included with an example located inside the example [`deploy.R`](./.deploy_app/deploy.R) file. 


## CI / CD

UPCOMING

Refer to [this CI/CD example](https://github.com/leesahanders/learn_shinytest2_LisaBranch)for how testing and automated deployment was integrated with this example.

## Environment management

Environment and package management is being done through [renv](https://cran.r-project.org/web/packages/renv/vignettes/renv.html).

For first time set up:

    renv::init()
    renv::snapshot() 

When pulling this project to get the current supported environment:

    renv::restore()

When adding new packages (reminder to test deployments against the relevant non-production deployment prior to production deployments):

    renv::snapshot()

Additionally this project is using package versions from a freezed date. This can be updated as needed by update the line that is like:

    options(repos = c(REPO_NAME = "https://colorado.rstudio.com/rspm/cran/__linux__/focal/2022-06-29"))

After updating the repository URL and running it locally the following should be run to update the renv lock file:

    renv::hydrate() 
