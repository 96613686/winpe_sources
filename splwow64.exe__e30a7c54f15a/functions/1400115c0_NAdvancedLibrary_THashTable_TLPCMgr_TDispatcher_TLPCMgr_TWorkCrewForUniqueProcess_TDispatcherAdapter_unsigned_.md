# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::KeyFromElement(NAdvancedLibrary::THashElementBase *)

- ea: `0x1400115c0`
- end: `0x1400115cb`
- name: `?KeyFromElement@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@MEBAPEBXPEAVTHashElementBase@2@@Z`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::KeyFromElement(
        __int64 a1,
        __int64 a2)
{
  return *(_QWORD *)(a2 + 32) + 232LL;
}

```

## disassembly

```asm
0x1400115c0  mov     rax, [rdx+20h]
0x1400115c4  add     rax, 0E8h
0x1400115ca  retn
```
