# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::CompareKeys(void const *,void const *)

- ea: `0x140010f70`
- end: `0x140010f83`
- name: `?CompareKeys@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@MEBAHPEBX0@Z`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140010f70`

## pseudocode

```c
__int64 __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::CompareKeys(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  if ( *a2 == *a3 )
    return 0;
  else
    return *a2 < *a3 ? -1 : 1;
}

```

## disassembly

```asm
0x140010f70  mov     rax, [rdx]
0x140010f73  cmp     rax, [r8]
0x140010f76  jnz     short loc_140010F7B
0x140010f78  xor     eax, eax
0x140010f7a  retn
0x140010f7b  sbb     eax, eax
0x140010f7d  and     eax, 0FFFFFFFEh
0x140010f80  inc     eax
0x140010f82  retn
```
