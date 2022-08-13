# Grails Plugin Property Source Demo

Note:
> This is a bug in Grails 5

Get Grails config and Environment from plugins' propertySources: 

## Comment propertySource

`plugins/comment/src/main/resources/plugin.yml`

```yml
hello: world
```

Result:
```
${applicationContext.environment.getProperty("grails.plugins.comment.hello", String.class)} = world
${grailsApplication.config.getProperty("grails.plugins.comment.hello", String.class)} = world
${grailsApplication.config.grails.plugins.comment.hello} = world
${applicationContext.environment.getProperty("hello", String.class)} = world
${grailsApplication.config.getProperty("hello", String.class)} = world
```

## Tag propertySource

`plugins/tag/src/main/resources/plugin.groovy`

```groovy
mytag = 'Grails'
```

Result:
```
${applicationContext.environment.getProperty("grails.plugins.tag.mytag", String.class)} = Grails
${grailsApplication.config.getProperty("grails.plugins.tag.mytag", String.class)} = Grails
${grailsApplication.config.grails.plugins.tag.mytag} = Grails
${applicationContext.environment.getProperty("mytag", String.class)} = Grails
${grailsApplication.config.getProperty("mytag", String.class)} = Grails
```
