# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::UnlockWrite(void)

- ea: `0x1400125a0`
- end: `0x1400125bb`
- name: `?UnlockWrite@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@MEAAXXZ`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1400125a0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400125b4`

## pseudocode

```c
void __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::UnlockWrite(
        __int64 a1)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)(a1 + 64);
  if ( (*(_DWORD *)(v1 + 44))-- == 1 )
    *(_DWORD *)(v1 + 40) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v1);
}

```

## disassembly

```asm
0x1400125a0  mov     rcx, [rcx+40h]
0x1400125a4  add     dword ptr [rcx+2Ch], 0FFFFFFFFh
0x1400125a8  mov     eax, [rcx+2Ch]
0x1400125ab  jnz     short loc_1400125B4
0x1400125ad  mov     dword ptr [rcx+28h], 0
0x1400125b4  jmp     cs:__imp_LeaveCriticalSection
```
