# PowerOnMonitor

- ea: `0x1400a8620`
- end: `0x1400a8901`
- name: `PowerOnMonitor`
- size: `737`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400a65c8`
- `0x1400a76b8`

## callees

- `0x140076b80`
- `0x1400a5774`
- `0x1400a5860`
- `0x1400a606c`
- `0x1400a8414`
- `0x1400a8620`
- `0x1400a8908`
- `0x1400a8980`
- `0x1400a89ac`
- `0x1400a8a38`
- `0x1400d0fc4`
- `0x1400fdec4`
- `0x14011dc28`
- `0x140161a70`
- `0x14016b5a0`
- `0x140174a34`
- `0x14017b724`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400a86f4`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400a88dc`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400a86f4`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400a88dc`
- `watchdog!DisplayRestoreVidPnJournalFinalize` at `0x1400a87dd`
- `watchdog!DisplayRestoreVidPnJournalFinalize` at `0x1400a87dd`
- `watchdog!DisplayRestoreVidPnJournalBegin` at `0x1400a8773`
- `watchdog!DisplayRestoreVidPnJournalBegin` at `0x1400a8773`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400a8863`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400a8888`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400a8863`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400a8888`
- `WIN32K!W32GetUserSessionState` at `0x1400a863a`
- `WIN32K!W32GetUserSessionState` at `0x1400a8658`
- `WIN32K!W32GetUserSessionState` at `0x1400a8694`
- `WIN32K!W32GetUserSessionState` at `0x1400a874b`
- `WIN32K!W32GetUserSessionState` at `0x1400a877f`
- `WIN32K!W32GetUserSessionState` at `0x1400a879c`
- `WIN32K!W32GetUserSessionState` at `0x1400a87c2`
- `WIN32K!W32GetUserSessionState` at `0x1400a87e9`
- `WIN32K!W32GetUserSessionState` at `0x1400a884e`
- `WIN32K!W32GetUserSessionState` at `0x1400a863a`
- `WIN32K!W32GetUserSessionState` at `0x1400a8658`
- `WIN32K!W32GetUserSessionState` at `0x1400a8694`
- `WIN32K!W32GetUserSessionState` at `0x1400a874b`
- `WIN32K!W32GetUserSessionState` at `0x1400a877f`
- `WIN32K!W32GetUserSessionState` at `0x1400a879c`
- `WIN32K!W32GetUserSessionState` at `0x1400a87c2`
- `WIN32K!W32GetUserSessionState` at `0x1400a87e9`
- `WIN32K!W32GetUserSessionState` at `0x1400a884e`

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
0x1400a8620  push    rbx
0x1400a8622  push    rbp
0x1400a8623  push    rsi
0x1400a8624  push    rdi
0x1400a8625  push    r12
0x1400a8627  push    r13
0x1400a8629  push    r14
0x1400a862b  push    r15
0x1400a862d  sub     rsp, 48h
0x1400a8631  mov     ebp, r8d
0x1400a8634  mov     r13, rdx
0x1400a8637  mov     r14d, ecx
0x1400a863a  call    cs:__imp_W32GetUserSessionState
0x1400a8641  nop     dword ptr [rax+rax+00h]
0x1400a8646  xor     r12d, r12d
0x1400a8649  mov     rbx, rax
0x1400a864c  mov     esi, [rax+0A8Ch]
0x1400a8652  test    esi, esi
0x1400a8654  setz    r12b
0x1400a8658  call    cs:__imp_W32GetUserSessionState
0x1400a865f  nop     dword ptr [rax+rax+00h]
0x1400a8664  mov     r8, [rax+0A68h]
0x1400a866b  mov     dl, [r8]
0x1400a866e  test    dl, dl
0x1400a8670  jnz     loc_1400A88EF
0x1400a8676  mov     ecx, ebp
0x1400a8678  xor     edi, edi
0x1400a867a  xor     r15d, r15d
0x1400a867d  call    EtwTracPowerOnMonitoreBegin
0x1400a8682  mov     edx, ebp
0x1400a8684  mov     ecx, r14d
0x1400a8687  call    ?PowerOnMonitor@Power@InputTraceLogging@@SAXW4POWER_MONITOR_REQUEST_REASON@@W4_POWERON_LOC@@@Z; InputTraceLogging::Power::PowerOnMonitor(POWER_MONITOR_REQUEST_REASON,_POWERON_LOC)
0x1400a868c  test    esi, esi
0x1400a868e  jnz     loc_1400A8822
0x1400a8694  call    cs:__imp_W32GetUserSessionState
0x1400a869b  nop     dword ptr [rax+rax+00h]
0x1400a86a0  cmp     [rax+10C80h], di
0x1400a86a7  jnz     loc_1400A881D
0x1400a86ad  cmp     [rbx+0A8Ch], edi
0x1400a86b3  jnz     short loc_1400A8700
0x1400a86b5  cmp     [rbx+0AA0h], edi
0x1400a86bb  jnz     short loc_1400A8700
0x1400a86bd  cmp     [rbx+0AA4h], edi
0x1400a86c3  jnz     short loc_1400A8700
0x1400a86c5  mov     [rsp+88h+var_58], edi
0x1400a86c9  lea     r15d, [rdi+1]
0x1400a86cd  mov     [rsp+88h+var_60], edi
0x1400a86d1  lea     r8d, [rdi+4]
0x1400a86d5  xor     r9d, r9d
0x1400a86d8  mov     [rsp+88h+arg_18], r15d
0x1400a86e0  lea     rdx, [rsp+88h+arg_18]
0x1400a86e8  mov     [rsp+88h+var_68], rdi
0x1400a86ed  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1400a86f4  call    cs:__imp_ZwUpdateWnfStateData
0x1400a86fb  nop     dword ptr [rax+rax+00h]
0x1400a8700  xor     ecx, ecx
0x1400a8702  call    DrvChangeD3RequestsState
0x1400a8707  call    ?UserSessionSwitchBlock_Start@@YAJXZ; UserSessionSwitchBlock_Start(void)
0x1400a870c  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400a8711  test    rax, rax
0x1400a8714  jz      short loc_1400A873B
0x1400a8716  mov     rax, [rax+1E8h]
0x1400a871d  test    rax, rax
0x1400a8720  jz      short loc_1400A873B
0x1400a8722  mov     rax, [rax+8]
0x1400a8726  test    rax, rax
0x1400a8729  jz      short loc_1400A873B
0x1400a872b  mov     rax, [rax]
0x1400a872e  mov     ecx, [rax+40h]
0x1400a8731  test    cl, 1
0x1400a8734  jz      short loc_1400A873B
0x1400a8736  call    DCompositionForceRender
0x1400a873b  xor     edx, edx
0x1400a873d  xor     r9d, r9d
0x1400a8740  xor     r8d, r8d
0x1400a8743  lea     ecx, [rdx+0Dh]
0x1400a8746  call    DrvDxgkLogCodePointPacket
0x1400a874b  call    cs:__imp_W32GetUserSessionState
0x1400a8752  nop     dword ptr [rax+rax+00h]
0x1400a8757  cmp     [rax+4B10h], rdi
0x1400a875e  jz      short loc_1400A8770
0x1400a8760  call    IsSetPointerSupported
0x1400a8765  test    eax, eax
0x1400a8767  js      short loc_1400A8770
0x1400a8769  xor     ecx, ecx
0x1400a876b  call    SetPointer
0x1400a8770  mov     ecx, r14d
0x1400a8773  call    cs:__imp_DisplayRestoreVidPnJournalBegin
0x1400a877a  nop     dword ptr [rax+rax+00h]
0x1400a877f  call    cs:__imp_W32GetUserSessionState
0x1400a8786  nop     dword ptr [rax+rax+00h]
0x1400a878b  mov     edx, 50h ; 'P'
0x1400a8790  mov     rcx, [rax+1F8h]
0x1400a8797  call    ?ArmPowerWatchdog@@YAXPEAXW4_POWER_WATCHDOG_TYPE@@@Z; ArmPowerWatchdog(void *,_POWER_WATCHDOG_TYPE)
0x1400a879c  call    cs:__imp_W32GetUserSessionState
0x1400a87a3  nop     dword ptr [rax+rax+00h]
0x1400a87a8  xor     r8d, r8d
0x1400a87ab  mov     r9, r13
0x1400a87ae  mov     rcx, [rax+0DDA8h]
0x1400a87b5  lea     edx, [r8+1]
0x1400a87b9  mov     rcx, [rcx+10h]
0x1400a87bd  call    DrvSetMonitorPowerState
0x1400a87c2  call    cs:__imp_W32GetUserSessionState
0x1400a87c9  nop     dword ptr [rax+rax+00h]
0x1400a87ce  mov     rcx, [rax+1F8h]
0x1400a87d5  call    ?DisarmPowerWatchdog@@YAXPEAXW4_POWER_WATCHDOG_TYPE@@@Z; DisarmPowerWatchdog(void *,_POWER_WATCHDOG_TYPE)
0x1400a87da  mov     rcx, r13
0x1400a87dd  call    cs:__imp_DisplayRestoreVidPnJournalFinalize
0x1400a87e4  nop     dword ptr [rax+rax+00h]
0x1400a87e9  call    cs:__imp_W32GetUserSessionState
0x1400a87f0  nop     dword ptr [rax+rax+00h]
0x1400a87f5  cmp     [rax+4B10h], rdi
0x1400a87fc  jz      short loc_1400A8811
0x1400a87fe  call    IsSetPointerSupported
0x1400a8803  test    eax, eax
0x1400a8805  js      short loc_1400A8811
0x1400a8807  mov     ecx, 1
0x1400a880c  call    SetPointer
0x1400a8811  call    ?UserSessionSwitchBlock_End@@YAXXZ; UserSessionSwitchBlock_End(void)
0x1400a8816  mov     cl, 1
0x1400a8818  call    DrvChangeD3RequestsState
0x1400a881d  mov     edi, 1
0x1400a8822  call    PowerUnDimMonitor
0x1400a8827  cmp     dword ptr [rbx+0B18h], 2
0x1400a882e  jz      short loc_1400A8838
0x1400a8830  xor     ebx, ebx
0x1400a8832  test    edi, edi
0x1400a8834  jnz     short loc_1400A883A
0x1400a8836  jmp     short loc_1400A884A
0x1400a8838  xor     ebx, ebx
0x1400a883a  mov     r8d, r12d; int
0x1400a883d  mov     edx, r14d; enum POWER_MONITOR_REQUEST_REASON
0x1400a8840  mov     ecx, 1; enum _MONITOR_DISPLAY_STATE
0x1400a8845  call    ?UpdateDisplayState@@YAXW4_MONITOR_DISPLAY_STATE@@W4POWER_MONITOR_REQUEST_REASON@@HH@Z; UpdateDisplayState(_MONITOR_DISPLAY_STATE,POWER_MONITOR_REQUEST_REASON,int,int)
0x1400a884a  test    esi, esi
0x1400a884c  jnz     short loc_1400A88A9
0x1400a884e  call    cs:__imp_W32GetUserSessionState
0x1400a8855  nop     dword ptr [rax+rax+00h]
0x1400a885a  cmp     [rax+4B10h], rbx
0x1400a8861  jz      short loc_1400A88A9
0x1400a8863  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400a886a  nop     dword ptr [rax+rax+00h]
0x1400a886f  mov     rcx, [rax+30h]
0x1400a8873  mov     rax, [rcx+820h]
0x1400a887a  test    rax, rax
0x1400a887d  jz      short loc_1400A88A9
0x1400a887f  call    _guard_dispatch_icall
0x1400a8884  test    eax, eax
0x1400a8886  js      short loc_1400A88A9
0x1400a8888  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400a888f  nop     dword ptr [rax+rax+00h]
0x1400a8894  mov     rcx, [rax+30h]
0x1400a8898  mov     rax, [rcx+828h]
0x1400a889f  test    rax, rax
0x1400a88a2  jz      short loc_1400A88A9
0x1400a88a4  call    _guard_dispatch_icall
0x1400a88a9  test    r15d, r15d
0x1400a88ac  jz      short loc_1400A88E8
0x1400a88ae  xor     r9d, r9d
0x1400a88b1  mov     [rsp+88h+var_58], ebx
0x1400a88b5  mov     [rsp+88h+var_60], ebx
0x1400a88b9  lea     rdx, [rsp+88h+arg_18]
0x1400a88c1  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1400a88c8  mov     [rsp+88h+arg_18], 3
0x1400a88d3  mov     [rsp+88h+var_68], rbx
0x1400a88d8  lea     r8d, [r9+4]
0x1400a88dc  call    cs:__imp_ZwUpdateWnfStateData
0x1400a88e3  nop     dword ptr [rax+rax+00h]
0x1400a88e8  mov     ecx, ebp
0x1400a88ea  call    EtwTracePowerOnMonitorEnd
0x1400a88ef  add     rsp, 48h
0x1400a88f3  pop     r15
0x1400a88f5  pop     r14
0x1400a88f7  pop     r13
0x1400a88f9  pop     r12
0x1400a88fb  pop     rdi
0x1400a88fc  pop     rsi
0x1400a88fd  pop     rbp
0x1400a88fe  pop     rbx
0x1400a88ff  retn
```
