# CompatibilityAdapter::Cleanup(int)

- ea: `0x1800060e0`
- end: `0x1800062bc`
- name: `?Cleanup@CompatibilityAdapter@@SAJH@Z`
- size: `476`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180006010`
- `0x180011880`

## callees

- `0x180005b10`
- `0x1800060e0`
- `0x1800074c8`
- `0x1800103b4`
- `0x180010530`
- `0x180016dd8`
- `0x180017f08`
- `0x18001851c`
- `0x18001ae60`
- `0x18002c49c`
- `0x18002e424`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000613a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006214`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000613a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006214`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000616e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000623e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000616e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000623e`
- `ntdll!RtlDeleteSecurityObject` at `0x1800061e4`
- `ntdll!RtlDeleteSecurityObject` at `0x1800061e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006226`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800060fc`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180006106`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800060fc`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180006106`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006178`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006178`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000618a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000618a`

## pseudocode

```c
__int64 __fastcall CompatibilityAdapter::Cleanup(int a1)
{
  JournalReader *v2; // rbx
  JournalReader *v3; // rbx
  unsigned int v4; // edx
  CompatibilityAdapter *v5; // rbx
  __int64 v6; // rdx
  EventManager *v7; // rbx

  StopRpcServer();
  v2 = JournalReader::s_pReader;
  CancelIo(*((HANDLE *)JournalReader::s_pReader + 11));
  CancelIo(*((HANDLE *)v2 + 6));
  v3 = JournalReader::s_pReader;
  if ( JournalReader::s_pReader )
  {
    JournalReader::~JournalReader((void **)JournalReader::s_pReader);
    operator delete(v3);
  }
  JournalReader::s_pReader = 0;
  EnterCriticalSection(&CompatibilityAdapter::s_csAdapterAccess);
  v5 = CompatibilityAdapter::g_pAdapter;
  if ( CompatibilityAdapter::g_pAdapter )
  {
    CompatibilityAdapter::~CompatibilityAdapter(CompatibilityAdapter::g_pAdapter, v4);
    operator delete(v5);
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
  v7 = g_pEventManager;
  if ( g_pEventManager )
  {
    EventManager::~EventManager(g_pEventManager);
    operator delete(v7);
  }
  g_pEventManager = 0;
  if ( g_TasksFolderInfo )
  {
    UpdateSADatServiceFlags(g_TasksFolderInfo, v6, 1);
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
0x1800060e0  mov     [rsp+arg_0], rbx
0x1800060e5  push    rdi
0x1800060e6  sub     rsp, 20h
0x1800060ea  mov     edi, ecx
0x1800060ec  call    ?StopRpcServer@@YAXXZ; StopRpcServer(void)
0x1800060f1  mov     rbx, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x1800060f8  mov     rcx, [rbx+58h]; hFile
0x1800060fc  call    cs:__imp_CancelIo
0x180006102  mov     rcx, [rbx+30h]; hFile
0x180006106  call    cs:__imp_CancelIo
0x18000610c  mov     rbx, cs:?s_pReader@JournalReader@@0PEAV1@EA; JournalReader * JournalReader::s_pReader
0x180006113  test    rbx, rbx
0x180006116  jz      short loc_180006128
0x180006118  mov     rcx, rbx; this
0x18000611b  call    ??1JournalReader@@QEAA@XZ; JournalReader::~JournalReader(void)
0x180006120  mov     rcx, rbx; Block
0x180006123  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006128  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000612f  mov     cs:?s_pReader@JournalReader@@0PEAV1@EA, 0; JournalReader * JournalReader::s_pReader
0x18000613a  call    cs:__imp_EnterCriticalSection
0x180006140  mov     rbx, cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x180006147  test    rbx, rbx
0x18000614a  jz      short loc_180006167
0x18000614c  mov     rcx, rbx; this
0x18000614f  call    ??1CompatibilityAdapter@@QEAA@XZ; CompatibilityAdapter::~CompatibilityAdapter(void)
0x180006154  mov     rcx, rbx; Block
0x180006157  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000615c  mov     cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA, 0; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x180006167  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000616e  call    cs:__imp_LeaveCriticalSection
0x180006174  test    edi, edi
0x180006176  jz      short loc_18000617E
0x180006178  call    cs:__imp_CoUninitialize
0x18000617e  mov     rcx, cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; Buffer
0x180006185  test    rcx, rcx
0x180006188  jz      short loc_18000619B
0x18000618a  call    cs:__imp_LsaFreeMemory
0x180006190  mov     cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA, 0; _POLICY_ACCOUNT_DOMAIN_INFO * gpDomainInfo
0x18000619b  mov     rcx, cs:?gpwszComputerName@@3PEAGEA; Block
0x1800061a2  test    rcx, rcx
0x1800061a5  jz      short loc_1800061B7
0x1800061a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800061ac  mov     cs:?gpwszComputerName@@3PEAGEA, 0; ushort * gpwszComputerName
0x1800061b7  mov     rcx, cs:?gpwszAtJobPathTemplate@@3PEAGEA; Block
0x1800061be  test    rcx, rcx
0x1800061c1  jz      short loc_1800061D3
0x1800061c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800061c8  mov     cs:?gpwszAtJobPathTemplate@@3PEAGEA, 0; ushort * gpwszAtJobPathTemplate
0x1800061d3  cmp     cs:?AtGlobalSecurityDescriptor@@3PEAXEA, 0; void * AtGlobalSecurityDescriptor
0x1800061db  jz      short loc_1800061EF
0x1800061dd  lea     rcx, ?AtGlobalSecurityDescriptor@@3PEAXEA; ObjectDescriptor
0x1800061e4  call    cs:__imp_RtlDeleteSecurityObject
0x1800061ea  call    NetpFreeWellKnownSids
0x1800061ef  call    ?Uninit@CredStore@@SAJXZ; CredStore::Uninit(void)
0x1800061f4  call    ?UninitializeUserTable@User@@SAXXZ; User::UninitializeUserTable(void)
0x1800061f9  mov     ecx, 472h; uID
0x1800061fe  call    ?LogServiceEvent@@YAXI@Z; LogServiceEvent(uint)
0x180006203  cmp     cs:?ghLog@@3PEAXEA, 0; void * ghLog
0x18000620b  jz      short loc_180006244
0x18000620d  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x180006214  call    cs:__imp_EnterCriticalSection
0x18000621a  mov     rcx, cs:?ghLog@@3PEAXEA; hObject
0x180006221  test    rcx, rcx
0x180006224  jz      short loc_180006237
0x180006226  call    cs:__imp_CloseHandle
0x18000622c  mov     cs:?ghLog@@3PEAXEA, 0; void * ghLog
0x180006237  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18000623e  call    cs:__imp_LeaveCriticalSection
0x180006244  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x18000624b  test    rbx, rbx
0x18000624e  jz      short loc_180006260
0x180006250  mov     rcx, rbx; this
0x180006253  call    ??1EventManager@@QEAA@XZ; EventManager::~EventManager(void)
0x180006258  mov     rcx, rbx; Block
0x18000625b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006260  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180006267  mov     cs:?g_pEventManager@@3PEAVEventManager@@EA, 0; EventManager * g_pEventManager
0x180006272  test    rcx, rcx
0x180006275  jz      short loc_18000629E
0x180006277  mov     r8d, 1; int
0x18000627d  call    ?UpdateSADatServiceFlags@@YAJPEBGEH@Z; UpdateSADatServiceFlags(ushort const *,uchar,int)
0x180006282  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; Block
0x180006289  test    rcx, rcx
0x18000628c  jz      short loc_18000629E
0x18000628e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006293  mov     cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A, 0; _TasksFolderInfo g_TasksFolderInfo
0x18000629e  mov     rcx, cs:?g_ptszSearchPath@@3PEAGEA; Block
0x1800062a5  test    rcx, rcx
0x1800062a8  jz      short loc_1800062AF
0x1800062aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800062af  mov     rbx, [rsp+28h+arg_0]
0x1800062b4  xor     eax, eax
0x1800062b6  add     rsp, 20h
0x1800062ba  pop     rdi
0x1800062bb  retn
```
