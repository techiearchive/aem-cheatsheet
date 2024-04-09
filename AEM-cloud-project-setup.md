# Create new AEM Cloud Project
Maven command to create new AEM cloud project with archetype version 39
```
 mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate \
    -D archetypeGroupId=com.adobe.aem \
    -D archetypeArtifactId=aem-project-archetype \
    -D archetypeVersion=39 \
    -D appTitle="Techiearchive AEM Project" \
    -D appId="techiearchive-aem" \
    -D groupId="techiearchive.aem" \
    -D artifactId="techiearchive-aem" \
    -D package="techiearchive.aem" \
    -D version="0.0.1-SNAPSHOT" \
    -D aemVersion="cloud" \
    -D includeExamples=n
```
## Useful Links
* [Project Setup Guide](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/project-setup)
* [Removing Samples From AEM Cloud Project](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/developing/aem-projects/remove-samples)
* [AEM Project Archetype](https://github.com/adobe/aem-project-archetype)
* [AEM Cloud Integration with Git](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/managing-code/integrating-with-git)
* [Deploy Code into AEM Cloud](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/cloud-manager/devops/deploy-code)
* [Managing Environments](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/manage-environments)
* [Sync Git Repository with Adobe Git Manually](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/issue-sync-project-git-repository-to-adobe-git-manual-way/m-p/600491)
* [AEM Cloud Rapid Development Environment](https://medium.com/@toimrank/adobe-cloud-manager-rapid-development-environments-rdes-7a7a36c50b9)



