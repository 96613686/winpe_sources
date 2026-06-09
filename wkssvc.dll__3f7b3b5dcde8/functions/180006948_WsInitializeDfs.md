# WsInitializeDfs

- ea: `0x180006948`
- end: `0x180006c33`
- name: `WsInitializeDfs`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800065c0`

## callees

- `0x180006948`
- `0x1800082f0`
- `0x18001e420`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x180006a53`
- `ntdll!WinSqmIsOptedIn` at `0x180006a53`
- `ntdll!RtlInitializeGenericTable` at `0x180006ad7`
- `ntdll!RtlInitializeGenericTable` at `0x180006ad7`
- `ntdll!RtlNtStatusToDosError` at `0x1800069fd`
- `ntdll!RtlNtStatusToDosError` at `0x180006b2f`
- `ntdll!RtlNtStatusToDosError` at `0x180006b99`
- `ntdll!RtlNtStatusToDosError` at `0x1800069fd`
- `ntdll!RtlNtStatusToDosError` at `0x180006b2f`
- `ntdll!RtlNtStatusToDosError` at `0x180006b99`
- `ntdll!NtCreateEvent` at `0x1800069f1`
- `ntdll!NtCreateEvent` at `0x1800069f1`
- `ntdll!NtClose` at `0x180006bdb`
- `ntdll!NtClose` at `0x180006bdb`
- `ntdll!RtlRegisterWait` at `0x180006b89`
- `ntdll!RtlRegisterWait` at `0x180006b89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b00`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006a3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006bef`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006a3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006bef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000699f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800069ac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000699f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800069ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006a22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006ae7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006a22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006ae7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006bc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006bce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006bc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006bce`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180006a63`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180006a63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a98`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180006b0d`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180006b0d`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180006b56`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x180006b56`

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
  NotifyIpInterfaceChange(0, (PIPINTERFACE_CHANGE_CALLBACK)DfsIpInterfaceDcUpdate, 0, 1u, &WsDfsIpNotify);
  v9 = RtlRegisterWait(
         &g_WsDomainNameChangeWorkItem,
         g_WsDomainNameChangeEvent,
         (WAITORTIMERCALLBACKFUNC)DfsPeriodicDcUpdate,
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
0x180006948  push    rbp
0x18000694a  push    rbx
0x18000694b  push    rdi
0x18000694c  push    r14
0x18000694e  lea     rbp, [rsp-3Fh]
0x180006953  sub     rsp, 88h
0x18000695a  mov     rax, cs:__security_cookie
0x180006961  xor     rax, rsp
0x180006964  mov     [rbp+57h+var_30], rax
0x180006968  xorps   xmm0, xmm0
0x18000696b  xor     eax, eax
0x18000696d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006971  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006975  lea     ebx, [rax+4]
0x180006978  lea     eax, [rbx+38h]
0x18000697b  mov     cs:g_ulInitThreshold, ebx
0x180006981  mov     cs:g_ulForceThreshold, eax
0x180006987  mov     cs:g_ulForce, eax
0x18000698d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180006991  call    WsInAWorkgroup
0x180006996  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18000699d  mov     edi, eax
0x18000699f  call    cs:__imp_InitializeCriticalSection
0x1800069a5  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x1800069ac  call    cs:__imp_InitializeCriticalSection
0x1800069b2  xorps   xmm0, xmm0
0x1800069b5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800069bc  lea     r9d, [rbx-3]; EventType
0x1800069c0  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800069c8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800069cc  mov     [rbp+57h+ObjectAttributes.Attributes], 80h
0x1800069d3  mov     edx, 100003h; DesiredAccess
0x1800069d8  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1800069e0  lea     rcx, WsDfsTearDownDoneEvent; EventHandle
0x1800069e7  mov     [rsp+0A0h+InitialState], 0; InitialState
0x1800069ec  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800069f1  call    cs:__imp_NtCreateEvent
0x1800069f7  test    eax, eax
0x1800069f9  jz      short loc_180006A08
0x1800069fb  mov     ecx, eax; Status
0x1800069fd  call    cs:__imp_RtlNtStatusToDosError
0x180006a03  jmp     loc_180006C1A
0x180006a08  cmp     cs:hMupEvent, 0
0x180006a10  jnz     short loc_180006A4C
0x180006a12  xor     r8d, r8d; bInitialState
0x180006a15  lea     r9, Name; "wkssvc:  MUP finished initializing even"...
0x180006a1c  xor     ecx, ecx; lpEventAttributes
0x180006a1e  lea     edx, [r8+1]; bManualReset
0x180006a22  call    cs:__imp_CreateEventW
0x180006a28  mov     cs:hMupEvent, rax
0x180006a2f  test    edi, edi
0x180006a31  jz      short loc_180006A4C
0x180006a33  cmp     cs:MupEventSignaled, 0
0x180006a3a  jnz     short loc_180006A4C
0x180006a3c  mov     rcx, rax; hEvent
0x180006a3f  call    cs:__imp_SetEvent
0x180006a45  mov     cs:MupEventSignaled, 1
0x180006a4c  xorps   xmm0, xmm0
0x180006a4f  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180006a53  call    cs:__imp_WinSqmIsOptedIn
0x180006a59  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180006a5d  mov     cs:?gm_IsWinSqmEnabled@DfsSqmWrapper@@0HA, eax; int DfsSqmWrapper::gm_IsWinSqmEnabled
0x180006a63  call    cs:__imp_GetLocalTime
0x180006a69  movzx   ecx, [rbp+57h+SystemTime.wHour]
0x180006a6d  mov     eax, 0AAAAAAABh
0x180006a72  mul     ecx
0x180006a74  shr     edx, 2
0x180006a77  lea     eax, [rdx+rdx*2]
0x180006a7a  xor     edx, edx; dwFlags
0x180006a7c  add     eax, eax
0x180006a7e  sub     ecx, eax
0x180006a80  mov     cs:?gm_wHour@DfsSqmClient@@2GA, cx; ushort DfsSqmClient::gm_wHour
0x180006a87  mov     rcx, gs:60h
0x180006a90  lea     r8d, [rdx+48h]; dwBytes
0x180006a94  mov     rcx, [rcx+30h]; hHeap
0x180006a98  call    cs:__imp_HeapAlloc
0x180006a9e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006aa2  mov     cs:WsDfsNetLuidTable, rax
0x180006aa9  test    rax, rax
0x180006aac  jnz     short loc_180006AB6
0x180006aae  lea     ebx, [rax+0Eh]
0x180006ab1  jmp     loc_180006BA1
0x180006ab6  lea     r9, WsDfsNetLuidTableFreeRoutine; FreeRoutine
0x180006abd  mov     qword ptr [rsp+0A0h+InitialState], 0; TableContext
0x180006ac6  lea     r8, WsDfsNetLuidTableAllocateRoutine; AllocateRoutine
0x180006acd  mov     rcx, rax; Table
0x180006ad0  lea     rdx, WsDfsNetLuidTableCompareRoutine; CompareRoutine
0x180006ad7  call    cs:__imp_RtlInitializeGenericTable
0x180006add  xor     r9d, r9d; lpName
0x180006ae0  xor     r8d, r8d; bInitialState
0x180006ae3  xor     edx, edx; bManualReset
0x180006ae5  xor     ecx, ecx; lpEventAttributes
0x180006ae7  call    cs:__imp_CreateEventW
0x180006aed  mov     cs:g_WsDomainNameChangeEvent, rax
0x180006af4  test    rax, rax
0x180006af7  jnz     short loc_180006B08
0x180006af9  mov     cs:g_WsDomainNameChangeEvent, r14
0x180006b00  call    cs:__imp_GetLastError
0x180006b06  jmp     short loc_180006B35
0x180006b08  mov     rdx, rax; NotificationEventHandle
0x180006b0b  mov     ecx, ebx; InformationClass
0x180006b0d  call    cs:__imp_LsaRegisterPolicyChangeNotification
0x180006b13  mov     ebx, eax
0x180006b15  test    eax, eax
0x180006b17  jns     short loc_180006B3B
0x180006b19  mov     rcx, cs:g_WsDomainNameChangeEvent; hObject
0x180006b20  call    cs:__imp_CloseHandle
0x180006b26  mov     ecx, ebx; Status
0x180006b28  mov     cs:g_WsDomainNameChangeEvent, r14
0x180006b2f  call    cs:__imp_RtlNtStatusToDosError
0x180006b35  mov     ebx, eax
0x180006b37  test    eax, eax
0x180006b39  jnz     short loc_180006BA1
0x180006b3b  lea     rax, WsDfsIpNotify
0x180006b42  xor     ecx, ecx; Family
0x180006b44  mov     r9b, 1; InitialNotification
0x180006b47  mov     qword ptr [rsp+0A0h+InitialState], rax; NotificationHandle
0x180006b4c  xor     r8d, r8d; CallerContext
0x180006b4f  lea     rdx, DfsIpInterfaceDcUpdate; Callback
0x180006b56  call    cs:__imp_NotifyIpInterfaceChange
0x180006b5c  mov     rdx, cs:g_WsDomainNameChangeEvent; hObject
0x180006b63  lea     r8, DfsPeriodicDcUpdate; Callback
0x180006b6a  neg     edi
0x180006b6c  mov     [rsp+0A0h+ulFlags], 19h; ulFlags
0x180006b74  mov     r9, rdx; pvContext
0x180006b77  lea     rcx, g_WsDomainNameChangeWorkItem; phNewWaitObject
0x180006b7e  sbb     eax, eax
0x180006b80  and     eax, 0FFFFFFFEh
0x180006b83  inc     eax
0x180006b85  mov     dword ptr [rsp+0A0h+InitialState], eax; ulMilliseconds
0x180006b89  call    cs:__imp_RtlRegisterWait
0x180006b8f  test    eax, eax
0x180006b91  jns     loc_180006C18
0x180006b97  mov     ecx, eax; Status
0x180006b99  call    cs:__imp_RtlNtStatusToDosError
0x180006b9f  mov     ebx, eax
0x180006ba1  mov     rcx, cs:g_WsDomainNameChangeEvent; hObject
0x180006ba8  cmp     rcx, r14
0x180006bab  jz      short loc_180006BBA
0x180006bad  call    cs:__imp_CloseHandle
0x180006bb3  mov     cs:g_WsDomainNameChangeEvent, r14
0x180006bba  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x180006bc1  call    cs:__imp_DeleteCriticalSection
0x180006bc7  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x180006bce  call    cs:__imp_DeleteCriticalSection
0x180006bd4  mov     rcx, cs:WsDfsTearDownDoneEvent; Handle
0x180006bdb  call    cs:__imp_NtClose
0x180006be1  mov     rcx, cs:hMupEvent; hEvent
0x180006be8  mov     cs:WsDfsTearDownDoneEvent, r14
0x180006bef  call    cs:__imp_SetEvent
0x180006bf5  mov     rcx, cs:hMupEvent; hObject
0x180006bfc  mov     cs:MupEventSignaled, 1
0x180006c03  call    cs:__imp_CloseHandle
0x180006c09  mov     eax, ebx
0x180006c0b  mov     cs:hMupEvent, 0
0x180006c16  jmp     short loc_180006C1A
0x180006c18  xor     eax, eax
0x180006c1a  mov     rcx, [rbp+57h+var_30]
0x180006c1e  xor     rcx, rsp; StackCookie
0x180006c21  call    __security_check_cookie
0x180006c26  add     rsp, 88h
0x180006c2d  pop     r14
0x180006c2f  pop     rdi
0x180006c30  pop     rbx
0x180006c31  pop     rbp
0x180006c32  retn
```
