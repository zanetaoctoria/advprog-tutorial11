# Reflection Hello Minikube

### 1. Compare the application logs before and after you exposed it as a Service.

**Before:**

![image 1](image/image1.png)
**After:**
![image 2](image/image2.png)

There is a noticeable difference in the logs before and after exposing the application as a Service. After exposing, the logs include additional entries that show which endpoints were accessed on the localhost IP, along with the HTTP methods used. The number of log entries corresponds to how many times the service was accessed.

---

### 2. Notice that there are two versions of the `kubectl get` command used in this tutorial. The first version has no options, while the second uses the `-n` option with the value `kube-system`. What is the purpose of the `-n` option, and why didn't the output list the pods/services you explicitly created?

The `-n` option in the `kubectl get` command specifies the namespace in which Kubernetes should search for resources like pods, services, etc.

By default, when you run `kubectl get` without the `-n` option, Kubernetes looks in the `default` namespace. However, when using `-n kube-system`, Kubernetes searches in the `kube-system` namespace instead, which is a special namespace used for system components and internal services like `kube-dns` and `kube-proxy`. That’s why the output didn’t include the pods or services you created — they were created in the `default` namespace, not in `kube-system`.
