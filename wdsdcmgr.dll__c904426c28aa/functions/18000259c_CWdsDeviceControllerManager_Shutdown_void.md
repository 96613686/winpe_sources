# CWdsDeviceControllerManager::Shutdown(void)

- ea: `0x18000259c`
- end: `0x18000267e`
- name: `?Shutdown@CWdsDeviceControllerManager@@QEAAXXZ`
- size: `226`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800076a0`
- `0x180016070`

## callees

- `0x18000259c`
- `0x180006bec`
- `0x180006c98`
- `0x180006d2c`
- `0x1800073ec`
- `0x180013314`
- `0x1800133ec`
- `0x1800150b8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800025a9`
- `KERNEL32!EnterCriticalSection` at `0x18000262d`
- `KERNEL32!EnterCriticalSection` at `0x1800025a9`
- `KERNEL32!EnterCriticalSection` at `0x18000262d`
- `KERNEL32!LeaveCriticalSection` at `0x1800025bf`
- `KERNEL32!LeaveCriticalSection` at `0x180002669`
- `KERNEL32!LeaveCriticalSection` at `0x1800025bf`
- `KERNEL32!LeaveCriticalSection` at `0x180002669`
- `KERNEL32!GetCurrentThreadId` at `0x18000263c`
- `KERNEL32!GetCurrentThreadId` at `0x18000263c`
- `ole32!CoUninitialize` at `0x18000264a`
- `ole32!CoUninitialize` at `0x18000264a`

## pseudocode

```c
void __fastcall CWdsDeviceControllerManager::Shutdown(LPCRITICAL_SECTION lpCriticalSection)
{
  int DebugInfo; // ebx
  PRTL_CRITICAL_SECTION_DEBUG v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8

  EnterCriticalSection(lpCriticalSection);
  lpCriticalSection[5].LockCount = 0;
  DebugInfo = (int)lpCriticalSection[6].DebugInfo;
  LeaveCriticalSection(lpCriticalSection);
  CloseEndpointOutsideLock<CCriticalSection>(lpCriticalSection);
  CloseEndpointOutsideLock<CCriticalSection>(lpCriticalSection);
  if ( DebugInfo )
  {
    CMRSWLock::WriterLock(lpCriticalSection + 1);
    CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocatePointer>::Clear(&lpCriticalSection[4]);
    CDynArray<CWdsDeviceControllerManager::CManagementEntry *,CDeallocatePointer>::Clear(&lpCriticalSection[4].LockSemaphore);
    v3 = lpCriticalSection[8].DebugInfo;
    if ( v3 )
    {
      operator delete(v3);
      lpCriticalSection[8].DebugInfo = 0;
    }
    CMRSWLock::WriterRelease((CMRSWLock *)&lpCriticalSection[1]);
  }
  EnterCriticalSection(lpCriticalSection);
  if ( LODWORD(lpCriticalSection[8].OwningThread) && lpCriticalSection[8].RecursionCount == GetCurrentThreadId() )
  {
    CoUninitialize();
    LODWORD(lpCriticalSection[8].OwningThread) = 0;
    lpCriticalSection[8].RecursionCount = 0;
  }
  lpCriticalSection[5].OwningThread = 0;
  LeaveCriticalSection(lpCriticalSection);
  McGenEventUnregister(v5, v4, v6);
}

```

## disassembly

```asm
0x18000259c  mov     [rsp+arg_0], rbx
0x1800025a1  push    rdi
0x1800025a2  sub     rsp, 20h
0x1800025a6  mov     rdi, rcx
0x1800025a9  call    cs:__imp_EnterCriticalSection
0x1800025af  and     dword ptr [rdi+0D0h], 0
0x1800025b6  mov     rcx, rdi; lpCriticalSection
0x1800025b9  mov     ebx, [rdi+0F0h]
0x1800025bf  call    cs:__imp_LeaveCriticalSection
0x1800025c5  lea     rdx, [rdi+0E0h]
0x1800025cc  mov     rcx, rdi; lpCriticalSection
0x1800025cf  call    ??$CloseEndpointOutsideLock@VCCriticalSection@@@@YAXAEAVCCriticalSection@@AEAPEAX@Z; CloseEndpointOutsideLock<CCriticalSection>(CCriticalSection &,void * &)
0x1800025d4  lea     rdx, [rdi+0E8h]
0x1800025db  mov     rcx, rdi; lpCriticalSection
0x1800025de  call    ??$CloseEndpointOutsideLock@VCCriticalSection@@@@YAXAEAVCCriticalSection@@AEAPEAX@Z; CloseEndpointOutsideLock<CCriticalSection>(CCriticalSection &,void * &)
0x1800025e3  test    ebx, ebx
0x1800025e5  jz      short loc_18000262A
0x1800025e7  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800025eb  call    ?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x1800025f0  lea     rcx, [rdi+0A0h]
0x1800025f7  call    ?Clear@?$CDynArray@PEAUCQueryEntry@CWdsDeviceControllerManager@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocatePointer>::Clear(void)
0x1800025fc  lea     rcx, [rdi+0B8h]
0x180002603  call    ?Clear@?$CDynArray@PEAUCManagementEntry@CWdsDeviceControllerManager@@VCDeallocatePointer@@@@QEAAXXZ; CDynArray<CWdsDeviceControllerManager::CManagementEntry *,CDeallocatePointer>::Clear(void)
0x180002608  mov     rcx, [rdi+140h]; Block
0x18000260f  test    rcx, rcx
0x180002612  jz      short loc_180002621
0x180002614  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002619  and     qword ptr [rdi+140h], 0
0x180002621  lea     rcx, [rdi+28h]; this
0x180002625  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x18000262a  mov     rcx, rdi; lpCriticalSection
0x18000262d  call    cs:__imp_EnterCriticalSection
0x180002633  cmp     dword ptr [rdi+150h], 0
0x18000263a  jz      short loc_18000265E
0x18000263c  call    cs:__imp_GetCurrentThreadId
0x180002642  cmp     [rdi+14Ch], eax
0x180002648  jnz     short loc_18000265E
0x18000264a  call    cs:__imp_CoUninitialize
0x180002650  and     dword ptr [rdi+150h], 0
0x180002657  and     dword ptr [rdi+14Ch], 0
0x18000265e  and     qword ptr [rdi+0D8h], 0
0x180002666  mov     rcx, rdi; lpCriticalSection
0x180002669  call    cs:__imp_LeaveCriticalSection
0x18000266f  mov     rbx, [rsp+28h+arg_0]
0x180002674  add     rsp, 20h
0x180002678  pop     rdi
0x180002679  jmp     McGenEventUnregister
```
