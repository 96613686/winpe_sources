# CRemoteConnectionManager::~CRemoteConnectionManager(void)

- ea: `0x18003e1cc`
- end: `0x18003e442`
- name: `??1CRemoteConnectionManager@@UEAA@XZ`
- size: `630`
- prototype: `void __fastcall(CRemoteConnectionManager *__hidden this)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d994`
- `0x18003da2c`
- `0x18003da90`
- `0x18003e8e0`

## callees

- `0x180013150`
- `0x1800241f0`
- `0x18002b5b4`
- `0x18003269c`
- `0x18003dbe8`
- `0x18003dce8`
- `0x18003def4`
- `0x18003e058`
- `0x18003e1cc`
- `0x18007d4bc`
- `0x180093078`
- `0x1800b767c`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18003e2fc`
- `ntdll!RtlDeleteResource` at `0x18003e319`
- `ntdll!RtlDeleteResource` at `0x18003e336`
- `ntdll!RtlDeleteResource` at `0x18003e377`
- `ntdll!RtlDeleteResource` at `0x18003e2fc`
- `ntdll!RtlDeleteResource` at `0x18003e319`
- `ntdll!RtlDeleteResource` at `0x18003e336`
- `ntdll!RtlDeleteResource` at `0x18003e377`
- `UMPDC!PdcTaskClientUnregister` at `0x18003e2ae`
- `UMPDC!PdcTaskClientUnregister` at `0x18003e2ae`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18003e295`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18003e295`

## pseudocode

```c
void __fastcall CRemoteConnectionManager::~CRemoteConnectionManager(CRemoteConnectionManager *this)
{
  __int64 *v2; // r12
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  CTerminalSupportManager *v7; // rcx
  void *v8; // rcx

  v2 = (__int64 *)((char *)this + 528);
  v3 = *((_QWORD *)this + 66);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
  v4 = *((_QWORD *)this + 64);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
  v5 = *((_QWORD *)this + 65);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
  v6 = *((_QWORD *)this + 67);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
  v7 = (CTerminalSupportManager *)*((_QWORD *)this + 155);
  if ( v7 )
  {
    CTerminalSupportManager::Stop(v7);
    SmartPtr<ITerminal>::operator=((char *)this + 1240, 0);
  }
  v8 = (void *)*((_QWORD *)this + 11);
  if ( v8 )
  {
    operator delete(v8);
    *((_QWORD *)this + 11) = 0;
  }
  if ( *((_QWORD *)this + 326) )
  {
    Pdcv2ActivationClientUnregister((char *)this + 2608);
    *((_QWORD *)this + 326) = 0;
  }
  if ( *((_QWORD *)this + 327) )
    PdcTaskClientUnregister();
  SmartPtr<CRemoteConnectionManager::CPnPOnRemoteDisplayDeviceRemovalWorkItem>::~SmartPtr<CRemoteConnectionManager::CPnPOnRemoteDisplayDeviceRemovalWorkItem>((char *)this + 2560);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 155);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 154);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 153);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 152);
  if ( *((_DWORD *)this + 300) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1104));
  *((_DWORD *)this + 300) = 0;
  if ( *((_DWORD *)this + 274) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1000));
  *((_DWORD *)this + 274) = 0;
  if ( *((_DWORD *)this + 248) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 896));
  *((_DWORD *)this + 248) = 0;
  CUniqueIdMap::~CUniqueIdMap((CRemoteConnectionManager *)((char *)this + 704));
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 87);
  SmartArray<ITSObjectStorage,long>::~SmartArray<ITSObjectStorage,long>((char *)this + 672);
  if ( *((_DWORD *)this + 166) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 568));
  *((_DWORD *)this + 166) = 0;
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 70);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 69);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 68);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 67);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(v2);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 65);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 64);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 63);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 62);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 61);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 60);
  CRemoteConnectionManager::CListenersList::~CListenersList((CRemoteConnectionManager *)((char *)this + 280));
  CWPPConfig::~CWPPConfig((CRemoteConnectionManager *)((char *)this + 264));
  CThreadPool::~CThreadPool((CRemoteConnectionManager *)((char *)this + 96));
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 10);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)this + 9);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CRemoteConnectionManager *)((char *)this + 24));
}

```

## disassembly

```asm
0x18003e1cc  push    rbx
0x18003e1ce  push    rbp
0x18003e1cf  push    rsi
0x18003e1d0  push    rdi
0x18003e1d1  push    r12
0x18003e1d3  push    r14
0x18003e1d5  push    r15
0x18003e1d7  sub     rsp, 20h
0x18003e1db  mov     rbx, rcx
0x18003e1de  lea     r12, [rcx+210h]
0x18003e1e5  mov     rcx, [r12]
0x18003e1e9  test    rcx, rcx
0x18003e1ec  jz      short loc_18003E1FA
0x18003e1ee  mov     rax, [rcx]
0x18003e1f1  mov     rax, [rax+20h]
0x18003e1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1fa  lea     r15, [rbx+200h]
0x18003e201  mov     rcx, [r15]
0x18003e204  test    rcx, rcx
0x18003e207  jz      short loc_18003E215
0x18003e209  mov     rax, [rcx]
0x18003e20c  mov     rax, [rax+20h]
0x18003e210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e215  lea     rbp, [rbx+208h]
0x18003e21c  mov     rcx, [rbp+0]
0x18003e220  test    rcx, rcx
0x18003e223  jz      short loc_18003E231
0x18003e225  mov     rax, [rcx]
0x18003e228  mov     rax, [rax+20h]
0x18003e22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e231  lea     r14, [rbx+218h]
0x18003e238  mov     rcx, [r14]
0x18003e23b  test    rcx, rcx
0x18003e23e  jz      short loc_18003E24C
0x18003e240  mov     rax, [rcx]
0x18003e243  mov     rax, [rax+20h]
0x18003e247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e24c  lea     rsi, [rbx+4D8h]
0x18003e253  mov     rcx, [rsi]; this
0x18003e256  test    rcx, rcx
0x18003e259  jz      short loc_18003E26A
0x18003e25b  call    ?Stop@CTerminalSupportManager@@QEAAJXZ; CTerminalSupportManager::Stop(void)
0x18003e260  xor     edx, edx
0x18003e262  mov     rcx, rsi
0x18003e265  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18003e26a  mov     rcx, [rbx+58h]; Block
0x18003e26e  test    rcx, rcx
0x18003e271  jz      short loc_18003E285
0x18003e273  mov     edx, 1678h
0x18003e278  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003e27d  mov     qword ptr [rbx+58h], 0
0x18003e285  lea     rdi, [rbx+0A30h]
0x18003e28c  cmp     qword ptr [rdi], 0
0x18003e290  jz      short loc_18003E2A2
0x18003e292  mov     rcx, rdi
0x18003e295  call    cs:__imp_Pdcv2ActivationClientUnregister
0x18003e29b  mov     qword ptr [rdi], 0
0x18003e2a2  mov     rcx, [rbx+0A38h]
0x18003e2a9  test    rcx, rcx
0x18003e2ac  jz      short loc_18003E2B4
0x18003e2ae  call    cs:__imp_PdcTaskClientUnregister
0x18003e2b4  lea     rcx, [rbx+0A00h]
0x18003e2bb  call    ??1?$SmartPtr@VCPnPOnRemoteDisplayDeviceRemovalWorkItem@CRemoteConnectionManager@@@@QEAA@XZ; SmartPtr<CRemoteConnectionManager::CPnPOnRemoteDisplayDeviceRemovalWorkItem>::~SmartPtr<CRemoteConnectionManager::CPnPOnRemoteDisplayDeviceRemovalWorkItem>(void)
0x18003e2c0  mov     rcx, rsi; void *
0x18003e2c3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e2c8  lea     rcx, [rbx+4D0h]; void *
0x18003e2cf  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e2d4  lea     rcx, [rbx+4C8h]; void *
0x18003e2db  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e2e0  lea     rcx, [rbx+4C0h]; void *
0x18003e2e7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e2ec  lea     rdi, [rbx+450h]
0x18003e2f3  cmp     dword ptr [rdi+60h], 0
0x18003e2f7  jz      short loc_18003E302
0x18003e2f9  mov     rcx, rdi; Resource
0x18003e2fc  call    cs:__imp_RtlDeleteResource
0x18003e302  mov     dword ptr [rdi+60h], 0
0x18003e309  lea     rdi, [rbx+3E8h]
0x18003e310  cmp     dword ptr [rdi+60h], 0
0x18003e314  jz      short loc_18003E31F
0x18003e316  mov     rcx, rdi; Resource
0x18003e319  call    cs:__imp_RtlDeleteResource
0x18003e31f  mov     dword ptr [rdi+60h], 0
0x18003e326  lea     rdi, [rbx+380h]
0x18003e32d  cmp     dword ptr [rdi+60h], 0
0x18003e331  jz      short loc_18003E33C
0x18003e333  mov     rcx, rdi; Resource
0x18003e336  call    cs:__imp_RtlDeleteResource
0x18003e33c  mov     dword ptr [rdi+60h], 0
0x18003e343  lea     rcx, [rbx+2C0h]; this
0x18003e34a  call    ??1CUniqueIdMap@@QEAA@XZ; CUniqueIdMap::~CUniqueIdMap(void)
0x18003e34f  lea     rcx, [rbx+2B8h]; void *
0x18003e356  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e35b  lea     rcx, [rbx+2A0h]
0x18003e362  call    ??1?$SmartArray@VITSObjectStorage@@J@@QEAA@XZ; SmartArray<ITSObjectStorage,long>::~SmartArray<ITSObjectStorage,long>(void)
0x18003e367  lea     rdi, [rbx+238h]
0x18003e36e  cmp     dword ptr [rdi+60h], 0
0x18003e372  jz      short loc_18003E37D
0x18003e374  mov     rcx, rdi; Resource
0x18003e377  call    cs:__imp_RtlDeleteResource
0x18003e37d  mov     dword ptr [rdi+60h], 0
0x18003e384  lea     rcx, [rbx+230h]; void *
0x18003e38b  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e390  lea     rcx, [rbx+228h]; void *
0x18003e397  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e39c  lea     rcx, [rbx+220h]; void *
0x18003e3a3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e3a8  mov     rcx, r14; void *
0x18003e3ab  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e3b0  mov     rcx, r12; void *
0x18003e3b3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e3b8  mov     rcx, rbp; void *
0x18003e3bb  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e3c0  mov     rcx, r15; void *
0x18003e3c3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e3c8  lea     rcx, [rbx+1F8h]; void *
0x18003e3cf  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e3d4  lea     rcx, [rbx+1F0h]; void *
0x18003e3db  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e3e0  lea     rcx, [rbx+1E8h]; void *
0x18003e3e7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e3ec  lea     rcx, [rbx+1E0h]; void *
0x18003e3f3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e3f8  lea     rcx, [rbx+118h]; this
0x18003e3ff  call    ??1CListenersList@CRemoteConnectionManager@@QEAA@XZ; CRemoteConnectionManager::CListenersList::~CListenersList(void)
0x18003e404  lea     rcx, [rbx+108h]; this
0x18003e40b  call    ??1CWPPConfig@@QEAA@XZ; CWPPConfig::~CWPPConfig(void)
0x18003e410  lea     rcx, [rbx+60h]; this
0x18003e414  call    ??1CThreadPool@@UEAA@XZ; CThreadPool::~CThreadPool(void)
0x18003e419  lea     rcx, [rbx+50h]; void *
0x18003e41d  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e422  lea     rcx, [rbx+48h]; void *
0x18003e426  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003e42b  lea     rcx, [rbx+18h]; this
0x18003e42f  add     rsp, 20h
0x18003e433  pop     r15
0x18003e435  pop     r14
0x18003e437  pop     r12
0x18003e439  pop     rdi
0x18003e43a  pop     rsi
0x18003e43b  pop     rbp
0x18003e43c  pop     rbx
0x18003e43d  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
