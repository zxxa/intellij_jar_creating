# intellij jar creating
## how to create jars in intellij idea
### quick tutorial for H.

* Project Structure
* Artifacts
* \+ JAR -> From modules with dependencies...
* Do what you want and then check generated .xml file, because not every change is saved in this .xml, sadly
* .idea/artifacts/name.xml

### example .idea/artifacts/name.xml file
```xml
<component name="ArtifactManager">
  <artifact type="jar" name="name:jar">
    <output-path>$PROJECT_DIR$/example_jar_output_path</output-path>
    <root id="archive" name="name.jar">
      <element id="directory" name="META-INF">
 # directory for META-INF 
        <element id="file-copy" path="$PROJECT_DIR$/your_dir/META-INF/MANIFEST.MF" /> 
      </element>
      <element id="module-output" name="module1_name" />
      <element id="module-output" name="module2_name" />
 # if you have resources you get them for exmaple with getClass().getClassLoader().getResource("resource_name")
 # $PROJECT_DIR$/src/main/resources is the most probable path for your resources
      <element id="dir-copy" path="$PROJECT_DIR$/src/main/resources" />  
    </root>
  </artifact>
</component>
```

* Build
* Build Artifacts...
* Check possible bugs in console with 'java -jar name.jar'


