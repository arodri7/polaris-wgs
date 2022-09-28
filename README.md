# polaris-wgs
Running tests for NGS analysis on [Polaris ALCF](https://www.alcf.anl.gov/polaris)

I will be testing several NGS tools for fast throughput analysis of WGS on Polaris.

## NVIDIA Clara Parabricks
First we will try [NVIDIA Clara-Parabricks](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/clara/containers/clara-parabricks). 
The container is distributed via Docker and unfortunately Polaris does not allow usage of Docker. In order to use Parabricks within Polaris we must first create a Singularity container:
```
$module load singularity/3.8.7
$singularity  build parabricks-4.0 docker://nvcr.io/nvidia/clara/clara-parabricks:4.0.0-1
INFO:    Starting build...
Getting image source signatures
Copying blob d7bfe07ed847 done
Copying blob bbbbd451a669 done
Copying blob 773163705c35 done
Copying blob d6949fcf1aef done
Copying blob 3eb73064088b done
Copying blob a3ac3ab0ee35 done
Copying blob 8d88682a5e1d done
Copying config 41b997ec10 done
Writing manifest to image destination
Storing signatures
2022/09/28 19:08:34  info unpack layer: sha256:d7bfe07ed8476565a440c2113cc64d7c0409dba8ef761fb3ec019d7e6b5952df
2022/09/28 19:08:34  warn xattr{etc/gshadow} ignoring ENOTSUP on setxattr "user.rootlesscontainers"
2022/09/28 19:08:34  warn xattr{/tmp/build-temp-256462640/rootfs/etc/gshadow} destination filesystem does not support xattrs, further warnings will be suppressed
2022/09/28 19:08:35  info unpack layer: sha256:bbbbd451a669065c9ef688d0d43e47f20ae334efda40dfc323d82fd342763976
2022/09/28 19:08:35  warn xattr{var/log/apt/term.log} ignoring ENOTSUP on setxattr "user.rootlesscontainers"
2022/09/28 19:08:35  warn xattr{/tmp/build-temp-256462640/rootfs/var/log/apt/term.log} destination filesystem does not support xattrs, further warnings will be suppressed
2022/09/28 19:08:35  info unpack layer: sha256:773163705c35e00e6c9cdb84e4e8db9079b8777f8f3f62839ec2008af668f939
2022/09/28 19:08:36  warn xattr{var/log/apt/term.log} ignoring ENOTSUP on setxattr "user.rootlesscontainers"
2022/09/28 19:08:36  warn xattr{/tmp/build-temp-256462640/rootfs/var/log/apt/term.log} destination filesystem does not support xattrs, further warnings will be suppressed
2022/09/28 19:08:36  info unpack layer: sha256:d6949fcf1aef0c0e95826220c5f2731c2909492c994d70707d8c93eb4c815b99
2022/09/28 19:08:36  info unpack layer: sha256:3eb73064088b62826e9ea4b1bcbd9b10270f134e45f6436214db7c8ebed6052b
2022/09/28 19:08:36  info unpack layer: sha256:a3ac3ab0ee351d7e137a83615b01acb272d3b091c745163fb506cdf7b96c077b
2022/09/28 19:08:37  warn xattr{usr/local/lib/python3.8} ignoring ENOTSUP on setxattr "user.rootlesscontainers"
2022/09/28 19:08:37  warn xattr{/tmp/build-temp-256462640/rootfs/usr/local/lib/python3.8} destination filesystem does not support xattrs, further warnings will be suppressed
2022/09/28 19:09:23  info unpack layer: sha256:8d88682a5e1dfc9375ea4a4834e5aff43e780f2c6e82ddbec89eabbd5a9800fa
2022/09/28 19:09:23  warn xattr{var/cache/apt/archives/partial} ignoring ENOTSUP on setxattr "user.rootlesscontainers"
2022/09/28 19:09:23  warn xattr{/tmp/build-temp-256462640/rootfs/var/cache/apt/archives/partial} destination filesystem does not support xattrs, further warnings will be suppressed
INFO:    Creating SIF file...
INFO:    Build complete: parabricks-4.0
```

Now we can go ahead and test a simple job to see if our Singularity container build was a success.

```

```

