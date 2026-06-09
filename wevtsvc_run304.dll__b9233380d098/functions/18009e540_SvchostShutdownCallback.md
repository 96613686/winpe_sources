# SvchostShutdownCallback

- ea: `0x18009e540`
- end: `0x18009e5d0`
- name: `SvchostShutdownCallback`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800660ac`
- `0x18009e314`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009e593`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009e593`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009e55c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009e5bb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009e55c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009e5bb`

## pseudocode

```c
__int64 SvchostShutdownCallback()
{
  RTL_SRWLOCK *v1; // [rsp+20h] [rbp-18h] BYREF
  char v2; // [rsp+28h] [rbp-10h]

  ServiceStatus.dwCurrentState = 3;
  SetServiceStatus(g_serviceControl, &ServiceStatus);
  (*(void (__fastcall **)(__int64))(qword_180111728 + 216))(qword_1801116A8);
  qword_1801116A8 = 0;
  v1 = &stru_1801119A8;
  AcquireSRWLockExclusive(&stru_1801119A8);
  v2 = 1;
  Shutdown();
  ServiceStatus.dwCurrentState = 1;
  SetServiceStatus(g_serviceControl, &ServiceStatus);
  return utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v1);
}

```

## disassembly

```asm
0x18009e540  sub     rsp, 38h
0x18009e544  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18009e54b  lea     rdx, ServiceStatus; lpServiceStatus
0x18009e552  mov     cs:ServiceStatus.dwCurrentState, 3
0x18009e55c  call    cs:__imp_SetServiceStatus
0x18009e562  mov     rax, cs:qword_180111728
0x18009e569  mov     rcx, cs:qword_1801116A8
0x18009e570  mov     rax, [rax+0D8h]
0x18009e577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e57c  lea     rcx, stru_1801119A8; SRWLock
0x18009e583  mov     cs:qword_1801116A8, 0
0x18009e58e  mov     [rsp+38h+var_18], rcx
0x18009e593  call    cs:__imp_AcquireSRWLockExclusive
0x18009e599  mov     [rsp+38h+var_10], 1
0x18009e59e  call    ?Shutdown@@YAXAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z; Shutdown(utl::unique_lock<utl::mutex> &)
0x18009e5a3  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18009e5aa  lea     rdx, ServiceStatus; lpServiceStatus
0x18009e5b1  mov     cs:ServiceStatus.dwCurrentState, 1
0x18009e5bb  call    cs:__imp_SetServiceStatus
0x18009e5c1  lea     rcx, [rsp+38h+var_18]
0x18009e5c6  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x18009e5cb  add     rsp, 38h
0x18009e5cf  retn
```
