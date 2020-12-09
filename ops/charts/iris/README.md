Oncall chart
==========

Usage
-----

```
helm3 dep update

tar -xvzf charts/mysql-0.2.6.tgz -C charts/
sed -i 's:extensions/v1beta1:apps/v1:' charts/mysql/templates/deployment.yaml
sed -e '11i\      app: {{ template "fullname" . }}' -i charts/mysql/templates/deployment.yaml
sed -e '11i\    matchLabels:' -i charts/mysql/templates/deployment.yaml
sed -e '11i\  selector:' -i charts/mysql/templates/deployment.yaml

helm3 install oncall .
```
