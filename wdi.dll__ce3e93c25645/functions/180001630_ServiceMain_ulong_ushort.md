# ServiceMain(ulong,ushort * *)

- ea: `0x180001630`
- end: `0x180001828`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `504`
- prototype: `void __fastcall(int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001630`
- `0x180001980`
- `0x180002ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001711`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001684`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001684`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001753`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180001753`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800016c6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800016c6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800016ec`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800016ec`

## string_xrefs

- `0x180001789`: `ServiceMain`

## pseudocode

```c
void __fastcall ServiceMain(int a1, LPCWSTR *a2)
{
  signed int Args; // ebx
  HANDLE EventW; // rcx
  signed int LastError; // eax
  int v5; // r8d
  signed int v6; // eax
  bool v7; // sf
  signed int v8; // eax

  g_sSvcStatus.dwServiceType = 32;
  *(_QWORD *)&g_sSvcStatus.dwCheckPoint = 0;
  g_hHostShutdown = 0;
  LOWORD(Args) = 0;
  *(_OWORD *)&g_sSvcStatus.dwCurrentState = 0;
  _InterlockedExchange(&g_HostState, 1);
  if ( !a1 )
    goto LABEL_2;
  g_hService = RegisterServiceCtrlHandlerExW(*a2, WdipSvcHandlerEx, 0);
  if ( (((unsigned __int64)g_hService + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    Args = LastError;
    if ( LastError > 0 )
      Args = (unsigned __int16)LastError | 0x80070000;
    if ( Args < 0 )
    {
      v5 = 683;
LABEL_16:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
        (int)L"ServiceMain",
        v5,
        (int)L"Error = %d",
        Args);
      goto LABEL_2;
    }
  }
  EventW = CreateEventW(0, 1, 0, 0);
  g_hHostShutdown = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v8 = GetLastError();
    Args = v8;
    if ( v8 > 0 )
      Args = (unsigned __int16)v8 | 0x80070000;
    if ( Args < 0 )
    {
      v5 = 686;
      goto LABEL_16;
    }
    EventW = g_hHostShutdown;
  }
  LOWORD(Args) = WdipTriggerHost(EventW);
  _InterlockedOr(&g_fControl, 1u);
  while ( (g_fControl & 2) != 0 )
    Sleep(0x64u);
LABEL_2:
  if ( (char *)g_hHostShutdown - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hHostShutdown);
    g_hHostShutdown = 0;
  }
  _InterlockedExchange(&g_HostState, 0);
  if ( g_hService )
  {
    g_sSvcStatus.dwWin32ExitCode = (unsigned __int16)Args;
    *(_QWORD *)&g_sSvcStatus.dwCheckPoint = 0;
    g_sSvcStatus.dwCurrentState = 1;
    if ( !SetServiceStatus(g_hService, &g_sSvcStatus) )
    {
      v6 = GetLastError();
      v7 = v6 < 0;
      if ( v6 > 0 )
      {
        v6 = (unsigned __int16)v6 | 0x80070000;
        v7 = v6 < 0;
      }
      if ( v7 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
          (int)L"WdipNotifySvc",
          639,
          (int)L"Error = %d",
          v6);
    }
  }
}

```

## disassembly

```asm
0x180001630  mov     [rsp+arg_0], rbx
0x180001635  push    rdi
0x180001636  sub     rsp, 30h
0x18000163a  xor     edi, edi
0x18000163c  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_sSvcStatus ...
0x180001646  mov     qword ptr cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, rdi; _SERVICE_STATUS g_sSvcStatus ...
0x18000164d  xorps   xmm0, xmm0
0x180001650  mov     cs:g_hHostShutdown, rdi
0x180001657  mov     eax, 1
0x18000165c  mov     r9, rdx
0x18000165f  mov     ebx, edi
0x180001661  movdqu  xmmword ptr cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, xmm0; _SERVICE_STATUS g_sSvcStatus ...
0x180001669  xchg    eax, cs:g_HostState
0x18000166f  test    ecx, ecx
0x180001671  jnz     short loc_1800016DF
0x180001673  mov     rcx, cs:g_hHostShutdown; hObject
0x18000167a  lea     rax, [rcx-1]
0x18000167e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001682  ja      short loc_180001691
0x180001684  call    cs:__imp_CloseHandle
0x18000168a  mov     cs:g_hHostShutdown, rdi
0x180001691  mov     eax, edi
0x180001693  xchg    eax, cs:g_HostState
0x180001699  mov     rcx, cs:?g_hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800016a0  test    rcx, rcx
0x1800016a3  jz      short loc_1800016D4
0x1800016a5  movzx   eax, bx
0x1800016a8  lea     rdx, ?g_sSvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800016af  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, eax; _SERVICE_STATUS g_sSvcStatus ...
0x1800016b5  mov     qword ptr cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, rdi; _SERVICE_STATUS g_sSvcStatus ...
0x1800016bc  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_sSvcStatus ...
0x1800016c6  call    cs:__imp_SetServiceStatus
0x1800016cc  test    eax, eax
0x1800016ce  jz      loc_1800017A5
0x1800016d4  mov     rbx, [rsp+38h+arg_0]
0x1800016d9  add     rsp, 30h
0x1800016dd  pop     rdi
0x1800016de  retn
0x1800016df  mov     rcx, [r9]; lpServiceName
0x1800016e2  lea     rdx, ?WdipSvcHandlerEx@@YAKKKPEAX0@Z; lpHandlerProc
0x1800016e9  xor     r8d, r8d; lpContext
0x1800016ec  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800016f2  mov     cs:?g_hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hService
0x1800016f9  inc     rax
0x1800016fc  test    rax, 0FFFFFFFFFFFFFFFEh
0x180001702  jz      short loc_180001769
0x180001704  xor     r9d, r9d; lpName
0x180001707  xor     r8d, r8d; bInitialState
0x18000170a  mov     edx, 1; bManualReset
0x18000170f  xor     ecx, ecx; lpEventAttributes
0x180001711  call    cs:__imp_CreateEventW
0x180001717  mov     rcx, rax; Parameter
0x18000171a  mov     cs:g_hHostShutdown, rax
0x180001721  inc     rax
0x180001724  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000172a  jz      loc_1800017F8
0x180001730  call    WdipTriggerHost
0x180001735  mov     ebx, eax
0x180001737  lock or cs:?g_fControl@@3JC, 1; long volatile g_fControl
0x18000173f  mov     ecx, cs:?g_fControl@@3JC; long volatile g_fControl
0x180001745  test    cl, 2
0x180001748  jz      loc_180001673
0x18000174e  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180001753  call    cs:__imp_Sleep
0x180001759  mov     ecx, cs:?g_fControl@@3JC; long volatile g_fControl
0x18000175f  test    cl, 2
0x180001762  jnz     short loc_18000174E
0x180001764  jmp     loc_180001673
0x180001769  call    cs:__imp_GetLastError
0x18000176f  mov     ebx, eax
0x180001771  test    eax, eax
0x180001773  jg      short loc_1800017E1
0x180001775  test    ebx, ebx
0x180001777  jns     short loc_180001704
0x180001779  mov     r8d, 2ABh; int
0x18000177f  movzx   eax, bx
0x180001782  lea     r9, aErrorD_0; "Error = %d"
0x180001789  lea     rdx, aServicemain_0; "ServiceMain"
0x180001790  mov     dword ptr [rsp+38h+Args], eax; Args
0x180001794  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000179b  call    WdipTraceError
0x1800017a0  jmp     loc_180001673
0x1800017a5  call    cs:__imp_GetLastError
0x1800017ab  test    eax, eax
0x1800017ad  jg      short loc_1800017EC
0x1800017af  jns     loc_1800016D4
0x1800017b5  movzx   eax, ax
0x1800017b8  lea     r9, aErrorD_0; "Error = %d"
0x1800017bf  mov     r8d, 27Fh; int
0x1800017c5  mov     dword ptr [rsp+38h+Args], eax; Args
0x1800017c9  lea     rdx, aWdipnotifysvc; "WdipNotifySvc"
0x1800017d0  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800017d7  call    WdipTraceError
0x1800017dc  jmp     loc_1800016D4
0x1800017e1  movzx   ebx, ax
0x1800017e4  or      ebx, 80070000h
0x1800017ea  jmp     short loc_180001775
0x1800017ec  movzx   eax, ax
0x1800017ef  or      eax, 80070000h
0x1800017f4  test    eax, eax
0x1800017f6  jmp     short loc_1800017AF
0x1800017f8  call    cs:__imp_GetLastError
0x1800017fe  mov     ebx, eax
0x180001800  test    eax, eax
0x180001802  jle     short loc_18000180D
0x180001804  movzx   ebx, ax
0x180001807  or      ebx, 80070000h
0x18000180d  test    ebx, ebx
0x18000180f  jns     short loc_18000181C
0x180001811  mov     r8d, 2AEh
0x180001817  jmp     loc_18000177F
0x18000181c  mov     rcx, cs:g_hHostShutdown
0x180001823  jmp     loc_180001730
```
