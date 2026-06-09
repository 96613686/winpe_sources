# ServiceHandlerEx

- ea: `0x180004940`
- end: `0x180004bb2`
- name: `ServiceHandlerEx`
- size: `626`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004940`
- `0x180006a50`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800049fa`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800049fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004b0e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b6e`

## string_xrefs

- `0x180004ad1`: `SetCurrentServiceStatus fails with error %d`
- `0x180004b77`: `SetCurrentServiceStatus fails with error %d`

## pseudocode

```c
__int64 __fastcall ServiceHandlerEx(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD v5; // edx
  int v6; // ecx
  SERVICE_STATUS_HANDLE *v7; // rcx
  volatile __int32 *v9; // rcx
  DWORD v10; // eax
  DWORD LastError; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-D8h] BYREF
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( dwControl == 4 )
  {
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceInfo,
        L"INTERROGATE received");
    *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
    ServiceStatus.dwWaitHint = 0;
    ServiceStatus.dwServiceType = 32;
    v5 = *(_DWORD *)SstpSvcGlobals;
    ServiceStatus.dwControlsAccepted = *((_DWORD *)SstpSvcGlobals + 1);
    ServiceStatus.dwWin32ExitCode = *((_DWORD *)SstpSvcGlobals + 3);
    ServiceStatus.dwCurrentState = v5;
    if ( v5 <= 7 && (v6 = 146, _bittest(&v6, v5)) )
    {
      _InterlockedExchange((volatile __int32 *)SstpSvcGlobals + 2, 0);
      v7 = (SERVICE_STATUS_HANDLE *)SstpSvcGlobals;
      ServiceStatus.dwWaitHint = 0;
      ServiceStatus.dwCheckPoint = *((_DWORD *)SstpSvcGlobals + 2);
    }
    else
    {
      ServiceStatus.dwWaitHint = 2000;
      ServiceStatus.dwCheckPoint = _InterlockedIncrement((volatile signed __int32 *)SstpSvcGlobals + 2);
      v7 = (SERVICE_STATUS_HANDLE *)SstpSvcGlobals;
    }
    if ( !SetServiceStatus(v7[5], &ServiceStatus) && (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v13) = 0;
      LastError = GetLastError();
      FormatRRASErrorString(&v13, L"SetCurrentServiceStatus fails with error %d", LastError);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v13);
    }
    return 0;
  }
  if ( dwControl == 1 || dwControl == 5 )
  {
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceInfo,
        L"STOP or Shutdown request received");
    v9 = (volatile __int32 *)SstpSvcGlobals;
    *(_QWORD *)SstpSvcGlobals = 3;
    _InterlockedExchange(v9 + 2, 0);
    if ( !(unsigned int)SetCurrentServiceStatus() && (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v13) = 0;
      v10 = GetLastError();
      FormatRRASErrorString(&v13, L"SetCurrentServiceStatus fails with error %d", v10);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v13);
    }
    SetEvent(*((HANDLE *)SstpSvcGlobals + 3));
    return 0;
  }
  if ( (byte_18002D803 & 8) != 0 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"Received Control code (%d) - NOT PROCESSED", dwControl);
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v13);
  }
  return 120;
}

```

## disassembly

```asm
0x180004940  push    rbp
0x180004942  push    rbx
0x180004943  push    rsi
0x180004944  push    rdi
0x180004945  lea     rbp, [rsp-768h]
0x18000494d  sub     rsp, 868h
0x180004954  mov     rax, cs:__security_cookie
0x18000495b  xor     rax, rsp
0x18000495e  mov     [rbp+780h+var_30], rax
0x180004965  mov     edi, ecx
0x180004967  xor     esi, esi
0x180004969  lea     rcx, [rsp+880h+var_82C]; void *
0x18000496e  mov     [rsp+880h+var_830], esi
0x180004972  xor     edx, edx; Val
0x180004974  mov     r8d, 7FCh; Size
0x18000497a  mov     ebx, esi
0x18000497c  call    memset_0
0x180004981  cmp     edi, 4
0x180004984  jnz     loc_180004A25
0x18000498a  test    cs:byte_18002D803, 10h
0x180004991  jnz     loc_180004B19
0x180004997  mov     rax, cs:SstpSvcGlobals
0x18000499e  mov     qword ptr [rsp+880h+ServiceStatus.dwServiceSpecificExitCode], rsi
0x1800049a3  mov     [rsp+880h+ServiceStatus.dwWaitHint], esi
0x1800049a7  mov     [rsp+880h+ServiceStatus.dwServiceType], 20h ; ' '
0x1800049af  mov     ecx, [rax+4]
0x1800049b2  mov     edx, [rax]
0x1800049b4  mov     [rsp+880h+ServiceStatus.dwControlsAccepted], ecx
0x1800049b8  mov     ecx, [rax+0Ch]
0x1800049bb  mov     [rsp+880h+ServiceStatus.dwWin32ExitCode], ecx
0x1800049bf  mov     [rsp+880h+ServiceStatus.dwCurrentState], edx
0x1800049c3  cmp     edx, 7
0x1800049c6  ja      loc_180004B38
0x1800049cc  mov     ecx, 92h
0x1800049d1  bt      ecx, edx
0x1800049d4  jnb     loc_180004B38
0x1800049da  mov     ecx, esi
0x1800049dc  xchg    ecx, [rax+8]
0x1800049df  mov     rcx, cs:SstpSvcGlobals
0x1800049e6  mov     [rsp+880h+ServiceStatus.dwWaitHint], esi
0x1800049ea  mov     eax, [rcx+8]
0x1800049ed  mov     [rsp+880h+ServiceStatus.dwCheckPoint], eax
0x1800049f1  mov     rcx, [rcx+28h]; hServiceStatus
0x1800049f5  lea     rdx, [rsp+880h+ServiceStatus]; lpServiceStatus
0x1800049fa  call    cs:__imp_SetServiceStatus
0x180004a00  test    eax, eax
0x180004a02  jz      loc_180004B5C
0x180004a08  mov     eax, ebx
0x180004a0a  mov     rcx, [rbp+780h+var_30]
0x180004a11  xor     rcx, rsp; StackCookie
0x180004a14  call    __security_check_cookie
0x180004a19  add     rsp, 868h
0x180004a20  pop     rdi
0x180004a21  pop     rsi
0x180004a22  pop     rbx
0x180004a23  pop     rbp
0x180004a24  retn
0x180004a25  mov     eax, edi
0x180004a27  sub     eax, 1
0x180004a2a  jz      short loc_180004A7B
0x180004a2c  cmp     eax, 4
0x180004a2f  jz      short loc_180004A7B
0x180004a31  test    cs:byte_18002D803, 8
0x180004a38  jz      short loc_180004A74
0x180004a3a  mov     r8d, edi
0x180004a3d  mov     word ptr [rsp+880h+var_830], si
0x180004a42  lea     rdx, aReceivedContro; "Received Control code (%d) - NOT PROCES"...
0x180004a49  lea     rcx, [rsp+880h+var_830]
0x180004a4e  call    FormatRRASErrorString
0x180004a53  test    cs:byte_18002D803, 8
0x180004a5a  jz      short loc_180004A74
0x180004a5c  lea     r8, [rsp+880h+var_830]
0x180004a61  lea     rdx, RasSSTPSvcTraceError
0x180004a68  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004a6f  call    McTemplateU0z_EventWriteTransfer
0x180004a74  mov     eax, 78h ; 'x'
0x180004a79  jmp     short loc_180004A0A
0x180004a7b  test    cs:byte_18002D803, 10h
0x180004a82  jz      short loc_180004A9E
0x180004a84  lea     r8, aStopOrShutdown; "STOP or Shutdown request received"
0x180004a8b  lea     rdx, RasSSTPSvcTraceInfo
0x180004a92  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004a99  call    McTemplateU0z_EventWriteTransfer
0x180004a9e  mov     rcx, cs:SstpSvcGlobals
0x180004aa5  mov     eax, esi
0x180004aa7  mov     qword ptr [rcx], 3
0x180004aae  xchg    eax, [rcx+8]
0x180004ab1  call    SetCurrentServiceStatus
0x180004ab6  test    eax, eax
0x180004ab8  jnz     short loc_180004B03
0x180004aba  test    cs:byte_18002D803, 8
0x180004ac1  jz      short loc_180004B03
0x180004ac3  mov     word ptr [rsp+880h+var_830], si
0x180004ac8  call    cs:__imp_GetLastError
0x180004ace  mov     r8d, eax
0x180004ad1  lea     rdx, aSetcurrentserv; "SetCurrentServiceStatus fails with erro"...
0x180004ad8  lea     rcx, [rsp+880h+var_830]
0x180004add  call    FormatRRASErrorString
0x180004ae2  test    cs:byte_18002D803, 8
0x180004ae9  jz      short loc_180004B03
0x180004aeb  lea     r8, [rsp+880h+var_830]
0x180004af0  lea     rdx, RasSSTPSvcTraceError
0x180004af7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004afe  call    McTemplateU0z_EventWriteTransfer
0x180004b03  mov     rcx, cs:SstpSvcGlobals
0x180004b0a  mov     rcx, [rcx+18h]; hEvent
0x180004b0e  call    cs:__imp_SetEvent
0x180004b14  jmp     loc_180004A08
0x180004b19  lea     r8, aInterrogateRec; "INTERROGATE received"
0x180004b20  lea     rdx, RasSSTPSvcTraceInfo
0x180004b27  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004b2e  call    McTemplateU0z_EventWriteTransfer
0x180004b33  jmp     loc_180004997
0x180004b38  mov     ecx, 1
0x180004b3d  lock xadd [rax+8], ecx
0x180004b42  inc     ecx
0x180004b44  mov     [rsp+880h+ServiceStatus.dwWaitHint], 7D0h
0x180004b4c  mov     [rsp+880h+ServiceStatus.dwCheckPoint], ecx
0x180004b50  mov     rcx, cs:SstpSvcGlobals
0x180004b57  jmp     loc_1800049F1
0x180004b5c  test    cs:byte_18002D803, 8
0x180004b63  jz      loc_180004A08
0x180004b69  mov     word ptr [rsp+880h+var_830], si
0x180004b6e  call    cs:__imp_GetLastError
0x180004b74  mov     r8d, eax
0x180004b77  lea     rdx, aSetcurrentserv; "SetCurrentServiceStatus fails with erro"...
0x180004b7e  lea     rcx, [rsp+880h+var_830]
0x180004b83  call    FormatRRASErrorString
0x180004b88  test    cs:byte_18002D803, 8
0x180004b8f  jz      loc_180004A08
0x180004b95  lea     r8, [rsp+880h+var_830]
0x180004b9a  lea     rdx, RasSSTPSvcTraceError
0x180004ba1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004ba8  call    McTemplateU0z_EventWriteTransfer
0x180004bad  jmp     loc_180004A08
```
