# RpcServer::RetrieveTask(ushort const *,ushort const *,ulong *,ushort * *)

- ea: `0x18000d8a0`
- end: `0x18000fd9d`
- name: `?RetrieveTask@RpcServer@@QEAAJPEBG0PEAKPEAPEAG@Z`
- size: `9469`
- prototype: `__int64 __fastcall(RpcServer *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cba0`

## callees

- `0x18000b8c4`
- `0x18000ba20`
- `0x18000bb10`
- `0x18000cb10`
- `0x18000cbe0`
- `0x18000cc40`
- `0x18000ce10`
- `0x18000ce30`
- `0x18000d160`
- `0x18000d1c0`
- `0x18000d830`
- `0x18000d8a0`
- `0x18000fda4`
- `0x18000fe50`
- `0x18000ff10`
- `0x1800103d4`
- `0x1800104c0`
- `0x180013530`
- `0x180014f48`
- `0x180016630`
- `0x18001ea40`
- `0x18001fe10`
- `0x180024730`
- `0x18002f814`
- `0x18002f9d0`
- `0x180040fd0`
- `0x180054824`
- `0x180054bd8`
- `0x18005a2bc`
- `0x18005a2d6`
- `0x180069eb0`
- `0x18006e318`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000dbb1`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dc30`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e0ef`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e14e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e57f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e5de`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f1a9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f4dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f568`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dbb1`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dc30`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e0ef`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e14e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e57f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e5de`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f1a9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f4dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f568`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000e94c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000e94c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e966`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea68`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea76`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eda2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efb0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eff1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f032`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f073`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fcbb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fcff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e966`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea68`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea76`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eda2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efb0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eff1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f032`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f073`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fcbb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fcff`
- `OLEAUT32!__imp_SysStringLen` at `0x18000dc91`
- `OLEAUT32!__imp_SysStringLen` at `0x18000dcac`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e1bf`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e1da`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e647`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e662`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ea93`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f20f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f226`
- `OLEAUT32!__imp_SysStringLen` at `0x18000dc91`
- `OLEAUT32!__imp_SysStringLen` at `0x18000dcac`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e1bf`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e1da`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e647`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e662`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ea93`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f20f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f226`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000dcea`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000e20e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000e697`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000f0e4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000dcea`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000e20e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000e697`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000f0e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000db3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000db3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000df3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ee24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f9f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fce2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000df3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ee24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f9f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fce2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000de5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000debf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000de5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000debf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ddd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000df13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ddd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000df13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ec85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000efd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f019`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f05a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f09b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ec85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000edc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000efd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f019`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f05a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f09b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dbff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e01d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e0be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e11d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e17c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e369`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e3f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e4b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e54e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e5ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e60c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eac4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f177`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f1d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f4ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f537`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dbff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e01d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e0be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e11d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e17c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e369`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e3f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e4b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e54e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e5ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e60c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eac4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f177`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f1d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f4ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000daf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000daf3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000db11`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000db11`
- `RPCRT4!RpcImpersonateClient` at `0x18000dadd`
- `RPCRT4!RpcImpersonateClient` at `0x18000e901`
- `RPCRT4!RpcImpersonateClient` at `0x18000dadd`
- `RPCRT4!RpcImpersonateClient` at `0x18000e901`
- `RPCRT4!RpcRevertToSelf` at `0x18000db25`
- `RPCRT4!RpcRevertToSelf` at `0x18000e934`
- `RPCRT4!RpcRevertToSelf` at `0x18000f5ae`
- `RPCRT4!RpcRevertToSelf` at `0x18000fc6a`
- `RPCRT4!RpcRevertToSelf` at `0x18000db25`
- `RPCRT4!RpcRevertToSelf` at `0x18000e934`
- `RPCRT4!RpcRevertToSelf` at `0x18000f5ae`
- `RPCRT4!RpcRevertToSelf` at `0x18000fc6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000def9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000df2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dfd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000def9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000df2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dfd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f801`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000de84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000de84`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18000dfb7`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x18000dfb7`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000f3cd`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000f3cd`

## string_xrefs

- `0x18000e0e8`: `NT TASK`
- `0x18000e578`: `NT TASK`
- `0x18000f4d6`: `NT TASK\`
- `0x18000f561`: `NT TASK\`
- `0x18000dbaa`: `TaskCache\Tree`
- `0x18000f61e`: `RetrieveTask`
- `0x18000fc15`: `RpcServer::RetrieveTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
__int64 __fastcall RpcServer::RetrieveTask(
        RpcServer *this,
        OLECHAR *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int16 **a5)
{
  unsigned __int16 v7; // r8
  int i; // ecx
  int v9; // r10d
  bool v10; // zf
  unsigned int v11; // r9d
  __int64 v13; // rax
  const OLECHAR *v14; // r9
  __int64 v15; // r10
  OLECHAR *v16; // rcx
  OLECHAR v17; // r8
  __int64 v18; // rcx
  OLECHAR *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  OLECHAR *v22; // r8
  OLECHAR v23; // cx
  OLECHAR *v24; // rcx
  RPC_STATUS v25; // eax
  EventManager *v26; // rcx
  RPC_STATUS v27; // ebx
  HANDLE CurrentThread; // rax
  RTL_SRWLOCK *v29; // r14
  JobStore *v30; // r13
  void *v31; // r12
  BYTE *v32; // r15
  HKEY v33; // rdi
  OLECHAR *v34; // rax
  OLECHAR *v35; // rbx
  BSTR v36; // rax
  struct IErrorInfo *v37; // rdx
  OLECHAR *v38; // rax
  BSTR *v39; // rax
  BSTR *v40; // rsi
  BSTR v41; // rax
  struct IErrorInfo *v42; // rdx
  BSTR *v43; // rax
  struct IErrorInfo *v44; // rdx
  BSTR *v45; // r12
  UINT v46; // eax
  UINT v47; // ecx
  UINT v48; // r13d
  struct IErrorInfo *v49; // rdx
  BSTR v50; // rcx
  const WCHAR *v51; // rdx
  LSTATUS v52; // eax
  unsigned int v53; // edx
  signed int v54; // esi
  HKEY v55; // rcx
  LSTATUS v56; // eax
  BYTE *v57; // rbx
  LSTATUS v58; // eax
  int v59; // edx
  int v60; // r8d
  JobBucket *v61; // rax
  JobBucket *v62; // rax
  unsigned int v63; // edx
  JobBucket *v64; // rbx
  JobBucket *v65; // rcx
  _bstr_t::Data_t *v66; // rcx
  _bstr_t::Data_t *v67; // rax
  _bstr_t::Data_t *v68; // rbx
  BSTR v69; // rax
  struct IErrorInfo *v70; // rdx
  BSTR *v71; // rax
  BSTR *v72; // rbx
  BSTR v73; // rax
  struct IErrorInfo *v74; // rdx
  _bstr_t::Data_t *v75; // rax
  struct IErrorInfo *v76; // rdx
  _bstr_t::Data_t *v77; // rdi
  UINT v78; // r15d
  UINT v79; // r12d
  UINT v80; // esi
  struct IErrorInfo *v81; // rdx
  BSTR v82; // rcx
  _bstr_t::Data_t *v83; // rcx
  BSTR v84; // rax
  OLECHAR j; // cx
  int v86; // ebx
  UINT v87; // r13d
  OLECHAR *v88; // rsi
  LPVOID v89; // rdi
  __int64 v90; // rbx
  StringStream *v91; // rcx
  __int64 v92; // rcx
  struct IErrorInfo *v93; // rdx
  int v94; // ebx
  HKEY v95; // rdi
  HKEY v96; // r15
  TaskXmlReader *v97; // rax
  TaskXmlReader *v98; // rbx
  int v99; // edx
  int v100; // r8d
  JobBucket *v101; // rax
  JobBucket *v102; // rax
  unsigned int v103; // edx
  JobBucket *v104; // rbx
  JobBucket *v105; // rcx
  _bstr_t::Data_t *v106; // rcx
  _bstr_t::Data_t *v107; // rax
  _bstr_t::Data_t *v108; // rbx
  BSTR v109; // rax
  struct IErrorInfo *v110; // rdx
  BSTR *v111; // rax
  BSTR *v112; // rbx
  BSTR v113; // rax
  struct IErrorInfo *v114; // rdx
  _bstr_t::Data_t *v115; // rax
  struct IErrorInfo *v116; // rdx
  _bstr_t::Data_t *v117; // r15
  UINT v118; // eax
  UINT v119; // r12d
  struct IErrorInfo *v120; // rdx
  BSTR v121; // rcx
  _bstr_t::Data_t *v122; // rcx
  BSTR v123; // rax
  OLECHAR k; // cx
  bool v125; // dl
  __int64 v126; // rcx
  _QWORD *v127; // rax
  void (__fastcall ***v128)(_QWORD, __int64); // rcx
  _QWORD *m; // rbx
  void **v130; // r8
  void **v131; // rbx
  _QWORD *v132; // rax
  _QWORD *n; // rbx
  void **v134; // r8
  RPC_STATUS v135; // eax
  EventManager *v136; // rcx
  RPC_STATUS v137; // ebx
  __int64 v138; // rbx
  OLECHAR *v139; // r12
  OLECHAR *v140; // r13
  unsigned __int64 v141; // r10
  __int64 v142; // r11
  __int64 v143; // r15
  unsigned __int64 v144; // rcx
  OLECHAR *v145; // rdx
  unsigned __int64 v146; // r9
  OLECHAR *v147; // r8
  OLECHAR v148; // ax
  __int64 v149; // rax
  void (__fastcall ***v150)(_QWORD, __int64); // rcx
  UINT v151; // eax
  _WORD **v152; // rdx
  unsigned __int64 v153; // rbx
  SIZE_T v154; // rax
  unsigned __int16 *v155; // rax
  _WORD *v156; // rcx
  __int16 v157; // ax
  BSTR *v158; // rbx
  BSTR *v159; // rbx
  void ***v160; // rax
  void ***ii; // rbx
  void **v162; // r8
  BSTR *v163; // rbx
  __int64 v164; // rdx
  void **v165; // r8
  void ***v166; // rax
  void ***jj; // rbx
  void **v168; // rbx
  void (__fastcall ***v169)(_QWORD, __int64, void **); // rcx
  JobBucket *v170; // rcx
  _bstr_t::Data_t *v171; // rbx
  TaskXmlReader *v172; // rcx
  JobBucket *v173; // rcx
  _bstr_t::Data_t *v174; // rbx
  void **v175; // rcx
  void **v176; // rcx
  void **v177; // rbx
  void **v178; // rbx
  BSTR v179; // rcx
  BSTR v180; // rcx
  BSTR v181; // rcx
  void *v182; // rcx
  void *v183; // rcx
  struct IErrorInfo *v184; // rdx
  BSTR v185; // rcx
  volatile signed __int32 *v186; // rax
  volatile signed __int32 *v187; // rsi
  BSTR v188; // rax
  struct IErrorInfo *v189; // rdx
  OLECHAR *v190; // rax
  struct IErrorInfo *v191; // rdx
  UINT v192; // eax
  OLECHAR *v193; // rcx
  UINT v194; // r13d
  __int64 v195; // rax
  const OLECHAR *v196; // r10
  __int64 v197; // rdx
  OLECHAR *p_psz; // rcx
  OLECHAR v199; // r8
  _bstr_t::Data_t *v200; // rcx
  _bstr_t::Data_t *v201; // rax
  BSTR v202; // rax
  struct IErrorInfo *v203; // rdx
  _bstr_t::Data_t *v204; // rcx
  _bstr_t::Data_t *v205; // rax
  BSTR v206; // rax
  struct IErrorInfo *v207; // rdx
  signed int LastError; // eax
  signed int v209; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  const struct _GUID *lpcbData; // [rsp+28h] [rbp-D8h]
  const struct _GUID *lpcbDataa; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  void **pExceptionObject; // [rsp+88h] [rbp-78h] BYREF
  char v216; // [rsp+90h] [rbp-70h]
  const unsigned __int16 *v217; // [rsp+98h] [rbp-68h]
  __int64 v218; // [rsp+A0h] [rbp-60h]
  __int64 v219; // [rsp+A8h] [rbp-58h]
  int v220; // [rsp+B0h] [rbp-50h]
  __int64 v221; // [rsp+B4h] [rbp-4Ch]
  DWORD Type[2]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD PrivilegeSetLength[2]; // [rsp+C8h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+D0h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+D8h] [rbp-28h] BYREF
  HKEY v226; // [rsp+E0h] [rbp-20h] BYREF
  BYTE *v227; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v228; // [rsp+F0h] [rbp-10h]
  void *v229; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v230; // [rsp+100h] [rbp+0h]
  LPVOID v231; // [rsp+108h] [rbp+8h]
  TaskXmlReader *v232; // [rsp+110h] [rbp+10h]
  char v233; // [rsp+118h] [rbp+18h] BYREF
  int v234; // [rsp+119h] [rbp+19h]
  __int16 v235; // [rsp+11Dh] [rbp+1Dh]
  char v236; // [rsp+11Fh] [rbp+1Fh]
  __int64 v237; // [rsp+120h] [rbp+20h]
  __int128 v238; // [rsp+128h] [rbp+28h] BYREF
  LPVOID lpMem[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v240; // [rsp+148h] [rbp+48h]
  OLECHAR *v241; // [rsp+150h] [rbp+50h]
  unsigned int *v242; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v243; // [rsp+160h] [rbp+60h] BYREF
  OLECHAR *v244; // [rsp+168h] [rbp+68h]
  _bstr_t::Data_t *v245; // [rsp+170h] [rbp+70h]
  unsigned __int16 **v246; // [rsp+178h] [rbp+78h]
  RTL_SRWLOCK *v247; // [rsp+180h] [rbp+80h]
  _GENERIC_MAPPING GenericMapping; // [rsp+188h] [rbp+88h] BYREF
  GUID v249; // [rsp+198h] [rbp+98h] BYREF
  _bstr_t::Data_t *v250; // [rsp+1A8h] [rbp+A8h]
  BSTR v251; // [rsp+1B0h] [rbp+B0h]
  JobBucket *v252; // [rsp+1B8h] [rbp+B8h]
  GUID v253; // [rsp+1C0h] [rbp+C0h] BYREF
  _bstr_t::Data_t *v254; // [rsp+1D0h] [rbp+D0h]
  BSTR v255; // [rsp+1D8h] [rbp+D8h]
  JobBucket *v256; // [rsp+1E0h] [rbp+E0h]
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v258[520]; // [rsp+200h] [rbp+100h] BYREF
  char v259[24]; // [rsp+408h] [rbp+308h] BYREF
  char v260[240]; // [rsp+420h] [rbp+320h] BYREF
  char v261[24]; // [rsp+510h] [rbp+410h] BYREF
  LPVOID v262; // [rsp+528h] [rbp+428h]
  LPVOID v263; // [rsp+530h] [rbp+430h]
  _bstr_t::Data_t *v264; // [rsp+5E0h] [rbp+4E0h]
  char v265[8]; // [rsp+618h] [rbp+518h] BYREF
  __int64 v266; // [rsp+620h] [rbp+520h]
  __int64 v267; // [rsp+628h] [rbp+528h]
  OLECHAR psz; // [rsp+640h] [rbp+540h] BYREF
  __int16 v269; // [rsp+642h] [rbp+542h] BYREF

  v242 = a4;
  v243 = a3;
  v246 = a5;
  if ( a5 )
    *a5 = 0;
  memset_0(&psz, 0, 0x20Au);
  if ( !a2 || !*a2 )
  {
    v195 = 2147483646;
    v196 = L"\\";
    v197 = 261;
    p_psz = &psz;
    v11 = 0;
    do
    {
      if ( !v195 )
        goto LABEL_42;
      v199 = *v196;
      if ( !*v196 )
        goto LABEL_42;
      ++v196;
      *p_psz++ = v199;
      --v195;
      --v197;
    }
    while ( v197 );
    --p_psz;
    v11 = -2147024774;
LABEL_42:
    *p_psz = 0;
    if ( (v11 & 0x80000000) == 0 )
      goto LABEL_43;
    return v11;
  }
  if ( *a2 != 92 )
  {
    v13 = 2147483646;
    v14 = L"\\";
    v15 = 261;
    v16 = &psz;
    while ( v13 )
    {
      v17 = *v14;
      if ( !*v14 )
        break;
      ++v14;
      *v16++ = v17;
      --v13;
      if ( !--v15 )
        return (unsigned int)-2147024774;
    }
    *v16 = 0;
  }
  v7 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 261 )
      return (unsigned int)-2147024773;
    v9 = a2[i];
    if ( !(_WORD)v9 )
      break;
    if ( v9 == 92 )
    {
      v10 = v7 == 92;
LABEL_11:
      if ( v10 )
        return (unsigned int)-2147024773;
      goto LABEL_12;
    }
    if ( v9 == 32 )
    {
      if ( v7 == 92 )
        return (unsigned int)-2147024773;
      v10 = v7 == 0;
      goto LABEL_11;
    }
    if ( v9 != 46 )
    {
      if ( v9 == 47 )
        return (unsigned int)-2147024773;
      v10 = v9 == 58;
      goto LABEL_11;
    }
    if ( v7 == 46 || v7 == 92 && a2[i + 1] == 92 )
      return (unsigned int)-2147024773;
LABEL_12:
    v7 = a2[i];
  }
  if ( v7 == 92 && i > 1 )
    return (unsigned int)-2147024773;
  v18 = 261;
  v19 = &psz;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  v11 = -2147024809;
  if ( !v18 )
    return v11;
  v20 = 2147483646;
  v21 = v18;
  v22 = &psz + 261 - v18;
  do
  {
    if ( !v20 )
      break;
    v23 = *a2;
    if ( !*a2 )
      break;
    ++a2;
    *v22++ = v23;
    --v20;
    --v21;
  }
  while ( v21 );
  v11 = -2147024774;
  if ( v21 )
    v11 = 0;
  v24 = v22 - 1;
  if ( v21 )
    v24 = v22;
  *v24 = 0;
  if ( !v21 )
    return v11;
LABEL_43:
  if ( !psz || !v269 && psz == 92 )
    return 2147942487LL;
  TokenHandle = 0;
  v25 = RpcImpersonateClient(0);
  v27 = v25;
  if ( v25 )
  {
    EventManager::EvtReport(v26, &IMPERSONATION_FAILURE, L"RetrieveTask", v25, phkResult, lpcbData);
    v216 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v217 = &qword_1800A8718;
    v218 = 0;
    v219 = 0;
    v220 = v27;
    v221 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    RpcRevertToSelf();
  }
  else
  {
    LastError = GetLastError();
    v209 = LastError;
    if ( LastError > 0 )
      v209 = (unsigned __int16)LastError | 0x80070000;
    RpcRevertToSelf();
    if ( v209 < 0 )
    {
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      return (unsigned int)v209;
    }
  }
  v29 = (RTL_SRWLOCK *)((char *)this + 16);
  v247 = v29;
  AcquireSRWLockShared(v29);
  v30 = JobStore::m_pCommonStore;
  v226 = (HKEY)JobStore::m_pCommonStore;
  v31 = TokenHandle;
  v232 = (TaskXmlReader *)TokenHandle;
  v32 = 0;
  v227 = 0;
  LODWORD(v228) = 0;
  v33 = 0;
  v245 = 0;
  hKey = 0;
  v34 = (OLECHAR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v35 = v34;
  if ( !v34 )
  {
    v216 = 0;
    v217 = &qword_1800A8718;
    v218 = 0;
    v219 = 0;
    v220 = 14;
    v221 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v244 = v34;
  *((_QWORD *)v34 + 1) = 0;
  *((_DWORD *)v34 + 4) = 1;
  v36 = SysAllocString(L"TaskCache\\Tree");
  *(_QWORD *)v35 = v36;
  if ( !v36 )
    _com_raise_error(-2147024882, v37);
  v244 = v35;
  if ( psz == 92 )
    v38 = (OLECHAR *)&v269;
  else
    v38 = &psz;
  v241 = v38;
  if ( *v38 )
  {
    v39 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v40 = v39;
    if ( !v39 )
    {
      v216 = 0;
      v217 = &qword_1800A8718;
      v218 = 0;
      v219 = 0;
      v220 = 14;
      v221 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    *(_QWORD *)PrivilegeSetLength = v39;
    v39[1] = 0;
    *((_DWORD *)v39 + 4) = 1;
    v41 = SysAllocString(L"\\");
    *v40 = v41;
    if ( !v41 )
      _com_raise_error(-2147024882, v42);
    *(_QWORD *)PrivilegeSetLength = v40;
    v43 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v45 = v43;
    if ( !v43 )
    {
      v216 = 0;
      v217 = &qword_1800A8718;
      v218 = 0;
      v219 = 0;
      v220 = 14;
      v221 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    *(_QWORD *)&GenericMapping.GenericRead = v43;
    v43[1] = 0;
    *((_DWORD *)v43 + 4) = 1;
    if ( *(_QWORD *)v35 )
      v46 = SysStringLen(*(BSTR *)v35);
    else
      v46 = 0;
    Type[0] = v46;
    if ( *v40 )
    {
      v47 = SysStringLen(*v40);
      v46 = Type[0];
    }
    else
    {
      v47 = 0;
    }
    cbData = v47;
    v48 = v47 + v46;
    if ( v47 + v46 < v46 || (v44 = (struct IErrorInfo *)(2LL * v48), (unsigned __int64)v44 > 0xFFFFFFFF) )
      _com_raise_error(-2147024882, v44);
    v185 = SysAllocStringByteLen(0, (UINT)v44);
    *v45 = v185;
    if ( v185 )
    {
      if ( *(_QWORD *)v35 )
        memcpy_0(v185, *(const void **)v35, 2LL * (Type[0] + 1));
      v184 = (struct IErrorInfo *)*v40;
      if ( *v40 )
        memcpy_0(&(*v45)[Type[0]], v184, 2LL * (cbData + 1));
    }
    else if ( v48 )
    {
      _com_raise_error(-2147024882, v184);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v35, (unsigned int)v184);
    v244 = (OLECHAR *)v45;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v40 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v40, (unsigned int)v184);
    v186 = (volatile signed __int32 *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v187 = v186;
    if ( !v186 )
    {
      v216 = 0;
      v217 = &qword_1800A8718;
      v218 = 0;
      v219 = 0;
      v220 = 14;
      v221 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    *(_QWORD *)&GenericMapping.GenericRead = v186;
    *((_QWORD *)v186 + 1) = 0;
    *((_DWORD *)v186 + 4) = 1;
    v188 = SysAllocString(v241);
    *(_QWORD *)v187 = v188;
    if ( !v188 )
      _com_raise_error(-2147024882, v189);
    *(_QWORD *)&GenericMapping.GenericRead = v187;
    v190 = (OLECHAR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v35 = v190;
    if ( !v190 )
    {
      v216 = 0;
      v217 = &qword_1800A8718;
      v218 = 0;
      v219 = 0;
      v220 = 14;
      v221 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v241 = v190;
    *((_QWORD *)v190 + 1) = 0;
    *((_DWORD *)v190 + 4) = 1;
    if ( *v45 )
      v192 = SysStringLen(*v45);
    else
      v192 = 0;
    Type[0] = v192;
    v193 = *(OLECHAR **)v187;
    if ( *(_QWORD *)v187 )
    {
      LODWORD(v193) = SysStringLen(v193);
      v192 = Type[0];
    }
    cbData = (unsigned int)v193;
    v194 = (_DWORD)v193 + v192;
    if ( (unsigned int)v193 + v192 < v192
      || (v191 = (struct IErrorInfo *)(2LL * v194), (unsigned __int64)v191 > 0xFFFFFFFF) )
    {
      _com_raise_error(-2147024882, v191);
    }
    v50 = SysAllocStringByteLen(0, (UINT)v191);
    *(_QWORD *)v35 = v50;
    if ( v50 )
    {
      if ( *v45 )
        memcpy_0(v50, *v45, 2LL * (Type[0] + 1));
      v49 = *(struct IErrorInfo **)v187;
      if ( *(_QWORD *)v187 )
        memcpy_0((void *)(*(_QWORD *)v35 + 2LL * Type[0]), v49, 2LL * (cbData + 1));
    }
    else if ( v194 )
    {
      _com_raise_error(-2147024882, v49);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v45 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v45, (unsigned int)v49);
    if ( _InterlockedExchangeAdd(v187 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v187, (unsigned int)v49);
    v30 = (JobStore *)v226;
    v31 = v232;
  }
  if ( v35 )
    v51 = *(const WCHAR **)v35;
  else
    v51 = 0;
  v52 = RegOpenKeyExW(*((HKEY *)v30 + 2), v51, 0, 0xF003Fu, &hKey);
  v54 = v52;
  if ( !v52 )
  {
    v33 = hKey;
    v55 = 0;
    hKey = 0;
    if ( v35 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v35, 0);
      v55 = hKey;
    }
    if ( v55 )
    {
      RegCloseKey(v55);
      hKey = 0;
    }
LABEL_91:
    Type[0] = 3;
    cbData = 0;
    hKey = 0;
    v56 = RegQueryValueExW(v33, L"SD", 0, Type, 0, &cbData);
    v54 = v56;
    if ( v56 )
    {
      if ( v56 > 0 )
        v54 = (unsigned __int16)v56 | 0x80070000;
    }
    else
    {
      if ( Type[0] != 3 )
        goto LABEL_427;
      v57 = (BYTE *)LocalAlloc(0, cbData);
      hKey = (HKEY)v57;
      if ( !v57 )
      {
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hKey);
        goto LABEL_100;
      }
      v58 = RegQueryValueExW(v33, L"SD", 0, Type, v57, &cbData);
      v54 = v58;
      if ( !v58 )
      {
        if ( Type[0] != 3 )
        {
          LocalFree(v57);
          v54 = -2147023537;
          goto LABEL_101;
        }
        if ( cbData )
        {
          v32 = v57;
          v227 = v57;
          LODWORD(v228) = cbData;
LABEL_100:
          v54 = 0;
          goto LABEL_101;
        }
LABEL_427:
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&hKey);
        v54 = -2147023537;
        goto LABEL_101;
      }
      if ( v58 > 0 )
        v54 = (unsigned __int16)v58 | 0x80070000;
      LocalFree(v57);
    }
    if ( v54 < 0 )
      goto LABEL_101;
    goto LABEL_100;
  }
  if ( v52 > 0 )
    v54 = (unsigned __int16)v52 | 0x80070000;
  if ( v35 && _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 4, 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v35, v53);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v54 >= 0 )
    goto LABEL_91;
LABEL_101:
  if ( v33 )
    RegCloseKey(v33);
  if ( v54 >= 0 )
  {
    cbData = 0;
    if ( !v31 )
      goto LABEL_382;
    if ( !v32 )
      goto LABEL_382;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Privilege[0].Attributes = 2;
    RequiredPrivileges.Privilege[0].Luid = (LUID)17LL;
    if ( !PrivilegeCheck(v31, &RequiredPrivileges, (LPBOOL)&cbData)
      || !cbData
      && ((GenericMapping.GenericRead = 1179785,
           GenericMapping.GenericWrite = 1179926,
           GenericMapping.GenericExecute = 1179808,
           GenericMapping.GenericAll = 2032127,
           PrivilegeSetLength[0] = 20,
           memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges)),
           Type[0] = 0,
           !AccessCheck(v32, v31, 1u, &GenericMapping, &RequiredPrivileges, PrivilegeSetLength, Type, (LPBOOL)&cbData))
       || !cbData
       || (Type[0] & 1) == 0) )
    {
LABEL_382:
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v227);
      v54 = -2147024891;
      goto LABEL_106;
    }
    LocalFree(v32);
    v250 = 0;
    v252 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v59, v60, (unsigned int)&v249, (__int64)&psz, 0);
    }
    v61 = (JobBucket *)HeapAlloc(g_PrivateHeap, 0, 0xD8u);
    if ( !v61 )
    {
      v216 = 0;
      v217 = &qword_1800A8718;
      v218 = 0;
      v219 = 0;
      v220 = 14;
      v221 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v62 = JobBucket::JobBucket(v61);
    v64 = v62;
    if ( v62 )
      _InterlockedIncrement((volatile signed __int32 *)v62 + 2);
    v65 = v252;
    if ( v252 && _InterlockedExchangeAdd((volatile signed __int32 *)v252 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(JobBucket *, __int64))v65)(v65, 1);
    v252 = v64;
    if ( psz == 92 || psz == 47 )
    {
      v66 = v250;
      if ( v250 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v250 + 4, 0xFFFFFFFF) == 1 )
          _bstr_t::Data_t::`scalar deleting destructor'(v66, v63);
        v250 = 0;
      }
      v67 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v68 = v67;
      if ( !v67 )
      {
        v216 = 0;
        v217 = &qword_1800A8718;
        v218 = 0;
        v219 = 0;
        v220 = 14;
        v221 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      *(_QWORD *)&GenericMapping.GenericRead = v67;
      *((_QWORD *)v67 + 1) = 0;
      *((_DWORD *)v67 + 4) = 1;
      v69 = SysAllocString(L"NT TASK");
      *(_QWORD *)v68 = v69;
      if ( !v69 )
        _com_raise_error(-2147024882, v70);
    }
    else
    {
      v200 = v250;
      if ( v250 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v250 + 4, 0xFFFFFFFF) == 1 )
          _bstr_t::Data_t::`scalar deleting destructor'(v200, v63);
        v250 = 0;
      }
      v201 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v68 = v201;
      if ( !v201 )
      {
        v216 = 0;
        v217 = &qword_1800A8718;
        v218 = 0;
        v219 = 0;
        v220 = 14;
        v221 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      *(_QWORD *)&GenericMapping.GenericRead = v201;
      *((_QWORD *)v201 + 1) = 0;
      *((_DWORD *)v201 + 4) = 1;
      v202 = SysAllocString(L"NT TASK\\");
      *(_QWORD *)v68 = v202;
      if ( !v202 )
        _com_raise_error(-2147024882, v203);
    }
    v250 = v68;
    v71 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v72 = v71;
    if ( !v71 )
    {
      v216 = 0;
      v217 = &qword_1800A8718;
      v218 = 0;
      v219 = 0;
      v220 = 14;
      v221 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    *(_QWORD *)&GenericMapping.GenericRead = v71;
    v71[1] = 0;
    *((_DWORD *)v71 + 4) = 1;
    v73 = SysAllocString(&psz);
    *v72 = v73;
    if ( !v73 )
      _com_raise_error(-2147024882, v74);
    *(_QWORD *)&GenericMapping.GenericRead = v72;
    v75 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v77 = v75;
    if ( !v75 )
    {
      v216 = 0;
      v217 = &qword_1800A8718;
      v218 = 0;
      v219 = 0;
      v220 = 14;
      v221 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v245 = v75;
    *((_QWORD *)v75 + 1) = 0;
    *((_DWORD *)v75 + 4) = 1;
    if ( v250 && *(_QWORD *)v250 )
      v78 = SysStringLen(*(BSTR *)v250);
    else
      v78 = 0;
    if ( *v72 )
      v79 = SysStringLen(*v72);
    else
      v79 = 0;
    v80 = v79 + v78;
    if ( v79 + v78 < v78 || (v76 = (struct IErrorInfo *)(2LL * v80), (unsigned __int64)v76 > 0xFFFFFFFF) )
      _com_raise_error(-2147024882, v76);
    v82 = SysAllocStringByteLen(0, (UINT)v76);
    *(_QWORD *)v77 = v82;
    if ( v82 )
    {
      if ( v250 && *(_QWORD *)v250 )
        memcpy_0(v82, *(const void **)v250, 2LL * (v78 + 1));
      v81 = (struct IErrorInfo *)*v72;
      if ( *v72 )
        memcpy_0((void *)(*(_QWORD *)v77 + 2LL * v78), v81, 2LL * (v79 + 1));
    }
    else if ( v80 )
    {
      _com_raise_error(-2147024882, v81);
    }
    v83 = v250;
    if ( v250 && _InterlockedExchangeAdd((volatile signed __int32 *)v250 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'(v83, (unsigned int)v81);
    v250 = v77;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v72 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v72, (unsigned int)v81);
    if ( v250 )
      v84 = *(BSTR *)v250;
    else
      v84 = 0;
    for ( j = *v84; *v84; j = *v84 )
    {
      if ( j == 47 )
      {
        *v84 = 92;
      }
      else if ( j != 92 )
      {
        ++v84;
        continue;
      }
      v251 = ++v84;
    }
    v249 = GUID_NULL;
    *((_DWORD *)v252 + 15) = 0;
    *(_QWORD *)Type = 0;
    v86 = JobStore::GenerateTaskXmlFromRegistry(v30, &v249, v243, v242, Type);
    if ( v86 >= 0 )
    {
      v87 = 0;
      v88 = 0;
      v242 = 0;
      hKey = 0;
      v89 = *(LPVOID *)Type;
      if ( !*(_QWORD *)Type )
      {
        ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&hKey);
        SysFreeString(0);
        operator delete(0);
        JobMoniker::~JobMoniker((JobMoniker *)&v249);
        ReleaseSRWLockShared(v29);
        wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
        return 2147942487LL;
      }
      v90 = -1;
      do
        ++v90;
      while ( *(_WORD *)(*(_QWORD *)Type + 2 * v90) );
      v91 = (StringStream *)HeapAlloc(g_PrivateHeap, 0, 0x28u);
      if ( !v91 )
      {
        v216 = 0;
        v217 = &qword_1800A8718;
        v218 = 0;
        v219 = 0;
        v220 = 14;
        v221 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      StringStream::StringStream(v91);
      *(_QWORD *)v92 = &StringReader::`vftable';
      *(_QWORD *)(v92 + 16) = -1;
      *(_DWORD *)(v92 + 24) = v90;
      *(_QWORD *)(v92 + 32) = v89;
      v226 = 0;
      v94 = ((__int64 (__fastcall *)(__int64, GUID *, HKEY *))StringReader::`vftable')(
              v92,
              &GUID_0000000c_0000_0000_c000_000000000046,
              &v226);
      if ( v94 < 0 )
      {
        ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&hKey);
        v95 = 0;
        hKey = 0;
        v96 = 0;
      }
      else
      {
        v95 = v226;
        hKey = v226;
        v96 = v226;
      }
      if ( (int)(v94 + 0x80000000) >= 0 && v94 != -2147467262 )
        _com_raise_error(v94, v93);
      if ( !v96 )
      {
        v216 = 0;
        v217 = &qword_1800A8718;
        v218 = 0;
        v219 = 0;
        v220 = 14;
        v221 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v97 = (TaskXmlReader *)HeapAlloc(g_PrivateHeap, 0, 0x460u);
      v98 = v97;
      v232 = v97;
      if ( !v97 )
      {
        v216 = 0;
        v217 = &qword_1800A8718;
        v218 = 0;
        v219 = 0;
        v220 = 14;
        v221 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      *(_QWORD *)v97 = &wmi::RefBase::`vftable';
      *((_DWORD *)v97 + 2) = 0;
      *(_QWORD *)v97 = &TaskXmlReader::`vftable';
      *((_QWORD *)v97 + 2) = 0;
      *((_QWORD *)v97 + 3) = 0;
      *((_QWORD *)v97 + 4) = v96;
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)v96 + 8LL))(v96);
      *((_BYTE *)v98 + 40) = 0;
      *((_QWORD *)v98 + 6) = 0;
      *((_QWORD *)v98 + 7) = 0;
      *((_BYTE *)v98 + 1106) &= 0xFCu;
      *((_DWORD *)v98 + 16) = 0;
      *((_QWORD *)v98 + 9) = 0;
      *((_WORD *)v98 + 40) = 0;
      *((_BYTE *)v98 + 1112) = 0;
      *((_DWORD *)v98 + 279) = 65542;
      v243 = (const unsigned __int16 *)v98;
      _InterlockedIncrement((volatile signed __int32 *)v98 + 2);
      v254 = 0;
      v256 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v99, v100, (unsigned int)&v253, (__int64)&psz, 0);
      }
      v101 = (JobBucket *)HeapAlloc(g_PrivateHeap, 0, 0xD8u);
      if ( !v101 )
      {
        v216 = 0;
        v217 = &qword_1800A8718;
        v218 = 0;
        v219 = 0;
        v220 = 14;
        v221 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v102 = JobBucket::JobBucket(v101);
      v104 = v102;
      if ( v102 )
        _InterlockedIncrement((volatile signed __int32 *)v102 + 2);
      v105 = v256;
      if ( v256 )
      {
        v103 = _InterlockedExchangeAdd((volatile signed __int32 *)v256 + 2, 0xFFFFFFFF);
        if ( v103 == 1 )
          (**(void (__fastcall ***)(JobBucket *))v105)(v105);
      }
      v256 = v104;
      if ( psz == 92 || psz == 47 )
      {
        v106 = v254;
        if ( v254 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v254 + 4, 0xFFFFFFFF) == 1 )
            _bstr_t::Data_t::`scalar deleting destructor'(v106, v103);
          v254 = 0;
        }
        v107 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
        v108 = v107;
        if ( !v107 )
        {
          wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)&pExceptionObject);
          throw (wmi::OutOfMemoryException *)&pExceptionObject;
        }
        *(_QWORD *)&GenericMapping.GenericRead = v107;
        *((_QWORD *)v107 + 1) = 0;
        *((_DWORD *)v107 + 4) = 1;
        v109 = SysAllocString(L"NT TASK");
        *(_QWORD *)v108 = v109;
        if ( !v109 )
          _com_raise_error(-2147024882, v110);
      }
      else
      {
        v204 = v254;
        if ( v254 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v254 + 4, 0xFFFFFFFF) == 1 )
            _bstr_t::Data_t::`scalar deleting destructor'(v204, v103);
          v254 = 0;
        }
        v205 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
        v108 = v205;
        if ( !v205 )
        {
          v216 = 0;
          v217 = &qword_1800A8718;
          v218 = 0;
          v219 = 0;
          v220 = 14;
          v221 = -1;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::OutOfMemoryException *)&pExceptionObject;
        }
        *(_QWORD *)&GenericMapping.GenericRead = v205;
        *((_QWORD *)v205 + 1) = 0;
        *((_DWORD *)v205 + 4) = 1;
        v206 = SysAllocString(L"NT TASK\\");
        *(_QWORD *)v108 = v206;
        if ( !v206 )
          _com_raise_error(-2147024882, v207);
      }
      v254 = v108;
      v111 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v112 = v111;
      if ( !v111 )
      {
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)&pExceptionObject);
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      *(_QWORD *)&GenericMapping.GenericRead = v111;
      v111[1] = 0;
      *((_DWORD *)v111 + 4) = 1;
      v113 = SysAllocString(&psz);
      *v112 = v113;
      if ( !v113 )
        _com_raise_error(-2147024882, v114);
      *(_QWORD *)&GenericMapping.GenericRead = v112;
      v115 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v117 = v115;
      if ( !v115 )
      {
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)&pExceptionObject);
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v245 = v115;
      *((_QWORD *)v115 + 1) = 0;
      *((_DWORD *)v115 + 4) = 1;
      if ( v254 && *(_QWORD *)v254 )
        v87 = SysStringLen(*(BSTR *)v254);
      if ( *v112 )
        v118 = SysStringLen(*v112);
      else
        v118 = 0;
      cbData = v118;
      v119 = v118 + v87;
      if ( v118 + v87 < v87 || (v116 = (struct IErrorInfo *)(2LL * v119), (unsigned __int64)v116 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, v116);
      v121 = SysAllocStringByteLen(0, (UINT)v116);
      *(_QWORD *)v117 = v121;
      if ( v121 )
      {
        if ( v254 && *(_QWORD *)v254 )
          memcpy_0(v121, *(const void **)v254, 2LL * (v87 + 1));
        v120 = (struct IErrorInfo *)*v112;
        if ( *v112 )
          memcpy_0((void *)(*(_QWORD *)v117 + 2LL * v87), v120, 2LL * (cbData + 1));
      }
      else if ( v119 )
      {
        _com_raise_error(-2147024882, v120);
      }
      v122 = v254;
      if ( v254 && _InterlockedExchangeAdd((volatile signed __int32 *)v254 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'(v122, (unsigned int)v120);
      v254 = v117;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v112 + 4, 0xFFFFFFFF) == 1 )
        _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v112, (unsigned int)v120);
      if ( v254 )
        v123 = *(BSTR *)v254;
      else
        v123 = 0;
      for ( k = *v123; *v123; k = *v123 )
      {
        if ( k == 47 )
        {
          *v123 = 92;
        }
        else if ( k != 92 )
        {
          ++v123;
          continue;
        }
        v255 = ++v123;
      }
      v253 = GUID_NULL;
      *((_DWORD *)v256 + 15) = 0;
      TSTime::TSTime((TSTime *)&v233, (bool)v120);
      TSTime::TSTime((TSTime *)&v238, v125);
      *(_OWORD *)lpMem = 0;
      v127 = (_QWORD *)std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v126, 0, 0);
      lpMem[0] = v127;
      v240 = 0;
      if ( lpMem[1] )
      {
        for ( m = (_QWORD *)*v127; m != v127; m = (_QWORD *)*m )
        {
          v128 = (void (__fastcall ***)(_QWORD, __int64))m[2];
          if ( v128 )
          {
            (**v128)(v128, 1);
            m[2] = 0;
            v127 = lpMem[0];
          }
        }
        v130 = (void **)*v127;
        *v127 = v127;
        *((LPVOID *)lpMem[0] + 1) = lpMem[0];
        lpMem[1] = 0;
        if ( v130 != lpMem[0] )
        {
          do
          {
            v131 = (void **)*v130;
            HeapFree(g_PrivateHeap, 0, v130);
            v130 = v131;
          }
          while ( v131 != lpMem[0] );
        }
      }
      v233 = 0;
      v234 = *(_DWORD *)((char *)&v227 + 1);
      v235 = *(_WORD *)((char *)&v227 + 5);
      v236 = HIBYTE(v227);
      v237 = -1;
      LOBYTE(v227) = 0;
      v228 = 0;
      v238 = (unsigned __int64)v227;
      v229 = 0;
      v230 = 0;
      v132 = (_QWORD *)std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v128, 0, 0);
      v229 = v132;
      v231 = 0;
      if ( v230 )
      {
        for ( n = (_QWORD *)*v132; n != v132; n = (_QWORD *)*n )
        {
          v150 = (void (__fastcall ***)(_QWORD, __int64))n[2];
          if ( v150 )
          {
            (**v150)(v150, 1);
            n[2] = 0;
            v132 = v229;
          }
        }
        v134 = (void **)*v132;
        *v132 = v132;
        *((_QWORD *)v229 + 1) = v229;
        v230 = 0;
        if ( v134 != v229 )
        {
          do
          {
            v177 = (void **)*v134;
            HeapFree(g_PrivateHeap, 0, v134);
            v134 = v177;
          }
          while ( v177 != v229 );
        }
      }
      v226 = 0;
      ServerXMLUpdateHandler::ServerXMLUpdateHandler(
        (ServerXMLUpdateHandler *)v258,
        0,
        1,
        &psz,
        0,
        0,
        0,
        (const struct JobMoniker *)&v253,
        (const struct User *)&v226,
        (struct Triggers::Trigulator *)&v233,
        (struct Actions::ActionCollection *)&v229,
        0,
        0,
        0,
        6u);
      wmi::AutoRef<User::UserEntry>::Release(&v226);
      PrivilegeSetLength[0] = 1;
      v135 = RpcImpersonateClient(0);
      v137 = v135;
      if ( v135 )
      {
        EventManager::EvtReport(v136, &IMPERSONATION_FAILURE, L"RpcServer::RetrieveTask", v135, phkResulta, lpcbDataa);
        v216 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v217 = &qword_1800A8718;
        v218 = 0;
        v219 = 0;
        v220 = v137;
        v221 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      v86 = TaskXmlReader::ProcessXml(v232, (struct ITaskXmlHandler *)v258);
      PrivilegeSetLength[0] = v86;
      if ( v86 >= 0 )
      {
        RpcRevertToSelf();
        v138 = v266;
        v139 = SysAllocStringLen(0, *(_DWORD *)(v266 + 16));
        if ( v139 )
        {
          SysFreeString(0);
          v140 = v139;
          v141 = *(_QWORD *)(v138 + 16) + 1LL;
          v142 = *(_QWORD *)(v138 + 24);
          v143 = 2147483646;
          while ( v142 )
          {
            if ( !v141 )
              goto LABEL_233;
            if ( v141 > 0x7FFFFFFF || (v144 = *(_QWORD *)(v142 + 8), v144 > 0x7FFFFFFE) )
            {
              *v140 = 0;
LABEL_233:
              SysFreeString(v139);
              goto LABEL_242;
            }
            v145 = *(OLECHAR **)v142;
            v146 = v141;
            v147 = v140;
            while ( v144 )
            {
              v148 = *v145;
              if ( !*v145 )
                break;
              ++v145;
              *v147++ = v148;
              --v144;
              if ( !--v146 )
              {
                *(v147 - 1) = 0;
                goto LABEL_233;
              }
            }
            *v147 = 0;
            v149 = *(_QWORD *)(v142 + 8);
            v140 += v149;
            v141 -= v149;
            v142 = *(_QWORD *)(v142 + 16);
          }
          SysFreeString(0);
          SysFreeString(0);
          v88 = v139;
          v242 = (unsigned int *)v139;
        }
        else
        {
          SysFreeString(0);
          v143 = 2147483646;
        }
LABEL_242:
        v151 = SysStringLen(v88);
        if ( v151 )
        {
          v153 = v151 + 1LL;
          v154 = 2 * v153;
          if ( !is_mul_ok(v153, 2u) )
            v154 = -1;
          v155 = (unsigned __int16 *)HeapAlloc(g_PrivateHeap, 0, v154);
          if ( !v155 )
          {
            wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)&pExceptionObject);
            throw (wmi::OutOfMemoryException *)&pExceptionObject;
          }
          v152 = v246;
          *v246 = v155;
          *v155 = 0;
          v156 = *v152;
          if ( v153 > 0x7FFFFFFF )
          {
            *v156 = 0;
          }
          else
          {
            v152 = (_WORD **)v88;
            while ( v143 )
            {
              v157 = *(_WORD *)v152;
              if ( !*(_WORD *)v152 )
                break;
              v152 = (_WORD **)((char *)v152 + 2);
              *v156++ = v157;
              --v143;
              if ( !--v153 )
                goto LABEL_251;
            }
            if ( !v153 )
LABEL_251:
              --v156;
            *v156 = 0;
          }
        }
        if ( v267 )
          (*(void (__fastcall **)(__int64, _WORD **))(*(_QWORD *)v267 + 16LL))(v267, v152);
        std::unique_ptr<TaskXmlWriter>::~unique_ptr<TaskXmlWriter>(v265, v152);
        if ( v264 )
        {
          _bstr_t::Data_t::Release(v264);
          v264 = 0;
        }
        v158 = (BSTR *)v263;
        if ( v263 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v263 + 4, 0xFFFFFFFF) == 1 )
          {
            if ( *v158 )
            {
              SysFreeString(*v158);
              *v158 = 0;
            }
            v179 = v158[1];
            if ( v179 )
            {
              operator delete(v179);
              v158[1] = 0;
            }
            HeapFree(g_PrivateHeap, 0, v158);
          }
          v263 = 0;
        }
        v159 = (BSTR *)v262;
        if ( v262 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v262 + 4, 0xFFFFFFFF) == 1 )
          {
            if ( *v159 )
            {
              SysFreeString(*v159);
              *v159 = 0;
            }
            v180 = v159[1];
            if ( v180 )
            {
              operator delete(v180);
              v159[1] = 0;
            }
            HeapFree(g_PrivateHeap, 0, v159);
          }
          v262 = 0;
        }
        std::vector<_DAB_SCHEDULE_BY_DAY *>::~vector<_DAB_SCHEDULE_BY_DAY *>(v261);
        TriggersXmlHandler::CurrentAction::~CurrentAction((TriggersXmlHandler::CurrentAction *)v260);
        wmi::AutoRef<User::UserEntry>::Release(v259);
        ValidationXmlHandler::~ValidationXmlHandler((ValidationXmlHandler *)v258);
        if ( v230 )
        {
          v160 = (void ***)v229;
          for ( ii = *(void ****)v229; ii != v160; ii = (void ***)*ii )
          {
            v175 = ii[2];
            if ( v175 )
            {
              (*(void (__fastcall **)(void **, __int64))*v175)(v175, 1);
              ii[2] = 0;
              v160 = (void ***)v229;
            }
          }
          v162 = *v160;
          *v160 = (void **)v160;
          *((_QWORD *)v229 + 1) = v229;
          v230 = 0;
          if ( v162 != v229 )
          {
            do
            {
              v178 = (void **)*v162;
              HeapFree(g_PrivateHeap, 0, v162);
              v162 = v178;
            }
            while ( v178 != v229 );
          }
        }
        v163 = (BSTR *)v231;
        if ( v231 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v231 + 4, 0xFFFFFFFF) == 1 )
          {
            if ( *v163 )
            {
              SysFreeString(*v163);
              *v163 = 0;
            }
            v181 = v163[1];
            if ( v181 )
            {
              operator delete(v181);
              v163[1] = 0;
            }
            HeapFree(g_PrivateHeap, 0, v163);
          }
          v231 = 0;
        }
        std::list<Task *>::clear(&v229);
        operator delete(v229);
        if ( lpMem[1] )
        {
          v166 = (void ***)lpMem[0];
          for ( jj = *(void ****)lpMem[0]; jj != v166; jj = (void ***)*jj )
          {
            v176 = jj[2];
            if ( v176 )
            {
              (*(void (__fastcall **)(void **, __int64))*v176)(v176, 1);
              jj[2] = 0;
              v166 = (void ***)lpMem[0];
            }
          }
          v165 = *v166;
          *v166 = (void **)v166;
          *((LPVOID *)lpMem[0] + 1) = lpMem[0];
          lpMem[1] = 0;
          if ( v165 != lpMem[0] )
          {
            do
            {
              v168 = (void **)*v165;
              HeapFree(g_PrivateHeap, 0, v165);
              v165 = v168;
            }
            while ( v168 != lpMem[0] );
          }
        }
        v233 = 0;
        v234 = *(_DWORD *)((char *)&v227 + 1);
        v235 = *(_WORD *)((char *)&v227 + 5);
        v236 = HIBYTE(v227);
        v237 = -1;
        LOBYTE(v227) = 0;
        v228 = 0;
        v238 = (unsigned __int64)v227;
        v169 = (void (__fastcall ***)(_QWORD, __int64, void **))v240;
        if ( v240 && _InterlockedExchangeAdd((volatile signed __int32 *)(v240 + 8), 0xFFFFFFFF) == 1 )
          (**v169)(v169, 1, v165);
        v240 = 0;
        std::list<Triggers::Trigger *>::clear(lpMem, v164, v165);
        if ( lpMem[0] )
          HeapFree(g_PrivateHeap, 0, lpMem[0]);
        v170 = v256;
        if ( v256 && _InterlockedExchangeAdd((volatile signed __int32 *)v256 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(JobBucket *, __int64))v170)(v170, 1);
        v256 = 0;
        v171 = v254;
        if ( v254 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v254 + 4, 0xFFFFFFFF) == 1 )
          {
            if ( *(_QWORD *)v171 )
            {
              SysFreeString(*(BSTR *)v171);
              *(_QWORD *)v171 = 0;
            }
            v182 = (void *)*((_QWORD *)v171 + 1);
            if ( v182 )
            {
              operator delete(v182);
              *((_QWORD *)v171 + 1) = 0;
            }
            HeapFree(g_PrivateHeap, 0, v171);
          }
          v254 = 0;
        }
        v172 = v232;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v232 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(TaskXmlReader *, __int64))v172)(v172, 1);
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v95 + 16LL))(v95);
        SysFreeString(v88);
        if ( *(_QWORD *)Type )
          HeapFree(g_PrivateHeap, 0, *(LPVOID *)Type);
        v173 = v252;
        if ( v252 && _InterlockedExchangeAdd((volatile signed __int32 *)v252 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(JobBucket *, __int64))v173)(v173, 1);
        v252 = 0;
        v174 = v250;
        if ( v250 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v250 + 4, 0xFFFFFFFF) == 1 )
          {
            if ( *(_QWORD *)v174 )
            {
              SysFreeString(*(BSTR *)v174);
              *(_QWORD *)v174 = 0;
            }
            v183 = (void *)*((_QWORD *)v174 + 1);
            if ( v183 )
            {
              operator delete(v183);
              *((_QWORD *)v174 + 1) = 0;
            }
            HeapFree(g_PrivateHeap, 0, v174);
          }
          v250 = 0;
        }
        ReleaseSRWLockShared(v29);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        return PrivilegeSetLength[0];
      }
      RpcRevertToSelf();
      ServerXMLUpdateHandler::~ServerXMLUpdateHandler((ServerXMLUpdateHandler *)v258);
      Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&v229);
      Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v233);
      JobMoniker::~JobMoniker((JobMoniker *)&v253);
      wmi::AutoRef<TaskXmlReader>::Release(&v243);
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&hKey);
      SysFreeString(0);
    }
    operator delete(*(void **)Type);
    JobMoniker::~JobMoniker((JobMoniker *)&v249);
    ReleaseSRWLockShared(v29);
    wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
    return (unsigned int)v86;
  }
  if ( v32 )
    LocalFree(v32);
LABEL_106:
  ReleaseSRWLockShared(v29);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v54;
}

```

## disassembly

```asm
0x18000d8a0  mov     [rsp-8+arg_0], rbx
0x18000d8a5  push    rbp
0x18000d8a6  push    rsi
0x18000d8a7  push    rdi
0x18000d8a8  push    r12
0x18000d8aa  push    r13
0x18000d8ac  push    r14
0x18000d8ae  push    r15
0x18000d8b0  lea     rbp, [rsp-760h]
0x18000d8b8  sub     rsp, 860h
0x18000d8bf  mov     rax, cs:__security_cookie
0x18000d8c6  xor     rax, rsp
0x18000d8c9  mov     [rbp+790h+var_40], rax
0x18000d8d0  mov     [rbp+790h+var_738], r9
0x18000d8d4  mov     [rbp+790h+var_730], r8
0x18000d8d8  mov     rbx, rdx
0x18000d8db  mov     r14, rcx
0x18000d8de  mov     rax, [rbp+790h+arg_20]
0x18000d8e5  mov     [rbp+790h+var_718], rax
0x18000d8e9  xor     esi, esi
0x18000d8eb  test    rax, rax
0x18000d8ee  jz      short loc_18000D8F3
0x18000d8f0  mov     [rax], rsi
0x18000d8f3  xor     edx, edx; Val
0x18000d8f5  mov     r8d, 20Ah; Size
0x18000d8fb  lea     rcx, [rbp+790h+psz]; void *
0x18000d902  call    memset_0
0x18000d907  test    rbx, rbx
0x18000d90a  jz      loc_18000F41F
0x18000d910  movzx   eax, word ptr [rbx]
0x18000d913  test    ax, ax
0x18000d916  jz      loc_18000F41F
0x18000d91c  mov     edi, 7FFFFFFEh
0x18000d921  mov     edx, 105h
0x18000d926  cmp     ax, 5Ch ; '\'
0x18000d92a  jnz     loc_18000D9BF
0x18000d930  mov     r8d, esi
0x18000d933  mov     ecx, esi
0x18000d935  cmp     ecx, edx
0x18000d937  jge     short loc_18000D962
0x18000d939  movsxd  r11, ecx
0x18000d93c  movzx   r10d, word ptr [rbx+r11*2]
0x18000d941  test    r10w, r10w
0x18000d945  jz      loc_18000DA0F
0x18000d94b  mov     r9d, r10d
0x18000d94e  cmp     r10d, 5Ch ; '\'
0x18000d952  jnz     short loc_18000D996
0x18000d954  cmp     r8w, r10w
0x18000d958  jz      short loc_18000D962
0x18000d95a  movzx   r8d, r10w
0x18000d95e  inc     ecx
0x18000d960  jmp     short loc_18000D935
0x18000d962  mov     r9d, 8007007Bh
0x18000d968  mov     eax, r9d
0x18000d96b  mov     rcx, [rbp+790h+var_40]
0x18000d972  xor     rcx, rsp; StackCookie
0x18000d975  call    __security_check_cookie
0x18000d97a  mov     rbx, [rsp+890h+arg_0]
0x18000d982  add     rsp, 860h
0x18000d989  pop     r15
0x18000d98b  pop     r14
0x18000d98d  pop     r13
0x18000d98f  pop     r12
0x18000d991  pop     rdi
0x18000d992  pop     rsi
0x18000d993  pop     rbp
0x18000d994  retn
0x18000d996  sub     r9d, 20h ; ' '
0x18000d99a  jnz     short loc_18000D9A9
0x18000d99c  cmp     r8w, 5Ch ; '\'
0x18000d9a1  jz      short loc_18000D962
0x18000d9a3  test    r8w, r8w
0x18000d9a7  jmp     short loc_18000D958
0x18000d9a9  sub     r9d, 0Eh
0x18000d9ad  jz      loc_18000F5D2
0x18000d9b3  sub     r9d, 1
0x18000d9b7  jz      short loc_18000D962
0x18000d9b9  cmp     r9d, 0Bh
0x18000d9bd  jmp     short loc_18000D958
0x18000d9bf  mov     rax, rdi
0x18000d9c2  lea     r9, asc_1800A7EC0; "\\"
0x18000d9c9  mov     r10, rdx
0x18000d9cc  lea     rcx, [rbp+790h+psz]
0x18000d9d3  test    rax, rax
0x18000d9d6  jz      short loc_18000DA07
0x18000d9d8  movzx   r8d, word ptr [r9]
0x18000d9dc  test    r8w, r8w
0x18000d9e0  jz      short loc_18000DA02
0x18000d9e2  add     r9, 2
0x18000d9e6  mov     [rcx], r8w
0x18000d9ea  add     rcx, 2
0x18000d9ee  dec     rax
0x18000d9f1  sub     r10, 1
0x18000d9f5  jnz     short loc_18000D9D3
0x18000d9f7  mov     r9d, 8007007Ah
0x18000d9fd  jmp     loc_18000D968
0x18000da02  test    r10, r10
0x18000da05  jz      short loc_18000D9F7
0x18000da07  mov     [rcx], si
0x18000da0a  jmp     loc_18000D930
0x18000da0f  cmp     r8w, 5Ch ; '\'
0x18000da14  jz      loc_18000F5F9
0x18000da1a  mov     rcx, rdx
0x18000da1d  lea     rax, [rbp+790h+psz]
0x18000da24  cmp     [rax], si
0x18000da27  jz      short loc_18000DA33
0x18000da29  add     rax, 2
0x18000da2d  sub     rcx, 1
0x18000da31  jnz     short loc_18000DA24
0x18000da33  mov     r9d, 80070057h
0x18000da39  test    rcx, rcx
0x18000da3c  cmovnz  r9d, esi
0x18000da40  mov     r8, rdx
0x18000da43  sub     r8, rcx
0x18000da46  test    rcx, rcx
0x18000da49  cmovz   r8, rsi
0x18000da4d  jz      loc_18000D968
0x18000da53  mov     rax, rdi
0x18000da56  sub     rdx, r8
0x18000da59  lea     r8, [rbp+r8*2+790h+psz]
0x18000da61  jz      short loc_18000DA85
0x18000da63  test    rax, rax
0x18000da66  jz      short loc_18000DA85
0x18000da68  movzx   ecx, word ptr [rbx]
0x18000da6b  test    cx, cx
0x18000da6e  jz      short loc_18000DA85
0x18000da70  add     rbx, 2
0x18000da74  mov     [r8], cx
0x18000da78  add     r8, 2
0x18000da7c  dec     rax
0x18000da7f  sub     rdx, 1
0x18000da83  jnz     short loc_18000DA63
0x18000da85  mov     r9d, 8007007Ah
0x18000da8b  test    rdx, rdx
0x18000da8e  cmovnz  r9d, esi
0x18000da92  lea     rcx, [r8-2]
0x18000da96  cmovnz  rcx, r8
0x18000da9a  mov     [rcx], si
0x18000da9d  jz      loc_18000D968
0x18000daa3  jmp     short loc_18000DABA
0x18000daa5  test    rdx, rdx
0x18000daa8  jz      loc_18000F46C
0x18000daae  mov     [rcx], si
0x18000dab1  test    r9d, r9d
0x18000dab4  js      loc_18000D968
0x18000daba  movzx   eax, [rbp+790h+psz]
0x18000dac1  test    ax, ax
0x18000dac4  jz      loc_18000F611
0x18000daca  cmp     [rbp+790h+var_24E], si
0x18000dad1  jz      loc_18000F607
0x18000dad7  mov     [rbp+790h+TokenHandle], rsi
0x18000dadb  xor     ecx, ecx; BindingHandle
0x18000dadd  call    cs:__imp_RpcImpersonateClient
0x18000dae4  nop     dword ptr [rax+rax+00h]
0x18000dae9  mov     ebx, eax
0x18000daeb  test    eax, eax
0x18000daed  jnz     loc_18000F61B
0x18000daf3  call    cs:__imp_GetCurrentThread
0x18000dafa  nop     dword ptr [rax+rax+00h]
0x18000daff  mov     rcx, rax; ThreadHandle
0x18000db02  lea     r9, [rbp+790h+TokenHandle]; TokenHandle
0x18000db06  mov     edx, 8; DesiredAccess
0x18000db0b  mov     r8d, 1; OpenAsSelf
0x18000db11  call    cs:__imp_OpenThreadToken
0x18000db18  nop     dword ptr [rax+rax+00h]
0x18000db1d  test    eax, eax
0x18000db1f  jz      loc_18000F593
0x18000db25  call    cs:__imp_RpcRevertToSelf
0x18000db2c  nop     dword ptr [rax+rax+00h]
0x18000db31  add     r14, 10h
0x18000db35  mov     [rbp+790h+var_710], r14
0x18000db3c  mov     rcx, r14; SRWLock
0x18000db3f  call    cs:__imp_AcquireSRWLockShared
0x18000db46  nop     dword ptr [rax+rax+00h]
0x18000db4b  nop
0x18000db4c  mov     r13, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18000db53  mov     [rbp+790h+var_7B0], r13
0x18000db57  mov     r12, [rbp+790h+TokenHandle]
0x18000db5b  mov     [rbp+790h+var_780], r12
0x18000db5f  mov     r15, rsi
0x18000db62  mov     qword ptr [rbp+790h+var_7A8], rsi
0x18000db66  mov     dword ptr [rbp+790h+var_7A8+8], esi
0x18000db69  mov     rdi, rsi
0x18000db6c  mov     [rbp+790h+var_720], rsi
0x18000db70  mov     [rbp+790h+hKey], rsi
0x18000db74  xor     edx, edx; dwFlags
0x18000db76  mov     r8d, 18h; dwBytes
0x18000db7c  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000db83  call    cs:__imp_HeapAlloc
0x18000db8a  nop     dword ptr [rax+rax+00h]
0x18000db8f  mov     rbx, rax
0x18000db92  test    rax, rax
0x18000db95  jz      loc_18000F66F
0x18000db9b  mov     [rbp+790h+var_728], rax
0x18000db9f  mov     [rax+8], rsi
0x18000dba3  mov     dword ptr [rax+10h], 1
0x18000dbaa  lea     rcx, psz; "TaskCache\\Tree"
0x18000dbb1  call    cs:__imp_SysAllocString
0x18000dbb8  nop     dword ptr [rax+rax+00h]
0x18000dbbd  mov     [rbx], rax
0x18000dbc0  test    rax, rax
0x18000dbc3  jz      loc_18000EEB9
0x18000dbc9  mov     [rbp+790h+var_728], rbx
0x18000dbcd  cmp     [rbp+790h+psz], 5Ch ; '\'
0x18000dbd5  jnz     loc_18000F413
0x18000dbdb  lea     rax, [rbp+790h+var_24E]
0x18000dbe2  mov     [rbp+790h+var_740], rax
0x18000dbe6  cmp     word ptr [rax], 0
0x18000dbea  jz      loc_18000DD73
0x18000dbf0  xor     edx, edx; dwFlags
0x18000dbf2  mov     r8d, 18h; dwBytes
0x18000dbf8  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000dbff  call    cs:__imp_HeapAlloc
0x18000dc06  nop     dword ptr [rax+rax+00h]
0x18000dc0b  mov     rsi, rax
0x18000dc0e  test    rax, rax
0x18000dc11  jz      loc_18000F6B1
0x18000dc17  mov     qword ptr [rbp+790h+PrivilegeSetLength], rax
0x18000dc1b  xor     r13d, r13d
0x18000dc1e  mov     [rax+8], r13
0x18000dc22  mov     dword ptr [rax+10h], 1
0x18000dc29  lea     rcx, asc_1800A7EC0; "\\"
0x18000dc30  call    cs:__imp_SysAllocString
0x18000dc37  nop     dword ptr [rax+rax+00h]
0x18000dc3c  mov     [rsi], rax
0x18000dc3f  test    rax, rax
0x18000dc42  jz      loc_18000F2A1
0x18000dc48  mov     qword ptr [rbp+790h+PrivilegeSetLength], rsi
0x18000dc4c  xor     edx, edx; dwFlags
0x18000dc4e  mov     r8d, 18h; dwBytes
0x18000dc54  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000dc5b  call    cs:__imp_HeapAlloc
0x18000dc62  nop     dword ptr [rax+rax+00h]
0x18000dc67  mov     r12, rax
0x18000dc6a  test    rax, rax
0x18000dc6d  jz      loc_18000F6F5
0x18000dc73  mov     qword ptr [rbp+790h+GenericMapping.GenericRead], rax
0x18000dc7a  mov     [rax+8], r13
0x18000dc7e  mov     dword ptr [rax+10h], 1
0x18000dc85  mov     rcx, [rbx]; pbstr
0x18000dc88  test    rcx, rcx
0x18000dc8b  jz      loc_18000F737
0x18000dc91  call    cs:__imp_SysStringLen
0x18000dc98  nop     dword ptr [rax+rax+00h]
0x18000dc9d  mov     [rbp+790h+Type], eax
0x18000dca0  mov     rcx, [rsi]; pbstr
0x18000dca3  test    rcx, rcx
0x18000dca6  jz      loc_18000F73F
0x18000dcac  call    cs:__imp_SysStringLen
0x18000dcb3  nop     dword ptr [rax+rax+00h]
0x18000dcb8  mov     ecx, eax
0x18000dcba  mov     eax, [rbp+790h+Type]
0x18000dcbd  mov     [rbp+790h+cbData], ecx
0x18000dcc0  lea     r13d, [rcx+rax]
0x18000dcc4  cmp     r13d, eax
0x18000dcc7  jb      short loc_18000DCDD
0x18000dcc9  mov     edx, r13d
0x18000dccc  add     rdx, rdx; struct IErrorInfo *
0x18000dccf  mov     eax, 0FFFFFFFFh
0x18000dcd4  cmp     rdx, rax
0x18000dcd7  jbe     loc_18000F0E2
0x18000dcdd  mov     ecx, 8007000Eh; int
0x18000dce2  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000dce8  xor     ecx, ecx; psz
0x18000dcea  call    cs:__imp_SysAllocStringByteLen
0x18000dcf1  nop     dword ptr [rax+rax+00h]
0x18000dcf6  mov     rcx, rax; void *
0x18000dcf9  mov     [rbx], rax
0x18000dcfc  test    rax, rax
0x18000dcff  jz      loc_18000F300
0x18000dd05  mov     rdx, [r12]; Src
0x18000dd09  mov     r13d, [rbp+790h+Type]
0x18000dd0d  test    rdx, rdx
0x18000dd10  jz      short loc_18000DD1E
0x18000dd12  lea     r8d, [r13+1]
0x18000dd16  add     r8, r8; Size
0x18000dd19  call    memcpy_0
0x18000dd1e  mov     rdx, [rsi]; Src
0x18000dd21  test    rdx, rdx
0x18000dd24  jz      short loc_18000DD40
0x18000dd26  mov     r8d, [rbp+790h+cbData]
0x18000dd2a  inc     r8d
0x18000dd2d  add     r8, r8; Size
0x18000dd30  mov     ecx, r13d
0x18000dd33  mov     rax, [rbx]
0x18000dd36  lea     rcx, [rax+rcx*2]; void *
0x18000dd3a  call    memcpy_0
0x18000dd3f  nop
0x18000dd40  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000dd47  mov     eax, ecx
0x18000dd49  lock xadd [r12+10h], eax
0x18000dd50  cmp     eax, 1
0x18000dd53  jz      loc_18000F32E
0x18000dd59  mov     eax, ecx
0x18000dd5b  lock xadd [rsi+10h], eax
0x18000dd60  cmp     eax, 1
0x18000dd63  jz      loc_18000F342
0x18000dd69  xor     esi, esi
0x18000dd6b  mov     r13, [rbp+790h+var_7B0]
0x18000dd6f  mov     r12, [rbp+790h+var_780]
  ... truncated ...
```
