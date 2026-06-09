# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::~THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>(void)

- ea: `0x1400105e4`
- end: `0x14001060d`
- name: `??1?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@UEAA@XZ`
- size: `41`
- prototype: `__int64 __fastcall(NAdvancedLibrary::THashTableBase *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400108dc`
- `0x1400109f0`
- `0x140010c60`

## callees

- `0x140013ff8`
- `0x140014110`

## pseudocode

```c
void __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::~THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>(
        LPCRITICAL_SECTION *this)
{
  *this = (LPCRITICAL_SECTION)&NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::`vftable';
  NAdvancedLibrary::TCopyCritsec::~TCopyCritsec(this + 8);
  NAdvancedLibrary::THashTableBase::~THashTableBase((NAdvancedLibrary::THashTableBase *)this);
}

```

## disassembly

```asm
0x1400105e4  push    rbx
0x1400105e6  sub     rsp, 20h
0x1400105ea  lea     rax, ??_7?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@6B@; const NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::`vftable'
0x1400105f1  mov     rbx, rcx
0x1400105f4  mov     [rcx], rax
0x1400105f7  add     rcx, 40h ; '@'; this
0x1400105fb  call    ??1TCopyCritsec@NAdvancedLibrary@@QEAA@XZ; NAdvancedLibrary::TCopyCritsec::~TCopyCritsec(void)
0x140010600  mov     rcx, rbx; this
0x140010603  add     rsp, 20h
0x140010607  pop     rbx
0x140010608  jmp     ??1THashTableBase@NAdvancedLibrary@@UEAA@XZ; NAdvancedLibrary::THashTableBase::~THashTableBase(void)
```
