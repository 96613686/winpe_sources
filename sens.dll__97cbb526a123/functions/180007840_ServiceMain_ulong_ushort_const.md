# ServiceMain(ulong,ushort * * const)

- ea: `0x180007840`
- end: `0x1800079a0`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `352`
- prototype: `void __fastcall(__int64, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x1800066d0`
- `0x180007164`
- `0x180007840`
- `0x180008300`
- `0x180009310`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078d3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800078aa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800078aa`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000788d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000788d`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **const a2)
{
  unsigned int v2; // edx
  DWORD LastError; // eax
  unsigned int v4; // eax
  unsigned int v5; // edx

  ghStatusHandle = 0;
  gServiceStatus.dwServiceType = 16;
  gServiceStatus.dwCurrentState = 2;
  gServiceStatus.dwWaitHint = 3000;
  *(_OWORD *)&gServiceStatus.dwControlsAccepted = 0;
  ghStatusHandle = RegisterServiceCtrlHandlerExW(L"SENS", ServiceControl, (LPVOID)0x19732304);
  if ( ghStatusHandle )
  {
    if ( !GetSystemPowerStatus(&gSystemPowerState)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids, LastError);
    }
    if ( (unsigned int)ReportStatusToSCM(2u, v2, 0xBB8u) )
    {
      ServiceStart();
      v4 = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, _DWORD))g_svchostGlobals
            + 24))(
             &g_svchostShutdownWaitHandle,
             L"SENS",
             g_svchostShutdownEvent,
             SvchostShutdownCallback,
             0,
             0);
      if ( v4 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids, v4);
        }
        ServiceStop();
        ReportStatusToSCM(1u, v5, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x180007840  push    rsi
0x180007842  sub     rsp, 40h
0x180007846  xorps   xmm0, xmm0
0x180007849  mov     cs:?ghStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, 0; SERVICE_STATUS_HANDLE__ * ghStatusHandle
0x180007854  mov     r8d, 19732304h; lpContext
0x18000785a  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 10h; _SERVICE_STATUS gServiceStatus ...
0x180007864  lea     rdx, ?ServiceControl@@YAKKKPEAX0@Z; lpHandlerProc
0x18000786b  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS gServiceStatus ...
0x180007875  lea     rcx, aSens; "SENS"
0x18000787c  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0BB8h; _SERVICE_STATUS gServiceStatus ...
0x180007886  movups  xmmword ptr cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, xmm0; _SERVICE_STATUS gServiceStatus ...
0x18000788d  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180007893  mov     cs:?ghStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * ghStatusHandle
0x18000789a  test    rax, rax
0x18000789d  jz      loc_18000799A
0x1800078a3  lea     rcx, ?gSystemPowerState@@3U_SYSTEM_POWER_STATUS@@A; lpSystemPowerStatus
0x1800078aa  call    cs:__imp_GetSystemPowerStatus
0x1800078b0  lea     rsi, WPP_GLOBAL_Control
0x1800078b7  test    eax, eax
0x1800078b9  jnz     short loc_1800078F8
0x1800078bb  mov     rax, cs:WPP_GLOBAL_Control
0x1800078c2  cmp     rax, rsi
0x1800078c5  jz      short loc_1800078F8
0x1800078c7  test    byte ptr [rax+1Ch], 1
0x1800078cb  jz      short loc_1800078F8
0x1800078cd  cmp     byte ptr [rax+19h], 2
0x1800078d1  jb      short loc_1800078F8
0x1800078d3  call    cs:__imp_GetLastError
0x1800078d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078e0  lea     r8, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids
0x1800078e7  mov     edx, 12h
0x1800078ec  mov     r9d, eax
0x1800078ef  mov     rcx, [rcx+10h]
0x1800078f3  call    WPP_SF_d
0x1800078f8  mov     ecx, 2; unsigned int
0x1800078fd  mov     r8d, 0BB8h; unsigned int
0x180007903  call    ?ReportStatusToSCM@@YAHKKK@Z; ReportStatusToSCM(ulong,ulong,ulong)
0x180007908  test    eax, eax
0x18000790a  jz      loc_18000799A
0x180007910  call    ?ServiceStart@@YAXXZ; ServiceStart(void)
0x180007915  mov     rax, cs:?g_svchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_svchostGlobals
0x18000791c  lea     r9, ?SvchostShutdownCallback@@YAXPEAXE@Z; SvchostShutdownCallback(void *,uchar)
0x180007923  mov     r8, cs:?g_svchostShutdownEvent@@3PEAXEA; void * g_svchostShutdownEvent
0x18000792a  lea     rdx, aSens; "SENS"
0x180007931  mov     [rsp+48h+var_20], 0
0x180007939  lea     rcx, ?g_svchostShutdownWaitHandle@@3PEAXEA; void * g_svchostShutdownWaitHandle
0x180007940  mov     [rsp+48h+var_28], 0
0x180007949  mov     rax, [rax+0C0h]
0x180007950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007955  test    eax, eax
0x180007957  jz      short loc_18000799A
0x180007959  mov     rcx, cs:WPP_GLOBAL_Control
0x180007960  cmp     rcx, rsi
0x180007963  jz      short loc_180007989
0x180007965  test    byte ptr [rcx+1Ch], 1
0x180007969  jz      short loc_180007989
0x18000796b  cmp     byte ptr [rcx+19h], 2
0x18000796f  jb      short loc_180007989
0x180007971  mov     rcx, [rcx+10h]
0x180007975  lea     r8, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids
0x18000797c  mov     edx, 13h
0x180007981  mov     r9d, eax
0x180007984  call    WPP_SF_d
0x180007989  call    ?ServiceStop@@YAXXZ; ServiceStop(void)
0x18000798e  xor     r8d, r8d; unsigned int
0x180007991  lea     ecx, [r8+1]; unsigned int
0x180007995  call    ?ReportStatusToSCM@@YAHKKK@Z; ReportStatusToSCM(ulong,ulong,ulong)
0x18000799a  add     rsp, 40h
0x18000799e  pop     rsi
0x18000799f  retn
```
