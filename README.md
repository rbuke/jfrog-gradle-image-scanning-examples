<h3> JFrog Xray scanning workflows for gradle projects that use the Jib plugin to create and publish images. </h3>
</br>

Each workflow builds the image using the jib gradle plugin, scans the image using the JFrog CLI, and then publishes to Artifactory. 

</br>

<b>Workflows:</b>


<b> scan-and-publish  </b>  
* Builds the image using the jibDockerBuild gradle task
* Scans the image with Xray
* Uploads the image to Artifactory
* Publishes the build information to Artifactory.
* Recommended method as only one build of the image is required. 

<b> local-tar </b>
* Initially, the image is built as a tar using the ./gradlew jibBuildTar gradle task. 
* The tar of the image is scanned using Xray
* The image is then published to Artifactory using the jib gradle task.
* This method requires two builds which could signficantly affect the time the workflow takes to complete.

</br>
<h1> TO DO: Remove hardcoded values from workflows </h1>