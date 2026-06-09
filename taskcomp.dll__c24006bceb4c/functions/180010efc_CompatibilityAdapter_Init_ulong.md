# CompatibilityAdapter::Init(ulong)

- ea: `0x180010efc`
- end: `0x180011245`
- name: `?Init@CompatibilityAdapter@@AEAAJK@Z`
- size: `841`
- prototype: `__int64 __fastcall(CompatibilityAdapter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001124c`

## callees

- `0x1800031a0`
- `0x180003ef0`
- `0x180004e1c`
- `0x180005474`
- `0x1800055d0`
- `0x18000567c`
- `0x1800059b0`
- `0x180007488`
- `0x1800074d4`
- `0x18000c760`
- `0x180010efc`
- `0x180011308`
- `0x1800115bc`
- `0x180011d44`
- `0x180014b04`
- `0x180015b7c`
- `0x180016dd8`
- `0x18001733c`
- `0x18001a334`
- `0x180026c28`
- `0x180027044`
- `0x18002ae64`
- `0x18002c49c`
- `0x18002c5d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011203`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011203`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010f3d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010f3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800110f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001114d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800110f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001114d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011217`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011217`
- `ntdll!EtwEventRegister` at `0x180010f62`
- `ntdll!EtwEventRegister` at `0x180010f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001110f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001110f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800110e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800110e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010fd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010fd4`

## string_xrefs

- `0x180010fcd`: `taskcomp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180010efc  mov     [rsp+arg_0], rbx
0x180010f01  mov     [rsp+arg_8], rbp
0x180010f06  push    rsi
0x180010f07  push    rdi
0x180010f08  push    r14
0x180010f0a  sub     rsp, 30h
0x180010f0e  mov     rsi, rcx
0x180010f11  mov     ebp, edx
0x180010f13  mov     ecx, 30h ; '0'; Size
0x180010f18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010f1d  xor     r14d, r14d
0x180010f20  mov     [rsp+48h+arg_10], rax
0x180010f25  mov     rbx, rax
0x180010f28  test    rax, rax
0x180010f2b  jz      loc_180011226
0x180010f31  lea     rcx, [rax+8]; lpCriticalSection
0x180010f35  mov     [rax], r14
0x180010f38  xor     r8d, r8d; Flags
0x180010f3b  xor     edx, edx; dwSpinCount
0x180010f3d  call    cs:__imp_InitializeCriticalSectionEx
0x180010f43  mov     cs:?g_pEventManager@@3PEAVEventManager@@EA, rbx; EventManager * g_pEventManager
0x180010f4a  test    rbx, rbx
0x180010f4d  jz      loc_18001122D
0x180010f53  mov     r9, rbx
0x180010f56  lea     rcx, TASKSCHED
0x180010f5d  xor     r8d, r8d
0x180010f60  xor     edx, edx
0x180010f62  call    cs:__imp_EtwEventRegister
0x180010f68  mov     edi, eax
0x180010f6a  cmp     [rbx], r14
0x180010f6d  jz      short loc_180010F73
0x180010f6f  test    eax, eax
0x180010f71  jz      short loc_180010FCD
0x180010f73  mov     r8d, edi; unsigned int
0x180010f76  lea     rdx, aEventregisterE; "EventRegister error"
0x180010f7d  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180010f82  mov     [rbx], r14
0x180010f85  test    edi, edi
0x180010f87  jle     short loc_180010F94
0x180010f89  movzx   edi, di
0x180010f8c  or      edi, 80070000h
0x180010f92  test    edi, edi
0x180010f94  jns     short loc_180010FCD
0x180010f96  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f9d  lea     rax, WPP_GLOBAL_Control
0x180010fa4  cmp     rcx, rax
0x180010fa7  jz      short loc_180010FCD
0x180010fa9  test    byte ptr [rcx+1Ch], 2
0x180010fad  jz      short loc_180010FCD
0x180010faf  cmp     byte ptr [rcx+19h], 2
0x180010fb3  jb      short loc_180010FCD
0x180010fb5  mov     rcx, [rcx+10h]
0x180010fb9  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180010fc0  mov     edx, 0Ah
0x180010fc5  mov     r9d, edi
0x180010fc8  call    WPP_SF_d
0x180010fcd  lea     rcx, ModuleName; "taskcomp.dll"
0x180010fd4  call    cs:__imp_GetModuleHandleW
0x180010fda  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstance
0x180010fe1  call    ?IsLoggingEnabledW@@YAHXZ; IsLoggingEnabledW(void)
0x180010fe6  test    eax, eax
0x180010fe8  jz      short loc_180011021
0x180010fea  call    ?OpenLogFile@@YAJXZ; OpenLogFile(void)
0x180010fef  mov     ebx, eax
0x180010ff1  test    eax, eax
0x180010ff3  jns     short loc_180011012
0x180010ff5  lea     rdx, COMPAT_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180010ffc  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180011003  mov     r8d, ebx; unsigned int
0x180011006  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x18001100b  mov     eax, ebx
0x18001100d  jmp     loc_180011232
0x180011012  mov     ecx, 471h; uID
0x180011017  call    ?LogServiceEvent@@YAXI@Z; LogServiceEvent(uint)
0x18001101c  call    ?RecordFileVersion@@YAXXZ; RecordFileVersion(void)
0x180011021  call    ?InitGlobals@@YAJXZ; InitGlobals(void)
0x180011026  mov     ebx, eax
0x180011028  test    eax, eax
0x18001102a  js      short loc_180010FF5
0x18001102c  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180011033  test    rcx, rcx
0x180011036  jz      short loc_180011040
0x180011038  xor     r8d, r8d; int
0x18001103b  call    ?UpdateSADatServiceFlags@@YAJPEBGEH@Z; UpdateSADatServiceFlags(ushort const *,uchar,int)
0x180011040  call    ?InitSS@@YAJXZ; InitSS(void)
0x180011045  mov     ebx, eax
0x180011047  test    eax, eax
0x180011049  jns     short loc_180011054
0x18001104b  lea     rdx, COMPAT_START_LSA_FAILED
0x180011052  jmp     short loc_180010FFC
0x180011054  call    ?InitializeUserTable@User@@SAJH@Z; User::InitializeUserTable(int)
0x180011059  mov     ebx, eax
0x18001105b  test    eax, eax
0x18001105d  js      short loc_180010FF5
0x18001105f  call    ?Init@CredStore@@SAJXZ; CredStore::Init(void)
0x180011064  mov     ebx, eax
0x180011066  test    eax, eax
0x180011068  js      short loc_180010FF5
0x18001106a  mov     ecx, 50h ; 'P'; Size
0x18001106f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011074  mov     [rsp+48h+arg_10], rax
0x180011079  test    rax, rax
0x18001107c  jz      short loc_180011088
0x18001107e  mov     rcx, rax; this
0x180011081  call    ??0CSchedule@@QEAA@XZ; CSchedule::CSchedule(void)
0x180011086  jmp     short loc_18001108B
0x180011088  mov     rax, r14
0x18001108b  mov     [rsi+8], rax
0x18001108f  test    rax, rax
0x180011092  jnz     short loc_1800110B2
0x180011094  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x18001109b  lea     rdx, COMPAT_START_FAILED; struct _EVENT_DESCRIPTOR *
0x1800110a2  mov     r8d, 8007000Eh; unsigned int
0x1800110a8  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x1800110ad  jmp     loc_18001122D
0x1800110b2  mov     rcx, rax; this
0x1800110b5  call    ?Init@CSchedule@@QEAAJXZ; CSchedule::Init(void)
0x1800110ba  mov     ebx, eax
0x1800110bc  test    eax, eax
0x1800110be  js      loc_180010FF5
0x1800110c4  mov     ecx, ebp; unsigned int
0x1800110c6  call    ?InitializeNetScheduleApi@@YAJK@Z; InitializeNetScheduleApi(ulong)
0x1800110cb  mov     ebx, eax
0x1800110cd  test    eax, eax
0x1800110cf  jns     short loc_1800110DD
0x1800110d1  lea     rdx, COMPAT_START_NETSCHEDULE_FAILED
0x1800110d8  jmp     loc_180010FFC
0x1800110dd  lea     rcx, ?g_ftLastChecked@@3U_FILETIME@@A; lpSystemTimeAsFileTime
0x1800110e4  call    cs:__imp_GetSystemTimeAsFileTime
0x1800110ea  xor     r9d, r9d; lpName
0x1800110ed  xor     r8d, r8d; bInitialState
0x1800110f0  xor     edx, edx; bManualReset
0x1800110f2  xor     ecx, ecx; lpEventAttributes
0x1800110f4  call    cs:__imp_CreateEventW
0x1800110fa  lea     rcx, [rsi+50h]; this
0x1800110fe  mov     rdi, rax
0x180011101  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180011106  mov     [rsi+50h], rdi
0x18001110a  test    rdi, rdi
0x18001110d  jnz     short loc_180011143
0x18001110f  call    cs:__imp_GetLastError
0x180011115  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x18001111c  lea     rdx, COMPAT_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180011123  mov     r8d, eax; unsigned int
0x180011126  mov     ebx, eax
0x180011128  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x18001112d  test    ebx, ebx
0x18001112f  jle     loc_18001100B
0x180011135  movzx   ebx, bx
0x180011138  or      ebx, 80070000h
0x18001113e  jmp     loc_18001100B
0x180011143  xor     r9d, r9d; lpName
0x180011146  xor     r8d, r8d; bInitialState
0x180011149  xor     edx, edx; bManualReset
0x18001114b  xor     ecx, ecx; lpEventAttributes
0x18001114d  call    cs:__imp_CreateEventW
0x180011153  lea     rcx, [rsi+58h]; this
0x180011157  mov     rdi, rax
0x18001115a  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18001115f  mov     [rsi+58h], rdi
0x180011163  test    rdi, rdi
0x180011166  jz      short loc_18001110F
0x180011168  mov     rcx, rsi; struct IFileChangeNotification *
0x18001116b  call    ?Initialize@JournalReader@@SAJPEAUIFileChangeNotification@@@Z; JournalReader::Initialize(IFileChangeNotification *)
0x180011170  mov     ebx, eax
0x180011172  test    eax, eax
0x180011174  js      loc_180010FF5
0x18001117a  mov     rdx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; _TasksFolderInfo g_TasksFolderInfo
0x180011181  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011185  mov     rcx, r8
0x180011188  inc     rcx
0x18001118b  cmp     [rdx+rcx*2], r14w
0x180011190  jnz     short loc_180011188
0x180011192  lea     rbx, [rcx+7]
0x180011196  mov     eax, 2
0x18001119b  mul     rbx
0x18001119e  cmovb   rax, r8
0x1800111a2  mov     rcx, rax; unsigned __int64
0x1800111a5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800111aa  mov     cs:?g_ptszSearchPath@@3PEAGEA, rax; ushort * g_ptszSearchPath
0x1800111b1  mov     r10, rax
0x1800111b4  test    rax, rax
0x1800111b7  jz      loc_180011094
0x1800111bd  mov     [rax], r14w
0x1800111c1  mov     rdx, rbx; unsigned __int64
0x1800111c4  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x1800111cb  mov     rcx, rax; unsigned __int16 *
0x1800111ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800111d3  lea     r8, aJob_1; "\\*.job"
0x1800111da  mov     rdx, rbx; unsigned __int64
0x1800111dd  mov     rcx, r10; unsigned __int16 *
0x1800111e0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800111e5  call    ?StartRpcServer@@YAJXZ; StartRpcServer(void)
0x1800111ea  mov     ebx, eax
0x1800111ec  test    eax, eax
0x1800111ee  jns     short loc_1800111FC
0x1800111f0  lea     rdx, COMPAT_START_RPC_FAILED
0x1800111f7  jmp     loc_180010FFC
0x1800111fc  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011203  call    cs:__imp_EnterCriticalSection
0x180011209  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011210  mov     cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA, rsi; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x180011217  call    cs:__imp_LeaveCriticalSection
0x18001121d  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,void *,_GUID const *)
0x180011222  xor     eax, eax
0x180011224  jmp     short loc_180011232
0x180011226  mov     cs:?g_pEventManager@@3PEAVEventManager@@EA, r14; EventManager * g_pEventManager
0x18001122d  mov     eax, 8007000Eh
0x180011232  mov     rbx, [rsp+48h+arg_0]
0x180011237  mov     rbp, [rsp+48h+arg_8]
0x18001123c  add     rsp, 30h
0x180011240  pop     r14
0x180011242  pop     rdi
0x180011243  pop     rsi
0x180011244  retn
```
