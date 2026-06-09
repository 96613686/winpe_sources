# PowerOffMonitor

- ea: `0x1401ce0d0`
- end: `0x1401ce52c`
- name: `PowerOffMonitor`
- size: `1116`
- prototype: `__int64 __fastcall(enum POWER_MONITOR_REQUEST_REASON)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400c0e98`
- `0x1400c1f88`

## callees

- `0x140012c80`
- `0x14002a0e4`
- `0x140060b24`
- `0x140073a50`
- `0x140076ef0`
- `0x1400c0044`
- `0x1400c0130`
- `0x14011dda0`
- `0x1401611d0`
- `0x14016ada0`
- `0x1401aa4fc`
- `0x1401cd3d0`
- `0x1401cd6a4`
- `0x1401ce0d0`
- `0x1401d14f0`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401ce30a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401ce30a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ce192`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ce507`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ce192`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ce507`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce1f2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce217`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce26a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce3df`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce408`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce1f2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce217`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce26a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce3df`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ce408`
- `WIN32K!W32GetUserSessionState` at `0x1401ce0ee`
- `WIN32K!W32GetUserSessionState` at `0x1401ce146`
- `WIN32K!W32GetUserSessionState` at `0x1401ce1a9`
- `WIN32K!W32GetUserSessionState` at `0x1401ce1c1`
- `WIN32K!W32GetUserSessionState` at `0x1401ce1d6`
- `WIN32K!W32GetUserSessionState` at `0x1401ce2b2`
- `WIN32K!W32GetUserSessionState` at `0x1401ce3b1`
- `WIN32K!W32GetUserSessionState` at `0x1401ce433`
- `WIN32K!W32GetUserSessionState` at `0x1401ce47f`
- `WIN32K!W32GetUserSessionState` at `0x1401ce4bf`
- `WIN32K!W32GetUserSessionState` at `0x1401ce0ee`
- `WIN32K!W32GetUserSessionState` at `0x1401ce146`
- `WIN32K!W32GetUserSessionState` at `0x1401ce1a9`
- `WIN32K!W32GetUserSessionState` at `0x1401ce1c1`
- `WIN32K!W32GetUserSessionState` at `0x1401ce1d6`
- `WIN32K!W32GetUserSessionState` at `0x1401ce2b2`
- `WIN32K!W32GetUserSessionState` at `0x1401ce3b1`
- `WIN32K!W32GetUserSessionState` at `0x1401ce433`
- `WIN32K!W32GetUserSessionState` at `0x1401ce47f`
- `WIN32K!W32GetUserSessionState` at `0x1401ce4bf`

## pseudocode

```c
void __fastcall PowerOffMonitor(__int64 a1, __int64 a2)
{
  enum POWER_MONITOR_REQUEST_REASON v2; // ebx
  _DWORD *UserSessionState; // rax
  _DWORD *v4; // r14
  int v5; // r12d
  int v6; // r13d
  __int64 v7; // rcx
  int v8; // r9d
  int v9; // r15d
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  int (__fastcall *v15)(__int64, __int64, __int64); // rax
  int (__fastcall *v16)(unsigned int *, __int64 *, int *); // rax
  __int64 v17; // rax
  __int64 v18; // rdi
  unsigned int v19; // esi
  __int64 v20; // rcx
  void (__fastcall *v21)(_QWORD, __int64, __int64, _QWORD, __int64, int, int); // rax
  __int64 v22; // rcx
  __int64 v23; // rsi
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v27; // rax
  _QWORD *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // rcx
  int (*v32)(void); // rax
  __int64 v33; // rdi
  void (__fastcall *v34)(__int64); // rax
  unsigned __int64 v35; // rcx
  __int64 v36; // rax
  unsigned __int64 GlobalTickCountWithSequence; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // [rsp+20h] [rbp-40h]
  int v41; // [rsp+28h] [rbp-38h]
  int v42; // [rsp+30h] [rbp-30h]
  int v43; // [rsp+40h] [rbp-20h] BYREF
  int v44; // [rsp+44h] [rbp-1Ch] BYREF
  __int64 v45; // [rsp+48h] [rbp-18h] BYREF
  __int64 v46; // [rsp+50h] [rbp-10h] BYREF
  int v48; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v49; // [rsp+B8h] [rbp+58h] BYREF

  v2 = (int)a1;
  UserSessionState = (_DWORD *)W32GetUserSessionState(a1);
  v4 = UserSessionState;
  v49 = 0;
  v45 = 0;
  v48 = 0;
  v5 = UserSessionState[675];
  v46 = 0;
  if ( v5 || UserSessionState[680] || UserSessionState[681] )
  {
    v6 = 0;
    InputTraceLogging::Power::PowerOffMonitor(v2);
    if ( !*(_WORD *)(W32GetUserSessionState(v7) + 68736) )
    {
      v9 = 0;
      if ( v2 != MonitorRequestReasonGracePeriod && v2 != MonitorRequestReasonNearProximity )
      {
        v42 = 0;
        v41 = 0;
        v43 = 2;
        v40 = 0;
        ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v43, 4);
        v6 = 1;
      }
      UserSessionSwitchBlock_Start();
      if ( *(_DWORD *)(W32GetUserSessionState(v10) + 42776)
        || !*(_QWORD *)(W32GetUserSessionState(v11) + 19216)
        || (v9 = 1,
            *(_DWORD *)(W32GetUserSessionState(v11) + 42776) = 1,
            v11 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v12) + 48),
            (v15 = *(int (__fastcall **)(__int64, __int64, __int64))(v11 + 2024)) == 0)
        || v15(v11, v13, v14) < 0
        || (v11 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v11) + 48),
            (v16 = *(int (__fastcall **)(unsigned int *, __int64 *, int *))(v11 + 2032)) != 0)
        && v16(&v49, &v45, &v48) >= 0 )
      {
        v17 = v45;
      }
      else
      {
        v17 = 0;
        v45 = 0;
      }
      if ( v48 )
      {
        UserSessionSwitchLeaveCritWithNonPaged(v11);
        v18 = v45;
        v19 = v49;
        v21 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, int, int))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v20) + 48)
                                                                                         + 2040LL);
        if ( v21 )
          v21(v19, v18, 167, 0, v40, v41, v42);
        DrvDxgkLogCodePointPacket(14, v45 != 0, 0, 0);
        v23 = W32GetUserSessionState(v22);
        v24 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
                v23,
                1,
                0,
                _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
        *(_QWORD *)(v23 + 16) = v24;
        if ( v24 )
        {
          v25 = 0;
          if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v24 + 520), 0, 0) & 0x1000000) != 0
            && *(char *)(v24 + 1360) >= 0 )
          {
            CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
            if ( CurrentProcessWin32Process )
            {
              if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
              {
                while ( 1 )
                {
                  v28 = *(_QWORD **)(v23 + 19544);
                  if ( !v28 )
                    break;
                  *(_QWORD *)(v23 + 19544) = v28[2];
                  v27 = *v28;
                  v28[2] = 0;
                  if ( !*(_DWORD *)(v27 + 8) )
                  {
                    v43 = 0x20000;
                    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                  }
                  HMUnlockObject(*v28);
                }
                DestroyDeferredUnlockObjectAssignmentList(v23 + 19576);
                DestroyDeferredUnlockObjectAssignmentList(v23 + 19560);
              }
            }
          }
        }
      }
      else
      {
        DrvDxgkLogCodePointPacket(14, v17 != 0, 0, 0);
      }
      v29 = W32GetUserSessionState(v25);
      LOBYTE(v30) = 1;
      DrvSetMonitorPowerState(*(_QWORD *)(*(_QWORD *)(v29 + 56744) + 16LL), 4, v30, a2);
      if ( v45 )
      {
        v31 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v31) + 48);
        v32 = *(int (**)(void))(v31 + 2048);
        if ( v32 )
        {
          if ( v32() >= 0 )
          {
            v33 = v45;
            v34 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v31) + 48) + 2056LL);
            if ( v34 )
              v34(v33);
          }
        }
      }
      if ( v9 )
        *(_DWORD *)(W32GetUserSessionState(v31) + 42776) = 0;
      UserSessionSwitchBlock_End();
    }
    if ( v2 != MonitorRequestReasonGracePeriod && v2 != MonitorRequestReasonNearProximity )
    {
      v35 = (unsigned __int64)MEMORY[0xFFFFF78000000004] << 32;
      *((_QWORD *)v4 + 349) = (v35 * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
      v36 = W32GetUserSessionState(v35);
      GlobalTickCountWithSequence = CInputGlobals::GetGlobalTickCountWithSequence(*(_QWORD *)(v36 + 3008), 0, &v46);
      v38 = v46;
      if ( GlobalTickCountWithSequence > *((_QWORD *)v4 + 349) )
        v38 = 0;
      *((_QWORD *)v4 + 350) = v38;
    }
    UpdateDisplayState(PowerMonitorOff, v2, v5, v8);
    if ( *(_QWORD *)(W32GetUserSessionState(v39) + 62592) )
      PostWinlogonMessage(1029, 0);
    if ( v6 )
    {
      v44 = 0;
      ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v44, 4);
    }
  }
  else if ( v2 == MonitorRequestReasonNearProximity )
  {
    SetProximityBlocking();
  }
}

```

## disassembly

```asm
0x1401ce0d0  mov     [rsp-38h+arg_0], rbx
0x1401ce0d5  mov     [rsp-38h+arg_8], rdx
0x1401ce0da  push    rbp
0x1401ce0db  push    rsi
0x1401ce0dc  push    rdi
0x1401ce0dd  push    r12
0x1401ce0df  push    r13
0x1401ce0e1  push    r14
0x1401ce0e3  push    r15
0x1401ce0e5  mov     rbp, rsp
0x1401ce0e8  sub     rsp, 60h
0x1401ce0ec  mov     ebx, ecx
0x1401ce0ee  call    cs:__imp_W32GetUserSessionState
0x1401ce0f5  nop     dword ptr [rax+rax+00h]
0x1401ce0fa  xor     edi, edi
0x1401ce0fc  mov     r14, rax
0x1401ce0ff  mov     [rbp+arg_18], edi
0x1401ce102  mov     [rbp+var_18], rdi
0x1401ce106  mov     [rbp+arg_10], edi
0x1401ce109  mov     r12d, [rax+0A8Ch]
0x1401ce110  mov     [rbp+var_10], rdi
0x1401ce114  test    r12d, r12d
0x1401ce117  jnz     short loc_1401CE13C
0x1401ce119  cmp     [rax+0AA0h], edi
0x1401ce11f  jnz     short loc_1401CE13C
0x1401ce121  cmp     [rax+0AA4h], edi
0x1401ce127  jnz     short loc_1401CE13C
0x1401ce129  cmp     ebx, 16h
0x1401ce12c  jnz     loc_1401CE513
0x1401ce132  call    ?SetProximityBlocking@@YAXXZ; SetProximityBlocking(void)
0x1401ce137  jmp     loc_1401CE513
0x1401ce13c  mov     ecx, ebx; enum POWER_MONITOR_REQUEST_REASON
0x1401ce13e  mov     r13d, edi
0x1401ce141  call    ?PowerOffMonitor@Power@InputTraceLogging@@SAXW4POWER_MONITOR_REQUEST_REASON@@@Z; InputTraceLogging::Power::PowerOffMonitor(POWER_MONITOR_REQUEST_REASON)
0x1401ce146  call    cs:__imp_W32GetUserSessionState
0x1401ce14d  nop     dword ptr [rax+rax+00h]
0x1401ce152  cmp     [rax+10C80h], di
0x1401ce159  jnz     loc_1401CE44A
0x1401ce15f  mov     r15d, edi
0x1401ce162  cmp     ebx, 11h
0x1401ce165  jz      short loc_1401CE1A4
0x1401ce167  cmp     ebx, 16h
0x1401ce16a  jz      short loc_1401CE1A4
0x1401ce16c  xor     r9d, r9d
0x1401ce16f  mov     [rsp+60h+var_30], edi
0x1401ce173  mov     [rsp+60h+var_38], edi
0x1401ce177  lea     rdx, [rbp+var_20]
0x1401ce17b  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1401ce182  mov     [rbp+var_20], 2
0x1401ce189  mov     [rsp+60h+var_40], rdi
0x1401ce18e  lea     r8d, [r9+4]
0x1401ce192  call    cs:__imp_ZwUpdateWnfStateData
0x1401ce199  nop     dword ptr [rax+rax+00h]
0x1401ce19e  mov     r13d, 1
0x1401ce1a4  call    ?UserSessionSwitchBlock_Start@@YAJXZ; UserSessionSwitchBlock_Start(void)
0x1401ce1a9  call    cs:__imp_W32GetUserSessionState
0x1401ce1b0  nop     dword ptr [rax+rax+00h]
0x1401ce1b5  cmp     [rax+0A718h], edi
0x1401ce1bb  jnz     loc_1401CE251
0x1401ce1c1  call    cs:__imp_W32GetUserSessionState
0x1401ce1c8  nop     dword ptr [rax+rax+00h]
0x1401ce1cd  cmp     [rax+4B10h], rdi
0x1401ce1d4  jz      short loc_1401CE251
0x1401ce1d6  call    cs:__imp_W32GetUserSessionState
0x1401ce1dd  nop     dword ptr [rax+rax+00h]
0x1401ce1e2  mov     r15d, 1
0x1401ce1e8  mov     dword ptr [rax+0A718h], 1
0x1401ce1f2  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce1f9  nop     dword ptr [rax+rax+00h]
0x1401ce1fe  mov     rcx, [rax+30h]
0x1401ce202  mov     rax, [rcx+7E8h]
0x1401ce209  test    rax, rax
0x1401ce20c  jz      short loc_1401CE251
0x1401ce20e  call    _guard_dispatch_icall
0x1401ce213  test    eax, eax
0x1401ce215  js      short loc_1401CE251
0x1401ce217  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce21e  nop     dword ptr [rax+rax+00h]
0x1401ce223  mov     rcx, [rax+30h]
0x1401ce227  mov     rax, [rcx+7F0h]
0x1401ce22e  test    rax, rax
0x1401ce231  jz      short loc_1401CE248
0x1401ce233  lea     r8, [rbp+arg_10]
0x1401ce237  lea     rdx, [rbp+var_18]
0x1401ce23b  lea     rcx, [rbp+arg_18]
0x1401ce23f  call    _guard_dispatch_icall
0x1401ce244  test    eax, eax
0x1401ce246  jns     short loc_1401CE251
0x1401ce248  mov     rax, rdi
0x1401ce24b  mov     [rbp+var_18], rax
0x1401ce24f  jmp     short loc_1401CE255
0x1401ce251  mov     rax, [rbp+var_18]
0x1401ce255  cmp     [rbp+arg_10], edi
0x1401ce258  jz      loc_1401CE39A
0x1401ce25e  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401ce263  mov     rdi, [rbp+var_18]
0x1401ce267  mov     esi, [rbp+arg_18]
0x1401ce26a  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce271  nop     dword ptr [rax+rax+00h]
0x1401ce276  mov     r8, [rax+30h]
0x1401ce27a  mov     rax, [r8+7F8h]
0x1401ce281  test    rax, rax
0x1401ce284  jz      short loc_1401CE299
0x1401ce286  xor     r9d, r9d
0x1401ce289  mov     r8d, 0A7h
0x1401ce28f  mov     rdx, rdi
0x1401ce292  mov     ecx, esi
0x1401ce294  call    _guard_dispatch_icall
0x1401ce299  xor     edi, edi
0x1401ce29b  cmp     [rbp+var_18], rdi
0x1401ce29f  mov     edx, edi
0x1401ce2a1  setnz   dl
0x1401ce2a4  xor     r9d, r9d
0x1401ce2a7  xor     r8d, r8d
0x1401ce2aa  lea     ecx, [rdi+0Eh]
0x1401ce2ad  call    DrvDxgkLogCodePointPacket
0x1401ce2b2  call    cs:__imp_W32GetUserSessionState
0x1401ce2b9  nop     dword ptr [rax+rax+00h]
0x1401ce2be  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401ce2c5  xor     r8d, r8d
0x1401ce2c8  mov     rcx, rax
0x1401ce2cb  lea     edx, [rdi+1]
0x1401ce2ce  mov     rsi, rax
0x1401ce2d1  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401ce2d6  mov     [rsi+10h], rax
0x1401ce2da  mov     rdx, rax
0x1401ce2dd  test    rax, rax
0x1401ce2e0  jz      loc_1401CE3B1
0x1401ce2e6  mov     ecx, edi
0x1401ce2e8  xor     eax, eax
0x1401ce2ea  lock cmpxchg [rdx+208h], ecx
0x1401ce2f2  bt      eax, 18h
0x1401ce2f6  jnb     loc_1401CE3B1
0x1401ce2fc  mov     al, [rdx+550h]
0x1401ce302  test    al, al
0x1401ce304  js      loc_1401CE3B1
0x1401ce30a  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401ce311  nop     dword ptr [rax+rax+00h]
0x1401ce316  test    rax, rax
0x1401ce319  jz      loc_1401CE3B1
0x1401ce31f  cmp     [rax], rdi
0x1401ce322  jz      loc_1401CE3B1
0x1401ce328  mov     al, [rax+4B0h]
0x1401ce32e  cmp     al, 1
0x1401ce330  jnz     short loc_1401CE3B1
0x1401ce332  jmp     short loc_1401CE374
0x1401ce334  mov     rax, [rdi+10h]
0x1401ce338  mov     [rsi+4C58h], rax
0x1401ce33f  mov     rax, [rdi]
0x1401ce342  mov     qword ptr [rdi+10h], 0
0x1401ce34a  cmp     dword ptr [rax+8], 1
0x1401ce34e  jnb     short loc_1401CE36C
0x1401ce350  mov     [rbp+var_20], 20000h
0x1401ce357  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401ce35e  mov     edx, [rbp+var_20]
0x1401ce361  mov     r8d, 1236h
0x1401ce367  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401ce36c  mov     rcx, [rdi]
0x1401ce36f  call    HMUnlockObject
0x1401ce374  mov     rdi, [rsi+4C58h]
0x1401ce37b  test    rdi, rdi
0x1401ce37e  jnz     short loc_1401CE334
0x1401ce380  lea     rcx, [rsi+4C78h]
0x1401ce387  call    DestroyDeferredUnlockObjectAssignmentList
0x1401ce38c  lea     rcx, [rsi+4C68h]
0x1401ce393  call    DestroyDeferredUnlockObjectAssignmentList
0x1401ce398  jmp     short loc_1401CE3B1
0x1401ce39a  test    rax, rax
0x1401ce39d  mov     edx, edi
0x1401ce39f  setnz   dl
0x1401ce3a2  xor     r9d, r9d
0x1401ce3a5  xor     r8d, r8d
0x1401ce3a8  lea     ecx, [r9+0Eh]
0x1401ce3ac  call    DrvDxgkLogCodePointPacket
0x1401ce3b1  call    cs:__imp_W32GetUserSessionState
0x1401ce3b8  nop     dword ptr [rax+rax+00h]
0x1401ce3bd  mov     r9, [rbp+arg_8]
0x1401ce3c1  mov     r8b, 1
0x1401ce3c4  mov     edx, 4
0x1401ce3c9  mov     rcx, [rax+0DDA8h]
0x1401ce3d0  mov     rcx, [rcx+10h]
0x1401ce3d4  call    DrvSetMonitorPowerState
0x1401ce3d9  cmp     [rbp+var_18], rdi
0x1401ce3dd  jz      short loc_1401CE42E
0x1401ce3df  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce3e6  nop     dword ptr [rax+rax+00h]
0x1401ce3eb  mov     rcx, [rax+30h]
0x1401ce3ef  mov     rax, [rcx+800h]
0x1401ce3f6  test    rax, rax
0x1401ce3f9  jz      short loc_1401CE42E
0x1401ce3fb  call    _guard_dispatch_icall
0x1401ce400  test    eax, eax
0x1401ce402  js      short loc_1401CE42E
0x1401ce404  mov     rdi, [rbp+var_18]
0x1401ce408  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401ce40f  nop     dword ptr [rax+rax+00h]
0x1401ce414  mov     rdx, [rax+30h]
0x1401ce418  mov     rax, [rdx+808h]
0x1401ce41f  test    rax, rax
0x1401ce422  jz      short loc_1401CE42C
0x1401ce424  mov     rcx, rdi
0x1401ce427  call    _guard_dispatch_icall
0x1401ce42c  xor     edi, edi
0x1401ce42e  test    r15d, r15d
0x1401ce431  jz      short loc_1401CE445
0x1401ce433  call    cs:__imp_W32GetUserSessionState
0x1401ce43a  nop     dword ptr [rax+rax+00h]
0x1401ce43f  mov     [rax+0A718h], edi
0x1401ce445  call    ?UserSessionSwitchBlock_End@@YAXXZ; UserSessionSwitchBlock_End(void)
0x1401ce44a  cmp     ebx, 11h
0x1401ce44d  jz      short loc_1401CE4B3
0x1401ce44f  cmp     ebx, 16h
0x1401ce452  jz      short loc_1401CE4B3
0x1401ce454  mov     rax, 0FFFFF78000000004h
0x1401ce45e  mov     ecx, [rax]
0x1401ce460  mov     rax, 0FFFFF78000000320h
0x1401ce46a  shl     rcx, 20h
0x1401ce46e  mov     rax, [rax]
0x1401ce471  shl     rax, 8
0x1401ce475  mul     rcx
0x1401ce478  mov     [r14+0AE8h], rdx
0x1401ce47f  call    cs:__imp_W32GetUserSessionState
0x1401ce486  nop     dword ptr [rax+rax+00h]
0x1401ce48b  lea     r8, [rbp+var_10]
0x1401ce48f  xor     edx, edx
0x1401ce491  mov     rcx, [rax+0BC0h]
0x1401ce498  call    ?GetGlobalTickCountWithSequence@CInputGlobals@@QEBA_KW4INPUT_GLOBALS_TICK_COUNT@@PEA_K@Z; CInputGlobals::GetGlobalTickCountWithSequence(INPUT_GLOBALS_TICK_COUNT,unsigned __int64 *)
0x1401ce49d  cmp     rax, [r14+0AE8h]
0x1401ce4a4  mov     rdx, [rbp+var_10]
0x1401ce4a8  cmova   rdx, rdi
0x1401ce4ac  mov     [r14+0AF0h], rdx
0x1401ce4b3  mov     r8d, r12d; int
0x1401ce4b6  mov     edx, ebx; enum POWER_MONITOR_REQUEST_REASON
0x1401ce4b8  xor     ecx, ecx; enum _MONITOR_DISPLAY_STATE
0x1401ce4ba  call    ?UpdateDisplayState@@YAXW4_MONITOR_DISPLAY_STATE@@W4POWER_MONITOR_REQUEST_REASON@@HH@Z; UpdateDisplayState(_MONITOR_DISPLAY_STATE,POWER_MONITOR_REQUEST_REASON,int,int)
0x1401ce4bf  call    cs:__imp_W32GetUserSessionState
0x1401ce4c6  nop     dword ptr [rax+rax+00h]
0x1401ce4cb  cmp     [rax+0F480h], rdi
0x1401ce4d2  jz      short loc_1401CE4E0
0x1401ce4d4  xor     edx, edx
0x1401ce4d6  mov     ecx, 405h
0x1401ce4db  call    PostWinlogonMessage
0x1401ce4e0  test    r13d, r13d
0x1401ce4e3  jz      short loc_1401CE513
0x1401ce4e5  xor     r9d, r9d
0x1401ce4e8  mov     [rsp+60h+var_30], edi
0x1401ce4ec  mov     [rsp+60h+var_38], edi
0x1401ce4f0  lea     rdx, [rbp+var_1C]
0x1401ce4f4  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1401ce4fb  mov     [rbp+var_1C], edi
0x1401ce4fe  mov     [rsp+60h+var_40], rdi
0x1401ce503  lea     r8d, [r9+4]
0x1401ce507  call    cs:__imp_ZwUpdateWnfStateData
0x1401ce50e  nop     dword ptr [rax+rax+00h]
0x1401ce513  mov     rbx, [rsp+60h+arg_0]
0x1401ce51b  add     rsp, 60h
0x1401ce51f  pop     r15
0x1401ce521  pop     r14
0x1401ce523  pop     r13
0x1401ce525  pop     r12
0x1401ce527  pop     rdi
0x1401ce528  pop     rsi
0x1401ce529  pop     rbp
0x1401ce52a  retn
```
