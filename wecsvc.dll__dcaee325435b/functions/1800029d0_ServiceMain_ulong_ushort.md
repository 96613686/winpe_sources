# ServiceMain(ulong,ushort * *)

- ea: `0x1800029d0`
- end: `0x180002b71`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `417`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x18000195c`
- `0x180002694`
- `0x1800029d0`
- `0x1800032dc`
- `0x180005ad0`
- `0x180023010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002a3a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002a6f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002a3a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002a6f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800029f1`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800029f1`

## string_xrefs

- `0x180002b11`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  unsigned int v3; // ebx
  wmi::Exception *v4; // [rsp+40h] [rbp-58h] BYREF
  wmi::Exception *v5; // [rsp+48h] [rbp-50h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-48h] BYREF
  char v7; // [rsp+58h] [rbp-40h]
  const char *v8; // [rsp+60h] [rbp-38h]
  __int64 v9; // [rsp+68h] [rbp-30h]
  __int64 v10; // [rsp+70h] [rbp-28h]
  unsigned int v11; // [rsp+78h] [rbp-20h]
  int v12; // [rsp+7Ch] [rbp-1Ch]
  int v13; // [rsp+80h] [rbp-18h]

  byte_18002F808 = 0;
  v2 = RegisterServiceCtrlHandlerExW(L"wecsvc", HandlerProc, 0);
  g_serviceControl = v2;
  if ( v2 )
  {
    *(_OWORD *)&g_serviceStatus.dwWin32ExitCode = 0;
    g_serviceStatus.dwCurrentState = 2;
    g_serviceStatus.dwServiceType = 32;
    g_serviceStatus.dwControlsAccepted = 0;
    if ( SetServiceStatus(v2, &g_serviceStatus) )
    {
      try
      {
        Initialize();
        g_serviceStatus.dwControlsAccepted = 5;
        g_serviceStatus.dwCurrentState = 4;
        SetServiceStatus(g_serviceControl, &g_serviceStatus);
      }
      catch ( wmi::Exception *v5 )
      {
        g_serviceStatus.dwCurrentState = 1;
        g_serviceStatus.dwWin32ExitCode = (**(__int64 (__fastcall ***)(wmi::Exception *))v5)(v5);
        SetServiceStatus(g_serviceControl, &g_serviceStatus);
        return;
      }
      catch ( ... )
      {
        EcTerminateService();
      }
      try
      {
        if ( !byte_18002F808 )
          CollectorService::SecondPhaseInitialize(g_service);
        v3 = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, _DWORD))g_svchostGlobals
              + 24))(
               &g_svchostShutdownWaitHandle,
               L"wecsvc",
               g_svchostShutdownEvent,
               SvchostShutdownCallback,
               0,
               0);
        if ( v3 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, v3);
          }
          v7 = 0;
          v8 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
          v9 = 0;
          v10 = 0;
          v11 = v3;
          v12 = -1;
          v13 = 361;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::GenericException *)&pExceptionObject;
        }
      }
      catch ( wmi::Exception *v4 )
      {
        Shutdown();
        g_serviceStatus.dwCurrentState = 1;
        g_serviceStatus.dwWin32ExitCode = (**(__int64 (__fastcall ***)(wmi::Exception *))v4)(v4);
        SetServiceStatus(g_serviceControl, &g_serviceStatus);
        return;
      }
      catch ( ... )
      {
        EcTerminateService();
      }
    }
  }
}

```

## disassembly

```asm
0x1800029d0  push    rbx
0x1800029d2  sub     rsp, 90h
0x1800029d9  mov     cs:byte_18002F808, 0
0x1800029e0  xor     r8d, r8d; lpContext
0x1800029e3  lea     rdx, ?HandlerProc@@YAKKKPEAX0@Z; lpHandlerProc
0x1800029ea  lea     rcx, ServiceName; "wecsvc"
0x1800029f1  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800029f7  mov     cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_serviceControl
0x1800029fe  test    rax, rax
0x180002a01  jz      loc_180002B64
0x180002a07  xorps   xmm0, xmm0
0x180002a0a  movdqu  xmmword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, xmm0; _SERVICE_STATUS g_serviceStatus ...
0x180002a12  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_serviceStatus ...
0x180002a1c  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_serviceStatus ...
0x180002a26  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 0; _SERVICE_STATUS g_serviceStatus ...
0x180002a30  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180002a37  mov     rcx, rax; hServiceStatus
0x180002a3a  call    cs:__imp_SetServiceStatus
0x180002a40  test    eax, eax
0x180002a42  jz      loc_180002B64
0x180002a48  call    ?Initialize@@YAXXZ; Initialize(void)
0x180002a4d  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 5; _SERVICE_STATUS g_serviceStatus ...
0x180002a57  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_serviceStatus ...
0x180002a61  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180002a68  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180002a6f  call    cs:__imp_SetServiceStatus
0x180002a75  nop
0x180002a76  cmp     cs:byte_18002F808, 0
0x180002a7d  jnz     short loc_180002A8B
0x180002a7f  mov     rcx, cs:?g_service@@3PEAVCollectorService@@EA; this
0x180002a86  call    ?SecondPhaseInitialize@CollectorService@@QEAAXXZ; CollectorService::SecondPhaseInitialize(void)
0x180002a8b  mov     rax, cs:?g_svchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_svchostGlobals
0x180002a92  mov     [rsp+98h+var_70], 0
0x180002a9a  mov     [rsp+98h+var_78], 0
0x180002aa3  lea     r9, ?SvchostShutdownCallback@@YAXPEAXE@Z; SvchostShutdownCallback(void *,uchar)
0x180002aaa  mov     r8, cs:?g_svchostShutdownEvent@@3PEAXEA; void * g_svchostShutdownEvent
0x180002ab1  lea     rdx, ServiceName; "wecsvc"
0x180002ab8  lea     rcx, ?g_svchostShutdownWaitHandle@@3PEAXEA; void * g_svchostShutdownWaitHandle
0x180002abf  mov     rax, [rax+0C0h]
0x180002ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002acb  mov     ebx, eax
0x180002acd  test    eax, eax
0x180002acf  jz      loc_180002B64
0x180002ad5  lea     rax, WPP_GLOBAL_Control
0x180002adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ae3  cmp     rcx, rax
0x180002ae6  jz      short loc_180002B0C
0x180002ae8  test    byte ptr [rcx+1Ch], 10h
0x180002aec  jz      short loc_180002B0C
0x180002aee  cmp     byte ptr [rcx+19h], 2
0x180002af2  jb      short loc_180002B0C
0x180002af4  mov     edx, 15h
0x180002af9  mov     r9d, ebx
0x180002afc  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x180002b03  mov     rcx, [rcx+10h]
0x180002b07  call    WPP_SF_D
0x180002b0c  mov     [rsp+98h+var_40], 0
0x180002b11  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x180002b18  mov     [rsp+98h+var_38], rax
0x180002b1d  mov     [rsp+98h+var_30], 0
0x180002b26  mov     [rsp+98h+var_28], 0
0x180002b2f  mov     [rsp+98h+var_20], ebx
0x180002b33  mov     [rsp+98h+var_1C], 0FFFFFFFFh
0x180002b3b  mov     [rsp+98h+var_18], 169h
0x180002b46  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180002b4d  mov     [rsp+98h+pExceptionObject], rax
0x180002b52  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180002b59  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180002b5e  call    _CxxThrowException_0
0x180002b64  add     rsp, 90h
0x180002b6b  pop     rbx
0x180002b6c  retn
0x180002b6d  jmp     short loc_180002B64
0x180002b6f  jmp     short loc_180002B64
```
