# ResolveClientOXID(void *,CProcess *,unsigned __int64 &,tagDUALSTRINGARRAY const *,ushort,ushort *,__MIDL_ILocalObjectExporter_0007 *,unsigned __int64 *,int,ushort,ulong,uchar *,bool,bool,int *,ulong *,uchar * *,ushort *)

- ea: `0x180031be0`
- end: `0x1800341ea`
- name: `?ResolveClientOXID@@YAKPEAXPEAVCProcess@@AEA_KPEBUtagDUALSTRINGARRAY@@GPEAGPEAU__MIDL_ILocalObjectExporter_0007@@PEA_KHGKPEAE_N8PEAHPEAKPEAPEAE4@Z`
- size: `9738`
- prototype: `unsigned int __usercall@<eax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, struct CProcess *@<rdx>, unsigned __int64 *@<r8>, const struct tagDUALSTRINGARRAY *@<r9>, unsigned __int16, unsigned __int16 *, struct __MIDL_ILocalObjectExporter_0007 *, unsigned __int64 *, int, unsigned __int16, unsigned int, unsigned __int8 *, bool, bool, int *, unsigned int *, unsigned __int8 **, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `41`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180030b10`
- `0x180040af0`
- `0x180069a90`

## callees

- `0x18001a780`
- `0x18001a7a0`
- `0x18001c624`
- `0x18001d134`
- `0x180031be0`
- `0x180034260`
- `0x180036644`
- `0x1800366bc`
- `0x180036ac0`
- `0x180036cb8`
- `0x1800375e0`
- `0x180037c10`
- `0x18003895c`
- `0x18004b524`
- `0x180052540`
- `0x180057288`
- `0x1800588a4`
- `0x18005b8ec`
- `0x18006920c`
- `0x18008a028`
- `0x180095c0c`
- `0x18009de74`
- `0x18009dfb4`
- `0x18009e160`
- `0x1800a13fc`
- `0x1800a31cc`
- `0x1800a4824`
- `0x1800a4b3c`
- `0x1800a5340`
- `0x1800a6474`
- `0x1800a64e4`
- `0x1800a6670`
- `0x1800a7304`
- `0x1800a78c8`
- `0x1800a7a14`
- `0x1800b7ac0`
- `0x1800c6fec`
- `0x1800c7294`
- `0x1800cb32c`
- `0x180112d84`
- `0x180114010`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800325e0`
- `RPCRT4!RpcBindingFree` at `0x180032db9`
- `RPCRT4!RpcBindingFree` at `0x180032f63`
- `RPCRT4!RpcBindingFree` at `0x18003306c`
- `RPCRT4!RpcBindingFree` at `0x1800331b6`
- `RPCRT4!RpcBindingFree` at `0x180033374`
- `RPCRT4!RpcBindingFree` at `0x1800333ea`
- `RPCRT4!RpcBindingFree` at `0x1800325e0`
- `RPCRT4!RpcBindingFree` at `0x180032db9`
- `RPCRT4!RpcBindingFree` at `0x180032f63`
- `RPCRT4!RpcBindingFree` at `0x18003306c`
- `RPCRT4!RpcBindingFree` at `0x1800331b6`
- `RPCRT4!RpcBindingFree` at `0x180033374`
- `RPCRT4!RpcBindingFree` at `0x1800333ea`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800328ca`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800328ca`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800329f8`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800329f8`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032473`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003250c`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032573`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032590`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800325ef`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032dc8`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032f72`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003307b`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800331c5`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003338b`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800333f9`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032473`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003250c`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032573`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032590`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800325ef`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032dc8`
- `RPCRT4!RpcRevertToSelfEx` at `0x180032f72`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003307b`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800331c5`
- `RPCRT4!RpcRevertToSelfEx` at `0x18003338b`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800333f9`
- `RPCRT4!RpcImpersonateClient` at `0x1800323bd`
- `RPCRT4!RpcImpersonateClient` at `0x1800323bd`
- `RPCRT4!NdrClientCall2` at `0x180032b54`
- `RPCRT4!NdrClientCall2` at `0x180032b54`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180031f3e`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180031f3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003270b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032955`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032977`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032c31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032cf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032d7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032d9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032f29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032f46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003304f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003317c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033199`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003333a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033357`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800333cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800339cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033ae8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033b51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033d25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034077`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003270b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032955`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032977`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032c31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032cf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032d7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032d9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032f29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032f46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033032`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003304f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003317c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033199`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003333a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033357`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800333cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800339cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033ae8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033b51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033d25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034077`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032688`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032688`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a3b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800320ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800320ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800320d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800320d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031d82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003210b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003225b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032de7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033093`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800331dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033418`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033540`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800336b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033968`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033b6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033d47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034092`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031d82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003210b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003225b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032de7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033093`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800331dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033418`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033540`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800336b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033968`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033b6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033d47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034092`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031dc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031e37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031f9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032243`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032380`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800330ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003384c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800338cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800338f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800339ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033ac3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033b2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033c8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033e6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033e9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800341b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031dc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031e37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031f9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032243`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032380`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800330ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003384c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800338cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800338f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800339ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033ac3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033b2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033c8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033e6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033e9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800341b7`

## string_xrefs

- `0x180032084`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x180031ce5`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180031d46`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180031db2`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180031e20`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18003216d`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18003221d`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800323d6`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18003245c`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800324f5`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032559`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800325bb`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032856`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800328e5`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800329d4`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032a0f`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032add`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032b9e`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032bce`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032c51`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032d5b`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032eff`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180032ff9`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180033123`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18003314d`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800333a3`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180033520`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18003368e`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180033829`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800338b5`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180033996`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180033aa5`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180033b15`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x180033ce2`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800322c7`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180032341`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180032e6a`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180033259`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x1800332d2`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180033484`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x1800335ac`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180033626`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x18003371d`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180033797`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180033bd7`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180033c50`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180033db3`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180033e2d`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x1800340fe`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180034178`: `onecore\com\combase\rpcss\objex\coxid.hxx`
- `0x180032752`: `Using authn service:%x SPN:%ws`
- `0x180032822`: `Using authn service:%x SPN:%ws`
- `0x180032989`: `Using authn service:%x SPN:%ws`
- `0x180032a29`: `Using authn service:%x SPN:%ws`

## pseudocode

```c
__int64 __fastcall ResolveClientOXID(
        RPC_BINDING_HANDLE BindingHandle,
        struct CProcess *a2,
        unsigned __int64 *a3,
        const struct tagDUALSTRINGARRAY *a4,
        unsigned __int16 a5,
        unsigned __int16 *a6,
        struct __MIDL_ILocalObjectExporter_0007 *a7,
        unsigned __int64 *a8,
        int a9,
        unsigned __int16 a10,
        unsigned int a11,
        unsigned __int8 *a12,
        bool a13,
        bool a14,
        int *a15,
        unsigned int *a16,
        unsigned __int8 **a17,
        unsigned __int16 *a18)
{
  struct __MIDL_ILocalObjectExporter_0007 *v20; // r13
  unsigned __int64 *v21; // r15
  unsigned __int16 *v22; // r10
  unsigned __int8 *v23; // rdi
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // ebx
  const WCHAR *v28; // rax
  unsigned int v29; // eax
  unsigned int v30; // ebx
  unsigned int v31; // edx
  unsigned int v32; // eax
  unsigned int v33; // ebx
  ObjexHashTable::CHashTable *v34; // rbx
  unsigned __int8 *v35; // r14
  __int64 v36; // rsi
  CClientOxid *v37; // rbx
  int v38; // r14d
  unsigned int v39; // ebx
  __int64 v40; // rcx
  bool v41; // r9
  int PrimaryOxidInfoFromOxidInfo; // eax
  unsigned __int16 v43; // bx
  unsigned int Pointer; // esi
  struct CClientOxid *v45; // rdi
  struct CClientOxid *v46; // rdi
  const struct tagDUALSTRINGARRAY *v47; // rcx
  unsigned int v48; // eax
  bool v49; // r8
  volatile signed __int32 *v50; // rbx
  unsigned int v51; // edi
  __int64 v52; // rdx
  unsigned __int16 *v53; // rcx
  int v54; // eax
  unsigned int v55; // eax
  CMid *v56; // rcx
  unsigned int v57; // edx
  unsigned int v58; // r9d
  unsigned int v59; // r13d
  unsigned __int16 *MachineName; // rbx
  __int64 v61; // rax
  unsigned __int64 v62; // rsi
  SIZE_T v63; // rax
  unsigned __int64 v64; // kr00_8
  unsigned __int16 *v65; // rax
  unsigned __int16 *v66; // rdi
  __int64 v67; // rcx
  const unsigned __int16 *v68; // r9
  unsigned __int64 v69; // r8
  unsigned __int16 *v70; // rcx
  unsigned __int16 v71; // r8
  const wchar_t *v72; // r10
  CRpcSecurityCallbackManager *v73; // rcx
  unsigned __int16 v74; // r15
  unsigned __int16 v75; // bx
  int v76; // eax
  unsigned int v77; // r9d
  unsigned int v78; // r8d
  unsigned int v79; // eax
  CRpcSecurityCallbackManager *v80; // rcx
  void *v81; // r8
  void *v82; // r8
  unsigned int v83; // eax
  CRpcSecurityCallbackManager *v84; // rcx
  CRpcSecurityCallbackManager *v85; // rcx
  void *v86; // r8
  int SecurityContextDetailsAndTurnOffCallback; // esi
  void *v88; // r8
  unsigned __int8 *v89; // r8
  CMid *v90; // rcx
  struct CClientOxid *v91; // rdi
  struct CClientOxid *v92; // rdi
  bool v93; // zf
  unsigned int v94; // eax
  unsigned int v95; // esi
  unsigned __int8 *v96; // r8
  unsigned int v97; // eax
  unsigned __int8 *v98; // r8
  __int64 v99; // rcx
  unsigned int v100; // eax
  unsigned __int8 *v101; // r8
  CMid *v102; // rcx
  struct CClientOxid *v103; // rdi
  struct CClientOxid *v104; // rdi
  unsigned __int8 *v105; // r8
  struct CClientOxid *v106; // rdi
  bool v107; // zf
  __int64 v108; // r10
  __int64 v109; // rdx
  struct CClientOxid *v110; // rdi
  struct CClientOxid *v111; // rdi
  int v112; // eax
  unsigned __int16 v113; // bx
  struct CClientOxid *v114; // rdi
  struct CClientOxid *v115; // rdi
  unsigned int v116; // eax
  unsigned int v117; // eax
  unsigned int Info; // eax
  void *v119; // r8
  unsigned int *v120; // rbx
  unsigned int v121; // edi
  _QWORD *v122; // r14
  CMid *v123; // rbx
  unsigned __int64 v124; // rax
  unsigned __int8 *v125; // rax
  CProcess *v126; // r12
  unsigned int v127; // eax
  void *v128; // r8
  void *v129; // r8
  struct CClientOxid *v130; // rdi
  struct CClientOxid *v131; // rdi
  unsigned int v132; // eax
  void *v133; // r8
  struct CClientOxid *v134; // rdi
  __int64 v135; // rcx
  __int128 v136; // xmm2
  __int128 v137; // xmm3
  __int128 v138; // xmm4
  __int128 v139; // xmm5
  __int128 v140; // xmm6
  __int128 v141; // xmm7
  __int128 v142; // xmm8
  __int128 v143; // xmm9
  __int64 v144; // xmm10_8
  CMid *v145; // rcx
  int *v146; // rdx
  LPVOID v147; // rax
  void *v148; // r8
  struct CClientOxid *v149; // rdi
  struct CClientOxid *v150; // rdi
  RPC_AUTH_IDENTITY_HANDLE AuthIdentity; // [rsp+20h] [rbp-E0h]
  RPC_AUTH_IDENTITY_HANDLE AuthIdentitya; // [rsp+20h] [rbp-E0h]
  unsigned int AuthIdentityb; // [rsp+20h] [rbp-E0h]
  unsigned int AuthIdentityc; // [rsp+20h] [rbp-E0h]
  RPC_AUTH_IDENTITY_HANDLE AuthIdentityd; // [rsp+20h] [rbp-E0h]
  RPC_AUTH_IDENTITY_HANDLE AuthIdentitye; // [rsp+20h] [rbp-E0h]
  RPC_AUTH_IDENTITY_HANDLE AuthIdentityf; // [rsp+20h] [rbp-E0h]
  unsigned int AuthIdentityg; // [rsp+20h] [rbp-E0h]
  RPC_AUTH_IDENTITY_HANDLE AuthIdentityh; // [rsp+20h] [rbp-E0h]
  struct tagDUALSTRINGARRAY **SecurityQOS; // [rsp+30h] [rbp-D0h]
  unsigned int v161; // [rsp+50h] [rbp-B0h] BYREF
  CMid *v162; // [rsp+58h] [rbp-A8h] BYREF
  bool v163[8]; // [rsp+60h] [rbp-A0h] BYREF
  struct CClientOxid *v164; // [rsp+68h] [rbp-98h] BYREF
  struct CClientOxid *v165; // [rsp+70h] [rbp-90h] BYREF
  struct CProcess *v166; // [rsp+78h] [rbp-88h] BYREF
  RPC_BINDING_HANDLE v167; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v168; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v169; // [rsp+90h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v171; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v172; // [rsp+A8h] [rbp-58h]
  unsigned int v173; // [rsp+ACh] [rbp-54h]
  _QWORD v174[4]; // [rsp+B0h] [rbp-50h] BYREF
  char v175; // [rsp+D0h] [rbp-30h]
  LPVOID lpMem; // [rsp+D8h] [rbp-28h] BYREF
  void **p_lpMem; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int8 *v178; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v179; // [rsp+F0h] [rbp-10h]
  unsigned __int64 *v180; // [rsp+110h] [rbp+10h]
  RTL_SRWLOCK *v181; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 *v182; // [rsp+120h] [rbp+20h] BYREF
  unsigned int *v183; // [rsp+128h] [rbp+28h]
  CProcess *v184; // [rsp+130h] [rbp+30h]
  unsigned __int64 *v185; // [rsp+138h] [rbp+38h]
  unsigned __int16 *v186; // [rsp+140h] [rbp+40h]
  int *v187; // [rsp+148h] [rbp+48h]
  __int64 v188[2]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v189; // [rsp+160h] [rbp+60h] BYREF
  struct _GUID v190; // [rsp+170h] [rbp+70h] BYREF
  __int128 v191; // [rsp+180h] [rbp+80h]
  struct tagDUALSTRINGARRAY *v192[2]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v193; // [rsp+1A0h] [rbp+A0h]
  __int128 v194; // [rsp+1B0h] [rbp+B0h]
  __int128 v195; // [rsp+1C0h] [rbp+C0h]
  struct _GUID v196; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v197; // [rsp+1E0h] [rbp+E0h]
  struct _EXCEPTION_RECORD pExceptionRecord; // [rsp+1F0h] [rbp+F0h] BYREF
  RPC_SECURITY_QOS v199; // [rsp+290h] [rbp+190h] BYREF
  __int128 v200; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v201; // [rsp+2B0h] [rbp+1B0h]
  __int128 v202; // [rsp+2C0h] [rbp+1C0h]
  __int128 v203; // [rsp+2D0h] [rbp+1D0h]
  __int128 v204; // [rsp+2E0h] [rbp+1E0h]
  __int128 v205; // [rsp+2F0h] [rbp+1F0h]
  __int128 v206; // [rsp+300h] [rbp+200h]
  __int128 v207; // [rsp+310h] [rbp+210h]
  __int128 v208; // [rsp+320h] [rbp+220h]
  __int64 v209; // [rsp+330h] [rbp+230h]
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  v20 = a7;
  v21 = a3;
  v22 = a6;
  v23 = a12;
  Binding = a17;
  v162 = 0;
  v164 = 0;
  v165 = 0;
  v166 = 0;
  v174[0] = &v162;
  v174[1] = &v164;
  v187 = a15;
  v174[2] = &v165;
  v184 = a2;
  v183 = a16;
  v174[3] = &v166;
  v180 = a3;
  v182 = a6;
  v181 = (RTL_SRWLOCK *)a7;
  v185 = a8;
  v186 = a18;
  v175 = 1;
  if ( !a7 || !a8 || !a18 )
  {
    v24 = 1050;
    goto LABEL_7;
  }
  if ( a4 && !DsaValid(a4) )
  {
    v24 = 1055;
LABEL_7:
    v25 = wil::details::in1diag3::Log_Win32(
            retaddr,
            (void *)v24,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (const char *)0x57,
            (unsigned int)AuthIdentity);
    v175 = 0;
    v26 = v25;
    lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v174);
    return v26;
  }
  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v28 = &Class;
    if ( v22 )
      v28 = v22;
    LODWORD(AuthIdentity) = 3;
    ComTraceMessage(
      0xFFFFFFFFLL,
      "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      "ResolveClientOXID",
      1058,
      AuthIdentity,
      L"OXID:%I64X Machine:%ws",
      *v21,
      v28);
  }
  AcquireSRWLockExclusive(&gpClientLock);
  v163[0] = 0;
  v29 = CMid::FindOrCreate(a4, &v162, v163);
  v30 = v29;
  if ( v29 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x42A,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)v29,
      (unsigned int)AuthIdentity);
    ReleaseSRWLockExclusive(&gpClientLock);
    v175 = 0;
    lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v174);
    return v30;
  }
  if ( v163[0] )
  {
    v31 = a11;
    *((_WORD *)v162 + 20) = a10;
    v32 = CMid::SetMarshaledTargetInfo(v162, v31, v23);
    v33 = v32;
    if ( v32 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x434,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)v32,
        (unsigned int)AuthIdentity);
      ReleaseSRWLockExclusive(&gpClientLock);
      v175 = 0;
      lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v174);
      return v33;
    }
  }
  v34 = gpClientOxidTable;
  v35 = (unsigned __int8 *)*v21;
  v36 = *((_QWORD *)v162 + 3);
  p_lpMem = &CId2Key::`vftable';
  v178 = v35;
  v179 = v36;
  v37 = *(CClientOxid **)(*((_QWORD *)v34 + 1) + 8LL * (CId2Key::Hash((CId2Key *)&p_lpMem) % *(_DWORD *)v34));
  if ( v37 )
  {
    while ( 1 )
    {
      if ( *((_QWORD *)v37 + 2) == 0xDEADDEADDEADDEADuLL )
      {
        pExceptionRecord.ExceptionFlags = 1;
        pExceptionRecord.ExceptionCode = -2147467261;
        pExceptionRecord.ExceptionRecord = 0;
        memset(&pExceptionRecord.NumberParameters, 0, 128);
        pExceptionRecord.ExceptionAddress = retaddr;
        RaiseFailFastException(&pExceptionRecord, 0, 2u);
      }
      if ( (*(unsigned __int8 (__fastcall **)(CClientOxid *, void ***))(*(_QWORD *)v37 + 40LL))(v37, &p_lpMem) )
        break;
      v37 = (CClientOxid *)*((_QWORD *)v37 + 2);
      if ( !v37 )
        goto LABEL_23;
    }
    if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      HIDWORD(SecurityQOS) = HIDWORD(v35);
      LODWORD(AuthIdentity) = 3;
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx",
        "CClientOxid::FindIfExists",
        115,
        AuthIdentity,
        L"Found ClientOXID OXID:%I64X MID:%I64X");
    }
    CClientOxid::Reference(v37);
    v38 = 0;
  }
  else
  {
LABEL_23:
    v38 = 0;
    v37 = 0;
  }
  v164 = v37;
  ReleaseSRWLockExclusive(&gpClientLock);
  if ( v164 )
    goto LABEL_325;
  *(_OWORD *)v188 = 0;
  v197 = 0;
  v189 = 0;
  v190 = 0;
  v191 = 0;
  *(_OWORD *)v192 = 0;
  v193 = 0;
  v194 = 0;
  v195 = 0;
  v196 = 0;
  if ( *((_BYTE *)v162 + 42) )
  {
    lambda_ed20763ba46da10d6147d4426465f69a_::_lambda_ed20763ba46da10d6147d4426465f69a_(
      (unsigned int)&p_lpMem,
      (_DWORD)v21,
      (unsigned int)&v162,
      (unsigned int)v188,
      (__int64)&a5,
      (__int64)&v182,
      (__int64)&v166);
    if ( a13 )
    {
      v39 = lambda_ed20763ba46da10d6147d4426465f69a_::operator()(&p_lpMem);
    }
    else
    {
      AcquireSRWLockShared(&gpServerLock);
      v39 = lambda_ed20763ba46da10d6147d4426465f69a_::operator()(&p_lpMem);
      ReleaseSRWLockShared(&gpServerLock);
    }
    if ( v39 )
      goto LABEL_323;
    goto LABEL_34;
  }
  v47 = (const struct tagDUALSTRINGARRAY *)*((_QWORD *)v20 + 8);
  if ( v47 )
  {
    if ( DsaValid(v47) )
    {
      if ( !*(_BYTE *)(v108 + 43) || *((_QWORD *)v20 + 16) )
      {
        v112 = CopyOxidInfo(v20, (struct __MIDL_ILocalObjectExporter_0007 *)v188, 0);
        v113 = v112;
        if ( v112 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5F4,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (const char *)(unsigned int)v112,
            (int)AuthIdentity);
          Pointer = v113;
          ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
          AcquireSRWLockExclusive(&gpClientLock);
          if ( v162 )
          {
            CReferencedObject::Release(v162);
            v162 = 0;
          }
          v114 = v164;
          if ( v164 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v164 + 2, 0xFFFFFFFF) == 1 )
            {
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              {
                LODWORD(AuthIdentityf) = 4;
                ComTraceMessage(
                  0xFFFFFFFFLL,
                  "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
                  "CClientOxid::Insert",
                  176,
                  AuthIdentityf,
                  L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
                  v114,
                  *((_QWORD *)v114 + 3));
              }
              CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v114 + 40));
            }
            v164 = 0;
          }
          v115 = v165;
          if ( v165 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) == 1 )
            {
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              {
                LODWORD(AuthIdentityf) = 4;
                ComTraceMessage(
                  0xFFFFFFFFLL,
                  "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
                  "CClientOxid::Insert",
                  176,
                  AuthIdentityf,
                  L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
                  v115,
                  *((_QWORD *)v115 + 3));
              }
              CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v115 + 40));
            }
            v165 = 0;
          }
          goto LABEL_61;
        }
        goto LABEL_34;
      }
      v109 = 1520;
    }
    else
    {
      v109 = 1514;
    }
    Pointer = wil::details::in1diag3::Log_Win32(
                retaddr,
                (void *)v109,
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
                (const char *)0x776,
                (unsigned int)AuthIdentity);
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
    AcquireSRWLockExclusive(&gpClientLock);
    if ( v162 )
    {
      CReferencedObject::Release(v162);
      v162 = 0;
    }
    v110 = v164;
    if ( v164 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v164 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
        {
          LODWORD(AuthIdentitye) = 4;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
            "CClientOxid::Insert",
            176,
            AuthIdentitye,
            L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
            v110,
            *((_QWORD *)v110 + 3));
        }
        CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v110 + 40));
      }
      v164 = 0;
    }
    v111 = v165;
    if ( v165 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
        {
          LODWORD(AuthIdentitye) = 4;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
            "CClientOxid::Insert",
            176,
            AuthIdentitye,
            L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
            v111,
            *((_QWORD *)v111 + 3));
        }
        CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v111 + 40));
      }
      v165 = 0;
    }
    goto LABEL_384;
  }
  v48 = RpcImpersonateClient(BindingHandle);
  v39 = v48;
  if ( v48 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x487,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)v48,
      (unsigned int)AuthIdentity);
LABEL_323:
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
    v175 = 0;
    lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v174);
    return v39;
  }
  if ( *((_BYTE *)v162 + 43) )
  {
    v50 = (volatile signed __int32 *)*((_QWORD *)v162 + 9);
    if ( v50 )
      _InterlockedIncrement(v50 + 2);
    v51 = CrossContainerClientSet::CallCrossContainerResolveOxid(
            (CrossContainerClientSet *)v50,
            *v21,
            v192,
            (struct _GUID *)v190.Data4,
            (unsigned __int64 *)&v196.Data1,
            (struct _GUID *)v196.Data4,
            (struct CONTAINERVERSION *)&v189);
    if ( v50 )
      ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CrossContainerClientSet,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CrossContainerClientSet,ObjectLibrary::Details::Allocation_StandardDeleteSelfLayer<CrossContainerClientSet,ObjectLibrary::Details::MixinBase<CrossContainerClientSet,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(v50);
    if ( v51 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x498,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)v51,
        (unsigned int)AuthIdentity);
      RpcRevertToSelfEx(BindingHandle);
      ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
      v175 = 0;
      lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v174);
      return v51;
    }
    if ( !DsaValid(v192[0]) )
    {
      v52 = 1183;
LABEL_77:
      v39 = wil::details::in1diag3::Log_Win32(
              retaddr,
              (void *)v52,
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
              (const char *)0x776,
              (unsigned int)AuthIdentity);
      RpcRevertToSelfEx(BindingHandle);
      goto LABEL_323;
    }
    if ( !*(_QWORD *)&v196.Data1 )
    {
      v52 = 1189;
      goto LABEL_77;
    }
    v53 = (unsigned __int16 *)*((_QWORD *)v162 + 4);
    a5 = *v53;
    if ( a5 != *((_WORD *)v192[0] + 2) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v53);
    v54 = ValidateNegotiatedContainerVersion((const struct CONTAINERVERSION *)&v189);
    LOWORD(v39) = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4AC,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)(unsigned int)v54,
        (int)AuthIdentity);
      v39 = (unsigned __int16)v39;
      RpcRevertToSelfEx(BindingHandle);
      goto LABEL_323;
    }
    HIDWORD(v188[1]) = DcomProtocolVersion_Current;
    RpcRevertToSelfEx(BindingHandle);
LABEL_34:
    if ( !DsaValid(v192[0]) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v40);
    AcquireSRWLockExclusive(&gpClientLock);
    if ( !*((_WORD *)v162 + 20) || a9 )
    {
      if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        CMid::PrintableName(v162);
        LODWORD(AuthIdentity) = 3;
        ComTraceMessage(
          0xFFFFFFFFLL,
          "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          "ResolveClientOXID",
          1538,
          AuthIdentity,
          L"Machine %ws, unsecure retry ok, assuming no sec");
      }
      *((_BYTE *)v162 + 44) = 0;
    }
    if ( *(_QWORD *)&v196.Data1 && *(_QWORD *)&v196.Data1 != *v21 )
    {
      memset(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      PrimaryOxidInfoFromOxidInfo = MakePrimaryOxidInfoFromOxidInfo(
                                      (const struct __MIDL_ILocalObjectExporter_0007 *)v188,
                                      *((_BYTE *)v162 + 42),
                                      (struct __MIDL_ILocalObjectExporter_0007 *)&pExceptionRecord,
                                      v41);
      v43 = PrimaryOxidInfoFromOxidInfo;
      if ( PrimaryOxidInfoFromOxidInfo < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x611,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (const char *)(unsigned int)PrimaryOxidInfoFromOxidInfo,
          (int)AuthIdentity);
        Pointer = v43;
        ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&pExceptionRecord);
        ReleaseSRWLockExclusive(&gpClientLock);
        ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
        AcquireSRWLockExclusive(&gpClientLock);
        if ( v162 )
        {
          CReferencedObject::Release(v162);
          v162 = 0;
        }
        v45 = v164;
        if ( v164 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v164 + 2, 0xFFFFFFFF) == 1 )
          {
            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
            {
              LODWORD(AuthIdentitya) = 4;
              ComTraceMessage(
                0xFFFFFFFFLL,
                "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
                "CClientOxid::Insert",
                176,
                AuthIdentitya,
                L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
                v45,
                *((_QWORD *)v45 + 3));
            }
            CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v45 + 40));
          }
          v164 = 0;
        }
        v46 = v165;
        if ( v165 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) == 1 )
          {
            if ( gfEnableTracing )
            {
              if ( (unsigned __int8)IsWppLevelEnabled(4) )
              {
                LODWORD(AuthIdentitya) = 4;
                ComTraceMessage(
                  0xFFFFFFFFLL,
                  "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
                  "CClientOxid::Insert",
                  176,
                  AuthIdentitya,
                  L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
                  v46,
                  *((_QWORD *)v46 + 3));
              }
            }
            CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v46 + 40));
          }
          v165 = 0;
        }
LABEL_61:
        ReleaseSRWLockExclusive(&gpClientLock);
        if ( !v166 )
          return Pointer;
        (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v166 + 16LL))(v166);
        return Pointer;
      }
      v116 = CClientOxid::FindOrCreate(
               *(unsigned __int64 *)&v196.Data1,
               v162,
               v166,
               (__int64)&pExceptionRecord,
               (__int64)&v165);
      Pointer = v116;
      if ( v116 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x61F,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (const char *)v116,
          AuthIdentityg);
        ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&pExceptionRecord);
        ReleaseSRWLockExclusive(&gpClientLock);
        ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
LABEL_266:
        AcquireSRWLockExclusive(&gpClientLock);
        if ( v162 )
        {
          CReferencedObject::Release(v162);
          v162 = 0;
        }
        v106 = v164;
        if ( v164 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v164 + 2, 0xFFFFFFFF) == 1 )
          {
            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
            {
              LODWORD(AuthIdentity) = 4;
              ComTraceMessage(
                0xFFFFFFFFLL,
                "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
                "CClientOxid::Insert",
                176,
                AuthIdentity,
                L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
                v106,
                *((_QWORD *)v106 + 3));
            }
            CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v106 + 40));
          }
          v164 = 0;
        }
        v92 = v165;
        if ( !v165 )
          goto LABEL_384;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) != 1 )
          goto LABEL_383;
        v107 = gfEnableTracing == 0;
        goto LABEL_378;
      }
      ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&pExceptionRecord);
    }
    v117 = CClientOxid::FindOrCreate(*v21, v162, v166, (__int64)v188, (__int64)&v164);
    v39 = v117;
    if ( v117 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x62F,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)v117,
        (unsigned int)AuthIdentity);
      ReleaseSRWLockExclusive(&gpClientLock);
      goto LABEL_323;
    }
    ReleaseSRWLockExclusive(&gpClientLock);
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
LABEL_325:
    v171 = 0;
    v200 = 0;
    v209 = 0;
    v201 = 0;
    v202 = 0;
    v203 = 0;
    v204 = 0;
    v205 = 0;
    v206 = 0;
    v207 = 0;
    v208 = 0;
    AcquireSRWLockExclusive(&gpClientLock);
    v181 = &gpClientLock;
    Info = CClientOxid::GetInfo(v164, (struct __MIDL_ILocalObjectExporter_0007 *)&v200);
    Pointer = Info;
    if ( Info )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x640,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)Info,
        (unsigned int)AuthIdentity);
      ReleaseSRWLockExclusive(&gpClientLock);
      v119 = v171;
      v171 = 0;
      if ( v119 )
        HeapFree(g_hHeap, 0, v119);
      ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&v200);
      goto LABEL_266;
    }
    v120 = v183;
    v121 = 0;
    v122 = Binding;
    if ( v183 && Binding )
    {
      v123 = v162;
      p_lpMem = &v171;
      LOBYTE(v179) = 1;
      v121 = 0;
      v178 = 0;
      v124 = *((unsigned int *)v162 + 14);
      if ( (_DWORD)v124 )
      {
        if ( v124 >= v124 + 7
          || (v125 = (unsigned __int8 *)HeapAlloc(g_hHeap, 0, (v124 + 7) & 0xFFFFFFFFFFFFFFF8uLL), (v178 = v125) == 0) )
        {
          wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>(&p_lpMem);
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x648,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (const char *)8,
            (unsigned int)AuthIdentity);
          ReleaseSRWLockExclusive(&gpClientLock);
          v129 = v171;
          v171 = 0;
          if ( v129 )
            HeapFree(g_hHeap, 0, v129);
          ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&v200);
          AcquireSRWLockExclusive(&gpClientLock);
          if ( v162 )
          {
            CReferencedObject::Release(v162);
            v162 = 0;
          }
          v130 = v164;
          if ( v164 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v164 + 2, 0xFFFFFFFF) == 1 )
            {
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              {
                LODWORD(AuthIdentityh) = 4;
                ComTraceMessage(
                  0xFFFFFFFFLL,
                  "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
                  "CClientOxid::Insert",
                  176,
                  AuthIdentityh,
                  L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
                  v130,
                  *((_QWORD *)v130 + 3));
              }
              CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v130 + 40));
            }
            v164 = 0;
          }
          v131 = v165;
          if ( v165 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) == 1 )
            {
              if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
              {
                LODWORD(AuthIdentityh) = 4;
                ComTraceMessage(
                  0xFFFFFFFFLL,
                  "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
                  "CClientOxid::Insert",
                  176,
                  AuthIdentityh,
                  L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
                  v131,
                  *((_QWORD *)v131 + 3));
              }
              CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v131 + 40));
            }
            v165 = 0;
          }
          ReleaseSRWLockExclusive(&gpClientLock);
          if ( v166 )
            (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v166 + 16LL))(v166);
          return 8;
        }
        memcpy_0(v125, *((const void **)v123 + 8), *((unsigned int *)v123 + 14));
        v121 = *((_DWORD *)v123 + 14);
      }
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>(&p_lpMem);
      v120 = v183;
    }
    if ( !*((_BYTE *)v162 + 42) )
    {
      v126 = v184;
      v127 = CProcess::ReferenceRemoteClientOxid(v184, v164);
      Pointer = v127;
      if ( v127 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x658,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (const char *)v127,
          (unsigned int)AuthIdentity);
        ReleaseSRWLockExclusive(&gpClientLock);
        v128 = v171;
        v171 = 0;
        if ( v128 )
          HeapFree(g_hHeap, 0, v128);
LABEL_366:
        ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&v200);
        AcquireSRWLockExclusive(&gpClientLock);
        if ( v162 )
        {
          CReferencedObject::Release(v162);
          v162 = 0;
        }
        v134 = v164;
        if ( v164 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v164 + 2, 0xFFFFFFFF) == 1 )
          {
            if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
            {
              LODWORD(AuthIdentity) = 4;
              ComTraceMessage(
                0xFFFFFFFFLL,
                "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
                "CClientOxid::Insert",
                176,
                AuthIdentity,
                L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
                v134,
                *((_QWORD *)v134 + 3));
            }
            CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v134 + 40));
          }
          v164 = 0;
        }
        v92 = v165;
        if ( !v165 )
          goto LABEL_384;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) != 1 )
          goto LABEL_383;
        v107 = gfEnableTracing == 0;
LABEL_378:
        if ( !v107 )
        {
          v93 = (unsigned __int8)IsWppLevelEnabled(4) == 0;
LABEL_380:
          if ( !v93 )
          {
            LODWORD(AuthIdentity) = 4;
            ComTraceMessage(
              0xFFFFFFFFLL,
              "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
              "CClientOxid::Insert",
              176,
              AuthIdentity,
              L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
              v92,
              *((_QWORD *)v92 + 3));
          }
        }
        goto LABEL_382;
      }
      if ( v165 )
      {
        v132 = CProcess::ReferenceRemoteClientOxid(v126, v165);
        Pointer = v132;
        if ( v132 )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x660,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (const char *)v132,
            (unsigned int)AuthIdentity);
          CProcess::ReleaseRemoteClientOxid(v126, v164);
          Microsoft::WRL::Wrappers::Details::SyncLockExclusive::~SyncLockExclusive((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v181);
          v133 = v171;
          v171 = 0;
          if ( v133 )
            HeapFree(g_hHeap, 0, v133);
          goto LABEL_366;
        }
      }
    }
    ReleaseSRWLockExclusive(&gpClientLock);
    if ( a14 && a11 )
    {
      if ( !*((_WORD *)v164 + 116) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v135);
      *v21 = 0;
    }
    ClearOxidInfo(v20);
    if ( *v21 )
    {
      v136 = v201;
      v137 = v202;
      v138 = v203;
      v139 = v204;
      v140 = v205;
      *(_OWORD *)v20 = v200;
      v141 = v206;
      *((_OWORD *)v20 + 1) = v136;
      v142 = v207;
      *((_OWORD *)v20 + 2) = v137;
      v143 = v208;
      *((_OWORD *)v20 + 3) = v138;
      v144 = v209;
      *((_OWORD *)v20 + 4) = v139;
      v209 = 0;
      *((_OWORD *)v20 + 5) = v140;
      *((_OWORD *)v20 + 6) = v141;
      *((_OWORD *)v20 + 7) = v142;
      *((_OWORD *)v20 + 8) = v143;
      *((_QWORD *)v20 + 18) = v144;
      v200 = 0;
      v201 = 0;
      v202 = 0;
      v203 = 0;
      v204 = 0;
      v205 = 0;
      v206 = 0;
      v207 = 0;
      v208 = 0;
    }
    v145 = v162;
    *v185 = *((_QWORD *)v162 + 3);
    v146 = v187;
    *v186 = *((_WORD *)v145 + 20);
    if ( v146 )
      *v146 = *((_WORD *)v164 + 116) == 0;
    if ( v120 && v122 )
    {
      v147 = v171;
      v148 = 0;
      *v120 = v121;
      *v122 = v147;
    }
    else
    {
      v148 = v171;
    }
    v171 = 0;
    if ( v148 )
      HeapFree(g_hHeap, 0, v148);
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&v200);
    AcquireSRWLockExclusive(&gpClientLock);
    if ( v162 )
    {
      CReferencedObject::Release(v162);
      v162 = 0;
    }
    v149 = v164;
    if ( v164 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v164 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
        {
          LODWORD(AuthIdentity) = 4;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
            "CClientOxid::Insert",
            176,
            AuthIdentity,
            L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
            v149,
            *((_QWORD *)v149 + 3));
        }
        CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v149 + 40));
      }
      v164 = 0;
    }
    v150 = v165;
    if ( v165 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
        {
          LODWORD(AuthIdentity) = 4;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
            "CClientOxid::Insert",
            176,
            AuthIdentity,
            L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
            v150,
            *((_QWORD *)v150 + 3));
        }
        CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v150 + 40));
      }
      v165 = 0;
    }
    ReleaseSRWLockExclusive(&gpClientLock);
    if ( v166 )
      (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v166 + 16LL))(v166);
    return 0;
  }
  v167 = 0;
  v55 = CMid::GetBinding(v162, &v167, v49);
  v39 = v55;
  if ( v55 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x4B8,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)v55,
      (unsigned int)AuthIdentity);
    if ( v167 )
    {
      Binding = v167;
      RpcBindingFree(&Binding);
    }
    RpcRevertToSelfEx(BindingHandle);
    goto LABEL_323;
  }
  v56 = v162;
  v57 = s_dwDCOMSCMRemoteCallFlags & 4;
  v58 = s_dwDCOMSCMRemoteCallFlags & 8;
  v172 = v57;
  v173 = v58;
  if ( (s_dwDCOMSCMRemoteCallFlags & 4) == 0 || *((_BYTE *)v162 + 44) )
  {
    v59 = (s_dwDCOMSCMRemoteCallFlags & 4) == 0;
    MachineName = ExtractMachineName(*((unsigned __int16 **)v162 + 4));
    if ( MachineName )
    {
      v61 = -1;
      do
        v93 = MachineName[++v61] == 0;
      while ( !v93 );
      v62 = v61 + 8;
      v64 = v61 + 8;
      v63 = 2 * (v61 + 8);
      if ( !is_mul_ok(v64, 2u) )
        v63 = -1;
      v65 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v63);
      v66 = v65;
      if ( v65 )
      {
        if ( v62 )
        {
          if ( v62 <= 0x7FFFFFFF )
          {
            v67 = 2147483646;
            v68 = L"RPCSS/";
            v69 = v62;
            do
            {
              if ( !v67 )
                break;
              if ( !*v68 )
                break;
              *v65++ = *v68++;
              --v67;
              --v69;
            }
            while ( v69 );
            v70 = v65 - 1;
            if ( v69 )
              v70 = v65;
            *v70 = 0;
          }
          else
          {
            *v65 = 0;
          }
        }
        StringCchCatW(v66, v62, MachineName);
      }
      HeapFree(g_hHeap, 0, MachineName);
      v56 = v162;
      v57 = v172;
      v58 = v173;
      goto LABEL_110;
    }
    v56 = v162;
    v57 = v172;
    v58 = v173;
  }
  else
  {
    v59 = s_cRpcssSvc + 1;
  }
  v66 = 0;
LABEL_110:
  v71 = *((_WORD *)v56 + 20);
  *(_WORD *)v163 = v71;
  if ( v59 >= s_cRpcssSvc + 2 )
  {
LABEL_261:
    Pointer = wil::details::in1diag3::Log_Win32(
                retaddr,
                (void *)0x5E0,
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
                (const char *)5,
                (unsigned int)AuthIdentity);
    if ( v66 )
      HeapFree(g_hHeap, 0, v66);
    if ( v167 )
    {
      Binding = v167;
      RpcBindingFree(&Binding);
    }
    RpcRevertToSelfEx(BindingHandle);
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
    goto LABEL_266;
  }
  v72 = L"Using authn service:%x SPN:%ws";
  v73 = (CRpcSecurityCallbackManager *)L"Using unsecure binding";
  while ( 1 )
  {
    v168 = 0;
    v74 = 0;
    if ( v59 < s_cRpcssSvc + 1 )
    {
      if ( v59 )
      {
        v73 = (CRpcSecurityCallbackManager *)(2LL * (v59 - 1));
        v75 = *((_WORD *)s_aRpcssSvc + 8 * v59 - 4);
        if ( !v57 )
        {
          if ( v75 != 9 )
            goto LABEL_147;
          v199.ImpersonationType = 3;
          v199.Version = 1;
          v199.Capabilities = 1;
          v199.IdentityTracking = 1;
LABEL_122:
          v76 = CRpcSecurityCallbackManager::RegisterForRpcAuthSvcCallBack(v73, v167);
          v72 = L"Using authn service:%x SPN:%ws";
          if ( v76 )
            v38 = 1;
LABEL_124:
          if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            LODWORD(SecurityQOS) = v75;
            LODWORD(AuthIdentity) = 3;
            ComTraceMessage(
              0xFFFFFFFFLL,
              "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
              "ResolveClientOXID",
              1313,
              AuthIdentity,
              v72,
              SecurityQOS,
              v66);
          }
          v77 = v75;
          if ( v75 == 0xFFFF )
            v77 = -1;
          v78 = 5;
          if ( !dword_1801578BC )
            v78 = 2;
          v79 = RpcBindingSetAuthInfoExW(v167, v66, v78, v77, 0, 0, &v199);
          if ( !v79 )
            goto LABEL_151;
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x52A,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (const char *)v79,
            AuthIdentityb);
          if ( !v38 )
            goto LABEL_146;
          p_lpMem = &lpMem;
          LOBYTE(v179) = 1;
          v38 = 0;
          lpMem = 0;
          v178 = 0;
          CRpcSecurityCallbackManager::GetSecurityContextDetailsAndTurnOffCallback(v80, v167, 0, &v161, &v178);
          if ( (_BYTE)v179 )
          {
            v81 = *p_lpMem;
            *p_lpMem = v178;
            if ( v81 )
              HeapFree(g_hHeap, 0, v81);
          }
          v82 = lpMem;
          lpMem = 0;
LABEL_137:
          if ( v82 )
            HeapFree(g_hHeap, 0, v82);
          v71 = *(_WORD *)v163;
          v72 = L"Using authn service:%x SPN:%ws";
          goto LABEL_148;
        }
        if ( v75 == v71 )
          goto LABEL_147;
      }
      else
      {
        v75 = v71;
      }
      if ( v57 && !(unsigned int)ValidAuthnSvc((CMid *)((char *)v162 + 80), v75) )
      {
        v71 = *(_WORD *)v163;
        goto LABEL_147;
      }
      v199.ImpersonationType = 3;
      v199.Version = 1;
      v199.Capabilities = 1;
      v199.IdentityTracking = 1;
      if ( v75 != 9 )
        goto LABEL_124;
      goto LABEL_122;
    }
    if ( !v58 )
      break;
    v38 = 0;
LABEL_149:
    if ( ++v59 >= s_cRpcssSvc + 2 )
      goto LABEL_261;
    v57 = v172;
    v58 = v173;
  }
  v75 = 0;
  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    LODWORD(AuthIdentity) = 3;
    ComTraceMessage(
      0xFFFFFFFFLL,
      "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      "ResolveClientOXID",
      1346,
      AuthIdentity,
      L"Using unsecure binding");
  }
  v83 = RpcBindingSetAuthInfoW(v167, 0, 1u, 0, 0, 0);
  if ( v83 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x549,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)v83,
      AuthIdentityc);
LABEL_146:
    v71 = *(_WORD *)v163;
    v72 = L"Using authn service:%x SPN:%ws";
LABEL_147:
    v38 = 0;
LABEL_148:
    v73 = (CRpcSecurityCallbackManager *)L"Using unsecure binding";
    goto LABEL_149;
  }
LABEL_151:
  Pointer = ResolveOxid2(
              (_DWORD)v167,
              (_DWORD)v180,
              (unsigned __int16)cMyNetworkProtseqs,
              (_DWORD)aMyNetworkProtseqs,
              (__int64)v192,
              (__int64)v190.Data4,
              (__int64)&v188[1],
              (__int64)&v188[1] + 4);
  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    LODWORD(AuthIdentity) = 3;
    ComTraceMessage(
      Pointer,
      "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      "ResolveClientOXID",
      1374,
      AuthIdentity,
      L"ResolveOxid2 returned %!WINERROR!");
  }
  if ( Pointer == 1745 )
  {
    HIDWORD(v188[1]) = DcomProtocolVersion_NoResolveOxid2;
    DWORD2(v191) = 0;
    SecurityQOS = v192;
    LODWORD(AuthIdentity) = (unsigned __int16)cMyNetworkProtseqs;
    Pointer = (unsigned int)NdrClientCall2(&stru_180117DC0, &byte_180124AC2, v167, v180).Pointer;
    if ( gfEnableTracing )
    {
      v84 = (CRpcSecurityCallbackManager *)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        LODWORD(AuthIdentity) = 3;
        ComTraceMessage(
          Pointer,
          "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          "ResolveClientOXID",
          1395,
          AuthIdentity,
          L"ResolveOxid returned %!WINERROR!");
      }
    }
  }
  v161 = 0;
  v169 = 0;
  if ( v38 )
  {
    if ( Pointer )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x57E,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)Pointer,
        (unsigned int)AuthIdentity);
      p_lpMem = (void **)&v169;
      LOBYTE(v179) = 1;
      v38 = 0;
      v178 = 0;
      CRpcSecurityCallbackManager::GetSecurityContextDetailsAndTurnOffCallback(v85, v167, 0, &v161, &v178);
      if ( (_BYTE)v179 )
      {
        v86 = *p_lpMem;
        *p_lpMem = v178;
        if ( v86 )
          HeapFree(g_hHeap, 0, v86);
      }
      goto LABEL_165;
    }
    p_lpMem = (void **)&v169;
    LOBYTE(v179) = 1;
    v178 = 0;
    SecurityContextDetailsAndTurnOffCallback = CRpcSecurityCallbackManager::GetSecurityContextDetailsAndTurnOffCallback(
                                                 v84,
                                                 v167,
                                                 &v168,
                                                 &v161,
                                                 &v178);
    if ( (_BYTE)v179 )
    {
      v88 = *p_lpMem;
      *p_lpMem = v178;
      if ( v88 )
        HeapFree(g_hHeap, 0, v88);
    }
    v74 = v168;
    if ( !SecurityContextDetailsAndTurnOffCallback )
      v38 = 0;
LABEL_202:
    v94 = NegotiateDCOMVersion_Client((struct tagCOMVERSION *)((char *)&v188[1] + 4));
    v95 = v94;
    if ( v94 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x5AA,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)v94,
        (unsigned int)AuthIdentity);
      v96 = v169;
      v169 = 0;
      if ( v96 )
        HeapFree(g_hHeap, 0, v96);
      if ( v66 )
        HeapFree(g_hHeap, 0, v66);
      if ( v167 )
      {
        Binding = v167;
        RpcBindingFree(&Binding);
      }
      RpcRevertToSelfEx(BindingHandle);
      ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
      v175 = 0;
      lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v174);
      return v95;
    }
    if ( v38 )
    {
      if ( v74 == 16 )
        *((_WORD *)v162 + 20) = 9;
      else
        *((_WORD *)v162 + 20) = v74;
      AcquireSRWLockExclusive(&gpClientLock);
      v97 = CMid::SetMarshaledTargetInfo(v162, v161, v169);
      Pointer = v97;
      if ( v97 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x5C6,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (const char *)v97,
          (unsigned int)AuthIdentity);
        ReleaseSRWLockExclusive(&gpClientLock);
        v98 = v169;
        v169 = 0;
        if ( v98 )
          HeapFree(g_hHeap, 0, v98);
        if ( v66 )
          HeapFree(g_hHeap, 0, v66);
        if ( v167 )
        {
          Binding = v167;
          RpcBindingFree(&Binding);
        }
        goto LABEL_235;
      }
      ReleaseSRWLockExclusive(&gpClientLock);
    }
    else
    {
      *((_WORD *)v162 + 20) = v75;
    }
    if ( DsaValid(v192[0]) )
    {
      v105 = v169;
      a5 = *(_WORD *)(v99 + 4);
      v169 = 0;
      if ( v105 )
        HeapFree(g_hHeap, 0, v105);
      if ( v66 )
        HeapFree(g_hHeap, 0, v66);
      if ( v167 )
      {
        lpMem = v167;
        RpcBindingFree(&lpMem);
      }
      v20 = (struct __MIDL_ILocalObjectExporter_0007 *)v181;
      v21 = v180;
      RpcRevertToSelfEx(BindingHandle);
      goto LABEL_34;
    }
    if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      CMid::PrintableName(v162);
      LODWORD(AuthIdentity) = 0;
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        "ResolveClientOXID",
        1492,
        AuthIdentity,
        L"Remote machine %ws returned bad bindings");
    }
    v100 = wil::details::in1diag3::Log_Win32(
             retaddr,
             (void *)0x5D5,
             (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
             (const char *)0x776,
             (unsigned int)AuthIdentity);
    v101 = v169;
    Pointer = v100;
    v169 = 0;
    if ( v101 )
      HeapFree(g_hHeap, 0, v101);
    if ( v66 )
      HeapFree(g_hHeap, 0, v66);
    if ( v167 )
    {
      Binding = v167;
      RpcBindingFree(&Binding);
    }
LABEL_235:
    RpcRevertToSelfEx(BindingHandle);
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
    AcquireSRWLockExclusive(&gpClientLock);
    v102 = v162;
    if ( v162 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v162 + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(CMid *, __int64))v102)(v102, 1);
      v162 = 0;
    }
    v103 = v164;
    if ( v164 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v164 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          LODWORD(AuthIdentityd) = 4;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
            "CClientOxid::Insert",
            176,
            AuthIdentityd,
            L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
            v103,
            *((_QWORD *)v103 + 3));
        }
        CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v103 + 40));
      }
      v164 = 0;
    }
    v104 = v165;
    if ( v165 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          LODWORD(AuthIdentityd) = 4;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
            "CClientOxid::Insert",
            176,
            AuthIdentityd,
            L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
            v104,
            *((_QWORD *)v104 + 3));
        }
        CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v104 + 40));
      }
      v165 = 0;
    }
    goto LABEL_384;
  }
  if ( !Pointer )
    goto LABEL_202;
  v38 = 0;
LABEL_165:
  wil::details::in1diag3::_Log_Win32(
    retaddr,
    (void *)0x598,
    (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
    (const char *)Pointer,
    (unsigned int)AuthIdentity);
  if ( Pointer == 5 || Pointer == 1747 || Pointer == 1750 || Pointer == 1825 )
  {
    v82 = v169;
    v169 = 0;
    goto LABEL_137;
  }
  if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LODWORD(SecurityQOS) = Pointer;
    LODWORD(AuthIdentity) = 0;
    ComTraceMessage(
      Pointer,
      "onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      "ResolveClientOXID",
      1444,
      AuthIdentity,
      L"Remote ResolveOXID failed:%!WINERROR!",
      SecurityQOS);
  }
  v89 = v169;
  v169 = 0;
  if ( v89 )
    HeapFree(g_hHeap, 0, v89);
  if ( v66 )
    HeapFree(g_hHeap, 0, v66);
  if ( v167 )
  {
    Binding = v167;
    RpcBindingFree(&Binding);
  }
  RpcRevertToSelfEx(BindingHandle);
  ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v188);
  AcquireSRWLockExclusive(&gpClientLock);
  v90 = v162;
  if ( v162 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v162 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(CMid *, __int64))v90)(v90, 1);
    v162 = 0;
  }
  v91 = v164;
  if ( v164 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v164 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        LODWORD(AuthIdentity) = 4;
        ComTraceMessage(
          0xFFFFFFFFLL,
          "onecore\\com\\combase\\rpcss\\objex\\coxid.hxx",
          "CClientOxid::Insert",
          176,
          AuthIdentity,
          L"this:%p client OXID:%I64x inserting in gpClientOxidPList",
          v91,
          *((_QWORD *)v91 + 3));
      }
      CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v91 + 40));
    }
    v164 = 0;
  }
  v92 = v165;
  if ( !v165 )
    goto LABEL_384;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v165 + 2, 0xFFFFFFFF) != 1 )
    goto LABEL_383;
  if ( gfEnableTracing )
  {
    v93 = (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0;
    goto LABEL_380;
  }
LABEL_382:
  CPList::Insert(gpClientOxidPList, (struct CClientOxid *)((char *)v92 + 40));
LABEL_383:
  v165 = 0;
LABEL_384:
  ReleaseSRWLockExclusive(&gpClientLock);
  if ( v166 )
    (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v166 + 16LL))(v166);
  return Pointer;
}

```

## disassembly

```asm
0x180031be0  push    rbp
0x180031be2  push    rbx
0x180031be3  push    rdi
0x180031be4  push    r12
0x180031be6  push    r13
0x180031be8  push    r15
0x180031bea  lea     rbp, [rsp-2B8h]
0x180031bf2  sub     rsp, 3B8h
0x180031bf9  mov     rax, cs:__security_cookie
0x180031c00  xor     rax, rsp
0x180031c03  mov     [rbp+2E0h+var_A0], rax
0x180031c0a  mov     rax, [rbp+2E0h+arg_70]
0x180031c11  mov     r12, rcx
0x180031c14  mov     rcx, [rbp+2E0h+arg_80]
0x180031c1b  mov     rbx, r9
0x180031c1e  mov     r13, [rbp+2E0h+arg_30]
0x180031c25  mov     r15, r8
0x180031c28  mov     r10, [rbp+2E0h+arg_28]
0x180031c2f  mov     rdi, [rbp+2E0h+arg_58]
0x180031c36  mov     [rbp+2E0h+Binding], rcx
0x180031c3a  xor     ecx, ecx
0x180031c3c  mov     [rsp+3E0h+var_388], rcx
0x180031c41  mov     [rsp+3E0h+var_378], rcx
0x180031c46  mov     [rsp+3E0h+var_370], rcx
0x180031c4b  mov     [rsp+3E0h+var_368], rcx
0x180031c50  lea     rcx, [rsp+3E0h+var_388]
0x180031c55  mov     [rbp+2E0h+var_330], rcx
0x180031c59  lea     rcx, [rsp+3E0h+var_378]
0x180031c5e  mov     [rbp+2E0h+var_328], rcx
0x180031c62  lea     rcx, [rsp+3E0h+var_370]
0x180031c67  mov     [rbp+2E0h+var_298], rax
0x180031c6b  mov     rax, [rbp+2E0h+arg_78]
0x180031c72  mov     [rbp+2E0h+var_320], rcx
0x180031c76  lea     rcx, [rsp+3E0h+var_368]
0x180031c7b  mov     [rbp+2E0h+var_2B0], rdx
0x180031c7f  mov     rdx, [rbp+2E0h+arg_38]
0x180031c86  mov     [rbp+2E0h+var_2B8], rax
0x180031c8a  mov     rax, [rbp+2E0h+arg_88]
0x180031c91  mov     [rbp+2E0h+var_318], rcx
0x180031c95  mov     [rbp+2E0h+var_2D0], r8
0x180031c99  mov     [rbp+2E0h+var_2C0], r10
0x180031c9d  mov     [rbp+2E0h+var_2C8], r13
0x180031ca1  mov     [rbp+2E0h+var_2A8], rdx
0x180031ca5  mov     [rbp+2E0h+var_2A0], rax
0x180031ca9  mov     [rbp+2E0h+var_310], 1
0x180031cad  test    r13, r13
0x180031cb0  jz      loc_1800341E0
0x180031cb6  test    rdx, rdx
0x180031cb9  jz      loc_1800341E0
0x180031cbf  test    rax, rax
0x180031cc2  jz      loc_1800341E0
0x180031cc8  test    rbx, rbx
0x180031ccb  jz      short loc_180031D0D
0x180031ccd  mov     rcx, rbx; struct tagDUALSTRINGARRAY *
0x180031cd0  call    ?DsaValid@@YA_NPEBUtagDUALSTRINGARRAY@@@Z; DsaValid(tagDUALSTRINGARRAY const *)
0x180031cd5  test    al, al
0x180031cd7  jnz     short loc_180031D0D
0x180031cd9  mov     edx, 41Fh; void *
0x180031cde  mov     rcx, [rbp+2E8h]; this
0x180031ce5  lea     r8, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x180031cec  mov     r9d, 57h ; 'W'; char *
0x180031cf2  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180031cf7  lea     rcx, [rbp+2E0h+var_330]
0x180031cfb  mov     [rbp+2E0h+var_310], 0
0x180031cff  mov     ebx, eax
0x180031d01  call    _lambda_505646f3df15c8bd29ef639cc06ee5bf___operator__
0x180031d06  mov     eax, ebx
0x180031d08  jmp     loc_1800324A7
0x180031d0d  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180031d14  mov     [rsp+3E0h+var_30], rsi
0x180031d1c  jz      short loc_180031D78
0x180031d1e  mov     rax, cs:WPP_GLOBAL_Control
0x180031d25  test    byte ptr [rax+1Ch], 8
0x180031d29  jz      short loc_180031D78
0x180031d2b  test    r10, r10
0x180031d2e  lea     rax, Class
0x180031d35  mov     r9d, 422h
0x180031d3b  lea     r8, aResolvecliento; "ResolveClientOXID"
0x180031d42  cmovnz  rax, r10
0x180031d46  lea     rdx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x180031d4d  mov     [rsp+3E0h+var_3A8], rax
0x180031d52  mov     ecx, 0FFFFFFFFh
0x180031d57  mov     rax, [r15]
0x180031d5a  mov     [rsp+3E0h+SecurityQOS], rax
0x180031d5f  lea     rax, aOxidI64xMachin; "OXID:%I64X Machine:%ws"
0x180031d66  mov     qword ptr [rsp+3E0h+AuthzSvc], rax
0x180031d6b  mov     dword ptr [rsp+3E0h+AuthIdentity], 3; unsigned int
0x180031d73  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180031d78  lea     rsi, ?gpClientLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpClientLock
0x180031d7f  mov     rcx, rsi; SRWLock
0x180031d82  call    cs:__imp_AcquireSRWLockExclusive
0x180031d89  nop     dword ptr [rax+rax+00h]
0x180031d8e  lea     r8, [rsp+3E0h+var_380]; bool *
0x180031d93  mov     [rsp+3E0h+var_380], 0
0x180031d98  lea     rdx, [rsp+3E0h+var_388]; struct CMid **
0x180031d9d  mov     rcx, rbx; struct tagDUALSTRINGARRAY *
0x180031da0  call    ?FindOrCreate@CMid@@SAJPEBUtagDUALSTRINGARRAY@@PEAPEAV1@PEA_N@Z; CMid::FindOrCreate(tagDUALSTRINGARRAY const *,CMid * *,bool *)
0x180031da5  mov     ebx, eax
0x180031da7  test    eax, eax
0x180031da9  jz      short loc_180031DE9
0x180031dab  mov     rcx, [rbp+2E8h]; this
0x180031db2  lea     r8, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x180031db9  mov     r9d, eax; char *
0x180031dbc  mov     edx, 42Ah; void *
0x180031dc1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180031dc6  mov     rcx, rsi; SRWLock
0x180031dc9  call    cs:__imp_ReleaseSRWLockExclusive
0x180031dd0  nop     dword ptr [rax+rax+00h]
0x180031dd5  lea     rcx, [rbp+2E0h+var_330]
0x180031dd9  mov     [rbp+2E0h+var_310], 0
0x180031ddd  call    _lambda_505646f3df15c8bd29ef639cc06ee5bf___operator__
0x180031de2  mov     eax, ebx
0x180031de4  jmp     loc_18003249F
0x180031de9  cmp     [rsp+3E0h+var_380], 0
0x180031dee  jz      short loc_180031E57
0x180031df0  mov     rcx, [rsp+3E0h+var_388]
0x180031df5  mov     r8, rdi; unsigned __int8 *
0x180031df8  movzx   eax, [rbp+2E0h+arg_48]
0x180031dff  mov     edx, [rbp+2E0h+arg_50]; unsigned int
0x180031e05  xchg    ax, [rcx+28h]
0x180031e09  mov     rcx, [rsp+3E0h+var_388]; this
0x180031e0e  call    ?SetMarshaledTargetInfo@CMid@@QEAAJKPEAE@Z; CMid::SetMarshaledTargetInfo(ulong,uchar *)
0x180031e13  mov     ebx, eax
0x180031e15  test    eax, eax
0x180031e17  jz      short loc_180031E57
0x180031e19  mov     rcx, [rbp+2E8h]; this
0x180031e20  lea     r8, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x180031e27  mov     r9d, eax; char *
0x180031e2a  mov     edx, 434h; void *
0x180031e2f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180031e34  mov     rcx, rsi; SRWLock
0x180031e37  call    cs:__imp_ReleaseSRWLockExclusive
0x180031e3e  nop     dword ptr [rax+rax+00h]
0x180031e43  lea     rcx, [rbp+2E0h+var_330]
0x180031e47  mov     [rbp+2E0h+var_310], 0
0x180031e4b  call    _lambda_505646f3df15c8bd29ef639cc06ee5bf___operator__
0x180031e50  mov     eax, ebx
0x180031e52  jmp     loc_18003249F
0x180031e57  mov     rax, [rsp+3E0h+var_388]
0x180031e5c  lea     rcx, [rbp+2E0h+var_300]; this
0x180031e60  mov     rbx, cs:?gpClientOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpClientOxidTable
0x180031e67  mov     [rsp+3E0h+var_38], r14
0x180031e6f  mov     r14, [r15]
0x180031e72  mov     rsi, [rax+18h]
0x180031e76  lea     rax, ??_7CId2Key@@6B@; const CId2Key::`vftable'
0x180031e7d  mov     [rbp+2E0h+var_300], rax
0x180031e81  mov     [rbp+2E0h+var_2F8], r14
0x180031e85  mov     [rbp+2E0h+var_2F0], rsi
0x180031e89  call    ?Hash@CId2Key@@UEBAKXZ; CId2Key::Hash(void)
0x180031e8e  xor     edx, edx
0x180031e90  mov     ecx, 1
0x180031e95  div     dword ptr [rbx]
0x180031e97  mov     rax, [rbx+8]
0x180031e9b  mov     rbx, [rax+rdx*8]
0x180031e9f  mov     edx, 2
0x180031ea4  test    rbx, rbx
0x180031ea7  jz      loc_180031F86
0x180031ead  mov     rax, 0DEADDEADDEADDEADh
0x180031eb7  nop     word ptr [rax+rax+00000000h]
0x180031ec0  cmp     [rbx+10h], rax
0x180031ec4  jnz     loc_180031F4A
0x180031eca  mov     rax, [rbp+2E8h]
0x180031ed1  xorps   xmm0, xmm0
0x180031ed4  mov     [rbp+2E0h+pExceptionRecord.ExceptionFlags], ecx
0x180031eda  mov     r8d, edx; dwFlags
0x180031edd  xor     ecx, ecx
0x180031edf  mov     [rbp+2E0h+pExceptionRecord.ExceptionCode], 80004003h
0x180031ee9  mov     [rbp+2E0h+pExceptionRecord.ExceptionRecord], rcx
0x180031ef0  xor     edx, edx; pContextRecord
0x180031ef2  mov     [rbp+2E0h+pExceptionRecord.NumberParameters], ecx
0x180031ef8  lea     rcx, [rbp+2E0h+pExceptionRecord]; pExceptionRecord
0x180031eff  movups  xmmword ptr [rbp+2E0h+pExceptionRecord.ExceptionInformation+5Ch], xmm0
0x180031f06  mov     [rbp+2E0h+pExceptionRecord.ExceptionAddress], rax
0x180031f0d  movups  xmmword ptr [rbp+2E0h+pExceptionRecord+1Ch], xmm0
0x180031f14  movups  xmmword ptr [rbp+2E0h+pExceptionRecord.ExceptionInformation+0Ch], xmm0
0x180031f1b  movups  xmmword ptr [rbp+2E0h+pExceptionRecord.ExceptionInformation+1Ch], xmm0
0x180031f22  movups  xmmword ptr [rbp+2E0h+pExceptionRecord.ExceptionInformation+2Ch], xmm0
0x180031f29  movups  xmmword ptr [rbp+2E0h+pExceptionRecord.ExceptionInformation+3Ch], xmm0
0x180031f30  movups  xmmword ptr [rbp+2E0h+pExceptionRecord.ExceptionInformation+4Ch], xmm0
0x180031f37  movups  xmmword ptr [rbp+2E0h+pExceptionRecord.ExceptionInformation+68h], xmm0
0x180031f3e  call    cs:__imp_RaiseFailFastException
0x180031f45  nop     dword ptr [rax+rax+00h]
0x180031f4a  mov     rax, [rbx]
0x180031f4d  lea     rdx, [rbp+2E0h+var_300]
0x180031f51  mov     rcx, rbx
0x180031f54  mov     rax, [rax+28h]
0x180031f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f5d  test    al, al
0x180031f5f  jnz     loc_180032051
0x180031f65  mov     rbx, [rbx+10h]
0x180031f69  mov     rax, 0DEADDEADDEADDEADh
0x180031f73  mov     ecx, 1
0x180031f78  mov     edx, 2
0x180031f7d  test    rbx, rbx
0x180031f80  jnz     loc_180031EC0
0x180031f86  xor     r14d, r14d
0x180031f89  mov     ebx, r14d
0x180031f8c  lea     rdi, ?gpClientLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpClientLock
0x180031f93  mov     [rsp+3E0h+var_378], rbx
0x180031f98  mov     rcx, rdi; SRWLock
0x180031f9b  call    cs:__imp_ReleaseSRWLockExclusive
0x180031fa2  nop     dword ptr [rax+rax+00h]
0x180031fa7  cmp     [rsp+3E0h+var_378], 0
0x180031fad  jnz     loc_18003390F
0x180031fb3  mov     r10, [rsp+3E0h+var_388]
0x180031fb8  xorps   xmm0, xmm0
0x180031fbb  xor     eax, eax
0x180031fbd  movups  xmmword ptr [rbp+2E0h+var_290], xmm0
0x180031fc1  mov     [rbp+2E0h+var_200], rax
0x180031fc8  movups  [rbp+2E0h+var_280], xmm0
0x180031fcc  movups  xmmword ptr [rbp+2E0h+var_270.Data1], xmm0
0x180031fd0  movups  [rbp+2E0h+var_260], xmm0
0x180031fd7  movups  xmmword ptr [rbp+2E0h+var_250], xmm0
0x180031fde  movups  [rbp+2E0h+var_240], xmm0
0x180031fe5  movups  [rbp+2E0h+var_230], xmm0
0x180031fec  movups  [rbp+2E0h+var_220], xmm0
0x180031ff3  movups  xmmword ptr [rbp+2E0h+var_210.Data1], xmm0
0x180031ffa  cmp     [r10+2Ah], al
0x180031ffe  jz      loc_1800323AD
0x180032004  lea     rax, [rsp+3E0h+var_368]
0x180032009  mov     rdx, r15
0x18003200c  mov     [rsp+3E0h+SecurityQOS], rax
0x180032011  lea     r9, [rbp+2E0h+var_290]
0x180032015  lea     rax, [rbp+2E0h+var_2C0]
0x180032019  mov     qword ptr [rsp+3E0h+AuthzSvc], rax
0x18003201e  lea     r8, [rsp+3E0h+var_388]
0x180032023  lea     rax, [rbp+2E0h+arg_20]
0x18003202a  lea     rcx, [rbp+2E0h+var_300]
0x18003202e  mov     [rsp+3E0h+AuthIdentity], rax
0x180032033  call    _lambda_ed20763ba46da10d6147d4426465f69a____lambda_ed20763ba46da10d6147d4426465f69a_
0x180032038  cmp     [rbp+2E0h+arg_60], 0
0x18003203f  jz      short loc_1800320B3
0x180032041  lea     rcx, [rbp+2E0h+var_300]
0x180032045  call    _lambda_ed20763ba46da10d6147d4426465f69a___operator__
0x18003204a  mov     ebx, eax
0x18003204c  jmp     loc_1800320E4
0x180032051  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180032058  jz      short loc_1800320A3
0x18003205a  mov     rax, cs:WPP_GLOBAL_Control
0x180032061  test    byte ptr [rax+1Ch], 8
0x180032065  jz      short loc_1800320A3
0x180032067  mov     [rsp+3E0h+var_3A8], rsi
0x18003206c  lea     rax, aFoundClientoxi_0; "Found ClientOXID OXID:%I64X MID:%I64X"
0x180032073  mov     [rsp+3E0h+SecurityQOS], r14
0x180032078  lea     r8, aCclientoxidFin; "CClientOxid::FindIfExists"
0x18003207f  mov     qword ptr [rsp+3E0h+AuthzSvc], rax
0x180032084  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x18003208b  mov     r9d, 73h ; 's'
0x180032091  mov     dword ptr [rsp+3E0h+AuthIdentity], 3
0x180032099  mov     ecx, 0FFFFFFFFh
0x18003209e  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800320a3  mov     rcx, rbx; this
0x1800320a6  call    ?Reference@CClientOxid@@UEAAXXZ; CClientOxid::Reference(void)
0x1800320ab  xor     r14d, r14d
0x1800320ae  jmp     loc_180031F8C
0x1800320b3  lea     rcx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800320ba  call    cs:__imp_AcquireSRWLockShared
0x1800320c1  nop     dword ptr [rax+rax+00h]
0x1800320c6  lea     rcx, [rbp+2E0h+var_300]
0x1800320ca  call    _lambda_ed20763ba46da10d6147d4426465f69a___operator__
0x1800320cf  lea     rcx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800320d6  mov     ebx, eax
0x1800320d8  call    cs:__imp_ReleaseSRWLockShared
0x1800320df  nop     dword ptr [rax+rax+00h]
0x1800320e4  test    ebx, ebx
0x1800320e6  jnz     loc_1800338D8
0x1800320ec  mov     rcx, [rbp+2E0h+var_250]; struct tagDUALSTRINGARRAY *
0x1800320f3  call    ?DsaValid@@YA_NPEBUtagDUALSTRINGARRAY@@@Z; DsaValid(tagDUALSTRINGARRAY const *)
0x1800320f8  test    al, al
0x1800320fa  jnz     short loc_180032101
0x1800320fc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180032101  lea     r12, ?gpClientLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpClientLock
0x180032108  mov     rcx, r12; SRWLock
0x18003210b  call    cs:__imp_AcquireSRWLockExclusive
0x180032112  nop     dword ptr [rax+rax+00h]
0x180032117  mov     rax, [rsp+3E0h+var_388]
0x18003211c  movzx   ecx, word ptr [rax+28h]
0x180032120  nop
0x180032121  test    cx, cx
0x180032124  jz      short loc_18003212F
0x180032126  cmp     [rbp+2E0h+arg_40], 0
0x18003212d  jz      short loc_18003218F
0x18003212f  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180032136  jz      short loc_180032186
0x180032138  mov     rax, cs:WPP_GLOBAL_Control
0x18003213f  test    byte ptr [rax+1Ch], 8
0x180032143  jz      short loc_180032186
0x180032145  mov     rcx, [rsp+3E0h+var_388]; this
0x18003214a  call    ?PrintableName@CMid@@QEAAPEAGXZ; CMid::PrintableName(void)
0x18003214f  mov     [rsp+3E0h+SecurityQOS], rax
0x180032154  lea     r8, aResolvecliento; "ResolveClientOXID"
0x18003215b  lea     rax, aMachineWsUnsec; "Machine %ws, unsecure retry ok, assumin"...
0x180032162  mov     r9d, 602h
0x180032168  mov     qword ptr [rsp+3E0h+AuthzSvc], rax
0x18003216d  lea     rdx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x180032174  mov     ecx, 0FFFFFFFFh
0x180032179  mov     dword ptr [rsp+3E0h+AuthIdentity], 3; int
0x180032181  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180032186  mov     rax, [rsp+3E0h+var_388]
0x18003218b  mov     byte ptr [rax+2Ch], 0
  ... truncated ...
```
