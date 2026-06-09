# CompatibilityAdapter::Cleanup(int)

- ea: `0x180006498`
- end: `0x1800066b1`
- name: `?Cleanup@CompatibilityAdapter@@SAJH@Z`
- size: `537`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800063b0`
- `0x180012360`

## callees

- `0x180005e54`
- `0x180006498`
- `0x180007988`
- `0x180010da0`
- `0x180010f30`
- `0x180017d84`
- `0x180018fec`
- `0x180019698`
- `0x18001c300`
- `0x18002e274`
- `0x180030564`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006538`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000662c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006538`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000662c`
- `ntdll!RtlDeleteSecurityObject` at `0x1800065c0`
- `ntdll!RtlDeleteSecurityObject` at `0x1800065c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000660e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000660e`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800064b4`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800064c4`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800064b4`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800064c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006548`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006548`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006560`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180006560`

## pseudocode

```c
__int64 __fastcall CompatibilityAdapter::Cleanup(int a1)
{
  JournalReader *v2; // rbx
  JournalReader *v3; // rbx
  CompatibilityAdapter *v4; // rbx
  unsigned __int8 v5; // dl
  EventManager *v6; // rbx

  StopRpcServer();
  v2 = JournalReader::s_pReader;
  CancelIo(*((HANDLE *)JournalReader::s_pReader + 11));
  CancelIo(*((HANDLE *)v2 + 6));
  v3 = JournalReader::s_pReader;
  if ( JournalReader::s_pReader )
  {
    JournalReader::~JournalReader(JournalReader::s_pReader);
    operator delete(v3);
  }
  JournalReader::s_pReader = 0;
  EnterCriticalSection(&CompatibilityAdapter::s_csAdapterAccess);
  v4 = CompatibilityAdapter::g_pAdapter;
  if ( CompatibilityAdapter::g_pAdapter )
  {
    CompatibilityAdapter::~CompatibilityAdapter(CompatibilityAdapter::g_pAdapter);
    operator delete(v4);
    CompatibilityAdapter::g_pAdapter = 0;
  }
  LeaveCriticalSection(&CompatibilityAdapter::s_csAdapterAccess);
  if ( a1 )
    CoUninitialize();
  if ( gpDomainInfo )
  {
    LsaFreeMemory(gpDomainInfo);
    gpDomainInfo = 0;
  }
  if ( gpwszComputerName )
  {
    operator delete(gpwszComputerName);
    gpwszComputerName = 0;
  }
  if ( gpwszAtJobPathTemplate )
  {
    operator delete(gpwszAtJobPathTemplate);
    gpwszAtJobPathTemplate = 0;
  }
  if ( AtGlobalSecurityDescriptor )
  {
    RtlDeleteSecurityObject(&AtGlobalSecurityDescriptor);
    NetpFreeWellKnownSids();
  }
  CredStore::Uninit();
  User::UninitializeUserTable();
  LogServiceEvent(0x472u);
  if ( ghLog )
  {
    EnterCriticalSection(&gcsLogCritSection);
    if ( ghLog )
    {
      CloseHandle(ghLog);
      ghLog = 0;
    }
    LeaveCriticalSection(&gcsLogCritSection);
  }
  v6 = g_pEventManager;
  if ( g_pEventManager )
  {
    EventManager::~EventManager(g_pEventManager);
    operator delete(v6);
  }
  g_pEventManager = 0;
  if ( g_TasksFolderInfo )
  {
    UpdateSADatServiceFlags(g_TasksFolderInfo, v5, 1);
    if ( g_TasksFolderInfo )
    {
      operator delete((void *)g_TasksFolderInfo);
      g_TasksFolderInfo = 0;
    }
  }
  if ( g_ptszSearchPath )
    operator delete((void *)g_ptszSearchPath);
  return 0;
}

```

## disassembly

```asm
0x180006498  mov     [rsp+arg_0], rbx
0x18000649d  push    rdi
0x18000649e  sub     rsp, 20h
0x1800064a2  mov     edi, ecx
0x1800064a4  call    ?StopRpcServer@@YAXXZ; StopRpcServer(void)
0x1800064a9  mov     rbx, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x1800064b0  mov     rcx, [rbx+58h]; hFile
0x1800064b4  call    cs:__imp_CancelIo
0x1800064bb  nop     dword ptr [rax+rax+00h]
0x1800064c0  mov     rcx, [rbx+30h]; hFile
0x1800064c4  call    cs:__imp_CancelIo
0x1800064cb  nop     dword ptr [rax+rax+00h]
0x1800064d0  mov     rbx, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x1800064d7  test    rbx, rbx
0x1800064da  jz      short loc_1800064EC
0x1800064dc  mov     rcx, rbx; this
0x1800064df  call    ??1JournalReader@@QEAA@XZ; JournalReader::~JournalReader(void)
0x1800064e4  mov     rcx, rbx; Block
0x1800064e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800064ec  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800064f3  mov     cs:?s_pReader@JournalReader@@0PEAV1@EA, 0; JournalReader * JournalReader::s_pReader
0x1800064fe  call    cs:__imp_EnterCriticalSection
0x180006505  nop     dword ptr [rax+rax+00h]
0x18000650a  mov     rbx, cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x180006511  test    rbx, rbx
0x180006514  jz      short loc_180006531
0x180006516  mov     rcx, rbx; this
0x180006519  call    ??1CompatibilityAdapter@@QEAA@XZ; CompatibilityAdapter::~CompatibilityAdapter(void)
0x18000651e  mov     rcx, rbx; Block
0x180006521  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006526  mov     cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA, 0; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x180006531  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006538  call    cs:__imp_LeaveCriticalSection
0x18000653f  nop     dword ptr [rax+rax+00h]
0x180006544  test    edi, edi
0x180006546  jz      short loc_180006554
0x180006548  call    cs:__imp_CoUninitialize
0x18000654f  nop     dword ptr [rax+rax+00h]
0x180006554  mov     rcx, cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; Buffer
0x18000655b  test    rcx, rcx
0x18000655e  jz      short loc_180006577
0x180006560  call    cs:__imp_LsaFreeMemory
0x180006567  nop     dword ptr [rax+rax+00h]
0x18000656c  mov     cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA, 0; _POLICY_ACCOUNT_DOMAIN_INFO * gpDomainInfo
0x180006577  mov     rcx, cs:?gpwszComputerName@@3PEAGEA; Block
0x18000657e  test    rcx, rcx
0x180006581  jz      short loc_180006593
0x180006583  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006588  mov     cs:?gpwszComputerName@@3PEAGEA, 0; ushort * gpwszComputerName
0x180006593  mov     rcx, cs:?gpwszAtJobPathTemplate@@3PEAGEA; Block
0x18000659a  test    rcx, rcx
0x18000659d  jz      short loc_1800065AF
0x18000659f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800065a4  mov     cs:?gpwszAtJobPathTemplate@@3PEAGEA, 0; ushort * gpwszAtJobPathTemplate
0x1800065af  cmp     cs:?AtGlobalSecurityDescriptor@@3PEAXEA, 0; void * AtGlobalSecurityDescriptor
0x1800065b7  jz      short loc_1800065D1
0x1800065b9  lea     rcx, ?AtGlobalSecurityDescriptor@@3PEAXEA; ObjectDescriptor
0x1800065c0  call    cs:__imp_RtlDeleteSecurityObject
0x1800065c7  nop     dword ptr [rax+rax+00h]
0x1800065cc  call    NetpFreeWellKnownSids
0x1800065d1  call    ?Uninit@CredStore@@SAJXZ; CredStore::Uninit(void)
0x1800065d6  call    ?UninitializeUserTable@User@@SAXXZ; User::UninitializeUserTable(void)
0x1800065db  mov     ecx, 472h; uID
0x1800065e0  call    ?LogServiceEvent@@YAXI@Z; LogServiceEvent(uint)
0x1800065e5  cmp     cs:?ghLog@@3PEAXEA, 0; void * ghLog
0x1800065ed  jz      short loc_180006638
0x1800065ef  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x1800065f6  call    cs:__imp_EnterCriticalSection
0x1800065fd  nop     dword ptr [rax+rax+00h]
0x180006602  mov     rcx, cs:?ghLog@@3PEAXEA; hObject
0x180006609  test    rcx, rcx
0x18000660c  jz      short loc_180006625
0x18000660e  call    cs:__imp_CloseHandle
0x180006615  nop     dword ptr [rax+rax+00h]
0x18000661a  mov     cs:?ghLog@@3PEAXEA, 0; void * ghLog
0x180006625  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18000662c  call    cs:__imp_LeaveCriticalSection
0x180006633  nop     dword ptr [rax+rax+00h]
0x180006638  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x18000663f  test    rbx, rbx
0x180006642  jz      short loc_180006654
0x180006644  mov     rcx, rbx; this
0x180006647  call    ??1EventManager@@QEAA@XZ; EventManager::~EventManager(void)
0x18000664c  mov     rcx, rbx; Block
0x18000664f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006654  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x18000665b  mov     cs:?g_pEventManager@@3PEAVEventManager@@EA, 0; EventManager * g_pEventManager
0x180006666  test    rcx, rcx
0x180006669  jz      short loc_180006692
0x18000666b  mov     r8d, 1; int
0x180006671  call    ?UpdateSADatServiceFlags@@YAJPEBGEH@Z; UpdateSADatServiceFlags(ushort const *,uchar,int)
0x180006676  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; Block
0x18000667d  test    rcx, rcx
0x180006680  jz      short loc_180006692
0x180006682  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006687  mov     cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A, 0; _TasksFolderInfo g_TasksFolderInfo
0x180006692  mov     rcx, cs:?g_ptszSearchPath@@3PEAGEA; Block
0x180006699  test    rcx, rcx
0x18000669c  jz      short loc_1800066A3
0x18000669e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800066a3  mov     rbx, [rsp+28h+arg_0]
0x1800066a8  xor     eax, eax
0x1800066aa  add     rsp, 20h
0x1800066ae  pop     rdi
0x1800066af  retn
```
