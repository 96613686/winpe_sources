# RpcServer::RegisterTask(ushort const *,ushort const *,ulong,ushort const *,ulong,ulong,_TASK_USER_CRED const *,DynamicTaskInfo const *,ushort * *,_TASK_XML_ERROR_INFO * *)

- ea: `0x180047ee0`
- end: `0x18004bddc`
- name: `?RegisterTask@RpcServer@@QEAAJPEBG0K0KKPEBU_TASK_USER_CRED@@PEBUDynamicTaskInfo@@PEAPEAGPEAPEAU_TASK_XML_ERROR_INFO@@@Z`
- size: `16124`
- prototype: `int(RpcServer *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, const struct _TASK_USER_CRED *, const struct DynamicTaskInfo *, unsigned __int16 **, struct _TASK_XML_ERROR_INFO **)`
- caller_count: `2`
- callee_count: `95`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180047e60`
- `0x18007a83c`

## callees

- `0x180002260`
- `0x1800044b0`
- `0x1800044fc`
- `0x180007b44`
- `0x18000ba20`
- `0x18000bb10`
- `0x18000bc60`
- `0x18000cc70`
- `0x18000ce30`
- `0x18000fe50`
- `0x180010390`
- `0x180011e40`
- `0x180013530`
- `0x1800138d8`
- `0x180013a90`
- `0x1800141e0`
- `0x180014f48`
- `0x180016630`
- `0x18001722c`
- `0x180017740`
- `0x18001d130`
- `0x18001ea40`
- `0x18001fe44`
- `0x180020350`
- `0x1800204e0`
- `0x1800206a0`
- `0x18002123c`
- `0x180021260`
- `0x180021ba0`
- `0x180022aa0`
- `0x1800246a8`
- `0x180024da0`
- `0x180025a3c`
- `0x180025de4`
- `0x180025e70`
- `0x180027910`
- `0x18002b210`
- `0x18002c470`
- `0x18002db74`
- `0x18002dbc4`
- `0x18002f814`
- `0x180030620`
- `0x180031a40`
- `0x180036020`
- `0x180037490`
- `0x1800375e0`
- `0x180039fd0`
- `0x18003a1f0`
- `0x18003b250`
- `0x18003ba40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004a763`
- `OLEAUT32!__imp_SysAllocString` at `0x18004ac63`
- `OLEAUT32!__imp_SysAllocString` at `0x18004a763`
- `OLEAUT32!__imp_SysAllocString` at `0x18004ac63`
- `OLEAUT32!__imp_SysFreeString` at `0x18004884b`
- `OLEAUT32!__imp_SysFreeString` at `0x180048c8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180048f36`
- `OLEAUT32!__imp_SysFreeString` at `0x1800494cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18004953b`
- `OLEAUT32!__imp_SysFreeString` at `0x180049c26`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a6f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a723`
- `OLEAUT32!__imp_SysFreeString` at `0x18004aac4`
- `OLEAUT32!__imp_SysFreeString` at `0x18004aae8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb84`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb99`
- `OLEAUT32!__imp_SysFreeString` at `0x18004884b`
- `OLEAUT32!__imp_SysFreeString` at `0x180048c8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180048f36`
- `OLEAUT32!__imp_SysFreeString` at `0x1800494cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18004953b`
- `OLEAUT32!__imp_SysFreeString` at `0x180049c26`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a6f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a723`
- `OLEAUT32!__imp_SysFreeString` at `0x18004aac4`
- `OLEAUT32!__imp_SysFreeString` at `0x18004aae8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb84`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bb99`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004a618`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004a9f3`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004a618`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004a9f3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18004a62e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18004aa09`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18004a62e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18004aa09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004958f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b2f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004958f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b2f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048302`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800495bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004960c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049693`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b3c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bbe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048302`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800495bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004960c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049693`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b3c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bbe2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049407`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004944f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049407`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004944f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049a7e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049a7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049b64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049fb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a01b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a0b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a133`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a39c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a46e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004af8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b035`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049b64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049fb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a01b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a0b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a133`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a39c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a46e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004af8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b035`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800493e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004942b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800493e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004942b`
- `ntdll!RtlSidDominates` at `0x180048293`
- `ntdll!RtlSidDominates` at `0x180048293`
- `ntdll!RtlFreeSid` at `0x1800482a9`
- `ntdll!RtlFreeSid` at `0x1800482a9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18004826b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18004826b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18004a55c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18004a55c`
- `ntdll!RtlNtStatusToDosError` at `0x1800482bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800482de`
- `ntdll!RtlNtStatusToDosError` at `0x180048eef`
- `ntdll!RtlNtStatusToDosError` at `0x1800490ad`
- `ntdll!RtlNtStatusToDosError` at `0x1800482bb`
- `ntdll!RtlNtStatusToDosError` at `0x1800482de`
- `ntdll!RtlNtStatusToDosError` at `0x180048eef`
- `ntdll!RtlNtStatusToDosError` at `0x1800490ad`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180048163`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004bae9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180048163`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004bae9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800486e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800487e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004886c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048888`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800489a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048f57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048f73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800491bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800494f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004950c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004955e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004957b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049c47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049c63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bcc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bce6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bd09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800486e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800487e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004886c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048888`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800489a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048f57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048f73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800491bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800494f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004950c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004955e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004957b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049c47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049c63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bcc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bce6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bd09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800481a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048da7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004b2c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800481a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048da7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004b2c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800481c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048dc9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b2e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800481c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048dc9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b2e8`
- `RPCRT4!RpcImpersonateClient` at `0x180048171`
- `RPCRT4!RpcImpersonateClient` at `0x180048737`
- `RPCRT4!RpcImpersonateClient` at `0x180048171`
- `RPCRT4!RpcImpersonateClient` at `0x180048737`
- `RPCRT4!RpcRevertToSelf` at `0x180048326`
- `RPCRT4!RpcRevertToSelf` at `0x1800487ab`
- `RPCRT4!RpcRevertToSelf` at `0x18004896c`
- `RPCRT4!RpcRevertToSelf` at `0x180048e35`
- `RPCRT4!RpcRevertToSelf` at `0x18004a45e`
- `RPCRT4!RpcRevertToSelf` at `0x18004a489`
- `RPCRT4!RpcRevertToSelf` at `0x18004ab54`
- `RPCRT4!RpcRevertToSelf` at `0x18004abb9`
- `RPCRT4!RpcRevertToSelf` at `0x18004ac92`
- `RPCRT4!RpcRevertToSelf` at `0x18004ae96`
- `RPCRT4!RpcRevertToSelf` at `0x18004af45`
- `RPCRT4!RpcRevertToSelf` at `0x18004b3e8`
- `RPCRT4!RpcRevertToSelf` at `0x18004b954`
- `RPCRT4!RpcRevertToSelf` at `0x180048326`
- `RPCRT4!RpcRevertToSelf` at `0x1800487ab`
- `RPCRT4!RpcRevertToSelf` at `0x18004896c`
- `RPCRT4!RpcRevertToSelf` at `0x180048e35`
- `RPCRT4!RpcRevertToSelf` at `0x18004a45e`
- `RPCRT4!RpcRevertToSelf` at `0x18004a489`
- `RPCRT4!RpcRevertToSelf` at `0x18004ab54`
- `RPCRT4!RpcRevertToSelf` at `0x18004abb9`
- `RPCRT4!RpcRevertToSelf` at `0x18004ac92`
- `RPCRT4!RpcRevertToSelf` at `0x18004ae96`
- `RPCRT4!RpcRevertToSelf` at `0x18004af45`
- `RPCRT4!RpcRevertToSelf` at `0x18004b3e8`
- `RPCRT4!RpcRevertToSelf` at `0x18004b954`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049ee5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049f2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049f4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a58f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a847`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a980`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a9a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049ee5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049f2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049f4b`

## string_xrefs

- `0x180049bb0`: `NT TASK`
- `0x180049bb7`: `NT TASK\`
- `0x18004a431`: `RpcServer::RegisterTask`
- `0x18004a9c0`: `RpcServer::RegisterTask`
- `0x18004ab81`: `RpcServer::RegisterTask`
- `0x18004adea`: `RpcServer::RegisterTask`
- `0x18004af05`: `RpcServer::RegisterTask`
- `0x18004b297`: `RpcServer::RegisterTask`
- `0x18004bd3f`: `RpcServer::RegisterTask`
- `0x18004bd79`: `RpcServer::RegisterTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=50 #try_helpers=1
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
  _BYTE *v13; // r14
  OLECHAR *v14; // r15
  _BYTE *v15; // rax
  RPC_STATUS v16; // eax
  EventManager *v17; // rcx
  unsigned int v18; // ebx
  HANDLE CurrentThread; // rax
  int v20; // eax
  NTSTATUS v21; // ebx
  ULONG LastError; // eax
  DWORD v23; // ebx
  int Sddl; // r12d
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // edx
  int v28; // eax
  unsigned __int16 *v29; // rax
  __int64 v30; // rax
  volatile signed __int32 *v31; // rbx
  struct _TASK_XML_ERROR_INFO *v32; // rax
  __int64 v33; // rsi
  unsigned __int16 *v34; // r14
  RPC_STATUS v35; // eax
  EventManager *v36; // rcx
  unsigned int v37; // ebx
  int v38; // eax
  tsched *v39; // rcx
  HANDLE v40; // r8
  __int64 DomainAccount; // rax
  BSTR *v42; // rbx
  BSTR v43; // r8
  const struct _TASK_USER_CRED *v44; // r13
  bool IsLocalSystem; // al
  int v46; // eax
  OLECHAR *v47; // rax
  __int64 v48; // rax
  volatile signed __int32 *v49; // rbx
  const unsigned __int16 *v50; // rax
  unsigned __int16 *v51; // r9
  _QWORD *v52; // rsi
  __int64 v53; // rax
  __int64 v54; // rdx
  int v55; // r8d
  int v56; // r9d
  char v57; // r13
  JobBucket *v58; // rsi
  JobBucket *v59; // rcx
  HANDLE v60; // rax
  int v61; // edx
  tsched *v62; // rcx
  int LastHrError; // eax
  JobBucket *v64; // rcx
  const struct _TASK_USER_CRED *v65; // r13
  __int64 v66; // rax
  WCHAR *v67; // rax
  int IsServiceAccount; // r8d
  bool v69; // si
  __int64 v70; // rcx
  signed int v71; // eax
  BSTR *v72; // rbx
  BSTR v73; // r8
  _QWORD *v74; // rcx
  int v75; // edx
  unsigned __int8 v76; // r12
  NTSTATUS v77; // eax
  signed int v78; // eax
  JobBucket *v79; // rbx
  User *LocalAdmin; // rax
  const unsigned __int16 *v81; // rdx
  tsched *v82; // rsi
  unsigned __int16 *v83; // rax
  const unsigned __int16 *v84; // rdx
  _QWORD *v85; // rcx
  __int64 v86; // rdx
  unsigned __int16 *v87; // r9
  JobStore *v88; // rbx
  const unsigned __int16 *Path; // rax
  JobBucket *v90; // rsi
  int v91; // eax
  JobBucket *v92; // rdx
  int v93; // eax
  bool v94; // zf
  int v95; // eax
  struct _RTL_CRITICAL_SECTION *v96; // rbx
  __int64 v97; // r12
  __int64 v98; // rax
  __int64 v99; // r12
  BSTR v100; // r13
  struct _RTL_CRITICAL_SECTION *v101; // rbx
  __int64 v102; // rsi
  __int64 v103; // rax
  __int64 v104; // rsi
  BSTR v105; // rcx
  int v106; // ebx
  void *v107; // r8
  void *v108; // r8
  signed int v109; // eax
  PSID v110; // r13
  int v111; // eax
  _QWORD *v112; // rcx
  int v113; // edx
  unsigned int v114; // ebx
  __int64 v115; // rax
  int v116; // eax
  unsigned int v117; // r9d
  int v118; // ebx
  int v119; // ecx
  const struct _TASK_USER_CRED *v120; // rsi
  __int64 v121; // rax
  __int64 v122; // rbx
  unsigned __int64 v123; // rbx
  void *v124; // rax
  unsigned int v125; // ebx
  struct _RTL_CRITICAL_SECTION *v126; // r13
  unsigned __int16 **v127; // rsi
  bool v128; // r9
  unsigned int v129; // r8d
  unsigned int v130; // edx
  const struct _TASK_USER_CRED *v131; // r9
  __int64 i; // rcx
  _BYTE *v133; // rax
  __int64 v134; // rcx
  unsigned int v135; // eax
  RTL_SRWLOCK *v136; // rsi
  unsigned __int16 *v137; // rbx
  int v138; // eax
  bool v139; // al
  const OLECHAR *v140; // rdx
  BSTR v141; // rbx
  void *v142; // r8
  _WORD *v143; // rax
  __int16 j; // cx
  const unsigned __int16 *v145; // rdx
  unsigned __int16 *v146; // rax
  int TreeInfo; // eax
  int v148; // edx
  HKEY *v149; // r12
  JobStore *v150; // rcx
  __int64 v151; // rcx
  int v152; // eax
  int v153; // ecx
  const unsigned __int16 *v154; // rax
  RpcServer *v155; // rcx
  const struct JobSecurity *v156; // r8
  __int64 v157; // rcx
  void *v158; // rbx
  unsigned int v159; // eax
  const unsigned __int16 *v160; // rax
  void *v161; // rbx
  const unsigned __int16 *v162; // rax
  unsigned int v163; // eax
  int v164; // edx
  const unsigned __int16 *v165; // rax
  JobMoniker *v166; // rax
  const unsigned __int16 *v167; // rax
  DWORD v168; // ebx
  CredStore *v169; // rbx
  __int64 Account; // rax
  const unsigned __int16 *v171; // rax
  __int64 v172; // rax
  char v173; // r14
  __int64 v174; // rbx
  unsigned int v175; // eax
  __int64 v176; // r9
  __int64 v177; // rax
  __int64 v178; // rcx
  __int64 v179; // rax
  __int64 v180; // rax
  tsched *v181; // rcx
  DWORD v182; // ebx
  char *v183; // rax
  const void *v184; // rdx
  char *v185; // rcx
  PSECURITY_DESCRIPTOR v186; // rbx
  HLOCAL v187; // r12
  HANDLE v188; // r12
  UINT v189; // eax
  OLECHAR *v190; // rax
  OLECHAR *v191; // rdi
  OLECHAR *v192; // rbx
  unsigned int v193; // eax
  void **v194; // rbx
  __int64 v195; // rcx
  CredStore *v196; // rbx
  __int64 v197; // rax
  const unsigned __int16 *v198; // rax
  void *v199; // r8
  unsigned __int8 v200; // bl
  JobStore *v201; // r14
  int updated; // eax
  unsigned int v203; // eax
  UINT v204; // eax
  OLECHAR *v205; // rax
  OLECHAR *v206; // rdi
  OLECHAR *v207; // rbx
  unsigned int v208; // eax
  unsigned int v209; // eax
  HKEY *v210; // rbx
  JobStore *v211; // rcx
  unsigned __int16 *v212; // r13
  JobBucket *v213; // rax
  void *v214; // rcx
  __int64 v215; // rcx
  CredStore *v216; // rbx
  __int64 v217; // rax
  const unsigned __int16 *v218; // rax
  __int64 v219; // rax
  char v220; // r14
  __int64 v221; // rbx
  unsigned int v222; // eax
  const struct User *v223; // r9
  unsigned int v224; // eax
  int v225; // eax
  const struct JobSecurity *v226; // r8
  unsigned int v227; // eax
  int v228; // edx
  unsigned int v229; // eax
  int v230; // edx
  unsigned int v231; // eax
  char v232; // bl
  _QWORD *v233; // rax
  _QWORD *k; // rbx
  __int64 v235; // rcx
  HANDLE v236; // rax
  signed int v237; // eax
  int v238; // eax
  EventManager *v239; // rcx
  unsigned int v240; // esi
  unsigned int v241; // eax
  const struct _EVENT_DESCRIPTOR *v242; // rax
  const struct _EVENT_DESCRIPTOR *v243; // rsi
  unsigned __int8 v244; // bl
  EventManager *v245; // rcx
  const unsigned __int16 *v246; // rax
  char v247; // bl
  unsigned int v248; // eax
  int v249; // edx
  const unsigned __int16 *v250; // rax
  unsigned __int16 *v251; // rax
  unsigned int v252; // eax
  _QWORD *v253; // rcx
  unsigned __int16 *v254; // rcx
  __int64 v255; // rax
  int v256; // eax
  __int64 v257; // rax
  int v258; // eax
  _BYTE *v259; // rcx
  __int64 v260; // rax
  __int64 m; // rax
  JobBucket *v262; // rcx
  unsigned __int16 *v263; // rcx
  __int64 n; // rax
  void *UserDataCount; // [rsp+20h] [rbp-848h]
  unsigned __int16 *UserDataCounta; // [rsp+20h] [rbp-848h]
  char UserDataCountb; // [rsp+20h] [rbp-848h]
  void *UserDataCountc; // [rsp+20h] [rbp-848h]
  const struct _GUID *UserData; // [rsp+28h] [rbp-840h]
  const struct _GUID *UserDataa; // [rsp+28h] [rbp-840h]
  const struct _GUID *UserDatab; // [rsp+28h] [rbp-840h]
  unsigned __int8 v273[8]; // [rsp+80h] [rbp-7E8h] BYREF
  unsigned __int16 *v274; // [rsp+88h] [rbp-7E0h]
  int v275; // [rsp+90h] [rbp-7D8h] BYREF
  unsigned __int16 *v276; // [rsp+98h] [rbp-7D0h] BYREF
  unsigned int v277; // [rsp+A0h] [rbp-7C8h]
  DWORD TokenInformationLength; // [rsp+A4h] [rbp-7C4h] BYREF
  HANDLE hObject; // [rsp+A8h] [rbp-7C0h] BYREF
  size_t Size; // [rsp+B0h] [rbp-7B8h] BYREF
  void *TokenHandle; // [rsp+B8h] [rbp-7B0h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp-7A8h] BYREF
  LPVOID lpMem; // [rsp+C8h] [rbp-7A0h] BYREF
  unsigned int v284; // [rsp+D0h] [rbp-798h]
  unsigned int v285; // [rsp+D4h] [rbp-794h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+E0h] [rbp-788h] BYREF
  DWORD ReturnLength[2]; // [rsp+F0h] [rbp-778h] BYREF
  unsigned int v288; // [rsp+F8h] [rbp-770h]
  const struct _TASK_USER_CRED *v289; // [rsp+100h] [rbp-768h]
  PSID Sid; // [rsp+108h] [rbp-760h] BYREF
  BSTR bstr; // [rsp+110h] [rbp-758h] BYREF
  HANDLE ClientToken; // [rsp+118h] [rbp-750h] BYREF
  unsigned __int16 *v293; // [rsp+120h] [rbp-748h] BYREF
  struct _TASK_XML_ERROR_INFO **v294; // [rsp+128h] [rbp-740h] BYREF
  BSTR v295; // [rsp+130h] [rbp-738h]
  unsigned int v296; // [rsp+138h] [rbp-730h]
  unsigned __int16 *v297; // [rsp+140h] [rbp-728h]
  _BYTE *v298; // [rsp+148h] [rbp-720h] BYREF
  unsigned __int16 *v299; // [rsp+150h] [rbp-718h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+158h] [rbp-710h] BYREF
  unsigned __int16 *v301; // [rsp+160h] [rbp-708h]
  unsigned __int16 *v302; // [rsp+168h] [rbp-700h] BYREF
  unsigned int v303; // [rsp+170h] [rbp-6F8h]
  unsigned __int16 **v304; // [rsp+178h] [rbp-6F0h]
  _BYTE *v305; // [rsp+180h] [rbp-6E8h]
  BSTR v306; // [rsp+188h] [rbp-6E0h] BYREF
  tsched **v307; // [rsp+190h] [rbp-6D8h] BYREF
  BYTE *lpData; // [rsp+198h] [rbp-6D0h]
  _QWORD v309[2]; // [rsp+1A0h] [rbp-6C8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+1B0h] [rbp-6B8h] BYREF
  int v311; // [rsp+1B8h] [rbp-6B0h]
  PSID v312; // [rsp+1C0h] [rbp-6A8h]
  unsigned __int16 *v313; // [rsp+1C8h] [rbp-6A0h]
  _BYTE v314[24]; // [rsp+1D0h] [rbp-698h] BYREF
  _BYTE *v315; // [rsp+1E8h] [rbp-680h]
  __int128 v316; // [rsp+1F0h] [rbp-678h] BYREF
  __int64 v317; // [rsp+200h] [rbp-668h]
  _BYTE v318[32]; // [rsp+208h] [rbp-660h] BYREF
  _QWORD *v319; // [rsp+228h] [rbp-640h]
  JobBucket *v320; // [rsp+238h] [rbp-630h]
  _BYTE v321[24]; // [rsp+240h] [rbp-628h] BYREF
  _BYTE v322[56]; // [rsp+258h] [rbp-610h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+290h] [rbp-5D8h] BYREF
  _BYTE v324[56]; // [rsp+2C8h] [rbp-5A0h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+300h] [rbp-568h] BYREF
  GUID v326; // [rsp+308h] [rbp-560h] BYREF
  _WORD **v327; // [rsp+318h] [rbp-550h] BYREF
  _WORD *v328; // [rsp+320h] [rbp-548h]
  JobBucket *v329; // [rsp+328h] [rbp-540h]
  GUID iid; // [rsp+330h] [rbp-538h] BYREF
  char v331[16]; // [rsp+340h] [rbp-528h] BYREF
  __int64 v332; // [rsp+350h] [rbp-518h] BYREF
  unsigned __int16 v333[256]; // [rsp+360h] [rbp-508h] BYREF
  char v334; // [rsp+560h] [rbp-308h]
  CBstrWriter *v335; // [rsp+780h] [rbp-E8h]
  struct _EVENT_DATA_DESCRIPTOR v336; // [rsp+7A0h] [rbp-C8h] BYREF
  char *v337; // [rsp+7B0h] [rbp-B8h]
  int v338; // [rsp+7B8h] [rbp-B0h]
  int v339; // [rsp+7BCh] [rbp-ACh]
  struct _EVENT_DATA_DESCRIPTOR TokenInformation; // [rsp+7C0h] [rbp-A8h] BYREF
  char *v341; // [rsp+7D0h] [rbp-98h]
  int v342; // [rsp+7D8h] [rbp-90h]
  int v343; // [rsp+7DCh] [rbp-8Ch]
  unsigned __int16 *v344; // [rsp+7E0h] [rbp-88h]
  int v345; // [rsp+7E8h] [rbp-80h]
  int v346; // [rsp+7ECh] [rbp-7Ch]
  _SID_IDENTIFIER_AUTHORITY *p_IdentifierAuthority; // [rsp+7F0h] [rbp-78h]
  __int64 v348; // [rsp+7F8h] [rbp-70h]
  unsigned __int16 *v349; // [rsp+800h] [rbp-68h]
  int v350; // [rsp+808h] [rbp-60h]
  int v351; // [rsp+80Ch] [rbp-5Ch]

  v297 = a3;
  v274 = a2;
  bstrString = this;
  v313 = a3;
  lpMem = a5;
  v289 = a8;
  lpData = a9;
  v304 = a10;
  v294 = a11;
  v277 = 0;
  v288 = 0;
  v275 = 0;
  v293 = 0;
  v276 = 0;
  StringSecurityDescriptor = 0;
  v13 = 0;
  v298 = 0;
  JobMoniker::JobMoniker(&iid, 0, 0);
  SecurityDescriptor = 0;
  v311 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v322);
  Actions::ActionCollection::ActionCollection((Actions::ActionCollection *)v321);
  v299 = 0;
  v301 = 0;
  v302 = 0;
  ClientToken = 0;
  v307 = 0;
  v316 = 0;
  v317 = 0;
  Triggers::Trigulator::Trigulator((Triggers::Trigulator *)v318);
  Actions::ActionCollection::ActionCollection((Actions::ActionCollection *)v314);
  v306 = 0;
  bstr = 0;
  v14 = 0;
  v312 = 0;
  JobMoniker::JobMoniker(&v326, a2, 0);
  if ( a7 )
    v15 = (_BYTE *)*((_QWORD *)a8 + 1);
  else
    v15 = 0;
  v305 = v15;
  v315 = v15;
  if ( (unsigned int)dword_1800C0358 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 261;
    EventDescriptor.Keyword = 0;
    v336.Ptr = (ULONGLONG)off_1800C0360;
    v336.Size = *(unsigned __int16 *)off_1800C0360;
    v336.Reserved = 2;
    v337 = byte_1800B1B13;
    v338 = 20;
    v339 = 1;
    v285 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &v336);
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
  v273[0] = 0;
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
      }
      else
      {
        v21 = RtlSidDominates(TokenInformation.Ptr, Sid, v273);
        RtlFreeSid(Sid);
        if ( v21 >= 0 )
        {
          v23 = 0;
          if ( !v273[0] )
            v23 = 5;
          goto LABEL_17;
        }
        LastError = RtlNtStatusToDosError(v21);
      }
    }
    else
    {
      LastError = GetLastError();
    }
    v23 = LastError;
LABEL_17:
    CloseHandle(TokenHandle);
    goto LABEL_19;
  }
  v23 = GetLastError();
LABEL_19:
  if ( v23 )
  {
    v253 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v23);
        v253 = WPP_GLOBAL_Control;
      }
      if ( v253 != &WPP_GLOBAL_Control && (*((_DWORD *)v253 + 7) & 0x10000) != 0 && *((_BYTE *)v253 + 25) >= 2u )
        WPP_SF_S(v253[2], 28, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, a2);
    }
    Sddl = -2147024891;
    RpcRevertToSelf();
    goto LABEL_704;
  }
  RpcRevertToSelf();
  if ( v304 )
    *v304 = 0;
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
    goto LABEL_29;
  }
  if ( !v297 )
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
      goto LABEL_704;
    }
    goto LABEL_29;
  }
  v27 = 2;
  if ( a4 )
    v27 = a4;
  v284 = v27;
  v296 = v27;
  if ( (v27 & 0xFFFFFFC0) != 0 || (v27 & 7) == 0 || (v27 & 0xFFFFFFFE) != 0 && (v27 & 1) != 0 )
  {
    v85 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v86 = 31;
    v87 = a2;
    goto LABEL_238;
  }
  if ( a7 )
  {
    if ( (*((_DWORD *)v289 + 4) & 0xFFFFFFFE) != 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 33;
        goto LABEL_35;
      }
      goto LABEL_29;
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
      goto LABEL_29;
    }
  }
  else if ( v289 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = 32;
      goto LABEL_35;
    }
LABEL_29:
    Sddl = -2147024809;
LABEL_704:
    v34 = v274;
    goto LABEL_705;
  }
  if ( (v27 & 1) != 0 )
  {
    TokenHandle = 0;
    v28 = StringReader::CreateStream(v297, &TokenHandle);
    Sddl = v28;
    if ( v28 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          (_DWORD)v274,
          v28);
      }
      if ( TokenHandle )
        (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
      goto LABEL_704;
    }
    lpMem = 0;
    v295 = 0;
    v29 = (unsigned __int16 *)operator new(0x460u);
    v313 = v29;
    if ( v29 )
    {
      v30 = TaskXmlReader::TaskXmlReader(v29, &TokenHandle, &lpMem, 0);
      v31 = (volatile signed __int32 *)v30;
      if ( v30 )
        _InterlockedIncrement((volatile signed __int32 *)(v30 + 8));
    }
    else
    {
      v31 = 0;
    }
    v295 = (BSTR)v31;
    ValidationXmlHandler::ValidationXmlHandler((ValidationXmlHandler *)v333, (const struct JobMoniker *)&v326, 2u, 0, 0);
    Sddl = TaskXmlReader::ProcessXml((TaskXmlReader *)v31, (struct ITaskXmlHandler *)v333);
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
        (_DWORD)v274,
        Sddl);
    }
    ValidationXmlHandler::~ValidationXmlHandler((ValidationXmlHandler *)v333);
    v33 = -1;
    if ( v31 && _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v31)(v31, 1);
    if ( lpMem )
      HeapFree(g_PrivateHeap, 0, lpMem);
    if ( TokenHandle )
      (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
    goto LABEL_83;
  }
  hObject = 0;
  Size = 0;
  ReturnLength[0] = 1;
  v35 = RpcImpersonateClient(0);
  v37 = v35;
  if ( v35 )
  {
    EventManager::EvtReport(v36, &IMPERSONATION_FAILURE, L"RpcServer::RegisterTask", v35, UserDataCount, UserData);
    wmi::GenericException::GenericException((wmi::GenericException *)v324, v37);
    throw (wmi::GenericException *)v324;
  }
  v38 = User::FromImpersonationToken((struct User *)&Size, 0);
  Sddl = v38;
  if ( v38 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v274,
        v38);
    }
    RpcRevertToSelf();
    goto LABEL_91;
  }
  if ( a7 )
  {
    v33 = -1;
    v44 = v289;
  }
  else
  {
    DomainAccount = User::GetDomainAccount(&Size, &Sid);
    _bstr_t::operator=(&v307, DomainAccount);
    v42 = (BSTR *)Sid;
    v33 = -1;
    if ( Sid )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Sid + 4, 0xFFFFFFFF) == 1 && v42 )
      {
        if ( *v42 )
        {
          SysFreeString(*v42);
          *v42 = 0;
        }
        v43 = v42[1];
        if ( v43 )
        {
          HeapFree(g_PrivateHeap, 0, v43);
          v42[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v42);
      }
      Sid = 0;
    }
    *((_QWORD *)&v316 + 1) = 0;
    if ( v307 )
      v39 = *v307;
    else
      v39 = 0;
    *(_QWORD *)&v316 = v39;
    LODWORD(v317) = 1;
    v44 = (const struct _TASK_USER_CRED *)&v316;
    v289 = (const struct _TASK_USER_CRED *)&v316;
  }
  if ( (unsigned int)tsched::IsUserAdmin(v39) || (IsLocalSystem = User::IsLocalSystem((User *)&Size)) )
    IsLocalSystem = 1;
  v273[0] = IsLocalSystem;
  if ( *((_DWORD *)bstrString + 7) && !IsLocalSystem )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v274);
    }
LABEL_117:
    Sddl = -2147024891;
    goto LABEL_118;
  }
  TokenHandle = 0;
  v46 = StringReader::CreateStream(v297, &TokenHandle);
  Sddl = v46;
  if ( v46 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v274,
        v46);
    }
    if ( TokenHandle )
LABEL_690:
      (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
LABEL_118:
    RpcRevertToSelf();
    wmi::AutoRef<User::UserEntry>::Release(&Size);
    if ( hObject )
    {
      HeapFree(g_PrivateHeap, 0, hObject);
      v34 = v274;
      goto LABEL_706;
    }
LABEL_83:
    v34 = v274;
LABEL_706:
    v212 = v276;
    goto LABEL_707;
  }
  v295 = 0;
  v47 = (OLECHAR *)operator new(0x460u);
  v295 = v47;
  if ( v47 )
  {
    v48 = TaskXmlReader::TaskXmlReader(v47, &TokenHandle, &hObject, 0);
    v49 = (volatile signed __int32 *)v48;
    if ( v48 )
      _InterlockedIncrement((volatile signed __int32 *)(v48 + 8));
  }
  else
  {
    v49 = 0;
  }
  v295 = (BSTR)v49;
  v50 = (const unsigned __int16 *)lpMem;
  if ( lpMem && !*(_WORD *)lpMem )
    v50 = 0;
  if ( !v274 || (v51 = 0, *v274) )
    v51 = v274;
  v303 = v284 & 8;
  *(_DWORD *)IdentifierAuthority.Value = v303;
  ServerXMLUpdateHandler::ServerXMLUpdateHandler(
    (ServerXMLUpdateHandler *)v333,
    v303 != 0,
    v303 == 0,
    v51,
    v50,
    v44,
    a6,
    (const struct JobMoniker *)&v326,
    (const struct User *)&Size,
    (struct Triggers::Trigulator *)v318,
    (struct Actions::ActionCollection *)v314,
    1,
    (struct ATL::CComBSTR *)&v306,
    (struct ATL::CComBSTR *)&bstr,
    0);
  Sddl = TaskXmlReader::ProcessXml((TaskXmlReader *)v49, (struct ITaskXmlHandler *)v333);
  if ( Sddl < 0 )
  {
    v52 = hObject;
    hObject = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v52 )
      {
        v53 = v52[2];
        v54 = v52[1];
        v55 = *((_DWORD *)v52 + 1);
        v56 = *(_DWORD *)v52;
      }
      else
      {
        v53 = 0;
        v54 = 0;
        v55 = 0;
        LOBYTE(v56) = 0;
      }
      WPP_SF_SDddSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v54, v55, (_DWORD)v274, Sddl, v56, v55, v54, v53);
    }
    if ( v294 && v52 )
      *v294 = (struct _TASK_XML_ERROR_INFO *)v52;
    ServerXMLUpdateHandler::~ServerXMLUpdateHandler((ServerXMLUpdateHandler *)v333);
    v33 = -1;
    if ( v49 && _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v49)(v49, 1);
    if ( TokenHandle )
      goto LABEL_690;
    goto LABEL_118;
  }
  v57 = v334;
  Sid = CBstrWriter::GetCopy(v335);
  if ( !Sid )
  {
    Sddl = -2147024882;
    ServerXMLUpdateHandler::~ServerXMLUpdateHandler((ServerXMLUpdateHandler *)v333);
    if ( v49 && _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v49)(v49, 1);
    if ( TokenHandle )
      goto LABEL_690;
    goto LABEL_118;
  }
  SysFreeString(0);
  v14 = (OLECHAR *)Sid;
  v312 = Sid;
  v58 = v329;
  if ( v329 )
    _InterlockedIncrement((volatile signed __int32 *)v329 + 2);
  v59 = v320;
  if ( v320 && _InterlockedExchangeAdd((volatile signed __int32 *)v320 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v59)(v59, 1);
  v320 = v58;
  ServerXMLUpdateHandler::~ServerXMLUpdateHandler((ServerXMLUpdateHandler *)v333);
  v33 = -1;
  if ( v49 && _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v49)(v49, 1);
  if ( TokenHandle )
    (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
  if ( !v273[0] && v57 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v274,
        Sddl);
    }
    goto LABEL_117;
  }
  v60 = GetCurrentThread();
  if ( !OpenThreadToken(v60, 0x2000Eu, 1, &ClientToken) )
  {
    LastHrError = tsched::GetLastHrError(v62, v61);
    Sddl = LastHrError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v274,
        LastHrError);
    }
    goto LABEL_118;
  }
  RpcRevertToSelf();
  v64 = v329;
  v65 = v289;
  if ( (*((_DWORD *)v329 + 4) & 0x40000) != 0 && (!v289 || !*((_QWORD *)v289 + 1)) )
  {
    v66 = User::GetDomainAccount((char *)v329 + 64, &TokenHandle);
    v67 = (WCHAR *)_bstr_t::operator unsigned short const *(v66);
    TokenInformationLength = 0;
    IsServiceAccount = 0;
    v69 = 0;
    if ( v67 )
    {
      if ( *v67 )
      {
        v70 = -1;
        do
          ++v70;
        while ( v67[v70] );
        if ( v67[(unsigned int)v70 - 1] == 36 )
        {
          IsServiceAccount = NetIsServiceAccount(0, v67, (BOOL *)&TokenInformationLength);
          if ( IsServiceAccount >= 0 )
            v69 = TokenInformationLength != 0;
        }
      }
    }
    v71 = RtlNtStatusToDosError(IsServiceAccount);
    Sddl = v71;
    if ( v71 > 0 )
      Sddl = (unsigned __int16)v71 | 0x80070000;
    v72 = (BSTR *)TokenHandle;
    if ( TokenHandle )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)TokenHandle + 4, 0xFFFFFFFF) == 1 && v72 )
      {
        if ( *v72 )
        {
          SysFreeString(*v72);
          *v72 = 0;
        }
        v73 = v72[1];
        if ( v73 )
        {
          HeapFree(g_PrivateHeap, 0, v73);
          v72[1] = 0;
        }
        HeapFree(g_PrivateHeap, 0, v72);
      }
      TokenHandle = 0;
    }
    if ( Sddl < 0 )
    {
      v74 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v75 = 43;
LABEL_201:
        WPP_SF_Sd(v74[2], v75, (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, (_DWORD)v274, Sddl);
        goto LABEL_202;
      }
      goto LABEL_202;
    }
    if ( v69 )
      *((_DWORD *)v329 + 4) |= 0x80000000;
    v64 = v329;
  }
  v76 = v273[0];
  if ( !v273[0] && JobBucket::GetPriority(v64) <= 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v274);
    }
    Sddl = -2147024891;
    goto LABEL_202;
  }
  TokenInformationLength = 0;
  v77 = LUAIsElevatedToken(ClientToken);
  if ( v77 < 0 )
  {
    v78 = RtlNtStatusToDosError(v77);
    Sddl = v78;
    if ( v78 > 0 )
      Sddl = (unsigned __int16)v78 | 0x80070000;
    v74 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v75 = 45;
      goto LABEL_201;
    }
LABEL_202:
    wmi::AutoRef<User::UserEntry>::Release(&Size);
    v40 = hObject;
    if ( !hObject )
    {
      v33 = -1;
      v34 = v274;
      goto LABEL_706;
    }
LABEL_92:
    HeapFree(g_PrivateHeap, 0, v40);
    goto LABEL_704;
  }
  v79 = v329;
  if ( (*((_DWORD *)v329 + 4) & 0x1000000) != 0
    || (LocalAdmin = User::GetLocalAdmin(),
        (unsigned __int8)User::operator==((JobBucket *)((char *)v79 + 64), LocalAdmin))
    || (*((_DWORD *)v329 + 4) & 0xFC000) == 0x4000 )
  {
    if ( !TokenInformationLength && !v76 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v274);
      }
      Sddl = -2147024891;
LABEL_91:
      wmi::AutoRef<User::UserEntry>::Release(&Size);
      v40 = hObject;
      if ( !hObject )
        goto LABEL_704;
      goto LABEL_92;
    }
  }
  wmi::AutoRef<User::UserEntry>::Release(&Size);
  if ( hObject )
    HeapFree(g_PrivateHeap, 0, hObject);
  v82 = (tsched *)v306;
  v274 = v306;
  v295 = v306;
  v83 = tsched::PathCopy((tsched *)v306, v81);
  wmi::AutoVectorPtr<unsigned short>::operator=(&v293, v83);
  if ( tsched::IsRoot(v82, v84) )
  {
    v85 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v86 = 47;
    v87 = (unsigned __int16 *)v82;
LABEL_238:
    WPP_SF_S(v85[2], v86, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v87);
    Sddl = -2147024809;
    goto LABEL_704;
  }
  JobMoniker::_SetPath((JobMoniker *)&v326, (const unsigned __int16 *)v82);
  v88 = JobStore::m_pCommonStore;
  TokenHandle = JobStore::m_pCommonStore;
  Path = JobMoniker::GetPath((JobMoniker *)&v326);
  JobStore::RegGetOverrideInfo(v88, Path, (enum JobFlags::StatePersistanceFlags *)&v275);
  *((_DWORD *)v329 + 5) = v275;
  if ( v65 && *((_QWORD *)v65 + 1) )
  {
    v90 = v329;
    v91 = *((_DWORD *)v329 + 4);
    if ( (v91 & 0x20000) != 0 || v91 < 0 )
    {
      Sddl = -2147023570;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_704;
      }
      v34 = v274;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v274,
        46);
LABEL_705:
      v33 = -1;
      goto LABEL_706;
    }
    goto LABEL_254;
  }
  v92 = v329;
  v93 = *((_DWORD *)v329 + 4);
  if ( (v93 & 0x100000) != 0 || (v93 & 0x20000) != 0 || (v93 & 0x40000) == 0 && (v93 & 0x80000) == 0 || v93 < 0 )
  {
LABEL_308:
    v114 = *((_DWORD *)v92 + 4);
    v115 = User::User(&v294, (char *)v92 + 64);
    v116 = IsPrincipalAllowed(v115, v114);
    Sddl = v116;
    if ( v116 < 0 )
    {
      v112 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_704;
      }
      v113 = 50;
      UserDataCountb = v116;
LABEL_313:
      v117 = (unsigned int)v82;
LABEL_314:
      WPP_SF_Sd(v112[2], v113, (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v117, UserDataCountb);
      goto LABEL_704;
    }
    goto LABEL_302;
  }
  if ( PlugIn::IsRegistering((PlugIn *)&PlugIn::s_singleton, (const unsigned __int16 *)v82, v297) )
  {
    v92 = v329;
    goto LABEL_308;
  }
  v90 = v329;
  if ( v65 )
  {
LABEL_254:
    *(_QWORD *)ReturnLength = *((_QWORD *)v65 + 1);
    goto LABEL_256;
  }
  *(_QWORD *)ReturnLength = 0;
LABEL_256:
  v94 = (*((_DWORD *)v90 + 4) & 0x10000) == 0;
  LODWORD(Size) = *((_DWORD *)v90 + 4) & 0x10000;
  v95 = 2;
  if ( v94 )
    v95 = 4;
  v285 = v95;
  hObject = 0;
  v96 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v97 = *((_QWORD *)v90 + 8);
  v98 = *(_QWORD *)(v97 + 24);
  if ( v98 )
    _InterlockedIncrement((volatile signed __int32 *)(v98 + 16));
  v99 = *(_QWORD *)(v97 + 24);
  LeaveCriticalSection(v96);
  if ( v99 )
    v100 = *(BSTR *)v99;
  else
    v100 = 0;
  v101 = User::s_cs;
  EnterCriticalSection(User::s_cs);
  v102 = *((_QWORD *)v90 + 8);
  v103 = *(_QWORD *)(v102 + 16);
  if ( v103 )
    _InterlockedIncrement((volatile signed __int32 *)(v103 + 16));
  v104 = *(_QWORD *)(v102 + 16);
  LeaveCriticalSection(v101);
  if ( v104 )
    v105 = *(BSTR *)v104;
  else
    v105 = 0;
  UserDataa = 0;
  LODWORD(UserDataCounta) = 0;
  v106 = LogonUserExExW(v105, v100, *(_QWORD *)ReturnLength, v285);
  if ( v104 && _InterlockedExchangeAdd((volatile signed __int32 *)(v104 + 16), 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v104 )
    {
      SysFreeString(*(BSTR *)v104);
      *(_QWORD *)v104 = 0;
    }
    v107 = *(void **)(v104 + 8);
    if ( v107 )
    {
      HeapFree(g_PrivateHeap, 0, v107);
      *(_QWORD *)(v104 + 8) = 0;
    }
    HeapFree(g_PrivateHeap, 0, (LPVOID)v104);
  }
  v33 = -1;
  if ( v99 && _InterlockedExchangeAdd((volatile signed __int32 *)(v99 + 16), 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v99 )
    {
      SysFreeString(*(BSTR *)v99);
      *(_QWORD *)v99 = 0;
    }
    v108 = *(void **)(v99 + 8);
    if ( v108 )
    {
      HeapFree(g_PrivateHeap, 0, v108);
      *(_QWORD *)(v99 + 8) = 0;
    }
    HeapFree(g_PrivateHeap, 0, (LPVOID)v99);
  }
  if ( v106 )
  {
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    Sddl = 0;
    goto LABEL_301;
  }
  v109 = GetLastError();
  if ( (_DWORD)Size )
  {
LABEL_289:
    Sddl = v109;
    if ( v109 > 0 )
      Sddl = (unsigned __int16)v109 | 0x80070000;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( Sddl < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v34 = v274;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          (_DWORD)v274,
          Sddl);
        goto LABEL_706;
      }
      goto LABEL_83;
    }
    goto LABEL_301;
  }
  if ( v109 != 1385 )
  {
    v109 = GetLastError();
    goto LABEL_289;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  Sddl = 267036;
LABEL_301:
  LODWORD(v82) = (_DWORD)v274;
LABEL_302:
  v285 = Sddl;
  v110 = Sid;
  v111 = JobStore::ComputeHash((struct JobMoniker *)&v326, (const unsigned __int16 *)Sid);
  Sddl = v111;
  if ( v111 < 0 )
  {
    v112 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_704;
    }
    v113 = 51;
    UserDataCountb = v111;
    goto LABEL_313;
  }
  v275 = 0;
  v118 = (*((__int64 (__fastcall **)(void ***, GUID *, _BYTE *, int *))UbpmProxySingleton::s_singleton[0] + 15))(
           UbpmProxySingleton::s_singleton,
           &v326,
           v314,
           &v275);
  if ( v118 < 0 )
    goto LABEL_681;
  if ( v275 )
  {
    *((_DWORD *)v329 + 4) |= 0x2000000u;
    goto LABEL_322;
  }
  UserDataCounta = (unsigned __int16 *)&v275;
  v118 = (*((__int64 (__fastcall **)(void ***, GUID *, _BYTE *, _BYTE *))UbpmProxySingleton::s_singleton[0] + 16))(
           UbpmProxySingleton::s_singleton,
           &v326,
           v318,
           v314);
  if ( v118 < 0 )
  {
LABEL_681:
    Sddl = v118;
LABEL_682:
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_704;
    }
    v252 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
    v113 = 52;
    UserDataCountb = v118;
    v117 = v252;
    v112 = WPP_GLOBAL_Control;
    goto LABEL_314;
  }
  if ( !v275 )
  {
    Sddl = -2147216599;
    LOBYTE(v118) = 41;
    goto LABEL_682;
  }
  *((_DWORD *)v329 + 4) &= ~0x2000000u;
LABEL_322:
  Sddl = v118;
  v119 = *((_DWORD *)v329 + 4);
  if ( (v119 & 0x40000) != 0 || (v119 & 0x80000) != 0 )
  {
    if ( a7 )
    {
      v120 = v289;
      if ( v289 )
      {
        v121 = *((_QWORD *)v289 + 1);
        if ( v121 )
        {
          if ( (v119 & 0x2000000) != 0 )
          {
            v122 = -1;
            do
              ++v122;
            while ( *(_WORD *)(v121 + 2 * v122) );
            v123 = v122 + 1;
            v124 = operator new(saturated_mul(v123, 2u));
            wmi::AutoVectorPtr<unsigned short>::operator=(&v299, v124);
            v301 = v299;
            v302 = v299;
            SafeStrCopy(v299, v123, *((const unsigned __int16 **)v120 + 1));
          }
          v125 = 0;
          v126 = CredStore::g_pCommonStore;
          while ( 1 )
          {
            hObject = 0;
            v127 = (unsigned __int16 **)((char *)v120 + 24 * v125);
            Sddl = User::FromUsername((struct User *)&hObject, *v127);
            if ( Sddl < 0 )
              break;
            Sddl = CredStore::StoreNtCredential(v126, (const struct User *)&hObject, v127[1], v128);
            if ( Sddl < 0 )
              break;
            wmi::AutoRef<User::UserEntry>::Release(&hObject);
            ++v125;
            v129 = a7;
            v120 = v289;
            if ( v125 >= a7 )
              goto LABEL_337;
          }
          wmi::AutoRef<User::UserEntry>::Release(&hObject);
          v129 = a7;
LABEL_337:
          v130 = 0;
          v131 = v289;
          do
          {
            i = 3LL * v130;
            v133 = (_BYTE *)*((_QWORD *)v131 + 3 * v130 + 1);
            if ( v133 )
            {
              v134 = -1;
              do
                ++v134;
              while ( *(_WORD *)&v133[2 * v134] );
              for ( i = 2 * v134; i; --i )
                *v133++ = 0;
            }
            ++v130;
          }
          while ( v130 < v129 );
          if ( Sddl < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v135 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                53,
                (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                v135,
                Sddl);
            }
            EventManager::EvtReport(
              (EventManager *)i,
              &TASK_REGISTERED_WITHOUT_CREDENTIALS,
              v293,
              Sddl,
              UserDataCounta,
              UserDataa);
            goto LABEL_704;
          }
          v110 = Sid;
        }
      }
    }
  }
  v136 = (RTL_SRWLOCK *)(bstrString + 8);
  v309[0] = bstrString + 8;
  AcquireSRWLockExclusive((PSRWLOCK)bstrString + 2);
  memset_0(v333, 0, 0x20Au);
  v137 = v274;
  if ( (*((_DWORD *)v329 + 4) & 0x200000) != 0 )
  {
    if ( !PlugIn::IsRegistering((PlugIn *)&PlugIn::s_singleton, v274, v297) )
    {
      if ( qword_1800C1718 )
      {
        UserDataCounta = v333;
        v138 = qword_1800C1718(v137, v110, lpMem, v284);
        Sddl = v138;
        if ( v138 < 0 )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0 )
          {
            v34 = v137;
          }
          else
          {
            v34 = v137;
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                54,
                (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                (_DWORD)v137,
                v138);
          }
          goto LABEL_360;
        }
      }
      else
      {
        Sddl = 1;
      }
    }
    if ( !Sddl && v333[0] )
    {
      v139 = 0;
      if ( v333[0] != 92 )
        v139 = v333[0] != 47;
      v140 = L"NT TASK\\";
      if ( !v139 )
        v140 = L"NT TASK";
      _bstr_t::operator=(&v327, v140);
      _bstr_t::_bstr_t((_bstr_t *)&bstrString, v333);
      _bstr_t::operator+=(&v327, &bstrString);
      v141 = bstrString;
      if ( bstrString && _InterlockedExchangeAdd((volatile signed __int32 *)bstrString + 4, 0xFFFFFFFF) == 1 && v141 )
      {
        if ( *(_QWORD *)v141 )
        {
          SysFreeString(*(BSTR *)v141);
          *(_QWORD *)v141 = 0;
        }
        v142 = (void *)*((_QWORD *)v141 + 1);
        if ( v142 )
        {
          HeapFree(g_PrivateHeap, 0, v142);
          *((_QWORD *)v141 + 1) = 0;
        }
        HeapFree(g_PrivateHeap, 0, v141);
      }
      if ( v327 )
        v143 = *v327;
      else
        v143 = 0;
      for ( j = *v143; *v143; j = *v143 )
      {
        if ( j == 47 )
        {
          *v143++ = 92;
          v328 = v143;
        }
        else
        {
          ++v143;
          if ( j == 92 )
            v328 = v143;
        }
      }
      v137 = (unsigned __int16 *)JobMoniker::GetPath((JobMoniker *)&v326);
      v274 = v137;
      v295 = v137;
      v146 = tsched::PathCopy((tsched *)v137, v145);
      wmi::AutoVectorPtr<unsigned short>::operator=(&v293, v146);
    }
  }
  else
  {
    v152 = PlugIn::DeleteTask((PlugIn *)&PlugIn::s_singleton, v274);
    if ( v152 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        (_DWORD)v137,
        v152);
    }
  }
  v336 = 0;
  TokenInformationLength = 0;
  TreeInfo = JobStore::RegGetTreeInfo(
               (JobStore *)TokenHandle,
               v137,
               (struct _GUID *)&v336,
               (enum JobStore::TaskIndex *)&TokenInformationLength);
  Sddl = TreeInfo;
  if ( TreeInfo < 0 || TokenInformationLength )
  {
    v151 = (unsigned int)TreeInfo;
  }
  else
  {
    JobMoniker::JobMoniker((JobMoniker *)&TokenInformation, v137, (const struct _GUID *)&v336);
    v149 = (HKEY *)TokenHandle;
    if ( (int)JobStore::RemoveTaskEntryP(TokenHandle, &TokenInformation, 0) >= 0 )
      JobStore::FlushTaskEntryP(v150, v149[2]);
    Sddl = -2147024894;
    JobMoniker::~JobMoniker((JobMoniker *)&TokenInformation);
    v151 = 2147942402LL;
  }
  if ( !tsched::IsErrorNotFound((tsched *)v151, v148) )
  {
    if ( v153 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v159 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          v159,
          Sddl);
      }
LABEL_467:
      ReleaseSRWLockExclusive(v136);
      goto LABEL_704;
    }
    if ( (v284 & 4) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v160 = JobMoniker::GetPath((JobMoniker *)&v326);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v160);
      }
      Sddl = -2147024713;
      ReleaseSRWLockExclusive(v136);
      goto LABEL_704;
    }
    v326 = (GUID)v336;
    v34 = v274;
    v161 = TokenHandle;
    Sddl = JobStore::RegJobSecurityQuery((JobStore *)TokenHandle, v274, (struct JobSecurity *)&SecurityDescriptor);
    if ( Sddl < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v162 = JobMoniker::GetPath((JobMoniker *)&v326);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v162);
      }
      goto LABEL_360;
    }
    Sddl = JobSecurity::GetSddl((JobSecurity *)&SecurityDescriptor, 7u, (unsigned __int16 **)&StringSecurityDescriptor);
    if ( Sddl >= 0 )
    {
      Sddl = JobAccessCheck(ClientToken, SecurityDescriptor, 2u);
      if ( Sddl >= 0 )
      {
        v165 = JobMoniker::GetPath((JobMoniker *)&v326);
        v166 = JobMoniker::JobMoniker((JobMoniker *)&TokenInformation, v165, &v326);
        JobMoniker::operator=(&iid, v166);
        JobMoniker::~JobMoniker((JobMoniker *)&TokenInformation);
        v167 = JobMoniker::GetPath((JobMoniker *)&v326);
        UserDataa = (const struct _GUID *)v321;
        UserDataCounta = (unsigned __int16 *)v322;
        Sddl = JobStore::LoadBucketFromRegistry(v161, v167, 15, &iid);
        v275 = Sddl;
        if ( Sddl >= 0 )
        {
          v168 = *(_DWORD *)(v332 + 16);
          TokenInformationLength = v168;
          wmi::AutoRef<User::UserEntry>::operator=(&v298, *(_QWORD *)(v332 + 64));
          v13 = v298;
          if ( v298 && *v298 )
          {
            v169 = (CredStore *)CredStore::g_pCommonStore;
            Account = User::GetAccount(v332 + 64, &v294);
            v171 = (const unsigned __int16 *)_bstr_t::operator unsigned short const *(Account);
            Sddl = CredStore::ResolveAlias(v169, v171, (struct User *)&v298);
            v275 = Sddl;
            _bstr_t::~_bstr_t((_bstr_t *)&v294);
            if ( Sddl < 0 )
            {
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                v173 = v277;
              }
              else
              {
                v172 = User::GetAccount(v332 + 64, &v294);
                v173 = 1;
                v174 = _bstr_t::operator unsigned short const *(v172);
                v175 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&iid);
                WPP_SF_SSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  63,
                  (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                  v175,
                  v174,
                  Sddl);
              }
              if ( (v173 & 1) != 0 )
                _bstr_t::~_bstr_t((_bstr_t *)&v294);
              goto LABEL_467;
            }
            v13 = v298;
            v168 = TokenInformationLength;
          }
          v176 = v332;
          v177 = *(_QWORD *)(v332 + 208);
          if ( v177 )
            v178 = *(_QWORD *)(v177 + 48);
          else
            v178 = 0;
          v179 = *((_QWORD *)v329 + 26);
          if ( v179 )
            v180 = *(_QWORD *)(v179 + 48);
          else
            v180 = 0;
          if ( v178 != v180
            || (((*(_DWORD *)(v332 + 16) >> 27) ^ (*((_DWORD *)v329 + 4) >> 27)) & 1) != 0
            || (((*(_DWORD *)(v332 + 16) >> 28) ^ (*((_DWORD *)v329 + 4) >> 28)) & 1) != 0 )
          {
            RpcAutoImpersonate::RpcAutoImpersonate(
              (RpcAutoImpersonate *)&TokenInformationLength,
              L"RpcServer::RegisterTask",
              1);
            if ( !(unsigned int)tsched::IsUserAdmin(v181) )
            {
              Sddl = -2147024891;
              if ( TokenInformationLength )
                RpcRevertToSelf();
              goto LABEL_467;
            }
            if ( TokenInformationLength )
              RpcRevertToSelf();
            v176 = v332;
          }
          v273[0] = 0;
          v182 = v168 & 0xFC000;
          TokenInformationLength = v182;
          v156 = (const struct JobSecurity *)*((unsigned int *)v329 + 15);
          v183 = (char *)v329 + 28;
          if ( !(_DWORD)v156 )
            v183 = 0;
          if ( v183 )
          {
            v184 = (const void *)(v176 + 28);
            if ( !*(_DWORD *)(v176 + 60) )
              v184 = 0;
            if ( v184 )
            {
              v185 = (_DWORD)v156 ? (char *)v329 + 28 : 0LL;
              if ( !memcmp_0(v185, v184, 0x20u) && !lpData )
                goto LABEL_598;
            }
          }
          goto LABEL_482;
        }
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_360:
          ReleaseSRWLockExclusive(v136);
          goto LABEL_705;
        }
        v163 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&iid);
        v164 = 62;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_360;
        }
        v163 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
        v164 = 61;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_360;
      }
      v163 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
      v164 = 60;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v164,
      (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
      v163,
      Sddl);
    goto LABEL_360;
  }
  if ( (v284 & 2) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v154 = JobMoniker::GetPath((JobMoniker *)&v326);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids, v154);
    }
    Sddl = -2147024894;
    ReleaseSRWLockExclusive(v136);
    goto LABEL_704;
  }
  v273[0] = 1;
  TokenInformationLength = 0;
  JobMoniker::_GenId((JobMoniker *)&v326);
  *(_QWORD *)&EventDescriptor.Id = 0;
  LODWORD(EventDescriptor.Keyword) = 0;
  Sddl = RpcServer::CreateRegistrationPath(v155, v137, (struct JobSecurity *)&EventDescriptor, ClientToken);
  v275 = Sddl;
  if ( Sddl < 0 )
  {
    v157 = *(_QWORD *)&EventDescriptor.Id;
    if ( *(_QWORD *)&EventDescriptor.Id )
      LocalFree(*(HLOCAL *)&EventDescriptor.Id);
    goto LABEL_553;
  }
  v158 = *(void **)&EventDescriptor.Id;
  Sddl = JobAccessCheck(ClientToken, *(PSECURITY_DESCRIPTOR *)&EventDescriptor.Id, 2u);
  v275 = Sddl;
  if ( Sddl < 0 )
  {
    if ( v158 )
      LocalFree(v158);
    goto LABEL_553;
  }
  if ( v158 )
    LocalFree(v158);
LABEL_482:
  *(_QWORD *)&EventDescriptor.Id = 0;
  LODWORD(EventDescriptor.Keyword) = 0;
  if ( v273[0] || lpMem )
  {
    v188 = ClientToken;
    if ( lpMem )
    {
      v190 = SysAllocString((const OLECHAR *)lpMem);
      v192 = v190;
      bstrString = v190;
      if ( !v190 )
        ATL::PrivateAtlThrow(0x8007000E);
      goto LABEL_499;
    }
LABEL_494:
    if ( bstr )
    {
      v189 = SysStringByteLen(bstr);
      v190 = SysAllocStringByteLen((LPCSTR)bstr, v189);
      v191 = v190;
      bstrString = v190;
      if ( bstr && !v190 )
        ATL::PrivateAtlThrow(0x8007000E);
      v277 = 2;
      v288 = 2;
      v192 = bstrString;
LABEL_500:
      Sddl = JobStore::GenerateJobSecurity(
               (JobStore *)TokenHandle,
               v274,
               v190,
               0,
               v188,
               (PSECURITY_DESCRIPTOR *)&EventDescriptor);
      v275 = Sddl;
      v193 = v277;
      if ( (v277 & 4) != 0 )
      {
        v277 &= ~4u;
        v288 = v193 & 0xFFFFFFFB;
        SysFreeString(v192);
        v193 = v277;
      }
      if ( (v193 & 2) != 0 )
      {
        v277 = v193 & 0xFFFFFFFD;
        v288 = v193 & 0xFFFFFFFD;
        SysFreeString(v191);
      }
      if ( Sddl < 0 )
      {
        v157 = *(_QWORD *)&EventDescriptor.Id;
        if ( !*(_QWORD *)&EventDescriptor.Id )
          goto LABEL_553;
LABEL_506:
        LocalFree(*(HLOCAL *)&EventDescriptor.Id);
        *(_QWORD *)&EventDescriptor.Id = 0;
        goto LABEL_553;
      }
LABEL_509:
      ReturnLength[0] = v284 & 0x10;
      if ( (v284 & 0x10) == 0 )
      {
        v194 = (void **)*((_QWORD *)v329 + 8);
        hObject = v194;
        if ( v194 )
          User::UserEntry::AddRef((User::UserEntry *)v194);
        if ( User::IsAlias((JobBucket *)((char *)v329 + 64)) )
        {
          v196 = (CredStore *)CredStore::g_pCommonStore;
          v197 = User::GetAccount(v195, &bstrString);
          v198 = (const unsigned __int16 *)_bstr_t::operator unsigned short const *(v197);
          Sddl = CredStore::ResolveAlias(v196, v198, (struct User *)&hObject);
          v275 = Sddl;
          _bstr_t::~_bstr_t((_bstr_t *)&bstrString);
          if ( Sddl < 0 )
            goto LABEL_514;
          v194 = (void **)hObject;
        }
        v199 = 0;
        if ( !v273[0] && !lpMem && !bstr )
          v199 = (void *)*((_QWORD *)v13 + 4);
        Sddl = JobSecurity::AddRemovePrincipalAce((JobSecurity *)&EventDescriptor, v194[4], v199);
        v275 = Sddl;
        if ( Sddl < 0 )
        {
LABEL_514:
          wmi::AutoRef<User::UserEntry>::Release(&hObject);
          v157 = *(_QWORD *)&EventDescriptor.Id;
          if ( !*(_QWORD *)&EventDescriptor.Id )
            goto LABEL_553;
          goto LABEL_506;
        }
        wmi::AutoRef<User::UserEntry>::Release(&hObject);
      }
      v200 = v273[0];
      v201 = (JobStore *)TokenHandle;
      if ( v273[0] )
        updated = JobStore::RegTaskEntryCreate(
                    (JobStore *)TokenHandle,
                    (const struct JobMoniker *)&v326,
                    (const struct JobSecurity *)&EventDescriptor,
                    (const struct Triggers::Trigulator *)v318,
                    (const struct Actions::ActionCollection *)v314,
                    lpData);
      else
        updated = JobStore::UpdateTaskEntry(
                    (JobStore *)TokenHandle,
                    (const struct JobMoniker *)&v326,
                    v156,
                    (const struct Triggers::Trigulator *)v318,
                    (const struct Actions::ActionCollection *)v314,
                    (const struct DynamicTaskInfo *)lpData);
      Sddl = updated;
      v275 = updated;
      if ( updated < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v203 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
            v203,
            Sddl);
        }
        v157 = *(_QWORD *)&EventDescriptor.Id;
        if ( *(_QWORD *)&EventDescriptor.Id )
        {
          LocalFree(*(HLOCAL *)&EventDescriptor.Id);
          *(_QWORD *)&EventDescriptor.Id = 0;
        }
        goto LABEL_554;
      }
      if ( *(_QWORD *)&EventDescriptor.Id )
      {
        LocalFree(*(HLOCAL *)&EventDescriptor.Id);
        *(_QWORD *)&EventDescriptor.Id = 0;
      }
      RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&Size, L"RpcServer::RegisterTask", 1);
      if ( lpMem )
      {
        v205 = SysAllocString((const OLECHAR *)lpMem);
        v207 = v205;
        bstrString = v205;
        if ( !v205 )
          ATL::PrivateAtlThrow(0x8007000E);
      }
      else
      {
        if ( bstr )
        {
          v204 = SysStringByteLen(bstr);
          v205 = SysAllocStringByteLen((LPCSTR)bstr, v204);
          v206 = v205;
          bstrString = v205;
          if ( bstr && !v205 )
            ATL::PrivateAtlThrow(0x8007000E);
          v277 |= 8u;
          v288 = v277;
          v207 = bstrString;
          goto LABEL_542;
        }
        v207 = 0;
        bstrString = 0;
        v205 = 0;
      }
      v277 |= 0x10u;
      v288 = v277;
      v206 = bstrString;
LABEL_542:
      Sddl = JobStore::XmlSaveTaskFile(v201, (const struct JobMoniker *)&v326, (const unsigned __int16 *)Sid, v205);
      v275 = Sddl;
      v208 = v277;
      if ( (v277 & 0x10) != 0 )
      {
        v277 &= ~0x10u;
        SysFreeString(v207);
        v208 = v277;
      }
      if ( (v208 & 8) != 0 )
      {
        v277 = v208 & 0xFFFFFFF7;
        SysFreeString(v206);
      }
      if ( Sddl >= 0 )
      {
        if ( (_DWORD)Size )
          RpcRevertToSelf();
        if ( !ReturnLength[0] )
        {
          v213 = v329;
          v214 = (void *)*((_QWORD *)v329 + 8);
          hObject = v214;
          if ( v214 )
          {
            User::UserEntry::AddRef((User::UserEntry *)v214);
            v213 = v329;
          }
          if ( User::IsAlias((JobBucket *)((char *)v213 + 64))
            && (v216 = (CredStore *)CredStore::g_pCommonStore,
                v217 = User::GetAccount(v215, &bstrString),
                v218 = (const unsigned __int16 *)_bstr_t::operator unsigned short const *(v217),
                Sddl = CredStore::ResolveAlias(v216, v218, (struct User *)&hObject),
                v275 = Sddl,
                _bstr_t::~_bstr_t((_bstr_t *)&bstrString),
                Sddl < 0) )
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              v220 = v277;
            }
            else
            {
              v219 = User::GetAccount((char *)v329 + 64, &bstrString);
              v220 = v277 | 0x20;
              v221 = _bstr_t::operator unsigned short const *(v219);
              v222 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
              WPP_SF_SSD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                66,
                (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                v222,
                v221,
                Sddl);
            }
            if ( (v220 & 0x20) != 0 )
              _bstr_t::~_bstr_t((_bstr_t *)&bstrString);
          }
          else
          {
            RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&Size, L"RpcServer::RegisterTask", 1);
            v223 = (const struct User *)&v298;
            if ( lpMem )
              v223 = 0;
            Sddl = JobStore::HammerAcl(v201, (const struct JobMoniker *)&v326, (const struct User *)&hObject, v223);
            v275 = Sddl;
            if ( Sddl < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v224 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
                v224,
                Sddl);
            }
            if ( (_DWORD)Size )
              RpcRevertToSelf();
          }
          wmi::AutoRef<User::UserEntry>::Release(&hObject);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v209 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
            v209,
            Sddl);
        }
        if ( (_DWORD)Size )
          RpcRevertToSelf();
      }
      goto LABEL_553;
    }
    v192 = 0;
    bstrString = 0;
    v190 = 0;
LABEL_499:
    v277 = 4;
    v288 = 4;
    v191 = bstrString;
    goto LABEL_500;
  }
  if ( bstr )
  {
    v188 = ClientToken;
    goto LABEL_494;
  }
  v186 = SecurityDescriptor;
  if ( !SecurityDescriptor )
  {
    *(_QWORD *)&EventDescriptor.Id = 0;
    LODWORD(EventDescriptor.Keyword) = 0;
    goto LABEL_509;
  }
  LODWORD(Size) = RtlLengthSecurityDescriptor(SecurityDescriptor);
  v187 = LocalAlloc(0, (unsigned int)Size);
  v157 = *(_QWORD *)&EventDescriptor.Id;
  if ( *(_QWORD *)&EventDescriptor.Id )
    LocalFree(*(HLOCAL *)&EventDescriptor.Id);
  *(_QWORD *)&EventDescriptor.Id = v187;
  if ( v187 )
  {
    LODWORD(EventDescriptor.Keyword) = Size;
    memcpy_0(v187, v186, (unsigned int)Size);
    goto LABEL_509;
  }
  Sddl = -2147024882;
  v275 = -2147024882;
LABEL_553:
  v200 = v273[0];
LABEL_554:
  if ( Sddl < 0 )
  {
    if ( v200 )
    {
      RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)ReturnLength, L"RpcServer::RegisterTask", 1);
      v210 = (HKEY *)TokenHandle;
      JobStore::FileRemoveTaskXml((JobStore *)TokenHandle, (const struct JobMoniker *)&v326);
      if ( ReturnLength[0] )
        RpcRevertToSelf();
      if ( (int)JobStore::RemoveTaskEntryP(v210, &v326, 0) >= 0 )
        JobStore::FlushTaskEntryP(v211, v210[2]);
      v212 = v276;
    }
    else
    {
      v225 = JobStore::GenerateTaskXmlFromCollections(v157, &iid, v322, v321, &v276);
      v212 = v276;
      if ( v225 >= 0 && (int)JobStore::ComputeHash((struct JobMoniker *)&iid, v276) >= 0 )
      {
        RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)ReturnLength, L"RpcServer::RegisterTask", 1);
        JobStore::XmlSaveTaskFile(
          (JobStore *)TokenHandle,
          (const struct JobMoniker *)&iid,
          v212,
          StringSecurityDescriptor);
        if ( ReturnLength[0] )
          RpcRevertToSelf();
      }
      JobStore::UpdateTaskEntry(
        (JobStore *)TokenHandle,
        (const struct JobMoniker *)&iid,
        v226,
        (const struct Triggers::Trigulator *)v322,
        (const struct Actions::ActionCollection *)v321,
        0);
    }
    v34 = v274;
    if ( (*(_DWORD *)(v332 + 16) & 0x200000) != 0 )
    {
      if ( !PlugIn::IsRegistering((PlugIn *)&PlugIn::s_singleton, v274, v297) )
        PlugIn::RegisterTask((PlugIn *)&PlugIn::s_singleton, v34, v212, StringSecurityDescriptor, v284, v333);
    }
    else
    {
      PlugIn::DeleteTask((PlugIn *)&PlugIn::s_singleton, v274);
    }
    ReleaseSRWLockExclusive(v136);
    v33 = -1;
    goto LABEL_707;
  }
  v182 = TokenInformationLength;
LABEL_598:
  if ( ((v182 - 0x40000) & 0xFFFBFFFF) == 0 )
  {
    Sddl = CredStore::DeleteNtCredential((CredStore *)CredStore::g_pCommonStore, (const struct User *)&v298, (bool)v156);
    v275 = Sddl;
    if ( Sddl < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v227 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
          v227,
          Sddl);
      }
      Sddl = 0;
      v275 = 0;
    }
  }
  ReleaseSRWLockExclusive(v136);
  if ( !v273[0] )
  {
    RpcServer::FlushTriggers((const struct JobMoniker *)&v326);
    if ( (*(_DWORD *)(v332 + 16) & 0x2000000) == 0 && (*((_DWORD *)v329 + 4) & 0x2000000) != 0 )
    {
      Sddl = RpcServer::FlushTriggers((const struct JobMoniker *)&iid);
      v275 = Sddl;
      if ( tsched::IsErrorNotFound((tsched *)(unsigned int)Sddl, v228) )
      {
        Sddl = 0;
        v275 = 0;
      }
      else if ( Sddl < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v229 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            69,
            (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
            v229,
            Sddl);
        }
        Sddl = 267035;
        v275 = 267035;
        v33 = -1;
        v34 = v274;
        v212 = v276;
        goto LABEL_707;
      }
    }
    if ( (*(_DWORD *)(v332 + 16) & 0x2000000) != 0 && (*((_DWORD *)v329 + 4) & 0x2000000) == 0 )
    {
      Sddl = (*((__int64 (__fastcall **)(void ***, GUID *))UbpmProxySingleton::s_singleton[0] + 1))(
               UbpmProxySingleton::s_singleton,
               &iid);
      v275 = Sddl;
      if ( tsched::IsErrorNotFound((tsched *)(unsigned int)Sddl, v230) )
      {
        Sddl = 0;
        v275 = 0;
      }
      else if ( Sddl < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v231 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            70,
            (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
            v231,
            Sddl);
        }
        Sddl = 267035;
        v275 = 267035;
        v33 = -1;
        v34 = v274;
        v212 = v276;
        goto LABEL_707;
      }
    }
  }
  v232 = v284;
  if ( (*((_DWORD *)v329 + 4) & 0x2000000) != 0 )
  {
    v233 = v319;
    for ( k = (_QWORD *)*v319; k != v233; k = (_QWORD *)*k )
    {
      v235 = k[2];
      if ( v235 )
      {
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v235 + 72LL))(v235) == 34952 )
        {
          RpcAutoImpersonate::RpcAutoImpersonate(
            (RpcAutoImpersonate *)&TokenInformationLength,
            L"RpcServer::RegisterTask",
            1);
          LODWORD(Size) = -1;
          bstrString = 0;
          ReturnLength[0] = 0;
          lpMem = 0;
          v236 = GetCurrentThread();
          if ( OpenThreadToken(v236, 8u, 1, &lpMem)
            && GetTokenInformation(lpMem, TokenSessionId, &Size, 4u, ReturnLength) )
          {
            Sddl = 0;
            if ( (unsigned __int8)IsUMgrQueryUserContextPresent() )
            {
              v238 = UMgrQueryUserContext(lpMem, &bstrString);
              Sddl = v238;
              if ( v238 == -2147023584 || v238 == -2147023652 )
                Sddl = 0;
            }
          }
          else
          {
            v237 = GetLastError();
            Sddl = v237;
            if ( v237 > 0 )
              Sddl = (unsigned __int16)v237 | 0x80070000;
            if ( Sddl >= 0 )
              Sddl = -2147467259;
          }
          if ( (char *)lpMem - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            CloseHandle(lpMem);
            lpMem = 0;
          }
          v275 = Sddl;
          if ( TokenInformationLength )
            RpcRevertToSelf();
          break;
        }
        v233 = v319;
      }
    }
    if ( Sddl >= 0 )
    {
      UserDataa = (const struct _GUID *)v314;
      UserDataCounta = (unsigned __int16 *)v318;
      Sddl = (*(__int64 (__fastcall **)(void ***, _QWORD, GUID *, _QWORD))UbpmProxySingleton::s_singleton[0])(
               UbpmProxySingleton::s_singleton,
               0,
               &v326,
               v273[0]);
      v275 = Sddl;
    }
    tsched::SecretGuard::Erase((tsched::SecretGuard *)&v302);
    wmi::AutoVectorPtr<unsigned short>::operator=(&v299, 0);
    v301 = v302;
    v232 = v284;
  }
  else
  {
    LOBYTE(EventDescriptor.Id) = 0;
    *(_DWORD *)((char *)&EventDescriptor.Id + 1) = *(_DWORD *)((char *)&v336.Ptr + 1);
    *(_WORD *)&EventDescriptor.Opcode = *(_WORD *)((char *)&v336.Ptr + 5);
    HIBYTE(EventDescriptor.Task) = HIBYTE(v336.Ptr);
    EventDescriptor.Keyword = -1;
    LOBYTE(v309[0]) = 0;
    *(_DWORD *)((char *)v309 + 1) = *(_DWORD *)((char *)&v336.Ptr + 1);
    *(_WORD *)((char *)v309 + 5) = *(_WORD *)((char *)&v336.Ptr + 5);
    HIBYTE(v309[0]) = HIBYTE(v336.Ptr);
    v309[1] = 0;
    LODWORD(UserDataCounta) = (v284 & 0x20) == 0;
    Sddl = Triggers::Trigulator::RegisterAll(v318, &v326, v309, &EventDescriptor);
    if ( Sddl == 1 )
      Sddl = 0;
    v275 = Sddl;
  }
  v34 = v274;
  v240 = v303;
  if ( Sddl < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v241 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
        v241,
        Sddl);
    }
    EventManager::EvtReport(v239, &TASK_REGISTERED_WITHOUT_SOME_TRIGGERS, v293, Sddl, UserDataCounta, UserDataa);
    Sddl = 267035;
  }
  v242 = &TASK_DISABLED;
  if ( !v240 )
    v242 = &JOB_REGISTERED;
  v243 = (const struct _EVENT_DESCRIPTOR *)TASK_UPDATED;
  if ( (v232 & 4) == 0 )
    v243 = v242;
  v244 = v273[0];
  if ( !v273[0] || &JOB_REGISTERED == v243 )
  {
    EventManager::EvtReport(v239, v243, v293, *(const unsigned __int16 **)v289, UserDataCounta, UserDataa);
    if ( !v244 )
    {
      v250 = JobMoniker::GetPath((JobMoniker *)&v326);
      v247 = Auditor::AuditJobOperation(g_pAuditor, 2, v250, v14);
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_676;
      }
      v248 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
      v249 = 73;
      goto LABEL_675;
    }
  }
  else
  {
    EventManager::EvtReport(v239, &JOB_REGISTERED, v293, *(const unsigned __int16 **)v289, UserDataCounta, UserDataa);
    EventManager::EvtReport(v245, v243, v293, *(const unsigned __int16 **)v289, UserDataCountc, UserDatab);
  }
  v246 = JobMoniker::GetPath((JobMoniker *)&v326);
  v247 = Auditor::AuditJobOperation(g_pAuditor, 0, v246, v14);
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    goto LABEL_676;
  }
  v248 = (unsigned int)JobMoniker::GetPath((JobMoniker *)&v326);
  v249 = 72;
LABEL_675:
  WPP_SF_Sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v249,
    (unsigned int)WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids,
    v248,
    v247);
LABEL_676:
  if ( v304 )
  {
    v251 = v293;
    v293 = 0;
    *v304 = v251;
  }
  if ( v285 != 267036 )
    goto LABEL_705;
  v33 = -1;
  v212 = v276;
  if ( Sddl != 267035 )
    Sddl = 267036;
LABEL_707:
  if ( (unsigned int)dword_1800C0358 > 4 )
  {
    *(_DWORD *)IdentifierAuthority.Value = Sddl;
    v254 = v297;
    if ( v297 )
    {
      v255 = -1;
      do
        ++v255;
      while ( v297[v255] );
      v256 = 2 * v255 + 2;
    }
    else
    {
      v254 = (unsigned __int16 *)&ChannelPath;
      v256 = 2;
    }
    v349 = v254;
    v350 = v256;
    v351 = 0;
    p_IdentifierAuthority = &IdentifierAuthority;
    v348 = 4;
    if ( v34 )
    {
      v257 = -1;
      do
        ++v257;
      while ( v34[v257] );
      v258 = 2 * v257 + 2;
    }
    else
    {
      v34 = (unsigned __int16 *)&ChannelPath;
      v258 = 2;
    }
    v344 = v34;
    v345 = v258;
    v346 = 0;
    v336.Ptr = 0x2040B000000LL;
    *(_QWORD *)&v336.Size = 0;
    TokenInformation.Ptr = (ULONGLONG)off_1800C0360;
    TokenInformation.Size = *(unsigned __int16 *)off_1800C0360;
    TokenInformation.Reserved = 2;
    v341 = byte_1800B1B33;
    v342 = 40;
    v343 = 1;
    v296 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&v336, 0, 0, 5u, &TokenInformation);
  }
  v259 = v305;
  if ( v305 )
  {
    v260 = -1;
    do
      ++v260;
    while ( *(_WORD *)&v305[2 * v260] );
    for ( m = 2 * v260; m; --m )
      *v259++ = 0;
  }
  v262 = v329;
  if ( v329 && _InterlockedExchangeAdd((volatile signed __int32 *)v329 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(JobBucket *, __int64))v262)(v262, 1);
  v329 = 0;
  _bstr_t::~_bstr_t((_bstr_t *)&v327);
  SysFreeString(v14);
  SysFreeString(bstr);
  SysFreeString(v306);
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v314);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v318);
  _bstr_t::~_bstr_t((_bstr_t *)&v307);
  if ( (char *)ClientToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(ClientToken);
    ClientToken = 0;
  }
  v263 = v301;
  if ( v301 )
  {
    do
      ++v33;
    while ( v301[v33] );
    for ( n = 2 * v33; n; --n )
    {
      *(_BYTE *)v263 = 0;
      v263 = (unsigned __int16 *)((char *)v263 + 1);
    }
  }
  if ( v299 )
    HeapFree(g_PrivateHeap, 0, v299);
  Actions::ActionCollection::~ActionCollection((Actions::ActionCollection *)v321);
  Triggers::Trigulator::~Trigulator((Triggers::Trigulator *)v322);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  wmi::AutoRef<JobBucket>::Release(&v332);
  _bstr_t::~_bstr_t((_bstr_t *)v331);
  wmi::AutoRef<User::UserEntry>::Release(&v298);
  if ( StringSecurityDescriptor )
    HeapFree(g_PrivateHeap, 0, (LPVOID)StringSecurityDescriptor);
  if ( v212 )
    HeapFree(g_PrivateHeap, 0, v212);
  if ( v293 )
    HeapFree(g_PrivateHeap, 0, v293);
  return (unsigned int)Sddl;
}

```

## disassembly

```asm
0x180047ee0  push    rbx
0x180047ee2  push    rsi
0x180047ee3  push    rdi
0x180047ee4  push    r12
0x180047ee6  push    r13
0x180047ee8  push    r14
0x180047eea  push    r15
0x180047eec  sub     rsp, 830h
0x180047ef3  mov     rax, cs:__security_cookie
0x180047efa  xor     rax, rsp
0x180047efd  mov     [rsp+868h+var_48], rax
0x180047f05  mov     esi, r9d
0x180047f08  mov     rax, r8
0x180047f0b  mov     [rsp+868h+var_728], rax
0x180047f13  mov     r12, rdx
0x180047f16  mov     [rsp+868h+var_7E0], rdx
0x180047f1e  mov     [rsp+868h+bstrString], rcx
0x180047f26  mov     [rsp+868h+var_6A0], rax
0x180047f2e  mov     rcx, [rsp+868h+arg_20]
0x180047f36  mov     [rsp+868h+lpMem], rcx
0x180047f3e  mov     rbx, [rsp+868h+arg_38]
0x180047f46  mov     [rsp+868h+var_768], rbx
0x180047f4e  mov     rax, [rsp+868h+arg_40]
0x180047f56  mov     [rsp+868h+lpData], rax
0x180047f5e  mov     rax, [rsp+868h+arg_48]
0x180047f66  mov     [rsp+868h+var_6F0], rax
0x180047f6e  mov     r13, [rsp+868h+arg_50]
0x180047f76  mov     [rsp+868h+var_740], r13
0x180047f7e  xor     edi, edi
0x180047f80  mov     eax, edi
0x180047f82  mov     [rsp+868h+var_7C8], eax
0x180047f89  mov     [rsp+868h+var_770], eax
0x180047f90  mov     [rsp+868h+var_7D8], edi
0x180047f97  mov     [rsp+868h+var_748], rdi
0x180047f9f  mov     [rsp+868h+var_7D0], rdi
0x180047fa7  mov     [rsp+868h+StringSecurityDescriptor], rdi
0x180047faf  mov     r14d, edi
0x180047fb2  mov     [rsp+868h+var_720], rdi
0x180047fba  xor     r8d, r8d; unsigned __int16 *
0x180047fbd  xor     edx, edx; psz
0x180047fbf  lea     rcx, [rsp+868h+iid]; lpiid
0x180047fc7  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x180047fcc  nop
0x180047fcd  mov     [rsp+868h+SecurityDescriptor], rdi
0x180047fd5  mov     [rsp+868h+var_6B0], edi
0x180047fdc  lea     rcx, [rsp+868h+var_610]; this
0x180047fe4  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180047fe9  nop
0x180047fea  lea     rcx, [rsp+868h+var_628]; this
0x180047ff2  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x180047ff7  nop
0x180047ff8  mov     [rsp+868h+var_718], rdi
0x180048000  mov     eax, edi
0x180048002  mov     [rsp+868h+var_708], rax
0x18004800a  mov     [rsp+868h+var_700], rax
0x180048012  mov     [rsp+868h+ClientToken], rdi
0x18004801a  mov     [rsp+868h+var_6D8], rdi
0x180048022  xorps   xmm0, xmm0
0x180048025  movups  [rsp+868h+var_678], xmm0
0x18004802d  mov     [rsp+868h+var_668], rax
0x180048035  lea     rcx, [rsp+868h+var_660]; this
0x18004803d  call    ??0Trigulator@Triggers@@QEAA@XZ; Triggers::Trigulator::Trigulator(void)
0x180048042  nop
0x180048043  lea     rcx, [rsp+868h+var_698]; this
0x18004804b  call    ??0ActionCollection@Actions@@QEAA@XZ; Actions::ActionCollection::ActionCollection(void)
0x180048050  nop
0x180048051  mov     [rsp+868h+var_6E0], rdi
0x180048059  mov     [rsp+868h+bstr], rdi
0x180048061  mov     r15d, edi
0x180048064  mov     [rsp+868h+var_6A8], rdi
0x18004806c  xor     r8d, r8d; unsigned __int16 *
0x18004806f  mov     rdx, r12; psz
0x180048072  lea     rcx, [rsp+868h+var_560]; lpiid
0x18004807a  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18004807f  nop
0x180048080  cmp     [rsp+868h+arg_30], edi
0x180048087  jbe     short loc_18004808F
0x180048089  mov     rax, [rbx+8]
0x18004808d  jmp     short loc_180048092
0x18004808f  mov     rax, rdi
0x180048092  mov     [rsp+868h+var_6E8], rax
0x18004809a  mov     [rsp+868h+var_680], rax
0x1800480a2  mov     eax, cs:dword_1800C0358
0x1800480a8  cmp     eax, 5
0x1800480ab  jbe     loc_18004816F
0x1800480b1  mov     dword ptr [rsp+868h+EventDescriptor.Id], 0B000000h
0x1800480bc  movzx   eax, cs:word_1800B1B09
0x1800480c3  mov     dword ptr [rsp+868h+EventDescriptor.Level], eax
0x1800480ca  mov     [rsp+868h+EventDescriptor.Keyword], rdi
0x1800480d2  mov     rax, cs:off_1800C0360
0x1800480d9  mov     [rsp+868h+var_C8.Ptr], rax
0x1800480e1  movzx   eax, word ptr [rax]
0x1800480e4  mov     [rsp+868h+var_C8.Size], eax
0x1800480eb  mov     dword ptr [rsp+868h+var_C8.0Ch], 2
0x1800480f6  lea     rax, byte_1800B1B13
0x1800480fd  mov     [rsp+868h+var_B8], rax
0x180048105  mov     [rsp+868h+var_B0], 14h
0x180048110  mov     [rsp+868h+var_AC], 1
0x18004811b  lea     rax, _TraceLoggingMetadataEnd
0x180048122  lea     rcx, _TraceLoggingMetadata
0x180048129  sub     eax, ecx
0x18004812b  mov     [rsp+868h+var_794], eax
0x180048132  mov     eax, [rsp+868h+var_794]
0x180048139  lea     rax, [rsp+868h+var_C8]
0x180048141  mov     [rsp+868h+UserData], rax; struct _GUID *
0x180048146  mov     [rsp+868h+UserDataCount], 2; void *
0x18004814e  xor     r9d, r9d; RelatedActivityId
0x180048151  xor     r8d, r8d; ActivityId
0x180048154  lea     rdx, [rsp+868h+EventDescriptor]; EventDescriptor
0x18004815c  mov     rcx, cs:RegHandle; RegHandle
0x180048163  call    cs:__imp_EventWriteTransfer
0x18004816a  nop     dword ptr [rax+rax+00h]
0x18004816f  xor     ecx, ecx; BindingHandle
0x180048171  call    cs:__imp_RpcImpersonateClient
0x180048178  nop     dword ptr [rax+rax+00h]
0x18004817d  mov     ebx, eax
0x18004817f  test    eax, eax
0x180048181  jnz     loc_18004BD3C
0x180048187  mov     [rsp+868h+TokenInformationLength], 58h ; 'X'
0x180048192  mov     [rsp+868h+TokenHandle], rdi
0x18004819a  mov     [rsp+868h+var_7E8], 0
0x1800481a2  call    cs:__imp_GetCurrentThread
0x1800481a9  nop     dword ptr [rax+rax+00h]
0x1800481ae  mov     rcx, rax; ThreadHandle
0x1800481b1  lea     r9, [rsp+868h+TokenHandle]; TokenHandle
0x1800481b9  mov     edx, 8; DesiredAccess
0x1800481be  mov     r8d, 1; OpenAsSelf
0x1800481c4  call    cs:__imp_OpenThreadToken
0x1800481cb  nop     dword ptr [rax+rax+00h]
0x1800481d0  test    eax, eax
0x1800481d2  jz      loc_180048310
0x1800481d8  lea     rax, [rsp+868h+TokenInformationLength]
0x1800481e0  mov     qword ptr [rsp+868h+UserDataCount], rax; ReturnLength
0x1800481e5  mov     r9d, [rsp+868h+TokenInformationLength]; TokenInformationLength
0x1800481ed  lea     r8, [rsp+868h+TokenInformation]; TokenInformation
0x1800481f5  mov     edx, 19h; TokenInformationClass
0x1800481fa  mov     rcx, [rsp+868h+TokenHandle]; TokenHandle
0x180048202  call    cs:__imp_GetTokenInformation
0x180048209  nop     dword ptr [rax+rax+00h]
0x18004820e  test    eax, eax
0x180048210  jz      loc_1800482EC
0x180048216  mov     dword ptr [rsp+868h+IdentifierAuthority.Value], 0
0x180048221  mov     word ptr [rsp+868h+IdentifierAuthority.Value+4], 1000h
0x18004822b  mov     [rsp+868h+var_760], rdi
0x180048233  lea     rax, [rsp+868h+var_760]
0x18004823b  mov     [rsp+868h+Sid], rax; Sid
0x180048240  mov     [rsp+868h+SubAuthority7], edi; SubAuthority7
0x180048244  mov     [rsp+868h+SubAuthority6], edi; SubAuthority6
0x180048248  mov     [rsp+868h+SubAuthority5], edi; SubAuthority5
0x18004824c  mov     [rsp+868h+SubAuthority4], edi; SubAuthority4
0x180048250  mov     dword ptr [rsp+868h+UserData], edi; SubAuthority3
0x180048254  mov     [rsp+868h+UserDataCount], edi; SubAuthority2
0x180048258  xor     r9d, r9d; SubAuthority1
0x18004825b  mov     r8d, 2000h; SubAuthority0
0x180048261  mov     dl, 1; SubAuthorityCount
0x180048263  lea     rcx, [rsp+868h+IdentifierAuthority]; IdentifierAuthority
0x18004826b  call    cs:__imp_RtlAllocateAndInitializeSid
0x180048272  nop     dword ptr [rax+rax+00h]
0x180048277  test    eax, eax
0x180048279  js      short loc_1800482DC
0x18004827b  lea     r8, [rsp+868h+var_7E8]
0x180048283  mov     rdx, [rsp+868h+var_760]
0x18004828b  mov     rcx, [rsp+868h+TokenInformation]
0x180048293  call    cs:__imp_RtlSidDominates
0x18004829a  nop     dword ptr [rax+rax+00h]
0x18004829f  mov     ebx, eax
0x1800482a1  mov     rcx, [rsp+868h+var_760]; Sid
0x1800482a9  call    cs:__imp_RtlFreeSid
0x1800482b0  nop     dword ptr [rax+rax+00h]
0x1800482b5  test    ebx, ebx
0x1800482b7  jns     short loc_1800482C9
0x1800482b9  mov     ecx, ebx; Status
0x1800482bb  call    cs:__imp_RtlNtStatusToDosError
0x1800482c2  nop     dword ptr [rax+rax+00h]
0x1800482c7  jmp     short loc_1800482F8
0x1800482c9  mov     ebx, edi
0x1800482cb  cmp     [rsp+868h+var_7E8], dil
0x1800482d3  jnz     short loc_1800482FA
0x1800482d5  mov     ebx, 5
0x1800482da  jmp     short loc_1800482FA
0x1800482dc  mov     ecx, eax; Status
0x1800482de  call    cs:__imp_RtlNtStatusToDosError
0x1800482e5  nop     dword ptr [rax+rax+00h]
0x1800482ea  jmp     short loc_1800482F8
0x1800482ec  call    cs:__imp_GetLastError
0x1800482f3  nop     dword ptr [rax+rax+00h]
0x1800482f8  mov     ebx, eax
0x1800482fa  mov     rcx, [rsp+868h+TokenHandle]; hObject
0x180048302  call    cs:__imp_CloseHandle
0x180048309  nop     dword ptr [rax+rax+00h]
0x18004830e  jmp     short loc_18004831E
0x180048310  call    cs:__imp_GetLastError
0x180048317  nop     dword ptr [rax+rax+00h]
0x18004831c  mov     ebx, eax
0x18004831e  test    ebx, ebx
0x180048320  jnz     loc_18004B8E1
0x180048326  call    cs:__imp_RpcRevertToSelf
0x18004832d  nop     dword ptr [rax+rax+00h]
0x180048332  mov     rax, [rsp+868h+var_6F0]
0x18004833a  test    rax, rax
0x18004833d  jz      short loc_180048342
0x18004833f  mov     [rax], rdi
0x180048342  test    r13, r13
0x180048345  jz      short loc_18004834B
0x180048347  mov     [r13+0], rdi
0x18004834b  mov     eax, [rsp+868h+arg_28]
0x180048352  cmp     eax, 6
0x180048355  jbe     short loc_1800483A0
0x180048357  lea     r13, WPP_GLOBAL_Control
0x18004835e  mov     rcx, cs:WPP_GLOBAL_Control
0x180048365  cmp     rcx, r13
0x180048368  jz      short loc_180048395
0x18004836a  test    dword ptr [rcx+1Ch], 10000h
0x180048371  jz      short loc_180048395
0x180048373  cmp     byte ptr [rcx+19h], 2
0x180048377  jb      short loc_180048395
0x180048379  mov     edx, 1Dh
0x18004837e  mov     [rsp+868h+UserDataCount], eax
0x180048382  mov     r9, r12
0x180048385  lea     r8, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids
0x18004838c  mov     rcx, [rcx+10h]
0x180048390  call    WPP_SF_Sd
0x180048395  mov     r12d, 80070057h
0x18004839b  jmp     loc_18004B960
0x1800483a0  mov     r8, [rsp+868h+var_728]
0x1800483a8  test    r8, r8
0x1800483ab  jnz     short loc_1800483F2
0x1800483ad  lea     r13, WPP_GLOBAL_Control
0x1800483b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483bb  cmp     rcx, r13
0x1800483be  jz      short loc_180048395
0x1800483c0  test    dword ptr [rcx+1Ch], 10000h
0x1800483c7  jz      short loc_180048395
0x1800483c9  cmp     byte ptr [rcx+19h], 2
0x1800483cd  jb      short loc_180048395
0x1800483cf  mov     edx, 1Eh
0x1800483d4  mov     r9, r12
0x1800483d7  lea     r8, WPP_91ce23f421b63f0f29b1ef8f0526c4d8_Traceguids
0x1800483de  mov     rcx, [rcx+10h]
0x1800483e2  call    WPP_SF_S
0x1800483e7  mov     r12d, 80070057h
0x1800483ed  jmp     loc_18004B960
0x1800483f2  mov     edx, 2
0x1800483f7  test    esi, esi
0x1800483f9  cmovnz  edx, esi
0x1800483fc  mov     [rsp+868h+var_798], edx
0x180048403  mov     [rsp+868h+var_730], edx
0x18004840a  test    edx, 0FFFFFFC0h
0x180048410  jnz     loc_18004B8A6
0x180048416  test    dl, 7
0x180048419  jz      loc_18004B8A6
0x18004841f  test    edx, 0FFFFFFFEh
0x180048425  setnz   cl
0x180048428  test    dl, 1
0x18004842b  setnz   al
0x18004842e  test    al, cl
0x180048430  jnz     loc_18004B8A6
0x180048436  mov     esi, [rsp+868h+arg_30]
0x18004843d  test    esi, esi
0x18004843f  jnz     short loc_180048488
0x180048441  cmp     [rsp+868h+var_768], 0
0x18004844a  jz      loc_180048513
0x180048450  lea     r13, WPP_GLOBAL_Control
0x180048457  mov     rcx, cs:WPP_GLOBAL_Control
0x18004845e  cmp     rcx, r13
0x180048461  jz      loc_180048395
0x180048467  test    dword ptr [rcx+1Ch], 10000h
0x18004846e  jz      loc_180048395
0x180048474  cmp     byte ptr [rcx+19h], 2
0x180048478  jb      loc_180048395
0x18004847e  mov     edx, 20h ; ' '
0x180048483  jmp     loc_1800483D4
0x180048488  mov     r9, [rsp+868h+var_768]
0x180048490  test    dword ptr [r9+10h], 0FFFFFFFEh
0x180048498  jz      short loc_1800484D2
0x18004849a  lea     r13, WPP_GLOBAL_Control
0x1800484a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484a8  cmp     rcx, r13
0x1800484ab  jz      loc_180048395
0x1800484b1  test    dword ptr [rcx+1Ch], 10000h
0x1800484b8  jz      loc_180048395
0x1800484be  cmp     byte ptr [rcx+19h], 2
0x1800484c2  jb      loc_180048395
0x1800484c8  mov     edx, 21h ; '!'
0x1800484cd  jmp     loc_1800483D4
0x1800484d2  cmp     esi, 1
0x1800484d5  jbe     short loc_180048513
0x1800484d7  lea     r13, WPP_GLOBAL_Control
0x1800484de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484e5  cmp     rcx, r13
0x1800484e8  jz      loc_180048395
0x1800484ee  test    dword ptr [rcx+1Ch], 10000h
0x1800484f5  jz      loc_180048395
0x1800484fb  cmp     byte ptr [rcx+19h], 2
0x1800484ff  jb      loc_180048395
0x180048505  mov     edx, 22h ; '"'
0x18004850a  mov     [rsp+868h+UserDataCount], esi
0x18004850e  jmp     loc_180048382
0x180048513  test    dl, 1
0x180048516  jz      loc_180048717
  ... truncated ...
```
