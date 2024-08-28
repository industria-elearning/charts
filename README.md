kubectl --kubeconfig=./ie/ie-mx-kubeconfig.yaml -n production get pods

kubectl --kubeconfig=./ie/ie-mx-kubeconfig.yaml -n production exec asoban-moodle-6b4b4bc776-qxs8g -it -- bash

