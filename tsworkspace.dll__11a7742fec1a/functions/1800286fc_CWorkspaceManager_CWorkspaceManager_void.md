# CWorkspaceManager::~CWorkspaceManager(void)

- ea: `0x1800286fc`
- end: `0x180028809`
- name: `??1CWorkspaceManager@@MEAA@XZ`
- size: `269`
- prototype: `void __fastcall(CWorkspaceManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028f80`

## callees

- `0x180005500`
- `0x1800055d0`
- `0x18000c3a0`
- `0x18000fed8`
- `0x1800119a4`
- `0x18001e7e4`
- `0x180028034`
- `0x1800286fc`
- `0x180034f90`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028789`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028789`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028792`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028792`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028727`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028727`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CWorkspaceManager::~CWorkspaceManager(CWorkspaceManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx

  *(_QWORD *)this = &CWorkspaceManager::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( *((_QWORD *)this + 1) )
  {
    TCntPtr<CConfigManager>::SafeRelease((char *)this + 8);
    *((_QWORD *)this + 1) = 0;
    TCntPtr<CConfigManager>::SafeAddRef((char *)this + 8);
  }
  *((_QWORD *)this + 2) = 0;
  if ( RdpWinDiagnosticsHttpManager::s_pInstance )
  {
    (*(void (__fastcall **)(RdpWinDiagnosticsHttpManager *, __int64))(*(_QWORD *)RdpWinDiagnosticsHttpManager::s_pInstance
                                                                    + 88LL))(
      RdpWinDiagnosticsHttpManager::s_pInstance,
      1);
    RdpWinDiagnosticsHttpManager::s_pInstance = 0;
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 8) + 24LL))((char *)this + 64);
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  CTSCriticalSection::Terminate((CWorkspaceManager *)((char *)this + 128));
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>((char *)this + 216);
  std::wstring::~wstring((char *)this + 184);
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>((char *)this + 152);
  RdpXSPtr<RdpXPlatKeyValuePair<unsigned __int64,RdpWinDiagnosticsHttpManager::HostMessage *>>::SafeRelease((char *)this + 144);
  CTSCriticalSection::Terminate((CWorkspaceManager *)((char *)this + 128));
  RdpXSPtrArray<RdXClientRadcTask,16,4294967294>::~RdpXSPtrArray<RdXClientRadcTask,16,4294967294>((char *)this + 96);
  CTSSimpleComPtrArray<CWorkspace>::~CTSSimpleComPtrArray<CWorkspace>((char *)this + 64);
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>((char *)this + 8);
}

```

## disassembly

```asm
0x1800286fc  mov     [rsp+arg_0], rcx
0x180028701  push    rbx
0x180028702  push    rsi
0x180028703  push    rdi
0x180028704  push    r14
0x180028706  sub     rsp, 38h
0x18002870a  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180028713  mov     rsi, rcx
0x180028716  lea     rax, ??_7CWorkspaceManager@@6B@; const CWorkspaceManager::`vftable'
0x18002871d  mov     [rcx], rax
0x180028720  lea     rbx, [rcx+18h]
0x180028724  mov     rcx, rbx; lpCriticalSection
0x180028727  call    cs:__imp_EnterCriticalSection
0x18002872d  lea     r14, [rsi+8]
0x180028731  xor     edi, edi
0x180028733  cmp     [r14], rdi
0x180028736  jz      short loc_18002874B
0x180028738  mov     rcx, r14
0x18002873b  call    ?SafeRelease@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeRelease(void)
0x180028740  mov     [r14], rdi
0x180028743  mov     rcx, r14
0x180028746  call    ?SafeAddRef@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeAddRef(void)
0x18002874b  mov     [rsi+10h], rdi
0x18002874f  mov     rcx, cs:?s_pInstance@RdpWinDiagnosticsHttpManager@@1PEAV1@EA; RdpWinDiagnosticsHttpManager * RdpWinDiagnosticsHttpManager::s_pInstance
0x180028756  test    rcx, rcx
0x180028759  jz      short loc_180028773
0x18002875b  mov     rax, [rcx]
0x18002875e  mov     edx, 1
0x180028763  mov     rax, [rax+58h]
0x180028767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002876c  mov     cs:?s_pInstance@RdpWinDiagnosticsHttpManager@@1PEAV1@EA, rdi; RdpWinDiagnosticsHttpManager * RdpWinDiagnosticsHttpManager::s_pInstance
0x180028773  lea     rdi, [rsi+40h]
0x180028777  mov     rax, [rdi]
0x18002877a  mov     rcx, rdi
0x18002877d  mov     rax, [rax+18h]
0x180028781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028786  mov     rcx, rbx; lpCriticalSection
0x180028789  call    cs:__imp_LeaveCriticalSection
0x18002878f  mov     rcx, rbx; lpCriticalSection
0x180028792  call    cs:__imp_DeleteCriticalSection
0x180028798  lea     rbx, [rsi+80h]
0x18002879f  mov     rcx, rbx; this
0x1800287a2  call    ?Terminate@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Terminate(void)
0x1800287a7  nop
0x1800287a8  lea     rcx, [rsi+0D8h]
0x1800287af  call    ??1?$ComPlainSmartPtr@VCRadcXmlIcon@@@@QEAA@XZ; ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(void)
0x1800287b4  nop
0x1800287b5  lea     rcx, [rsi+0B8h]; void *
0x1800287bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800287c1  nop
0x1800287c2  lea     rcx, [rsi+98h]
0x1800287c9  call    ??1?$ComPlainSmartPtr@VCRadcXmlIcon@@@@QEAA@XZ; ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(void)
0x1800287ce  nop
0x1800287cf  lea     rcx, [rsi+90h]
0x1800287d6  call    ?SafeRelease@?$RdpXSPtr@V?$RdpXPlatKeyValuePair@_KPEAUHostMessage@RdpWinDiagnosticsHttpManager@@@@@@AEAAXXZ; RdpXSPtr<RdpXPlatKeyValuePair<unsigned __int64,RdpWinDiagnosticsHttpManager::HostMessage *>>::SafeRelease(void)
0x1800287db  nop
0x1800287dc  mov     rcx, rbx; this
0x1800287df  call    ?Terminate@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Terminate(void)
0x1800287e4  nop
0x1800287e5  lea     rcx, [rsi+60h]
0x1800287e9  call    ??1?$RdpXSPtrArray@VRdXClientRadcTask@@$0BA@$0PPPPPPPO@@@UEAA@XZ; RdpXSPtrArray<RdXClientRadcTask,16,4294967294>::~RdpXSPtrArray<RdXClientRadcTask,16,4294967294>(void)
0x1800287ee  nop
0x1800287ef  mov     rcx, rdi
0x1800287f2  call    ??1?$CTSSimpleComPtrArray@VCWorkspace@@@@UEAA@XZ; CTSSimpleComPtrArray<CWorkspace>::~CTSSimpleComPtrArray<CWorkspace>(void)
0x1800287f7  nop
0x1800287f8  mov     rcx, r14
0x1800287fb  add     rsp, 38h
0x1800287ff  pop     r14
0x180028801  pop     rdi
0x180028802  pop     rsi
0x180028803  pop     rbx
0x180028804  jmp     ??1?$ComPlainSmartPtr@VCRadcXmlIcon@@@@QEAA@XZ; ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(void)
```
