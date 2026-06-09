# ServiceHandlerEx

- ea: `0x180004d10`
- end: `0x180004f9b`
- name: `ServiceHandlerEx`
- size: `651`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004d10`
- `0x180007110`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004dca`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004dca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004eeb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004eeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f51`

## string_xrefs

- `0x180004eae`: `SetCurrentServiceStatus fails with error %d`
- `0x180004f60`: `SetCurrentServiceStatus fails with error %d`

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
    if ( (byte_18002E903 & 0x10) != 0 )
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
    if ( !SetServiceStatus(v7[5], &ServiceStatus) && (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v13) = 0;
      LastError = GetLastError();
      FormatRRASErrorString(&v13, L"SetCurrentServiceStatus fails with error %d", LastError);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v13);
    }
    return 0;
  }
  if ( dwControl == 1 || dwControl == 5 )
  {
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceInfo,
        L"STOP or Shutdown request received");
    v9 = (volatile __int32 *)SstpSvcGlobals;
    *(_QWORD *)SstpSvcGlobals = 3;
    _InterlockedExchange(v9 + 2, 0);
    if ( !(unsigned int)SetCurrentServiceStatus() && (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v13) = 0;
      v10 = GetLastError();
      FormatRRASErrorString(&v13, L"SetCurrentServiceStatus fails with error %d", v10);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v13);
    }
    SetEvent(*((HANDLE *)SstpSvcGlobals + 3));
    return 0;
  }
  if ( (byte_18002E903 & 8) != 0 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"Received Control code (%d) - NOT PROCESSED", dwControl);
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v13);
  }
  return 120;
}

```

## disassembly

```asm
0x180004d10  push    rbp
0x180004d12  push    rbx
0x180004d13  push    rsi
0x180004d14  push    rdi
0x180004d15  lea     rbp, [rsp-768h]
0x180004d1d  sub     rsp, 868h
0x180004d24  mov     rax, cs:__security_cookie
0x180004d2b  xor     rax, rsp
0x180004d2e  mov     [rbp+780h+var_30], rax
0x180004d35  mov     edi, ecx
0x180004d37  xor     esi, esi
0x180004d39  lea     rcx, [rsp+880h+var_82C]; void *
0x180004d3e  mov     [rsp+880h+var_830], esi
0x180004d42  xor     edx, edx; Val
0x180004d44  mov     r8d, 7FCh; Size
0x180004d4a  mov     ebx, esi
0x180004d4c  call    memset_0
0x180004d51  cmp     edi, 4
0x180004d54  jnz     loc_180004DFC
0x180004d5a  test    cs:byte_18002E903, 10h
0x180004d61  jnz     loc_180004EFC
0x180004d67  mov     rax, cs:SstpSvcGlobals
0x180004d6e  mov     qword ptr [rsp+880h+ServiceStatus.dwServiceSpecificExitCode], rsi
0x180004d73  mov     [rsp+880h+ServiceStatus.dwWaitHint], esi
0x180004d77  mov     [rsp+880h+ServiceStatus.dwServiceType], 20h ; ' '
0x180004d7f  mov     ecx, [rax+4]
0x180004d82  mov     edx, [rax]
0x180004d84  mov     [rsp+880h+ServiceStatus.dwControlsAccepted], ecx
0x180004d88  mov     ecx, [rax+0Ch]
0x180004d8b  mov     [rsp+880h+ServiceStatus.dwWin32ExitCode], ecx
0x180004d8f  mov     [rsp+880h+ServiceStatus.dwCurrentState], edx
0x180004d93  cmp     edx, 7
0x180004d96  ja      loc_180004F1B
0x180004d9c  mov     ecx, 92h
0x180004da1  bt      ecx, edx
0x180004da4  jnb     loc_180004F1B
0x180004daa  mov     ecx, esi
0x180004dac  xchg    ecx, [rax+8]
0x180004daf  mov     rcx, cs:SstpSvcGlobals
0x180004db6  mov     [rsp+880h+ServiceStatus.dwWaitHint], esi
0x180004dba  mov     eax, [rcx+8]
0x180004dbd  mov     [rsp+880h+ServiceStatus.dwCheckPoint], eax
0x180004dc1  mov     rcx, [rcx+28h]; hServiceStatus
0x180004dc5  lea     rdx, [rsp+880h+ServiceStatus]; lpServiceStatus
0x180004dca  call    cs:__imp_SetServiceStatus
0x180004dd1  nop     dword ptr [rax+rax+00h]
0x180004dd6  test    eax, eax
0x180004dd8  jz      loc_180004F3F
0x180004dde  mov     eax, ebx
0x180004de0  mov     rcx, [rbp+780h+var_30]
0x180004de7  xor     rcx, rsp; StackCookie
0x180004dea  call    __security_check_cookie
0x180004def  add     rsp, 868h
0x180004df6  pop     rdi
0x180004df7  pop     rsi
0x180004df8  pop     rbx
0x180004df9  pop     rbp
0x180004dfa  retn
0x180004dfc  mov     eax, edi
0x180004dfe  sub     eax, 1
0x180004e01  jz      short loc_180004E52
0x180004e03  cmp     eax, 4
0x180004e06  jz      short loc_180004E52
0x180004e08  test    cs:byte_18002E903, 8
0x180004e0f  jz      short loc_180004E4B
0x180004e11  mov     r8d, edi
0x180004e14  mov     word ptr [rsp+880h+var_830], si
0x180004e19  lea     rdx, aReceivedContro; "Received Control code (%d) - NOT PROCES"...
0x180004e20  lea     rcx, [rsp+880h+var_830]
0x180004e25  call    FormatRRASErrorString
0x180004e2a  test    cs:byte_18002E903, 8
0x180004e31  jz      short loc_180004E4B
0x180004e33  lea     r8, [rsp+880h+var_830]
0x180004e38  lea     rdx, RasSSTPSvcTraceError
0x180004e3f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004e46  call    McTemplateU0z_EventWriteTransfer
0x180004e4b  mov     eax, 78h ; 'x'
0x180004e50  jmp     short loc_180004DE0
0x180004e52  test    cs:byte_18002E903, 10h
0x180004e59  jz      short loc_180004E75
0x180004e5b  lea     r8, aStopOrShutdown; "STOP or Shutdown request received"
0x180004e62  lea     rdx, RasSSTPSvcTraceInfo
0x180004e69  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004e70  call    McTemplateU0z_EventWriteTransfer
0x180004e75  mov     rcx, cs:SstpSvcGlobals
0x180004e7c  mov     eax, esi
0x180004e7e  mov     qword ptr [rcx], 3
0x180004e85  xchg    eax, [rcx+8]
0x180004e88  call    SetCurrentServiceStatus
0x180004e8d  test    eax, eax
0x180004e8f  jnz     short loc_180004EE0
0x180004e91  test    cs:byte_18002E903, 8
0x180004e98  jz      short loc_180004EE0
0x180004e9a  mov     word ptr [rsp+880h+var_830], si
0x180004e9f  call    cs:__imp_GetLastError
0x180004ea6  nop     dword ptr [rax+rax+00h]
0x180004eab  mov     r8d, eax
0x180004eae  lea     rdx, aSetcurrentserv; "SetCurrentServiceStatus fails with erro"...
0x180004eb5  lea     rcx, [rsp+880h+var_830]
0x180004eba  call    FormatRRASErrorString
0x180004ebf  test    cs:byte_18002E903, 8
0x180004ec6  jz      short loc_180004EE0
0x180004ec8  lea     r8, [rsp+880h+var_830]
0x180004ecd  lea     rdx, RasSSTPSvcTraceError
0x180004ed4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004edb  call    McTemplateU0z_EventWriteTransfer
0x180004ee0  mov     rcx, cs:SstpSvcGlobals
0x180004ee7  mov     rcx, [rcx+18h]; hEvent
0x180004eeb  call    cs:__imp_SetEvent
0x180004ef2  nop     dword ptr [rax+rax+00h]
0x180004ef7  jmp     loc_180004DDE
0x180004efc  lea     r8, aInterrogateRec; "INTERROGATE received"
0x180004f03  lea     rdx, RasSSTPSvcTraceInfo
0x180004f0a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004f11  call    McTemplateU0z_EventWriteTransfer
0x180004f16  jmp     loc_180004D67
0x180004f1b  mov     ecx, 1
0x180004f20  lock xadd [rax+8], ecx
0x180004f25  inc     ecx
0x180004f27  mov     [rsp+880h+ServiceStatus.dwWaitHint], 7D0h
0x180004f2f  mov     [rsp+880h+ServiceStatus.dwCheckPoint], ecx
0x180004f33  mov     rcx, cs:SstpSvcGlobals
0x180004f3a  jmp     loc_180004DC1
0x180004f3f  test    cs:byte_18002E903, 8
0x180004f46  jz      loc_180004DDE
0x180004f4c  mov     word ptr [rsp+880h+var_830], si
0x180004f51  call    cs:__imp_GetLastError
0x180004f58  nop     dword ptr [rax+rax+00h]
0x180004f5d  mov     r8d, eax
0x180004f60  lea     rdx, aSetcurrentserv; "SetCurrentServiceStatus fails with erro"...
0x180004f67  lea     rcx, [rsp+880h+var_830]
0x180004f6c  call    FormatRRASErrorString
0x180004f71  test    cs:byte_18002E903, 8
0x180004f78  jz      loc_180004DDE
0x180004f7e  lea     r8, [rsp+880h+var_830]
0x180004f83  lea     rdx, RasSSTPSvcTraceError
0x180004f8a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004f91  call    McTemplateU0z_EventWriteTransfer
0x180004f96  jmp     loc_180004DDE
```
