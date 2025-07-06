# Gitops-demo
A repo for understanding Gitops better for today and tomorrow 

# 🚀 GitOps Setup with Argo CD — Step-by-Step ✅ Pre-requisites
# Make sure these are already set up:

--> Minikube running

---> kubectl configured to point to Minikube

---> git, helm (optional), argocd CLI installed

----> A GitHub account with a repo for storing your manifests

🧱 Step 1: Install Argo CD in Minikube
-------------------------------------------------------

kubectl create namespace argocd

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

🔐 Step 2: Access Argo CD UI (via port-forward) 
-----------------------------------------------------------

kubectl port-forward svc/argocd-server -n argocd 8080:443
Now open your browser:
👉 https://localhost:8080


🔑 Login Credentials
------------------------------------------------------------
kubectl get secret argocd-initial-admin-secret -n argocd -ojsonpath="{.data.password}" | base64 -d




