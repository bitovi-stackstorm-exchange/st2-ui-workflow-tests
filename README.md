# st2-ui-workflow-tests
Stackstorm Workflow Composer Test Pack

## validate-alert

Test action that uses the `search` filter critera over an object named `alert`. For the `alert` object search will examine the `data` field of each object contained within looking for the value `foo` and if found will run a worklfow that outputs a list of the of each object's `data` fieeld. 

Provided with the `alert` object of the form:
```
{"alert": 
  [{"data":"bar","time":"6:00","type":"service"},
  {"data":"foo","time":"12:00","type":"system"},
  {"data":"baz","time":"18:00","type":"application"}]
}
```

The workflow should run and output a list of `data` values from all three objects:
```
["bar","foo","baz"]
```

If there is no `foo` object in `alert`, the workflow should not run.

To the Stackstorm UI console.
