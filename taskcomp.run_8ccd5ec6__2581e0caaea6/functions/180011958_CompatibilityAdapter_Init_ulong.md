# CompatibilityAdapter::Init(ulong)

- ea: `0x180011958`
- end: `0x180011cd8`
- name: `?Init@CompatibilityAdapter@@AEAAJK@Z`
- size: `896`
- prototype: `__int64 __fastcall(CompatibilityAdapter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180011ce0`

## callees

- `0x180003320`
- `0x1800040c0`
- `0x180005094`
- `0x18000571c`
- `0x180005894`
- `0x18000594c`
- `0x180005cc0`
- `0x180007948`
- `0x180007994`
- `0x18000cf80`
- `0x180011958`
- `0x180011da4`
- `0x180012098`
- `0x180012858`
- `0x18001580c`
- `0x1800169d8`
- `0x180017d84`
- `0x18001831c`
- `0x18001b68c`
- `0x1800283f8`
- `0x180028854`
- `0x18002ca08`
- `0x18002e274`
- `0x18002e3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011c89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011c89`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011999`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011999`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011b68`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011bcd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011b68`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011bcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ca3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ca3`
- `ntdll!EtwEventRegister` at `0x1800119c4`
- `ntdll!EtwEventRegister` at `0x1800119c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b89`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011b52`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011b52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011a3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011a3c`

## string_xrefs

- `0x180011a35`: `taskcomp.dll`

## pseudocode

```c
__int64 __fastcall CompatibilityAdapter::Init(CompatibilityAdapter *this, unsigned int a2)
{
  char *v4; // rax
  EventManager *v5; // rbx
  unsigned int v6; // eax
  EventManager *v7; // rcx
  signed int v8; // edi
  bool v9; // sf
  signed int inited; // ebx
  void *v11; // r9
  __int64 *v12; // rdx
  unsigned __int8 v14; // dl
  int v15; // ecx
  CSchedule *v16; // rax
  void *v17; // r9
  CSchedule *v18; // rax
  HANDLE EventW; // rdi
  void *v20; // r9
  HANDLE v21; // rdi
  __int64 v22; // rcx
  unsigned __int64 v23; // rbx
  WCHAR *v24; // rax
  unsigned __int16 *v25; // r10
  const struct _EVENT_DESCRIPTOR *v26; // rdx
  EventManager *v27; // rcx
  void *v28; // r8
  const struct _GUID *v29; // r9
  const struct _GUID *v30; // [rsp+20h] [rbp-28h]

  v4 = (char *)operator new(0x30u);
  v5 = (EventManager *)v4;
  if ( !v4 )
  {
    g_pEventManager = 0;
    return 2147942414LL;
  }
  *(_QWORD *)v4 = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v4 + 8), 0, 0);
  g_pEventManager = v5;
  v6 = EtwEventRegister(TASKSCHED, 0, 0, v5);
  v8 = v6;
  if ( !*(_QWORD *)v5 || v6 )
  {
    EventManager::LogIt(v7, L"EventRegister error", v6);
    *(_QWORD *)v5 = 0;
    v9 = v8 < 0;
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8 | 0x80070000;
      v9 = v8 < 0;
    }
    if ( v9
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
        (unsigned int)v8);
    }
  }
  g_hInstance = GetModuleHandleW(L"taskcomp.dll");
  if ( (unsigned int)IsLoggingEnabledW() )
  {
    inited = OpenLogFile();
    if ( inited < 0 )
      goto LABEL_13;
    LogServiceEvent(0x471u);
    RecordFileVersion();
  }
  inited = InitGlobals();
  if ( inited < 0 )
    goto LABEL_13;
  if ( g_TasksFolderInfo )
    UpdateSADatServiceFlags(g_TasksFolderInfo, v14, 0);
  inited = InitSS();
  if ( inited < 0 )
  {
    v12 = COMPAT_START_LSA_FAILED;
    goto LABEL_14;
  }
  inited = User::InitializeUserTable(v15);
  if ( inited < 0 || (inited = CredStore::Init(), inited < 0) )
  {
LABEL_13:
    v12 = (__int64 *)&COMPAT_START_FAILED;
LABEL_14:
    EventManager::EvtReport(g_pEventManager, (const struct _EVENT_DESCRIPTOR *)v12, inited, v11, v30);
    return (unsigned int)inited;
  }
  v16 = (CSchedule *)operator new(0x50u);
  if ( v16 )
    v18 = CSchedule::CSchedule(v16);
  else
    v18 = 0;
  *((_QWORD *)this + 1) = v18;
  if ( !v18 )
    goto LABEL_28;
  inited = CSchedule::Init(v18);
  if ( inited < 0 )
    goto LABEL_13;
  inited = InitializeNetScheduleApi(a2);
  if ( inited < 0 )
  {
    v12 = COMPAT_START_NETSCHEDULE_FAILED;
    goto LABEL_14;
  }
  GetSystemTimeAsFileTime(&g_ftLastChecked);
  EventW = CreateEventW(0, 0, 0, 0);
  wmi::AutoHandle::Close((CompatibilityAdapter *)((char *)this + 80));
  *((_QWORD *)this + 10) = EventW;
  if ( !EventW
    || (v21 = CreateEventW(0, 0, 0, 0),
        wmi::AutoHandle::Close((CompatibilityAdapter *)((char *)this + 88)),
        (*((_QWORD *)this + 11) = v21) == 0) )
  {
    inited = GetLastError();
    EventManager::EvtReport(g_pEventManager, &COMPAT_START_FAILED, inited, v20, v30);
    if ( inited > 0 )
      return (unsigned __int16)inited | 0x80070000;
    return (unsigned int)inited;
  }
  inited = JournalReader::Initialize(this);
  if ( inited < 0 )
    goto LABEL_13;
  v22 = -1;
  do
    ++v22;
  while ( g_TasksFolderInfo[v22] );
  v23 = v22 + 7;
  v24 = (WCHAR *)operator new[](saturated_mul(v22 + 7, 2u));
  g_ptszSearchPath = v24;
  if ( !v24 )
  {
LABEL_28:
    EventManager::EvtReport(g_pEventManager, &COMPAT_START_FAILED, 0x8007000E, v17, v30);
    return 2147942414LL;
  }
  *v24 = 0;
  StringCchCopyW(v24, v23, g_TasksFolderInfo);
  StringCchCatW(v25, v23, L"\\*.job");
  inited = StartRpcServer();
  if ( inited < 0 )
  {
    v12 = COMPAT_START_RPC_FAILED;
    goto LABEL_14;
  }
  EnterCriticalSection(&CompatibilityAdapter::s_csAdapterAccess);
  CompatibilityAdapter::g_pAdapter = this;
  LeaveCriticalSection(&CompatibilityAdapter::s_csAdapterAccess);
  EventManager::EvtReport(v27, v26, v28, v29);
  return 0;
}

```

## disassembly

```asm
0x180011958  mov     [rsp+arg_0], rbx
0x18001195d  mov     [rsp+arg_8], rbp
0x180011962  push    rsi
0x180011963  push    rdi
0x180011964  push    r14
0x180011966  sub     rsp, 30h
0x18001196a  mov     rsi, rcx
0x18001196d  mov     ebp, edx
0x18001196f  mov     ecx, 30h ; '0'; Size
0x180011974  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011979  xor     r14d, r14d
0x18001197c  mov     [rsp+48h+arg_10], rax
0x180011981  mov     rbx, rax
0x180011984  test    rax, rax
0x180011987  jz      loc_180011CB8
0x18001198d  lea     rcx, [rax+8]; lpCriticalSection
0x180011991  mov     [rax], r14
0x180011994  xor     r8d, r8d; Flags
0x180011997  xor     edx, edx; dwSpinCount
0x180011999  call    cs:__imp_InitializeCriticalSectionEx
0x1800119a0  nop     dword ptr [rax+rax+00h]
0x1800119a5  mov     cs:?g_pEventManager@@3PEAVEventManager@@EA, rbx; EventManager * g_pEventManager
0x1800119ac  test    rbx, rbx
0x1800119af  jz      loc_180011CBF
0x1800119b5  mov     r9, rbx
0x1800119b8  lea     rcx, TASKSCHED
0x1800119bf  xor     r8d, r8d
0x1800119c2  xor     edx, edx
0x1800119c4  call    cs:__imp_EtwEventRegister
0x1800119cb  nop     dword ptr [rax+rax+00h]
0x1800119d0  mov     edi, eax
0x1800119d2  cmp     [rbx], r14
0x1800119d5  jz      short loc_1800119DB
0x1800119d7  test    eax, eax
0x1800119d9  jz      short loc_180011A35
0x1800119db  mov     r8d, edi; unsigned int
0x1800119de  lea     rdx, aEventregisterE; "EventRegister error"
0x1800119e5  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x1800119ea  mov     [rbx], r14
0x1800119ed  test    edi, edi
0x1800119ef  jle     short loc_1800119FC
0x1800119f1  movzx   edi, di
0x1800119f4  or      edi, 80070000h
0x1800119fa  test    edi, edi
0x1800119fc  jns     short loc_180011A35
0x1800119fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a05  lea     rax, WPP_GLOBAL_Control
0x180011a0c  cmp     rcx, rax
0x180011a0f  jz      short loc_180011A35
0x180011a11  test    byte ptr [rcx+1Ch], 2
0x180011a15  jz      short loc_180011A35
0x180011a17  cmp     byte ptr [rcx+19h], 2
0x180011a1b  jb      short loc_180011A35
0x180011a1d  mov     rcx, [rcx+10h]
0x180011a21  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011a28  mov     edx, 0Ah
0x180011a2d  mov     r9d, edi
0x180011a30  call    WPP_SF_d
0x180011a35  lea     rcx, ModuleName; "taskcomp.dll"
0x180011a3c  call    cs:__imp_GetModuleHandleW
0x180011a43  nop     dword ptr [rax+rax+00h]
0x180011a48  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstance
0x180011a4f  call    ?IsLoggingEnabledW@@YAHXZ; IsLoggingEnabledW(void)
0x180011a54  test    eax, eax
0x180011a56  jz      short loc_180011A8F
0x180011a58  call    ?OpenLogFile@@YAJXZ; OpenLogFile(void)
0x180011a5d  mov     ebx, eax
0x180011a5f  test    eax, eax
0x180011a61  jns     short loc_180011A80
0x180011a63  lea     rdx, COMPAT_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180011a6a  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180011a71  mov     r8d, ebx; unsigned int
0x180011a74  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x180011a79  mov     eax, ebx
0x180011a7b  jmp     loc_180011CC4
0x180011a80  mov     ecx, 471h; uID
0x180011a85  call    ?LogServiceEvent@@YAXI@Z; LogServiceEvent(uint)
0x180011a8a  call    ?RecordFileVersion@@YAXXZ; RecordFileVersion(void)
0x180011a8f  call    ?InitGlobals@@YAJXZ; InitGlobals(void)
0x180011a94  mov     ebx, eax
0x180011a96  test    eax, eax
0x180011a98  js      short loc_180011A63
0x180011a9a  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180011aa1  test    rcx, rcx
0x180011aa4  jz      short loc_180011AAE
0x180011aa6  xor     r8d, r8d; int
0x180011aa9  call    ?UpdateSADatServiceFlags@@YAJPEBGEH@Z; UpdateSADatServiceFlags(ushort const *,uchar,int)
0x180011aae  call    ?InitSS@@YAJXZ; InitSS(void)
0x180011ab3  mov     ebx, eax
0x180011ab5  test    eax, eax
0x180011ab7  jns     short loc_180011AC2
0x180011ab9  lea     rdx, COMPAT_START_LSA_FAILED
0x180011ac0  jmp     short loc_180011A6A
0x180011ac2  call    ?InitializeUserTable@User@@SAJH@Z; User::InitializeUserTable(int)
0x180011ac7  mov     ebx, eax
0x180011ac9  test    eax, eax
0x180011acb  js      short loc_180011A63
0x180011acd  call    ?Init@CredStore@@SAJXZ; CredStore::Init(void)
0x180011ad2  mov     ebx, eax
0x180011ad4  test    eax, eax
0x180011ad6  js      short loc_180011A63
0x180011ad8  mov     ecx, 50h ; 'P'; Size
0x180011add  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011ae2  mov     [rsp+48h+arg_10], rax
0x180011ae7  test    rax, rax
0x180011aea  jz      short loc_180011AF6
0x180011aec  mov     rcx, rax; this
0x180011aef  call    ??0CSchedule@@QEAA@XZ; CSchedule::CSchedule(void)
0x180011af4  jmp     short loc_180011AF9
0x180011af6  mov     rax, r14
0x180011af9  mov     [rsi+8], rax
0x180011afd  test    rax, rax
0x180011b00  jnz     short loc_180011B20
0x180011b02  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180011b09  lea     rdx, COMPAT_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180011b10  mov     r8d, 8007000Eh; unsigned int
0x180011b16  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x180011b1b  jmp     loc_180011CBF
0x180011b20  mov     rcx, rax; this
0x180011b23  call    ?Init@CSchedule@@QEAAJXZ; CSchedule::Init(void)
0x180011b28  mov     ebx, eax
0x180011b2a  test    eax, eax
0x180011b2c  js      loc_180011A63
0x180011b32  mov     ecx, ebp; unsigned int
0x180011b34  call    ?InitializeNetScheduleApi@@YAJK@Z; InitializeNetScheduleApi(ulong)
0x180011b39  mov     ebx, eax
0x180011b3b  test    eax, eax
0x180011b3d  jns     short loc_180011B4B
0x180011b3f  lea     rdx, COMPAT_START_NETSCHEDULE_FAILED
0x180011b46  jmp     loc_180011A6A
0x180011b4b  lea     rcx, ?g_ftLastChecked@@3U_FILETIME@@A; lpSystemTimeAsFileTime
0x180011b52  call    cs:__imp_GetSystemTimeAsFileTime
0x180011b59  nop     dword ptr [rax+rax+00h]
0x180011b5e  xor     r9d, r9d; lpName
0x180011b61  xor     r8d, r8d; bInitialState
0x180011b64  xor     edx, edx; bManualReset
0x180011b66  xor     ecx, ecx; lpEventAttributes
0x180011b68  call    cs:__imp_CreateEventW
0x180011b6f  nop     dword ptr [rax+rax+00h]
0x180011b74  lea     rcx, [rsi+50h]; this
0x180011b78  mov     rdi, rax
0x180011b7b  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180011b80  mov     [rsi+50h], rdi
0x180011b84  test    rdi, rdi
0x180011b87  jnz     short loc_180011BC3
0x180011b89  call    cs:__imp_GetLastError
0x180011b90  nop     dword ptr [rax+rax+00h]
0x180011b95  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180011b9c  lea     rdx, COMPAT_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180011ba3  mov     r8d, eax; unsigned int
0x180011ba6  mov     ebx, eax
0x180011ba8  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x180011bad  test    ebx, ebx
0x180011baf  jle     loc_180011A79
0x180011bb5  movzx   ebx, bx
0x180011bb8  or      ebx, 80070000h
0x180011bbe  jmp     loc_180011A79
0x180011bc3  xor     r9d, r9d; lpName
0x180011bc6  xor     r8d, r8d; bInitialState
0x180011bc9  xor     edx, edx; bManualReset
0x180011bcb  xor     ecx, ecx; lpEventAttributes
0x180011bcd  call    cs:__imp_CreateEventW
0x180011bd4  nop     dword ptr [rax+rax+00h]
0x180011bd9  lea     rcx, [rsi+58h]; this
0x180011bdd  mov     rdi, rax
0x180011be0  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180011be5  mov     [rsi+58h], rdi
0x180011be9  test    rdi, rdi
0x180011bec  jz      short loc_180011B89
0x180011bee  mov     rcx, rsi; struct IFileChangeNotification *
0x180011bf1  call    ?Initialize@JournalReader@@SAJPEAUIFileChangeNotification@@@Z; JournalReader::Initialize(IFileChangeNotification *)
0x180011bf6  mov     ebx, eax
0x180011bf8  test    eax, eax
0x180011bfa  js      loc_180011A63
0x180011c00  mov     rdx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; _TasksFolderInfo g_TasksFolderInfo
0x180011c07  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011c0b  mov     rcx, r8
0x180011c0e  inc     rcx
0x180011c11  cmp     [rdx+rcx*2], r14w
0x180011c16  jnz     short loc_180011C0E
0x180011c18  lea     rbx, [rcx+7]
0x180011c1c  mov     eax, 2
0x180011c21  mul     rbx
0x180011c24  cmovb   rax, r8
0x180011c28  mov     rcx, rax; unsigned __int64
0x180011c2b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011c30  mov     cs:?g_ptszSearchPath@@3PEAGEA, rax; ushort * g_ptszSearchPath
0x180011c37  mov     r10, rax
0x180011c3a  test    rax, rax
0x180011c3d  jz      loc_180011B02
0x180011c43  mov     [rax], r14w
0x180011c47  mov     rdx, rbx; unsigned __int64
0x180011c4a  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180011c51  mov     rcx, rax; unsigned __int16 *
0x180011c54  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011c59  lea     r8, aJob_1; "\\*.job"
0x180011c60  mov     rdx, rbx; unsigned __int64
0x180011c63  mov     rcx, r10; unsigned __int16 *
0x180011c66  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011c6b  call    ?StartRpcServer@@YAJXZ; StartRpcServer(void)
0x180011c70  mov     ebx, eax
0x180011c72  test    eax, eax
0x180011c74  jns     short loc_180011C82
0x180011c76  lea     rdx, COMPAT_START_RPC_FAILED
0x180011c7d  jmp     loc_180011A6A
0x180011c82  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011c89  call    cs:__imp_EnterCriticalSection
0x180011c90  nop     dword ptr [rax+rax+00h]
0x180011c95  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011c9c  mov     cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA, rsi; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x180011ca3  call    cs:__imp_LeaveCriticalSection
0x180011caa  nop     dword ptr [rax+rax+00h]
0x180011caf  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,void *,_GUID const *)
0x180011cb4  xor     eax, eax
0x180011cb6  jmp     short loc_180011CC4
0x180011cb8  mov     cs:?g_pEventManager@@3PEAVEventManager@@EA, r14; EventManager * g_pEventManager
0x180011cbf  mov     eax, 8007000Eh
0x180011cc4  mov     rbx, [rsp+48h+arg_0]
0x180011cc9  mov     rbp, [rsp+48h+arg_8]
0x180011cce  add     rsp, 30h
0x180011cd2  pop     r14
0x180011cd4  pop     rdi
0x180011cd5  pop     rsi
0x180011cd6  retn
```
