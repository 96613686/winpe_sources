# WdipControlServer

- ea: `0x180002e70`
- end: `0x1800030af`
- name: `WdipControlServer`
- size: `575`
- prototype: `signed int __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001980`

## callees

- `0x180002ba0`
- `0x180002e70`
- `0x1800068f0`

## import_xrefs

- `ntdll!NtAlpcDisconnectPort` at `0x180002e9b`
- `ntdll!NtAlpcDisconnectPort` at `0x180002fab`
- `ntdll!NtAlpcDisconnectPort` at `0x180002e9b`
- `ntdll!NtAlpcDisconnectPort` at `0x180002fab`
- `ntdll!TpWaitForAlpcCompletion` at `0x180002ef7`
- `ntdll!TpWaitForAlpcCompletion` at `0x18000302b`
- `ntdll!TpWaitForAlpcCompletion` at `0x180002ef7`
- `ntdll!TpWaitForAlpcCompletion` at `0x18000302b`
- `ntdll!NtAlpcQueryInformation` at `0x180002ebc`
- `ntdll!NtAlpcQueryInformation` at `0x180002fc7`
- `ntdll!NtAlpcQueryInformation` at `0x180002ebc`
- `ntdll!NtAlpcQueryInformation` at `0x180002fc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fe8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fe8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002e8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002eea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003010`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002e8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002eea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f3e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002f34`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002f34`

## pseudocode

```c
signed int __fastcall WdipControlServer(void *a1)
{
  signed int Args; // eax
  bool v2; // sf
  __int32 v3; // edi
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  signed int result; // eax
  _QWORD *v7; // rbx
  __int64 v8; // rcx
  _DWORD *v9; // rbx
  __int128 v10; // [rsp+30h] [rbp-28h] BYREF
  __int128 v11; // [rsp+40h] [rbp-18h] BYREF

  v10 = 0;
  WaitForSingleObject(a1, 0xFFFFFFFF);
  NtAlpcDisconnectPort(g_hDMHost, 0);
  NtAlpcQueryInformation(g_hDMHost, 0, &v10, 16, 0);
  g_lExpectedHostMessageCount = DWORD1(v10) - 1;
  if ( g_lReceivedHostMessageCount < DWORD1(v10) - 1 )
    WaitForSingleObject(g_hTPHostShutdown, 0xFFFFFFFF);
  TpWaitForAlpcCompletion(g_pHostAlpcCompletion);
  if ( g_hService )
  {
    g_sSvcStatus.dwWin32ExitCode = 0;
    g_sSvcStatus.dwCurrentState = 3;
    g_sSvcStatus.dwCheckPoint = 1;
    g_sSvcStatus.dwWaitHint = 10000;
    if ( !SetServiceStatus(g_hService, &g_sSvcStatus) )
    {
      Args = GetLastError();
      v2 = Args < 0;
      if ( Args > 0 )
      {
        Args = (unsigned __int16)Args | 0x80070000;
        v2 = Args < 0;
      }
      if ( v2 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
          (int)L"WdipNotifySvc",
          639,
          (int)L"Error = %d",
          Args);
    }
  }
  v11 = 0;
  v3 = 0;
  EnterCriticalSection(&g_csWDI);
  v4 = g_pWdiSessionHead;
  if ( g_pWdiSessionHead )
  {
    do
    {
      v5 = v4[7];
      if ( v5 )
      {
        NtAlpcDisconnectPort(v5, 0);
        NtAlpcQueryInformation(v4[7], 0, &v11, 16, 0);
        v3 += DWORD1(v11) - 1;
      }
      v3 += *((_DWORD *)v4 + 21);
      v4 = (_QWORD *)v4[13];
    }
    while ( v4 );
  }
  LeaveCriticalSection(&g_csWDI);
  _InterlockedExchange(&g_lExpectedDMMessageCount, v3);
  result = g_lExpectedDMMessageCount;
  if ( g_lReceivedDMMessageCount < g_lExpectedDMMessageCount )
    result = WaitForSingleObject(g_hTPDMShutdown, 0xFFFFFFFF);
  v7 = g_pWdiSessionHead;
  if ( g_pWdiSessionHead )
  {
    do
    {
      v8 = v7[11];
      if ( v8 )
        result = TpWaitForAlpcCompletion(v8);
      v7 = (_QWORD *)v7[13];
    }
    while ( v7 );
    v9 = g_pWdiSessionHead;
    if ( g_pWdiSessionHead )
    {
      while ( 1 )
      {
        if ( *((_QWORD *)v9 + 7) )
        {
          v9[4] = 8;
          result = WdipUnloadDM(v9);
          if ( result < 0 )
            break;
        }
        v9 = (_DWORD *)*((_QWORD *)v9 + 13);
        if ( !v9 )
          return result;
      }
      return WdipTraceError(
               (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\sessions.cpp",
               (int)L"WdipUnloadActiveDMs",
               332,
               (int)L"Error = %d",
               result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002e70  mov     [rsp+arg_0], rbx
0x180002e75  mov     [rsp+arg_8], rsi
0x180002e7a  push    rdi
0x180002e7b  sub     rsp, 50h
0x180002e7f  xorps   xmm0, xmm0
0x180002e82  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180002e87  movups  [rsp+58h+var_28], xmm0
0x180002e8c  call    cs:__imp_WaitForSingleObject
0x180002e92  mov     rcx, cs:g_hDMHost
0x180002e99  xor     edx, edx
0x180002e9b  call    cs:__imp_NtAlpcDisconnectPort
0x180002ea1  mov     rcx, cs:g_hDMHost
0x180002ea8  lea     r8, [rsp+58h+var_28]
0x180002ead  xor     esi, esi
0x180002eaf  mov     r9d, 10h
0x180002eb5  xor     edx, edx
0x180002eb7  mov     qword ptr [rsp+58h+Args], rsi
0x180002ebc  call    cs:__imp_NtAlpcQueryInformation
0x180002ec2  mov     eax, dword ptr [rsp+58h+var_28+4]
0x180002ec6  dec     eax
0x180002ec8  mov     cs:g_lExpectedHostMessageCount, eax
0x180002ece  mov     ecx, cs:g_lReceivedHostMessageCount
0x180002ed4  mov     eax, cs:g_lExpectedHostMessageCount
0x180002eda  cmp     ecx, eax
0x180002edc  jge     short loc_180002EF0
0x180002ede  mov     rcx, cs:g_hTPHostShutdown; hHandle
0x180002ee5  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180002eea  call    cs:__imp_WaitForSingleObject
0x180002ef0  mov     rcx, cs:g_pHostAlpcCompletion
0x180002ef7  call    cs:__imp_TpWaitForAlpcCompletion
0x180002efd  mov     rcx, cs:?g_hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180002f04  test    rcx, rcx
0x180002f07  jz      short loc_180002F7B
0x180002f09  lea     rdx, ?g_sSvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180002f10  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, esi; _SERVICE_STATUS g_sSvcStatus ...
0x180002f16  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_sSvcStatus ...
0x180002f20  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS g_sSvcStatus ...
0x180002f2a  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 2710h; _SERVICE_STATUS g_sSvcStatus ...
0x180002f34  call    cs:__imp_SetServiceStatus
0x180002f3a  test    eax, eax
0x180002f3c  jnz     short loc_180002F7B
0x180002f3e  call    cs:__imp_GetLastError
0x180002f44  test    eax, eax
0x180002f46  jle     short loc_180002F52
0x180002f48  movzx   eax, ax
0x180002f4b  or      eax, 80070000h
0x180002f50  test    eax, eax
0x180002f52  jns     short loc_180002F7B
0x180002f54  movzx   eax, ax
0x180002f57  lea     r9, aErrorD_0; "Error = %d"
0x180002f5e  mov     r8d, 27Fh; int
0x180002f64  mov     dword ptr [rsp+58h+Args], eax; Args
0x180002f68  lea     rdx, aWdipnotifysvc; "WdipNotifySvc"
0x180002f6f  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002f76  call    WdipTraceError
0x180002f7b  xorps   xmm0, xmm0
0x180002f7e  lea     rcx, g_csWDI; lpCriticalSection
0x180002f85  movups  [rsp+58h+var_18], xmm0
0x180002f8a  mov     edi, esi
0x180002f8c  call    cs:__imp_EnterCriticalSection
0x180002f92  mov     rbx, cs:g_pWdiSessionHead
0x180002f99  test    rbx, rbx
0x180002f9c  jz      short loc_180002FE1
0x180002f9e  xchg    ax, ax
0x180002fa0  mov     rcx, [rbx+38h]
0x180002fa4  test    rcx, rcx
0x180002fa7  jz      short loc_180002FD5
0x180002fa9  xor     edx, edx
0x180002fab  call    cs:__imp_NtAlpcDisconnectPort
0x180002fb1  mov     rcx, [rbx+38h]
0x180002fb5  lea     r8, [rsp+58h+var_18]
0x180002fba  mov     r9d, 10h
0x180002fc0  mov     qword ptr [rsp+58h+Args], rsi
0x180002fc5  xor     edx, edx
0x180002fc7  call    cs:__imp_NtAlpcQueryInformation
0x180002fcd  mov     eax, dword ptr [rsp+58h+var_18+4]
0x180002fd1  dec     eax
0x180002fd3  add     edi, eax
0x180002fd5  add     edi, [rbx+54h]
0x180002fd8  mov     rbx, [rbx+68h]
0x180002fdc  test    rbx, rbx
0x180002fdf  jnz     short loc_180002FA0
0x180002fe1  lea     rcx, g_csWDI; lpCriticalSection
0x180002fe8  call    cs:__imp_LeaveCriticalSection
0x180002fee  xchg    edi, cs:g_lExpectedDMMessageCount
0x180002ff4  mov     ecx, cs:g_lReceivedDMMessageCount
0x180002ffa  mov     eax, cs:g_lExpectedDMMessageCount
0x180003000  cmp     ecx, eax
0x180003002  jge     short loc_180003016
0x180003004  mov     rcx, cs:g_hTPDMShutdown; hHandle
0x18000300b  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180003010  call    cs:__imp_WaitForSingleObject
0x180003016  mov     rbx, cs:g_pWdiSessionHead
0x18000301d  test    rbx, rbx
0x180003020  jz      short loc_18000309F
0x180003022  mov     rcx, [rbx+58h]
0x180003026  test    rcx, rcx
0x180003029  jz      short loc_180003031
0x18000302b  call    cs:__imp_TpWaitForAlpcCompletion
0x180003031  mov     rbx, [rbx+68h]
0x180003035  test    rbx, rbx
0x180003038  jnz     short loc_180003022
0x18000303a  mov     rbx, cs:g_pWdiSessionHead
0x180003041  test    rbx, rbx
0x180003044  jz      short loc_18000309F
0x180003046  cmp     [rbx+38h], rsi
0x18000304a  jz      short loc_18000305F
0x18000304c  mov     rcx, rbx
0x18000304f  mov     dword ptr [rbx+10h], 8
0x180003056  call    WdipUnloadDM
0x18000305b  test    eax, eax
0x18000305d  js      short loc_180003078
0x18000305f  mov     rbx, [rbx+68h]
0x180003063  test    rbx, rbx
0x180003066  jnz     short loc_180003046
0x180003068  mov     rbx, [rsp+58h+arg_0]
0x18000306d  mov     rsi, [rsp+58h+arg_8]
0x180003072  add     rsp, 50h
0x180003076  pop     rdi
0x180003077  retn
0x180003078  movzx   eax, ax
0x18000307b  lea     r9, aErrorD_0; "Error = %d"
0x180003082  mov     r8d, 14Ch; int
0x180003088  mov     dword ptr [rsp+58h+Args], eax; Args
0x18000308c  lea     rdx, aWdipunloadacti; "WdipUnloadActiveDMs"
0x180003093  lea     rcx, aClientcoreBase_3; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000309a  call    WdipTraceError
0x18000309f  mov     rbx, [rsp+58h+arg_0]
0x1800030a4  mov     rsi, [rsp+58h+arg_8]
0x1800030a9  add     rsp, 50h
0x1800030ad  pop     rdi
0x1800030ae  retn
```
