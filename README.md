# Solsta Promote Action for GitHub

This project is a GitHub Action that uses Solid State Networks tools and services to promote a release from one repository to another, or to the head of a single repository.  

The action is compatible with Windows, Linux, and OSX runners.  Windows self-hosted runners require git-bash (https://git-scm.com/) in the %PATH%.

## Variables

* **solsta_client_id:** Client ID to authenticate usage of Solid State Networks console tools
* **solsta_client_secret:** Secret Key to authenticate usage of Solid State Networks console tools
* **console_version:** Version of Solsta Console Tools to use
* **scripts_version:** Version of Solsta Deploy Scripts to use
* **source_product:** Source product to promote from (case-sensitive)
* **source_environment:** Source environment to promote from (case-sensitive)
* **source_repository:** Source repository to promote from (case-sensitive)
* **target_product:** Target product to promote to (case-sensitive)
* **target_environment:** Target environment to promote to(case-sensitive)
* **target_repository:** Target repository to promote to (case-sensitive)

## Using

Here is an example YAML Fragment in the steps section of a build:

```yaml
    steps:
    - name: Promote a Release from Dev to QA
      uses: snxd/deploy-github-promote-action@v3
      with:
        console_version: '6.1.2.84'
        scripts_version: '3.8.2'
        source_product: 'Emutil'
        source_environment: 'Java'
        source_repository: 'Dev'
        target_product: 'Emutil'
        target_environment: 'Java'
        target_repository: 'QA'
        solsta_client_id:  ${{ secrets.SOLSTA_CLIENT_ID }}
        solsta_client_secret:  ${{ secrets.SOLSTA_CLIENT_SECRET }}
```

## License
(C) 2022 Solid State Networks, LLC.  All Rights Reserved.
