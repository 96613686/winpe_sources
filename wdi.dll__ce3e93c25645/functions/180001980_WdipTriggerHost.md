# WdipTriggerHost

- ea: `0x180001980`
- end: `0x180001ce4`
- name: `WdipTriggerHost`
- size: `868`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001550`
- `0x1800015b0`
- `0x180001630`

## callees

- `0x180001980`
- `0x180001cf0`
- `0x180002720`
- `0x180002890`
- `0x180002ba0`
- `0x180002e70`

## import_xrefs

- `ntdll!TpAllocAlpcCompletion` at `0x180001aaf`
- `ntdll!TpAllocAlpcCompletion` at `0x180001aaf`
- `ntdll!RtlNtStatusToDosError` at `0x180001bbe`
- `ntdll!RtlNtStatusToDosError` at `0x180001bbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800019e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001a09`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001ae5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800019e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001a09`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001cc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001cd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001cc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001cd9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001a6b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001a6b`

## pseudocode

```c
__int64 __fastcall WdipTriggerHost(PVOID Parameter)
{
  char *EventW; // rsi
  int Args; // eax
  signed int v4; // ebx
  signed int v5; // eax
  PVOID v6; // r9
  NTSTATUS v7; // eax
  signed int v8; // eax
  int v9; // r8d
  signed int v11; // eax
  signed int LastError; // eax
  signed int v13; // eax

  g_lReceivedHostMessageCount = 0;
  EventW = 0;
  g_lExpectedHostMessageCount = 0;
  g_lReceivedDMMessageCount = 0;
  g_lExpectedDMMessageCount = 0;
  g_pHostAlpcCompletion = 0;
  g_hTPHostShutdown = 0;
  g_hTPDMShutdown = 0;
  g_hDMHost = 0;
  Args = WdipLoadSessionInformation();
  v4 = Args;
  if ( Args < 0 )
  {
    v9 = 315;
    goto LABEL_23;
  }
  g_hTPHostShutdown = CreateEventW(0, 1, 0, 0);
  if ( (((unsigned __int64)g_hTPHostShutdown + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      LOBYTE(Args) = v4;
      v9 = 318;
      goto LABEL_23;
    }
  }
  g_hTPDMShutdown = CreateEventW(0, 1, 0, 0);
  if ( (((unsigned __int64)g_hTPDMShutdown + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v13 = GetLastError();
    v4 = v13;
    if ( v13 > 0 )
      v4 = (unsigned __int16)v13 | 0x80070000;
    if ( v4 < 0 )
    {
      LOBYTE(Args) = v4;
      v9 = 321;
      goto LABEL_23;
    }
  }
  g_hDMHost = (HANDLE)WdipDMConnect(0);
  if ( !g_hDMHost )
  {
    v4 = -2147023844;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
      (int)L"WdipTriggerHost",
      326,
      (int)L"Error = %d",
      28);
    goto LABEL_24;
  }
  if ( g_hService )
  {
    *(_QWORD *)&g_sSvcStatus.dwControlsAccepted = 5;
    *(_QWORD *)&g_sSvcStatus.dwCheckPoint = 0;
    g_sSvcStatus.dwCurrentState = 4;
    if ( !SetServiceStatus(g_hService, &g_sSvcStatus) )
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      if ( v4 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
          (int)L"WdipNotifySvc",
          639,
          (int)L"Error = %d",
          v4);
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
          (int)L"WdipTriggerHost",
          343,
          (int)L"Error = %d",
          v4);
        goto LABEL_24;
      }
    }
  }
  if ( Parameter )
  {
    v6 = Parameter;
    goto LABEL_12;
  }
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  if ( ((unsigned __int64)(EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    if ( v4 < 0 )
    {
      LOBYTE(Args) = v4;
      v9 = 353;
LABEL_23:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
        (int)L"WdipTriggerHost",
        v9,
        (int)L"Error = %d",
        Args);
      goto LABEL_24;
    }
  }
  v6 = EventW;
LABEL_12:
  v7 = TpAllocAlpcCompletion(&g_pHostAlpcCompletion, g_hDMHost, WdipHostListener, v6, 0);
  if ( v7 < 0 )
  {
    v11 = RtlNtStatusToDosError(v7);
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
  }
  else
  {
    v4 = 0;
  }
  if ( v4 < 0 )
  {
    LOBYTE(Args) = v4;
    v9 = 365;
    goto LABEL_23;
  }
  if ( !Parameter )
    Parameter = EventW;
  WdipControlServer(Parameter);
LABEL_24:
  if ( (char *)g_hTPHostShutdown - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hTPHostShutdown);
    g_hTPHostShutdown = 0;
  }
  if ( (char *)g_hTPDMShutdown - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hTPDMShutdown);
    g_hTPDMShutdown = 0;
  }
  if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(EventW);
  WdipCleanup();
  _InterlockedExchange(&g_HostState, 0);
  if ( (char *)g_hDMHost - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hDMHost);
    g_hDMHost = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001980  push    rbx
0x180001982  push    rbp
0x180001983  push    rsi
0x180001984  push    rdi
0x180001985  sub     rsp, 38h
0x180001989  xor     ebp, ebp
0x18000198b  mov     rdi, rcx
0x18000198e  mov     cs:g_lReceivedHostMessageCount, ebp
0x180001994  mov     esi, ebp
0x180001996  mov     cs:g_lExpectedHostMessageCount, ebp
0x18000199c  mov     cs:g_lReceivedDMMessageCount, ebp
0x1800019a2  mov     cs:g_lExpectedDMMessageCount, ebp
0x1800019a8  mov     cs:g_pHostAlpcCompletion, rbp
0x1800019af  mov     cs:g_hTPHostShutdown, rbp
0x1800019b6  mov     cs:g_hTPDMShutdown, rbp
0x1800019bd  mov     cs:g_hDMHost, rbp
0x1800019c4  call    WdipLoadSessionInformation
0x1800019c9  mov     ebx, eax
0x1800019cb  test    eax, eax
0x1800019cd  js      loc_180001B9F
0x1800019d3  xor     r9d, r9d; lpName
0x1800019d6  xor     r8d, r8d; bInitialState
0x1800019d9  mov     edx, 1; bManualReset
0x1800019de  xor     ecx, ecx; lpEventAttributes
0x1800019e0  call    cs:__imp_CreateEventW
0x1800019e6  mov     cs:g_hTPHostShutdown, rax
0x1800019ed  inc     rax
0x1800019f0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800019f6  jz      loc_180001C30
0x1800019fc  xor     r9d, r9d; lpName
0x1800019ff  xor     r8d, r8d; bInitialState
0x180001a02  mov     edx, 1; bManualReset
0x180001a07  xor     ecx, ecx; lpEventAttributes
0x180001a09  call    cs:__imp_CreateEventW
0x180001a0f  mov     cs:g_hTPDMShutdown, rax
0x180001a16  inc     rax
0x180001a19  test    rax, 0FFFFFFFFFFFFFFFEh
0x180001a1f  jz      loc_180001C5B
0x180001a25  xor     ecx, ecx
0x180001a27  call    WdipDMConnect
0x180001a2c  mov     cs:g_hDMHost, rax
0x180001a33  test    rax, rax
0x180001a36  jz      loc_180001BEA
0x180001a3c  mov     rcx, cs:?g_hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180001a43  test    rcx, rcx
0x180001a46  jz      short loc_180001A8D
0x180001a48  lea     rdx, ?g_sSvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180001a4f  mov     qword ptr cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 5; _SERVICE_STATUS g_sSvcStatus ...
0x180001a5a  mov     qword ptr cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, rbp; _SERVICE_STATUS g_sSvcStatus ...
0x180001a61  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_sSvcStatus ...
0x180001a6b  call    cs:__imp_SetServiceStatus
0x180001a71  test    eax, eax
0x180001a73  jnz     short loc_180001A8D
0x180001a75  call    cs:__imp_GetLastError
0x180001a7b  mov     ebx, eax
0x180001a7d  test    eax, eax
0x180001a7f  jg      loc_180001C22
0x180001a85  test    ebx, ebx
0x180001a87  js      loc_180001C86
0x180001a8d  test    rdi, rdi
0x180001a90  jz      short loc_180001AD8
0x180001a92  mov     r9, rdi
0x180001a95  mov     rdx, cs:g_hDMHost
0x180001a9c  lea     r8, WdipHostListener
0x180001aa3  lea     rcx, g_pHostAlpcCompletion
0x180001aaa  mov     qword ptr [rsp+58h+Args], rbp
0x180001aaf  call    cs:__imp_TpAllocAlpcCompletion
0x180001ab5  test    eax, eax
0x180001ab7  js      loc_180001BBC
0x180001abd  mov     ebx, ebp
0x180001abf  test    ebx, ebx
0x180001ac1  js      loc_180001BDC
0x180001ac7  test    rdi, rdi
0x180001aca  cmovz   rdi, rsi
0x180001ace  mov     rcx, rdi
0x180001ad1  call    WdipControlServer
0x180001ad6  jmp     short loc_180001B3E
0x180001ad8  xor     r9d, r9d; lpName
0x180001adb  xor     r8d, r8d; bInitialState
0x180001ade  mov     edx, 1; bManualReset
0x180001ae3  xor     ecx, ecx; lpEventAttributes
0x180001ae5  call    cs:__imp_CreateEventW
0x180001aeb  mov     rsi, rax
0x180001aee  lea     rcx, [rax+1]
0x180001af2  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180001af9  jnz     loc_180001CBC
0x180001aff  call    cs:__imp_GetLastError
0x180001b05  mov     ebx, eax
0x180001b07  test    eax, eax
0x180001b09  jg      loc_180001C02
0x180001b0f  test    ebx, ebx
0x180001b11  jns     loc_180001CBC
0x180001b17  movzx   eax, bx
0x180001b1a  mov     r8d, 161h; int
0x180001b20  mov     dword ptr [rsp+58h+Args], eax; Args
0x180001b24  lea     r9, aErrorD_0; "Error = %d"
0x180001b2b  lea     rdx, aWdiptriggerhos; "WdipTriggerHost"
0x180001b32  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001b39  call    WdipTraceError
0x180001b3e  mov     rcx, cs:g_hTPHostShutdown; hObject
0x180001b45  lea     rax, [rcx-1]
0x180001b49  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001b4d  jbe     loc_180001C10
0x180001b53  mov     rcx, cs:g_hTPDMShutdown; hObject
0x180001b5a  lea     rax, [rcx-1]
0x180001b5e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001b62  jbe     loc_180001CC4
0x180001b68  lea     rax, [rsi-1]
0x180001b6c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001b70  jbe     loc_180001CD6
0x180001b76  call    WdipCleanup
0x180001b7b  mov     eax, ebp
0x180001b7d  xchg    eax, cs:g_HostState
0x180001b83  mov     rcx, cs:g_hDMHost; hObject
0x180001b8a  lea     rax, [rcx-1]
0x180001b8e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001b92  jbe     short loc_180001BAD
0x180001b94  mov     eax, ebx
0x180001b96  add     rsp, 38h
0x180001b9a  pop     rdi
0x180001b9b  pop     rsi
0x180001b9c  pop     rbp
0x180001b9d  pop     rbx
0x180001b9e  retn
0x180001b9f  movzx   eax, ax
0x180001ba2  mov     r8d, 13Bh
0x180001ba8  jmp     loc_180001B20
0x180001bad  call    cs:__imp_CloseHandle
0x180001bb3  mov     cs:g_hDMHost, rbp
0x180001bba  jmp     short loc_180001B94
0x180001bbc  mov     ecx, eax; Status
0x180001bbe  call    cs:__imp_RtlNtStatusToDosError
0x180001bc4  mov     ebx, eax
0x180001bc6  test    eax, eax
0x180001bc8  jle     loc_180001ABF
0x180001bce  movzx   ebx, ax
0x180001bd1  or      ebx, 80070000h
0x180001bd7  jmp     loc_180001ABF
0x180001bdc  movzx   eax, bx
0x180001bdf  mov     r8d, 16Dh
0x180001be5  jmp     loc_180001B20
0x180001bea  mov     ebx, 8007041Ch
0x180001bef  mov     dword ptr [rsp+58h+Args], 41Ch
0x180001bf7  mov     r8d, 146h
0x180001bfd  jmp     loc_180001B24
0x180001c02  movzx   ebx, ax
0x180001c05  or      ebx, 80070000h
0x180001c0b  jmp     loc_180001B0F
0x180001c10  call    cs:__imp_CloseHandle
0x180001c16  mov     cs:g_hTPHostShutdown, rbp
0x180001c1d  jmp     loc_180001B53
0x180001c22  movzx   ebx, ax
0x180001c25  or      ebx, 80070000h
0x180001c2b  jmp     loc_180001A85
0x180001c30  call    cs:__imp_GetLastError
0x180001c36  mov     ebx, eax
0x180001c38  test    eax, eax
0x180001c3a  jle     short loc_180001C45
0x180001c3c  movzx   ebx, ax
0x180001c3f  or      ebx, 80070000h
0x180001c45  test    ebx, ebx
0x180001c47  jns     loc_1800019FC
0x180001c4d  movzx   eax, bx
0x180001c50  mov     r8d, 13Eh
0x180001c56  jmp     loc_180001B20
0x180001c5b  call    cs:__imp_GetLastError
0x180001c61  mov     ebx, eax
0x180001c63  test    eax, eax
0x180001c65  jle     short loc_180001C70
0x180001c67  movzx   ebx, ax
0x180001c6a  or      ebx, 80070000h
0x180001c70  test    ebx, ebx
0x180001c72  jns     loc_180001A25
0x180001c78  movzx   eax, bx
0x180001c7b  mov     r8d, 141h
0x180001c81  jmp     loc_180001B20
0x180001c86  movzx   edi, bx
0x180001c89  lea     r9, aErrorD_0; "Error = %d"
0x180001c90  mov     r8d, 27Fh; int
0x180001c96  mov     dword ptr [rsp+58h+Args], edi; Args
0x180001c9a  lea     rdx, aWdipnotifysvc; "WdipNotifySvc"
0x180001ca1  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001ca8  call    WdipTraceError
0x180001cad  mov     dword ptr [rsp+58h+Args], edi
0x180001cb1  mov     r8d, 157h
0x180001cb7  jmp     loc_180001B24
0x180001cbc  mov     r9, rsi
0x180001cbf  jmp     loc_180001A95
0x180001cc4  call    cs:__imp_CloseHandle
0x180001cca  mov     cs:g_hTPDMShutdown, rbp
0x180001cd1  jmp     loc_180001B68
0x180001cd6  mov     rcx, rsi; hObject
0x180001cd9  call    cs:__imp_CloseHandle
0x180001cdf  jmp     loc_180001B76
```
