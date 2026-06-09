# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::`scalar deleting destructor'(uint)

- ea: `0x1400109f0`
- end: `0x140010a24`
- name: `??_G?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x140001b90`
- `0x1400105e4`
- `0x1400109f0`

## pseudocode

```c
LPCRITICAL_SECTION *__fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::`scalar deleting destructor'(
        LPCRITICAL_SECTION *Block,
        char a2)
{
  NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::~THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1400109f0  mov     [rsp+arg_0], rbx
0x1400109f5  push    rdi
0x1400109f6  sub     rsp, 20h
0x1400109fa  mov     ebx, edx
0x1400109fc  mov     rdi, rcx
0x1400109ff  call    ??1?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@UEAA@XZ; NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::~THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>(void)
0x140010a04  test    bl, 1
0x140010a07  jz      short loc_140010A16
0x140010a09  mov     edx, 50h ; 'P'
0x140010a0e  mov     rcx, rdi; Block
0x140010a11  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140010a16  mov     rbx, [rsp+28h+arg_0]
0x140010a1b  mov     rax, rdi
0x140010a1e  add     rsp, 20h
0x140010a22  pop     rdi
0x140010a23  retn
```
