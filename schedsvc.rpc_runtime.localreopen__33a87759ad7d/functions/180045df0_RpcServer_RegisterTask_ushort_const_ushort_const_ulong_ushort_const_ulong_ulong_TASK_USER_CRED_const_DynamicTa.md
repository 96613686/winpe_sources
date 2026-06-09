# RpcServer::RegisterTask(ushort const *,ushort const *,ulong,ushort const *,ulong,ulong,_TASK_USER_CRED const *,DynamicTaskInfo const *,ushort * *,_TASK_XML_ERROR_INFO * *)

- ea: `0x180045df0`
- end: `0x180049b6c`
- name: `?RegisterTask@RpcServer@@QEAAJPEBG0K0KKPEBU_TASK_USER_CRED@@PEBUDynamicTaskInfo@@PEAPEAGPEAPEAU_TASK_XML_ERROR_INFO@@@Z`
- size: `15740`
- prototype: `__int64 __fastcall(OLECHAR *this, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, const struct _TASK_USER_CRED *, BYTE *, unsigned __int16 **, struct _TASK_XML_ERROR_INFO **)`
- caller_count: `2`
- callee_count: `89`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180045d70`
- `0x18007683c`

## callees

- `0x180007ddc`
- `0x180007ec0`
- `0x180008180`
- `0x180008330`
- `0x180008720`
- `0x18000b4e0`
- `0x18000dc30`
- `0x18000e910`
- `0x18000f6a8`
- `0x18001351c`
- `0x180016e3c`
- `0x180017e70`
- `0x18001a430`
- `0x18001ec90`
- `0x18001fdb0`
- `0x18002132c`
- `0x180022600`
- `0x180023b60`
- `0x1800244ac`
- `0x1800245dc`
- `0x180024690`
- `0x1800247e0`
- `0x18002506c`
- `0x180025550`
- `0x1800256d0`
- `0x180025870`
- `0x18002643c`
- `0x180026460`
- `0x1800269f0`
- `0x180027c30`
- `0x180028ce0`
- `0x1800291c0`
- `0x18002ab20`
- `0x18002ab90`
- `0x18002b1d0`
- `0x18002d3d0`
- `0x18002db7c`
- `0x18002e41c`
- `0x18002f040`
- `0x18002f35c`
- `0x18002f3e0`
- `0x180030f80`
- `0x1800322a0`
- `0x180032340`
- `0x1800349c0`
- `0x180038000`
- `0x180039b6c`
- `0x18003a400`
- `0x18003abc0`
- `0x18003b2c0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800486e5`
- `OLEAUT32!__imp_SysAllocString` at `0x180048a20`
- `OLEAUT32!__imp_SysAllocString` at `0x1800486e5`
- `OLEAUT32!__imp_SysAllocString` at `0x180048a20`
- `OLEAUT32!__imp_SysFreeString` at `0x18004676c`
- `OLEAUT32!__imp_SysFreeString` at `0x180046b92`
- `OLEAUT32!__imp_SysFreeString` at `0x180046e0d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800473bf`
- `OLEAUT32!__imp_SysFreeString` at `0x180047417`
- `OLEAUT32!__imp_SysFreeString` at `0x180048688`
- `OLEAUT32!__imp_SysFreeString` at `0x1800486ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18004898a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800489a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004991f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004992e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004993d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004676c`
- `OLEAUT32!__imp_SysFreeString` at `0x180046b92`
- `OLEAUT32!__imp_SysFreeString` at `0x180046e0d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800473bf`
- `OLEAUT32!__imp_SysFreeString` at `0x180047417`
- `OLEAUT32!__imp_SysFreeString` at `0x180048688`
- `OLEAUT32!__imp_SysFreeString` at `0x1800486ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18004898a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800489a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004991f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004992e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004993d`
- `OLEAUT32!__imp_SysStringLen` at `0x180047147`
- `OLEAUT32!__imp_SysStringLen` at `0x1800495ce`
- `OLEAUT32!__imp_SysStringLen` at `0x180047147`
- `OLEAUT32!__imp_SysStringLen` at `0x1800495ce`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800485b4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800488c5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800485b4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800488c5`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800485c4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800488d5`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800485c4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800488d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004621b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004621b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047456`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800461bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800461e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800461fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004747e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800474c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004754a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049980`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800461bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800461e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800461fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004747e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800474c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004754a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049980`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046735`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004730f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004734a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800483de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046735`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004730f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004734a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800483de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047962`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047962`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047a3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047c3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047ea1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047f2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048df6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047a3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047c3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047ea1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047f2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048df6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800466ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800472f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004732c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800483d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800466ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800472f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004732c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800483d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a80`
- `ntdll!RtlSidDominates` at `0x180046193`
- `ntdll!RtlSidDominates` at `0x180046193`
- `ntdll!RtlFreeSid` at `0x1800461a3`
- `ntdll!RtlFreeSid` at `0x1800461a3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180046171`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180046171`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180048339`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180048339`
- `ntdll!RtlNtStatusToDosError` at `0x1800461af`
- `ntdll!RtlNtStatusToDosError` at `0x1800461eb`
- `ntdll!RtlNtStatusToDosError` at `0x180046dcc`
- `ntdll!RtlNtStatusToDosError` at `0x180046f76`
- `ntdll!RtlNtStatusToDosError` at `0x1800461af`
- `ntdll!RtlNtStatusToDosError` at `0x1800461eb`
- `ntdll!RtlNtStatusToDosError` at `0x180046dcc`
- `ntdll!RtlNtStatusToDosError` at `0x180046f76`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180046081`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800498a9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180046081`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800498a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800465eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800466ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004679d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800468ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046e3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046ebe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004707a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800473da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800473f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047432`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047448`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800499d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049a68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049a88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049aa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800465eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800466ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004679d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800468ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046e3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046ebe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004707a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800473da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800473f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047432`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047448`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800499d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049a68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049a88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049aa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800460b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046ca0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004907a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800460b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046ca0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004907a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800460d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180046cbc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180049096`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800460d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180046cbc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180049096`
- `RPCRT4!RpcImpersonateClient` at `0x180046089`
- `RPCRT4!RpcImpersonateClient` at `0x180046631`
- `RPCRT4!RpcImpersonateClient` at `0x180046089`
- `RPCRT4!RpcImpersonateClient` at `0x180046631`
- `RPCRT4!RpcRevertToSelf` at `0x18004622b`
- `RPCRT4!RpcRevertToSelf` at `0x18004669f`
- `RPCRT4!RpcRevertToSelf` at `0x18004687d`
- `RPCRT4!RpcRevertToSelf` at `0x180046d22`
- `RPCRT4!RpcRevertToSelf` at `0x180048256`
- `RPCRT4!RpcRevertToSelf` at `0x18004826b`
- `RPCRT4!RpcRevertToSelf` at `0x1800484d6`
- `RPCRT4!RpcRevertToSelf` at `0x180048a12`
- `RPCRT4!RpcRevertToSelf` at `0x180048a49`
- `RPCRT4!RpcRevertToSelf` at `0x180048c56`
- `RPCRT4!RpcRevertToSelf` at `0x180048c79`
- `RPCRT4!RpcRevertToSelf` at `0x180048d22`
- `RPCRT4!RpcRevertToSelf` at `0x180049175`
- `RPCRT4!RpcRevertToSelf` at `0x180049768`
- `RPCRT4!RpcRevertToSelf` at `0x18004622b`
- `RPCRT4!RpcRevertToSelf` at `0x18004669f`
- `RPCRT4!RpcRevertToSelf` at `0x18004687d`
- `RPCRT4!RpcRevertToSelf` at `0x180046d22`
- `RPCRT4!RpcRevertToSelf` at `0x180048256`
- `RPCRT4!RpcRevertToSelf` at `0x18004826b`
- `RPCRT4!RpcRevertToSelf` at `0x1800484d6`
- `RPCRT4!RpcRevertToSelf` at `0x180048a12`
- `RPCRT4!RpcRevertToSelf` at `0x180048a49`
- `RPCRT4!RpcRevertToSelf` at `0x180048c56`
- `RPCRT4!RpcRevertToSelf` at `0x180048c79`
- `RPCRT4!RpcRevertToSelf` at `0x180048d22`
- `RPCRT4!RpcRevertToSelf` at `0x180049175`
- `RPCRT4!RpcRevertToSelf` at `0x180049768`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d45`

## string_xrefs

- `0x180048225`: `RpcServer::RegisterTask`
- `0x18004849e`: `RpcServer::RegisterTask`
- `0x180048892`: `RpcServer::RegisterTask`
- `0x180048baf`: `RpcServer::RegisterTask`
- `0x180048ce2`: `RpcServer::RegisterTask`
- `0x180049047`: `RpcServer::RegisterTask`
- `0x180049acf`: `RpcServer::RegisterTask`
- `0x180049b09`: `RpcServer::RegisterTask`

## pseudocode

```c
__int64 __fastcall RpcServer::RegisterTask(
        OLECHAR *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        const struct _TASK_USER_CRED *a8,
        BYTE *a9,
        unsigned __int16 **a10,
        struct _TASK_XML_ERROR_INFO **a11)
{
  _BYTE *v13; // rsi
  OLECHAR *v14; // r14
  _BYTE *v15; // rax
  RPC_STATUS v16; // eax
  EventManager *v17; // rcx
  unsigned int v18; // ebx
  HANDLE CurrentThread; // rax
  int v20; // eax
  NTSTATUS v21; // ebx
  ULONG LastError; // ebx
  int Sddl; // r15d
  unsigned __int16 *v24; // r12
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // edx
  int v28; // eax
  unsigned __int16 *v29; // rax
  __int64 v30; // rax
  volatile signed __int32 *v31; // rbx
  struct _TASK_XML_ERROR_INFO *v32; // rax
  RPC_STATUS v33; // eax
  EventManager *v34; // rcx
  unsigned int v35; // ebx
  int v36; // eax
  tsched *v37; // rcx
  void *v38; // r8
  struct _RTL_CRITICAL_SECTION *v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdi
  __int64 v43; // rcx
  void *v44; // r8
  const struct _TASK_USER_CRED *v45; // r12
  bool IsLocalSystem; // al
  int v47; // eax
  void *v48; // rax
  __int64 v49; // rax
  volatile signed __int32 *v50; // rbx
  const unsigned __int16 *v51; // rax
  unsigned __int16 *v52; // r9
  _QWORD *v53; // rdi
  __int64 v54; // rax
  __int64 v55; // rdx
  int v56; // r8d
  int v57; // r9d
  char v58; // r12
  unsigned __int16 *Copy; // rdi
  JobBucket *v60; // rdi
  JobBucket *v61; // rcx
  HANDLE v62; // rax
  int v63; // edx
  tsched *v64; // rcx
  int LastHrError; // eax
  JobBucket *v66; // rcx
  const struct _TASK_USER_CRED *v67; // r12
  __int64 DomainAccount; // rax
  WCHAR *v69; // rax
  int IsServiceAccount; // r8d
  bool v71; // di
  __int64 v72; // rcx
  signed int v73; // eax
  BSTR *v74; // rbx
  BSTR v75; // r8
  _QWORD *v76; // rcx
  int v77; // edx
  unsigned __int8 v78; // r15
  NTSTATUS v79; // eax
  signed int v80; // eax
  const unsigned __int16 *v81; // rdx
  tsched *v82; // rdi
  const unsigned __int16 *v83; // rdx
  unsigned __int16 *v84; // rsi
  JobStore *v85; // r9
  BSTR *v86; // rax
  UINT v87; // ecx
  __int64 v88; // rdx
  JobBucket *v89; // rdi
  int v90; // eax
  JobBucket *v91; // rdx
  int v92; // eax
  bool v93; // zf
  int v94; // eax
  struct _RTL_CRITICAL_SECTION *v95; // rbx
  __int64 v96; // r15
  __int64 v97; // rax
  __int64 v98; // r15
  BSTR v99; // r12
  struct _RTL_CRITICAL_SECTION *v100; // rbx
  __int64 v101; // rdi
  __int64 v102; // rax
  __int64 v103; // rdi
  BSTR v104; // rcx
  int v105; // ebx
  void *v106; // r8
  void *v107; // r8
  signed int v108; // eax
  unsigned __int16 *v109; // r12
  int v110; // eax
  _QWORD *v111; // rcx
  int v112; // edx
  __int64 v113; // r9
  unsigned int v114; // ebx
  __int64 v115; // rax
  int v116; // eax
  int v117; // ebx
  int v118; // ecx
  const struct _TASK_USER_CRED *v119; // rdi
  __int64 v120; // rax
  __int64 v121; // rbx
  unsigned __int64 v122; // rbx
  unsigned int v123; // ebx
  struct _RTL_CRITICAL_SECTION *v124; // r12
  unsigned __int16 **v125; // rdi
  bool v126; // r9
  unsigned int v127; // r8d
  unsigned int v128; // edx
  const struct _TASK_USER_CRED *v129; // r9
  __int64 i; // rcx
  _BYTE *v131; // rax
  __int64 v132; // rcx
  unsigned int Path; // eax
  RTL_SRWLOCK *v134; // rdi
  unsigned __int16 *v135; // rbx
  int v136; // eax
  const unsigned __int16 *v137; // rdx
  unsigned __int16 *v138; // rax
  HKEY *v139; // rbx
  int TreeInfo; // eax
  int v141; // edx
  JobStore *v142; // rcx
  __int64 v143; // rcx
  int v144; // eax
  int v145; // ecx
  const unsigned __int16 *v146; // rax
  unsigned __int16 *v147; // rcx
  __int64 v148; // rax
  int v149; // eax
  RpcServer *v150; // rcx
  const struct JobSecurity *v151; // r8
  void *v152; // rcx
  void *v153; // rbx
  unsigned int v154; // eax
  const unsigned __int16 *v155; // rax
  const unsigned __int16 *v156; // rax
  unsigned int v157; // eax
  int v158; // edx
  const unsigned __int16 *v159; // rax
  JobMoniker *v160; // rax
  const unsigned __int16 *v161; // rax
  DWORD v162; // ebx
  CredStore *v163; // rbx
  __int64 Account; // rax
  const unsigned __int16 *v165; // rax
  __int64 v166; // rax
  char v167; // si
  __int64 v168; // rbx
  unsigned int v169; // eax
  __int64 v170; // r9
  __int64 v171; // rax
  __int64 v172; // rcx
  __int64 v173; // rax
  __int64 v174; // rax
  tsched *v175; // rcx
  DWORD v176; // ebx
  char *v177; // rax
  const void *v178; // rdx
  char *v179; // rcx
  PSECURITY_DESCRIPTOR v180; // rbx
  SIZE_T v181; // r15
  HLOCAL v182; // rdi
  __int64 v183; // rdi
  struct _RTL_CRITICAL_SECTION *v184; // rbx
  __int64 v185; // rcx
  CredStore *v186; // rbx
  __int64 v187; // rax
  const unsigned __int16 *v188; // rax
  unsigned __int8 v189; // bl
  HKEY *v190; // rbx
  JobStore *v191; // rcx
  unsigned __int16 *v192; // rbx
  HANDLE v193; // r15
  UINT v194; // eax
  OLECHAR *v195; // rax
  OLECHAR *v196; // rdi
  OLECHAR *v197; // rbx
  unsigned int v198; // eax
  void *v199; // r8
  JobStore *v200; // rsi
  int updated; // eax
  unsigned int v202; // eax
  UINT v203; // eax
  OLECHAR *v204; // rax
  OLECHAR *v205; // rdi
  OLECHAR *v206; // rbx
  unsigned int v207; // eax
  unsigned int v208; // eax
  JobBucket *v209; // rax
  __int64 v210; // rdi
  struct _RTL_CRITICAL_SECTION *v211; // rbx
  __int64 v212; // rcx
  CredStore *v213; // rbx
  __int64 v214; // rax
  const unsigned __int16 *v215; // rax
  __int64 v216; // rax
  char v217; // si
  __int64 v218; // rbx
  unsigned int v219; // eax
  const struct User *v220; // r9
  unsigned int v221; // eax
  int v222; // eax
  const struct JobSecurity *v223; // r8
  unsigned int v224; // eax
  int v225; // edx
  unsigned int v226; // eax
  int v227; // edx
  unsigned int v228; // eax
  char v229; // bl
  _QWORD *v230; // rax
  _QWORD *j; // rbx
  __int64 v232; // rcx
  HANDLE v233; // rax
  signed int v234; // eax
  int v235; // eax
  EventManager *v236; // rcx
  unsigned int v237; // edi
  unsigned int v238; // eax
  const struct _EVENT_DESCRIPTOR *v239; // rax
  const struct _EVENT_DESCRIPTOR *v240; // rbx
  unsigned __int8 v241; // di
  const unsigned __int16 **v242; // rdi
  EventManager *v243; // rcx
  const unsigned __int16 *v244; // rax
  char v245; // bl
  unsigned int v246; // eax
  int v247; // edx
  const unsigned __int16 *v248; // rax
  BSTR *v249; // rax
  UINT v250; // edx
  _QWORD *v251; // rcx
  __int64 v252; // rax
  int v253; // eax
  _BYTE *v254; // rcx
  __int64 v255; // rax
  __int64 k; // rax
  JobBucket *v257; // rcx
  _BYTE *v258; // rcx
  __int64 v259; // rax
  __int64 m; // rax
  void (__fastcall ***v261)(_QWORD, __int64); // rcx
  void *UserDataCount; // [rsp+20h] [rbp-838h]
  int *UserDataCounta; // [rsp+20h] [rbp-838h]
  char UserDataCountb; // [rsp+20h] [rbp-838h]
  void *UserDataCountc; // [rsp+20h] [rbp-838h]
  const struct _GUID *UserData; // [rsp+28h] [rbp-830h]
  const struct _GUID *UserDataa; // [rsp+28h] [rbp-830h]
  const struct _GUID *UserDatab; // [rsp+28h] [rbp-830h]
  unsigned __int8 v270[8]; // [rsp+80h] [rbp-7D8h] BYREF
  unsigned __int16 *v271; // [rsp+88h] [rbp-7D0h]
  int v272; // [rsp+90h] [rbp-7C8h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp-7C0h] BYREF
  unsigned int v274; // [rsp+A0h] [rbp-7B8h]
  DWORD TokenInformationLength; // [rsp+A4h] [rbp-7B4h] BYREF
  unsigned __int16 *v276; // [rsp+A8h] [rbp-7B0h]
  __int64 v277; // [rsp+B0h] [rbp-7A8h] BYREF
  PSID Sid; // [rsp+B8h] [rbp-7A0h] BYREF
  DWORD ReturnLength[2]; // [rsp+C0h] [rbp-798h] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp-790h] BYREF
  LPVOID lpMem; // [rsp+D0h] [rbp-788h] BYREF
  unsigned int v282; // [rsp+D8h] [rbp-780h]
  unsigned int v283; // [rsp+DCh] [rbp-77Ch]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+E0h] [rbp-778h] BYREF
  unsigned int v285; // [rsp+F0h] [rbp-768h]
  const struct _TASK_USER_CRED *v286; // [rsp+F8h] [rbp-760h]
  BSTR bstr; // [rsp+100h] [rbp-758h] BYREF
  HANDLE hObject; // [rsp+108h] [rbp-750h] BYREF
  BSTR v289; // [rsp+110h] [rbp-748h] BYREF
  unsigned int v290; // [rsp+118h] [rbp-740h]
  unsigned __int16 *v291; // [rsp+120h] [rbp-738h]
  _BYTE *v292; // [rsp+128h] [rbp-730h] BYREF
  unsigned __int16 *v293; // [rsp+130h] [rbp-728h] BYREF
  unsigned __int16 *v294; // [rsp+138h] [rbp-720h]
  _QWORD v295[2]; // [rsp+140h] [rbp-718h] BYREF
  LPVOID v296; // [rsp+150h] [rbp-708h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+158h] [rbp-700h] BYREF
  unsigned __int16 *v298; // [rsp+160h] [rbp-6F8h] BYREF
  _BYTE *v299; // [rsp+168h] [rbp-6F0h] BYREF
  _BYTE *v300; // [rsp+170h] [rbp-6E8h]
  _BYTE *v301; // [rsp+178h] [rbp-6E0h]
  BSTR v302; // [rsp+180h] [rbp-6D8h] BYREF
  tsched **v303; // [rsp+188h] [rbp-6D0h] BYREF
  unsigned int v304; // [rsp+190h] [rbp-6C8h]
  BYTE *lpData; // [rsp+198h] [rbp-6C0h]
  unsigned __int16 **v306; // [rsp+1A0h] [rbp-6B8h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+1A8h] [rbp-6B0h] BYREF
  int v308; // [rsp+1B0h] [rbp-6A8h]
  unsigned __int16 *v309; // [rsp+1B8h] [rbp-6A0h]
  unsigned __int16 *v310; // [rsp+1C0h] [rbp-698h]
  _BYTE v311[24]; // [rsp+1C8h] [rbp-690h] BYREF
  _BYTE *v312; // [rsp+1E0h] [rbp-678h]
  __int128 v313; // [rsp+1E8h] [rbp-670h] BYREF
  __int64 v314; // [rsp+1F8h] [rbp-660h]
  _BYTE v315[32]; // [rsp+200h] [rbp-658h] BYREF
  _QWORD *v316; // [rsp+220h] [rbp-638h]
  JobBucket *v317; // [rsp+230h] [rbp-628h]
  _BYTE v318[24]; // [rsp+238h] [rbp-620h] BYREF
  _BYTE v319[56]; // [rsp+250h] [rbp-608h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+288h] [rbp-5D0h] BYREF
  _BYTE v321[56]; // [rsp+2C0h] [rbp-598h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+2F8h] [rbp-560h] BYREF
  GUID v323; // [rsp+300h] [rbp-558h] BYREF
  BSTR *v324; // [rsp+310h] [rbp-548h] BYREF
  JobBucket *v325; // [rsp+320h] [rbp-538h]
  GUID iid; // [rsp+328h] [rbp-530h] BYREF
  char v327[16]; // [rsp+338h] [rbp-520h] BYREF
  __int64 v328; // [rsp+348h] [rbp-510h]
  unsigned __int16 v329[256]; // [rsp+350h] [rbp-508h] BYREF
  char v330; // [rsp+550h] [rbp-308h]
  CBstrWriter *v331; // [rsp+770h] [rbp-E8h]
  struct _EVENT_DATA_DESCRIPTOR v332; // [rsp+790h] [rbp-C8h] BYREF
  char *v333; // [rsp+7A0h] [rbp-B8h]
  int v334; // [rsp+7A8h] [rbp-B0h]
  int v335; // [rsp+7ACh] [rbp-ACh]
  struct _EVENT_DATA_DESCRIPTOR TokenInformation; // [rsp+7B0h] [rbp-A8h] BYREF
  char *v337; // [rsp+7C0h] [rbp-98h]
  int v338; // [rsp+7C8h] [rbp-90h]
  int v339; // [rsp+7CCh] [rbp-8Ch]
  unsigned __int16 *v340; // [rsp+7D0h] [rbp-88h]
  int v341; // [rsp+7D8h] [rbp-80h]
  int v342; // [rsp+7DCh] [rbp-7Ch]
  _SID_IDENTIFIER_AUTHORITY *p_IdentifierAuthority; // [rsp+7E0h] [rbp-78h]
  __int64 v344; // [rsp+7E8h] [rbp-70h]
  unsigned __int16 *v345; // [rsp+7F0h] [rbp-68h]
  int v346; // [rsp+7F8h] [rbp-60h]
  int v347; // [rsp+7FCh] [rbp-5Ch]

  v291 = a3;
  v271 = a2;
  bstrString = this;
  v310 = a3;
  lpMem = a5;
  v286 = a8;
  lpData = a9;
  v306 = a10;
  v294 = (unsigned __int16 *)a11;
  v274 = 0;
  v285 = 0;
  v272 = 0;
  v276 = 0;
  v298 = 0;
  v293 = 0;
  StringSecurityDescriptor = 0;
  v13 = 0;
  v292 = 0;
  JobMoniker::JobMoniker(&iid, 0, 0);
  SecurityDescriptor = 0;
  v308 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v319);
  Actions::ActionCollection::ActionCollection((Actions::ActionCollection *)v318);
  v296 = 0;
  v300 = 0;
  v299 = 0;
  hObject = 0;
  v303 = 0;
  v313 = 0;
  v314 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v315);
  Actions::ActionCollection::ActionCollection((Actions::ActionCollection *)v311);
  v302 = 0;
  bstr = 0;
  v14 = 0;
  v309 = 0;
  JobMoniker::JobMoniker(&v323, a2, 0);
  if ( a7 )
    v15 = (_BYTE *)*((_QWORD *)a8 + 1);
  else
    v15 = 0;
  v301 = v15;
  v312 = v15;
  if ( (unsigned int)dword_1800BC358 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 261;
    EventDescriptor.Keyword = 0;
    v332.Ptr = (ULONGLONG)off_1800BC360;
    v332.Size = *(unsigned __int16 *)off_1800BC360;
    v332.Reserved = 2;
    v333 = byte_1800ADACB;
    v334 = 20;
    v335 = 1;
    v283 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &v332);
  }
  v16 = RpcImpersonateClient(0);
  v18 = v16;
  if ( v16 )
  {
    EventManager::EvtReport(v17, &IMPERSONATION_FAILURE, L"RpcServer::RegisterTask", v16, UserDataCount, UserData);
    wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v18);
    throw (wmi::GenericException *)pExceptionObject;
  }
  TokenInformationLength = 88;
  TokenHandle = 0;
  v270[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetTokenInformation(
           TokenHandle,
           TokenIntegrityLevel,
           &TokenInformation,
           TokenInformationLength,
           &TokenInformationLength) )
    {
      *(_DWORD *)IdentifierAuthority.Value = 0;
      *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
      Sid = 0;
      v20 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x2000u, 0, 0, 0, 0, 0, 0, 0, &Sid);
      if ( v20 < 0 )
      {
        LastError = RtlNtStatusToDosError(v20);
        CloseHandle(TokenHandle);
        goto LABEL_18;
      }
      v21 = RtlSidDominates(TokenInformation.Ptr, Sid, v270);
      RtlFreeSid(Sid);
      if ( v21 < 0 )
      {
        LastError = RtlNtStatusToDosError(v21);
        CloseHandle(TokenHandle);
        goto LABEL_18;
      }
      LastError = 0;
      if ( !v270[0] )
      {
        LastError = 5;
        CloseHandle(TokenHandle);
        goto LABEL_18;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_18:
  if ( LastError )
  {
    v251 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, LastError);
        v251 = WPP_GLOBAL_Control;
      }
      if ( v251 != &WPP_GLOBAL_Control && (*((_DWORD *)v251 + 7) & 0x10000) != 0 && *((_BYTE *)v251 + 25) >= 2u )
        WPP_SF_S(v251[2], 28, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, a2);
    }
    Sddl = -2147024891;
    RpcRevertToSelf();
    v24 = 0;
    goto LABEL_399;
  }
  RpcRevertToSelf();
  if ( v306 )
    *v306 = 0;
  if ( a11 )
    *a11 = 0;
  if ( a6 > 6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)a2,
        a6);
    }
    goto LABEL_28;
  }
  if ( !v291 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = 30;
LABEL_35:
      WPP_SF_S(v25[2], v26, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, a2);
      Sddl = -2147024809;
      v24 = 0;
      goto LABEL_399;
    }
    goto LABEL_28;
  }
  v27 = 2;
  if ( a4 )
    v27 = a4;
  v282 = v27;
  v290 = v27;
  if ( (v27 & 0xFFFFFFC0) != 0 || (v27 & 7) == 0 || (v27 & 0xFFFFFFFE) != 0 && (v27 & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, a2);
      Sddl = -2147024809;
      v24 = 0;
      goto LABEL_399;
    }
    goto LABEL_28;
  }
  if ( a7 )
  {
    if ( (*((_DWORD *)v286 + 4) & 0xFFFFFFFE) != 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 33;
        goto LABEL_35;
      }
      goto LABEL_28;
    }
    if ( a7 > 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          (_DWORD)a2,
          a7);
      }
      goto LABEL_28;
    }
  }
  else if ( v286 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = 32;
      goto LABEL_35;
    }
LABEL_28:
    Sddl = -2147024809;
LABEL_29:
    v24 = 0;
LABEL_399:
    v84 = v271;
    goto LABEL_400;
  }
  if ( (v27 & 1) != 0 )
  {
    Sid = 0;
    v28 = StringReader::CreateStream(v291, &Sid);
    Sddl = v28;
    if ( v28 >= 0 )
    {
      lpMem = 0;
      v289 = 0;
      v29 = (unsigned __int16 *)operator new(0x460u);
      v310 = v29;
      if ( v29 )
      {
        v30 = TaskXmlReader::TaskXmlReader(v29, &Sid, &lpMem, 0);
        v31 = (volatile signed __int32 *)v30;
        if ( v30 )
          _InterlockedIncrement((volatile signed __int32 *)(v30 + 8));
      }
      else
      {
        v31 = 0;
      }
      v289 = (BSTR)v31;
      ValidationXmlHandler::ValidationXmlHandler(
        (ValidationXmlHandler *)v329,
        (const struct JobMoniker *)&v323,
        2u,
        0,
        0);
      Sddl = TaskXmlReader::ProcessXml((TaskXmlReader *)v31, (struct ITaskXmlHandler *)v329);
      if ( a11 )
      {
        v32 = (struct _TASK_XML_ERROR_INFO *)lpMem;
        if ( lpMem )
        {
          lpMem = 0;
          *a11 = v32;
        }
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          (_DWORD)v271,
          Sddl);
      }
      ValidationXmlHandler::~ValidationXmlHandler((ValidationXmlHandler *)v329);
      if ( v31 && _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v31)(v31, 1);
      if ( lpMem )
        HeapFree(g_PrivateHeap, 0, lpMem);
      if ( Sid )
        (*(void (__fastcall **)(PSID))(*(_QWORD *)Sid + 16LL))(Sid);
      v24 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          (_DWORD)v271,
          v28);
      }
      if ( Sid )
        (*(void (__fastcall **)(PSID))(*(_QWORD *)Sid + 16LL))(Sid);
      v24 = 0;
    }
    goto LABEL_399;
  }
  TokenHandle = 0;
  v277 = 0;
  ReturnLength[0] = 1;
  v33 = RpcImpersonateClient(0);
  v35 = v33;
  if ( v33 )
  {
    EventManager::EvtReport(v34, &IMPERSONATION_FAILURE, L"RpcServer::RegisterTask", v33, UserDataCount, UserData);
    wmi::GenericException::GenericException((wmi::GenericException *)v321, v35);
    throw (wmi::GenericException *)v321;
  }
  v36 = User::FromImpersonationToken((struct User *)&v277, 0);
  Sddl = v36;
  if ( v36 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v271,
        v36);
    }
    RpcRevertToSelf();
    goto LABEL_92;
  }
  if ( a7 )
  {
    v45 = v286;
  }
  else
  {
    v39 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v40 = v277;
    if ( v277 && *(_BYTE *)v277 )
    {
      v41 = *(_QWORD *)(v277 + 16);
      if ( v41 )
        _InterlockedIncrement((volatile signed __int32 *)(v41 + 16));
      v42 = *(_QWORD *)(v40 + 16);
    }
    else
    {
      v43 = *(_QWORD *)(v277 + 8);
      if ( v43 )
        _InterlockedIncrement((volatile signed __int32 *)(v43 + 16));
      v42 = *(_QWORD *)(v40 + 8);
    }
    v289 = (BSTR)v42;
    LeaveCriticalSection(v39);
    _bstr_t::operator=(&v303, &v289);
    if ( v42 && _InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v42 )
      {
        SysFreeString(*(BSTR *)v42);
        *(_QWORD *)v42 = 0;
      }
      v44 = *(void **)(v42 + 8);
      if ( v44 )
      {
        HeapFree(g_PrivateHeap, 0, v44);
        *(_QWORD *)(v42 + 8) = 0;
      }
      HeapFree(g_PrivateHeap, 0, (LPVOID)v42);
    }
    *((_QWORD *)&v313 + 1) = 0;
    if ( v303 )
      v37 = *v303;
    else
      v37 = 0;
    *(_QWORD *)&v313 = v37;
    LODWORD(v314) = 1;
    v45 = (const struct _TASK_USER_CRED *)&v313;
    v286 = (const struct _TASK_USER_CRED *)&v313;
  }
  if ( (unsigned int)tsched::IsUserAdmin(v37) || (IsLocalSystem = User::IsLocalSystem((User *)&v277)) )
    IsLocalSystem = 1;
  v270[0] = IsLocalSystem;
  if ( *((_DWORD *)bstrString + 7) && !IsLocalSystem )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v271);
    }
LABEL_124:
    Sddl = -2147024891;
    goto LABEL_125;
  }
  Sid = 0;
  v47 = StringReader::CreateStream(v291, &Sid);
  Sddl = v47;
  if ( v47 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v271,
        v47);
    }
    if ( Sid )
LABEL_707:
      (*(void (__fastcall **)(PSID))(*(_QWORD *)Sid + 16LL))(Sid);
LABEL_125:
    RpcRevertToSelf();
    wmi::AutoRef<User::UserEntry>::Release(&v277);
    if ( TokenHandle )
    {
      HeapFree(g_PrivateHeap, 0, TokenHandle);
      v24 = 0;
      goto LABEL_399;
    }
    goto LABEL_708;
  }
  v289 = 0;
  v48 = operator new(0x460u);
  v295[0] = v48;
  if ( v48 )
  {
    v49 = TaskXmlReader::TaskXmlReader(v48, &Sid, &TokenHandle, 0);
    v50 = (volatile signed __int32 *)v49;
    if ( v49 )
      _InterlockedIncrement((volatile signed __int32 *)(v49 + 8));
  }
  else
  {
    v50 = 0;
  }
  v289 = (BSTR)v50;
  v51 = (const unsigned __int16 *)lpMem;
  if ( lpMem && !*(_WORD *)lpMem )
    v51 = 0;
  if ( !v271 || (v52 = 0, *v271) )
    v52 = v271;
  v304 = v282 & 8;
  *(_DWORD *)IdentifierAuthority.Value = v304;
  ServerXMLUpdateHandler::ServerXMLUpdateHandler(
    (ServerXMLUpdateHandler *)v329,
    v304 != 0,
    v304 == 0,
    v52,
    v51,
    v45,
    a6,
    (const struct JobMoniker *)&v323,
    (const struct User *)&v277,
    (struct Triggers::Trigulator *)v315,
    (struct Actions::ActionCollection *)v311,
    1,
    (struct ATL::CComBSTR *)&v302,
    (struct ATL::CComBSTR *)&bstr,
    0);
  Sddl = TaskXmlReader::ProcessXml((TaskXmlReader *)v50, (struct ITaskXmlHandler *)v329);
  if ( Sddl < 0 )
  {
    v53 = TokenHandle;
    TokenHandle = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v53 )
      {
        v54 = v53[2];
        v55 = v53[1];
        v56 = *((_DWORD *)v53 + 1);
        v57 = *(_DWORD *)v53;
      }
      else
      {
        v54 = 0;
        v55 = 0;
        v56 = 0;
        LOBYTE(v57) = 0;
      }
      WPP_SF_SDddSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, v56, (_DWORD)v271, Sddl, v57, v56, v55, v54);
    }
    if ( v294 && v53 )
      *(_QWORD *)v294 = v53;
    ServerXMLUpdateHandler::~ServerXMLUpdateHandler((ServerXMLUpdateHandler *)v329);
    if ( v50 && _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v50)(v50, 1);
    if ( Sid )
      goto LABEL_707;
    goto LABEL_125;
  }
  v58 = v330;
  Copy = CBstrWriter::GetCopy(v331);
  v294 = Copy;
  if ( !Copy )
  {
    Sddl = -2147024882;
    ServerXMLUpdateHandler::~ServerXMLUpdateHandler((ServerXMLUpdateHandler *)v329);
    if ( v50 && _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v50)(v50, 1);
    if ( Sid )
      goto LABEL_707;
    goto LABEL_125;
  }
  SysFreeString(0);
  v14 = Copy;
  v309 = Copy;
  v60 = v325;
  if ( v325 )
    _InterlockedIncrement((volatile signed __int32 *)v325 + 2);
  v61 = v317;
  if ( v317 && _InterlockedExchangeAdd((volatile signed __int32 *)v317 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v61)(v61, 1);
  v317 = v60;
  ServerXMLUpdateHandler::~ServerXMLUpdateHandler((ServerXMLUpdateHandler *)v329);
  if ( v50 && _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v50)(v50, 1);
  if ( Sid )
    (*(void (__fastcall **)(PSID))(*(_QWORD *)Sid + 16LL))(Sid);
  if ( !v270[0] && v58 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v271,
        Sddl);
    }
    goto LABEL_124;
  }
  v62 = GetCurrentThread();
  if ( !OpenThreadToken(v62, 0x2000Eu, 1, &hObject) )
  {
    LastHrError = tsched::GetLastHrError(v64, v63);
    Sddl = LastHrError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v271,
        LastHrError);
    }
    goto LABEL_125;
  }
  RpcRevertToSelf();
  v66 = v325;
  v67 = v286;
  if ( (*((_DWORD *)v325 + 4) & 0x40000) != 0 && (!v286 || !*((_QWORD *)v286 + 1)) )
  {
    DomainAccount = User::GetDomainAccount((char *)v325 + 64, &Sid);
    v69 = (WCHAR *)_bstr_t::operator unsigned short const *(DomainAccount);
    TokenInformationLength = 0;
    IsServiceAccount = 0;
    v71 = 0;
    if ( v69 )
    {
      if ( *v69 )
      {
        v72 = -1;
        do
          ++v72;
        while ( v69[v72] );
        if ( v69[(unsigned int)v72 - 1] == 36 )
        {
          IsServiceAccount = NetIsServiceAccount(0, v69, (BOOL *)&TokenInformationLength);
          if ( IsServiceAccount >= 0 )
            v71 = TokenInformationLength != 0;
        }
      }
    }
    v73 = RtlNtStatusToDosError(IsServiceAccount);
    Sddl = v73;
    if ( v73 > 0 )
      Sddl = (unsigned __int16)v73 | 0x80070000;
    v74 = (BSTR *)Sid;
    if ( Sid )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Sid + 4, 0xFFFFFFFF) == 1 && v74 )
      {
        if ( *v74 )
        {
          SysFreeString(*v74);
          *v74 = 0;
        }
        v75 = v74[1];
        if ( v75 )
        {
          HeapFree(g_PrivateHeap, 0, v75);
          v74[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v74);
      }
      Sid = 0;
    }
    if ( Sddl < 0 )
    {
      v76 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v77 = 43;
LABEL_208:
        WPP_SF_Sd(v76[2], v77, (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, (_DWORD)v271, Sddl);
        goto LABEL_209;
      }
      goto LABEL_209;
    }
    if ( v71 )
      *((_DWORD *)v325 + 4) |= 0x80000000;
    v66 = v325;
  }
  v78 = v270[0];
  if ( !v270[0] && JobBucket::GetPriority(v66) <= 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v271);
    }
    Sddl = -2147024891;
    goto LABEL_209;
  }
  TokenInformationLength = 0;
  v79 = LUAIsElevatedToken(hObject);
  if ( v79 < 0 )
  {
    v80 = RtlNtStatusToDosError(v79);
    Sddl = v80;
    if ( v80 > 0 )
      Sddl = (unsigned __int16)v80 | 0x80070000;
    v76 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v77 = 45;
      goto LABEL_208;
    }
LABEL_209:
    wmi::AutoRef<User::UserEntry>::Release(&v277);
    v38 = TokenHandle;
    if ( TokenHandle )
      goto LABEL_93;
LABEL_708:
    v24 = v276;
    goto LABEL_399;
  }
  if ( ((*((_DWORD *)v325 + 4) & 0x1000000) != 0
     || User::IsLocalAdmin((JobBucket *)((char *)v325 + 64))
     || (*((_DWORD *)v325 + 4) & 0xFC000) == 0x4000)
    && !TokenInformationLength
    && !v78 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v271);
    }
    Sddl = -2147024891;
LABEL_92:
    wmi::AutoRef<User::UserEntry>::Release(&v277);
    v38 = TokenHandle;
    if ( !TokenHandle )
      goto LABEL_29;
LABEL_93:
    HeapFree(g_PrivateHeap, 0, v38);
    v24 = 0;
    goto LABEL_399;
  }
  wmi::AutoRef<User::UserEntry>::Release(&v277);
  if ( TokenHandle )
    HeapFree(g_PrivateHeap, 0, TokenHandle);
  v82 = (tsched *)v302;
  v271 = v302;
  v289 = v302;
  v276 = tsched::PathCopy((tsched *)v302, v81);
  v298 = v276;
  if ( tsched::IsRoot(v82, v83) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v82);
    }
    Sddl = -2147024809;
    v84 = (unsigned __int16 *)v82;
    goto LABEL_246;
  }
  JobMoniker::_SetPath((JobMoniker *)&v323, (const unsigned __int16 *)v82);
  v85 = JobStore::m_pCommonStore;
  Sid = JobStore::m_pCommonStore;
  v86 = v324;
  if ( v324 && (!*v324 ? (JobStore *)(v87 = 0) : (v87 = SysStringLen(*v324), v86 = v324, v85 = (JobStore *)Sid), v87) )
  {
    if ( v86 )
      v88 = (__int64)(*v86 + 7);
    else
      v88 = 14;
  }
  else
  {
    v88 = 0;
  }
  JobStore::RegGetOverrideInfo(v85, (const unsigned __int16 *)v88, (enum JobFlags::StatePersistanceFlags *)&v272);
  *((_DWORD *)v325 + 5) = v272;
  if ( v67 && *((_QWORD *)v67 + 1) )
  {
    v89 = v325;
    v90 = *((_DWORD *)v325 + 4);
    if ( (v90 & 0x20000) != 0 || v90 < 0 )
    {
      Sddl = -2147023570;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v84 = v271;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          (_DWORD)v271,
          46);
        v24 = v276;
        goto LABEL_400;
      }
      goto LABEL_708;
    }
    goto LABEL_271;
  }
  v91 = v325;
  v92 = *((_DWORD *)v325 + 4);
  if ( (v92 & 0x100000) != 0 || (v92 & 0x20000) != 0 || (v92 & 0x40000) == 0 && (v92 & 0x80000) == 0 || v92 < 0 )
  {
LABEL_326:
    v114 = *((_DWORD *)v91 + 4);
    v115 = User::User(&TokenHandle, (char *)v91 + 64);
    v116 = IsPrincipalAllowed(v115, v114);
    Sddl = v116;
    if ( v116 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          (_DWORD)v82,
          v116);
        v84 = (unsigned __int16 *)v82;
        v24 = v276;
        goto LABEL_400;
      }
      goto LABEL_708;
    }
    goto LABEL_319;
  }
  if ( PlugIn::IsRegistering((PlugIn *)&PlugIn::s_singleton, (const unsigned __int16 *)v82, v291) )
  {
    v91 = v325;
    goto LABEL_326;
  }
  v89 = v325;
  if ( v67 )
  {
LABEL_271:
    *(_QWORD *)ReturnLength = *((_QWORD *)v67 + 1);
    goto LABEL_273;
  }
  *(_QWORD *)ReturnLength = 0;
LABEL_273:
  v93 = (*((_DWORD *)v89 + 4) & 0x10000) == 0;
  LODWORD(v277) = *((_DWORD *)v89 + 4) & 0x10000;
  v94 = 2;
  if ( v93 )
    v94 = 4;
  v283 = v94;
  TokenHandle = 0;
  v95 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v96 = *((_QWORD *)v89 + 8);
  v97 = *(_QWORD *)(v96 + 24);
  if ( v97 )
    _InterlockedIncrement((volatile signed __int32 *)(v97 + 16));
  v98 = *(_QWORD *)(v96 + 24);
  LeaveCriticalSection(v95);
  if ( v98 )
    v99 = *(BSTR *)v98;
  else
    v99 = 0;
  v100 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v101 = *((_QWORD *)v89 + 8);
  v102 = *(_QWORD *)(v101 + 16);
  if ( v102 )
    _InterlockedIncrement((volatile signed __int32 *)(v102 + 16));
  v103 = *(_QWORD *)(v101 + 16);
  LeaveCriticalSection(v100);
  if ( v103 )
    v104 = *(BSTR *)v103;
  else
    v104 = 0;
  UserDataa = 0;
  LODWORD(UserDataCounta) = 0;
  v105 = LogonUserExExW(v104, v99, *(_QWORD *)ReturnLength, v283);
  if ( v103 && _InterlockedExchangeAdd((volatile signed __int32 *)(v103 + 16), 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v103 )
    {
      SysFreeString(*(BSTR *)v103);
      *(_QWORD *)v103 = 0;
    }
    v106 = *(void **)(v103 + 8);
    if ( v106 )
    {
      HeapFree(g_PrivateHeap, 0, v106);
      *(_QWORD *)(v103 + 8) = 0;
    }
    HeapFree(g_PrivateHeap, 0, (LPVOID)v103);
  }
  if ( v98 && _InterlockedExchangeAdd((volatile signed __int32 *)(v98 + 16), 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v98 )
    {
      SysFreeString(*(BSTR *)v98);
      *(_QWORD *)v98 = 0;
    }
    v107 = *(void **)(v98 + 8);
    if ( v107 )
    {
      HeapFree(g_PrivateHeap, 0, v107);
      *(_QWORD *)(v98 + 8) = 0;
    }
    HeapFree(g_PrivateHeap, 0, (LPVOID)v98);
  }
  if ( v105 )
  {
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    Sddl = 0;
    goto LABEL_318;
  }
  v108 = GetLastError();
  if ( (_DWORD)v277 )
  {
LABEL_306:
    Sddl = v108;
    if ( v108 > 0 )
      Sddl = (unsigned __int16)v108 | 0x80070000;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    if ( Sddl < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0 )
        goto LABEL_708;
      v84 = v271;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          (_DWORD)v271,
          Sddl);
        v24 = v276;
        goto LABEL_400;
      }
LABEL_246:
      v24 = v276;
      goto LABEL_400;
    }
    goto LABEL_318;
  }
  if ( v108 != 1385 )
  {
    v108 = GetLastError();
    goto LABEL_306;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  Sddl = 267036;
LABEL_318:
  LODWORD(v82) = (_DWORD)v271;
LABEL_319:
  v283 = Sddl;
  v109 = v294;
  v110 = JobStore::ComputeHash((struct JobMoniker *)&v323, v294);
  Sddl = v110;
  if ( v110 < 0 )
  {
    v111 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_398;
    }
    v112 = 51;
    UserDataCountb = v110;
    LODWORD(v113) = (_DWORD)v82;
    goto LABEL_324;
  }
  v272 = 0;
  v117 = (*((__int64 (__fastcall **)(void ***, GUID *, _BYTE *, int *))UbpmProxySingleton::s_singleton[0] + 15))(
           UbpmProxySingleton::s_singleton,
           &v323,
           v311,
           &v272);
  if ( v117 < 0 )
    goto LABEL_689;
  if ( v272 )
  {
    *((_DWORD *)v325 + 4) |= 0x2000000u;
    goto LABEL_338;
  }
  UserDataCounta = &v272;
  v117 = (*((__int64 (__fastcall **)(void ***, GUID *, _BYTE *, _BYTE *))UbpmProxySingleton::s_singleton[0] + 16))(
           UbpmProxySingleton::s_singleton,
           &v323,
           v315,
           v311);
  if ( v117 < 0 )
  {
LABEL_689:
    Sddl = v117;
LABEL_690:
    v111 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_398;
    }
    v249 = v324;
    if ( v324
      && (!*v324 ? (BSTR *)(v250 = 0) : (v250 = SysStringLen(*v324), v111 = WPP_GLOBAL_Control, v249 = v324), v250) )
    {
      if ( v249 )
        v113 = (__int64)(*v249 + 7);
      else
        LODWORD(v113) = 14;
      v112 = 52;
      UserDataCountb = v117;
    }
    else
    {
      LODWORD(v113) = 0;
      v112 = 52;
      UserDataCountb = v117;
    }
LABEL_324:
    WPP_SF_Sd(v111[2], v112, (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v113, UserDataCountb);
LABEL_398:
    v24 = v276;
    goto LABEL_399;
  }
  if ( !v272 )
  {
    Sddl = -2147216599;
    LOBYTE(v117) = 41;
    goto LABEL_690;
  }
  *((_DWORD *)v325 + 4) &= ~0x2000000u;
LABEL_338:
  Sddl = v117;
  v118 = *((_DWORD *)v325 + 4);
  if ( (v118 & 0x40000) != 0 || (v118 & 0x80000) != 0 )
  {
    if ( a7 )
    {
      v119 = v286;
      if ( v286 )
      {
        v120 = *((_QWORD *)v286 + 1);
        if ( v120 )
        {
          if ( (v118 & 0x2000000) != 0 )
          {
            v121 = -1;
            do
              ++v121;
            while ( *(_WORD *)(v120 + 2 * v121) );
            v122 = v121 + 1;
            v296 = operator new(saturated_mul(v122, 2u));
            v300 = v296;
            v299 = v296;
            SafeStrCopy((unsigned __int16 *)v296, v122, *((const unsigned __int16 **)v119 + 1));
          }
          v123 = 0;
          v124 = CredStore::g_pCommonStore;
          while ( 1 )
          {
            TokenHandle = 0;
            v125 = (unsigned __int16 **)((char *)v119 + 24 * v123);
            Sddl = User::FromUsername((struct User *)&TokenHandle, *v125);
            if ( Sddl < 0 )
              break;
            Sddl = CredStore::StoreNtCredential(v124, (const struct User *)&TokenHandle, v125[1], v126);
            if ( Sddl < 0 )
              break;
            wmi::AutoRef<User::UserEntry>::Release(&TokenHandle);
            ++v123;
            v127 = a7;
            v119 = v286;
            if ( v123 >= a7 )
              goto LABEL_353;
          }
          wmi::AutoRef<User::UserEntry>::Release(&TokenHandle);
          v127 = a7;
LABEL_353:
          v128 = 0;
          v129 = v286;
          do
          {
            i = 3LL * v128;
            v131 = (_BYTE *)*((_QWORD *)v129 + 3 * v128 + 1);
            if ( v131 )
            {
              v132 = -1;
              do
                ++v132;
              while ( *(_WORD *)&v131[2 * v132] );
              for ( i = 2 * v132; i; --i )
                *v131++ = 0;
            }
            ++v128;
          }
          while ( v128 < v127 );
          if ( Sddl < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              Path = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                53,
                (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                Path,
                Sddl);
            }
            v24 = v276;
            EventManager::EvtReport(
              (EventManager *)i,
              &TASK_REGISTERED_WITHOUT_CREDENTIALS,
              v276,
              Sddl,
              UserDataCounta,
              UserDataa);
            goto LABEL_399;
          }
          v109 = v294;
        }
      }
    }
  }
  v134 = (RTL_SRWLOCK *)(bstrString + 8);
  TokenHandle = bstrString + 8;
  AcquireSRWLockExclusive((PSRWLOCK)bstrString + 2);
  memset_0(v329, 0, 0x20Au);
  v135 = v271;
  if ( (*((_DWORD *)v325 + 4) & 0x200000) != 0 )
  {
    if ( !PlugIn::IsRegistering((PlugIn *)&PlugIn::s_singleton, v271, v291) )
    {
      v136 = PlugIn::RegisterTask(
               (PlugIn *)&PlugIn::s_singleton,
               v135,
               v109,
               (const unsigned __int16 *)lpMem,
               v282,
               v329);
      Sddl = v136;
      if ( v136 < 0 )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0 )
        {
          v84 = v135;
        }
        else
        {
          v84 = v135;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
              (_DWORD)v135,
              v136);
        }
        goto LABEL_375;
      }
    }
    if ( !Sddl && v329[0] )
    {
      JobMoniker::_SetPath((JobMoniker *)&v323, v329);
      v271 = (unsigned __int16 *)JobMoniker::GetPath((JobMoniker *)&v323);
      v289 = v271;
      v138 = tsched::PathCopy((tsched *)v271, v137);
      wmi::AutoVectorPtr<unsigned short>::operator=(&v298, v138);
      v276 = v298;
    }
  }
  else
  {
    v144 = PlugIn::DeleteTask((PlugIn *)&PlugIn::s_singleton, v271);
    if ( v144 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v135,
        v144);
    }
  }
  v332 = 0;
  TokenInformationLength = 0;
  v139 = (HKEY *)Sid;
  TreeInfo = JobStore::RegGetTreeInfo(
               (JobStore *)Sid,
               v271,
               (struct _GUID *)&v332,
               (enum JobStore::TaskIndex *)&TokenInformationLength);
  Sddl = TreeInfo;
  if ( TreeInfo < 0 || TokenInformationLength )
  {
    v143 = (unsigned int)TreeInfo;
  }
  else
  {
    JobMoniker::JobMoniker((JobMoniker *)&TokenInformation, v271, (const struct _GUID *)&v332);
    if ( (int)JobStore::RemoveTaskEntryP(v139, &TokenInformation, 0) >= 0 )
      JobStore::FlushTaskEntryP(v142, v139[2]);
    Sddl = -2147024894;
    JobMoniker::~JobMoniker((JobMoniker *)&TokenInformation);
    v143 = 2147942402LL;
  }
  if ( !tsched::IsErrorNotFound((tsched *)v143, v141) )
  {
    if ( v145 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v154 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          v154,
          Sddl);
      }
      goto LABEL_397;
    }
    if ( (v282 & 4) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v155 = JobMoniker::GetPath((JobMoniker *)&v323);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v155);
      }
      Sddl = -2147024713;
      goto LABEL_397;
    }
    v323 = (GUID)v332;
    v84 = v271;
    Sddl = JobStore::RegJobSecurityQuery((JobStore *)v139, v271, (struct JobSecurity *)&SecurityDescriptor);
    if ( Sddl < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v156 = JobMoniker::GetPath((JobMoniker *)&v323);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v156);
      }
      goto LABEL_375;
    }
    Sddl = JobSecurity::GetSddl((JobSecurity *)&SecurityDescriptor, 7u, (unsigned __int16 **)&StringSecurityDescriptor);
    if ( Sddl >= 0 )
    {
      Sddl = JobAccessCheck(hObject, SecurityDescriptor, 2u);
      if ( Sddl >= 0 )
      {
        v159 = JobMoniker::GetPath((JobMoniker *)&v323);
        v160 = JobMoniker::JobMoniker((JobMoniker *)&TokenInformation, v159, &v323);
        JobMoniker::operator=(&iid, v160);
        JobMoniker::~JobMoniker((JobMoniker *)&TokenInformation);
        v161 = JobMoniker::GetPath((JobMoniker *)&v323);
        UserDataa = (const struct _GUID *)v318;
        UserDataCounta = (int *)v319;
        Sddl = JobStore::LoadBucketFromRegistry(v139, v161, 15, &iid);
        v272 = Sddl;
        if ( Sddl >= 0 )
        {
          v162 = *(_DWORD *)(v328 + 16);
          TokenInformationLength = v162;
          wmi::AutoRef<User::UserEntry>::operator=(&v292, *(_QWORD *)(v328 + 64));
          v13 = v292;
          if ( v292 && *v292 )
          {
            v163 = (CredStore *)CredStore::g_pCommonStore;
            Account = User::GetAccount(v328 + 64, v295);
            v165 = (const unsigned __int16 *)_bstr_t::operator unsigned short const *(Account);
            Sddl = CredStore::ResolveAlias(v163, v165, (struct User *)&v292);
            v272 = Sddl;
            _bstr_t::~_bstr_t((_bstr_t *)v295);
            if ( Sddl < 0 )
            {
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                v167 = v274;
              }
              else
              {
                v166 = User::GetAccount(v328 + 64, v295);
                v167 = 1;
                v168 = _bstr_t::operator unsigned short const *(v166);
                v169 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&iid);
                WPP_SF_SSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  63,
                  (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                  v169,
                  v168,
                  Sddl);
              }
              if ( (v167 & 1) != 0 )
                _bstr_t::~_bstr_t((_bstr_t *)v295);
              goto LABEL_397;
            }
            v13 = v292;
            v162 = TokenInformationLength;
          }
          v170 = v328;
          v171 = *(_QWORD *)(v328 + 208);
          if ( v171 )
            v172 = *(_QWORD *)(v171 + 48);
          else
            v172 = 0;
          v173 = *((_QWORD *)v325 + 26);
          if ( v173 )
            v174 = *(_QWORD *)(v173 + 48);
          else
            v174 = 0;
          if ( v172 != v174
            || (((*((_DWORD *)v325 + 4) >> 27) ^ (*(_DWORD *)(v328 + 16) >> 27)) & 1) != 0
            || (((*((_DWORD *)v325 + 4) >> 28) ^ (*(_DWORD *)(v328 + 16) >> 28)) & 1) != 0 )
          {
            RpcAutoImpersonate::RpcAutoImpersonate(
              (RpcAutoImpersonate *)&TokenInformationLength,
              L"RpcServer::RegisterTask",
              1);
            if ( !(unsigned int)tsched::IsUserAdmin(v175) )
            {
              Sddl = -2147024891;
              if ( TokenInformationLength )
                RpcRevertToSelf();
              goto LABEL_397;
            }
            if ( TokenInformationLength )
              RpcRevertToSelf();
            v170 = v328;
          }
          v270[0] = 0;
          v176 = v162 & 0xFC000;
          TokenInformationLength = v176;
          v151 = (const struct JobSecurity *)*((unsigned int *)v325 + 15);
          v177 = (char *)v325 + 28;
          if ( !(_DWORD)v151 )
            v177 = 0;
          if ( v177 )
          {
            v178 = (const void *)(v170 + 28);
            if ( !*(_DWORD *)(v170 + 60) )
              v178 = 0;
            if ( v178 )
            {
              v179 = (_DWORD)v151 ? (char *)v325 + 28 : 0LL;
              if ( !memcmp_0(v179, v178, 0x20u) && !lpData )
                goto LABEL_605;
            }
          }
          goto LABEL_482;
        }
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_375:
          ReleaseSRWLockExclusive(v134);
          v24 = v276;
          goto LABEL_400;
        }
        v157 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&iid);
        v158 = 62;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_375;
        }
        v157 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
        v158 = 61;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_375;
      }
      v157 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
      v158 = 60;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v158,
      (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
      v157,
      Sddl);
    goto LABEL_375;
  }
  if ( (v282 & 2) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v146 = JobMoniker::GetPath((JobMoniker *)&v323);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v146);
    }
    Sddl = -2147024894;
LABEL_397:
    ReleaseSRWLockExclusive(v134);
    goto LABEL_398;
  }
  v270[0] = 1;
  TokenInformationLength = 0;
  JobMoniker::_GenId((JobMoniker *)&v323);
  *(_QWORD *)&EventDescriptor.Id = 0;
  LODWORD(EventDescriptor.Keyword) = 0;
  Sddl = RpcServer::CreateRegistrationPath(v150, v271, (struct JobSecurity *)&EventDescriptor, hObject);
  v272 = Sddl;
  if ( Sddl < 0 )
  {
    v152 = *(void **)&EventDescriptor.Id;
    if ( *(_QWORD *)&EventDescriptor.Id )
      LocalFree(*(HLOCAL *)&EventDescriptor.Id);
    goto LABEL_499;
  }
  v153 = *(void **)&EventDescriptor.Id;
  Sddl = JobAccessCheck(hObject, *(PSECURITY_DESCRIPTOR *)&EventDescriptor.Id, 2u);
  v272 = Sddl;
  if ( Sddl < 0 )
  {
    if ( v153 )
      LocalFree(v153);
    goto LABEL_499;
  }
  if ( v153 )
    LocalFree(v153);
LABEL_482:
  *(_QWORD *)&EventDescriptor.Id = 0;
  LODWORD(EventDescriptor.Keyword) = 0;
  if ( v270[0] || lpMem )
  {
    v193 = hObject;
    if ( lpMem )
    {
      v195 = SysAllocString((const OLECHAR *)lpMem);
      v197 = v195;
      bstrString = v195;
      if ( !v195 )
        ATL::PrivateAtlThrow(0x8007000E);
      goto LABEL_518;
    }
LABEL_513:
    if ( bstr )
    {
      v194 = SysStringByteLen(bstr);
      v195 = SysAllocStringByteLen((LPCSTR)bstr, v194);
      v196 = v195;
      bstrString = v195;
      if ( bstr && !v195 )
        ATL::PrivateAtlThrow(0x8007000E);
      v274 = 2;
      v285 = 2;
      v197 = bstrString;
LABEL_519:
      Sddl = JobStore::GenerateJobSecurity(
               (JobStore *)Sid,
               v271,
               v195,
               0,
               v193,
               (PSECURITY_DESCRIPTOR *)&EventDescriptor);
      v272 = Sddl;
      v198 = v274;
      if ( (v274 & 4) != 0 )
      {
        v274 &= ~4u;
        v285 = v198 & 0xFFFFFFFB;
        SysFreeString(v197);
        v198 = v274;
      }
      if ( (v198 & 2) != 0 )
      {
        v274 = v198 & 0xFFFFFFFD;
        v285 = v198 & 0xFFFFFFFD;
        SysFreeString(v196);
      }
      if ( Sddl < 0 )
      {
        v152 = *(void **)&EventDescriptor.Id;
        if ( *(_QWORD *)&EventDescriptor.Id )
          goto LABEL_497;
        v189 = v270[0];
        goto LABEL_526;
      }
LABEL_491:
      ReturnLength[0] = v282 & 0x10;
      if ( (v282 & 0x10) != 0 )
      {
        v189 = v270[0];
      }
      else
      {
        v183 = *((_QWORD *)v325 + 8);
        v277 = v183;
        if ( v183 )
        {
          v184 = User::s_cs;
          EnterCriticalSection(User::s_cs);
          ++*(_DWORD *)(v183 + 44);
          LeaveCriticalSection(v184);
        }
        if ( User::IsAlias((JobBucket *)((char *)v325 + 64)) )
        {
          v186 = (CredStore *)CredStore::g_pCommonStore;
          v187 = User::GetAccount(v185, &bstrString);
          v188 = (const unsigned __int16 *)_bstr_t::operator unsigned short const *(v187);
          Sddl = CredStore::ResolveAlias(v186, v188, (struct User *)&v277);
          v272 = Sddl;
          _bstr_t::~_bstr_t((_bstr_t *)&bstrString);
          if ( Sddl < 0 )
          {
            wmi::AutoRef<User::UserEntry>::Release(&v277);
            v152 = *(void **)&EventDescriptor.Id;
            if ( !*(_QWORD *)&EventDescriptor.Id )
              goto LABEL_498;
LABEL_497:
            LocalFree(v152);
            *(_QWORD *)&EventDescriptor.Id = 0;
            goto LABEL_498;
          }
          v183 = v277;
        }
        v199 = 0;
        v189 = v270[0];
        if ( !v270[0] && !lpMem && !bstr )
          v199 = (void *)*((_QWORD *)v13 + 4);
        Sddl = JobSecurity::AddRemovePrincipalAce((JobSecurity *)&EventDescriptor, *(void **)(v183 + 32), v199);
        v272 = Sddl;
        if ( Sddl < 0 )
        {
          wmi::AutoRef<User::UserEntry>::Release(&v277);
          v152 = *(void **)&EventDescriptor.Id;
          if ( *(_QWORD *)&EventDescriptor.Id )
          {
            LocalFree(*(HLOCAL *)&EventDescriptor.Id);
            *(_QWORD *)&EventDescriptor.Id = 0;
LABEL_537:
            v134 = (RTL_SRWLOCK *)TokenHandle;
            goto LABEL_500;
          }
LABEL_526:
          v134 = (RTL_SRWLOCK *)TokenHandle;
          goto LABEL_500;
        }
        wmi::AutoRef<User::UserEntry>::Release(&v277);
      }
      v200 = (JobStore *)Sid;
      if ( v189 )
        updated = JobStore::RegTaskEntryCreate(
                    (JobStore *)Sid,
                    (const struct JobMoniker *)&v323,
                    (const struct JobSecurity *)&EventDescriptor,
                    (const struct Triggers::Trigulator *)v315,
                    (const struct Actions::ActionCollection *)v311,
                    lpData);
      else
        updated = JobStore::UpdateTaskEntry(
                    (JobStore *)Sid,
                    (const struct JobMoniker *)&v323,
                    v151,
                    (const struct Triggers::Trigulator *)v315,
                    (const struct Actions::ActionCollection *)v311,
                    (const struct DynamicTaskInfo *)lpData);
      Sddl = updated;
      v272 = updated;
      if ( updated < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v202 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
            v202,
            Sddl);
        }
        v152 = *(void **)&EventDescriptor.Id;
        if ( *(_QWORD *)&EventDescriptor.Id )
        {
          LocalFree(*(HLOCAL *)&EventDescriptor.Id);
          *(_QWORD *)&EventDescriptor.Id = 0;
          v134 = (RTL_SRWLOCK *)TokenHandle;
          goto LABEL_500;
        }
        goto LABEL_537;
      }
      if ( *(_QWORD *)&EventDescriptor.Id )
      {
        LocalFree(*(HLOCAL *)&EventDescriptor.Id);
        *(_QWORD *)&EventDescriptor.Id = 0;
      }
      RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v277, L"RpcServer::RegisterTask", 1);
      if ( lpMem )
      {
        v204 = SysAllocString((const OLECHAR *)lpMem);
        v206 = v204;
        bstrString = v204;
        if ( !v204 )
          ATL::PrivateAtlThrow(0x8007000E);
      }
      else
      {
        if ( bstr )
        {
          v203 = SysStringByteLen(bstr);
          v204 = SysAllocStringByteLen((LPCSTR)bstr, v203);
          v205 = v204;
          bstrString = v204;
          if ( bstr && !v204 )
            ATL::PrivateAtlThrow(0x8007000E);
          v274 |= 8u;
          v285 = v274;
          v206 = bstrString;
LABEL_559:
          Sddl = JobStore::XmlSaveTaskFile(v200, (const struct JobMoniker *)&v323, v294, v204);
          v272 = Sddl;
          v207 = v274;
          if ( (v274 & 0x10) != 0 )
          {
            v274 &= ~0x10u;
            SysFreeString(v206);
            v207 = v274;
          }
          if ( (v207 & 8) != 0 )
          {
            v274 = v207 & 0xFFFFFFF7;
            SysFreeString(v205);
          }
          if ( Sddl < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v208 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                65,
                (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                v208,
                Sddl);
            }
            if ( (_DWORD)v277 )
              RpcRevertToSelf();
            goto LABEL_498;
          }
          if ( (_DWORD)v277 )
            RpcRevertToSelf();
          if ( ReturnLength[0] )
            goto LABEL_498;
          v209 = v325;
          v210 = *((_QWORD *)v325 + 8);
          *(_QWORD *)ReturnLength = v210;
          if ( v210 )
          {
            v211 = User::s_cs;
            EnterCriticalSection(User::s_cs);
            ++*(_DWORD *)(v210 + 44);
            LeaveCriticalSection(v211);
            v209 = v325;
          }
          if ( User::IsAlias((JobBucket *)((char *)v209 + 64)) )
          {
            v213 = (CredStore *)CredStore::g_pCommonStore;
            v214 = User::GetAccount(v212, &bstrString);
            v215 = (const unsigned __int16 *)_bstr_t::operator unsigned short const *(v214);
            Sddl = CredStore::ResolveAlias(v213, v215, (struct User *)ReturnLength);
            v272 = Sddl;
            _bstr_t::~_bstr_t((_bstr_t *)&bstrString);
            if ( Sddl < 0 )
            {
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                v217 = v274;
              }
              else
              {
                v216 = User::GetAccount((char *)v325 + 64, &bstrString);
                v217 = v274 | 0x20;
                v218 = _bstr_t::operator unsigned short const *(v216);
                v219 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
                WPP_SF_SSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  66,
                  (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                  v219,
                  v218,
                  Sddl);
              }
              if ( (v217 & 0x20) != 0 )
                _bstr_t::~_bstr_t((_bstr_t *)&bstrString);
              goto LABEL_597;
            }
          }
          RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v277, L"RpcServer::RegisterTask", 1);
          v220 = (const struct User *)&v292;
          if ( lpMem )
            v220 = 0;
          Sddl = JobStore::HammerAcl(v200, (const struct JobMoniker *)&v323, (const struct User *)ReturnLength, v220);
          v272 = Sddl;
          if ( Sddl >= 0 )
          {
            if ( !(_DWORD)v277 )
            {
LABEL_597:
              wmi::AutoRef<User::UserEntry>::Release(ReturnLength);
              goto LABEL_498;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v221 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                v221,
                Sddl);
            }
            if ( !(_DWORD)v277 )
              goto LABEL_597;
          }
          RpcRevertToSelf();
          goto LABEL_597;
        }
        v206 = 0;
        bstrString = 0;
        v204 = 0;
      }
      v274 |= 0x10u;
      v285 = v274;
      v205 = bstrString;
      goto LABEL_559;
    }
    v197 = 0;
    bstrString = 0;
    v195 = 0;
LABEL_518:
    v274 = 4;
    v285 = 4;
    v196 = bstrString;
    goto LABEL_519;
  }
  if ( bstr )
  {
    v193 = hObject;
    goto LABEL_513;
  }
  v180 = SecurityDescriptor;
  if ( !SecurityDescriptor )
  {
    *(_QWORD *)&EventDescriptor.Id = 0;
    LODWORD(EventDescriptor.Keyword) = 0;
    goto LABEL_491;
  }
  v181 = RtlLengthSecurityDescriptor(SecurityDescriptor);
  v182 = LocalAlloc(0, v181);
  v152 = *(void **)&EventDescriptor.Id;
  if ( *(_QWORD *)&EventDescriptor.Id )
    LocalFree(*(HLOCAL *)&EventDescriptor.Id);
  *(_QWORD *)&EventDescriptor.Id = v182;
  if ( v182 )
  {
    LODWORD(EventDescriptor.Keyword) = v181;
    memcpy_0(v182, v180, v181);
    goto LABEL_491;
  }
  Sddl = -2147024882;
  v272 = -2147024882;
LABEL_498:
  v134 = (RTL_SRWLOCK *)TokenHandle;
LABEL_499:
  v189 = v270[0];
LABEL_500:
  if ( Sddl < 0 )
  {
    if ( v189 )
    {
      RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)ReturnLength, L"RpcServer::RegisterTask", 1);
      v190 = (HKEY *)Sid;
      JobStore::FileRemoveTaskXml((JobStore *)Sid, (const struct JobMoniker *)&v323);
      if ( ReturnLength[0] )
        RpcRevertToSelf();
      if ( (int)JobStore::RemoveTaskEntryP(v190, &v323, 0) >= 0 )
        JobStore::FlushTaskEntryP(v191, v190[2]);
      v192 = v293;
    }
    else
    {
      v222 = JobStore::GenerateTaskXmlFromCollections(v152, &iid, v319, v318, &v293);
      v192 = v293;
      if ( v222 >= 0 && (int)JobStore::ComputeHash((struct JobMoniker *)&iid, v293) >= 0 )
      {
        RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)ReturnLength, L"RpcServer::RegisterTask", 1);
        JobStore::XmlSaveTaskFile((JobStore *)Sid, (const struct JobMoniker *)&iid, v192, StringSecurityDescriptor);
        if ( ReturnLength[0] )
          RpcRevertToSelf();
      }
      JobStore::UpdateTaskEntry(
        (JobStore *)Sid,
        (const struct JobMoniker *)&iid,
        v223,
        (const struct Triggers::Trigulator *)v319,
        (const struct Actions::ActionCollection *)v318,
        0);
    }
    v84 = v271;
    if ( (*(_DWORD *)(v328 + 16) & 0x200000) != 0 )
    {
      if ( !PlugIn::IsRegistering((PlugIn *)&PlugIn::s_singleton, v271, v291) )
        PlugIn::RegisterTask((PlugIn *)&PlugIn::s_singleton, v84, v192, StringSecurityDescriptor, v282, v329);
    }
    else
    {
      PlugIn::DeleteTask((PlugIn *)&PlugIn::s_singleton, v271);
    }
    goto LABEL_375;
  }
  v176 = TokenInformationLength;
LABEL_605:
  if ( ((v176 - 0x40000) & 0xFFFBFFFF) == 0 )
  {
    Sddl = CredStore::DeleteNtCredential((CredStore *)CredStore::g_pCommonStore, (const struct User *)&v292, (bool)v151);
    v272 = Sddl;
    if ( Sddl < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v224 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          v224,
          Sddl);
      }
      Sddl = 0;
      v272 = 0;
    }
  }
  ReleaseSRWLockExclusive(v134);
  if ( v270[0] )
    goto LABEL_633;
  RpcServer::FlushTriggers((const struct JobMoniker *)&v323);
  if ( (*(_DWORD *)(v328 + 16) & 0x2000000) != 0 || (*((_DWORD *)v325 + 4) & 0x2000000) == 0 )
    goto LABEL_623;
  Sddl = RpcServer::FlushTriggers((const struct JobMoniker *)&iid);
  v272 = Sddl;
  if ( tsched::IsErrorNotFound((tsched *)(unsigned int)Sddl, v225) )
  {
    Sddl = 0;
    v272 = 0;
    goto LABEL_623;
  }
  if ( Sddl >= 0 )
  {
LABEL_623:
    if ( (*(_DWORD *)(v328 + 16) & 0x2000000) != 0 && (*((_DWORD *)v325 + 4) & 0x2000000) == 0 )
    {
      Sddl = (*((__int64 (__fastcall **)(void ***, GUID *))UbpmProxySingleton::s_singleton[0] + 1))(
               UbpmProxySingleton::s_singleton,
               &iid);
      v272 = Sddl;
      if ( tsched::IsErrorNotFound((tsched *)(unsigned int)Sddl, v227) )
      {
        Sddl = 0;
        v272 = 0;
        goto LABEL_633;
      }
      if ( Sddl < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v228 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            70,
            (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
            v228,
            Sddl);
        }
        Sddl = 267035;
        v272 = 267035;
        v84 = v271;
        v24 = v276;
        goto LABEL_400;
      }
    }
LABEL_633:
    v229 = v282;
    if ( (*((_DWORD *)v325 + 4) & 0x2000000) != 0 )
    {
      v230 = v316;
      for ( j = (_QWORD *)*v316; j != v230; j = (_QWORD *)*j )
      {
        v232 = j[2];
        if ( v232 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v232 + 72LL))(v232) == 34952 )
          {
            RpcAutoImpersonate::RpcAutoImpersonate(
              (RpcAutoImpersonate *)&TokenInformationLength,
              L"RpcServer::RegisterTask",
              1);
            LODWORD(v277) = -1;
            bstrString = 0;
            ReturnLength[0] = 0;
            lpMem = 0;
            v233 = GetCurrentThread();
            if ( OpenThreadToken(v233, 8u, 1, &lpMem)
              && GetTokenInformation(lpMem, TokenSessionId, &v277, 4u, ReturnLength) )
            {
              Sddl = 0;
              if ( (unsigned __int8)IsUMgrQueryUserContextPresent() )
              {
                v235 = UMgrQueryUserContext(lpMem, &bstrString);
                Sddl = v235;
                if ( v235 == -2147023584 || v235 == -2147023652 )
                  Sddl = 0;
              }
            }
            else
            {
              v234 = GetLastError();
              Sddl = v234;
              if ( v234 > 0 )
                Sddl = (unsigned __int16)v234 | 0x80070000;
              if ( Sddl >= 0 )
                Sddl = -2147467259;
            }
            if ( (char *)lpMem - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            {
              CloseHandle(lpMem);
              lpMem = 0;
            }
            v272 = Sddl;
            if ( TokenInformationLength )
              RpcRevertToSelf();
            break;
          }
          v230 = v316;
        }
      }
      if ( Sddl >= 0 )
      {
        UserDataa = (const struct _GUID *)v311;
        UserDataCounta = (int *)v315;
        Sddl = (*(__int64 (__fastcall **)(void ***, _QWORD, GUID *, _QWORD))UbpmProxySingleton::s_singleton[0])(
                 UbpmProxySingleton::s_singleton,
                 0,
                 &v323,
                 v270[0]);
        v272 = Sddl;
      }
      tsched::SecretGuard::Erase((tsched::SecretGuard *)&v299);
      wmi::AutoVectorPtr<unsigned short>::operator=(&v296, 0);
      v300 = v299;
      v229 = v282;
    }
    else
    {
      LOBYTE(EventDescriptor.Id) = 0;
      *(_DWORD *)((char *)&EventDescriptor.Id + 1) = *(_DWORD *)((char *)&v332.Ptr + 1);
      *(_WORD *)&EventDescriptor.Opcode = *(_WORD *)((char *)&v332.Ptr + 5);
      HIBYTE(EventDescriptor.Task) = HIBYTE(v332.Ptr);
      EventDescriptor.Keyword = -1;
      LOBYTE(v295[0]) = 0;
      *(_DWORD *)((char *)v295 + 1) = *(_DWORD *)((char *)&v332.Ptr + 1);
      *(_WORD *)((char *)v295 + 5) = *(_WORD *)((char *)&v332.Ptr + 5);
      HIBYTE(v295[0]) = HIBYTE(v332.Ptr);
      v295[1] = 0;
      LODWORD(UserDataCounta) = (v282 & 0x20) == 0;
      Sddl = Triggers::Trigulator::RegisterAll(v315, &v323, v295, &EventDescriptor);
      if ( Sddl == 1 )
        Sddl = 0;
      v272 = Sddl;
    }
    v84 = v271;
    v237 = v304;
    if ( Sddl < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v238 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          v238,
          Sddl);
      }
      EventManager::EvtReport(v236, &TASK_REGISTERED_WITHOUT_SOME_TRIGGERS, v276, Sddl, UserDataCounta, UserDataa);
      Sddl = 267035;
    }
    v239 = &TASK_DISABLED;
    if ( !v237 )
      v239 = &JOB_REGISTERED;
    v93 = (v229 & 4) == 0;
    v240 = (const struct _EVENT_DESCRIPTOR *)TASK_UPDATED;
    if ( v93 )
      v240 = v239;
    v241 = v270[0];
    if ( !v270[0] || &JOB_REGISTERED == v240 )
    {
      EventManager::EvtReport(v236, v240, v276, *(const unsigned __int16 **)v286, UserDataCounta, UserDataa);
      if ( !v241 )
      {
        v248 = JobMoniker::GetPath((JobMoniker *)&v323);
        v245 = Auditor::AuditJobOperation(g_pAuditor, 2, v248, v14);
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_683;
        }
        v246 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
        v247 = 73;
        goto LABEL_682;
      }
    }
    else
    {
      v242 = (const unsigned __int16 **)v286;
      EventManager::EvtReport(v236, &JOB_REGISTERED, v276, *(const unsigned __int16 **)v286, UserDataCounta, UserDataa);
      EventManager::EvtReport(v243, v240, v276, *v242, UserDataCountc, UserDatab);
    }
    v244 = JobMoniker::GetPath((JobMoniker *)&v323);
    v245 = Auditor::AuditJobOperation(g_pAuditor, 0, v244, v14);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_683;
    }
    v246 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
    v247 = 72;
LABEL_682:
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v247,
      (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
      v246,
      v245);
LABEL_683:
    if ( v306 )
    {
      v24 = 0;
      *v306 = v276;
    }
    else
    {
      v24 = v276;
    }
    if ( v283 == 267036 && Sddl != 267035 )
      Sddl = 267036;
    goto LABEL_400;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v226 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v323);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
      v226,
      Sddl);
  }
  Sddl = 267035;
  v272 = 267035;
  v84 = v271;
  v24 = v276;
LABEL_400:
  if ( (unsigned int)dword_1800BC358 > 4 )
  {
    *(_DWORD *)IdentifierAuthority.Value = Sddl;
    v147 = v291;
    if ( v291 )
    {
      v148 = -1;
      do
        ++v148;
      while ( v291[v148] );
      v149 = 2 * v148 + 2;
    }
    else
    {
      v147 = (unsigned __int16 *)&ChannelPath;
      v149 = 2;
    }
    v345 = v147;
    v346 = v149;
    v347 = 0;
    p_IdentifierAuthority = &IdentifierAuthority;
    v344 = 4;
    if ( v84 )
    {
      v252 = -1;
      do
        ++v252;
      while ( v84[v252] );
      v253 = 2 * v252 + 2;
    }
    else
    {
      v84 = (unsigned __int16 *)&ChannelPath;
      v253 = 2;
    }
    v340 = v84;
    v341 = v253;
    v342 = 0;
    v332.Ptr = 0x2040B000000LL;
    *(_QWORD *)&v332.Size = 0;
    TokenInformation.Ptr = (ULONGLONG)off_1800BC360;
    TokenInformation.Size = *(unsigned __int16 *)off_1800BC360;
    TokenInformation.Reserved = 2;
    v337 = byte_1800ADAEB;
    v338 = 40;
    v339 = 1;
    v290 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&v332, 0, 0, 5u, &TokenInformation);
  }
  v254 = v301;
  if ( v301 )
  {
    v255 = -1;
    do
      ++v255;
    while ( *(_WORD *)&v301[2 * v255] );
    for ( k = 2 * v255; k; --k )
      *v254++ = 0;
  }
  v257 = v325;
  if ( v325 && _InterlockedExchangeAdd((volatile signed __int32 *)v325 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v257)(v257, 1);
  v325 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v324);
  SysFreeString(v14);
  SysFreeString(bstr);
  SysFreeString(v302);
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v311);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v315);
  _bstr_t::~_bstr_t((_bstr_t *)&v303);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v258 = v300;
  if ( v300 )
  {
    v259 = -1;
    do
      ++v259;
    while ( *(_WORD *)&v300[2 * v259] );
    for ( m = 2 * v259; m; --m )
      *v258++ = 0;
  }
  if ( v296 )
    HeapFree(g_PrivateHeap, 0, v296);
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v318);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v319);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  v261 = (void (__fastcall ***)(_QWORD, __int64))v328;
  if ( v328 && _InterlockedExchangeAdd((volatile signed __int32 *)(v328 + 8), 0xFFFFFFFF) == 1 )
    (**v261)(v261, 1);
  v328 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)v327);
  wmi::AutoRef<User::UserEntry>::Release(&v292);
  if ( StringSecurityDescriptor )
    HeapFree(g_PrivateHeap, 0, (LPVOID)StringSecurityDescriptor);
  if ( v293 )
    HeapFree(g_PrivateHeap, 0, v293);
  if ( v24 )
    HeapFree(g_PrivateHeap, 0, v24);
  return (unsigned int)Sddl;
}

```

## disassembly

```asm
0x180045df0  push    rbx
0x180045df2  push    rsi
0x180045df3  push    rdi
0x180045df4  push    r12
0x180045df6  push    r13
0x180045df8  push    r14
0x180045dfa  push    r15
0x180045dfc  sub     rsp, 820h
0x180045e03  mov     rax, cs:__security_cookie
0x180045e0a  xor     rax, rsp
0x180045e0d  mov     [rsp+858h+var_48], rax
0x180045e15  mov     edi, r9d
0x180045e18  mov     rax, r8
0x180045e1b  mov     [rsp+858h+var_738], rax
0x180045e23  mov     r15, rdx
0x180045e26  mov     [rsp+858h+var_7D0], rdx
0x180045e2e  mov     [rsp+858h+bstrString], rcx
0x180045e36  mov     [rsp+858h+var_698], rax
0x180045e3e  mov     rax, [rsp+858h+arg_20]
0x180045e46  mov     [rsp+858h+lpMem], rax
0x180045e4e  mov     rbx, [rsp+858h+arg_38]
0x180045e56  mov     [rsp+858h+var_760], rbx
0x180045e5e  mov     rax, [rsp+858h+arg_40]
0x180045e66  mov     [rsp+858h+lpData], rax
0x180045e6e  mov     rax, [rsp+858h+arg_48]
0x180045e76  mov     [rsp+858h+var_6B8], rax
0x180045e7e  mov     r12, [rsp+858h+arg_50]
0x180045e86  mov     [rsp+858h+var_720], r12
0x180045e8e  xor     r13d, r13d
0x180045e91  mov     eax, r13d
0x180045e94  mov     [rsp+858h+var_7B8], eax
0x180045e9b  mov     [rsp+858h+var_768], eax
0x180045ea2  mov     [rsp+858h+var_7C8], r13d
0x180045eaa  mov     [rsp+858h+var_7B0], rax
0x180045eb2  mov     [rsp+858h+var_6F8], rax
0x180045eba  mov     [rsp+858h+var_728], r13
0x180045ec2  mov     [rsp+858h+StringSecurityDescriptor], r13
0x180045eca  mov     esi, r13d
0x180045ecd  mov     [rsp+858h+var_730], r13
0x180045ed5  xor     r8d, r8d; unsigned __int16 *
0x180045ed8  xor     edx, edx; psz
0x180045eda  lea     rcx, [rsp+858h+iid]; lpiid
0x180045ee2  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x180045ee7  nop
0x180045ee8  mov     [rsp+858h+SecurityDescriptor], r13
0x180045ef0  mov     [rsp+858h+var_6A8], r13d
0x180045ef8  lea     rcx, [rsp+858h+var_608]; this
0x180045f00  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180045f05  nop
0x180045f06  lea     rcx, [rsp+858h+var_620]; this
0x180045f0e  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x180045f13  nop
0x180045f14  mov     [rsp+858h+var_708], r13
0x180045f1c  mov     eax, r13d
0x180045f1f  mov     [rsp+858h+var_6E8], rax
0x180045f27  mov     [rsp+858h+var_6F0], rax
0x180045f2f  mov     [rsp+858h+hObject], r13
0x180045f37  mov     [rsp+858h+var_6D0], r13
0x180045f3f  xorps   xmm0, xmm0
0x180045f42  movups  [rsp+858h+var_670], xmm0
0x180045f4a  mov     [rsp+858h+var_660], rax
0x180045f52  lea     rcx, [rsp+858h+var_658]; this
0x180045f5a  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180045f5f  nop
0x180045f60  lea     rcx, [rsp+858h+var_690]; this
0x180045f68  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x180045f6d  nop
0x180045f6e  mov     [rsp+858h+var_6D8], r13
0x180045f76  mov     [rsp+858h+bstr], r13
0x180045f7e  mov     r14d, r13d
0x180045f81  mov     [rsp+858h+var_6A0], r13
0x180045f89  xor     r8d, r8d; unsigned __int16 *
0x180045f8c  mov     rdx, r15; psz
0x180045f8f  lea     rcx, [rsp+858h+var_558]; lpiid
0x180045f97  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x180045f9c  nop
0x180045f9d  cmp     [rsp+858h+arg_30], r13d
0x180045fa5  jbe     short loc_180045FAD
0x180045fa7  mov     rax, [rbx+8]
0x180045fab  jmp     short loc_180045FB0
0x180045fad  mov     rax, r13
0x180045fb0  mov     [rsp+858h+var_6E0], rax
0x180045fb8  mov     [rsp+858h+var_678], rax
0x180045fc0  mov     eax, cs:dword_1800BC358
0x180045fc6  cmp     eax, 5
0x180045fc9  jbe     loc_180046087
0x180045fcf  mov     dword ptr [rsp+858h+EventDescriptor.Id], 0B000000h
0x180045fda  movzx   eax, cs:word_1800ADAC1
0x180045fe1  mov     dword ptr [rsp+858h+EventDescriptor.Level], eax
0x180045fe8  mov     [rsp+858h+EventDescriptor.Keyword], r13
0x180045ff0  mov     rax, cs:off_1800BC360
0x180045ff7  mov     [rsp+858h+var_C8.Ptr], rax
0x180045fff  movzx   eax, word ptr [rax]
0x180046002  mov     [rsp+858h+var_C8.Size], eax
0x180046009  mov     dword ptr [rsp+858h+var_C8.0Ch], 2
0x180046014  lea     rax, byte_1800ADACB
0x18004601b  mov     [rsp+858h+var_B8], rax
0x180046023  mov     [rsp+858h+var_B0], 14h
0x18004602e  mov     [rsp+858h+var_AC], 1
0x180046039  lea     rax, _TraceLoggingMetadataEnd
0x180046040  lea     rcx, _TraceLoggingMetadata
0x180046047  sub     eax, ecx
0x180046049  mov     [rsp+858h+var_77C], eax
0x180046050  mov     eax, [rsp+858h+var_77C]
0x180046057  lea     rax, [rsp+858h+var_C8]
0x18004605f  mov     [rsp+858h+UserData], rax; struct _GUID *
0x180046064  mov     [rsp+858h+UserDataCount], 2; void *
0x18004606c  xor     r9d, r9d; RelatedActivityId
0x18004606f  xor     r8d, r8d; ActivityId
0x180046072  lea     rdx, [rsp+858h+EventDescriptor]; EventDescriptor
0x18004607a  mov     rcx, cs:RegHandle; RegHandle
0x180046081  call    cs:__imp_EventWriteTransfer
0x180046087  xor     ecx, ecx; BindingHandle
0x180046089  call    cs:__imp_RpcImpersonateClient
0x18004608f  mov     ebx, eax
0x180046091  test    eax, eax
0x180046093  jnz     loc_180049ACC
0x180046099  mov     [rsp+858h+TokenInformationLength], 58h ; 'X'
0x1800460a4  mov     [rsp+858h+TokenHandle], r13
0x1800460ac  mov     [rsp+858h+var_7D8], 0
0x1800460b4  call    cs:__imp_GetCurrentThread
0x1800460ba  mov     rcx, rax; ThreadHandle
0x1800460bd  lea     r9, [rsp+858h+TokenHandle]; TokenHandle
0x1800460c5  mov     edx, 8; DesiredAccess
0x1800460ca  mov     r8d, 1; OpenAsSelf
0x1800460d0  call    cs:__imp_OpenThreadToken
0x1800460d6  test    eax, eax
0x1800460d8  jz      loc_18004621B
0x1800460de  lea     rax, [rsp+858h+TokenInformationLength]
0x1800460e6  mov     qword ptr [rsp+858h+UserDataCount], rax; ReturnLength
0x1800460eb  mov     r9d, [rsp+858h+TokenInformationLength]; TokenInformationLength
0x1800460f3  lea     r8, [rsp+858h+TokenInformation]; TokenInformation
0x1800460fb  mov     edx, 19h; TokenInformationClass
0x180046100  mov     rcx, [rsp+858h+TokenHandle]; TokenHandle
0x180046108  call    cs:__imp_GetTokenInformation
0x18004610e  test    eax, eax
0x180046110  jz      loc_180046203
0x180046116  mov     dword ptr [rsp+858h+IdentifierAuthority.Value], 0
0x180046121  mov     word ptr [rsp+858h+IdentifierAuthority.Value+4], 1000h
0x18004612b  mov     [rsp+858h+var_7A0], r13
0x180046133  lea     rax, [rsp+858h+var_7A0]
0x18004613b  mov     [rsp+858h+Sid], rax; Sid
0x180046140  mov     [rsp+858h+SubAuthority7], r13d; SubAuthority7
0x180046145  mov     [rsp+858h+SubAuthority6], r13d; SubAuthority6
0x18004614a  mov     [rsp+858h+SubAuthority5], r13d; SubAuthority5
0x18004614f  mov     [rsp+858h+SubAuthority4], r13d; SubAuthority4
0x180046154  mov     dword ptr [rsp+858h+UserData], r13d; SubAuthority3
0x180046159  mov     [rsp+858h+UserDataCount], r13d; SubAuthority2
0x18004615e  xor     r9d, r9d; SubAuthority1
0x180046161  mov     r8d, 2000h; SubAuthority0
0x180046167  mov     dl, 1; SubAuthorityCount
0x180046169  lea     rcx, [rsp+858h+IdentifierAuthority]; IdentifierAuthority
0x180046171  call    cs:__imp_RtlAllocateAndInitializeSid
0x180046177  test    eax, eax
0x180046179  js      short loc_1800461E9
0x18004617b  lea     r8, [rsp+858h+var_7D8]
0x180046183  mov     rdx, [rsp+858h+var_7A0]
0x18004618b  mov     rcx, [rsp+858h+TokenInformation]
0x180046193  call    cs:__imp_RtlSidDominates
0x180046199  mov     ebx, eax
0x18004619b  mov     rcx, [rsp+858h+var_7A0]; Sid
0x1800461a3  call    cs:__imp_RtlFreeSid
0x1800461a9  test    ebx, ebx
0x1800461ab  jns     short loc_1800461C7
0x1800461ad  mov     ecx, ebx; Status
0x1800461af  call    cs:__imp_RtlNtStatusToDosError
0x1800461b5  mov     ebx, eax
0x1800461b7  mov     rcx, [rsp+858h+TokenHandle]; hObject
0x1800461bf  call    cs:__imp_CloseHandle
0x1800461c5  jmp     short loc_180046223
0x1800461c7  mov     ebx, r13d
0x1800461ca  cmp     [rsp+858h+var_7D8], r13b
0x1800461d2  jnz     short loc_18004620B
0x1800461d4  mov     ebx, 5
0x1800461d9  mov     rcx, [rsp+858h+TokenHandle]; hObject
0x1800461e1  call    cs:__imp_CloseHandle
0x1800461e7  jmp     short loc_180046223
0x1800461e9  mov     ecx, eax; Status
0x1800461eb  call    cs:__imp_RtlNtStatusToDosError
0x1800461f1  mov     ebx, eax
0x1800461f3  mov     rcx, [rsp+858h+TokenHandle]; hObject
0x1800461fb  call    cs:__imp_CloseHandle
0x180046201  jmp     short loc_180046223
0x180046203  call    cs:__imp_GetLastError
0x180046209  mov     ebx, eax
0x18004620b  mov     rcx, [rsp+858h+TokenHandle]; hObject
0x180046213  call    cs:__imp_CloseHandle
0x180046219  jmp     short loc_180046223
0x18004621b  call    cs:__imp_GetLastError
0x180046221  mov     ebx, eax
0x180046223  test    ebx, ebx
0x180046225  jnz     loc_1800496F5
0x18004622b  call    cs:__imp_RpcRevertToSelf
0x180046231  mov     rax, [rsp+858h+var_6B8]
0x180046239  test    rax, rax
0x18004623c  jz      short loc_180046241
0x18004623e  mov     [rax], r13
0x180046241  test    r12, r12
0x180046244  jz      short loc_18004624A
0x180046246  mov     [r12], r13
0x18004624a  mov     eax, [rsp+858h+arg_28]
0x180046251  cmp     eax, 6
0x180046254  jbe     short loc_1800462A2
0x180046256  lea     r12, WPP_GLOBAL_Control
0x18004625d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046264  cmp     rcx, r12
0x180046267  jz      short loc_180046294
0x180046269  test    dword ptr [rcx+1Ch], 10000h
0x180046270  jz      short loc_180046294
0x180046272  cmp     byte ptr [rcx+19h], 2
0x180046276  jb      short loc_180046294
0x180046278  mov     edx, 1Dh
0x18004627d  mov     [rsp+858h+UserDataCount], eax
0x180046281  mov     r9, r15
0x180046284  lea     r8, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids
0x18004628b  mov     rcx, [rcx+10h]
0x18004628f  call    WPP_SF_Sd
0x180046294  mov     r15d, 80070057h
0x18004629a  mov     r12, r13
0x18004629d  jmp     loc_180047C48
0x1800462a2  mov     r8, [rsp+858h+var_738]
0x1800462aa  test    r8, r8
0x1800462ad  jnz     short loc_1800462F7
0x1800462af  lea     r12, WPP_GLOBAL_Control
0x1800462b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462bd  cmp     rcx, r12
0x1800462c0  jz      short loc_180046294
0x1800462c2  test    dword ptr [rcx+1Ch], 10000h
0x1800462c9  jz      short loc_180046294
0x1800462cb  cmp     byte ptr [rcx+19h], 2
0x1800462cf  jb      short loc_180046294
0x1800462d1  mov     edx, 1Eh
0x1800462d6  mov     r9, r15
0x1800462d9  lea     r8, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids
0x1800462e0  mov     rcx, [rcx+10h]
0x1800462e4  call    WPP_SF_S
0x1800462e9  mov     r15d, 80070057h
0x1800462ef  mov     r12, r13
0x1800462f2  jmp     loc_180047C48
0x1800462f7  mov     edx, 2
0x1800462fc  test    edi, edi
0x1800462fe  cmovnz  edx, edi
0x180046301  mov     [rsp+858h+var_780], edx
0x180046308  mov     [rsp+858h+var_740], edx
0x18004630f  test    edx, 0FFFFFFC0h
0x180046315  jnz     loc_1800496A1
0x18004631b  test    dl, 7
0x18004631e  jz      loc_1800496A1
0x180046324  test    edx, 0FFFFFFFEh
0x18004632a  setnz   cl
0x18004632d  test    dl, 1
0x180046330  setnz   al
0x180046333  test    al, cl
0x180046335  jnz     loc_1800496A1
0x18004633b  mov     edi, [rsp+858h+arg_30]
0x180046342  test    edi, edi
0x180046344  jnz     short loc_18004638D
0x180046346  cmp     [rsp+858h+var_760], 0
0x18004634f  jz      loc_180046418
0x180046355  lea     r12, WPP_GLOBAL_Control
0x18004635c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046363  cmp     rcx, r12
0x180046366  jz      loc_180046294
0x18004636c  test    dword ptr [rcx+1Ch], 10000h
0x180046373  jz      loc_180046294
0x180046379  cmp     byte ptr [rcx+19h], 2
0x18004637d  jb      loc_180046294
0x180046383  mov     edx, 20h ; ' '
0x180046388  jmp     loc_1800462D6
0x18004638d  mov     r9, [rsp+858h+var_760]
0x180046395  test    dword ptr [r9+10h], 0FFFFFFFEh
0x18004639d  jz      short loc_1800463D7
0x18004639f  lea     r12, WPP_GLOBAL_Control
0x1800463a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463ad  cmp     rcx, r12
0x1800463b0  jz      loc_180046294
0x1800463b6  test    dword ptr [rcx+1Ch], 10000h
0x1800463bd  jz      loc_180046294
0x1800463c3  cmp     byte ptr [rcx+19h], 2
0x1800463c7  jb      loc_180046294
0x1800463cd  mov     edx, 21h ; '!'
0x1800463d2  jmp     loc_1800462D6
0x1800463d7  cmp     edi, 1
0x1800463da  jbe     short loc_180046418
0x1800463dc  lea     r12, WPP_GLOBAL_Control
0x1800463e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463ea  cmp     rcx, r12
0x1800463ed  jz      loc_180046294
0x1800463f3  test    dword ptr [rcx+1Ch], 10000h
0x1800463fa  jz      loc_180046294
0x180046400  cmp     byte ptr [rcx+19h], 2
0x180046404  jb      loc_180046294
0x18004640a  mov     edx, 22h ; '"'
0x18004640f  mov     [rsp+858h+UserDataCount], edi
0x180046413  jmp     loc_180046281
0x180046418  test    dl, 1
0x18004641b  jz      loc_180046614
0x180046421  mov     [rsp+858h+var_7A0], r13
0x180046429  lea     rdx, [rsp+858h+var_7A0]
0x180046431  mov     rcx, r8
  ... truncated ...
```
