# RpcServer::RetrieveTask(ushort const *,ushort const *,ulong *,ushort * *)

- ea: `0x180009010`
- end: `0x18000b431`
- name: `?RetrieveTask@RpcServer@@QEAAJPEBG0PEAKPEAPEAG@Z`
- size: `9249`
- prototype: `__int64 __fastcall(RpcServer *this, OLECHAR *, const unsigned __int16 *, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180008140`

## callees

- `0x180007ddc`
- `0x180007ec0`
- `0x180008318`
- `0x180008330`
- `0x180008660`
- `0x1800086c0`
- `0x180008720`
- `0x180009010`
- `0x18000b438`
- `0x18000b4e0`
- `0x18000c3c0`
- `0x18000e468`
- `0x18000f6a8`
- `0x18000fa4c`
- `0x18001a260`
- `0x18001acb0`
- `0x18001b070`
- `0x180022600`
- `0x180025040`
- `0x180033b00`
- `0x180039b6c`
- `0x180039d00`
- `0x18003fa50`
- `0x180042cec`
- `0x180052118`
- `0x18005248c`
- `0x18005250c`
- `0x18005790c`
- `0x180057926`
- `0x180066c8c`
- `0x18006ae24`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800092fc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000936f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800097b6`
- `OLEAUT32!__imp_SysAllocString` at `0x180009809`
- `OLEAUT32!__imp_SysAllocString` at `0x180009c07`
- `OLEAUT32!__imp_SysAllocString` at `0x180009c5a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a864`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ab6e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000abed`
- `OLEAUT32!__imp_SysAllocString` at `0x1800092fc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000936f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800097b6`
- `OLEAUT32!__imp_SysAllocString` at `0x180009809`
- `OLEAUT32!__imp_SysAllocString` at `0x180009c07`
- `OLEAUT32!__imp_SysAllocString` at `0x180009c5a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a864`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ab6e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000abed`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180009fc0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180009fc0`
- `OLEAUT32!__imp_SysFreeString` at `0x180009fd4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a04c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a0cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a0d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a403`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a5b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a5e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a61e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a653`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a688`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a72f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a768`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b062`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b361`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b399`
- `OLEAUT32!__imp_SysFreeString` at `0x180009fd4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a04c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a0cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a0d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a403`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a5b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a5e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a61e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a653`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a688`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a6f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a72f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a768`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b062`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b361`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b399`
- `OLEAUT32!__imp_SysStringLen` at `0x1800093c4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800093d9`
- `OLEAUT32!__imp_SysStringLen` at `0x18000986e`
- `OLEAUT32!__imp_SysStringLen` at `0x180009883`
- `OLEAUT32!__imp_SysStringLen` at `0x180009cbf`
- `OLEAUT32!__imp_SysStringLen` at `0x180009cd4`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a0ea`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a8be`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a8cf`
- `OLEAUT32!__imp_SysStringLen` at `0x1800093c4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800093d9`
- `OLEAUT32!__imp_SysStringLen` at `0x18000986e`
- `OLEAUT32!__imp_SysStringLen` at `0x180009883`
- `OLEAUT32!__imp_SysStringLen` at `0x180009cbf`
- `OLEAUT32!__imp_SysStringLen` at `0x180009cd4`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a0ea`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a8be`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a8cf`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180009411`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800098b1`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180009d03`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a7ab`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180009411`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800098b1`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180009d03`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000a7ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac12`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009e08`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009e16`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009e08`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009e16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000963b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a48e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000963b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a48e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009296`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009296`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009626`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a479`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b082`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b382`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009626`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a479`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b082`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b382`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000956e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800095c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000956e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800095c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009535`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000960a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009535`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000960a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a373`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a41c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a56c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a58d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a60b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a640`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a6aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a6e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a71c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a78e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a373`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a41c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a56c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a58d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a60b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a640`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a6aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a6e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a71c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a78e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800092d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009344`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009394`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000978b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800097de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009831`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009bdc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a115`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a838`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a88c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ab43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abc2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800092d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009344`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009394`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000978b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800097de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009831`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009bdc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a115`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a838`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a88c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ab43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000925c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000925c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009274`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009274`
- `RPCRT4!RpcImpersonateClient` at `0x18000924c`
- `RPCRT4!RpcImpersonateClient` at `0x180009f81`
- `RPCRT4!RpcImpersonateClient` at `0x18000924c`
- `RPCRT4!RpcImpersonateClient` at `0x180009f81`
- `RPCRT4!RpcRevertToSelf` at `0x180009282`
- `RPCRT4!RpcRevertToSelf` at `0x180009fae`
- `RPCRT4!RpcRevertToSelf` at `0x18000ac27`
- `RPCRT4!RpcRevertToSelf` at `0x18000b316`
- `RPCRT4!RpcRevertToSelf` at `0x180009282`
- `RPCRT4!RpcRevertToSelf` at `0x180009fae`
- `RPCRT4!RpcRevertToSelf` at `0x18000ac27`
- `RPCRT4!RpcRevertToSelf` at `0x18000b316`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000961c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800096b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae74`

## string_xrefs

- `0x1800097af`: `NT TASK`
- `0x180009c00`: `NT TASK`
- `0x18000ab67`: `NT TASK\`
- `0x18000abe6`: `NT TASK\`
- `0x1800092f5`: `TaskCache\Tree`
- `0x18000b2e7`: `RpcServer::RetrieveTask`
- `0x18000ac91`: `RetrieveTask`

## pseudocode

```c
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
  _bstr_t::Data_t *v77; // rsi
  UINT v78; // r15d
  UINT v79; // r12d
  UINT v80; // edi
  struct IErrorInfo *v81; // rdx
  BSTR v82; // rcx
  _bstr_t::Data_t *v83; // rdi
  BSTR v84; // rax
  OLECHAR j; // cx
  int v86; // ebx
  OLECHAR *v87; // rsi
  LPVOID v88; // rdi
  __int64 v89; // rbx
  StringStream *v90; // rcx
  __int64 v91; // rcx
  struct IErrorInfo *v92; // rdx
  int v93; // ebx
  User::UserEntry *v94; // rdi
  User::UserEntry *v95; // r15
  TaskXmlReader *v96; // rax
  TaskXmlReader *v97; // rbx
  int v98; // edx
  int v99; // r8d
  JobBucket *v100; // rax
  JobBucket *v101; // rax
  unsigned int v102; // edx
  JobBucket *v103; // rbx
  JobBucket *v104; // rcx
  _bstr_t::Data_t *v105; // rcx
  _bstr_t::Data_t *v106; // rax
  _bstr_t::Data_t *v107; // rbx
  BSTR v108; // rax
  struct IErrorInfo *v109; // rdx
  BSTR *v110; // rax
  BSTR *v111; // rbx
  BSTR v112; // rax
  struct IErrorInfo *v113; // rdx
  _bstr_t::Data_t *v114; // rax
  struct IErrorInfo *v115; // rdx
  _bstr_t::Data_t *v116; // r12
  UINT v117; // r15d
  UINT v118; // eax
  UINT v119; // r13d
  struct IErrorInfo *v120; // rdx
  BSTR v121; // rcx
  _bstr_t::Data_t *v122; // r15
  BSTR v123; // rax
  OLECHAR k; // cx
  __int64 v125; // rcx
  _QWORD *v126; // rax
  void (__fastcall ***v127)(_QWORD, __int64); // rcx
  _QWORD *m; // rbx
  void **v129; // r8
  void **v130; // rbx
  void **v131; // rax
  void **v132; // r8
  void **n; // rbx
  RPC_STATUS v134; // eax
  EventManager *v135; // rcx
  unsigned int v136; // ebx
  __int64 v137; // rbx
  OLECHAR *v138; // r12
  OLECHAR *v139; // r13
  unsigned __int64 v140; // r10
  __int64 v141; // r11
  __int64 v142; // r15
  unsigned __int64 v143; // rcx
  OLECHAR *v144; // rdx
  unsigned __int64 v145; // r9
  OLECHAR *v146; // r8
  OLECHAR v147; // ax
  __int64 v148; // rax
  void (__fastcall ***v149)(_QWORD, __int64); // rcx
  UINT v150; // eax
  _WORD **v151; // rdx
  unsigned __int64 v152; // rbx
  SIZE_T v153; // rax
  unsigned __int16 *v154; // rax
  _WORD *v155; // rcx
  __int16 v156; // ax
  unsigned int v157; // edx
  _bstr_t::Data_t *v158; // rcx
  BSTR *v159; // rbx
  BSTR *v160; // rbx
  void ***v161; // rax
  void ***ii; // rbx
  void **v163; // r8
  BSTR *v164; // rbx
  void ***v165; // rax
  void ***jj; // rbx
  void **v167; // r8
  void **v168; // rbx
  void (__fastcall ***v169)(_QWORD, __int64); // rcx
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
  void *v184; // rcx
  BSTR v185; // rcx
  void *v186; // rcx
  BSTR v187; // rcx
  struct IErrorInfo *v188; // rdx
  BSTR v189; // rcx
  volatile signed __int32 *v190; // rax
  volatile signed __int32 *v191; // rsi
  BSTR v192; // rax
  struct IErrorInfo *v193; // rdx
  OLECHAR *v194; // rax
  struct IErrorInfo *v195; // rdx
  UINT v196; // eax
  OLECHAR *v197; // rcx
  UINT v198; // r13d
  __int64 v199; // rax
  const OLECHAR *v200; // r10
  __int64 v201; // rdx
  OLECHAR *p_psz; // rcx
  OLECHAR v203; // r8
  _bstr_t::Data_t *v204; // rcx
  _bstr_t::Data_t *v205; // rax
  BSTR v206; // rax
  struct IErrorInfo *v207; // rdx
  _bstr_t::Data_t *v208; // rcx
  _bstr_t::Data_t *v209; // rax
  BSTR v210; // rax
  struct IErrorInfo *v211; // rdx
  signed int LastError; // eax
  signed int v213; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  const struct _GUID *lpcbData; // [rsp+28h] [rbp-D8h]
  const struct _GUID *lpcbDataa; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  void **pExceptionObject; // [rsp+88h] [rbp-78h] BYREF
  char v220; // [rsp+90h] [rbp-70h]
  const unsigned __int16 *v221; // [rsp+98h] [rbp-68h]
  __int64 v222; // [rsp+A0h] [rbp-60h]
  __int64 v223; // [rsp+A8h] [rbp-58h]
  int v224; // [rsp+B0h] [rbp-50h]
  __int64 v225; // [rsp+B4h] [rbp-4Ch]
  DWORD Type[2]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD PrivilegeSetLength[2]; // [rsp+C8h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+D0h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+D8h] [rbp-28h] BYREF
  User::UserEntry *v230; // [rsp+E0h] [rbp-20h] BYREF
  BYTE *v231; // [rsp+E8h] [rbp-18h] BYREF
  DWORD v232; // [rsp+F0h] [rbp-10h]
  LPVOID lpMem; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v234; // [rsp+100h] [rbp+0h]
  LPVOID v235; // [rsp+108h] [rbp+8h]
  char v236; // [rsp+110h] [rbp+10h] BYREF
  int v237; // [rsp+111h] [rbp+11h]
  __int16 v238; // [rsp+115h] [rbp+15h]
  char v239; // [rsp+117h] [rbp+17h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+118h] [rbp+18h] BYREF
  char v241; // [rsp+120h] [rbp+20h]
  int v242; // [rsp+121h] [rbp+21h]
  __int16 v243; // [rsp+125h] [rbp+25h]
  char v244; // [rsp+127h] [rbp+27h]
  struct _FILETIME v245; // [rsp+128h] [rbp+28h] BYREF
  LPVOID v246[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v247; // [rsp+140h] [rbp+40h]
  TaskXmlReader *v248; // [rsp+148h] [rbp+48h]
  OLECHAR *v249; // [rsp+150h] [rbp+50h]
  unsigned int *v250; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v251; // [rsp+160h] [rbp+60h] BYREF
  OLECHAR *v252; // [rsp+168h] [rbp+68h]
  _bstr_t::Data_t *v253; // [rsp+170h] [rbp+70h]
  unsigned __int16 **v254; // [rsp+178h] [rbp+78h]
  RTL_SRWLOCK *v255; // [rsp+180h] [rbp+80h]
  _GENERIC_MAPPING GenericMapping; // [rsp+188h] [rbp+88h] BYREF
  GUID v257; // [rsp+198h] [rbp+98h] BYREF
  _bstr_t::Data_t *v258; // [rsp+1A8h] [rbp+A8h]
  BSTR v259; // [rsp+1B0h] [rbp+B0h]
  JobBucket *v260; // [rsp+1B8h] [rbp+B8h]
  GUID v261; // [rsp+1C0h] [rbp+C0h] BYREF
  _bstr_t::Data_t *v262; // [rsp+1D0h] [rbp+D0h]
  BSTR v263; // [rsp+1D8h] [rbp+D8h]
  JobBucket *v264; // [rsp+1E0h] [rbp+E0h]
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v266[520]; // [rsp+200h] [rbp+100h] BYREF
  char v267[24]; // [rsp+408h] [rbp+308h] BYREF
  char v268[240]; // [rsp+420h] [rbp+320h] BYREF
  char v269[24]; // [rsp+510h] [rbp+410h] BYREF
  LPVOID v270; // [rsp+528h] [rbp+428h]
  LPVOID v271; // [rsp+530h] [rbp+430h]
  _bstr_t::Data_t *v272; // [rsp+5E0h] [rbp+4E0h]
  char v273[8]; // [rsp+618h] [rbp+518h] BYREF
  __int64 v274; // [rsp+620h] [rbp+520h]
  __int64 v275; // [rsp+628h] [rbp+528h]
  OLECHAR psz; // [rsp+640h] [rbp+540h] BYREF
  __int16 v277; // [rsp+642h] [rbp+542h] BYREF

  v250 = a4;
  v251 = a3;
  v254 = a5;
  if ( a5 )
    *a5 = 0;
  memset_0(&psz, 0, 0x20Au);
  if ( !a2 || !*a2 )
  {
    v199 = 2147483646;
    v200 = L"\\";
    v201 = 261;
    p_psz = &psz;
    v11 = 0;
    do
    {
      if ( !v199 )
        goto LABEL_42;
      v203 = *v200;
      if ( !*v200 )
        goto LABEL_42;
      ++v200;
      *p_psz++ = v203;
      --v199;
      --v201;
    }
    while ( v201 );
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
  if ( !psz || !v277 && psz == 92 )
    return 2147942487LL;
  TokenHandle = 0;
  v25 = RpcImpersonateClient(0);
  v27 = v25;
  if ( v25 )
  {
    EventManager::EvtReport(v26, &IMPERSONATION_FAILURE, L"RetrieveTask", v25, phkResult, lpcbData);
    v220 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v221 = &qword_1800A4718;
    v222 = 0;
    v223 = 0;
    v224 = v27;
    v225 = -1;
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
    v213 = LastError;
    if ( LastError > 0 )
      v213 = (unsigned __int16)LastError | 0x80070000;
    RpcRevertToSelf();
    if ( v213 < 0 )
    {
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      return (unsigned int)v213;
    }
  }
  v29 = (RTL_SRWLOCK *)((char *)this + 16);
  v255 = v29;
  AcquireSRWLockShared(v29);
  v30 = JobStore::m_pCommonStore;
  v230 = JobStore::m_pCommonStore;
  v31 = TokenHandle;
  v248 = (TaskXmlReader *)TokenHandle;
  v32 = 0;
  v231 = 0;
  v232 = 0;
  v33 = 0;
  v253 = 0;
  hKey = 0;
  v34 = (OLECHAR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
  v35 = v34;
  if ( !v34 )
  {
    v220 = 0;
    v221 = &qword_1800A4718;
    v222 = 0;
    v223 = 0;
    v224 = 14;
    v225 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v252 = v34;
  *((_QWORD *)v34 + 1) = 0;
  *((_DWORD *)v34 + 4) = 1;
  v36 = SysAllocString(L"TaskCache\\Tree");
  *(_QWORD *)v35 = v36;
  if ( !v36 )
    _com_raise_error(-2147024882, v37);
  v252 = v35;
  if ( psz == 92 )
    v38 = (OLECHAR *)&v277;
  else
    v38 = &psz;
  v249 = v38;
  if ( *v38 )
  {
    v39 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v40 = v39;
    if ( !v39 )
    {
      v220 = 0;
      v221 = &qword_1800A4718;
      v222 = 0;
      v223 = 0;
      v224 = 14;
      v225 = -1;
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
      v220 = 0;
      v221 = &qword_1800A4718;
      v222 = 0;
      v223 = 0;
      v224 = 14;
      v225 = -1;
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
    v189 = SysAllocStringByteLen(0, (UINT)v44);
    *v45 = v189;
    if ( v189 )
    {
      if ( *(_QWORD *)v35 )
        memcpy_0(v189, *(const void **)v35, 2LL * (Type[0] + 1));
      v188 = (struct IErrorInfo *)*v40;
      if ( *v40 )
        memcpy_0(&(*v45)[Type[0]], v188, 2LL * (cbData + 1));
    }
    else if ( v48 )
    {
      _com_raise_error(-2147024882, v188);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v35, (unsigned int)v188);
    v252 = (OLECHAR *)v45;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v40 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v40, (unsigned int)v188);
    v190 = (volatile signed __int32 *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v191 = v190;
    if ( !v190 )
    {
      v220 = 0;
      v221 = &qword_1800A4718;
      v222 = 0;
      v223 = 0;
      v224 = 14;
      v225 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    *(_QWORD *)&GenericMapping.GenericRead = v190;
    *((_QWORD *)v190 + 1) = 0;
    *((_DWORD *)v190 + 4) = 1;
    v192 = SysAllocString(v249);
    *(_QWORD *)v191 = v192;
    if ( !v192 )
      _com_raise_error(-2147024882, v193);
    *(_QWORD *)&GenericMapping.GenericRead = v191;
    v194 = (OLECHAR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v35 = v194;
    if ( !v194 )
    {
      v220 = 0;
      v221 = &qword_1800A4718;
      v222 = 0;
      v223 = 0;
      v224 = 14;
      v225 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v249 = v194;
    *((_QWORD *)v194 + 1) = 0;
    *((_DWORD *)v194 + 4) = 1;
    if ( *v45 )
      v196 = SysStringLen(*v45);
    else
      v196 = 0;
    Type[0] = v196;
    v197 = *(OLECHAR **)v191;
    if ( *(_QWORD *)v191 )
    {
      LODWORD(v197) = SysStringLen(v197);
      v196 = Type[0];
    }
    cbData = (unsigned int)v197;
    v198 = (_DWORD)v197 + v196;
    if ( (unsigned int)v197 + v196 < v196
      || (v195 = (struct IErrorInfo *)(2LL * v198), (unsigned __int64)v195 > 0xFFFFFFFF) )
    {
      _com_raise_error(-2147024882, v195);
    }
    v50 = SysAllocStringByteLen(0, (UINT)v195);
    *(_QWORD *)v35 = v50;
    if ( v50 )
    {
      if ( *v45 )
        memcpy_0(v50, *v45, 2LL * (Type[0] + 1));
      v49 = *(struct IErrorInfo **)v191;
      if ( *(_QWORD *)v191 )
        memcpy_0((void *)(*(_QWORD *)v35 + 2LL * Type[0]), v49, 2LL * (cbData + 1));
    }
    else if ( v198 )
    {
      _com_raise_error(-2147024882, v49);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v45 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v45, (unsigned int)v49);
    if ( _InterlockedExchangeAdd(v191 + 4, 0xFFFFFFFF) == 1 )
      _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v191, (unsigned int)v49);
    v30 = v230;
    v31 = v248;
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
        goto LABEL_448;
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
          v231 = v57;
          v232 = cbData;
LABEL_100:
          v54 = 0;
          goto LABEL_101;
        }
LABEL_448:
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
      goto LABEL_403;
    if ( !v32 )
      goto LABEL_403;
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
LABEL_403:
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v231);
      v54 = -2147024891;
      goto LABEL_106;
    }
    LocalFree(v32);
    v258 = 0;
    v260 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v59, v60, (unsigned int)&v257, (__int64)&psz, 0);
    }
    v61 = (JobBucket *)HeapAlloc(g_PrivateHeap, 0, 0xD8u);
    if ( !v61 )
    {
      v220 = 0;
      v221 = &qword_1800A4718;
      v222 = 0;
      v223 = 0;
      v224 = 14;
      v225 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v62 = JobBucket::JobBucket(v61);
    v64 = v62;
    if ( v62 )
      _InterlockedIncrement((volatile signed __int32 *)v62 + 2);
    v65 = v260;
    if ( v260 && _InterlockedExchangeAdd((volatile signed __int32 *)v260 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(JobBucket *, __int64))v65)(v65, 1);
    v260 = v64;
    if ( psz == 92 || psz == 47 )
    {
      v66 = v258;
      if ( v258 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v258 + 4, 0xFFFFFFFF) == 1 )
          _bstr_t::Data_t::`scalar deleting destructor'(v66, v63);
        v258 = 0;
      }
      v67 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v68 = v67;
      if ( !v67 )
      {
        v220 = 0;
        v221 = &qword_1800A4718;
        v222 = 0;
        v223 = 0;
        v224 = 14;
        v225 = -1;
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
      v204 = v258;
      if ( v258 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v258 + 4, 0xFFFFFFFF) == 1 )
          _bstr_t::Data_t::`scalar deleting destructor'(v204, v63);
        v258 = 0;
      }
      v205 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v68 = v205;
      if ( !v205 )
      {
        v220 = 0;
        v221 = &qword_1800A4718;
        v222 = 0;
        v223 = 0;
        v224 = 14;
        v225 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      *(_QWORD *)&GenericMapping.GenericRead = v205;
      *((_QWORD *)v205 + 1) = 0;
      *((_DWORD *)v205 + 4) = 1;
      v206 = SysAllocString(L"NT TASK\\");
      *(_QWORD *)v68 = v206;
      if ( !v206 )
        _com_raise_error(-2147024882, v207);
    }
    v258 = v68;
    v71 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
    v72 = v71;
    if ( !v71 )
    {
      v220 = 0;
      v221 = &qword_1800A4718;
      v222 = 0;
      v223 = 0;
      v224 = 14;
      v225 = -1;
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
      v220 = 0;
      v221 = &qword_1800A4718;
      v222 = 0;
      v223 = 0;
      v224 = 14;
      v225 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    v253 = v75;
    *((_QWORD *)v75 + 1) = 0;
    *((_DWORD *)v75 + 4) = 1;
    if ( v258 && *(_QWORD *)v258 )
      v78 = SysStringLen(*(BSTR *)v258);
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
      if ( v258 && *(_QWORD *)v258 )
        memcpy_0(v82, *(const void **)v258, 2LL * (v78 + 1));
      if ( *v72 )
        memcpy_0((void *)(*(_QWORD *)v77 + 2LL * v78), *v72, 2LL * (v79 + 1));
    }
    else if ( v80 )
    {
      _com_raise_error(-2147024882, v81);
    }
    v83 = v258;
    if ( v258 && _InterlockedExchangeAdd((volatile signed __int32 *)v258 + 4, 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v83 )
      {
        SysFreeString(*(BSTR *)v83);
        *(_QWORD *)v83 = 0;
      }
      v184 = (void *)*((_QWORD *)v83 + 1);
      if ( v184 )
      {
        operator delete(v184);
        *((_QWORD *)v83 + 1) = 0;
      }
      HeapFree(g_PrivateHeap, 0, v83);
    }
    v258 = v77;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v72 + 4, 0xFFFFFFFF) == 1 )
    {
      if ( *v72 )
      {
        SysFreeString(*v72);
        *v72 = 0;
      }
      v185 = v72[1];
      if ( v185 )
      {
        operator delete(v185);
        v72[1] = 0;
      }
      HeapFree(g_PrivateHeap, 0, v72);
    }
    if ( v258 )
      v84 = *(BSTR *)v258;
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
      v259 = ++v84;
    }
    v257 = GUID_NULL;
    *((_DWORD *)v260 + 15) = 0;
    *(_QWORD *)Type = 0;
    v86 = JobStore::GenerateTaskXmlFromRegistry(v30, &v257, v251, v250, Type);
    if ( v86 >= 0 )
    {
      v87 = 0;
      v250 = 0;
      hKey = 0;
      v88 = *(LPVOID *)Type;
      if ( !*(_QWORD *)Type )
      {
        ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&hKey);
        SysFreeString(0);
        operator delete(0);
        JobMoniker::~JobMoniker((JobMoniker *)&v257);
        ReleaseSRWLockShared(v29);
        wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
        return 2147942487LL;
      }
      v89 = -1;
      do
        ++v89;
      while ( *(_WORD *)(*(_QWORD *)Type + 2 * v89) );
      v90 = (StringStream *)HeapAlloc(g_PrivateHeap, 0, 0x28u);
      if ( !v90 )
      {
        v220 = 0;
        v221 = &qword_1800A4718;
        v222 = 0;
        v223 = 0;
        v224 = 14;
        v225 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      StringStream::StringStream(v90);
      *(_QWORD *)v91 = &StringReader::`vftable';
      *(_QWORD *)(v91 + 16) = -1;
      *(_DWORD *)(v91 + 24) = v89;
      *(_QWORD *)(v91 + 32) = v88;
      v230 = 0;
      v93 = ((__int64 (__fastcall *)(__int64, GUID *, User::UserEntry **))StringReader::`vftable')(
              v91,
              &GUID_0000000c_0000_0000_c000_000000000046,
              &v230);
      if ( v93 < 0 )
      {
        ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&hKey);
        v94 = 0;
        hKey = 0;
        v95 = 0;
      }
      else
      {
        v94 = v230;
        hKey = (HKEY)v230;
        v95 = v230;
      }
      if ( (int)(v93 + 0x80000000) >= 0 && v93 != -2147467262 )
        _com_raise_error(v93, v92);
      if ( !v95 )
      {
        v220 = 0;
        v221 = &qword_1800A4718;
        v222 = 0;
        v223 = 0;
        v224 = 14;
        v225 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v96 = (TaskXmlReader *)HeapAlloc(g_PrivateHeap, 0, 0x460u);
      v97 = v96;
      v248 = v96;
      if ( !v96 )
      {
        v220 = 0;
        v221 = &qword_1800A4718;
        v222 = 0;
        v223 = 0;
        v224 = 14;
        v225 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      *(_QWORD *)v96 = &wmi::RefBase::`vftable';
      *((_DWORD *)v96 + 2) = 0;
      *(_QWORD *)v96 = &TaskXmlReader::`vftable';
      *((_QWORD *)v96 + 2) = 0;
      *((_QWORD *)v96 + 3) = 0;
      *((_QWORD *)v96 + 4) = v95;
      (*(void (__fastcall **)(User::UserEntry *))(*(_QWORD *)v95 + 8LL))(v95);
      *((_BYTE *)v97 + 40) = 0;
      *((_QWORD *)v97 + 6) = 0;
      *((_QWORD *)v97 + 7) = 0;
      *((_BYTE *)v97 + 1106) &= 0xFCu;
      *((_DWORD *)v97 + 16) = 0;
      *((_QWORD *)v97 + 9) = 0;
      *((_WORD *)v97 + 40) = 0;
      *((_BYTE *)v97 + 1112) = 0;
      *((_DWORD *)v97 + 279) = 65542;
      v251 = (const unsigned __int16 *)v97;
      _InterlockedIncrement((volatile signed __int32 *)v97 + 2);
      v262 = 0;
      v264 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v98, v99, (unsigned int)&v261, (__int64)&psz, 0);
      }
      v100 = (JobBucket *)HeapAlloc(g_PrivateHeap, 0, 0xD8u);
      if ( !v100 )
      {
        v220 = 0;
        v221 = &qword_1800A4718;
        v222 = 0;
        v223 = 0;
        v224 = 14;
        v225 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v101 = JobBucket::JobBucket(v100);
      v103 = v101;
      if ( v101 )
        _InterlockedIncrement((volatile signed __int32 *)v101 + 2);
      v104 = v264;
      if ( v264 )
      {
        v102 = _InterlockedExchangeAdd((volatile signed __int32 *)v264 + 2, 0xFFFFFFFF);
        if ( v102 == 1 )
          (**(void (__fastcall ***)(JobBucket *))v104)(v104);
      }
      v264 = v103;
      if ( psz == 92 || psz == 47 )
      {
        v105 = v262;
        if ( v262 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v262 + 4, 0xFFFFFFFF) == 1 )
            _bstr_t::Data_t::`scalar deleting destructor'(v105, v102);
          v262 = 0;
        }
        v106 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
        v107 = v106;
        if ( !v106 )
        {
          v220 = 0;
          v221 = &qword_1800A4718;
          v222 = 0;
          v223 = 0;
          v224 = 14;
          v225 = -1;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::OutOfMemoryException *)&pExceptionObject;
        }
        *(_QWORD *)&GenericMapping.GenericRead = v106;
        *((_QWORD *)v106 + 1) = 0;
        *((_DWORD *)v106 + 4) = 1;
        v108 = SysAllocString(L"NT TASK");
        *(_QWORD *)v107 = v108;
        if ( !v108 )
          _com_raise_error(-2147024882, v109);
      }
      else
      {
        v208 = v262;
        if ( v262 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v262 + 4, 0xFFFFFFFF) == 1 )
            _bstr_t::Data_t::`scalar deleting destructor'(v208, v102);
          v262 = 0;
        }
        v209 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
        v107 = v209;
        if ( !v209 )
        {
          v220 = 0;
          v221 = &qword_1800A4718;
          v222 = 0;
          v223 = 0;
          v224 = 14;
          v225 = -1;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::OutOfMemoryException *)&pExceptionObject;
        }
        *(_QWORD *)&GenericMapping.GenericRead = v209;
        *((_QWORD *)v209 + 1) = 0;
        *((_DWORD *)v209 + 4) = 1;
        v210 = SysAllocString(L"NT TASK\\");
        *(_QWORD *)v107 = v210;
        if ( !v210 )
          _com_raise_error(-2147024882, v211);
      }
      v262 = v107;
      v110 = (BSTR *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v111 = v110;
      if ( !v110 )
      {
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)&pExceptionObject);
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      *(_QWORD *)&GenericMapping.GenericRead = v110;
      v110[1] = 0;
      *((_DWORD *)v110 + 4) = 1;
      v112 = SysAllocString(&psz);
      *v111 = v112;
      if ( !v112 )
        _com_raise_error(-2147024882, v113);
      *(_QWORD *)&GenericMapping.GenericRead = v111;
      v114 = (_bstr_t::Data_t *)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v116 = v114;
      if ( !v114 )
      {
        wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)&pExceptionObject);
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v253 = v114;
      *((_QWORD *)v114 + 1) = 0;
      *((_DWORD *)v114 + 4) = 1;
      if ( v262 && *(_QWORD *)v262 )
        v117 = SysStringLen(*(BSTR *)v262);
      else
        v117 = 0;
      if ( *v111 )
        v118 = SysStringLen(*v111);
      else
        v118 = 0;
      cbData = v118;
      v119 = v118 + v117;
      if ( v118 + v117 < v117 || (v115 = (struct IErrorInfo *)(2LL * v119), (unsigned __int64)v115 > 0xFFFFFFFF) )
        _com_raise_error(-2147024882, v115);
      v121 = SysAllocStringByteLen(0, (UINT)v115);
      *(_QWORD *)v116 = v121;
      if ( v121 )
      {
        if ( v262 && *(_QWORD *)v262 )
          memcpy_0(v121, *(const void **)v262, 2LL * (v117 + 1));
        if ( *v111 )
          memcpy_0((void *)(*(_QWORD *)v116 + 2LL * v117), *v111, 2LL * (cbData + 1));
      }
      else if ( v119 )
      {
        _com_raise_error(-2147024882, v120);
      }
      v122 = v262;
      if ( v262 && _InterlockedExchangeAdd((volatile signed __int32 *)v262 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)v122 )
        {
          SysFreeString(*(BSTR *)v122);
          *(_QWORD *)v122 = 0;
        }
        v186 = (void *)*((_QWORD *)v122 + 1);
        if ( v186 )
        {
          operator delete(v186);
          *((_QWORD *)v122 + 1) = 0;
        }
        HeapFree(g_PrivateHeap, 0, v122);
      }
      v262 = v116;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v111 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *v111 )
        {
          SysFreeString(*v111);
          *v111 = 0;
        }
        v187 = v111[1];
        if ( v187 )
        {
          operator delete(v187);
          v111[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v111);
      }
      if ( v262 )
        v123 = *(BSTR *)v262;
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
        v263 = ++v123;
      }
      v261 = GUID_NULL;
      *((_DWORD *)v264 + 15) = 0;
      v236 = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v241 = 0;
      GetSystemTimeAsFileTime(&v245);
      *(_OWORD *)v246 = 0;
      v126 = (_QWORD *)std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v125, 0, 0);
      v246[0] = v126;
      v247 = 0;
      if ( v246[1] )
      {
        for ( m = (_QWORD *)*v126; m != v126; m = (_QWORD *)*m )
        {
          v127 = (void (__fastcall ***)(_QWORD, __int64))m[2];
          if ( v127 )
          {
            (**v127)(v127, 1);
            m[2] = 0;
            v126 = v246[0];
          }
        }
        v129 = (void **)*v126;
        *v126 = v126;
        *((LPVOID *)v246[0] + 1) = v246[0];
        v246[1] = 0;
        if ( v129 != v246[0] )
        {
          do
          {
            v130 = (void **)*v129;
            HeapFree(g_PrivateHeap, 0, v129);
            v129 = v130;
          }
          while ( v130 != v246[0] );
        }
      }
      v236 = 0;
      v237 = *(_DWORD *)((char *)&v231 + 1);
      v238 = *(_WORD *)((char *)&v231 + 5);
      v239 = HIBYTE(v231);
      SystemTimeAsFileTime = (struct _FILETIME)-1LL;
      v241 = 0;
      v242 = *(_DWORD *)((char *)&v231 + 1);
      v243 = *(_WORD *)((char *)&v231 + 5);
      v244 = HIBYTE(v231);
      v245 = 0;
      lpMem = 0;
      v234 = 0;
      v131 = (void **)std::_List_alloc<0,std::_List_base_types<Triggers::Trigger *>>::_Buynode0(v127, 0, 0);
      lpMem = v131;
      v235 = 0;
      if ( v234 )
      {
        for ( n = (void **)*v131; n != v131; n = (void **)*n )
        {
          v149 = (void (__fastcall ***)(_QWORD, __int64))n[2];
          if ( v149 )
          {
            (**v149)(v149, 1);
            n[2] = 0;
            v131 = (void **)lpMem;
          }
        }
        v132 = (void **)*v131;
        *v131 = v131;
        *((_QWORD *)lpMem + 1) = lpMem;
        v234 = 0;
        if ( v132 != lpMem )
        {
          do
          {
            v177 = (void **)*v132;
            HeapFree(g_PrivateHeap, 0, v132);
            v132 = v177;
          }
          while ( v177 != lpMem );
        }
      }
      v230 = 0;
      LOBYTE(v132) = 1;
      ServerXMLUpdateHandler::ServerXMLUpdateHandler(
        (ServerXMLUpdateHandler *)v266,
        0,
        (__int64)v132,
        &psz,
        0,
        0,
        0,
        (const struct JobMoniker *)&v261,
        &v230,
        (struct Triggers::Trigulator *)&v236,
        (struct Actions::ActionCollection *)&lpMem,
        0,
        0,
        0,
        6u);
      wmi::AutoRef<User::UserEntry>::Release(&v230);
      PrivilegeSetLength[0] = 1;
      v134 = RpcImpersonateClient(0);
      v136 = v134;
      if ( v134 )
      {
        EventManager::EvtReport(v135, &IMPERSONATION_FAILURE, L"RpcServer::RetrieveTask", v134, phkResulta, lpcbDataa);
        wmi::GenericException::GenericException((wmi::GenericException *)&pExceptionObject, v136);
        throw (wmi::GenericException *)&pExceptionObject;
      }
      v86 = TaskXmlReader::ProcessXml(v248, (struct ITaskXmlHandler *)v266);
      PrivilegeSetLength[0] = v86;
      if ( v86 >= 0 )
      {
        RpcRevertToSelf();
        v137 = v274;
        v138 = SysAllocStringLen(0, *(_DWORD *)(v274 + 16));
        if ( v138 )
        {
          SysFreeString(0);
          v139 = v138;
          v140 = *(_QWORD *)(v137 + 16) + 1LL;
          v141 = *(_QWORD *)(v137 + 24);
          v142 = 2147483646;
          while ( v141 )
          {
            if ( !v140 )
              goto LABEL_229;
            if ( v140 > 0x7FFFFFFF || (v143 = *(_QWORD *)(v141 + 8), v143 > 0x7FFFFFFE) )
            {
              *v139 = 0;
LABEL_229:
              SysFreeString(v138);
              goto LABEL_238;
            }
            v144 = *(OLECHAR **)v141;
            v145 = v140;
            v146 = v139;
            while ( v143 )
            {
              v147 = *v144;
              if ( !*v144 )
                break;
              ++v144;
              *v146++ = v147;
              --v143;
              if ( !--v145 )
              {
                *(v146 - 1) = 0;
                goto LABEL_229;
              }
            }
            *v146 = 0;
            v148 = *(_QWORD *)(v141 + 8);
            v139 += v148;
            v140 -= v148;
            v141 = *(_QWORD *)(v141 + 16);
          }
          SysFreeString(0);
          SysFreeString(0);
          v87 = v138;
          v250 = (unsigned int *)v138;
        }
        else
        {
          SysFreeString(0);
          v142 = 2147483646;
        }
LABEL_238:
        v150 = SysStringLen(v87);
        if ( v150 )
        {
          v152 = v150 + 1LL;
          v153 = 2 * v152;
          if ( !is_mul_ok(v152, 2u) )
            v153 = -1;
          v154 = (unsigned __int16 *)HeapAlloc(g_PrivateHeap, 0, v153);
          if ( !v154 )
          {
            wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)&pExceptionObject);
            throw (wmi::OutOfMemoryException *)&pExceptionObject;
          }
          v151 = v254;
          *v254 = v154;
          *v154 = 0;
          v155 = *v151;
          if ( v152 > 0x7FFFFFFF )
          {
            *v155 = 0;
          }
          else
          {
            v151 = (_WORD **)v87;
            while ( v142 )
            {
              v156 = *(_WORD *)v151;
              if ( !*(_WORD *)v151 )
                break;
              v151 = (_WORD **)((char *)v151 + 2);
              *v155++ = v156;
              --v142;
              if ( !--v152 )
                goto LABEL_247;
            }
            if ( !v152 )
LABEL_247:
              --v155;
            *v155 = 0;
          }
        }
        if ( v275 )
          (*(void (__fastcall **)(__int64, _WORD **))(*(_QWORD *)v275 + 16LL))(v275, v151);
        std::unique_ptr<TaskXmlWriter>::~unique_ptr<TaskXmlWriter>(v273, v151);
        v158 = v272;
        if ( v272 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v272 + 4, 0xFFFFFFFF) == 1 )
            _bstr_t::Data_t::`scalar deleting destructor'(v158, v157);
          v272 = 0;
        }
        v159 = (BSTR *)v271;
        if ( v271 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v271 + 4, 0xFFFFFFFF) == 1 )
          {
            if ( *v159 )
            {
              SysFreeString(*v159);
              *v159 = 0;
            }
            v179 = v159[1];
            if ( v179 )
            {
              operator delete(v179);
              v159[1] = 0;
            }
            HeapFree(g_PrivateHeap, 0, v159);
          }
          v271 = 0;
        }
        v160 = (BSTR *)v270;
        if ( v270 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v270 + 4, 0xFFFFFFFF) == 1 )
          {
            if ( *v160 )
            {
              SysFreeString(*v160);
              *v160 = 0;
            }
            v180 = v160[1];
            if ( v180 )
            {
              operator delete(v180);
              v160[1] = 0;
            }
            HeapFree(g_PrivateHeap, 0, v160);
          }
          v270 = 0;
        }
        std::vector<_DAB_SCHEDULE_BY_DAY *>::~vector<_DAB_SCHEDULE_BY_DAY *>(v269);
        TriggersXmlHandler::CurrentAction::~CurrentAction((TriggersXmlHandler::CurrentAction *)v268);
        wmi::AutoRef<User::UserEntry>::Release(v267);
        ValidationXmlHandler::~ValidationXmlHandler((ValidationXmlHandler *)v266);
        if ( v234 )
        {
          v161 = (void ***)lpMem;
          for ( ii = *(void ****)lpMem; ii != v161; ii = (void ***)*ii )
          {
            v175 = ii[2];
            if ( v175 )
            {
              (*(void (__fastcall **)(void **, __int64))*v175)(v175, 1);
              ii[2] = 0;
              v161 = (void ***)lpMem;
            }
          }
          v163 = *v161;
          *v161 = (void **)v161;
          *((_QWORD *)lpMem + 1) = lpMem;
          v234 = 0;
          if ( v163 != lpMem )
          {
            do
            {
              v178 = (void **)*v163;
              HeapFree(g_PrivateHeap, 0, v163);
              v163 = v178;
            }
            while ( v178 != lpMem );
          }
        }
        v164 = (BSTR *)v235;
        if ( v235 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v235 + 4, 0xFFFFFFFF) == 1 )
          {
            if ( *v164 )
            {
              SysFreeString(*v164);
              *v164 = 0;
            }
            v181 = v164[1];
            if ( v181 )
            {
              operator delete(v181);
              v164[1] = 0;
            }
            HeapFree(g_PrivateHeap, 0, v164);
          }
          v235 = 0;
        }
        std::list<Task *>::clear(&lpMem);
        if ( lpMem )
          HeapFree(g_PrivateHeap, 0, lpMem);
        if ( v246[1] )
        {
          v165 = (void ***)v246[0];
          for ( jj = *(void ****)v246[0]; jj != v165; jj = (void ***)*jj )
          {
            v176 = jj[2];
            if ( v176 )
            {
              (*(void (__fastcall **)(void **, __int64))*v176)(v176, 1);
              jj[2] = 0;
              v165 = (void ***)v246[0];
            }
          }
          v167 = *v165;
          *v165 = (void **)v165;
          *((LPVOID *)v246[0] + 1) = v246[0];
          v246[1] = 0;
          if ( v167 != v246[0] )
          {
            do
            {
              v168 = (void **)*v167;
              HeapFree(g_PrivateHeap, 0, v167);
              v167 = v168;
            }
            while ( v168 != v246[0] );
          }
        }
        v236 = 0;
        v237 = *(_DWORD *)((char *)&v231 + 1);
        v238 = *(_WORD *)((char *)&v231 + 5);
        v239 = HIBYTE(v231);
        SystemTimeAsFileTime = (struct _FILETIME)-1LL;
        v241 = 0;
        v242 = *(_DWORD *)((char *)&v231 + 1);
        v243 = *(_WORD *)((char *)&v231 + 5);
        v244 = HIBYTE(v231);
        v245 = 0;
        v169 = (void (__fastcall ***)(_QWORD, __int64))v247;
        if ( v247 && _InterlockedExchangeAdd((volatile signed __int32 *)(v247 + 8), 0xFFFFFFFF) == 1 )
          (**v169)(v169, 1);
        v247 = 0;
        std::list<Triggers::Trigger *>::clear(v246);
        if ( v246[0] )
          HeapFree(g_PrivateHeap, 0, v246[0]);
        v170 = v264;
        if ( v264 && _InterlockedExchangeAdd((volatile signed __int32 *)v264 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(JobBucket *, __int64))v170)(v170, 1);
        v264 = 0;
        v171 = v262;
        if ( v262 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v262 + 4, 0xFFFFFFFF) == 1 )
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
          v262 = 0;
        }
        v172 = v248;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v248 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(TaskXmlReader *, __int64))v172)(v172, 1);
        (*(void (__fastcall **)(User::UserEntry *))(*(_QWORD *)v94 + 16LL))(v94);
        SysFreeString(v87);
        if ( *(_QWORD *)Type )
          HeapFree(g_PrivateHeap, 0, *(LPVOID *)Type);
        v173 = v260;
        if ( v260 && _InterlockedExchangeAdd((volatile signed __int32 *)v260 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(JobBucket *, __int64))v173)(v173, 1);
        v260 = 0;
        v174 = v258;
        if ( v258 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v258 + 4, 0xFFFFFFFF) == 1 )
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
          v258 = 0;
        }
        ReleaseSRWLockShared(v29);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        return PrivilegeSetLength[0];
      }
      RpcRevertToSelf();
      ServerXMLUpdateHandler::~ServerXMLUpdateHandler((ServerXMLUpdateHandler *)v266);
      Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)&lpMem);
      Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)&v236);
      JobMoniker::~JobMoniker((JobMoniker *)&v261);
      wmi::AutoRef<TaskXmlReader>::Release(&v251);
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&hKey);
      SysFreeString(0);
    }
    operator delete(*(void **)Type);
    JobMoniker::~JobMoniker((JobMoniker *)&v257);
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
0x180009010  mov     [rsp-8+arg_0], rbx
0x180009015  push    rbp
0x180009016  push    rsi
0x180009017  push    rdi
0x180009018  push    r12
0x18000901a  push    r13
0x18000901c  push    r14
0x18000901e  push    r15
0x180009020  lea     rbp, [rsp-760h]
0x180009028  sub     rsp, 860h
0x18000902f  mov     rax, cs:__security_cookie
0x180009036  xor     rax, rsp
0x180009039  mov     [rbp+790h+var_40], rax
0x180009040  mov     [rbp+790h+var_738], r9
0x180009044  mov     [rbp+790h+var_730], r8
0x180009048  mov     rbx, rdx
0x18000904b  mov     r14, rcx
0x18000904e  mov     rax, [rbp+790h+arg_20]
0x180009055  mov     [rbp+790h+var_718], rax
0x180009059  xor     esi, esi
0x18000905b  test    rax, rax
0x18000905e  jz      short loc_180009063
0x180009060  mov     [rax], rsi
0x180009063  xor     edx, edx; Val
0x180009065  mov     r8d, 20Ah; Size
0x18000906b  lea     rcx, [rbp+790h+psz]; void *
0x180009072  call    memset_0
0x180009077  test    rbx, rbx
0x18000907a  jz      loc_18000AABC
0x180009080  movzx   eax, word ptr [rbx]
0x180009083  test    ax, ax
0x180009086  jz      loc_18000AABC
0x18000908c  mov     edi, 7FFFFFFEh
0x180009091  mov     edx, 105h
0x180009096  cmp     ax, 5Ch ; '\'
0x18000909a  jnz     loc_18000912E
0x1800090a0  mov     r8d, esi
0x1800090a3  mov     ecx, esi
0x1800090a5  cmp     ecx, edx
0x1800090a7  jge     short loc_1800090D2
0x1800090a9  movsxd  r11, ecx
0x1800090ac  movzx   r10d, word ptr [rbx+r11*2]
0x1800090b1  test    r10w, r10w
0x1800090b5  jz      loc_18000917E
0x1800090bb  mov     r9d, r10d
0x1800090be  cmp     r10d, 5Ch ; '\'
0x1800090c2  jnz     short loc_180009105
0x1800090c4  cmp     r8w, r10w
0x1800090c8  jz      short loc_1800090D2
0x1800090ca  movzx   r8d, r10w
0x1800090ce  inc     ecx
0x1800090d0  jmp     short loc_1800090A5
0x1800090d2  mov     r9d, 8007007Bh
0x1800090d8  mov     eax, r9d
0x1800090db  mov     rcx, [rbp+790h+var_40]
0x1800090e2  xor     rcx, rsp; StackCookie
0x1800090e5  call    __security_check_cookie
0x1800090ea  mov     rbx, [rsp+890h+arg_0]
0x1800090f2  add     rsp, 860h
0x1800090f9  pop     r15
0x1800090fb  pop     r14
0x1800090fd  pop     r13
0x1800090ff  pop     r12
0x180009101  pop     rdi
0x180009102  pop     rsi
0x180009103  pop     rbp
0x180009104  retn
0x180009105  sub     r9d, 20h ; ' '
0x180009109  jnz     short loc_180009118
0x18000910b  cmp     r8w, 5Ch ; '\'
0x180009110  jz      short loc_1800090D2
0x180009112  test    r8w, r8w
0x180009116  jmp     short loc_1800090C8
0x180009118  sub     r9d, 0Eh
0x18000911c  jz      loc_18000AC45
0x180009122  sub     r9d, 1
0x180009126  jz      short loc_1800090D2
0x180009128  cmp     r9d, 0Bh
0x18000912c  jmp     short loc_1800090C8
0x18000912e  mov     rax, rdi
0x180009131  lea     r9, asc_1800A3DA8; "\\"
0x180009138  mov     r10, rdx
0x18000913b  lea     rcx, [rbp+790h+psz]
0x180009142  test    rax, rax
0x180009145  jz      short loc_180009176
0x180009147  movzx   r8d, word ptr [r9]
0x18000914b  test    r8w, r8w
0x18000914f  jz      short loc_180009171
0x180009151  add     r9, 2
0x180009155  mov     [rcx], r8w
0x180009159  add     rcx, 2
0x18000915d  dec     rax
0x180009160  sub     r10, 1
0x180009164  jnz     short loc_180009142
0x180009166  mov     r9d, 8007007Ah
0x18000916c  jmp     loc_1800090D8
0x180009171  test    r10, r10
0x180009174  jz      short loc_180009166
0x180009176  mov     [rcx], si
0x180009179  jmp     loc_1800090A0
0x18000917e  cmp     r8w, 5Ch ; '\'
0x180009183  jz      loc_18000AC6C
0x180009189  mov     rcx, rdx
0x18000918c  lea     rax, [rbp+790h+psz]
0x180009193  cmp     [rax], si
0x180009196  jz      short loc_1800091A2
0x180009198  add     rax, 2
0x18000919c  sub     rcx, 1
0x1800091a0  jnz     short loc_180009193
0x1800091a2  mov     r9d, 80070057h
0x1800091a8  test    rcx, rcx
0x1800091ab  cmovnz  r9d, esi
0x1800091af  mov     r8, rdx
0x1800091b2  sub     r8, rcx
0x1800091b5  test    rcx, rcx
0x1800091b8  cmovz   r8, rsi
0x1800091bc  jz      loc_1800090D8
0x1800091c2  mov     rax, rdi
0x1800091c5  sub     rdx, r8
0x1800091c8  lea     r8, [rbp+r8*2+790h+psz]
0x1800091d0  jz      short loc_1800091F4
0x1800091d2  test    rax, rax
0x1800091d5  jz      short loc_1800091F4
0x1800091d7  movzx   ecx, word ptr [rbx]
0x1800091da  test    cx, cx
0x1800091dd  jz      short loc_1800091F4
0x1800091df  add     rbx, 2
0x1800091e3  mov     [r8], cx
0x1800091e7  add     r8, 2
0x1800091eb  dec     rax
0x1800091ee  sub     rdx, 1
0x1800091f2  jnz     short loc_1800091D2
0x1800091f4  mov     r9d, 8007007Ah
0x1800091fa  test    rdx, rdx
0x1800091fd  cmovnz  r9d, esi
0x180009201  lea     rcx, [r8-2]
0x180009205  cmovnz  rcx, r8
0x180009209  mov     [rcx], si
0x18000920c  jz      loc_1800090D8
0x180009212  jmp     short loc_180009229
0x180009214  test    rdx, rdx
0x180009217  jz      loc_18000AB03
0x18000921d  mov     [rcx], si
0x180009220  test    r9d, r9d
0x180009223  js      loc_1800090D8
0x180009229  movzx   eax, [rbp+790h+psz]
0x180009230  test    ax, ax
0x180009233  jz      loc_18000AC84
0x180009239  cmp     [rbp+790h+var_24E], si
0x180009240  jz      loc_18000AC7A
0x180009246  mov     [rbp+790h+TokenHandle], rsi
0x18000924a  xor     ecx, ecx; BindingHandle
0x18000924c  call    cs:__imp_RpcImpersonateClient
0x180009252  mov     ebx, eax
0x180009254  test    eax, eax
0x180009256  jnz     loc_18000AC8E
0x18000925c  call    cs:__imp_GetCurrentThread
0x180009262  mov     rcx, rax; ThreadHandle
0x180009265  lea     r9, [rbp+790h+TokenHandle]; TokenHandle
0x180009269  mov     edx, 8; DesiredAccess
0x18000926e  mov     r8d, 1; OpenAsSelf
0x180009274  call    cs:__imp_OpenThreadToken
0x18000927a  test    eax, eax
0x18000927c  jz      loc_18000AC12
0x180009282  call    cs:__imp_RpcRevertToSelf
0x180009288  add     r14, 10h
0x18000928c  mov     [rbp+790h+var_710], r14
0x180009293  mov     rcx, r14; SRWLock
0x180009296  call    cs:__imp_AcquireSRWLockShared
0x18000929c  nop
0x18000929d  mov     r13, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x1800092a4  mov     [rbp+790h+var_7B0], r13
0x1800092a8  mov     r12, [rbp+790h+TokenHandle]
0x1800092ac  mov     [rbp+790h+var_748], r12
0x1800092b0  mov     r15, rsi
0x1800092b3  mov     [rbp+790h+var_7A8], rsi
0x1800092b7  mov     [rbp+790h+var_7A0], esi
0x1800092ba  mov     rdi, rsi
0x1800092bd  mov     [rbp+790h+var_720], rsi
0x1800092c1  mov     [rbp+790h+hKey], rsi
0x1800092c5  xor     edx, edx; dwFlags
0x1800092c7  mov     r8d, 18h; dwBytes
0x1800092cd  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800092d4  call    cs:__imp_HeapAlloc
0x1800092da  mov     rbx, rax
0x1800092dd  test    rax, rax
0x1800092e0  jz      loc_18000ACE2
0x1800092e6  mov     [rbp+790h+var_728], rax
0x1800092ea  mov     [rax+8], rsi
0x1800092ee  mov     dword ptr [rax+10h], 1
0x1800092f5  lea     rcx, aTaskcacheTree; "TaskCache\\Tree"
0x1800092fc  call    cs:__imp_SysAllocString
0x180009302  mov     [rbx], rax
0x180009305  test    rax, rax
0x180009308  jz      loc_18000A502
0x18000930e  mov     [rbp+790h+var_728], rbx
0x180009312  cmp     [rbp+790h+psz], 5Ch ; '\'
0x18000931a  jnz     loc_18000AAB0
0x180009320  lea     rax, [rbp+790h+var_24E]
0x180009327  mov     [rbp+790h+var_740], rax
0x18000932b  cmp     word ptr [rax], 0
0x18000932f  jz      loc_180009494
0x180009335  xor     edx, edx; dwFlags
0x180009337  mov     r8d, 18h; dwBytes
0x18000933d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180009344  call    cs:__imp_HeapAlloc
0x18000934a  mov     rsi, rax
0x18000934d  test    rax, rax
0x180009350  jz      loc_18000AD24
0x180009356  mov     qword ptr [rbp+790h+PrivilegeSetLength], rax
0x18000935a  xor     r13d, r13d
0x18000935d  mov     [rax+8], r13
0x180009361  mov     dword ptr [rax+10h], 1
0x180009368  lea     rcx, asc_1800A3DA8; "\\"
0x18000936f  call    cs:__imp_SysAllocString
0x180009375  mov     [rsi], rax
0x180009378  test    rax, rax
0x18000937b  jz      loc_18000A944
0x180009381  mov     qword ptr [rbp+790h+PrivilegeSetLength], rsi
0x180009385  xor     edx, edx; dwFlags
0x180009387  mov     r8d, 18h; dwBytes
0x18000938d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180009394  call    cs:__imp_HeapAlloc
0x18000939a  mov     r12, rax
0x18000939d  test    rax, rax
0x1800093a0  jz      loc_18000AD68
0x1800093a6  mov     qword ptr [rbp+790h+GenericMapping.GenericRead], rax
0x1800093ad  mov     [rax+8], r13
0x1800093b1  mov     dword ptr [rax+10h], 1
0x1800093b8  mov     rcx, [rbx]; pbstr
0x1800093bb  test    rcx, rcx
0x1800093be  jz      loc_18000ADAA
0x1800093c4  call    cs:__imp_SysStringLen
0x1800093ca  mov     [rbp+790h+Type], eax
0x1800093cd  mov     rcx, [rsi]; pbstr
0x1800093d0  test    rcx, rcx
0x1800093d3  jz      loc_18000ADB2
0x1800093d9  call    cs:__imp_SysStringLen
0x1800093df  mov     ecx, eax
0x1800093e1  mov     eax, [rbp+790h+Type]
0x1800093e4  mov     [rbp+790h+cbData], ecx
0x1800093e7  lea     r13d, [rcx+rax]
0x1800093eb  cmp     r13d, eax
0x1800093ee  jb      short loc_180009404
0x1800093f0  mov     edx, r13d
0x1800093f3  add     rdx, rdx; struct IErrorInfo *
0x1800093f6  mov     eax, 0FFFFFFFFh
0x1800093fb  cmp     rdx, rax
0x1800093fe  jbe     loc_18000A7A9
0x180009404  mov     ecx, 8007000Eh; int
0x180009409  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18000940f  xor     ecx, ecx; psz
0x180009411  call    cs:__imp_SysAllocStringByteLen
0x180009417  mov     rcx, rax; void *
0x18000941a  mov     [rbx], rax
0x18000941d  test    rax, rax
0x180009420  jz      loc_18000A9A3
0x180009426  mov     rdx, [r12]; Src
0x18000942a  mov     r13d, [rbp+790h+Type]
0x18000942e  test    rdx, rdx
0x180009431  jz      short loc_18000943F
0x180009433  lea     r8d, [r13+1]
0x180009437  add     r8, r8; Size
0x18000943a  call    memcpy_0
0x18000943f  mov     rdx, [rsi]; Src
0x180009442  test    rdx, rdx
0x180009445  jz      short loc_180009461
0x180009447  mov     r8d, [rbp+790h+cbData]
0x18000944b  inc     r8d
0x18000944e  add     r8, r8; Size
0x180009451  mov     ecx, r13d
0x180009454  mov     rax, [rbx]
0x180009457  lea     rcx, [rax+rcx*2]; void *
0x18000945b  call    memcpy_0
0x180009460  nop
0x180009461  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009468  mov     eax, ecx
0x18000946a  lock xadd [r12+10h], eax
0x180009471  cmp     eax, 1
0x180009474  jz      loc_18000A9D1
0x18000947a  mov     eax, ecx
0x18000947c  lock xadd [rsi+10h], eax
0x180009481  cmp     eax, 1
0x180009484  jz      loc_18000A9E5
0x18000948a  xor     esi, esi
0x18000948c  mov     r13, [rbp+790h+var_7B0]
0x180009490  mov     r12, [rbp+790h+var_748]
0x180009494  test    rbx, rbx
0x180009497  jz      loc_18000A912
0x18000949d  mov     rdx, [rbx]; lpSubKey
0x1800094a0  lea     rax, [rbp+790h+hKey]
0x1800094a4  mov     [rsp+890h+phkResult], rax; phkResult
0x1800094a9  mov     r9d, 0F003Fh; samDesired
0x1800094af  xor     r8d, r8d; ulOptions
0x1800094b2  mov     rcx, [r13+10h]; hKey
0x1800094b6  call    cs:__imp_RegOpenKeyExW
0x1800094bc  mov     esi, eax
0x1800094be  test    eax, eax
0x1800094c0  jz      short loc_180009508
0x1800094c2  jle     short loc_1800094CD
  ... truncated ...
```
