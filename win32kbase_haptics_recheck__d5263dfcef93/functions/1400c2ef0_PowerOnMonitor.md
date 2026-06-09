# PowerOnMonitor

- ea: `0x1400c2ef0`
- end: `0x1400c31d1`
- name: `PowerOnMonitor`
- size: `737`
- prototype: `__int64 __fastcall(enum POWER_MONITOR_REQUEST_REASON)`
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400c0e98`
- `0x1400c1f88`

## callees

- `0x140060b24`
- `0x1400759e0`
- `0x1400c0044`
- `0x1400c0130`
- `0x1400c093c`
- `0x1400c2ce4`
- `0x1400c2ef0`
- `0x1400c31d8`
- `0x1400c3250`
- `0x1400c327c`
- `0x1400c3308`
- `0x140102654`
- `0x14011d8b8`
- `0x1401611d0`
- `0x14016ada0`
- `0x140173cd4`
- `0x14017abc4`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400c2fc4`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400c31ac`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400c2fc4`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400c31ac`
- `watchdog!DisplayRestoreVidPnJournalFinalize` at `0x1400c30ad`
- `watchdog!DisplayRestoreVidPnJournalFinalize` at `0x1400c30ad`
- `watchdog!DisplayRestoreVidPnJournalBegin` at `0x1400c3043`
- `watchdog!DisplayRestoreVidPnJournalBegin` at `0x1400c3043`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400c3133`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400c3158`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400c3133`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400c3158`
- `WIN32K!W32GetUserSessionState` at `0x1400c2f0a`
- `WIN32K!W32GetUserSessionState` at `0x1400c2f28`
- `WIN32K!W32GetUserSessionState` at `0x1400c2f64`
- `WIN32K!W32GetUserSessionState` at `0x1400c301b`
- `WIN32K!W32GetUserSessionState` at `0x1400c304f`
- `WIN32K!W32GetUserSessionState` at `0x1400c306c`
- `WIN32K!W32GetUserSessionState` at `0x1400c3092`
- `WIN32K!W32GetUserSessionState` at `0x1400c30b9`
- `WIN32K!W32GetUserSessionState` at `0x1400c311e`
- `WIN32K!W32GetUserSessionState` at `0x1400c2f0a`
- `WIN32K!W32GetUserSessionState` at `0x1400c2f28`
- `WIN32K!W32GetUserSessionState` at `0x1400c2f64`
- `WIN32K!W32GetUserSessionState` at `0x1400c301b`
- `WIN32K!W32GetUserSessionState` at `0x1400c304f`
- `WIN32K!W32GetUserSessionState` at `0x1400c306c`
- `WIN32K!W32GetUserSessionState` at `0x1400c3092`
- `WIN32K!W32GetUserSessionState` at `0x1400c30b9`
- `WIN32K!W32GetUserSessionState` at `0x1400c311e`

## pseudocode

```c
__int64 __fastcall PowerOnMonitor(__int64 a1, __int64 a2, unsigned int a3)
{
  enum POWER_MONITOR_REQUEST_REASON v5; // r14d
  _DWORD *UserSessionState; // rbx
  int v7; // esi
  __int64 v8; // rcx
  __int64 result; // rax
  int v10; // edi
  int v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  struct tagTHREADINFO *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v37; // r9d
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  int (__fastcall *v42)(__int64, __int64, __int64); // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  void (__fastcall *v47)(__int64, __int64, __int64); // rax
  int v48; // [rsp+A8h] [rbp+20h] BYREF

  v5 = (int)a1;
  UserSessionState = (_DWORD *)W32GetUserSessionState(a1);
  v7 = UserSessionState[675];
  result = W32GetUserSessionState(v8);
  if ( !**(_BYTE **)(result + 2664) )
  {
    v10 = 0;
    v11 = 0;
    EtwTracPowerOnMonitoreBegin(a3);
    InputTraceLogging::Power::PowerOnMonitor((unsigned int)v5, a3);
    if ( !v7 )
    {
      if ( !*(_WORD *)(W32GetUserSessionState(v13) + 68736) )
      {
        if ( !UserSessionState[675] && !UserSessionState[680] && !UserSessionState[681] )
        {
          v11 = 1;
          v48 = 1;
          ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v48, 4);
        }
        DrvChangeD3RequestsState(0);
        UserSessionSwitchBlock_Start();
        v15 = PtiCurrent();
        if ( v15 )
        {
          v18 = *((_QWORD *)v15 + 61);
          if ( v18 )
          {
            v19 = *(_QWORD *)(v18 + 8);
            if ( v19 )
            {
              v20 = *(unsigned int *)(*(_QWORD *)v19 + 64LL);
              if ( (v20 & 1) != 0 )
                DCompositionForceRender(v20, v16, v17);
            }
          }
        }
        DrvDxgkLogCodePointPacket(13, 0, 0, 0);
        if ( *(_QWORD *)(W32GetUserSessionState(v21) + 19216) && (int)IsSetPointerSupported(v23, v22, v24) >= 0 )
          SetPointer(0);
        DisplayRestoreVidPnJournalBegin((unsigned int)v5);
        v26 = W32GetUserSessionState(v25);
        ArmPowerWatchdog(*(_QWORD *)(v26 + 504), 80);
        v28 = W32GetUserSessionState(v27);
        DrvSetMonitorPowerState(*(_QWORD *)(*(_QWORD *)(v28 + 56744) + 16LL), 1, 0, a2);
        v30 = W32GetUserSessionState(v29);
        DisarmPowerWatchdog(*(_QWORD *)(v30 + 504));
        DisplayRestoreVidPnJournalFinalize(a2);
        if ( *(_QWORD *)(W32GetUserSessionState(v31) + 19216) && (int)IsSetPointerSupported(v33, v32, v34) >= 0 )
          SetPointer(1);
        UserSessionSwitchBlock_End();
        LOBYTE(v35) = 1;
        DrvChangeD3RequestsState(v35);
      }
      v10 = 1;
    }
    PowerUnDimMonitor(v13, v12, v14);
    if ( UserSessionState[710] == 2 || v10 )
      UpdateDisplayState(PowerMonitorOn, v5, v7 == 0, v37);
    if ( !v7 )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v36) + 19216) )
      {
        v40 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v38) + 48);
        v42 = *(int (__fastcall **)(__int64, __int64, __int64))(v40 + 2080);
        if ( v42 )
        {
          if ( v42(v40, v39, v41) >= 0 )
          {
            v45 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v43) + 48);
            v47 = *(void (__fastcall **)(__int64, __int64, __int64))(v45 + 2088);
            if ( v47 )
              v47(v45, v44, v46);
          }
        }
      }
    }
    if ( v11 )
    {
      v48 = 3;
      ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v48, 4);
    }
    return EtwTracePowerOnMonitorEnd(a3);
  }
  return result;
}

```

## disassembly

```asm
0x1400c2ef0  push    rbx
0x1400c2ef2  push    rbp
0x1400c2ef3  push    rsi
0x1400c2ef4  push    rdi
0x1400c2ef5  push    r12
0x1400c2ef7  push    r13
0x1400c2ef9  push    r14
0x1400c2efb  push    r15
0x1400c2efd  sub     rsp, 48h
0x1400c2f01  mov     ebp, r8d
0x1400c2f04  mov     r13, rdx
0x1400c2f07  mov     r14d, ecx
0x1400c2f0a  call    cs:__imp_W32GetUserSessionState
0x1400c2f11  nop     dword ptr [rax+rax+00h]
0x1400c2f16  xor     r12d, r12d
0x1400c2f19  mov     rbx, rax
0x1400c2f1c  mov     esi, [rax+0A8Ch]
0x1400c2f22  test    esi, esi
0x1400c2f24  setz    r12b
0x1400c2f28  call    cs:__imp_W32GetUserSessionState
0x1400c2f2f  nop     dword ptr [rax+rax+00h]
0x1400c2f34  mov     r8, [rax+0A68h]
0x1400c2f3b  mov     dl, [r8]
0x1400c2f3e  test    dl, dl
0x1400c2f40  jnz     loc_1400C31BF
0x1400c2f46  mov     ecx, ebp
0x1400c2f48  xor     edi, edi
0x1400c2f4a  xor     r15d, r15d
0x1400c2f4d  call    EtwTracPowerOnMonitoreBegin
0x1400c2f52  mov     edx, ebp
0x1400c2f54  mov     ecx, r14d
0x1400c2f57  call    ?PowerOnMonitor@Power@InputTraceLogging@@SAXW4POWER_MONITOR_REQUEST_REASON@@W4_POWERON_LOC@@@Z; InputTraceLogging::Power::PowerOnMonitor(POWER_MONITOR_REQUEST_REASON,_POWERON_LOC)
0x1400c2f5c  test    esi, esi
0x1400c2f5e  jnz     loc_1400C30F2
0x1400c2f64  call    cs:__imp_W32GetUserSessionState
0x1400c2f6b  nop     dword ptr [rax+rax+00h]
0x1400c2f70  cmp     [rax+10C80h], di
0x1400c2f77  jnz     loc_1400C30ED
0x1400c2f7d  cmp     [rbx+0A8Ch], edi
0x1400c2f83  jnz     short loc_1400C2FD0
0x1400c2f85  cmp     [rbx+0AA0h], edi
0x1400c2f8b  jnz     short loc_1400C2FD0
0x1400c2f8d  cmp     [rbx+0AA4h], edi
0x1400c2f93  jnz     short loc_1400C2FD0
0x1400c2f95  mov     [rsp+88h+var_58], edi
0x1400c2f99  lea     r15d, [rdi+1]
0x1400c2f9d  mov     [rsp+88h+var_60], edi
0x1400c2fa1  lea     r8d, [rdi+4]
0x1400c2fa5  xor     r9d, r9d
0x1400c2fa8  mov     [rsp+88h+arg_18], r15d
0x1400c2fb0  lea     rdx, [rsp+88h+arg_18]
0x1400c2fb8  mov     [rsp+88h+var_68], rdi
0x1400c2fbd  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1400c2fc4  call    cs:__imp_ZwUpdateWnfStateData
0x1400c2fcb  nop     dword ptr [rax+rax+00h]
0x1400c2fd0  xor     ecx, ecx
0x1400c2fd2  call    DrvChangeD3RequestsState
0x1400c2fd7  call    ?UserSessionSwitchBlock_Start@@YAJXZ; UserSessionSwitchBlock_Start(void)
0x1400c2fdc  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400c2fe1  test    rax, rax
0x1400c2fe4  jz      short loc_1400C300B
0x1400c2fe6  mov     rax, [rax+1E8h]
0x1400c2fed  test    rax, rax
0x1400c2ff0  jz      short loc_1400C300B
0x1400c2ff2  mov     rax, [rax+8]
0x1400c2ff6  test    rax, rax
0x1400c2ff9  jz      short loc_1400C300B
0x1400c2ffb  mov     rax, [rax]
0x1400c2ffe  mov     ecx, [rax+40h]
0x1400c3001  test    cl, 1
0x1400c3004  jz      short loc_1400C300B
0x1400c3006  call    DCompositionForceRender
0x1400c300b  xor     edx, edx
0x1400c300d  xor     r9d, r9d
0x1400c3010  xor     r8d, r8d
0x1400c3013  lea     ecx, [rdx+0Dh]
0x1400c3016  call    DrvDxgkLogCodePointPacket
0x1400c301b  call    cs:__imp_W32GetUserSessionState
0x1400c3022  nop     dword ptr [rax+rax+00h]
0x1400c3027  cmp     [rax+4B10h], rdi
0x1400c302e  jz      short loc_1400C3040
0x1400c3030  call    IsSetPointerSupported
0x1400c3035  test    eax, eax
0x1400c3037  js      short loc_1400C3040
0x1400c3039  xor     ecx, ecx
0x1400c303b  call    SetPointer
0x1400c3040  mov     ecx, r14d
0x1400c3043  call    cs:__imp_DisplayRestoreVidPnJournalBegin
0x1400c304a  nop     dword ptr [rax+rax+00h]
0x1400c304f  call    cs:__imp_W32GetUserSessionState
0x1400c3056  nop     dword ptr [rax+rax+00h]
0x1400c305b  mov     edx, 50h ; 'P'
0x1400c3060  mov     rcx, [rax+1F8h]
0x1400c3067  call    ?ArmPowerWatchdog@@YAXPEAXW4_POWER_WATCHDOG_TYPE@@@Z; ArmPowerWatchdog(void *,_POWER_WATCHDOG_TYPE)
0x1400c306c  call    cs:__imp_W32GetUserSessionState
0x1400c3073  nop     dword ptr [rax+rax+00h]
0x1400c3078  xor     r8d, r8d
0x1400c307b  mov     r9, r13
0x1400c307e  mov     rcx, [rax+0DDA8h]
0x1400c3085  lea     edx, [r8+1]
0x1400c3089  mov     rcx, [rcx+10h]
0x1400c308d  call    DrvSetMonitorPowerState
0x1400c3092  call    cs:__imp_W32GetUserSessionState
0x1400c3099  nop     dword ptr [rax+rax+00h]
0x1400c309e  mov     rcx, [rax+1F8h]
0x1400c30a5  call    ?DisarmPowerWatchdog@@YAXPEAXW4_POWER_WATCHDOG_TYPE@@@Z; DisarmPowerWatchdog(void *,_POWER_WATCHDOG_TYPE)
0x1400c30aa  mov     rcx, r13
0x1400c30ad  call    cs:__imp_DisplayRestoreVidPnJournalFinalize
0x1400c30b4  nop     dword ptr [rax+rax+00h]
0x1400c30b9  call    cs:__imp_W32GetUserSessionState
0x1400c30c0  nop     dword ptr [rax+rax+00h]
0x1400c30c5  cmp     [rax+4B10h], rdi
0x1400c30cc  jz      short loc_1400C30E1
0x1400c30ce  call    IsSetPointerSupported
0x1400c30d3  test    eax, eax
0x1400c30d5  js      short loc_1400C30E1
0x1400c30d7  mov     ecx, 1
0x1400c30dc  call    SetPointer
0x1400c30e1  call    ?UserSessionSwitchBlock_End@@YAXXZ; UserSessionSwitchBlock_End(void)
0x1400c30e6  mov     cl, 1
0x1400c30e8  call    DrvChangeD3RequestsState
0x1400c30ed  mov     edi, 1
0x1400c30f2  call    PowerUnDimMonitor
0x1400c30f7  cmp     dword ptr [rbx+0B18h], 2
0x1400c30fe  jz      short loc_1400C3108
0x1400c3100  xor     ebx, ebx
0x1400c3102  test    edi, edi
0x1400c3104  jnz     short loc_1400C310A
0x1400c3106  jmp     short loc_1400C311A
0x1400c3108  xor     ebx, ebx
0x1400c310a  mov     r8d, r12d; int
0x1400c310d  mov     edx, r14d; enum POWER_MONITOR_REQUEST_REASON
0x1400c3110  mov     ecx, 1; enum _MONITOR_DISPLAY_STATE
0x1400c3115  call    ?UpdateDisplayState@@YAXW4_MONITOR_DISPLAY_STATE@@W4POWER_MONITOR_REQUEST_REASON@@HH@Z; UpdateDisplayState(_MONITOR_DISPLAY_STATE,POWER_MONITOR_REQUEST_REASON,int,int)
0x1400c311a  test    esi, esi
0x1400c311c  jnz     short loc_1400C3179
0x1400c311e  call    cs:__imp_W32GetUserSessionState
0x1400c3125  nop     dword ptr [rax+rax+00h]
0x1400c312a  cmp     [rax+4B10h], rbx
0x1400c3131  jz      short loc_1400C3179
0x1400c3133  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400c313a  nop     dword ptr [rax+rax+00h]
0x1400c313f  mov     rcx, [rax+30h]
0x1400c3143  mov     rax, [rcx+820h]
0x1400c314a  test    rax, rax
0x1400c314d  jz      short loc_1400C3179
0x1400c314f  call    _guard_dispatch_icall
0x1400c3154  test    eax, eax
0x1400c3156  js      short loc_1400C3179
0x1400c3158  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400c315f  nop     dword ptr [rax+rax+00h]
0x1400c3164  mov     rcx, [rax+30h]
0x1400c3168  mov     rax, [rcx+828h]
0x1400c316f  test    rax, rax
0x1400c3172  jz      short loc_1400C3179
0x1400c3174  call    _guard_dispatch_icall
0x1400c3179  test    r15d, r15d
0x1400c317c  jz      short loc_1400C31B8
0x1400c317e  xor     r9d, r9d
0x1400c3181  mov     [rsp+88h+var_58], ebx
0x1400c3185  mov     [rsp+88h+var_60], ebx
0x1400c3189  lea     rdx, [rsp+88h+arg_18]
0x1400c3191  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1400c3198  mov     [rsp+88h+arg_18], 3
0x1400c31a3  mov     [rsp+88h+var_68], rbx
0x1400c31a8  lea     r8d, [r9+4]
0x1400c31ac  call    cs:__imp_ZwUpdateWnfStateData
0x1400c31b3  nop     dword ptr [rax+rax+00h]
0x1400c31b8  mov     ecx, ebp
0x1400c31ba  call    EtwTracePowerOnMonitorEnd
0x1400c31bf  add     rsp, 48h
0x1400c31c3  pop     r15
0x1400c31c5  pop     r14
0x1400c31c7  pop     r13
0x1400c31c9  pop     r12
0x1400c31cb  pop     rdi
0x1400c31cc  pop     rsi
0x1400c31cd  pop     rbp
0x1400c31ce  pop     rbx
0x1400c31cf  retn
```
