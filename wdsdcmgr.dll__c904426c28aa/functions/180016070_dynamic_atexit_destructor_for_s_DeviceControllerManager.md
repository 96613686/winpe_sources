# _dynamic_atexit_destructor_for__s_DeviceControllerManager__

- ea: `0x180016070`
- end: `0x1800160c2`
- name: `_dynamic_atexit_destructor_for__s_DeviceControllerManager__`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000259c`
- `0x180006bec`
- `0x180006c98`
- `0x18000a5e8`
- `0x180013048`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800160bb`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_DeviceControllerManager__()
{
  __int64 v0; // rdx
  __int64 v1; // r8
  int v2; // r9d

  CWdsDeviceControllerManager::Shutdown(&CriticalSection);
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&qword_18001DEA8);
  CDynArray<CWdsDeviceControllerManager::CManagementEntry *,CDeallocatePointer>::Clear(&qword_18001DE68);
  CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocatePointer>::Clear(&qword_18001DE50);
  CMRSWLock::~CMRSWLock((CMRSWLock *)&stru_18001DDD8, v0, v1, v2);
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180016070  sub     rsp, 28h
0x180016074  lea     rcx, CriticalSection; lpCriticalSection
0x18001607b  call    ?Shutdown@CWdsDeviceControllerManager@@QEAAXXZ; CWdsDeviceControllerManager::Shutdown(void)
0x180016080  lea     rcx, qword_18001DEA8; this
0x180016087  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x18001608c  lea     rcx, qword_18001DE68
0x180016093  call    ?Clear@?$CDynArray@PEAUCManagementEntry@CWdsDeviceControllerManager@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsDeviceControllerManager::CManagementEntry *,CDeallocatePointer>::Clear(void)
0x180016098  lea     rcx, qword_18001DE50
0x18001609f  call    ?Clear@?$CDynArray@PEAUCQueryEntry@CWdsDeviceControllerManager@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocatePointer>::Clear(void)
0x1800160a4  lea     rcx, stru_18001DDD8; this
0x1800160ab  call    ??1CMRSWLock@@QEAA@XZ; CMRSWLock::~CMRSWLock(void)
0x1800160b0  lea     rcx, CriticalSection
0x1800160b7  add     rsp, 28h
0x1800160bb  jmp     cs:__imp_DeleteCriticalSection
```
