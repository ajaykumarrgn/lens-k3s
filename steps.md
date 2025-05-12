Before getting into the deployment steps, ensure that the following values are correctly specified in all the deployment-files:

- **Images**
- **Versions**
- **Site Name**
- **DB Service Names**
- **Created Namespace**
- **User names**
- **Passwords**
- **PV-PVC Names**
  
**Steps to be followed to create demolens site**
__________________________________________________________

kubectl create namespace lenshxm-amr

kubectl apply -n lenshxm-amr -f demo-mariadb.yaml

helm repo add frappe https://helm.erpnext.com

kubectl apply -n lenshxm-amr -f demo-site-pv-pvc.yaml

helm install lenshxm-bench -n lenshxm-amr -f demo-custom-values.yaml frappe/erpnext 

kubectl apply -n lenshxm-amr -f demo_lens-create-site.yaml

kubectl apply -n lenshxm-amr -f demo-ingressroute.yaml

______________________________________________________________________

