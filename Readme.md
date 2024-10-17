#pre-reqs
You will need to brew-install git-crypt
possibly brew install gpg

In this demo `helm/testapp1` and `kustomize/testapp2` values are encrypted while the others are not - you can verify this by trying to see the files locally or in the web browswer
You can find the encrpytion key in 1pass
Create a file that contains that key locally 
To see the contents of the file locally run
`git-crypt unlock /path/to/key`
Then you can see the contents of the encrypted values file and run `helm install whatever`

What is encrypted is defined in the `.gitattributes` file
```
git-crypt status
not encrypted: helm/testapp1/.gitattributes
    encrypted: helm/testapp1/values-developement.yaml
    encrypted: helm/testapp1/values-staging.yaml
not encrypted: helm/testapp2/values-developement.yaml
not encrypted: helm/testapp2/values-staging.yaml
not encrypted: kustomize/testapp1/values-developement.yaml
not encrypted: kustomize/testapp1/values-staging.yaml
not encrypted: kustomize/testapp2/.gitattributes
    encrypted: kustomize/testapp2/values-developement.yaml
    encrypted: kustomize/testapp2/values-staging.yaml```