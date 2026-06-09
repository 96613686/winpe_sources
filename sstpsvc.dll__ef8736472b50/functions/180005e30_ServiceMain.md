# ServiceMain

- ea: `0x180005e30`
- end: `0x180006283`
- name: `ServiceMain`
- size: `1107`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800056e0`
- `0x180005e30`
- `0x1800067b4`
- `0x180006960`
- `0x180006b50`
- `0x180006c24`
- `0x1800079d4`
- `0x1800089dc`
- `0x180008b90`
- `0x18000bd24`
- `0x180014484`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005fd9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006166`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005fd9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006166`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005f42`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005f42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800060e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800060e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005edb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005edb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ef5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ef5`
- `sstpcfg!GetSstpProxyConfig` at `0x180006027`
- `sstpcfg!GetSstpProxyConfig` at `0x180006027`

## string_xrefs

- `0x180005e9b`: `ServiceMain`
- `0x180005f84`: `RegisterServiceCtrlHandlerEx fails with 0x%x (%d)`
- `0x18000605d`: `ServiceMain: InitializeSstpServer failed with error %d`
- `0x180006093`: `ServiceMain failed to load proxy config from xml. LoadSstpProxyConfigFromXmlFile failed with error %d`
- `0x18000610d`: `ServiceMain failed to initialize RPC server`
- `0x1800061de`: `ServiceMain failed to retrieve the svchost RegisterStopCallback`
- `0x1800061cc`: `ServiceMain failed to register stop callback`
- `0x180006219`: `ServiceMain fails with 0x%x (%d)`

## pseudocode

```c
__int64 ServiceMain()
{
  unsigned int v0; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v2; // rax
  const wchar_t *v3; // r8
  SERVICE_STATUS_HANDLE v4; // rax
  LPVOID v5; // rcx
  DWORD LastError; // eax
  int v7; // ebx
  unsigned int v8; // eax
  unsigned int SstpProxyConfigFromXmlFile; // eax
  RTL_SRWLOCK *v10; // rcx
  LPVOID v11; // rcx
  __int64 (__fastcall *v12)(char *, const WCHAR *, _QWORD, __int64 (__fastcall *)(_QWORD, _QWORD), _QWORD, int); // rax
  __int64 result; // rax
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v14 = 0;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( (int)McGenEventRegister_EventRegister() >= 0 )
    SetLibParams();
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v16) = 0;
    FormatRRASErrorString(&v16, L"Entering %ws", L"ServiceMain");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v16);
  }
  v0 = 0;
  ProcessHeap = GetProcessHeap();
  v2 = HeapAlloc(ProcessHeap, 8u, 0x310u);
  SstpSvcGlobals = v2;
  if ( !v2 )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_38;
    v3 = L"Unable to allocate memory for SstpSvcGlobals";
    goto LABEL_37;
  }
  v2[94] = -1;
  v4 = RegisterServiceCtrlHandlerExW(L"sstpsvc", ServiceHandlerEx, 0);
  v5 = SstpSvcGlobals;
  *((_QWORD *)SstpSvcGlobals + 5) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_38;
    LOWORD(v16) = 0;
    FormatRRASErrorString(&v16, L"RegisterServiceCtrlHandlerEx fails with 0x%x (%d)", LastError, LastError);
LABEL_12:
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_38;
    v3 = (const wchar_t *)&v16;
    goto LABEL_37;
  }
  ServiceStatus.dwServiceType = 32;
  *(_DWORD *)v5 = 2;
  ServiceStatus.dwCheckPoint = 1;
  ServiceStatus.dwWaitHint = 3000;
  ServiceStatus.dwCurrentState = *(_DWORD *)v5;
  SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v5 + 5), &ServiceStatus);
  if ( (unsigned int)ConfigureMiniports(16, 5, (char *)SstpSvcGlobals + 296, (char *)SstpSvcGlobals + 304) )
    goto LABEL_38;
  v0 = InitializeService();
  if ( v0 )
    goto LABEL_38;
  GetSstpProxyConfig(0, &v14);
  v7 = v14;
  if ( v14 )
  {
    v8 = InitializeSstpServer(0);
    v0 = v8;
    if ( v8 )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_38;
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"ServiceMain: InitializeSstpServer failed with error %d", v8);
      goto LABEL_12;
    }
    SstpProxyConfigFromXmlFile = LoadSstpProxyConfigFromXmlFile();
    v0 = SstpProxyConfigFromXmlFile;
    if ( SstpProxyConfigFromXmlFile )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_38;
      LOWORD(v16) = 0;
      FormatRRASErrorString(
        &v16,
        L"ServiceMain failed to load proxy config from xml. LoadSstpProxyConfigFromXmlFile failed with error %d",
        SstpProxyConfigFromXmlFile);
      goto LABEL_12;
    }
    v7 = v14;
  }
  AcquireSRWLockExclusive((PSRWLOCK)SstpSvcGlobals + 96);
  v10 = (RTL_SRWLOCK *)SstpSvcGlobals;
  if ( v7 )
    *((_DWORD *)SstpSvcGlobals + 194) |= 1u;
  else
    *((_DWORD *)SstpSvcGlobals + 194) &= ~1u;
  ReleaseSRWLockExclusive(v10 + 96);
  v0 = InitializeSstpSvcRpcServer();
  if ( v0 )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_38;
    v3 = L"ServiceMain failed to initialize RPC server";
    goto LABEL_37;
  }
  v11 = SstpSvcGlobals;
  *((_DWORD *)SstpSvcGlobals + 1) = 5;
  *((_DWORD *)v11 + 190) = 1;
  *(_DWORD *)v11 = 4;
  ServiceStatus.dwCurrentState = 4;
  ServiceStatus.dwControlsAccepted = *((_DWORD *)v11 + 1);
  _InterlockedExchange((volatile __int32 *)v11 + 2, 0);
  ServiceStatus.dwCheckPoint = *((_DWORD *)SstpSvcGlobals + 2);
  ServiceStatus.dwWaitHint = 0;
  SetServiceStatus(*((SERVICE_STATUS_HANDLE *)SstpSvcGlobals + 5), &ServiceStatus);
  if ( !SstpSvchostGlobal
    || (v12 = *(__int64 (__fastcall **)(char *, const WCHAR *, _QWORD, __int64 (__fastcall *)(_QWORD, _QWORD), _QWORD, int))(SstpSvchostGlobal + 192)) == 0 )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_38;
    v3 = L"ServiceMain failed to retrieve the svchost RegisterStopCallback";
    goto LABEL_37;
  }
  result = v12((char *)SstpSvcGlobals + 32, L"sstpsvc", *((_QWORD *)SstpSvcGlobals + 3), StartServiceCleanup, 0, 8);
  v0 = result;
  if ( !(_DWORD)result )
    return result;
  if ( (byte_18002E903 & 8) != 0 )
  {
    v3 = L"ServiceMain failed to register stop callback";
LABEL_37:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v3);
  }
LABEL_38:
  if ( SstpSvcGlobals && v0 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"ServiceMain fails with 0x%x (%d)", v0, v0);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v16);
    }
    *((_DWORD *)SstpSvcGlobals + 3) = v0;
  }
  return StartServiceCleanup(0, 0);
}

```

## disassembly

```asm
0x180005e30  mov     [rsp-8+arg_0], rbx
0x180005e35  mov     [rsp-8+arg_8], rdi
0x180005e3a  push    rbp
0x180005e3b  lea     rbp, [rsp-780h]
0x180005e43  sub     rsp, 880h
0x180005e4a  mov     rax, cs:__security_cookie
0x180005e51  xor     rax, rsp
0x180005e54  mov     [rbp+780h+var_10], rax
0x180005e5b  xorps   xmm0, xmm0
0x180005e5e  lea     rcx, [rsp+880h+var_80C]; void *
0x180005e63  xor     edi, edi
0x180005e65  xor     edx, edx; Val
0x180005e67  movups  xmmword ptr [rsp+880h+ServiceStatus.dwServiceType], xmm0
0x180005e6c  mov     r8d, 7FCh; Size
0x180005e72  mov     [rsp+880h+var_840], edi
0x180005e76  movups  xmmword ptr [rsp+880h+ServiceStatus.dwWin32ExitCode], xmm0
0x180005e7b  mov     [rsp+880h+var_810], edi
0x180005e7f  call    memset_0
0x180005e84  call    McGenEventRegister_EventRegister
0x180005e89  test    eax, eax
0x180005e8b  js      short loc_180005E92
0x180005e8d  call    SetLibParams
0x180005e92  test    cs:byte_18002E903, 10h
0x180005e99  jz      short loc_180005ED9
0x180005e9b  lea     r8, aServicemain_0; "ServiceMain"
0x180005ea2  mov     word ptr [rsp+880h+var_810], di
0x180005ea7  lea     rdx, aEnteringWs; "Entering %ws"
0x180005eae  lea     rcx, [rsp+880h+var_810]
0x180005eb3  call    FormatRRASErrorString
0x180005eb8  test    cs:byte_18002E903, 10h
0x180005ebf  jz      short loc_180005ED9
0x180005ec1  lea     r8, [rsp+880h+var_810]
0x180005ec6  lea     rdx, RasSSTPSvcTraceInfo
0x180005ecd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005ed4  call    McTemplateU0z_EventWriteTransfer
0x180005ed9  mov     ebx, edi
0x180005edb  call    cs:__imp_GetProcessHeap
0x180005ee2  nop     dword ptr [rax+rax+00h]
0x180005ee7  mov     edx, 8; dwFlags
0x180005eec  mov     r8d, 310h; dwBytes
0x180005ef2  mov     rcx, rax; hHeap
0x180005ef5  call    cs:__imp_HeapAlloc
0x180005efc  nop     dword ptr [rax+rax+00h]
0x180005f01  mov     cs:SstpSvcGlobals, rax
0x180005f08  test    rax, rax
0x180005f0b  jnz     short loc_180005F26
0x180005f0d  test    cs:byte_18002E903, 8
0x180005f14  jz      loc_1800061F8
0x180005f1a  lea     r8, aUnableToAlloca_1; "Unable to allocate memory for SstpSvcGl"...
0x180005f21  jmp     loc_1800061E5
0x180005f26  xor     r8d, r8d; lpContext
0x180005f29  mov     qword ptr [rax+2F0h], 0FFFFFFFFFFFFFFFFh
0x180005f34  lea     rdx, ServiceHandlerEx; lpHandlerProc
0x180005f3b  lea     rcx, ServiceName; "sstpsvc"
0x180005f42  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180005f49  nop     dword ptr [rax+rax+00h]
0x180005f4e  mov     rcx, cs:SstpSvcGlobals
0x180005f55  mov     [rcx+28h], rax
0x180005f59  test    rax, rax
0x180005f5c  jnz     short loc_180005FAC
0x180005f5e  call    cs:__imp_GetLastError
0x180005f65  nop     dword ptr [rax+rax+00h]
0x180005f6a  test    cs:byte_18002E903, 8
0x180005f71  mov     ebx, eax
0x180005f73  jz      loc_1800061F8
0x180005f79  mov     r9d, eax
0x180005f7c  mov     word ptr [rsp+880h+var_810], di
0x180005f81  mov     r8d, eax
0x180005f84  lea     rdx, aRegisterservic; "RegisterServiceCtrlHandlerEx fails with"...
0x180005f8b  lea     rcx, [rsp+880h+var_810]
0x180005f90  call    FormatRRASErrorString
0x180005f95  test    cs:byte_18002E903, 8
0x180005f9c  jz      loc_1800061F8
0x180005fa2  lea     r8, [rsp+880h+var_810]
0x180005fa7  jmp     loc_1800061E5
0x180005fac  mov     [rsp+880h+ServiceStatus.dwServiceType], 20h ; ' '
0x180005fb4  lea     rdx, [rsp+880h+ServiceStatus]; lpServiceStatus
0x180005fb9  mov     dword ptr [rcx], 2
0x180005fbf  mov     [rsp+880h+ServiceStatus.dwCheckPoint], 1
0x180005fc7  mov     [rsp+880h+ServiceStatus.dwWaitHint], 0BB8h
0x180005fcf  mov     eax, [rcx]
0x180005fd1  mov     [rsp+880h+ServiceStatus.dwCurrentState], eax
0x180005fd5  mov     rcx, [rcx+28h]; hServiceStatus
0x180005fd9  call    cs:__imp_SetServiceStatus
0x180005fe0  nop     dword ptr [rax+rax+00h]
0x180005fe5  mov     r8, cs:SstpSvcGlobals
0x180005fec  mov     edx, 5
0x180005ff1  mov     ecx, 10h
0x180005ff6  lea     r9, [r8+130h]
0x180005ffd  add     r8, 128h
0x180006004  call    ConfigureMiniports
0x180006009  test    eax, eax
0x18000600b  jnz     loc_1800061F8
0x180006011  call    InitializeService
0x180006016  mov     ebx, eax
0x180006018  test    eax, eax
0x18000601a  jnz     loc_1800061F8
0x180006020  lea     rdx, [rsp+880h+var_840]
0x180006025  xor     ecx, ecx
0x180006027  call    cs:__imp_GetSstpProxyConfig
0x18000602e  nop     dword ptr [rax+rax+00h]
0x180006033  mov     ebx, [rsp+880h+var_840]
0x180006037  test    ebx, ebx
0x180006039  jz      short loc_1800060AD
0x18000603b  xor     ecx, ecx
0x18000603d  call    InitializeSstpServer
0x180006042  mov     ebx, eax
0x180006044  test    eax, eax
0x180006046  jz      short loc_180006073
0x180006048  test    cs:byte_18002E903, 8
0x18000604f  jz      loc_1800061F8
0x180006055  mov     r8d, eax
0x180006058  mov     word ptr [rsp+880h+var_810], di
0x18000605d  lea     rdx, aServicemainIni; "ServiceMain: InitializeSstpServer faile"...
0x180006064  lea     rcx, [rsp+880h+var_810]
0x180006069  call    FormatRRASErrorString
0x18000606e  jmp     loc_180005F95
0x180006073  call    LoadSstpProxyConfigFromXmlFile
0x180006078  mov     ebx, eax
0x18000607a  test    eax, eax
0x18000607c  jz      short loc_1800060A9
0x18000607e  test    cs:byte_18002E903, 8
0x180006085  jz      loc_1800061F8
0x18000608b  mov     r8d, eax
0x18000608e  mov     word ptr [rsp+880h+var_810], di
0x180006093  lea     rdx, aServicemainFai_0; "ServiceMain failed to load proxy config"...
0x18000609a  lea     rcx, [rsp+880h+var_810]
0x18000609f  call    FormatRRASErrorString
0x1800060a4  jmp     loc_180005F95
0x1800060a9  mov     ebx, [rsp+880h+var_840]
0x1800060ad  mov     rcx, cs:SstpSvcGlobals
0x1800060b4  add     rcx, 300h; SRWLock
0x1800060bb  call    cs:__imp_AcquireSRWLockExclusive
0x1800060c2  nop     dword ptr [rax+rax+00h]
0x1800060c7  mov     rcx, cs:SstpSvcGlobals
0x1800060ce  test    ebx, ebx
0x1800060d0  jz      short loc_1800060DB
0x1800060d2  or      dword ptr [rcx+308h], 1
0x1800060d9  jmp     short loc_1800060E2
0x1800060db  and     dword ptr [rcx+308h], 0FFFFFFFEh
0x1800060e2  add     rcx, 300h; SRWLock
0x1800060e9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800060f0  nop     dword ptr [rax+rax+00h]
0x1800060f5  call    InitializeSstpSvcRpcServer
0x1800060fa  mov     ebx, eax
0x1800060fc  test    eax, eax
0x1800060fe  jz      short loc_180006119
0x180006100  test    cs:byte_18002E903, 8
0x180006107  jz      loc_1800061F8
0x18000610d  lea     r8, aServicemainFai_3; "ServiceMain failed to initialize RPC se"...
0x180006114  jmp     loc_1800061E5
0x180006119  mov     rcx, cs:SstpSvcGlobals
0x180006120  lea     rdx, [rsp+880h+ServiceStatus]; lpServiceStatus
0x180006125  mov     dword ptr [rcx+4], 5
0x18000612c  mov     dword ptr [rcx+2F8h], 1
0x180006136  mov     dword ptr [rcx], 4
0x18000613c  mov     [rsp+880h+ServiceStatus.dwCurrentState], 4
0x180006144  mov     eax, [rcx+4]
0x180006147  mov     [rsp+880h+ServiceStatus.dwControlsAccepted], eax
0x18000614b  mov     eax, edi
0x18000614d  xchg    eax, [rcx+8]
0x180006150  mov     rcx, cs:SstpSvcGlobals
0x180006157  mov     eax, [rcx+8]
0x18000615a  mov     [rsp+880h+ServiceStatus.dwCheckPoint], eax
0x18000615e  mov     [rsp+880h+ServiceStatus.dwWaitHint], edi
0x180006162  mov     rcx, [rcx+28h]; hServiceStatus
0x180006166  call    cs:__imp_SetServiceStatus
0x18000616d  nop     dword ptr [rax+rax+00h]
0x180006172  mov     rax, cs:SstpSvchostGlobal
0x180006179  test    rax, rax
0x18000617c  jz      short loc_1800061D5
0x18000617e  mov     rax, [rax+0C0h]
0x180006185  test    rax, rax
0x180006188  jz      short loc_1800061D5
0x18000618a  mov     r8, cs:SstpSvcGlobals
0x180006191  lea     r9, StartServiceCleanup
0x180006198  mov     [rsp+880h+var_858], 8
0x1800061a0  lea     rdx, ServiceName; "sstpsvc"
0x1800061a7  mov     [rsp+880h+var_860], rdi
0x1800061ac  lea     rcx, [r8+20h]
0x1800061b0  mov     r8, [r8+18h]
0x1800061b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b9  mov     ebx, eax
0x1800061bb  test    eax, eax
0x1800061bd  jz      loc_18000625E
0x1800061c3  test    cs:byte_18002E903, 8
0x1800061ca  jz      short loc_1800061F8
0x1800061cc  lea     r8, aServicemainFai_2; "ServiceMain failed to register stop cal"...
0x1800061d3  jmp     short loc_1800061E5
0x1800061d5  test    cs:byte_18002E903, 8
0x1800061dc  jz      short loc_1800061F8
0x1800061de  lea     r8, aServicemainFai; "ServiceMain failed to retrieve the svch"...
0x1800061e5  lea     rdx, RasSSTPSvcTraceError
0x1800061ec  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800061f3  call    McTemplateU0z_EventWriteTransfer
0x1800061f8  cmp     cs:SstpSvcGlobals, rdi
0x1800061ff  jz      short loc_180006255
0x180006201  test    ebx, ebx
0x180006203  jz      short loc_180006255
0x180006205  test    cs:byte_18002E903, 8
0x18000620c  jz      short loc_18000624B
0x18000620e  mov     r9d, ebx
0x180006211  mov     word ptr [rsp+880h+var_810], di
0x180006216  mov     r8d, ebx
0x180006219  lea     rdx, aServicemainFai_1; "ServiceMain fails with 0x%x (%d)"
0x180006220  lea     rcx, [rsp+880h+var_810]
0x180006225  call    FormatRRASErrorString
0x18000622a  test    cs:byte_18002E903, 8
0x180006231  jz      short loc_18000624B
0x180006233  lea     r8, [rsp+880h+var_810]
0x180006238  lea     rdx, RasSSTPSvcTraceError
0x18000623f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006246  call    McTemplateU0z_EventWriteTransfer
0x18000624b  mov     rax, cs:SstpSvcGlobals
0x180006252  mov     [rax+0Ch], ebx
0x180006255  xor     edx, edx
0x180006257  xor     ecx, ecx
0x180006259  call    StartServiceCleanup
0x18000625e  mov     rcx, [rbp+780h+var_10]
0x180006265  xor     rcx, rsp; StackCookie
0x180006268  call    __security_check_cookie
0x18000626d  lea     r11, [rsp+880h+var_s0]
0x180006275  mov     rbx, [r11+10h]
0x180006279  mov     rdi, [r11+18h]
0x18000627d  mov     rsp, r11
0x180006280  pop     rbp
0x180006281  retn
```
