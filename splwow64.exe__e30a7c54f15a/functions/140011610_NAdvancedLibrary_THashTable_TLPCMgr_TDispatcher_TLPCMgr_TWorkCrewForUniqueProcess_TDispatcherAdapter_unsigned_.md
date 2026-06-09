# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::NodeLifetimeIncrementIfNotZero(NAdvancedLibrary::THashElementBase *)

- ea: `0x140011610`
- end: `0x14001161c`
- name: `?NodeLifetimeIncrementIfNotZero@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@MEBAJPEAVTHashElementBase@2@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140016010`

## pseudocode

```c
__int64 __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::NodeLifetimeIncrementIfNotZero(
        __int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
}

```

## disassembly

```asm
0x140011610  mov     rax, [rcx]
0x140011613  mov     rax, [rax+28h]
0x140011617  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
