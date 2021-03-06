# SLO

## 1. Install Grafana Operator
Use ```https://www.techbeatly.com/2020/03/install-grafana-operator-on-openshift-container-platform-4.html#.Xw8UCZNKhb9``` for directions to install and configure Grafana operator. Make sure you create the Grafana instance in a new project.

## 2. Apply rules for kubeapi
```rules-kubeapi.yaml```  this is the prometheusrule for the kubeapi. Apply it to cluster with ```oc apply -f rules-kubeapi.yaml```

## 3. Apply alerts for kubeapi
```alerts-kubeapi.yaml``` this is the prometheusrule for the alerts(it's configured with slack, you can modify it to reach your own slack channel). Apply it with ```oc apply -f alerts-kubeapi.yaml```

## 4. Observe Grafana route
Look for the route in your new project with ```oc get route -n (newprojectname)```

## 5. Authentication
Login to your grafana instance the user and password should be ```root``` and ```secret```if you didn't change it.

## 6. Import Grafana dashboards
import the three Grafana dashboards once you're new Grafana instance is up. (the dashboards are the files that are in .json)
