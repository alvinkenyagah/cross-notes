PRODEV NOTES

## GIT FLOW


1) `sudo apt-get install git-flow` ----------- Install git flow

2) `git flow init`  ----- Defines the branches  ie production branch (main) 
                                                                    development branch 

3)  `git push --set-upstream origin development` ------ push the local branch to the remote repository


4) `git flow feature start feature_branch`  -------- Create a feature branch named 'feature_branch' based on development branch



5)  `git flow feature finish feature_branch` ---------- After working on features and wouldl like to push the complete features to the development branch


6)  `git flow release start '0.1.0'` --------- Creates a release branch 

7)   `git push --set-upstream origin release/0.1.0`

8) `git flow release finish '0.1.0'` ------ Merges to main ad development branch 

9)
`git checkout main` -------------|
                                                  ----> Checkout to the main and git push to push changes from release to main
`git push`       --------------------|


10) `git tag -l`  ----------------- shows version of number of the project




_________________________________________________________________________________________________________________

## START POSTGRESQL SERVER

1) sudo service postgresql start

DELETE FEATURE BRANCH
____________________________

`git push origin --delete feature/login-signup`


==> sendgrid  

## DEPLOYING


`https://betterprogramming.pub/how-to-deploy-an-api-only-ruby-on-rails-application-to-render-6012a19ba2cd`


## UPDATE REACT AND IT DEPENDANCIES

`https://www.delftstack.com/howto/react/update-react-version/`




## DEPLOYMENT

Access rails masterkey: 

 `EDITOR=nano rails credentials:edit`
