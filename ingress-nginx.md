# kubernetes/ingress-nginx

A small docs change, added as part of an old job.

## Commit

```text
commit 72de2600d776873ef4ecf907bd798c2d27fb8fb3
Author: Ashley Davis <...>
Date:   Tue Oct 9 22:10:56 2018 +0100

    Add some extra detail to the client cert auth example

    Multiple people within my work organisation were caught out by the fact
    that the trusted client cert issuers must be given in a file named
    `ca.crt` and that other filenames will fail to work.

    This change makes it more clear to those who stumble across the
    documentation that this is a potential gotcha.

diff --git a/docs/examples/auth/client-certs/README.md b/docs/examples/auth/client-certs/README.md
index 04e44661a..e0dd1efe0 100644
--- a/docs/examples/auth/client-certs/README.md
+++ b/docs/examples/auth/client-certs/README.md
@@ -1,11 +1,11 @@
 # Client Certificate Authentication
+It is possible to enable Client Certificate Authentication using additional annotations in Ingress resources, created by you.
 
-It is possible to enable Client Certificate Authentication using additional annotations in the Ingress.
+## Setup Instructions
+1. Create a file named `ca.crt` containing the trusted certificate authority chain to verify client certificates. All of the certificates must be in PEM format.  
+   *NB:* The file containing the trusted certificates must be named `ca.crt` exactly - this is expected to be found in the secret.
 
-## Setup instructions
-1. Create a file named `ca.crt` containing the trusted certificate authority chain (all ca certificates in PEM format) to verify client certificates. 
- 
-2. Create a secret from this file:
+2. Create a secret from this file:  
 `kubectl create secret generic auth-tls-chain --from-file=ca.crt --namespace=default`
 
-3. Add the annotations as provided in the [ingress.yaml](ingress.yaml) example to your ingress object.
\ No newline at end of file
+3. Add the annotations as provided in the [ingress.yaml](ingress.yaml) example to your own ingress resources as required.
diff --git a/docs/examples/auth/client-certs/ingress.yaml b/docs/examples/auth/client-certs/ingress.yaml
index 215727b0b..559a483da 100644
--- a/docs/examples/auth/client-certs/ingress.yaml
+++ b/docs/examples/auth/client-certs/ingress.yaml
@@ -5,6 +5,7 @@ metadata:
     # Enable client certificate authentication
     nginx.ingress.kubernetes.io/auth-tls-verify-client: "on"
     # Create the secret containing the trusted ca certificates with `kubectl create secret generic auth-tls-chain --from-file=ca.crt --namespace=default`
+    # NB: The file _must_ be named "ca.crt" and nothing else. This filename is expected to be found in the secret.
     nginx.ingress.kubernetes.io/auth-tls-secret: "default/auth-tls-chain"
     # Specify the verification depth in the client certificates chain
     nginx.ingress.kubernetes.io/auth-tls-verify-depth: "1"
```
