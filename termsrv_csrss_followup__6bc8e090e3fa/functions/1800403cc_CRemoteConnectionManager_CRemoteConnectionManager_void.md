# CRemoteConnectionManager::~CRemoteConnectionManager(void)

- ea: `0x1800403cc`
- end: `0x180040666`
- name: `??1CRemoteConnectionManager@@UEAA@XZ`
- size: `666`
- prototype: `void __fastcall(CRemoteConnectionManager *__hidden this)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003fbbc`
- `0x18003fc54`
- `0x18003fcb8`
- `0x180040b30`

## callees

- `0x1800139c0`
- `0x18002558c`
- `0x18002cd54`
- `0x18003440c`
- `0x18003fe10`
- `0x18003feb4`
- `0x1800400d0`
- `0x180040248`
- `0x1800403cc`
- `0x180080b9c`
- `0x180096f18`
- `0x1800bde7c`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180040508`
- `ntdll!RtlDeleteResource` at `0x18004052b`
- `ntdll!RtlDeleteResource` at `0x18004054e`
- `ntdll!RtlDeleteResource` at `0x180040595`
- `ntdll!RtlDeleteResource` at `0x180040508`
- `ntdll!RtlDeleteResource` at `0x18004052b`
- `ntdll!RtlDeleteResource` at `0x18004054e`
- `ntdll!RtlDeleteResource` at `0x180040595`
- `UMPDC!PdcTaskClientUnregister` at `0x1800404b4`
- `UMPDC!PdcTaskClientUnregister` at `0x1800404b4`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180040495`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180040495`

## pseudocode

```c
void __fastcall CRemoteConnectionManager::~CRemoteConnectionManager(CRemoteConnectionManager *this)
{
  char *v2; // r12
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  CTerminalSupportManager *v7; // rcx
  void *v8; // rcx

  v2 = (char *)this + 528;
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
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 1240);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 1232);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 1224);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 1216);
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
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 696);
  SmartArray<ITSObjectStorage,long>::~SmartArray<ITSObjectStorage,long>((char *)this + 672);
  if ( *((_DWORD *)this + 166) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 568));
  *((_DWORD *)this + 166) = 0;
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 560);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 552);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 544);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 536);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(v2);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 520);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 512);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 504);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 496);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 488);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 480);
  CRemoteConnectionManager::CListenersList::~CListenersList((CRemoteConnectionManager *)((char *)this + 280));
  CWPPConfig::~CWPPConfig((CRemoteConnectionManager *)((char *)this + 264));
  CThreadPool::~CThreadPool((CRemoteConnectionManager *)((char *)this + 96));
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 80);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 72);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CRemoteConnectionManager *)((char *)this + 24));
}

```

## disassembly

```asm
0x1800403cc  push    rbx
0x1800403ce  push    rbp
0x1800403cf  push    rsi
0x1800403d0  push    rdi
0x1800403d1  push    r12
0x1800403d3  push    r14
0x1800403d5  push    r15
0x1800403d7  sub     rsp, 20h
0x1800403db  mov     rbx, rcx
0x1800403de  lea     r12, [rcx+210h]
0x1800403e5  mov     rcx, [r12]
0x1800403e9  test    rcx, rcx
0x1800403ec  jz      short loc_1800403FA
0x1800403ee  mov     rax, [rcx]
0x1800403f1  mov     rax, [rax+20h]
0x1800403f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403fa  lea     r15, [rbx+200h]
0x180040401  mov     rcx, [r15]
0x180040404  test    rcx, rcx
0x180040407  jz      short loc_180040415
0x180040409  mov     rax, [rcx]
0x18004040c  mov     rax, [rax+20h]
0x180040410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040415  lea     rbp, [rbx+208h]
0x18004041c  mov     rcx, [rbp+0]
0x180040420  test    rcx, rcx
0x180040423  jz      short loc_180040431
0x180040425  mov     rax, [rcx]
0x180040428  mov     rax, [rax+20h]
0x18004042c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040431  lea     r14, [rbx+218h]
0x180040438  mov     rcx, [r14]
0x18004043b  test    rcx, rcx
0x18004043e  jz      short loc_18004044C
0x180040440  mov     rax, [rcx]
0x180040443  mov     rax, [rax+20h]
0x180040447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004044c  lea     rsi, [rbx+4D8h]
0x180040453  mov     rcx, [rsi]; this
0x180040456  test    rcx, rcx
0x180040459  jz      short loc_18004046A
0x18004045b  call    ?Stop@CTerminalSupportManager@@QEAAJXZ; CTerminalSupportManager::Stop(void)
0x180040460  xor     edx, edx
0x180040462  mov     rcx, rsi
0x180040465  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18004046a  mov     rcx, [rbx+58h]; Block
0x18004046e  test    rcx, rcx
0x180040471  jz      short loc_180040485
0x180040473  mov     edx, 1678h
0x180040478  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004047d  mov     qword ptr [rbx+58h], 0
0x180040485  lea     rdi, [rbx+0A30h]
0x18004048c  cmp     qword ptr [rdi], 0
0x180040490  jz      short loc_1800404A8
0x180040492  mov     rcx, rdi
0x180040495  call    cs:__imp_Pdcv2ActivationClientUnregister
0x18004049c  nop     dword ptr [rax+rax+00h]
0x1800404a1  mov     qword ptr [rdi], 0
0x1800404a8  mov     rcx, [rbx+0A38h]
0x1800404af  test    rcx, rcx
0x1800404b2  jz      short loc_1800404C0
0x1800404b4  call    cs:__imp_PdcTaskClientUnregister
0x1800404bb  nop     dword ptr [rax+rax+00h]
0x1800404c0  lea     rcx, [rbx+0A00h]
0x1800404c7  call    ??1?$SmartPtr@VCPnPOnRemoteDisplayDeviceRemovalWorkItem@CRemoteConnectionManager@@@@QEAA@XZ; SmartPtr<CRemoteConnectionManager::CPnPOnRemoteDisplayDeviceRemovalWorkItem>::~SmartPtr<CRemoteConnectionManager::CPnPOnRemoteDisplayDeviceRemovalWorkItem>(void)
0x1800404cc  mov     rcx, rsi; void *
0x1800404cf  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800404d4  lea     rcx, [rbx+4D0h]; void *
0x1800404db  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800404e0  lea     rcx, [rbx+4C8h]; void *
0x1800404e7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800404ec  lea     rcx, [rbx+4C0h]; void *
0x1800404f3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800404f8  lea     rdi, [rbx+450h]
0x1800404ff  cmp     dword ptr [rdi+60h], 0
0x180040503  jz      short loc_180040514
0x180040505  mov     rcx, rdi; Resource
0x180040508  call    cs:__imp_RtlDeleteResource
0x18004050f  nop     dword ptr [rax+rax+00h]
0x180040514  mov     dword ptr [rdi+60h], 0
0x18004051b  lea     rdi, [rbx+3E8h]
0x180040522  cmp     dword ptr [rdi+60h], 0
0x180040526  jz      short loc_180040537
0x180040528  mov     rcx, rdi; Resource
0x18004052b  call    cs:__imp_RtlDeleteResource
0x180040532  nop     dword ptr [rax+rax+00h]
0x180040537  mov     dword ptr [rdi+60h], 0
0x18004053e  lea     rdi, [rbx+380h]
0x180040545  cmp     dword ptr [rdi+60h], 0
0x180040549  jz      short loc_18004055A
0x18004054b  mov     rcx, rdi; Resource
0x18004054e  call    cs:__imp_RtlDeleteResource
0x180040555  nop     dword ptr [rax+rax+00h]
0x18004055a  mov     dword ptr [rdi+60h], 0
0x180040561  lea     rcx, [rbx+2C0h]; this
0x180040568  call    ??1CUniqueIdMap@@QEAA@XZ; CUniqueIdMap::~CUniqueIdMap(void)
0x18004056d  lea     rcx, [rbx+2B8h]; void *
0x180040574  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180040579  lea     rcx, [rbx+2A0h]
0x180040580  call    ??1?$SmartArray@VITSObjectStorage@@J@@QEAA@XZ; SmartArray<ITSObjectStorage,long>::~SmartArray<ITSObjectStorage,long>(void)
0x180040585  lea     rdi, [rbx+238h]
0x18004058c  cmp     dword ptr [rdi+60h], 0
0x180040590  jz      short loc_1800405A1
0x180040592  mov     rcx, rdi; Resource
0x180040595  call    cs:__imp_RtlDeleteResource
0x18004059c  nop     dword ptr [rax+rax+00h]
0x1800405a1  mov     dword ptr [rdi+60h], 0
0x1800405a8  lea     rcx, [rbx+230h]; void *
0x1800405af  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800405b4  lea     rcx, [rbx+228h]; void *
0x1800405bb  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800405c0  lea     rcx, [rbx+220h]; void *
0x1800405c7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800405cc  mov     rcx, r14; void *
0x1800405cf  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800405d4  mov     rcx, r12; void *
0x1800405d7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800405dc  mov     rcx, rbp; void *
0x1800405df  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800405e4  mov     rcx, r15; void *
0x1800405e7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800405ec  lea     rcx, [rbx+1F8h]; void *
0x1800405f3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800405f8  lea     rcx, [rbx+1F0h]; void *
0x1800405ff  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180040604  lea     rcx, [rbx+1E8h]; void *
0x18004060b  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180040610  lea     rcx, [rbx+1E0h]; void *
0x180040617  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18004061c  lea     rcx, [rbx+118h]; this
0x180040623  call    ??1CListenersList@CRemoteConnectionManager@@QEAA@XZ; CRemoteConnectionManager::CListenersList::~CListenersList(void)
0x180040628  lea     rcx, [rbx+108h]; this
0x18004062f  call    ??1CWPPConfig@@QEAA@XZ; CWPPConfig::~CWPPConfig(void)
0x180040634  lea     rcx, [rbx+60h]; this
0x180040638  call    ??1CThreadPool@@UEAA@XZ; CThreadPool::~CThreadPool(void)
0x18004063d  lea     rcx, [rbx+50h]; void *
0x180040641  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180040646  lea     rcx, [rbx+48h]; void *
0x18004064a  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18004064f  lea     rcx, [rbx+18h]; this
0x180040653  add     rsp, 20h
0x180040657  pop     r15
0x180040659  pop     r14
0x18004065b  pop     r12
0x18004065d  pop     rdi
0x18004065e  pop     rsi
0x18004065f  pop     rbp
0x180040660  pop     rbx
0x180040661  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
