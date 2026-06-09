# AUTOPROXY_RPC_SERVER::DoGetProxyForUrl(IGetProxyForUrlCompletionEx *,tagProxyResolveUrl const *,tagProxySettings const *,_SESSION_OPTIONS const *,ulong,int,int,void *,_SID *,IUnknown *,IProxyResult * *)

- ea: `0x180050d90`
- end: `0x18005105e`
- name: `?DoGetProxyForUrl@AUTOPROXY_RPC_SERVER@@QEAAJPEAUIGetProxyForUrlCompletionEx@@PEBUtagProxyResolveUrl@@PEBUtagProxySettings@@PEBU_SESSION_OPTIONS@@KHHPEAXPEAU_SID@@PEAUIUnknown@@PEAPEAUIProxyResult@@@Z`
- size: `718`
- prototype: `__int64 __usercall@<rax>(AUTOPROXY_RPC_SERVER *__hidden this@<rcx>, struct IGetProxyForUrlCompletionEx *@<rdx>, const struct tagProxyResolveUrl *@<r8>, const struct tagProxySettings *@<r9>, const struct _SESSION_OPTIONS *, unsigned int, int, int, void *, struct _SID *, struct IUnknown *, struct IProxyResult **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180050aa0`
- `0x1800ac9c0`

## callees

- `0x180050d90`
- `0x180051070`
- `0x1800a1d10`
- `0x1800cfe48`
- `0x1800db6b0`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180050e75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180050e75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180050efe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180050f5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180050efe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180050f5d`

## pseudocode

```c

```
