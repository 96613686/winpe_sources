# WsInitializeDfs

- ea: `0x180006ea0`
- end: `0x18000721c`
- name: `WsInitializeDfs`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006a98`

## callees

- `0x180006ea0`
- `0x18000b190`
- `0x18001fbd0`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x180006fcf`
- `ntdll!WinSqmIsOptedIn` at `0x180006fcf`
- `ntdll!RtlInitializeGenericTable` at `0x180007065`
- `ntdll!RtlInitializeGenericTable` at `0x180007065`
- `ntdll!RtlNtStatusToDosError` at `0x180006f67`
- `ntdll!RtlNtStatusToDosError` at `0x1800070db`
- `ntdll!RtlNtStatusToDosError` at `0x180007157`
- `ntdll!RtlNtStatusToDosError` at `0x180006f67`
- `ntdll!RtlNtStatusToDosError` at `0x1800070db`
- `ntdll!RtlNtStatusToDosError` at `0x180007157`
- `ntdll!NtCreateEvent` at `0x180006f55`
- `ntdll!NtCreateEvent` at `0x180006f55`
- `ntdll!NtClose` at `0x1800071b1`
- `ntdll!NtClose` at `0x1800071b1`
- `ntdll!RtlRegisterWait` at `0x180007141`
- `ntdll!RtlRegisterWait` at `0x180007141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000709a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000709a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006fb5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800071cb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006fb5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800071cb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006ef7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006f0a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006ef7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006f0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006f92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000707b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006f92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000707b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000718b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000719e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000718b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000719e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180006fe5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180006fe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007171`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007171`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007020`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007020`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x1800070ad`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x1800070ad`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180007108`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180007108`

## pseudocode

```c
ULONG WsInitializeDfs()
{
  int v0; // edi
  NTSTATUS v1; // eax
  ULONG result; // eax
  HANDLE EventW; // rax
  struct _RTL_GENERIC_TABLE *v4; // rax
  ULONG v5; // ebx
  HANDLE v6; // rax
  DWORD LastError; // eax
  int v8; // ebx
  int v9; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-19h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp+17h] BYREF

  memset(&ObjectAttributes.Length + 1, 0, 40);
  g_ulInitThreshold = 4;
  g_ulForceThreshold = 60;
  g_ulForce = 60;
  v0 = WsInAWorkgroup();
  InitializeCriticalSection(&WsDfsTearDownCriticalSection);
  InitializeCriticalSection(&WsDfsNetLuidTableCriticalSection);
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 128;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = NtCreateEvent(&WsDfsTearDownDoneEvent, 0x100003u, &ObjectAttributes, SynchronizationEvent, 0);
  if ( v1 )
    return RtlNtStatusToDosError(v1);
  if ( !hMupEvent )
  {
    EventW = CreateEventW(0, 1, 0, L"wkssvc:  MUP finished initializing event");
    hMupEvent = EventW;
    if ( v0 )
    {
      if ( !MupEventSignaled )
      {
        SetEvent(EventW);
        MupEventSignaled = 1;
      }
    }
  }
  SystemTime = 0;
  DfsSqmWrapper::gm_IsWinSqmEnabled = WinSqmIsOptedIn();
  GetLocalTime(&SystemTime);
  DfsSqmClient::gm_wHour = SystemTime.wHour % 6u;
  v4 = (struct _RTL_GENERIC_TABLE *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
  WsDfsNetLuidTable = v4;
  if ( !v4 )
  {
    v5 = 14;
    goto LABEL_16;
  }
  RtlInitializeGenericTable(
    v4,
    WsDfsNetLuidTableCompareRoutine,
    WsDfsNetLuidTableAllocateRoutine,
    WsDfsNetLuidTableFreeRoutine,
    0);
  v6 = CreateEventW(0, 0, 0, 0);
  g_WsDomainNameChangeEvent = v6;
  if ( !v6 )
  {
    g_WsDomainNameChangeEvent = (HANDLE)-1LL;
    LastError = GetLastError();
    goto LABEL_13;
  }
  v8 = LsaRegisterPolicyChangeNotification(PolicyNotifyDnsDomainInformation, v6);
  if ( v8 < 0 )
  {
    CloseHandle(g_WsDomainNameChangeEvent);
    g_WsDomainNameChangeEvent = (HANDLE)-1LL;
    LastError = RtlNtStatusToDosError(v8);
LABEL_13:
    v5 = LastError;
    if ( LastError )
      goto LABEL_16;
  }
  NotifyIpInterfaceChange(0, DfsIpInterfaceDcUpdate, 0, 1u, &WsDfsIpNotify);
  v9 = RtlRegisterWait(
         &g_WsDomainNameChangeWorkItem,
         g_WsDomainNameChangeEvent,
         DfsPeriodicDcUpdate,
         g_WsDomainNameChangeEvent,
         v0 != 0 ? -1 : 1,
         0x19u);
  if ( v9 >= 0 )
    return 0;
  v5 = RtlNtStatusToDosError(v9);
LABEL_16:
  if ( g_WsDomainNameChangeEvent != (HANDLE)-1LL )
  {
    CloseHandle(g_WsDomainNameChangeEvent);
    g_WsDomainNameChangeEvent = (HANDLE)-1LL;
  }
  DeleteCriticalSection(&WsDfsTearDownCriticalSection);
  DeleteCriticalSection(&WsDfsNetLuidTableCriticalSection);
  NtClose(WsDfsTearDownDoneEvent);
  WsDfsTearDownDoneEvent = (HANDLE)-1LL;
  SetEvent(hMupEvent);
  MupEventSignaled = 1;
  CloseHandle(hMupEvent);
  result = v5;
  hMupEvent = 0;
  return result;
}

```

## disassembly

```asm
0x180006ea0  push    rbp
0x180006ea2  push    rbx
0x180006ea3  push    rdi
0x180006ea4  push    r14
0x180006ea6  lea     rbp, [rsp-3Fh]
0x180006eab  sub     rsp, 88h
0x180006eb2  mov     rax, cs:__security_cookie
0x180006eb9  xor     rax, rsp
0x180006ebc  mov     [rbp+57h+var_30], rax
0x180006ec0  xorps   xmm0, xmm0
0x180006ec3  xor     eax, eax
0x180006ec5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006ec9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006ecd  lea     ebx, [rax+4]
0x180006ed0  lea     eax, [rbx+38h]
0x180006ed3  mov     cs:g_ulInitThreshold, ebx
0x180006ed9  mov     cs:g_ulForceThreshold, eax
0x180006edf  mov     cs:g_ulForce, eax
0x180006ee5  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180006ee9  call    WsInAWorkgroup
0x180006eee  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x180006ef5  mov     edi, eax
0x180006ef7  call    cs:__imp_InitializeCriticalSection
0x180006efe  nop     dword ptr [rax+rax+00h]
0x180006f03  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x180006f0a  call    cs:__imp_InitializeCriticalSection
0x180006f11  nop     dword ptr [rax+rax+00h]
0x180006f16  xorps   xmm0, xmm0
0x180006f19  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180006f20  lea     r9d, [rbx-3]; EventType
0x180006f24  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180006f2c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006f30  mov     [rbp+57h+ObjectAttributes.Attributes], 80h
0x180006f37  mov     edx, 100003h; DesiredAccess
0x180006f3c  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180006f44  lea     rcx, WsDfsTearDownDoneEvent; EventHandle
0x180006f4b  mov     [rsp+0A0h+InitialState], 0; InitialState
0x180006f50  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006f55  call    cs:__imp_NtCreateEvent
0x180006f5c  nop     dword ptr [rax+rax+00h]
0x180006f61  test    eax, eax
0x180006f63  jz      short loc_180006F78
0x180006f65  mov     ecx, eax; Status
0x180006f67  call    cs:__imp_RtlNtStatusToDosError
0x180006f6e  nop     dword ptr [rax+rax+00h]
0x180006f73  jmp     loc_180007202
0x180006f78  cmp     cs:hMupEvent, 0
0x180006f80  jnz     short loc_180006FC8
0x180006f82  xor     r8d, r8d; bInitialState
0x180006f85  lea     r9, Name; "wkssvc:  MUP finished initializing even"...
0x180006f8c  xor     ecx, ecx; lpEventAttributes
0x180006f8e  lea     edx, [r8+1]; bManualReset
0x180006f92  call    cs:__imp_CreateEventW
0x180006f99  nop     dword ptr [rax+rax+00h]
0x180006f9e  mov     cs:hMupEvent, rax
0x180006fa5  test    edi, edi
0x180006fa7  jz      short loc_180006FC8
0x180006fa9  cmp     cs:MupEventSignaled, 0
0x180006fb0  jnz     short loc_180006FC8
0x180006fb2  mov     rcx, rax; hEvent
0x180006fb5  call    cs:__imp_SetEvent
0x180006fbc  nop     dword ptr [rax+rax+00h]
0x180006fc1  mov     cs:MupEventSignaled, 1
0x180006fc8  xorps   xmm0, xmm0
0x180006fcb  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180006fcf  call    cs:__imp_WinSqmIsOptedIn
0x180006fd6  nop     dword ptr [rax+rax+00h]
0x180006fdb  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180006fdf  mov     cs:?gm_IsWinSqmEnabled@DfsSqmWrapper@@0HA, eax; int DfsSqmWrapper::gm_IsWinSqmEnabled
0x180006fe5  call    cs:__imp_GetLocalTime
0x180006fec  nop     dword ptr [rax+rax+00h]
0x180006ff1  movzx   ecx, [rbp+57h+SystemTime.wHour]
0x180006ff5  mov     eax, 0AAAAAAABh
0x180006ffa  mul     ecx
0x180006ffc  shr     edx, 2
0x180006fff  lea     eax, [rdx+rdx*2]
0x180007002  xor     edx, edx; dwFlags
0x180007004  add     eax, eax
0x180007006  sub     ecx, eax
0x180007008  mov     cs:?gm_wHour@DfsSqmClient@@2GA, cx; ushort DfsSqmClient::gm_wHour
0x18000700f  mov     rcx, gs:60h
0x180007018  lea     r8d, [rdx+48h]; dwBytes
0x18000701c  mov     rcx, [rcx+30h]; hHeap
0x180007020  call    cs:__imp_HeapAlloc
0x180007027  nop     dword ptr [rax+rax+00h]
0x18000702c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180007030  mov     cs:WsDfsNetLuidTable, rax
0x180007037  test    rax, rax
0x18000703a  jnz     short loc_180007044
0x18000703c  lea     ebx, [rax+0Eh]
0x18000703f  jmp     loc_180007165
0x180007044  lea     r9, WsDfsNetLuidTableFreeRoutine; FreeRoutine
0x18000704b  mov     qword ptr [rsp+0A0h+InitialState], 0; TableContext
0x180007054  lea     r8, WsDfsNetLuidTableAllocateRoutine; AllocateRoutine
0x18000705b  mov     rcx, rax; Table
0x18000705e  lea     rdx, WsDfsNetLuidTableCompareRoutine; CompareRoutine
0x180007065  call    cs:__imp_RtlInitializeGenericTable
0x18000706c  nop     dword ptr [rax+rax+00h]
0x180007071  xor     r9d, r9d; lpName
0x180007074  xor     r8d, r8d; bInitialState
0x180007077  xor     edx, edx; bManualReset
0x180007079  xor     ecx, ecx; lpEventAttributes
0x18000707b  call    cs:__imp_CreateEventW
0x180007082  nop     dword ptr [rax+rax+00h]
0x180007087  mov     cs:g_WsDomainNameChangeEvent, rax
0x18000708e  test    rax, rax
0x180007091  jnz     short loc_1800070A8
0x180007093  mov     cs:g_WsDomainNameChangeEvent, r14
0x18000709a  call    cs:__imp_GetLastError
0x1800070a1  nop     dword ptr [rax+rax+00h]
0x1800070a6  jmp     short loc_1800070E7
0x1800070a8  mov     rdx, rax; NotificationEventHandle
0x1800070ab  mov     ecx, ebx; InformationClass
0x1800070ad  call    cs:__imp_LsaRegisterPolicyChangeNotification
0x1800070b4  nop     dword ptr [rax+rax+00h]
0x1800070b9  mov     ebx, eax
0x1800070bb  test    eax, eax
0x1800070bd  jns     short loc_1800070ED
0x1800070bf  mov     rcx, cs:g_WsDomainNameChangeEvent; hObject
0x1800070c6  call    cs:__imp_CloseHandle
0x1800070cd  nop     dword ptr [rax+rax+00h]
0x1800070d2  mov     ecx, ebx; Status
0x1800070d4  mov     cs:g_WsDomainNameChangeEvent, r14
0x1800070db  call    cs:__imp_RtlNtStatusToDosError
0x1800070e2  nop     dword ptr [rax+rax+00h]
0x1800070e7  mov     ebx, eax
0x1800070e9  test    eax, eax
0x1800070eb  jnz     short loc_180007165
0x1800070ed  lea     rax, WsDfsIpNotify
0x1800070f4  xor     ecx, ecx; Family
0x1800070f6  mov     r9b, 1; InitialNotification
0x1800070f9  mov     qword ptr [rsp+0A0h+InitialState], rax; NotificationHandle
0x1800070fe  xor     r8d, r8d; CallerContext
0x180007101  lea     rdx, DfsIpInterfaceDcUpdate; Callback
0x180007108  call    cs:__imp_NotifyIpInterfaceChange
0x18000710f  nop     dword ptr [rax+rax+00h]
0x180007114  mov     rdx, cs:g_WsDomainNameChangeEvent; hObject
0x18000711b  lea     r8, DfsPeriodicDcUpdate; Callback
0x180007122  neg     edi
0x180007124  mov     [rsp+0A0h+ulFlags], 19h; ulFlags
0x18000712c  mov     r9, rdx; pvContext
0x18000712f  lea     rcx, g_WsDomainNameChangeWorkItem; phNewWaitObject
0x180007136  sbb     eax, eax
0x180007138  and     eax, 0FFFFFFFEh
0x18000713b  inc     eax
0x18000713d  mov     dword ptr [rsp+0A0h+InitialState], eax; ulMilliseconds
0x180007141  call    cs:__imp_RtlRegisterWait
0x180007148  nop     dword ptr [rax+rax+00h]
0x18000714d  test    eax, eax
0x18000714f  jns     loc_180007200
0x180007155  mov     ecx, eax; Status
0x180007157  call    cs:__imp_RtlNtStatusToDosError
0x18000715e  nop     dword ptr [rax+rax+00h]
0x180007163  mov     ebx, eax
0x180007165  mov     rcx, cs:g_WsDomainNameChangeEvent; hObject
0x18000716c  cmp     rcx, r14
0x18000716f  jz      short loc_180007184
0x180007171  call    cs:__imp_CloseHandle
0x180007178  nop     dword ptr [rax+rax+00h]
0x18000717d  mov     cs:g_WsDomainNameChangeEvent, r14
0x180007184  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18000718b  call    cs:__imp_DeleteCriticalSection
0x180007192  nop     dword ptr [rax+rax+00h]
0x180007197  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18000719e  call    cs:__imp_DeleteCriticalSection
0x1800071a5  nop     dword ptr [rax+rax+00h]
0x1800071aa  mov     rcx, cs:WsDfsTearDownDoneEvent; Handle
0x1800071b1  call    cs:__imp_NtClose
0x1800071b8  nop     dword ptr [rax+rax+00h]
0x1800071bd  mov     rcx, cs:hMupEvent; hEvent
0x1800071c4  mov     cs:WsDfsTearDownDoneEvent, r14
0x1800071cb  call    cs:__imp_SetEvent
0x1800071d2  nop     dword ptr [rax+rax+00h]
0x1800071d7  mov     rcx, cs:hMupEvent; hObject
0x1800071de  mov     cs:MupEventSignaled, 1
0x1800071e5  call    cs:__imp_CloseHandle
0x1800071ec  nop     dword ptr [rax+rax+00h]
0x1800071f1  mov     eax, ebx
0x1800071f3  mov     cs:hMupEvent, 0
0x1800071fe  jmp     short loc_180007202
0x180007200  xor     eax, eax
0x180007202  mov     rcx, [rbp+57h+var_30]
0x180007206  xor     rcx, rsp; StackCookie
0x180007209  call    __security_check_cookie
0x18000720e  add     rsp, 88h
0x180007215  pop     r14
0x180007217  pop     rdi
0x180007218  pop     rbx
0x180007219  pop     rbp
0x18000721a  retn
```
