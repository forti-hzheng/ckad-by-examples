
## check the existing daemonset

The **CoreDNS** should be run on all nodes, but in which Namespace?
Plz check and save the ds result to ~/ds.txt
```bash
k get ds -A  > ~/ds.txt
```


Plz check the kubectl / kubelet version

## Quiz

Q1 Assume you have 3 control plane and two worker , how many coredns pods will be created?

- [ ] A. 2
- [ ] B. 3
- [ ] C. 5 

<details>
  <summary> Answer </summary>
  <p><b>C</b></p>
</details>
