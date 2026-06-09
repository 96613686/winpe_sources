# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::LockWrite(void)

- ea: `0x1400115e0`
- end: `0x140011605`
- name: `?LockWrite@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@MEAAXXZ`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400115f6`
- `KERNEL32!GetCurrentThreadId` at `0x1400115f6`
- `KERNEL32!EnterCriticalSection` at `0x1400115ed`
- `KERNEL32!EnterCriticalSection` at `0x1400115ed`

## pseudocode

```c
DWORD __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::LockWrite(
        __int64 a1)
{
  __int64 v1; // rbx
  DWORD result; // eax

  v1 = *(_QWORD *)(a1 + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)v1);
  ++*(_DWORD *)(v1 + 44);
  result = GetCurrentThreadId();
  *(_DWORD *)(v1 + 40) = result;
  return result;
}

```

## disassembly

```asm
0x1400115e0  push    rbx
0x1400115e2  sub     rsp, 20h
0x1400115e6  mov     rbx, [rcx+40h]
0x1400115ea  mov     rcx, rbx; lpCriticalSection
0x1400115ed  call    cs:__imp_EnterCriticalSection
0x1400115f3  inc     dword ptr [rbx+2Ch]
0x1400115f6  call    cs:__imp_GetCurrentThreadId
0x1400115fc  mov     [rbx+28h], eax
0x1400115ff  add     rsp, 20h
0x140011603  pop     rbx
0x140011604  retn
```
