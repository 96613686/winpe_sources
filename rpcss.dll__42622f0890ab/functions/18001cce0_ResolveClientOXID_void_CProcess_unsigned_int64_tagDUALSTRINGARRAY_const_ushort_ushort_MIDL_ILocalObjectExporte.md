# ResolveClientOXID(void *,CProcess *,unsigned __int64 &,tagDUALSTRINGARRAY const *,ushort,ushort *,__MIDL_ILocalObjectExporter_0007 *,unsigned __int64 *,int,ushort,ulong,uchar *,bool,bool,int *,ulong *,uchar * *,ushort *)

- ea: `0x18001cce0`
- end: `0x18001e8e1`
- name: `?ResolveClientOXID@@YAKPEAXPEAVCProcess@@AEA_KPEBUtagDUALSTRINGARRAY@@GPEAGPEAU__MIDL_ILocalObjectExporter_0007@@PEA_KHGKPEAE_N8PEAHPEAKPEAPEAE4@Z`
- size: `7169`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, struct CProcess *, unsigned __int8 **, const struct tagDUALSTRINGARRAY *, unsigned __int16, unsigned __int16 *, struct __MIDL_ILocalObjectExporter_0007 *, unsigned __int64 *, int, unsigned __int16, unsigned int, unsigned __int8 *, bool, bool, int *, unsigned int *, unsigned __int8 **, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `38`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001c4f0`
- `0x180034b60`
- `0x180064460`

## callees

- `0x180016530`
- `0x180016550`
- `0x180018344`
- `0x180018380`
- `0x180019040`
- `0x18001cce0`
- `0x180027558`
- `0x1800277a0`
- `0x180027d80`
- `0x18002834c`
- `0x180028498`
- `0x18002ba28`
- `0x1800418c0`
- `0x180042640`
- `0x1800450dc`
- `0x18005642c`
- `0x180063cac`
- `0x1800851cc`
- `0x18008e98c`
- `0x180098884`
- `0x1800989b0`
- `0x180098b54`
- `0x18009bde0`
- `0x18009dad0`
- `0x18009eb90`
- `0x18009f60c`
- `0x18009ff38`
- `0x1800a1080`
- `0x1800a11ec`
- `0x1800a1e14`
- `0x1800a242c`
- `0x1800a2524`
- `0x1800b27e0`
- `0x1800c147c`
- `0x1800c1668`
- `0x1800c542c`
- `0x18010a084`
- `0x18010b010`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18001d3b1`
- `RPCRT4!RpcBindingFree` at `0x18001db5c`
- `RPCRT4!RpcBindingFree` at `0x18001dbe6`
- `RPCRT4!RpcBindingFree` at `0x18001dd54`
- `RPCRT4!RpcBindingFree` at `0x18001de23`
- `RPCRT4!RpcBindingFree` at `0x18001de8f`
- `RPCRT4!RpcBindingFree` at `0x18001d3b1`
- `RPCRT4!RpcBindingFree` at `0x18001db5c`
- `RPCRT4!RpcBindingFree` at `0x18001dbe6`
- `RPCRT4!RpcBindingFree` at `0x18001dd54`
- `RPCRT4!RpcBindingFree` at `0x18001de23`
- `RPCRT4!RpcBindingFree` at `0x18001de8f`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001d68d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001d68d`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18001d7a6`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18001d7a6`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d25d`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d2ef`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d350`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d367`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d3ba`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001db66`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001dbf0`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001dd5e`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001de38`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001de98`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d25d`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d2ef`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d350`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d367`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001d3ba`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001db66`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001dbf0`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001dd5e`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001de38`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001de98`
- `RPCRT4!RpcImpersonateClient` at `0x18001d1a6`
- `RPCRT4!RpcImpersonateClient` at `0x18001d1a6`
- `RPCRT4!NdrClientCall2` at `0x18001d85c`
- `RPCRT4!NdrClientCall2` at `0x18001d91a`
- `RPCRT4!NdrClientCall2` at `0x18001d85c`
- `RPCRT4!NdrClientCall2` at `0x18001d91a`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18001cffa`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18001cffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d4cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d711`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d72d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d9ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001daad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001db2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001db45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dd26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dd3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ddf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001de0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001de78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e4ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e5f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e852`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d4cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d711`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d72d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d9ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001daad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001db2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001db45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dd26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dd3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ddf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001de0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001de78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e4ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e5f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e852`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d448`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e440`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d448`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e440`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001d16b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001d16b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001d183`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001d183`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ce87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dc23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dd74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001df6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e0d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e31a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e392`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e518`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e60d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e86b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ce87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dc23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dd74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001df6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e0d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e31a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e392`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e518`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e60d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e86b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cf03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d04e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dc63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dc75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e0bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e12d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e20c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e285`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e2af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e35d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e4e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e561`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e5d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e656`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e680`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e8b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cf03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d04e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dc63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dc75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e0bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e12d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e20c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e285`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e2af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e35d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e4e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e561`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e5d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e656`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e680`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e8b4`

## string_xrefs

- `0x18001d138`: `onecore\com\combase\rpcss\objex\orclnt.cxx`
- `0x18001e077`: `onecore\com\combase\callheaders\oxidinfo.cpp`
- `0x18001cde9`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001ce51`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001ceed`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d1b9`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d246`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d2d8`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d336`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d38c`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d61b`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d6a2`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d782`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d7b7`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d8a0`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d95f`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d989`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001da06`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001db0a`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001db8e`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001dc48`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001dcdd`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001dcf7`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001de4e`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001deb7`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001def1`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001df2f`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001dfc7`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001e092`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001e1e5`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001e26a`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001e342`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001e49c`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001e4c5`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001e5ae`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x18001d50c`: `Using authn service:%x SPN:%ws`
- `0x18001d5e6`: `Using authn service:%x SPN:%ws`
- `0x18001d739`: `Using authn service:%x SPN:%ws`
- `0x18001d7d1`: `Using authn service:%x SPN:%ws`

## pseudocode

```c
__int64 __fastcall ResolveClientOXID(
        RPC_BINDING_HANDLE BindingHandle,
        struct CProcess *a2,
        unsigned __int8 **a3,
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
  RPC_BINDING_HANDLE v18; // r12
  struct __MIDL_ILocalObjectExporter_0007 *v19; // r13
  unsigned __int8 *v22; // rdi
  __int64 v23; // rdx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  unsigned int v27; // ebx
  __int64 v28; // rdx
  unsigned int v29; // edx
  unsigned __int8 *v30; // r15
  ObjexHashTable::CHashTable *v31; // rbx
  __int64 v32; // r14
  CClientOxid *v33; // rbx
  int v34; // r15d
  unsigned __int64 *v35; // r14
  unsigned int v36; // ebx
  const struct tagDUALSTRINGARRAY *v37; // rcx
  unsigned int v38; // eax
  bool v39; // r8
  volatile signed __int32 *v40; // rbx
  unsigned int v41; // edi
  __int64 v42; // rdx
  unsigned __int16 *v43; // rcx
  int v44; // eax
  unsigned int v45; // eax
  CMid *v46; // rcx
  unsigned int v47; // edx
  unsigned int v48; // r9d
  unsigned int v49; // r13d
  unsigned __int16 *MachineName; // rbx
  __int64 v51; // rax
  unsigned __int64 v53; // r14
  SIZE_T v54; // rax
  unsigned __int64 v55; // kr00_8
  unsigned __int16 *v56; // rax
  unsigned __int16 *v57; // rdi
  __int64 v58; // rcx
  const unsigned __int16 *v59; // r9
  unsigned __int64 v60; // r8
  unsigned __int16 *v61; // rcx
  unsigned __int16 v62; // r8
  CRpcSecurityCallbackManager *v63; // rcx
  unsigned __int16 v64; // r12
  unsigned __int16 v65; // r14
  unsigned int v66; // r9d
  unsigned int v67; // r8d
  unsigned int v68; // eax
  CRpcSecurityCallbackManager *v69; // rcx
  void *v70; // r8
  void *v71; // r8
  unsigned int v72; // eax
  CLIENT_CALL_RETURN v73; // rcx
  unsigned int Pointer; // ebx
  unsigned int v75; // eax
  CRpcSecurityCallbackManager *v76; // rcx
  void *v77; // r8
  int SecurityContextDetailsAndTurnOffCallback; // ebx
  void *v79; // r8
  unsigned __int8 *v80; // r8
  __int64 *v81; // rcx
  unsigned int v82; // eax
  unsigned __int8 *v83; // r8
  unsigned int v84; // eax
  __int64 v85; // rcx
  unsigned __int8 *v86; // r8
  CMid *v87; // rcx
  CClientOxid *v88; // rcx
  unsigned __int8 *v89; // r8
  __int64 v90; // r10
  int v91; // eax
  __int64 v92; // rcx
  char v93; // di
  int v94; // eax
  CMid *v95; // rcx
  unsigned int v96; // ecx
  unsigned int v97; // eax
  unsigned int v98; // eax
  unsigned int Info; // eax
  void *v100; // r8
  CMid *v101; // rcx
  unsigned int *v102; // rsi
  unsigned int v103; // edi
  _QWORD *v104; // r15
  CMid *v105; // rbx
  unsigned __int64 v106; // rax
  unsigned __int8 *v107; // rax
  CProcess *v108; // r12
  unsigned int v109; // eax
  void *v110; // r8
  unsigned int v111; // eax
  void *v112; // r8
  __int64 v113; // rcx
  __int128 v114; // xmm2
  __int128 v115; // xmm3
  __int128 v116; // xmm4
  __int128 v117; // xmm5
  __int128 v118; // xmm6
  __int128 v119; // xmm7
  __int128 v120; // xmm8
  __int128 v121; // xmm9
  __int64 v122; // xmm10_8
  CMid *v123; // rcx
  int *v124; // rdx
  LPVOID v125; // rax
  void *v126; // r8
  unsigned int AuthIdentity; // [rsp+20h] [rbp-E0h]
  RPC_AUTH_IDENTITY_HANDLE AuthIdentitya; // [rsp+20h] [rbp-E0h]
  int AuthIdentityc; // [rsp+20h] [rbp-E0h]
  unsigned int AuthIdentityb; // [rsp+20h] [rbp-E0h]
  CMid *v131; // [rsp+50h] [rbp-B0h] BYREF
  bool v132[8]; // [rsp+58h] [rbp-A8h] BYREF
  CClientOxid *v133; // [rsp+60h] [rbp-A0h] BYREF
  CClientOxid *v134; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v135; // [rsp+70h] [rbp-90h] BYREF
  struct CProcess *v136; // [rsp+78h] [rbp-88h] BYREF
  RPC_BINDING_HANDLE v137; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v138; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v139; // [rsp+90h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v141; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 *v142; // [rsp+A8h] [rbp-58h]
  unsigned int v143; // [rsp+B0h] [rbp-50h]
  unsigned int v144; // [rsp+B4h] [rbp-4Ch]
  RPC_BINDING_HANDLE BindingHandlea; // [rsp+B8h] [rbp-48h]
  _QWORD v146[4]; // [rsp+C0h] [rbp-40h] BYREF
  char v147; // [rsp+E0h] [rbp-20h]
  LPVOID lpMem; // [rsp+E8h] [rbp-18h] BYREF
  void **p_lpMem; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int8 *v150; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v151; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v152; // [rsp+120h] [rbp+20h] BYREF
  struct __MIDL_ILocalObjectExporter_0007 *v153; // [rsp+128h] [rbp+28h]
  unsigned int *v154; // [rsp+130h] [rbp+30h]
  CProcess *v155; // [rsp+138h] [rbp+38h]
  unsigned __int64 *v156; // [rsp+140h] [rbp+40h]
  unsigned __int16 *v157; // [rsp+148h] [rbp+48h]
  int *v158; // [rsp+150h] [rbp+50h]
  __int64 v159[2]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v160; // [rsp+170h] [rbp+70h] BYREF
  struct _GUID v161; // [rsp+180h] [rbp+80h] BYREF
  __int128 v162; // [rsp+190h] [rbp+90h]
  struct tagDUALSTRINGARRAY *v163[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v164; // [rsp+1B0h] [rbp+B0h]
  __int128 v165; // [rsp+1C0h] [rbp+C0h]
  __int128 v166; // [rsp+1D0h] [rbp+D0h]
  struct _GUID v167; // [rsp+1E0h] [rbp+E0h] BYREF
  ULONG_PTR v168; // [rsp+1F0h] [rbp+F0h]
  struct _EXCEPTION_RECORD pExceptionRecord; // [rsp+200h] [rbp+100h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v171; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v172; // [rsp+2C0h] [rbp+1C0h]
  __int128 v173; // [rsp+2D0h] [rbp+1D0h]
  __int128 v174; // [rsp+2E0h] [rbp+1E0h]
  __int128 v175; // [rsp+2F0h] [rbp+1F0h]
  __int128 v176; // [rsp+300h] [rbp+200h]
  __int128 v177; // [rsp+310h] [rbp+210h]
  __int128 v178; // [rsp+320h] [rbp+220h]
  __int128 v179; // [rsp+330h] [rbp+230h]
  __int64 v180; // [rsp+340h] [rbp+240h]
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  v18 = BindingHandle;
  v19 = a7;
  v22 = a12;
  BindingHandlea = BindingHandle;
  Binding = a17;
  v131 = 0;
  v133 = 0;
  v134 = 0;
  v136 = 0;
  v146[0] = &v131;
  v146[1] = &v133;
  v158 = a15;
  v146[2] = &v134;
  v155 = a2;
  v154 = a16;
  v146[3] = &v136;
  v142 = (unsigned __int64 *)a3;
  v152 = a6;
  v153 = a7;
  v156 = a8;
  v157 = a18;
  v147 = 1;
  if ( !a7 || !a8 || !a18 )
  {
    v23 = 1050;
    goto LABEL_7;
  }
  if ( a4 && !DsaValid(a4) )
  {
    v23 = 1055;
LABEL_7:
    v24 = wil::details::in1diag3::Log_Win32(
            retaddr,
            (void *)v23,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (const char *)0x57,
            AuthIdentity);
    v147 = 0;
    v25 = v24;
    lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v146);
    return v25;
  }
  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    AuthIdentity = 3;
    ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ResolveClientOXID", 1058);
  }
  AcquireSRWLockExclusive(&gpClientLock);
  v132[0] = 0;
  v27 = CMid::FindOrCreate(a4, &v131, v132);
  if ( v27 )
  {
    v28 = 1066;
LABEL_16:
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)v27,
      AuthIdentity);
    ReleaseSRWLockExclusive(&gpClientLock);
    v147 = 0;
    lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v146);
    return v27;
  }
  if ( v132[0] )
  {
    v29 = a11;
    *((_WORD *)v131 + 20) = a10;
    v27 = CMid::SetMarshaledTargetInfo(v131, v29, v22);
    if ( v27 )
    {
      v28 = 1076;
      goto LABEL_16;
    }
  }
  v30 = *a3;
  v31 = gpClientOxidTable;
  v32 = *((_QWORD *)v131 + 3);
  p_lpMem = &CId2Key::`vftable';
  v150 = v30;
  v151 = v32;
  v33 = *(CClientOxid **)(*((_QWORD *)v31 + 1) + 8LL * (CId2Key::Hash((CId2Key *)&p_lpMem) % *(_DWORD *)v31));
  if ( v33 )
  {
    while ( 1 )
    {
      if ( *((_QWORD *)v33 + 2) == 0xDEADDEADDEADDEADuLL )
      {
        pExceptionRecord.ExceptionFlags = 1;
        pExceptionRecord.ExceptionCode = -2147467261;
        pExceptionRecord.ExceptionRecord = 0;
        memset(&pExceptionRecord.NumberParameters, 0, 128);
        pExceptionRecord.ExceptionAddress = retaddr;
        RaiseFailFastException(&pExceptionRecord, 0, 2u);
      }
      if ( (*(unsigned __int8 (__fastcall **)(CClientOxid *, void ***))(*(_QWORD *)v33 + 40LL))(v33, &p_lpMem) )
        break;
      v33 = (CClientOxid *)*((_QWORD *)v33 + 2);
      if ( !v33 )
        goto LABEL_22;
    }
    if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      AuthIdentity = 3;
      ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\orclnt.cxx", "CClientOxid::FindIfExists", 115);
    }
    CClientOxid::Reference(v33);
    v34 = 0;
  }
  else
  {
LABEL_22:
    v34 = 0;
    v33 = 0;
  }
  v133 = v33;
  ReleaseSRWLockExclusive(&gpClientLock);
  if ( v133 )
  {
    v35 = v142;
    goto LABEL_248;
  }
  *(_OWORD *)v159 = 0;
  v168 = 0;
  v160 = 0;
  v161 = 0;
  v162 = 0;
  *(_OWORD *)v163 = 0;
  v164 = 0;
  v165 = 0;
  v166 = 0;
  v167 = 0;
  if ( *((_BYTE *)v131 + 42) )
  {
    v35 = v142;
    lambda_ed20763ba46da10d6147d4426465f69a_::_lambda_ed20763ba46da10d6147d4426465f69a_(
      (unsigned int)&p_lpMem,
      (_DWORD)v142,
      (unsigned int)&v131,
      (unsigned int)v159,
      (__int64)&a5,
      (__int64)&v152,
      (__int64)&v136);
    if ( a13 )
    {
      v36 = lambda_ed20763ba46da10d6147d4426465f69a_::operator()(&p_lpMem);
    }
    else
    {
      AcquireSRWLockShared(&gpServerLock);
      v36 = lambda_ed20763ba46da10d6147d4426465f69a_::operator()(&p_lpMem);
      ReleaseSRWLockShared(&gpServerLock);
    }
    if ( v36 )
      goto LABEL_245;
    goto LABEL_216;
  }
  v37 = (const struct tagDUALSTRINGARRAY *)*((_QWORD *)v19 + 8);
  if ( v37 )
  {
    if ( !DsaValid(v37) )
    {
      Pointer = wil::details::in1diag3::Log_Win32(
                  retaddr,
                  (void *)0x5EA,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
                  (const char *)0x776,
                  AuthIdentity);
      v81 = v159;
      goto LABEL_252;
    }
    if ( *(_BYTE *)(v90 + 43) && !*((_QWORD *)v19 + 16) )
    {
      Pointer = wil::details::in1diag3::Log_Win32(
                  retaddr,
                  (void *)0x5F0,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
                  (const char *)0x776,
                  AuthIdentity);
      v81 = v159;
      goto LABEL_252;
    }
    v91 = CopyOxidInfo(v19, (struct __MIDL_ILocalObjectExporter_0007 *)v159, 0);
    LOWORD(Pointer) = v91;
    if ( v91 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5F4,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)(unsigned int)v91,
        AuthIdentity);
      Pointer = (unsigned __int16)Pointer;
      goto LABEL_228;
    }
    v35 = v142;
    goto LABEL_216;
  }
  v38 = RpcImpersonateClient(v18);
  v36 = v38;
  if ( v38 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x487,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)v38,
      AuthIdentity);
    goto LABEL_245;
  }
  if ( *((_BYTE *)v131 + 43) )
  {
    v40 = (volatile signed __int32 *)*((_QWORD *)v131 + 9);
    if ( v40 )
      _InterlockedIncrement(v40 + 2);
    v35 = v142;
    v41 = CrossContainerClientSet::CallCrossContainerResolveOxid(
            (CrossContainerClientSet *)v40,
            *v142,
            v163,
            (struct _GUID *)v161.Data4,
            (unsigned __int64 *)&v167.Data1,
            (struct _GUID *)v167.Data4,
            (struct CONTAINERVERSION *)&v160);
    if ( v40 )
      ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CrossContainerClientSet,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CrossContainerClientSet,ObjectLibrary::Details::Allocation_StandardDeleteSelfLayer<CrossContainerClientSet,ObjectLibrary::Details::MixinBase<CrossContainerClientSet,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(v40);
    if ( v41 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x498,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)v41,
        AuthIdentity);
      RpcRevertToSelfEx(v18);
      ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v159);
      v147 = 0;
      lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v146);
      return v41;
    }
    if ( !DsaValid(v163[0]) )
    {
      v42 = 1183;
LABEL_48:
      v36 = wil::details::in1diag3::Log_Win32(
              retaddr,
              (void *)v42,
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
              (const char *)0x776,
              AuthIdentity);
      RpcRevertToSelfEx(v18);
      goto LABEL_245;
    }
    if ( !*(_QWORD *)&v167.Data1 )
    {
      v42 = 1189;
      goto LABEL_48;
    }
    v43 = (unsigned __int16 *)*((_QWORD *)v131 + 4);
    a5 = *v43;
    if ( a5 != *((_WORD *)v163[0] + 2) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v43);
    v44 = ValidateNegotiatedContainerVersion((const struct CONTAINERVERSION *)&v160);
    LOWORD(v36) = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4AC,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)(unsigned int)v44,
        AuthIdentity);
      v36 = (unsigned __int16)v36;
      RpcRevertToSelfEx(v18);
      goto LABEL_245;
    }
    HIDWORD(v159[1]) = DcomProtocolVersion_Current;
    RpcRevertToSelfEx(v18);
LABEL_216:
    if ( !DsaValid(v163[0]) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v92);
    AcquireSRWLockExclusive(&gpClientLock);
    if ( !*((_WORD *)v131 + 20) || a9 )
    {
      if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        CMid::PrintableName(v131);
        AuthIdentity = 3;
        ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ResolveClientOXID", 1538);
      }
      *((_BYTE *)v131 + 44) = 0;
    }
    if ( *(_QWORD *)&v167.Data1 && *(_QWORD *)&v167.Data1 != *v35 )
    {
      memset(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      v93 = *((_BYTE *)v131 + 42);
      v94 = CopyOxidInfo(
              (const struct __MIDL_ILocalObjectExporter_0007 *)v159,
              (struct __MIDL_ILocalObjectExporter_0007 *)&pExceptionRecord,
              0);
      Pointer = v94;
      if ( v94 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6D,
          (unsigned int)"onecore\\com\\combase\\callheaders\\oxidinfo.cpp",
          (const char *)(unsigned int)v94,
          AuthIdentity);
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x611,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (const char *)Pointer,
          AuthIdentityc);
        Pointer = (unsigned __int16)Pointer;
        ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&pExceptionRecord);
        ReleaseSRWLockExclusive(&gpClientLock);
LABEL_228:
        ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v159);
        AcquireSRWLockExclusive(&gpClientLock);
        v95 = v131;
        if ( v131 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v131 + 2, 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(CMid *, __int64))v95)(v95, 1);
          v131 = 0;
        }
        if ( v133 )
        {
          CClientOxid::Release(v133);
          v133 = 0;
        }
        if ( v134 )
        {
          CClientOxid::Release(v134);
          v134 = 0;
        }
        ReleaseSRWLockExclusive(&gpClientLock);
        if ( v136 )
        {
          (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v136 + 16LL))(v136);
          return Pointer;
        }
        return Pointer;
      }
      v96 = pExceptionRecord.ExceptionInformation[3] & 0xE0100000;
      pExceptionRecord.ExceptionInformation[1] = *(_QWORD *)v167.Data4;
      pExceptionRecord.ExceptionInformation[2] = v168;
      LODWORD(pExceptionRecord.ExceptionInformation[3]) &= 0xE0100000;
      if ( v93 )
      {
        pExceptionRecord.ExceptionCode = -1;
        LODWORD(pExceptionRecord.ExceptionInformation[3]) = v96 | 0x2000000;
      }
      v97 = CClientOxid::FindOrCreate(
              *(unsigned __int64 *)&v167.Data1,
              v131,
              v136,
              (__int64)&pExceptionRecord,
              (__int64)&v134);
      Pointer = v97;
      if ( v97 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x61F,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (const char *)v97,
          AuthIdentityb);
        ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&pExceptionRecord);
        ReleaseSRWLockExclusive(&gpClientLock);
        v81 = v159;
        goto LABEL_252;
      }
      ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&pExceptionRecord);
    }
    v98 = CClientOxid::FindOrCreate(*v35, v131, v136, (__int64)v159, (__int64)&v133);
    v36 = v98;
    if ( v98 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x62F,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)v98,
        AuthIdentity);
      ReleaseSRWLockExclusive(&gpClientLock);
      goto LABEL_245;
    }
    ReleaseSRWLockExclusive(&gpClientLock);
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v159);
LABEL_248:
    v141 = 0;
    v171 = 0;
    v180 = 0;
    v172 = 0;
    v173 = 0;
    v174 = 0;
    v175 = 0;
    v176 = 0;
    v177 = 0;
    v178 = 0;
    v179 = 0;
    AcquireSRWLockExclusive(&gpClientLock);
    Info = CClientOxid::GetInfo(v133, (struct __MIDL_ILocalObjectExporter_0007 *)&v171);
    Pointer = Info;
    if ( Info )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x640,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
        (const char *)Info,
        AuthIdentity);
      ReleaseSRWLockExclusive(&gpClientLock);
      v100 = v141;
      v141 = 0;
      if ( v100 )
        HeapFree(g_hHeap, 0, v100);
      v81 = (__int64 *)&v171;
      goto LABEL_252;
    }
    v102 = v154;
    v103 = 0;
    v104 = Binding;
    if ( v154 && Binding )
    {
      v105 = v131;
      p_lpMem = &v141;
      LOBYTE(v151) = 1;
      v103 = 0;
      v150 = 0;
      v106 = *((unsigned int *)v131 + 14);
      if ( (_DWORD)v106 )
      {
        if ( v106 >= v106 + 7
          || (v107 = (unsigned __int8 *)HeapAlloc(g_hHeap, 0, (v106 + 7) & 0xFFFFFFFFFFFFFFF8uLL), (v150 = v107) == 0) )
        {
          wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>(&p_lpMem);
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x648,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (const char *)8,
            AuthIdentity);
          ReleaseSRWLockExclusive(&gpClientLock);
          v110 = v141;
          v141 = 0;
          if ( v110 )
            HeapFree(g_hHeap, 0, v110);
          ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&v171);
          AcquireSRWLockExclusive(&gpClientLock);
          if ( v131 )
          {
            CReferencedObject::Release(v131);
            v131 = 0;
          }
          if ( v133 )
          {
            CClientOxid::Release(v133);
            v133 = 0;
          }
          if ( v134 )
          {
            CClientOxid::Release(v134);
            v134 = 0;
          }
          ReleaseSRWLockExclusive(&gpClientLock);
          if ( v136 )
            (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v136 + 16LL))(v136);
          return 8;
        }
        memcpy_0(v107, *((const void **)v105 + 8), *((unsigned int *)v105 + 14));
        v103 = *((_DWORD *)v105 + 14);
      }
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>(&p_lpMem);
    }
    if ( !*((_BYTE *)v131 + 42) )
    {
      v108 = v155;
      v109 = CProcess::ReferenceRemoteClientOxid(v155, v133);
      Pointer = v109;
      if ( v109 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x658,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (const char *)v109,
          AuthIdentity);
        goto LABEL_284;
      }
      if ( v134 )
      {
        v111 = CProcess::ReferenceRemoteClientOxid(v108, v134);
        Pointer = v111;
        if ( v111 )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x660,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (const char *)v111,
            AuthIdentity);
          CProcess::ReleaseRemoteClientOxid(v108, v133);
LABEL_284:
          ReleaseSRWLockExclusive(&gpClientLock);
          v112 = v141;
          v141 = 0;
          if ( v112 )
            HeapFree(g_hHeap, 0, v112);
          ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&v171);
          AcquireSRWLockExclusive(&gpClientLock);
          if ( v131 )
          {
            CReferencedObject::Release(v131);
            v131 = 0;
          }
          if ( v133 )
          {
            CClientOxid::Release(v133);
            v133 = 0;
          }
          v88 = v134;
          if ( !v134 )
            goto LABEL_292;
          goto LABEL_291;
        }
      }
    }
    ReleaseSRWLockExclusive(&gpClientLock);
    if ( a14 && a11 )
    {
      if ( !*((_WORD *)v133 + 116) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v113);
      *v35 = 0;
    }
    ClearOxidInfo(v19);
    if ( *v35 )
    {
      v114 = v172;
      v115 = v173;
      v116 = v174;
      v117 = v175;
      v118 = v176;
      *(_OWORD *)v19 = v171;
      v119 = v177;
      *((_OWORD *)v19 + 1) = v114;
      v120 = v178;
      *((_OWORD *)v19 + 2) = v115;
      v121 = v179;
      *((_OWORD *)v19 + 3) = v116;
      v122 = v180;
      *((_OWORD *)v19 + 4) = v117;
      v180 = 0;
      *((_OWORD *)v19 + 5) = v118;
      *((_OWORD *)v19 + 6) = v119;
      *((_OWORD *)v19 + 7) = v120;
      *((_OWORD *)v19 + 8) = v121;
      *((_QWORD *)v19 + 18) = v122;
      v171 = 0;
      v172 = 0;
      v173 = 0;
      v174 = 0;
      v175 = 0;
      v176 = 0;
      v177 = 0;
      v178 = 0;
      v179 = 0;
    }
    v123 = v131;
    *v156 = *((_QWORD *)v131 + 3);
    v124 = v158;
    *v157 = *((_WORD *)v123 + 20);
    if ( v124 )
      *v124 = *((_WORD *)v133 + 116) == 0;
    if ( v102 && v104 )
    {
      v125 = v141;
      v126 = 0;
      *v102 = v103;
      *v104 = v125;
    }
    else
    {
      v126 = v141;
    }
    v141 = 0;
    if ( v126 )
      HeapFree(g_hHeap, 0, v126);
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)&v171);
    AcquireSRWLockExclusive(&gpClientLock);
    if ( v131 )
    {
      CReferencedObject::Release(v131);
      v131 = 0;
    }
    if ( v133 )
    {
      CClientOxid::Release(v133);
      v133 = 0;
    }
    if ( v134 )
    {
      CClientOxid::Release(v134);
      v134 = 0;
    }
    ReleaseSRWLockExclusive(&gpClientLock);
    if ( v136 )
      (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v136 + 16LL))(v136);
    return 0;
  }
  v137 = 0;
  v45 = CMid::GetBinding(v131, &v137, v39);
  v36 = v45;
  if ( v45 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x4B8,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)v45,
      AuthIdentity);
    if ( v137 )
    {
      Binding = v137;
      RpcBindingFree(&Binding);
    }
    RpcRevertToSelfEx(v18);
    goto LABEL_245;
  }
  v46 = v131;
  v47 = s_dwDCOMSCMRemoteCallFlags & 4;
  v48 = s_dwDCOMSCMRemoteCallFlags & 8;
  v143 = v47;
  v144 = v48;
  if ( (s_dwDCOMSCMRemoteCallFlags & 4) == 0 || *((_BYTE *)v131 + 44) )
  {
    v49 = (s_dwDCOMSCMRemoteCallFlags & 4) == 0;
    MachineName = ExtractMachineName(*((unsigned __int16 **)v131 + 4));
    if ( MachineName )
    {
      v51 = -1;
      while ( MachineName[++v51] != 0 )
        ;
      v53 = v51 + 8;
      v55 = v51 + 8;
      v54 = 2 * (v51 + 8);
      if ( !is_mul_ok(v55, 2u) )
        v54 = -1;
      v56 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v54);
      v57 = v56;
      if ( v56 )
      {
        if ( v53 )
        {
          if ( v53 <= 0x7FFFFFFF )
          {
            v58 = 2147483646;
            v59 = L"RPCSS/";
            v60 = v53;
            do
            {
              if ( !v58 )
                break;
              if ( !*v59 )
                break;
              *v56++ = *v59++;
              --v58;
              --v60;
            }
            while ( v60 );
            v61 = v56 - 1;
            if ( v60 )
              v61 = v56;
            *v61 = 0;
          }
          else
          {
            *v56 = 0;
          }
        }
        StringCchCatW(v57, v53, MachineName);
      }
      HeapFree(g_hHeap, 0, MachineName);
      v46 = v131;
      v47 = v143;
      v48 = v144;
      goto LABEL_81;
    }
    v46 = v131;
    v47 = v143;
    v48 = v144;
  }
  else
  {
    v49 = s_cRpcssSvc + 1;
  }
  v57 = 0;
LABEL_81:
  v62 = *((_WORD *)v46 + 20);
  *(_WORD *)v132 = v62;
  if ( v49 >= s_cRpcssSvc + 2 )
  {
LABEL_203:
    Pointer = wil::details::in1diag3::Log_Win32(
                retaddr,
                (void *)0x5E0,
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
                (const char *)5,
                AuthIdentity);
    if ( v57 )
      HeapFree(g_hHeap, 0, v57);
    if ( v137 )
    {
      Binding = v137;
      RpcBindingFree(&Binding);
    }
    RpcRevertToSelfEx(v18);
    v81 = v159;
LABEL_252:
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v81);
    AcquireSRWLockExclusive(&gpClientLock);
    v101 = v131;
    if ( v131 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v131 + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(CMid *, __int64))v101)(v101, 1);
      v131 = 0;
    }
    if ( v133 )
    {
      CClientOxid::Release(v133);
      v133 = 0;
    }
    v88 = v134;
    if ( !v134 )
      goto LABEL_292;
    goto LABEL_291;
  }
  v63 = (CRpcSecurityCallbackManager *)L"Using unsecure binding";
  while ( 1 )
  {
    v138 = 0;
    v64 = 0;
    if ( v49 < s_cRpcssSvc + 1 )
    {
      if ( v49 )
      {
        v63 = (CRpcSecurityCallbackManager *)(2LL * (v49 - 1));
        v65 = *((_WORD *)s_aRpcssSvc + 8 * v49 - 4);
        if ( !v47 )
        {
          if ( v65 != 9 )
            goto LABEL_118;
          SecurityQOS.ImpersonationType = 3;
          SecurityQOS.Version = 1;
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
LABEL_93:
          if ( CRpcSecurityCallbackManager::RegisterForRpcAuthSvcCallBack(v63, v137) )
            v34 = 1;
LABEL_95:
          if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ResolveClientOXID", 1313);
          v66 = v65;
          if ( v65 == 0xFFFF )
            v66 = -1;
          v67 = 5;
          if ( !dword_18014E7BC )
            v67 = 2;
          v68 = RpcBindingSetAuthInfoExW(v137, v57, v67, v66, 0, 0, &SecurityQOS);
          if ( !v68 )
            goto LABEL_122;
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x52A,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
            (const char *)v68,
            (unsigned int)AuthIdentitya);
          if ( !v34 )
            goto LABEL_117;
          p_lpMem = &lpMem;
          LOBYTE(v151) = 1;
          v34 = 0;
          lpMem = 0;
          v150 = 0;
          CRpcSecurityCallbackManager::GetSecurityContextDetailsAndTurnOffCallback(v69, v137, 0, &v135, &v150);
          if ( (_BYTE)v151 )
          {
            v70 = *p_lpMem;
            *p_lpMem = v150;
            if ( v70 )
              HeapFree(g_hHeap, 0, v70);
          }
          v71 = lpMem;
          lpMem = 0;
          goto LABEL_108;
        }
        if ( v65 == v62 )
          goto LABEL_118;
      }
      else
      {
        v65 = v62;
      }
      if ( v47 && !(unsigned int)ValidAuthnSvc((CMid *)((char *)v131 + 80), v65) )
      {
        v62 = *(_WORD *)v132;
        goto LABEL_118;
      }
      SecurityQOS.ImpersonationType = 3;
      SecurityQOS.Version = 1;
      SecurityQOS.Capabilities = 1;
      SecurityQOS.IdentityTracking = 1;
      if ( v65 != 9 )
        goto LABEL_95;
      goto LABEL_93;
    }
    if ( !v48 )
      break;
    v34 = 0;
LABEL_120:
    if ( ++v49 >= s_cRpcssSvc + 2 )
    {
      v18 = BindingHandlea;
      goto LABEL_203;
    }
    v47 = v143;
    v48 = v144;
  }
  v65 = 0;
  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ResolveClientOXID", 1346);
  v72 = RpcBindingSetAuthInfoW(v137, 0, 1u, 0, 0, 0);
  if ( v72 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x549,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)v72,
      (unsigned int)AuthIdentitya);
LABEL_117:
    v62 = *(_WORD *)v132;
LABEL_118:
    v34 = 0;
LABEL_119:
    v63 = (CRpcSecurityCallbackManager *)L"Using unsecure binding";
    goto LABEL_120;
  }
LABEL_122:
  LODWORD(AuthIdentitya) = (unsigned __int16)cMyNetworkProtseqs;
  Pointer = (unsigned int)NdrClientCall2(
                            &stru_18010EDD0,
                            &byte_18011BB26,
                            v137,
                            v142,
                            AuthIdentitya,
                            aMyNetworkProtseqs,
                            v163,
                            v161.Data4,
                            &v159[1],
                            (char *)&v159[1] + 4).Pointer;
  if ( gfEnableTracing )
  {
    v73.Simple = (LONG_PTR)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      AuthIdentity = 3;
      ComTraceMessage(Pointer, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ResolveClientOXID", 1374);
    }
  }
  if ( Pointer == 1745 )
  {
    HIDWORD(v159[1]) = DcomProtocolVersion_NoResolveOxid2;
    DWORD2(v162) = 0;
    AuthIdentity = (unsigned __int16)cMyNetworkProtseqs;
    v75 = (unsigned int)NdrClientCall2(&stru_18010EDD0, &byte_18011BA42, v137, v142).Pointer;
    Pointer = v75;
    if ( gfEnableTracing )
    {
      v73.Simple = (LONG_PTR)WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        AuthIdentity = 3;
        ComTraceMessage(v75, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ResolveClientOXID", 1395);
      }
    }
  }
  v135 = 0;
  v139 = 0;
  if ( !v34 )
  {
    if ( !Pointer )
      goto LABEL_159;
    v34 = 0;
LABEL_136:
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x598,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)Pointer,
      AuthIdentity);
    if ( Pointer != 5 && Pointer != 1747 && Pointer != 1750 && Pointer != 1825 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        ComTraceMessage(Pointer, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ResolveClientOXID", 1444);
      v80 = v139;
      v139 = 0;
      if ( v80 )
        HeapFree(g_hHeap, 0, v80);
      if ( v57 )
        HeapFree(g_hHeap, 0, v57);
      if ( v137 )
      {
        Binding = v137;
        RpcBindingFree(&Binding);
      }
      RpcRevertToSelfEx(BindingHandlea);
      v81 = v159;
      goto LABEL_252;
    }
    v71 = v139;
    v139 = 0;
LABEL_108:
    if ( v71 )
      HeapFree(g_hHeap, 0, v71);
    v62 = *(_WORD *)v132;
    goto LABEL_119;
  }
  if ( Pointer )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x57E,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
      (const char *)Pointer,
      AuthIdentity);
    p_lpMem = (void **)&v139;
    LOBYTE(v151) = 1;
    v34 = 0;
    v150 = 0;
    CRpcSecurityCallbackManager::GetSecurityContextDetailsAndTurnOffCallback(v76, v137, 0, &v135, &v150);
    if ( (_BYTE)v151 )
    {
      v77 = *p_lpMem;
      *p_lpMem = v150;
      if ( v77 )
        HeapFree(g_hHeap, 0, v77);
    }
    goto LABEL_136;
  }
  p_lpMem = (void **)&v139;
  LOBYTE(v151) = 1;
  v150 = 0;
  SecurityContextDetailsAndTurnOffCallback = CRpcSecurityCallbackManager::GetSecurityContextDetailsAndTurnOffCallback(
                                               (CRpcSecurityCallbackManager *)v73.Pointer,
                                               v137,
                                               &v138,
                                               &v135,
                                               &v150);
  if ( (_BYTE)v151 )
  {
    v79 = *p_lpMem;
    *p_lpMem = v150;
    if ( v79 )
      HeapFree(g_hHeap, 0, v79);
  }
  v64 = v138;
  if ( !SecurityContextDetailsAndTurnOffCallback )
    v34 = 0;
LABEL_159:
  v82 = NegotiateDCOMVersion_Client((struct tagCOMVERSION *)((char *)&v159[1] + 4));
  v36 = v82;
  if ( !v82 )
  {
    if ( v34 )
    {
      if ( v64 == 16 )
        *((_WORD *)v131 + 20) = 9;
      else
        *((_WORD *)v131 + 20) = v64;
      AcquireSRWLockExclusive(&gpClientLock);
      v84 = CMid::SetMarshaledTargetInfo(v131, v135, v139);
      Pointer = v84;
      if ( v84 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x5C6,
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
          (const char *)v84,
          AuthIdentity);
        ReleaseSRWLockExclusive(&gpClientLock);
        goto LABEL_181;
      }
      ReleaseSRWLockExclusive(&gpClientLock);
    }
    else
    {
      *((_WORD *)v131 + 20) = v65;
    }
    if ( DsaValid(v163[0]) )
    {
      v89 = v139;
      a5 = *(_WORD *)(v85 + 4);
      v139 = 0;
      if ( v89 )
        HeapFree(g_hHeap, 0, v89);
      if ( v57 )
        HeapFree(g_hHeap, 0, v57);
      if ( v137 )
      {
        lpMem = v137;
        RpcBindingFree(&lpMem);
      }
      v35 = v142;
      v19 = v153;
      RpcRevertToSelfEx(BindingHandlea);
      goto LABEL_216;
    }
    if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      CMid::PrintableName(v131);
      AuthIdentity = 0;
      ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\manager.cxx", "ResolveClientOXID", 1492);
    }
    Pointer = wil::details::in1diag3::Log_Win32(
                retaddr,
                (void *)0x5D5,
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
                (const char *)0x776,
                AuthIdentity);
LABEL_181:
    v86 = v139;
    v139 = 0;
    if ( v86 )
      HeapFree(g_hHeap, 0, v86);
    if ( v57 )
      HeapFree(g_hHeap, 0, v57);
    if ( v137 )
    {
      Binding = v137;
      RpcBindingFree(&Binding);
    }
    RpcRevertToSelfEx(BindingHandlea);
    ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v159);
    AcquireSRWLockExclusive(&gpClientLock);
    v87 = v131;
    if ( v131 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v131 + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(CMid *, __int64))v87)(v87, 1);
      v131 = 0;
    }
    if ( v133 )
    {
      CClientOxid::Release(v133);
      v133 = 0;
    }
    v88 = v134;
    if ( !v134 )
      goto LABEL_292;
LABEL_291:
    CClientOxid::Release(v88);
    v134 = 0;
LABEL_292:
    ReleaseSRWLockExclusive(&gpClientLock);
    if ( v136 )
      (*(void (__fastcall **)(struct CProcess *))(*(_QWORD *)v136 + 16LL))(v136);
    return Pointer;
  }
  wil::details::in1diag3::_Log_Win32(
    retaddr,
    (void *)0x5AA,
    (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\manager.cxx",
    (const char *)v82,
    AuthIdentity);
  v83 = v139;
  v139 = 0;
  if ( v83 )
    HeapFree(g_hHeap, 0, v83);
  if ( v57 )
    HeapFree(g_hHeap, 0, v57);
  if ( v137 )
  {
    Binding = v137;
    RpcBindingFree(&Binding);
  }
  RpcRevertToSelfEx(BindingHandlea);
LABEL_245:
  ClearOxidInfo((struct __MIDL_ILocalObjectExporter_0007 *)v159);
  v147 = 0;
  lambda_505646f3df15c8bd29ef639cc06ee5bf_::operator()(v146);
  return v36;
}

```

## disassembly

```asm
0x18001cce0  push    rbp
0x18001cce2  push    rbx
0x18001cce3  push    rdi
0x18001cce4  push    r12
0x18001cce6  push    r13
0x18001cce8  push    r15
0x18001ccea  lea     rbp, [rsp-2C8h]
0x18001ccf2  sub     rsp, 3C8h
0x18001ccf9  mov     rax, cs:__security_cookie
0x18001cd00  xor     rax, rsp
0x18001cd03  mov     [rbp+2F0h+var_A0], rax
0x18001cd0a  mov     rax, [rbp+2F0h+arg_70]
0x18001cd11  mov     r12, rcx
0x18001cd14  mov     r13, [rbp+2F0h+arg_30]
0x18001cd1b  mov     rbx, r9
0x18001cd1e  mov     r10, [rbp+2F0h+arg_28]
0x18001cd25  mov     r15, r8
0x18001cd28  mov     rdi, [rbp+2F0h+arg_58]
0x18001cd2f  mov     [rbp+2F0h+BindingHandle], rcx
0x18001cd33  mov     rcx, [rbp+2F0h+arg_80]
0x18001cd3a  mov     [rbp+2F0h+Binding], rcx
0x18001cd3e  xor     ecx, ecx
0x18001cd40  mov     [rsp+3F0h+var_3A0], rcx
0x18001cd45  mov     [rsp+3F0h+var_390], rcx
0x18001cd4a  mov     [rsp+3F0h+var_388], rcx
0x18001cd4f  mov     [rsp+3F0h+var_378], rcx
0x18001cd54  lea     rcx, [rsp+3F0h+var_3A0]
0x18001cd59  mov     [rbp+2F0h+var_330], rcx
0x18001cd5d  lea     rcx, [rsp+3F0h+var_390]
0x18001cd62  mov     [rbp+2F0h+var_328], rcx
0x18001cd66  lea     rcx, [rsp+3F0h+var_388]
0x18001cd6b  mov     [rbp+2F0h+var_2A0], rax
0x18001cd6f  mov     rax, [rbp+2F0h+arg_78]
0x18001cd76  mov     [rbp+2F0h+var_320], rcx
0x18001cd7a  lea     rcx, [rsp+3F0h+var_378]
0x18001cd7f  mov     [rbp+2F0h+var_2B8], rdx
0x18001cd83  mov     rdx, [rbp+2F0h+arg_38]
0x18001cd8a  mov     [rbp+2F0h+var_2C0], rax
0x18001cd8e  mov     rax, [rbp+2F0h+arg_88]
0x18001cd95  mov     [rbp+2F0h+var_318], rcx
0x18001cd99  mov     [rbp+2F0h+var_348], r8
0x18001cd9d  mov     [rbp+2F0h+var_2D0], r10
0x18001cda1  mov     [rbp+2F0h+var_2C8], r13
0x18001cda5  mov     [rbp+2F0h+var_2B0], rdx
0x18001cda9  mov     [rbp+2F0h+var_2A8], rax
0x18001cdad  mov     [rbp+2F0h+var_310], 1
0x18001cdb1  test    r13, r13
0x18001cdb4  jz      loc_18001E8D7
0x18001cdba  test    rdx, rdx
0x18001cdbd  jz      loc_18001E8D7
0x18001cdc3  test    rax, rax
0x18001cdc6  jz      loc_18001E8D7
0x18001cdcc  test    rbx, rbx
0x18001cdcf  jz      short loc_18001CE11
0x18001cdd1  mov     rcx, rbx; struct tagDUALSTRINGARRAY *
0x18001cdd4  call    ?DsaValid@@YA_NPEBUtagDUALSTRINGARRAY@@@Z; DsaValid(tagDUALSTRINGARRAY const *)
0x18001cdd9  test    al, al
0x18001cddb  jnz     short loc_18001CE11
0x18001cddd  mov     edx, 41Fh; void *
0x18001cde2  mov     rcx, [rbp+2F8h]; this
0x18001cde9  lea     r8, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x18001cdf0  mov     r9d, 57h ; 'W'; char *
0x18001cdf6  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18001cdfb  lea     rcx, [rbp+2F0h+var_330]
0x18001cdff  mov     [rbp+2F0h+var_310], 0
0x18001ce03  mov     ebx, eax
0x18001ce05  call    _lambda_505646f3df15c8bd29ef639cc06ee5bf___operator__
0x18001ce0a  mov     eax, ebx
0x18001ce0c  jmp     loc_18001D28B
0x18001ce11  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18001ce18  mov     [rsp+3F0h+var_30], rsi
0x18001ce20  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001ce27  jz      short loc_18001CE80
0x18001ce29  mov     rax, cs:WPP_GLOBAL_Control
0x18001ce30  test    byte ptr [rax+1Ch], 8
0x18001ce34  jz      short loc_18001CE80
0x18001ce36  test    r10, r10
0x18001ce39  lea     rax, Class
0x18001ce40  mov     r9d, 422h
0x18001ce46  lea     r8, aResolvecliento; "ResolveClientOXID"
0x18001ce4d  cmovnz  rax, r10
0x18001ce51  lea     rdx, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x18001ce58  mov     [rsp+3F0h+var_3B8], rax
0x18001ce5d  mov     ecx, esi
0x18001ce5f  mov     rax, [r15]
0x18001ce62  mov     [rsp+3F0h+SecurityQOS], rax
0x18001ce67  lea     rax, aOxidI64xMachin; "OXID:%I64X Machine:%ws"
0x18001ce6e  mov     qword ptr [rsp+3F0h+AuthzSvc], rax
0x18001ce73  mov     dword ptr [rsp+3F0h+AuthIdentity], 3; unsigned int
0x18001ce7b  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18001ce80  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001ce87  call    cs:__imp_AcquireSRWLockExclusive
0x18001ce8d  lea     r8, [rsp+3F0h+var_398]; bool *
0x18001ce92  mov     [rsp+3F0h+var_398], 0
0x18001ce97  lea     rdx, [rsp+3F0h+var_3A0]; struct CMid **
0x18001ce9c  mov     rcx, rbx; struct tagDUALSTRINGARRAY *
0x18001ce9f  call    ?FindOrCreate@CMid@@SAJPEBUtagDUALSTRINGARRAY@@PEAPEAV1@PEA_N@Z; CMid::FindOrCreate(tagDUALSTRINGARRAY const *,CMid * *,bool *)
0x18001cea4  mov     ebx, eax
0x18001cea6  test    eax, eax
0x18001cea8  jz      short loc_18001CEB1
0x18001ceaa  mov     edx, 42Ah
0x18001ceaf  jmp     short loc_18001CEE6
0x18001ceb1  cmp     [rsp+3F0h+var_398], 0
0x18001ceb6  jz      short loc_18001CF1D
0x18001ceb8  mov     rcx, [rsp+3F0h+var_3A0]
0x18001cebd  mov     r8, rdi; unsigned __int8 *
0x18001cec0  movzx   eax, [rbp+2F0h+arg_48]
0x18001cec7  mov     edx, [rbp+2F0h+arg_50]; unsigned int
0x18001cecd  xchg    ax, [rcx+28h]
0x18001ced1  mov     rcx, [rsp+3F0h+var_3A0]; this
0x18001ced6  call    ?SetMarshaledTargetInfo@CMid@@QEAAJKPEAE@Z; CMid::SetMarshaledTargetInfo(ulong,uchar *)
0x18001cedb  mov     ebx, eax
0x18001cedd  test    eax, eax
0x18001cedf  jz      short loc_18001CF1D
0x18001cee1  mov     edx, 434h; void *
0x18001cee6  mov     rcx, [rbp+2F8h]; this
0x18001ceed  lea     r8, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x18001cef4  mov     r9d, ebx; char *
0x18001cef7  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001cefc  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001cf03  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cf09  lea     rcx, [rbp+2F0h+var_330]
0x18001cf0d  mov     [rbp+2F0h+var_310], 0
0x18001cf11  call    _lambda_505646f3df15c8bd29ef639cc06ee5bf___operator__
0x18001cf16  mov     eax, ebx
0x18001cf18  jmp     loc_18001D283
0x18001cf1d  mov     rax, [rsp+3F0h+var_3A0]
0x18001cf22  lea     rcx, [rbp+2F0h+var_300]; this
0x18001cf26  mov     r15, [r15]
0x18001cf29  mov     rbx, cs:?gpClientOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA; ObjexHashTable::CHashTable * gpClientOxidTable
0x18001cf30  mov     [rsp+3F0h+var_38], r14
0x18001cf38  mov     r14, [rax+18h]
0x18001cf3c  lea     rax, ??_7CId2Key@@6B@; const CId2Key::`vftable'
0x18001cf43  mov     [rbp+2F0h+var_300], rax
0x18001cf47  mov     [rbp+2F0h+var_2F8], r15
0x18001cf4b  mov     [rbp+2F0h+var_2F0], r14
0x18001cf4f  call    ?Hash@CId2Key@@UEBAKXZ; CId2Key::Hash(void)
0x18001cf54  xor     edx, edx
0x18001cf56  mov     ecx, 1
0x18001cf5b  div     dword ptr [rbx]
0x18001cf5d  mov     rax, [rbx+8]
0x18001cf61  mov     rbx, [rax+rdx*8]
0x18001cf65  mov     edx, 2
0x18001cf6a  test    rbx, rbx
0x18001cf6d  jz      loc_18001D03C
0x18001cf73  mov     rax, 0DEADDEADDEADDEADh
0x18001cf7d  nop     dword ptr [rax]
0x18001cf80  cmp     [rbx+10h], rax
0x18001cf84  jnz     short loc_18001D000
0x18001cf86  mov     rax, [rbp+2F8h]
0x18001cf8d  xorps   xmm0, xmm0
0x18001cf90  mov     [rbp+2F0h+pExceptionRecord.ExceptionFlags], ecx
0x18001cf96  mov     r8d, edx; dwFlags
0x18001cf99  xor     ecx, ecx
0x18001cf9b  mov     [rbp+2F0h+pExceptionRecord.ExceptionCode], 80004003h
0x18001cfa5  mov     [rbp+2F0h+pExceptionRecord.ExceptionRecord], rcx
0x18001cfac  xor     edx, edx; pContextRecord
0x18001cfae  mov     [rbp+2F0h+pExceptionRecord.NumberParameters], ecx
0x18001cfb4  lea     rcx, [rbp+2F0h+pExceptionRecord]; pExceptionRecord
0x18001cfbb  movups  xmmword ptr [rbp+2F0h+pExceptionRecord.ExceptionInformation+5Ch], xmm0
0x18001cfc2  mov     [rbp+2F0h+pExceptionRecord.ExceptionAddress], rax
0x18001cfc9  movups  xmmword ptr [rbp+2F0h+pExceptionRecord+1Ch], xmm0
0x18001cfd0  movups  xmmword ptr [rbp+2F0h+pExceptionRecord.ExceptionInformation+0Ch], xmm0
0x18001cfd7  movups  xmmword ptr [rbp+2F0h+pExceptionRecord.ExceptionInformation+1Ch], xmm0
0x18001cfde  movups  xmmword ptr [rbp+2F0h+pExceptionRecord.ExceptionInformation+2Ch], xmm0
0x18001cfe5  movups  xmmword ptr [rbp+2F0h+pExceptionRecord.ExceptionInformation+3Ch], xmm0
0x18001cfec  movups  xmmword ptr [rbp+2F0h+pExceptionRecord.ExceptionInformation+4Ch], xmm0
0x18001cff3  movups  xmmword ptr [rbp+2F0h+pExceptionRecord.ExceptionInformation+68h], xmm0
0x18001cffa  call    cs:__imp_RaiseFailFastException
0x18001d000  mov     rax, [rbx]
0x18001d003  lea     rdx, [rbp+2F0h+var_300]
0x18001d007  mov     rcx, rbx
0x18001d00a  mov     rax, [rax+28h]
0x18001d00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d013  test    al, al
0x18001d015  jnz     loc_18001D105
0x18001d01b  mov     rbx, [rbx+10h]
0x18001d01f  mov     rax, 0DEADDEADDEADDEADh
0x18001d029  mov     ecx, 1
0x18001d02e  mov     edx, 2
0x18001d033  test    rbx, rbx
0x18001d036  jnz     loc_18001CF80
0x18001d03c  xor     r15d, r15d
0x18001d03f  mov     ebx, r15d
0x18001d042  lea     rcx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001d049  mov     [rsp+3F0h+var_390], rbx
0x18001d04e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d054  cmp     [rsp+3F0h+var_390], 0
0x18001d05a  jnz     loc_18001E2C0
0x18001d060  mov     r10, [rsp+3F0h+var_3A0]
0x18001d065  xorps   xmm0, xmm0
0x18001d068  xor     eax, eax
0x18001d06a  movups  xmmword ptr [rbp+2F0h+var_290], xmm0
0x18001d06e  mov     [rbp+2F0h+var_200], rax
0x18001d075  movups  [rbp+2F0h+var_280], xmm0
0x18001d079  movups  xmmword ptr [rbp+2F0h+var_270.Data1], xmm0
0x18001d080  movups  [rbp+2F0h+var_260], xmm0
0x18001d087  movups  xmmword ptr [rbp+2F0h+var_250], xmm0
0x18001d08e  movups  [rbp+2F0h+var_240], xmm0
0x18001d095  movups  [rbp+2F0h+var_230], xmm0
0x18001d09c  movups  [rbp+2F0h+var_220], xmm0
0x18001d0a3  movups  xmmword ptr [rbp+2F0h+var_210.Data1], xmm0
0x18001d0aa  cmp     [r10+2Ah], al
0x18001d0ae  jz      loc_18001D196
0x18001d0b4  mov     r14, [rbp+2F0h+var_348]
0x18001d0b8  lea     rax, [rsp+3F0h+var_378]
0x18001d0bd  mov     [rsp+3F0h+SecurityQOS], rax
0x18001d0c2  lea     r9, [rbp+2F0h+var_290]
0x18001d0c6  lea     rax, [rbp+2F0h+var_2D0]
0x18001d0ca  mov     rdx, r14
0x18001d0cd  mov     qword ptr [rsp+3F0h+AuthzSvc], rax
0x18001d0d2  lea     r8, [rsp+3F0h+var_3A0]
0x18001d0d7  lea     rax, [rbp+2F0h+arg_20]
0x18001d0de  lea     rcx, [rbp+2F0h+var_300]
0x18001d0e2  mov     [rsp+3F0h+AuthIdentity], rax
0x18001d0e7  call    _lambda_ed20763ba46da10d6147d4426465f69a____lambda_ed20763ba46da10d6147d4426465f69a_
0x18001d0ec  cmp     [rbp+2F0h+arg_60], 0
0x18001d0f3  jz      short loc_18001D164
0x18001d0f5  lea     rcx, [rbp+2F0h+var_300]
0x18001d0f9  call    _lambda_ed20763ba46da10d6147d4426465f69a___operator__
0x18001d0fe  mov     ebx, eax
0x18001d100  jmp     loc_18001D189
0x18001d105  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18001d10c  jz      short loc_18001D154
0x18001d10e  mov     rax, cs:WPP_GLOBAL_Control
0x18001d115  test    byte ptr [rax+1Ch], 8
0x18001d119  jz      short loc_18001D154
0x18001d11b  mov     [rsp+3F0h+var_3B8], r14
0x18001d120  lea     rax, aFoundClientoxi_0; "Found ClientOXID OXID:%I64X MID:%I64X"
0x18001d127  mov     [rsp+3F0h+SecurityQOS], r15
0x18001d12c  lea     r8, aCclientoxidFin; "CClientOxid::FindIfExists"
0x18001d133  mov     qword ptr [rsp+3F0h+AuthzSvc], rax
0x18001d138  lea     rdx, aOnecoreComComb_0; "onecore\\com\\combase\\rpcss\\objex\\or"...
0x18001d13f  mov     r9d, 73h ; 's'
0x18001d145  mov     dword ptr [rsp+3F0h+AuthIdentity], 3
0x18001d14d  mov     ecx, esi
0x18001d14f  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18001d154  mov     rcx, rbx; this
0x18001d157  call    ?Reference@CClientOxid@@UEAAXXZ; CClientOxid::Reference(void)
0x18001d15c  xor     r15d, r15d
0x18001d15f  jmp     loc_18001D042
0x18001d164  lea     rcx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001d16b  call    cs:__imp_AcquireSRWLockShared
0x18001d171  lea     rcx, [rbp+2F0h+var_300]
0x18001d175  call    _lambda_ed20763ba46da10d6147d4426465f69a___operator__
0x18001d17a  lea     rcx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001d181  mov     ebx, eax
0x18001d183  call    cs:__imp_ReleaseSRWLockShared
0x18001d189  test    ebx, ebx
0x18001d18b  jz      loc_18001DF4F
0x18001d191  jmp     loc_18001E28B
0x18001d196  mov     rcx, [r13+40h]; struct tagDUALSTRINGARRAY *
0x18001d19a  test    rcx, rcx
0x18001d19d  jnz     loc_18001DEA7
0x18001d1a3  mov     rcx, r12; BindingHandle
0x18001d1a6  call    cs:__imp_RpcImpersonateClient
0x18001d1ac  mov     ebx, eax
0x18001d1ae  test    eax, eax
0x18001d1b0  jz      short loc_18001D1D2
0x18001d1b2  mov     rcx, [rbp+2F8h]; this
0x18001d1b9  lea     r8, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x18001d1c0  mov     r9d, eax; char *
0x18001d1c3  mov     edx, 487h; void *
0x18001d1c8  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001d1cd  jmp     loc_18001E28B
0x18001d1d2  mov     rcx, [rsp+3F0h+var_3A0]; this
0x18001d1d7  cmp     byte ptr [rcx+2Bh], 0
0x18001d1db  jz      loc_18001D372
0x18001d1e1  mov     rbx, [rcx+48h]
0x18001d1e5  test    rbx, rbx
0x18001d1e8  jz      short loc_18001D1EE
0x18001d1ea  lock inc dword ptr [rbx+8]
0x18001d1ee  mov     r14, [rbp+2F0h+var_348]
0x18001d1f2  lea     rax, [rbp+2F0h+var_280]
0x18001d1f6  mov     [rsp+3F0h+SecurityQOS], rax; struct CONTAINERVERSION *
0x18001d1fb  lea     r9, [rbp+2F0h+var_270.Data4]; struct _GUID *
0x18001d202  lea     rax, [rbp+2F0h+var_210.Data4]
0x18001d209  mov     rcx, rbx; this
0x18001d20c  mov     qword ptr [rsp+3F0h+AuthzSvc], rax; struct _GUID *
0x18001d211  lea     r8, [rbp+2F0h+var_250]; struct tagDUALSTRINGARRAY **
0x18001d218  mov     rdx, [r14]; unsigned __int64
0x18001d21b  lea     rax, [rbp+2F0h+var_210]
0x18001d222  mov     [rsp+3F0h+AuthIdentity], rax; int
0x18001d227  call    ?CallCrossContainerResolveOxid@CrossContainerClientSet@@QEAAJ_KPEAPEAUtagDUALSTRINGARRAY@@PEAU_GUID@@PEA_K2PEAUCONTAINERVERSION@@@Z; CrossContainerClientSet::CallCrossContainerResolveOxid(unsigned __int64,tagDUALSTRINGARRAY * *,_GUID *,unsigned __int64 *,_GUID *,CONTAINERVERSION *)
0x18001d22c  mov     edi, eax
0x18001d22e  test    rbx, rbx
0x18001d231  jz      short loc_18001D23B
0x18001d233  mov     rcx, rbx
0x18001d236  call    ?Release@?$AddComReferenceCounting_StandardReferenceCountingLayer@VCrossContainerClientSet@@V?$AddComReferenceCounting_ReferenceCountLayer@VCrossContainerClientSet@@V?$Allocation_StandardDeleteSelfLayer@VCrossContainerClientSet@@V?$MixinBase@VCrossContainerClientSet@@VMixins_NilBaseForwarderLayer@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<CrossContainerClientSet,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<CrossContainerClientSet,ObjectLibrary::Details::Allocation_StandardDeleteSelfLayer<CrossContainerClientSet,ObjectLibrary::Details::MixinBase<CrossContainerClientSet,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(void)
0x18001d23b  test    edi, edi
0x18001d23d  jz      short loc_18001D2AB
0x18001d23f  mov     rcx, [rbp+2F8h]; this
0x18001d246  lea     r8, aOnecoreComComb_93; "onecore\\com\\combase\\rpcss\\objex\\ma"...
0x18001d24d  mov     r9d, edi; char *
0x18001d250  mov     edx, 498h; void *
0x18001d255  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001d25a  mov     rcx, r12; BindingHandle
0x18001d25d  call    cs:__imp_RpcRevertToSelfEx
0x18001d263  lea     rcx, [rbp+2F0h+var_290]; struct __MIDL_ILocalObjectExporter_0007 *
0x18001d267  call    ?ClearOxidInfo@@YAXPEAU__MIDL_ILocalObjectExporter_0007@@@Z; ClearOxidInfo(__MIDL_ILocalObjectExporter_0007 *)
  ... truncated ...
```
