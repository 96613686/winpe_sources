# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::CalculateHash(void const *)

- ea: `0x140010f60`
- end: `0x140010f64`
- name: `?CalculateHash@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@MEBA_KPEBX@Z`
- size: `4`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::CalculateHash(
        __int64 a1,
        __int64 a2)
{
  return *(_QWORD *)a2;
}

```

## disassembly

```asm
0x140010f60  mov     rax, [rdx]
0x140010f63  retn
```
