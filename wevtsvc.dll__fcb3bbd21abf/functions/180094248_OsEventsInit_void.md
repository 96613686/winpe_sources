# OsEventsInit(void)

- ea: `0x180094248`
- end: `0x1800945c7`
- name: `?OsEventsInit@@YAJXZ`
- size: `895`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180080d50`

## callees

- `0x180006770`
- `0x18000a180`
- `0x18005ff90`
- `0x180087784`
- `0x180092008`
- `0x180092ee4`
- `0x180094248`
- `0x1800945d0`
- `0x1800976d4`
- `0x18009aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009431f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009431f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800943b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800943d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800943f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800943b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800943d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800943f4`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180094375`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180094397`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180094375`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180094397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800944ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800944ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009448c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009448c`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x180094549`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x18009456b`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x180094549`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x18009456b`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180094515`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180094515`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x1800942b3`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x1800942b3`

## string_xrefs

- `0x18009450e`: `OS Events thread`

## pseudocode

```c
__int64 OsEventsInit(void)
{
  __int64 v0; // rax
  unsigned int ServiceRegistryStateKey; // eax
  HKEY *phkResult; // rax
  unsigned int v3; // eax
  HANDLE WaitableTimer; // rax
  HANDLE v5; // rax
  HANDLE EventW; // rax
  HANDLE v7; // rax
  HANDLE v8; // rax
  HANDLE Thread; // rax
  DWORD LastError; // eax
  int v12; // [rsp+30h] [rbp-28h] BYREF
  _DWORD v13[4]; // [rsp+38h] [rbp-20h] BYREF

  dword_18010F6B4 = OsEventsStartType();
  g_bHeartBeatsDisabled = AreAnyRestrictionsEnabled(8);
  if ( !g_bHeartBeatsDisabled )
  {
    v0 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&qword_180111DC8);
    ServiceRegistryStateKey = GetServiceRegistryStateKey(g_serviceControl, 1, 131103, v0);
    if ( (ServiceRegistryStateKey || !qword_180111DC8)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids,
        ServiceRegistryStateKey);
    }
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Reliability",
           0,
           0x2001Fu,
           phkResult);
    if ( (v3 || !hKey)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, v3);
    }
  }
  OsEventsBuildNoonEventPData();
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  tlx::unique_any<tlx::file_handle_traits>::reset(&qword_180111550, WaitableTimer);
  v5 = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hTimer, v5);
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hObject, EventW);
  v7 = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&qword_180111560, v7);
  v8 = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&qword_180111548, v8);
  if ( qword_180111550 == (HANDLE)-1LL
    || (char *)qword_180111550 + 1 == HANDLE_FLAG_INHERIT
    || hTimer == (HANDLE)-1LL
    || (char *)hTimer + 1 == HANDLE_FLAG_INHERIT
    || hObject == (HANDLE)-1LL
    || (char *)hObject + 1 == HANDLE_FLAG_INHERIT
    || qword_180111560 == (HANDLE)-1LL
    || (char *)qword_180111560 + 1 == HANDLE_FLAG_INHERIT
    || qword_180111548 == (HANDLE)-1LL
    || (char *)qword_180111548 + 1 == HANDLE_FLAG_INHERIT )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
    }
    OsEventsCleanup(0);
    return 3221225626LL;
  }
  else
  {
    Thread = CreateThread(0, 0, OsEventsThread, 0, 4u, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(&hThread, Thread);
    if ( (unsigned __int64)hThread + 1 > 1 )
    {
      SetThreadDescription(hThread, L"OS Events thread");
      v13[0] = 1;
      v13[1] = 1;
      v13[2] = 1;
      SetThreadInformation(hThread, 3, v13);
      v12 = 2;
      SetThreadInformation(hThread, 0, &v12);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, LastError);
      }
      tlx::unique_any<tlx::file_handle_traits>::reset(&qword_180111548, 0);
      OsEventsCleanup(0);
      return 3221225473LL;
    }
  }
}

```

## disassembly

```asm
0x180094248  mov     [rsp+arg_0], r14
0x18009424d  push    r15
0x18009424f  sub     rsp, 50h
0x180094253  mov     rax, cs:__security_cookie
0x18009425a  xor     rax, rsp
0x18009425d  mov     [rsp+58h+var_10], rax
0x180094262  call    OsEventsStartType
0x180094267  mov     ecx, 8
0x18009426c  mov     cs:dword_18010F6B4, eax
0x180094272  call    ?AreAnyRestrictionsEnabled@@YA_NW4FeatureRestrictions@@@Z; AreAnyRestrictionsEnabled(FeatureRestrictions)
0x180094277  mov     cs:?g_bHeartBeatsDisabled@@3_NA, al; bool g_bHeartBeatsDisabled
0x18009427d  lea     r15, WPP_GLOBAL_Control
0x180094284  mov     r14d, 4000h
0x18009428a  test    al, al
0x18009428c  jnz     loc_180094363
0x180094292  lea     rcx, qword_180111DC8
0x180094299  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18009429e  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_serviceControl
0x1800942a5  mov     r9, rax
0x1800942a8  mov     edx, 1
0x1800942ad  mov     r8d, 2001Fh
0x1800942b3  call    cs:__imp_GetServiceRegistryStateKey
0x1800942b9  test    eax, eax
0x1800942bb  jnz     short loc_1800942C7
0x1800942bd  cmp     cs:qword_180111DC8, 0
0x1800942c5  jnz     short loc_1800942F7
0x1800942c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800942ce  cmp     rcx, r15
0x1800942d1  jz      short loc_1800942F7
0x1800942d3  test    [rcx+1Ch], r14d
0x1800942d7  jz      short loc_1800942F7
0x1800942d9  cmp     byte ptr [rcx+19h], 2
0x1800942dd  jb      short loc_1800942F7
0x1800942df  mov     rcx, [rcx+10h]
0x1800942e3  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x1800942ea  mov     edx, 37h ; '7'
0x1800942ef  mov     r9d, eax
0x1800942f2  call    WPP_SF_d
0x1800942f7  lea     rcx, hKey
0x1800942fe  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180094303  mov     r9d, 2001Fh; samDesired
0x180094309  mov     [rsp+58h+phkResult], rax; phkResult
0x18009430e  xor     r8d, r8d; ulOptions
0x180094311  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180094318  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009431f  call    cs:__imp_RegOpenKeyExW
0x180094325  test    eax, eax
0x180094327  jnz     short loc_180094333
0x180094329  cmp     cs:hKey, 0
0x180094331  jnz     short loc_180094363
0x180094333  mov     rcx, cs:WPP_GLOBAL_Control
0x18009433a  cmp     rcx, r15
0x18009433d  jz      short loc_180094363
0x18009433f  test    [rcx+1Ch], r14d
0x180094343  jz      short loc_180094363
0x180094345  cmp     byte ptr [rcx+19h], 2
0x180094349  jb      short loc_180094363
0x18009434b  mov     rcx, [rcx+10h]
0x18009434f  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x180094356  mov     edx, 38h ; '8'
0x18009435b  mov     r9d, eax
0x18009435e  call    WPP_SF_d
0x180094363  call    OsEventsBuildNoonEventPData
0x180094368  mov     r9d, 1F0003h; dwDesiredAccess
0x18009436e  xor     r8d, r8d; dwFlags
0x180094371  xor     edx, edx; lpTimerName
0x180094373  xor     ecx, ecx; lpTimerAttributes
0x180094375  call    cs:__imp_CreateWaitableTimerExW
0x18009437b  mov     rdx, rax
0x18009437e  lea     rcx, qword_180111550
0x180094385  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009438a  mov     r9d, 1F0003h; dwDesiredAccess
0x180094390  xor     r8d, r8d; dwFlags
0x180094393  xor     edx, edx; lpTimerName
0x180094395  xor     ecx, ecx; lpTimerAttributes
0x180094397  call    cs:__imp_CreateWaitableTimerExW
0x18009439d  mov     rdx, rax
0x1800943a0  lea     rcx, hTimer
0x1800943a7  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800943ac  xor     r9d, r9d; lpName
0x1800943af  xor     r8d, r8d; bInitialState
0x1800943b2  xor     edx, edx; bManualReset
0x1800943b4  xor     ecx, ecx; lpEventAttributes
0x1800943b6  call    cs:__imp_CreateEventW
0x1800943bc  mov     rdx, rax
0x1800943bf  lea     rcx, hObject
0x1800943c6  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800943cb  xor     r9d, r9d; lpName
0x1800943ce  xor     r8d, r8d; bInitialState
0x1800943d1  xor     edx, edx; bManualReset
0x1800943d3  xor     ecx, ecx; lpEventAttributes
0x1800943d5  call    cs:__imp_CreateEventW
0x1800943db  mov     rdx, rax
0x1800943de  lea     rcx, qword_180111560
0x1800943e5  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800943ea  xor     r9d, r9d; lpName
0x1800943ed  xor     r8d, r8d; bInitialState
0x1800943f0  xor     edx, edx; bManualReset
0x1800943f2  xor     ecx, ecx; lpEventAttributes
0x1800943f4  call    cs:__imp_CreateEventW
0x1800943fa  mov     rdx, rax
0x1800943fd  lea     rcx, qword_180111548
0x180094404  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180094409  mov     rax, cs:qword_180111550
0x180094410  inc     rax
0x180094413  cmp     rax, 1
0x180094417  jbe     loc_180094575
0x18009441d  mov     rax, cs:hTimer
0x180094424  inc     rax
0x180094427  cmp     rax, 1
0x18009442b  jbe     loc_180094575
0x180094431  mov     rax, cs:hObject
0x180094438  inc     rax
0x18009443b  cmp     rax, 1
0x18009443f  jbe     loc_180094575
0x180094445  mov     rax, cs:qword_180111560
0x18009444c  inc     rax
0x18009444f  cmp     rax, 1
0x180094453  jbe     loc_180094575
0x180094459  mov     rax, cs:qword_180111548
0x180094460  inc     rax
0x180094463  cmp     rax, 1
0x180094467  jbe     loc_180094575
0x18009446d  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180094476  lea     r8, OsEventsThread; lpStartAddress
0x18009447d  xor     r9d, r9d; lpParameter
0x180094480  mov     dword ptr [rsp+58h+phkResult], 4; dwCreationFlags
0x180094488  xor     edx, edx; dwStackSize
0x18009448a  xor     ecx, ecx; lpThreadAttributes
0x18009448c  call    cs:__imp_CreateThread
0x180094492  mov     rdx, rax
0x180094495  lea     rcx, hThread
0x18009449c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800944a1  mov     rcx, cs:hThread; hThread
0x1800944a8  lea     rax, [rcx+1]
0x1800944ac  cmp     rax, 1
0x1800944b0  ja      short loc_18009450E
0x1800944b2  mov     rax, cs:WPP_GLOBAL_Control
0x1800944b9  cmp     rax, r15
0x1800944bc  jz      short loc_1800944EF
0x1800944be  test    [rax+1Ch], r14d
0x1800944c2  jz      short loc_1800944EF
0x1800944c4  cmp     byte ptr [rax+19h], 2
0x1800944c8  jb      short loc_1800944EF
0x1800944ca  call    cs:__imp_GetLastError
0x1800944d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800944d7  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x1800944de  mov     edx, 3Ah ; ':'
0x1800944e3  mov     r9d, eax
0x1800944e6  mov     rcx, [rcx+10h]
0x1800944ea  call    WPP_SF_d
0x1800944ef  xor     edx, edx
0x1800944f1  lea     rcx, qword_180111548
0x1800944f8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800944fd  xor     ecx, ecx; bool
0x1800944ff  call    ?OsEventsCleanup@@YAJ_N@Z; OsEventsCleanup(bool)
0x180094504  mov     eax, 0C0000001h
0x180094509  jmp     loc_1800945AE
0x18009450e  lea     rdx, ThreadDescription; "OS Events thread"
0x180094515  call    cs:__imp_SetThreadDescription
0x18009451b  mov     rcx, cs:hThread
0x180094522  lea     r8, [rsp+58h+var_20]
0x180094527  mov     r9d, 0Ch
0x18009452d  mov     [rsp+58h+var_20], 1
0x180094535  mov     [rsp+58h+var_1C], 1
0x18009453d  mov     [rsp+58h+var_18], 1
0x180094545  lea     edx, [r9-9]
0x180094549  call    cs:__imp_SetThreadInformation
0x18009454f  mov     rcx, cs:hThread
0x180094556  lea     r8, [rsp+58h+var_28]
0x18009455b  mov     r9d, 4
0x180094561  mov     [rsp+58h+var_28], 2
0x180094569  xor     edx, edx
0x18009456b  call    cs:__imp_SetThreadInformation
0x180094571  xor     eax, eax
0x180094573  jmp     short loc_1800945AE
0x180094575  mov     rcx, cs:WPP_GLOBAL_Control
0x18009457c  cmp     rcx, r15
0x18009457f  jz      short loc_1800945A2
0x180094581  test    [rcx+1Ch], r14d
0x180094585  jz      short loc_1800945A2
0x180094587  cmp     byte ptr [rcx+19h], 2
0x18009458b  jb      short loc_1800945A2
0x18009458d  mov     rcx, [rcx+10h]
0x180094591  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x180094598  mov     edx, 39h ; '9'
0x18009459d  call    WPP_SF_
0x1800945a2  xor     ecx, ecx; bool
0x1800945a4  call    ?OsEventsCleanup@@YAJ_N@Z; OsEventsCleanup(bool)
0x1800945a9  mov     eax, 0C000009Ah
0x1800945ae  mov     rcx, [rsp+58h+var_10]
0x1800945b3  xor     rcx, rsp; StackCookie
0x1800945b6  call    __security_check_cookie
0x1800945bb  mov     r14, [rsp+58h+arg_0]
0x1800945c0  add     rsp, 50h
0x1800945c4  pop     r15
0x1800945c6  retn
```
