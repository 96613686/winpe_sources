# ServiceMain

- ea: `0x18001d2f0`
- end: `0x18001d8e0`
- name: `ServiceMain`
- size: `1520`
- prototype: `DWORD __fastcall(__int64, LPCWSTR *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008e48`
- `0x18001cb1c`
- `0x18001cf9c`
- `0x18001d024`
- `0x18001d1bc`
- `0x18001d2f0`
- `0x18001d8e8`
- `0x18001d9e0`
- `0x1800202e8`
- `0x180028a9c`
- `0x180028acc`
- `0x180028e10`
- `0x18002fb60`
- `0x180031bc0`
- `0x18003444c`
- `0x180042010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001d57f`
- `ntdll!EtwEventWrite` at `0x18001d7df`
- `ntdll!EtwEventWrite` at `0x18001d57f`
- `ntdll!EtwEventWrite` at `0x18001d7df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d6a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d6a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d5d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d71f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d71f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d86e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d86e`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001d349`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001d41c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001d4d9`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001d349`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001d41c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001d4d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d8d8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d8d8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d42b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d42b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d480`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d480`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001d565`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001d565`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001d67d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001d67d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001d35c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001d35c`

## string_xrefs

- `0x18001d6a0`: `VbsApi.dll`

## pseudocode

```c
DWORD __fastcall ServiceMain(__int64 a1, LPCWSTR *a2)
{
  DWORD result; // eax
  int v4; // esi
  HRESULT v5; // ebx
  CThirdPartyManager *v6; // rcx
  __int64 v7; // rdx
  HRESULT v8; // ebx
  CThirdPartyManager *v9; // rcx
  __int64 v10; // rdx
  unsigned int StartSinceBoot; // ebp
  int v12; // eax
  int v13; // eax
  signed int v14; // ebx
  DWORD LastError; // eax
  bool v16; // sf
  signed int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  DWORD v21; // eax
  bool v22; // sf
  unsigned int v23; // eax
  int v24; // eax
  bool v25; // sf
  int v26; // eax
  LPVOID ppv; // [rsp+98h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
  EventWrite(g_Provider, &WSC_SVC_Start_Begin, 0, 0);
  g_serviceStatusHandle = RegisterServiceCtrlHandlerExW(*a2, ServiceControlHandler, 0);
  if ( !g_serviceStatusHandle )
  {
    result = GetLastError();
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      return WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, result);
    }
    return result;
  }
  v4 = 2;
  v5 = SetWin32ServiceStatus(2u, 0, 0, 0, 0xEA60u);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_13;
    }
    v7 = 24;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, (unsigned int)v5);
LABEL_13:
    SetWin32ServiceStatus(1u, 0, (unsigned __int16)v5, 0, 0);
    return EventWrite(g_Provider, &WSC_SVC_Start_End, 0, 0);
  }
  v5 = CoInitializeEx(0, 0);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_13;
    }
    v7 = 25;
    goto LABEL_12;
  }
  ppv = 0;
  v8 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v10 = 26;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, (unsigned int)v8);
LABEL_23:
    SetWin32ServiceStatus(1u, 0, (unsigned __int16)v8, 0, 0);
    EventWrite(g_Provider, &WSC_SVC_Start_End, 0, 0);
    return ATL::CComPtrBase<IGlobalOptions>::~CComPtrBase<IGlobalOptions>(&ppv);
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v10 = 27;
    goto LABEL_22;
  }
  StartSinceBoot = IsFirstStartSinceBoot();
  v12 = SystemMonitoringInitialize();
  if ( v12 >= 0 )
  {
    v13 = SetWin32ServiceStatus(2u, 0, 0, 1u, 0xEA60u);
    v14 = v13;
    if ( v13 < 0 )
    {
      v4 = 1;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_b798000f0de738f41d9362b18d9c2686_Traceguids,
          (unsigned int)v13);
      }
    }
    else
    {
      g_stopServiceEvent = CreateEventW(0, 0, 0, 0);
      if ( !g_stopServiceEvent )
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, LastError);
        }
        v16 = v14 < 0;
        if ( v14 > 0 )
        {
          v14 = (unsigned __int16)v14 | 0x80070000;
          v16 = v14 < 0;
        }
        if ( !v16 )
          v14 = -2147467259;
      }
    }
    g_serviceStatus.dwCurrentState = 4;
    *(_QWORD *)&g_serviceStatus.dwCheckPoint = 0;
    if ( g_serviceStatusHandle )
    {
      if ( !SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus) )
      {
        v21 = GetLastError();
        v14 = v21;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, v21);
        }
        v22 = v14 < 0;
        if ( v14 > 0 )
        {
          v14 = (unsigned __int16)v14 | 0x80070000;
          v22 = v14 < 0;
        }
        if ( !v22 )
          LOWORD(v14) = 16389;
LABEL_84:
        if ( g_stopServiceEvent )
          CloseHandle(g_stopServiceEvent);
        SystemMonitoringCleanup();
        if ( g_serviceStatusHandle && v4 != 1 )
        {
          while ( 1 )
          {
            v26 = SetWin32ServiceStatus(1u, 0, (unsigned __int16)v14, 0, 0);
            LOWORD(v14) = v26;
            if ( v26 >= 0 )
              break;
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                36,
                WPP_b798000f0de738f41d9362b18d9c2686_Traceguids,
                (unsigned int)v26);
            }
            Sleep(0x1F4u);
          }
        }
        goto LABEL_32;
      }
      v4 = 4;
    }
    if ( v14 >= 0 )
    {
      g_hVbsApi = LoadLibraryExW(L"VbsApi.dll", 0, 0x800u);
      v17 = RegisterSecurityCenterBroker();
      if ( v17 < 0
        && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_b798000f0de738f41d9362b18d9c2686_Traceguids,
          (unsigned int)v17);
      }
      v18 = WscServiceStartup(StartSinceBoot);
      LOWORD(v14) = v18;
      if ( v18 >= 0 )
      {
        VelocityPollerStartup();
        v23 = (*((__int64 (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, _DWORD))g_svcHostGlobalData
               + 24))(
                &g_waitObject,
                *a2,
                g_stopServiceEvent,
                StopService,
                0,
                0);
        v14 = v23;
        if ( v23 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, v23);
          }
          v25 = v14 < 0;
          if ( v14 > 0 )
          {
            v14 = (unsigned __int16)v14 | 0x80070000;
            v25 = v14 < 0;
          }
          if ( !v25 )
            LOWORD(v14) = 16389;
          VelocityPollerExit();
          WscCleanup();
        }
        else
        {
          v24 = SetWin32ServiceStatus(4u, 0x85u, 0, 0, 0);
          v14 = v24;
          if ( v24 < 0 )
          {
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                34,
                WPP_b798000f0de738f41d9362b18d9c2686_Traceguids,
                (unsigned int)v24);
            }
          }
          else
          {
            v4 = 4;
            EtwEventWrite(g_Provider, WSC_SVC_Start_Running, 0, 0);
            SqmRecordStatus();
          }
          if ( v14 >= 0 )
            goto LABEL_32;
        }
      }
      else if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, StartSinceBoot, v18);
      }
    }
    goto LABEL_84;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      WPP_b798000f0de738f41d9362b18d9c2686_Traceguids,
      (unsigned int)v12);
LABEL_32:
  CoUninitialize();
  result = EtwEventWrite(g_Provider, &WSC_SVC_Start_End, 0, 0);
  if ( ppv )
    return (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return result;
}

```

## disassembly

```asm
0x18001d2f0  push    rbx
0x18001d2f2  push    rbp
0x18001d2f3  push    rsi
0x18001d2f4  push    rdi
0x18001d2f5  push    r12
0x18001d2f7  push    r13
0x18001d2f9  push    r14
0x18001d2fb  push    r15
0x18001d2fd  sub     rsp, 48h
0x18001d301  mov     r14, rdx
0x18001d304  lea     r12, WPP_GLOBAL_Control
0x18001d30b  lea     r13, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x18001d312  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d319  cmp     rcx, r12
0x18001d31c  jz      short loc_18001D335
0x18001d31e  test    byte ptr [rcx+1Ch], 4
0x18001d322  jz      short loc_18001D335
0x18001d324  mov     edx, 16h
0x18001d329  mov     r8, r13
0x18001d32c  mov     rcx, [rcx+10h]
0x18001d330  call    WPP_SF_
0x18001d335  xor     r9d, r9d; UserData
0x18001d338  xor     r8d, r8d; UserDataCount
0x18001d33b  lea     rdx, WSC_SVC_Start_Begin; EventDescriptor
0x18001d342  mov     rcx, cs:?g_Provider@@3_KA; RegHandle
0x18001d349  call    cs:__imp_EventWrite
0x18001d34f  xor     r8d, r8d; lpContext
0x18001d352  lea     rdx, ?ServiceControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18001d359  mov     rcx, [r14]; lpServiceName
0x18001d35c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18001d362  mov     cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_serviceStatusHandle
0x18001d369  xor     r15d, r15d
0x18001d36c  test    rax, rax
0x18001d36f  jnz     short loc_18001D3AC
0x18001d371  call    cs:__imp_GetLastError
0x18001d377  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d37e  cmp     rcx, r12
0x18001d381  jz      loc_18001D5A0
0x18001d387  lea     edi, [r15+1]
0x18001d38b  test    [rcx+1Ch], dil
0x18001d38f  jz      loc_18001D5A0
0x18001d395  lea     edx, [rdi+16h]
0x18001d398  mov     r9d, eax
0x18001d39b  mov     r8, r13
0x18001d39e  mov     rcx, [rcx+10h]
0x18001d3a2  call    WPP_SF_d
0x18001d3a7  jmp     loc_18001D5A0
0x18001d3ac  mov     dword ptr [rsp+88h+ppv], 0EA60h; unsigned int
0x18001d3b4  xor     r9d, r9d; unsigned int
0x18001d3b7  xor     r8d, r8d; unsigned int
0x18001d3ba  xor     edx, edx; unsigned int
0x18001d3bc  lea     esi, [rdx+2]
0x18001d3bf  mov     ecx, esi; unsigned int
0x18001d3c1  call    ?SetWin32ServiceStatus@@YAJKKKKK@Z; SetWin32ServiceStatus(ulong,ulong,ulong,ulong,ulong)
0x18001d3c6  mov     ebx, eax
0x18001d3c8  test    eax, eax
0x18001d3ca  jns     short loc_18001D427
0x18001d3cc  lea     edi, [rsi-1]
0x18001d3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3d6  cmp     rcx, r12
0x18001d3d9  jz      short loc_18001D3F3
0x18001d3db  test    [rcx+1Ch], dil
0x18001d3df  jz      short loc_18001D3F3
0x18001d3e1  lea     edx, [rsi+16h]
0x18001d3e4  mov     r9d, ebx
0x18001d3e7  mov     r8, r13
0x18001d3ea  mov     rcx, [rcx+10h]
0x18001d3ee  call    WPP_SF_d
0x18001d3f3  movzx   r8d, bx; unsigned int
0x18001d3f7  mov     dword ptr [rsp+88h+ppv], r15d; unsigned int
0x18001d3fc  xor     r9d, r9d; unsigned int
0x18001d3ff  xor     edx, edx; unsigned int
0x18001d401  mov     ecx, edi; unsigned int
0x18001d403  call    ?SetWin32ServiceStatus@@YAJKKKKK@Z; SetWin32ServiceStatus(ulong,ulong,ulong,ulong,ulong)
0x18001d408  xor     r9d, r9d; UserData
0x18001d40b  xor     r8d, r8d; UserDataCount
0x18001d40e  lea     rdx, WSC_SVC_Start_End; EventDescriptor
0x18001d415  mov     rcx, cs:?g_Provider@@3_KA; RegHandle
0x18001d41c  call    cs:__imp_EventWrite
0x18001d422  jmp     loc_18001D5A0
0x18001d427  xor     edx, edx; dwCoInit
0x18001d429  xor     ecx, ecx; pvReserved
0x18001d42b  call    cs:__imp_CoInitializeEx
0x18001d431  mov     ebx, eax
0x18001d433  test    eax, eax
0x18001d435  jns     short loc_18001D453
0x18001d437  mov     edi, 1
0x18001d43c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d443  cmp     rcx, r12
0x18001d446  jz      short loc_18001D3F3
0x18001d448  test    [rcx+1Ch], dil
0x18001d44c  jz      short loc_18001D3F3
0x18001d44e  lea     edx, [rdi+18h]
0x18001d451  jmp     short loc_18001D3E4
0x18001d453  mov     [rsp+88h+arg_8], r15
0x18001d45b  lea     rax, [rsp+88h+arg_8]
0x18001d463  mov     [rsp+88h+ppv], rax; ppv
0x18001d468  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18001d46f  mov     edi, 1
0x18001d474  mov     r8d, edi; dwClsContext
0x18001d477  xor     edx, edx; pUnkOuter
0x18001d479  lea     rcx, CLSID_GlobalOptions; rclsid
0x18001d480  call    cs:__imp_CoCreateInstance
0x18001d486  mov     ebx, eax
0x18001d488  test    eax, eax
0x18001d48a  jns     short loc_18001D4F1
0x18001d48c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d493  cmp     rcx, r12
0x18001d496  jz      short loc_18001D4B0
0x18001d498  test    [rcx+1Ch], dil
0x18001d49c  jz      short loc_18001D4B0
0x18001d49e  lea     edx, [rdi+19h]
0x18001d4a1  mov     r9d, ebx
0x18001d4a4  mov     r8, r13
0x18001d4a7  mov     rcx, [rcx+10h]
0x18001d4ab  call    WPP_SF_d
0x18001d4b0  movzx   r8d, bx; unsigned int
0x18001d4b4  mov     dword ptr [rsp+88h+ppv], r15d; unsigned int
0x18001d4b9  xor     r9d, r9d; unsigned int
0x18001d4bc  xor     edx, edx; unsigned int
0x18001d4be  mov     ecx, edi; unsigned int
0x18001d4c0  call    ?SetWin32ServiceStatus@@YAJKKKKK@Z; SetWin32ServiceStatus(ulong,ulong,ulong,ulong,ulong)
0x18001d4c5  xor     r9d, r9d; UserData
0x18001d4c8  xor     r8d, r8d; UserDataCount
0x18001d4cb  lea     rdx, WSC_SVC_Start_End; EventDescriptor
0x18001d4d2  mov     rcx, cs:?g_Provider@@3_KA; RegHandle
0x18001d4d9  call    cs:__imp_EventWrite
0x18001d4df  lea     rcx, [rsp+88h+arg_8]
0x18001d4e7  call    ??1?$CComPtrBase@UIGlobalOptions@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IGlobalOptions>::~CComPtrBase<IGlobalOptions>(void)
0x18001d4ec  jmp     loc_18001D5A0
0x18001d4f1  mov     rcx, [rsp+88h+arg_8]
0x18001d4f9  mov     rax, [rcx]
0x18001d4fc  mov     r8, rdi
0x18001d4ff  mov     edx, 5
0x18001d504  mov     rax, [rax+18h]
0x18001d508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d50d  mov     ebx, eax
0x18001d50f  test    eax, eax
0x18001d511  jns     short loc_18001D52F
0x18001d513  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d51a  cmp     rcx, r12
0x18001d51d  jz      short loc_18001D4B0
0x18001d51f  test    [rcx+1Ch], dil
0x18001d523  jz      short loc_18001D4B0
0x18001d525  mov     edx, 1Bh
0x18001d52a  jmp     loc_18001D4A1
0x18001d52f  call    ?IsFirstStartSinceBoot@@YAHXZ; IsFirstStartSinceBoot(void)
0x18001d534  mov     ebp, eax
0x18001d536  call    ?SystemMonitoringInitialize@@YAJXZ; SystemMonitoringInitialize(void)
0x18001d53b  test    eax, eax
0x18001d53d  jns     short loc_18001D5B1
0x18001d53f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d546  cmp     rcx, r12
0x18001d549  jz      short loc_18001D565
0x18001d54b  test    [rcx+1Ch], dil
0x18001d54f  jz      short loc_18001D565
0x18001d551  mov     edx, 1Ch
0x18001d556  mov     r9d, eax
0x18001d559  mov     r8, r13
0x18001d55c  mov     rcx, [rcx+10h]
0x18001d560  call    WPP_SF_d
0x18001d565  call    cs:__imp_CoUninitialize
0x18001d56b  xor     r9d, r9d
0x18001d56e  xor     r8d, r8d
0x18001d571  lea     rdx, WSC_SVC_Start_End
0x18001d578  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x18001d57f  call    cs:__imp_EtwEventWrite
0x18001d585  nop
0x18001d586  mov     rcx, [rsp+88h+arg_8]
0x18001d58e  test    rcx, rcx
0x18001d591  jz      short loc_18001D5A0
0x18001d593  mov     rax, [rcx]
0x18001d596  mov     rax, [rax+10h]
0x18001d59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d59f  nop
0x18001d5a0  add     rsp, 48h
0x18001d5a4  pop     r15
0x18001d5a6  pop     r14
0x18001d5a8  pop     r13
0x18001d5aa  pop     r12
0x18001d5ac  pop     rdi
0x18001d5ad  pop     rsi
0x18001d5ae  pop     rbp
0x18001d5af  pop     rbx
0x18001d5b0  retn
0x18001d5b1  mov     dword ptr [rsp+88h+ppv], 0EA60h; unsigned int
0x18001d5b9  mov     r9d, edi; unsigned int
0x18001d5bc  xor     r8d, r8d; unsigned int
0x18001d5bf  xor     edx, edx; unsigned int
0x18001d5c1  mov     ecx, esi; unsigned int
0x18001d5c3  call    ?SetWin32ServiceStatus@@YAJKKKKK@Z; SetWin32ServiceStatus(ulong,ulong,ulong,ulong,ulong)
0x18001d5c8  mov     ebx, eax
0x18001d5ca  test    eax, eax
0x18001d5cc  js      short loc_18001D631
0x18001d5ce  xor     r9d, r9d; lpName
0x18001d5d1  xor     r8d, r8d; bInitialState
0x18001d5d4  xor     edx, edx; bManualReset
0x18001d5d6  xor     ecx, ecx; lpEventAttributes
0x18001d5d8  call    cs:__imp_CreateEventW
0x18001d5de  mov     cs:?g_stopServiceEvent@@3PEAXEA, rax; void * g_stopServiceEvent
0x18001d5e5  test    rax, rax
0x18001d5e8  jnz     short loc_18001D659
0x18001d5ea  call    cs:__imp_GetLastError
0x18001d5f0  mov     ebx, eax
0x18001d5f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5f9  cmp     rcx, r12
0x18001d5fc  jz      short loc_18001D618
0x18001d5fe  test    [rcx+1Ch], dil
0x18001d602  jz      short loc_18001D618
0x18001d604  mov     edx, 1Eh
0x18001d609  mov     r9d, eax
0x18001d60c  mov     r8, r13
0x18001d60f  mov     rcx, [rcx+10h]
0x18001d613  call    WPP_SF_d
0x18001d618  test    ebx, ebx
0x18001d61a  jle     short loc_18001D627
0x18001d61c  movzx   ebx, bx
0x18001d61f  or      ebx, 80070000h
0x18001d625  test    ebx, ebx
0x18001d627  mov     eax, 80004005h
0x18001d62c  cmovns  ebx, eax
0x18001d62f  jmp     short loc_18001D659
0x18001d631  mov     esi, edi
0x18001d633  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d63a  cmp     rcx, r12
0x18001d63d  jz      short loc_18001D659
0x18001d63f  test    [rcx+1Ch], dil
0x18001d643  jz      short loc_18001D659
0x18001d645  mov     edx, 1Dh
0x18001d64a  mov     r9d, eax
0x18001d64d  mov     r8, r13
0x18001d650  mov     rcx, [rcx+10h]
0x18001d654  call    WPP_SF_d
0x18001d659  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_serviceStatus ...
0x18001d663  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r15; _SERVICE_STATUS g_serviceStatus ...
0x18001d66a  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18001d671  test    rcx, rcx
0x18001d674  jz      short loc_18001D690
0x18001d676  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18001d67d  call    cs:__imp_SetServiceStatus
0x18001d683  test    eax, eax
0x18001d685  jz      loc_18001D71F
0x18001d68b  mov     esi, 4
0x18001d690  test    ebx, ebx
0x18001d692  js      loc_18001D862
0x18001d698  xor     edx, edx; hFile
0x18001d69a  mov     r8d, 800h; dwFlags
0x18001d6a0  lea     rcx, aVbsapiDll_0; "VbsApi.dll"
0x18001d6a7  call    cs:__imp_LoadLibraryExW
0x18001d6ad  mov     cs:?g_hVbsApi@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hVbsApi
0x18001d6b4  call    RegisterSecurityCenterBroker
0x18001d6b9  test    eax, eax
0x18001d6bb  jns     short loc_18001D6E3
0x18001d6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6c4  cmp     rcx, r12
0x18001d6c7  jz      short loc_18001D6E3
0x18001d6c9  test    [rcx+1Ch], dil
0x18001d6cd  jz      short loc_18001D6E3
0x18001d6cf  mov     edx, 20h ; ' '
0x18001d6d4  mov     r9d, eax
0x18001d6d7  mov     r8, r13
0x18001d6da  mov     rcx, [rcx+10h]
0x18001d6de  call    WPP_SF_d
0x18001d6e3  mov     ecx, ebp; int
0x18001d6e5  call    ?WscServiceStartup@@YAJH@Z; WscServiceStartup(int)
0x18001d6ea  mov     ebx, eax
0x18001d6ec  test    eax, eax
0x18001d6ee  jns     short loc_18001D769
0x18001d6f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6f7  cmp     rcx, r12
0x18001d6fa  jz      loc_18001D862
0x18001d700  test    [rcx+1Ch], dil
0x18001d704  jz      loc_18001D862
0x18001d70a  mov     dword ptr [rsp+88h+ppv], eax
0x18001d70e  mov     r9d, ebp
0x18001d711  mov     rcx, [rcx+10h]
0x18001d715  call    WPP_SF_dD
0x18001d71a  jmp     loc_18001D862
0x18001d71f  call    cs:__imp_GetLastError
0x18001d725  mov     ebx, eax
0x18001d727  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d72e  cmp     rcx, r12
0x18001d731  jz      short loc_18001D74D
0x18001d733  test    [rcx+1Ch], dil
0x18001d737  jz      short loc_18001D74D
0x18001d739  mov     edx, 1Fh
0x18001d73e  mov     r9d, eax
0x18001d741  mov     r8, r13
0x18001d744  mov     rcx, [rcx+10h]
0x18001d748  call    WPP_SF_d
0x18001d74d  test    ebx, ebx
0x18001d74f  jle     short loc_18001D75C
0x18001d751  movzx   ebx, bx
0x18001d754  or      ebx, 80070000h
0x18001d75a  test    ebx, ebx
0x18001d75c  mov     eax, 80004005h
0x18001d761  cmovns  ebx, eax
0x18001d764  jmp     loc_18001D862
0x18001d769  call    ?VelocityPollerStartup@@YAXXZ; VelocityPollerStartup(void)
0x18001d76e  mov     rax, cs:?g_svcHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_svcHostGlobalData
  ... truncated ...
```
