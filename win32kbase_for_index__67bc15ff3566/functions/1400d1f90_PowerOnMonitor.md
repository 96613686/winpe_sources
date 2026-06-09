# PowerOnMonitor

- ea: `0x1400d1f90`
- end: `0x1400d2271`
- name: `PowerOnMonitor`
- size: `737`
- prototype: `__int64 __fastcall(enum POWER_MONITOR_REQUEST_REASON)`
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400cff38`
- `0x1400d1028`

## callees

- `0x14000f20c`
- `0x14004dfb0`
- `0x1400c3e10`
- `0x1400cf0ec`
- `0x1400cf1d8`
- `0x1400cf9dc`
- `0x1400d1d84`
- `0x1400d1f90`
- `0x1400d2278`
- `0x1400d22f0`
- `0x1400d231c`
- `0x1400d2348`
- `0x140121608`
- `0x140164040`
- `0x14016dc50`
- `0x140176654`
- `0x14017d6c4`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400d2064`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400d224c`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400d2064`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400d224c`
- `watchdog!DisplayRestoreVidPnJournalFinalize` at `0x1400d214d`
- `watchdog!DisplayRestoreVidPnJournalFinalize` at `0x1400d214d`
- `watchdog!DisplayRestoreVidPnJournalBegin` at `0x1400d20e3`
- `watchdog!DisplayRestoreVidPnJournalBegin` at `0x1400d20e3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d21d3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d21f8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d21d3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d21f8`
- `WIN32K!W32GetUserSessionState` at `0x1400d1faa`
- `WIN32K!W32GetUserSessionState` at `0x1400d1fc8`
- `WIN32K!W32GetUserSessionState` at `0x1400d2004`
- `WIN32K!W32GetUserSessionState` at `0x1400d20bb`
- `WIN32K!W32GetUserSessionState` at `0x1400d20ef`
- `WIN32K!W32GetUserSessionState` at `0x1400d210c`
- `WIN32K!W32GetUserSessionState` at `0x1400d2132`
- `WIN32K!W32GetUserSessionState` at `0x1400d2159`
- `WIN32K!W32GetUserSessionState` at `0x1400d21be`
- `WIN32K!W32GetUserSessionState` at `0x1400d1faa`
- `WIN32K!W32GetUserSessionState` at `0x1400d1fc8`
- `WIN32K!W32GetUserSessionState` at `0x1400d2004`
- `WIN32K!W32GetUserSessionState` at `0x1400d20bb`
- `WIN32K!W32GetUserSessionState` at `0x1400d20ef`
- `WIN32K!W32GetUserSessionState` at `0x1400d210c`
- `WIN32K!W32GetUserSessionState` at `0x1400d2132`
- `WIN32K!W32GetUserSessionState` at `0x1400d2159`
- `WIN32K!W32GetUserSessionState` at `0x1400d21be`

## pseudocode

```c
__int64 __fastcall PowerOnMonitor(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebp
  enum POWER_MONITOR_REQUEST_REASON v5; // r14d
  _DWORD *UserSessionState; // rbx
  int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 result; // rax
  int v12; // edi
  int v13; // r15d
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  struct tagTHREADINFO *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  int v51; // r9d
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  int (__fastcall *v57)(__int64, __int64, __int64); // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  void (__fastcall *v63)(__int64, __int64, __int64); // rax
  int v64; // [rsp+A8h] [rbp+20h] BYREF

  v3 = a3;
  v5 = (int)a1;
  UserSessionState = (_DWORD *)W32GetUserSessionState(a1, a2, a3);
  v7 = UserSessionState[675];
  result = W32GetUserSessionState(v9, v8, v10);
  if ( !**(_BYTE **)(result + 2664) )
  {
    v12 = 0;
    v13 = 0;
    EtwTracPowerOnMonitoreBegin(v3);
    InputTraceLogging::Power::PowerOnMonitor((unsigned int)v5, v3);
    if ( !v7 )
    {
      if ( !*(_WORD *)(W32GetUserSessionState(v15, v14, v16) + 68736) )
      {
        if ( !UserSessionState[675] && !UserSessionState[680] && !UserSessionState[681] )
        {
          v13 = 1;
          v64 = 1;
          ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v64, 4);
        }
        DrvChangeD3RequestsState(0);
        UserSessionSwitchBlock_Start();
        v17 = PtiCurrent();
        if ( v17 )
        {
          v20 = *((_QWORD *)v17 + 61);
          if ( v20 )
          {
            v21 = *(_QWORD *)(v20 + 8);
            if ( v21 )
            {
              v22 = *(unsigned int *)(*(_QWORD *)v21 + 64LL);
              if ( (v22 & 1) != 0 )
                DCompositionForceRender(v22, v18, v19);
            }
          }
        }
        DrvDxgkLogCodePointPacket(13, 0, 0, 0);
        if ( *(_QWORD *)(W32GetUserSessionState(v24, v23, v25) + 19216)
          && (int)IsSetPointerSupported(v27, v26, v28) >= 0 )
        {
          SetPointer(0);
        }
        DisplayRestoreVidPnJournalBegin((unsigned int)v5);
        v32 = W32GetUserSessionState(v30, v29, v31);
        ArmPowerWatchdog(*(_QWORD *)(v32 + 504), 80);
        v36 = W32GetUserSessionState(v34, v33, v35);
        DrvSetMonitorPowerState(*(_QWORD *)(*(_QWORD *)(v36 + 56744) + 16LL), 1, 0, a2);
        v40 = W32GetUserSessionState(v38, v37, v39);
        DisarmPowerWatchdog(*(_QWORD *)(v40 + 504));
        DisplayRestoreVidPnJournalFinalize(a2);
        if ( *(_QWORD *)(W32GetUserSessionState(v42, v41, v43) + 19216)
          && (int)IsSetPointerSupported(v45, v44, v46) >= 0 )
        {
          SetPointer(1);
        }
        UserSessionSwitchBlock_End();
        LOBYTE(v47) = 1;
        DrvChangeD3RequestsState(v47);
      }
      v12 = 1;
    }
    PowerUnDimMonitor(v15, v14, v16);
    if ( UserSessionState[710] == 2 || v12 )
      UpdateDisplayState(PowerMonitorOn, v5, v7 == 0, v51);
    if ( !v7 )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v49, v48, v50) + 19216) )
      {
        v55 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v53, v52) + 48);
        v57 = *(int (__fastcall **)(__int64, __int64, __int64))(v55 + 2080);
        if ( v57 )
        {
          if ( v57(v55, v54, v56) >= 0 )
          {
            v61 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v59, v58) + 48);
            v63 = *(void (__fastcall **)(__int64, __int64, __int64))(v61 + 2088);
            if ( v63 )
              v63(v61, v60, v62);
          }
        }
      }
    }
    if ( v13 )
    {
      v64 = 3;
      ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v64, 4);
    }
    return EtwTracePowerOnMonitorEnd(v3);
  }
  return result;
}

```

## disassembly

```asm
0x1400d1f90  push    rbx
0x1400d1f92  push    rbp
0x1400d1f93  push    rsi
0x1400d1f94  push    rdi
0x1400d1f95  push    r12
0x1400d1f97  push    r13
0x1400d1f99  push    r14
0x1400d1f9b  push    r15
0x1400d1f9d  sub     rsp, 48h
0x1400d1fa1  mov     ebp, r8d
0x1400d1fa4  mov     r13, rdx
0x1400d1fa7  mov     r14d, ecx
0x1400d1faa  call    cs:__imp_W32GetUserSessionState
0x1400d1fb1  nop     dword ptr [rax+rax+00h]
0x1400d1fb6  xor     r12d, r12d
0x1400d1fb9  mov     rbx, rax
0x1400d1fbc  mov     esi, [rax+0A8Ch]
0x1400d1fc2  test    esi, esi
0x1400d1fc4  setz    r12b
0x1400d1fc8  call    cs:__imp_W32GetUserSessionState
0x1400d1fcf  nop     dword ptr [rax+rax+00h]
0x1400d1fd4  mov     r8, [rax+0A68h]
0x1400d1fdb  mov     dl, [r8]
0x1400d1fde  test    dl, dl
0x1400d1fe0  jnz     loc_1400D225F
0x1400d1fe6  mov     ecx, ebp
0x1400d1fe8  xor     edi, edi
0x1400d1fea  xor     r15d, r15d
0x1400d1fed  call    EtwTracPowerOnMonitoreBegin
0x1400d1ff2  mov     edx, ebp
0x1400d1ff4  mov     ecx, r14d
0x1400d1ff7  call    ?PowerOnMonitor@Power@InputTraceLogging@@SAXW4POWER_MONITOR_REQUEST_REASON@@W4_POWERON_LOC@@@Z; InputTraceLogging::Power::PowerOnMonitor(POWER_MONITOR_REQUEST_REASON,_POWERON_LOC)
0x1400d1ffc  test    esi, esi
0x1400d1ffe  jnz     loc_1400D2192
0x1400d2004  call    cs:__imp_W32GetUserSessionState
0x1400d200b  nop     dword ptr [rax+rax+00h]
0x1400d2010  cmp     [rax+10C80h], di
0x1400d2017  jnz     loc_1400D218D
0x1400d201d  cmp     [rbx+0A8Ch], edi
0x1400d2023  jnz     short loc_1400D2070
0x1400d2025  cmp     [rbx+0AA0h], edi
0x1400d202b  jnz     short loc_1400D2070
0x1400d202d  cmp     [rbx+0AA4h], edi
0x1400d2033  jnz     short loc_1400D2070
0x1400d2035  mov     [rsp+88h+var_58], edi
0x1400d2039  lea     r15d, [rdi+1]
0x1400d203d  mov     [rsp+88h+var_60], edi
0x1400d2041  lea     r8d, [rdi+4]
0x1400d2045  xor     r9d, r9d
0x1400d2048  mov     [rsp+88h+arg_18], r15d
0x1400d2050  lea     rdx, [rsp+88h+arg_18]
0x1400d2058  mov     [rsp+88h+var_68], rdi
0x1400d205d  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1400d2064  call    cs:__imp_ZwUpdateWnfStateData
0x1400d206b  nop     dword ptr [rax+rax+00h]
0x1400d2070  xor     ecx, ecx
0x1400d2072  call    DrvChangeD3RequestsState
0x1400d2077  call    ?UserSessionSwitchBlock_Start@@YAJXZ; UserSessionSwitchBlock_Start(void)
0x1400d207c  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400d2081  test    rax, rax
0x1400d2084  jz      short loc_1400D20AB
0x1400d2086  mov     rax, [rax+1E8h]
0x1400d208d  test    rax, rax
0x1400d2090  jz      short loc_1400D20AB
0x1400d2092  mov     rax, [rax+8]
0x1400d2096  test    rax, rax
0x1400d2099  jz      short loc_1400D20AB
0x1400d209b  mov     rax, [rax]
0x1400d209e  mov     ecx, [rax+40h]
0x1400d20a1  test    cl, 1
0x1400d20a4  jz      short loc_1400D20AB
0x1400d20a6  call    DCompositionForceRender
0x1400d20ab  xor     edx, edx
0x1400d20ad  xor     r9d, r9d
0x1400d20b0  xor     r8d, r8d
0x1400d20b3  lea     ecx, [rdx+0Dh]
0x1400d20b6  call    DrvDxgkLogCodePointPacket
0x1400d20bb  call    cs:__imp_W32GetUserSessionState
0x1400d20c2  nop     dword ptr [rax+rax+00h]
0x1400d20c7  cmp     [rax+4B10h], rdi
0x1400d20ce  jz      short loc_1400D20E0
0x1400d20d0  call    IsSetPointerSupported
0x1400d20d5  test    eax, eax
0x1400d20d7  js      short loc_1400D20E0
0x1400d20d9  xor     ecx, ecx
0x1400d20db  call    SetPointer
0x1400d20e0  mov     ecx, r14d
0x1400d20e3  call    cs:__imp_DisplayRestoreVidPnJournalBegin
0x1400d20ea  nop     dword ptr [rax+rax+00h]
0x1400d20ef  call    cs:__imp_W32GetUserSessionState
0x1400d20f6  nop     dword ptr [rax+rax+00h]
0x1400d20fb  mov     edx, 50h ; 'P'
0x1400d2100  mov     rcx, [rax+1F8h]
0x1400d2107  call    ?ArmPowerWatchdog@@YAXPEAXW4_POWER_WATCHDOG_TYPE@@@Z; ArmPowerWatchdog(void *,_POWER_WATCHDOG_TYPE)
0x1400d210c  call    cs:__imp_W32GetUserSessionState
0x1400d2113  nop     dword ptr [rax+rax+00h]
0x1400d2118  xor     r8d, r8d
0x1400d211b  mov     r9, r13
0x1400d211e  mov     rcx, [rax+0DDA8h]
0x1400d2125  lea     edx, [r8+1]
0x1400d2129  mov     rcx, [rcx+10h]
0x1400d212d  call    DrvSetMonitorPowerState
0x1400d2132  call    cs:__imp_W32GetUserSessionState
0x1400d2139  nop     dword ptr [rax+rax+00h]
0x1400d213e  mov     rcx, [rax+1F8h]
0x1400d2145  call    ?DisarmPowerWatchdog@@YAXPEAXW4_POWER_WATCHDOG_TYPE@@@Z; DisarmPowerWatchdog(void *,_POWER_WATCHDOG_TYPE)
0x1400d214a  mov     rcx, r13
0x1400d214d  call    cs:__imp_DisplayRestoreVidPnJournalFinalize
0x1400d2154  nop     dword ptr [rax+rax+00h]
0x1400d2159  call    cs:__imp_W32GetUserSessionState
0x1400d2160  nop     dword ptr [rax+rax+00h]
0x1400d2165  cmp     [rax+4B10h], rdi
0x1400d216c  jz      short loc_1400D2181
0x1400d216e  call    IsSetPointerSupported
0x1400d2173  test    eax, eax
0x1400d2175  js      short loc_1400D2181
0x1400d2177  mov     ecx, 1
0x1400d217c  call    SetPointer
0x1400d2181  call    ?UserSessionSwitchBlock_End@@YAXXZ; UserSessionSwitchBlock_End(void)
0x1400d2186  mov     cl, 1
0x1400d2188  call    DrvChangeD3RequestsState
0x1400d218d  mov     edi, 1
0x1400d2192  call    PowerUnDimMonitor
0x1400d2197  cmp     dword ptr [rbx+0B18h], 2
0x1400d219e  jz      short loc_1400D21A8
0x1400d21a0  xor     ebx, ebx
0x1400d21a2  test    edi, edi
0x1400d21a4  jnz     short loc_1400D21AA
0x1400d21a6  jmp     short loc_1400D21BA
0x1400d21a8  xor     ebx, ebx
0x1400d21aa  mov     r8d, r12d; int
0x1400d21ad  mov     edx, r14d; enum POWER_MONITOR_REQUEST_REASON
0x1400d21b0  mov     ecx, 1; enum _MONITOR_DISPLAY_STATE
0x1400d21b5  call    ?UpdateDisplayState@@YAXW4_MONITOR_DISPLAY_STATE@@W4POWER_MONITOR_REQUEST_REASON@@HH@Z; UpdateDisplayState(_MONITOR_DISPLAY_STATE,POWER_MONITOR_REQUEST_REASON,int,int)
0x1400d21ba  test    esi, esi
0x1400d21bc  jnz     short loc_1400D2219
0x1400d21be  call    cs:__imp_W32GetUserSessionState
0x1400d21c5  nop     dword ptr [rax+rax+00h]
0x1400d21ca  cmp     [rax+4B10h], rbx
0x1400d21d1  jz      short loc_1400D2219
0x1400d21d3  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d21da  nop     dword ptr [rax+rax+00h]
0x1400d21df  mov     rcx, [rax+30h]
0x1400d21e3  mov     rax, [rcx+820h]
0x1400d21ea  test    rax, rax
0x1400d21ed  jz      short loc_1400D2219
0x1400d21ef  call    _guard_dispatch_icall
0x1400d21f4  test    eax, eax
0x1400d21f6  js      short loc_1400D2219
0x1400d21f8  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d21ff  nop     dword ptr [rax+rax+00h]
0x1400d2204  mov     rcx, [rax+30h]
0x1400d2208  mov     rax, [rcx+828h]
0x1400d220f  test    rax, rax
0x1400d2212  jz      short loc_1400D2219
0x1400d2214  call    _guard_dispatch_icall
0x1400d2219  test    r15d, r15d
0x1400d221c  jz      short loc_1400D2258
0x1400d221e  xor     r9d, r9d
0x1400d2221  mov     [rsp+88h+var_58], ebx
0x1400d2225  mov     [rsp+88h+var_60], ebx
0x1400d2229  lea     rdx, [rsp+88h+arg_18]
0x1400d2231  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1400d2238  mov     [rsp+88h+arg_18], 3
0x1400d2243  mov     [rsp+88h+var_68], rbx
0x1400d2248  lea     r8d, [r9+4]
0x1400d224c  call    cs:__imp_ZwUpdateWnfStateData
0x1400d2253  nop     dword ptr [rax+rax+00h]
0x1400d2258  mov     ecx, ebp
0x1400d225a  call    EtwTracePowerOnMonitorEnd
0x1400d225f  add     rsp, 48h
0x1400d2263  pop     r15
0x1400d2265  pop     r14
0x1400d2267  pop     r13
0x1400d2269  pop     r12
0x1400d226b  pop     rdi
0x1400d226c  pop     rsi
0x1400d226d  pop     rbp
0x1400d226e  pop     rbx
0x1400d226f  retn
```
