# StopService(void *,uchar)

- ea: `0x18001c8e0`
- end: `0x18001cb14`
- name: `?StopService@@YAXPEAXE@Z`
- size: `564`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008e48`
- `0x18001c8e0`
- `0x18001cb1c`
- `0x1800202e8`
- `0x180028a30`
- `0x180028acc`
- `0x180028e10`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001ca87`
- `ntdll!EtwEventWrite` at `0x18001ca87`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001c966`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001c966`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ca6d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ca6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cac0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c9f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c9f6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001caf1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001caf1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18001c988`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18001c988`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001c924`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001c924`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ca10`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ca10`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001cb05`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001cb05`

## pseudocode

```c
void __fastcall StopService(void *a1)
{
  HRESULT v1; // eax
  char v2; // bl
  DWORD LastError; // eax
  SERVICE_STATUS_HANDLE v4; // rcx
  DWORD v5; // eax

  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
  v1 = CoInitializeEx(0, 0);
  if ( v1 >= 0 )
  {
    v2 = 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_b798000f0de738f41d9362b18d9c2686_Traceguids,
        (unsigned int)v1);
    }
    v2 = 0;
  }
  VelocityPollerExit();
  FreeLibrary(g_hVbsApi);
  g_hVbsApi = 0;
  UnregisterSecurityCenterBroker();
  WscCleanup();
  if ( UnregisterWait(g_waitObject) )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 997
      && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, LastError);
    }
  }
  if ( g_stopServiceEvent )
  {
    CloseHandle(g_stopServiceEvent);
    g_stopServiceEvent = 0;
  }
  SystemMonitoringCleanup();
  if ( v2 )
    CoUninitialize();
  v4 = g_serviceStatusHandle;
  g_serviceStatus.dwCurrentState = 1;
  *(_QWORD *)&g_serviceStatus.dwCheckPoint = 0;
  if ( g_serviceStatusHandle )
  {
    while ( !SetServiceStatus(v4, &g_serviceStatus) )
    {
      v5 = GetLastError();
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, v5);
      }
      Sleep(0x1F4u);
      v4 = g_serviceStatusHandle;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
    }
    LoadLibraryExW(L"wscsvc", 0, 0x800u);
  }
  EtwEventWrite(g_Provider, "i", 0, 0);
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
}

```

## disassembly

```asm
0x18001c8e0  mov     [rsp+arg_0], rbx
0x18001c8e5  mov     [rsp+arg_8], rbp
0x18001c8ea  push    rsi
0x18001c8eb  sub     rsp, 20h
0x18001c8ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c8f6  lea     rsi, WPP_GLOBAL_Control
0x18001c8fd  lea     rbp, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x18001c904  cmp     rcx, rsi
0x18001c907  jz      short loc_18001C920
0x18001c909  test    byte ptr [rcx+1Ch], 8
0x18001c90d  jz      short loc_18001C920
0x18001c90f  mov     rcx, [rcx+10h]
0x18001c913  mov     edx, 25h ; '%'
0x18001c918  mov     r8, rbp
0x18001c91b  call    WPP_SF_
0x18001c920  xor     edx, edx; dwCoInit
0x18001c922  xor     ecx, ecx; pvReserved
0x18001c924  call    cs:__imp_CoInitializeEx
0x18001c92a  test    eax, eax
0x18001c92c  jns     short loc_18001C958
0x18001c92e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c935  cmp     rcx, rsi
0x18001c938  jz      short loc_18001C954
0x18001c93a  test    byte ptr [rcx+1Ch], 1
0x18001c93e  jz      short loc_18001C954
0x18001c940  mov     rcx, [rcx+10h]
0x18001c944  mov     edx, 26h ; '&'
0x18001c949  mov     r9d, eax
0x18001c94c  mov     r8, rbp
0x18001c94f  call    WPP_SF_d
0x18001c954  xor     bl, bl
0x18001c956  jmp     short loc_18001C95A
0x18001c958  mov     bl, 1
0x18001c95a  call    ?VelocityPollerExit@@YAXXZ; VelocityPollerExit(void)
0x18001c95f  mov     rcx, cs:?g_hVbsApi@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001c966  call    cs:__imp_FreeLibrary
0x18001c96c  mov     cs:?g_hVbsApi@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hVbsApi
0x18001c977  call    UnregisterSecurityCenterBroker
0x18001c97c  call    ?WscCleanup@@YAXXZ; WscCleanup(void)
0x18001c981  mov     rcx, cs:?g_waitObject@@3PEAXEA; WaitHandle
0x18001c988  call    cs:__imp_UnregisterWait
0x18001c98e  test    eax, eax
0x18001c990  jnz     short loc_18001C9C7
0x18001c992  call    cs:__imp_GetLastError
0x18001c998  cmp     eax, 3E5h
0x18001c99d  jz      short loc_18001C9EA
0x18001c99f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9a6  cmp     rcx, rsi
0x18001c9a9  jz      short loc_18001C9EA
0x18001c9ab  test    byte ptr [rcx+1Ch], 1
0x18001c9af  jz      short loc_18001C9EA
0x18001c9b1  mov     rcx, [rcx+10h]
0x18001c9b5  mov     edx, 27h ; '''
0x18001c9ba  mov     r9d, eax
0x18001c9bd  mov     r8, rbp
0x18001c9c0  call    WPP_SF_d
0x18001c9c5  jmp     short loc_18001C9EA
0x18001c9c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9ce  cmp     rcx, rsi
0x18001c9d1  jz      short loc_18001C9EA
0x18001c9d3  test    byte ptr [rcx+1Ch], 1
0x18001c9d7  jz      short loc_18001C9EA
0x18001c9d9  mov     rcx, [rcx+10h]
0x18001c9dd  mov     edx, 28h ; '('
0x18001c9e2  mov     r8, rbp
0x18001c9e5  call    WPP_SF_
0x18001c9ea  mov     rcx, cs:?g_stopServiceEvent@@3PEAXEA; hObject
0x18001c9f1  test    rcx, rcx
0x18001c9f4  jz      short loc_18001CA07
0x18001c9f6  call    cs:__imp_CloseHandle
0x18001c9fc  mov     cs:?g_stopServiceEvent@@3PEAXEA, 0; void * g_stopServiceEvent
0x18001ca07  call    ?SystemMonitoringCleanup@@YAXXZ; SystemMonitoringCleanup(void)
0x18001ca0c  test    bl, bl
0x18001ca0e  jz      short loc_18001CA16
0x18001ca10  call    cs:__imp_CoUninitialize
0x18001ca16  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_serviceStatusHandle
0x18001ca1d  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_serviceStatus ...
0x18001ca27  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_serviceStatus ...
0x18001ca32  test    rcx, rcx
0x18001ca35  jnz     loc_18001CAFE
0x18001ca3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca42  cmp     rcx, rsi
0x18001ca45  jz      short loc_18001CA5E
0x18001ca47  test    byte ptr [rcx+1Ch], 1
0x18001ca4b  jz      short loc_18001CA5E
0x18001ca4d  mov     rcx, [rcx+10h]
0x18001ca51  mov     edx, 2Ah ; '*'
0x18001ca56  mov     r8, rbp
0x18001ca59  call    WPP_SF_
0x18001ca5e  xor     edx, edx; hFile
0x18001ca60  lea     rcx, LibFileName; "wscsvc"
0x18001ca67  mov     r8d, 800h; dwFlags
0x18001ca6d  call    cs:__imp_LoadLibraryExW
0x18001ca73  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x18001ca7a  lea     rdx, WSC_SVC_Stop_End; "i"
0x18001ca81  xor     r9d, r9d
0x18001ca84  xor     r8d, r8d
0x18001ca87  call    cs:__imp_EtwEventWrite
0x18001ca8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca94  cmp     rcx, rsi
0x18001ca97  jz      short loc_18001CAB0
0x18001ca99  test    byte ptr [rcx+1Ch], 4
0x18001ca9d  jz      short loc_18001CAB0
0x18001ca9f  mov     rcx, [rcx+10h]
0x18001caa3  mov     edx, 2Bh ; '+'
0x18001caa8  mov     r8, rbp
0x18001caab  call    WPP_SF_
0x18001cab0  mov     rbx, [rsp+28h+arg_0]
0x18001cab5  mov     rbp, [rsp+28h+arg_8]
0x18001caba  add     rsp, 20h
0x18001cabe  pop     rsi
0x18001cabf  retn
0x18001cac0  call    cs:__imp_GetLastError
0x18001cac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cacd  cmp     rcx, rsi
0x18001cad0  jz      short loc_18001CAEC
0x18001cad2  test    byte ptr [rcx+1Ch], 1
0x18001cad6  jz      short loc_18001CAEC
0x18001cad8  mov     rcx, [rcx+10h]
0x18001cadc  mov     edx, 29h ; ')'
0x18001cae1  mov     r9d, eax
0x18001cae4  mov     r8, rbp
0x18001cae7  call    WPP_SF_d
0x18001caec  mov     ecx, 1F4h; dwMilliseconds
0x18001caf1  call    cs:__imp_Sleep
0x18001caf7  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18001cafe  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18001cb05  call    cs:__imp_SetServiceStatus
0x18001cb0b  test    eax, eax
0x18001cb0d  jz      short loc_18001CAC0
0x18001cb0f  jmp     loc_18001CA73
```
