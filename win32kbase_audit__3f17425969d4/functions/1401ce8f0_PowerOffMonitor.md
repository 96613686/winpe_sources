# PowerOffMonitor

- ea: `0x1401ce8f0`
- end: `0x1401ced4c`
- name: `PowerOffMonitor`
- size: `1116`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400cff38`
- `0x1400d1028`

## callees

- `0x140029710`
- `0x14004c020`
- `0x14004f4c0`
- `0x1400701d4`
- `0x1400c3e10`
- `0x1400cf0ec`
- `0x1400cf1d8`
- `0x140121af0`
- `0x140164040`
- `0x14016dc50`
- `0x1401aab9c`
- `0x1401cdbf0`
- `0x1401cdec4`
- `0x1401ce8f0`
- `0x1401d1d10`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401ceb2a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401ceb2a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ce9b2`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ced27`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ce9b2`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ced27`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cea12`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cea37`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cea8a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cebff`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cec28`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cea12`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cea37`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cea8a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cebff`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cec28`
- `WIN32K!W32GetUserSessionState` at `0x1401ce90e`
- `WIN32K!W32GetUserSessionState` at `0x1401ce966`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9c9`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9e1`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9f6`
- `WIN32K!W32GetUserSessionState` at `0x1401cead2`
- `WIN32K!W32GetUserSessionState` at `0x1401cebd1`
- `WIN32K!W32GetUserSessionState` at `0x1401cec53`
- `WIN32K!W32GetUserSessionState` at `0x1401cec9f`
- `WIN32K!W32GetUserSessionState` at `0x1401cecdf`
- `WIN32K!W32GetUserSessionState` at `0x1401ce90e`
- `WIN32K!W32GetUserSessionState` at `0x1401ce966`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9c9`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9e1`
- `WIN32K!W32GetUserSessionState` at `0x1401ce9f6`
- `WIN32K!W32GetUserSessionState` at `0x1401cead2`
- `WIN32K!W32GetUserSessionState` at `0x1401cebd1`
- `WIN32K!W32GetUserSessionState` at `0x1401cec53`
- `WIN32K!W32GetUserSessionState` at `0x1401cec9f`
- `WIN32K!W32GetUserSessionState` at `0x1401cecdf`

## pseudocode

```c
void __fastcall PowerOffMonitor(__int64 a1, __int64 a2)
{
  enum POWER_MONITOR_REQUEST_REASON v2; // ebx
  _DWORD *UserSessionState; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  _DWORD *v6; // r14
  int v7; // r12d
  int v8; // r13d
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int (*v17)(void); // rax
  int (__fastcall *v18)(unsigned int *, __int64 *, int *); // rax
  __int64 v19; // rax
  __int64 v20; // rdi
  unsigned int v21; // esi
  __int64 v22; // rcx
  void (__fastcall *v23)(_QWORD, __int64, __int64, _QWORD); // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *v26; // rsi
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v31; // rax
  __int64 *v32; // rdi
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  int (*v36)(void); // rax
  __int64 v37; // rdi
  void (__fastcall *v38)(__int64); // rax
  unsigned __int64 v39; // rcx
  unsigned __int128 v40; // rax
  __int64 v41; // rax
  unsigned __int64 GlobalTickCountWithSequence; // rax
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rcx
  int v46; // [rsp+40h] [rbp-20h] BYREF
  int v47; // [rsp+44h] [rbp-1Ch] BYREF
  __int64 v48; // [rsp+48h] [rbp-18h] BYREF
  __int64 v49; // [rsp+50h] [rbp-10h] BYREF
  int v51; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v52; // [rsp+B8h] [rbp+58h] BYREF

  v2 = (int)a1;
  UserSessionState = (_DWORD *)W32GetUserSessionState(a1, a2);
  v6 = UserSessionState;
  v52 = 0;
  v48 = 0;
  v51 = 0;
  v7 = UserSessionState[675];
  v49 = 0;
  if ( v7 || UserSessionState[680] || UserSessionState[681] )
  {
    v8 = 0;
    InputTraceLogging::Power::PowerOffMonitor(v2);
    if ( !*(_WORD *)(W32GetUserSessionState(v10, v9) + 68736) )
    {
      v11 = 0;
      if ( v2 != MonitorRequestReasonGracePeriod && v2 != MonitorRequestReasonNearProximity )
      {
        v46 = 2;
        ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v46, 4, 0, 0, 0, 0);
        v8 = 1;
      }
      UserSessionSwitchBlock_Start();
      if ( *(_DWORD *)(W32GetUserSessionState(v13, v12) + 42776)
        || !*(_QWORD *)(W32GetUserSessionState(v15, v14) + 19216)
        || (v11 = 1,
            *(_DWORD *)(W32GetUserSessionState(v15, v14) + 42776) = 1,
            v15 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v16) + 48),
            (v17 = *(int (**)(void))(v15 + 2024)) == 0)
        || v17() < 0
        || (v15 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v15) + 48),
            (v18 = *(int (__fastcall **)(unsigned int *, __int64 *, int *))(v15 + 2032)) != 0)
        && v18(&v52, &v48, &v51) >= 0 )
      {
        v19 = v48;
      }
      else
      {
        v19 = 0;
        v48 = 0;
      }
      if ( v51 )
      {
        UserSessionSwitchLeaveCritWithNonPaged(v15, v14);
        v20 = v48;
        v21 = v52;
        v23 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v22) + 48)
                                                                      + 2040LL);
        if ( v23 )
          v23(v21, v20, 167, 0);
        DrvDxgkLogCodePointPacket(14, v48 != 0, 0, 0);
        v26 = (_QWORD *)W32GetUserSessionState(v25, v24);
        v27 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
                v26,
                1,
                0,
                (void (__fastcall *)(_QWORD, __int64))_lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
        v26[2] = v27;
        v29 = v27;
        if ( v27 )
        {
          v28 = 0;
          if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v27 + 520), 0, 0) & 0x1000000) != 0
            && *(char *)(v27 + 1360) >= 0 )
          {
            CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(0);
            if ( CurrentProcessWin32Process )
            {
              if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
              {
                while ( 1 )
                {
                  v32 = (__int64 *)v26[2443];
                  if ( !v32 )
                    break;
                  v26[2443] = v32[2];
                  v31 = *v32;
                  v32[2] = 0;
                  if ( !*(_DWORD *)(v31 + 8) )
                  {
                    v46 = 0x20000;
                    MicrosoftTelemetryAssertTriggeredArgsKM((__int64)"IXPTelAssert", 0x20000, 4662);
                  }
                  HMUnlockObject(*v32, v29);
                }
                DestroyDeferredUnlockObjectAssignmentList(v26 + 2447);
                DestroyDeferredUnlockObjectAssignmentList(v26 + 2445);
              }
            }
          }
        }
      }
      else
      {
        DrvDxgkLogCodePointPacket(14, v19 != 0, 0, 0);
      }
      v33 = W32GetUserSessionState(v28, v29);
      DrvSetMonitorPowerState(*(_QWORD *)(*(_QWORD *)(v33 + 56744) + 16LL), 4, 1, a2);
      if ( v48 )
      {
        v35 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v35) + 48);
        v36 = *(int (**)(void))(v35 + 2048);
        if ( v36 )
        {
          if ( v36() >= 0 )
          {
            v37 = v48;
            v34 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v35) + 48);
            v38 = *(void (__fastcall **)(__int64))(v34 + 2056);
            if ( v38 )
              v38(v37);
          }
        }
      }
      if ( v11 )
        *(_DWORD *)(W32GetUserSessionState(v35, v34) + 42776) = 0;
      UserSessionSwitchBlock_End();
    }
    if ( v2 != MonitorRequestReasonGracePeriod && v2 != MonitorRequestReasonNearProximity )
    {
      v39 = (unsigned __int64)MEMORY[0xFFFFF78000000004] << 32;
      v40 = v39 * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
      *((_QWORD *)v6 + 349) = *((_QWORD *)&v40 + 1);
      v41 = W32GetUserSessionState(v39, *((_QWORD *)&v40 + 1));
      GlobalTickCountWithSequence = CInputGlobals::GetGlobalTickCountWithSequence(*(_QWORD *)(v41 + 3008), 0, &v49);
      v43 = v49;
      if ( GlobalTickCountWithSequence > *((_QWORD *)v6 + 349) )
        v43 = 0;
      *((_QWORD *)v6 + 350) = v43;
    }
    UpdateDisplayState(0, v2, v7);
    if ( *(_QWORD *)(W32GetUserSessionState(v45, v44) + 62592) )
      PostWinlogonMessage(1029, 0);
    if ( v8 )
    {
      v47 = 0;
      ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v47, 4, 0, 0, 0, 0);
    }
  }
  else if ( v2 == MonitorRequestReasonNearProximity )
  {
    SetProximityBlocking(v5, v4);
  }
}

```

## disassembly

```asm
0x1401ce8f0  mov     [rsp-38h+arg_0], rbx
0x1401ce8f5  mov     [rsp-38h+arg_8], rdx
0x1401ce8fa  push    rbp
0x1401ce8fb  push    rsi
0x1401ce8fc  push    rdi
0x1401ce8fd  push    r12
0x1401ce8ff  push    r13
0x1401ce901  push    r14
0x1401ce903  push    r15
0x1401ce905  mov     rbp, rsp
0x1401ce908  sub     rsp, 60h
0x1401ce90c  mov     ebx, ecx
0x1401ce90e  call    cs:__imp_W32GetUserSessionState
0x1401ce915  nop     dword ptr [rax+rax+00h]
0x1401ce91a  xor     edi, edi
0x1401ce91c  mov     r14, rax
0x1401ce91f  mov     [rbp+arg_18], edi
0x1401ce922  mov     [rbp+var_18], rdi
0x1401ce926  mov     [rbp+arg_10], edi
0x1401ce929  mov     r12d, [rax+0A8Ch]
0x1401ce930  mov     [rbp+var_10], rdi
0x1401ce934  test    r12d, r12d
0x1401ce937  jnz     short loc_1401CE95C
0x1401ce939  cmp     [rax+0AA0h], edi
0x1401ce93f  jnz     short loc_1401CE95C
0x1401ce941  cmp     [rax+0AA4h], edi
0x1401ce947  jnz     short loc_1401CE95C
0x1401ce949  cmp     ebx, 16h
0x1401ce94c  jnz     loc_1401CED33
0x1401ce952  call    ?SetProximityBlocking@@YAXXZ; SetProximityBlocking(void)
0x1401ce957  jmp     loc_1401CED33
0x1401ce95c  mov     ecx, ebx; enum POWER_MONITOR_REQUEST_REASON
0x1401ce95e  mov     r13d, edi
0x1401ce961  call    ?PowerOffMonitor@Power@InputTraceLogging@@SAXW4POWER_MONITOR_REQUEST_REASON@@@Z; InputTraceLogging::Power::PowerOffMonitor(POWER_MONITOR_REQUEST_REASON)
0x1401ce966  call    cs:__imp_W32GetUserSessionState
0x1401ce96d  nop     dword ptr [rax+rax+00h]
0x1401ce972  cmp     [rax+10C80h], di
0x1401ce979  jnz     loc_1401CEC6A
0x1401ce97f  mov     r15d, edi
0x1401ce982  cmp     ebx, 11h
0x1401ce985  jz      short loc_1401CE9C4
0x1401ce987  cmp     ebx, 16h
0x1401ce98a  jz      short loc_1401CE9C4
0x1401ce98c  xor     r9d, r9d
0x1401ce98f  mov     [rsp+60h+var_30], edi
0x1401ce993  mov     [rsp+60h+var_38], edi
0x1401ce997  lea     rdx, [rbp+var_20]
0x1401ce99b  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1401ce9a2  mov     [rbp+var_20], 2
0x1401ce9a9  mov     [rsp+60h+var_40], rdi
0x1401ce9ae  lea     r8d, [r9+4]
0x1401ce9b2  call    cs:__imp_ZwUpdateWnfStateData
0x1401ce9b9  nop     dword ptr [rax+rax+00h]
0x1401ce9be  mov     r13d, 1
0x1401ce9c4  call    ?UserSessionSwitchBlock_Start@@YAJXZ; UserSessionSwitchBlock_Start(void)
0x1401ce9c9  call    cs:__imp_W32GetUserSessionState
0x1401ce9d0  nop     dword ptr [rax+rax+00h]
0x1401ce9d5  cmp     [rax+0A718h], edi
0x1401ce9db  jnz     loc_1401CEA71
0x1401ce9e1  call    cs:__imp_W32GetUserSessionState
0x1401ce9e8  nop     dword ptr [rax+rax+00h]
0x1401ce9ed  cmp     [rax+4B10h], rdi
0x1401ce9f4  jz      short loc_1401CEA71
0x1401ce9f6  call    cs:__imp_W32GetUserSessionState
0x1401ce9fd  nop     dword ptr [rax+rax+00h]
0x1401cea02  mov     r15d, 1
0x1401cea08  mov     dword ptr [rax+0A718h], 1
0x1401cea12  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cea19  nop     dword ptr [rax+rax+00h]
0x1401cea1e  mov     rcx, [rax+30h]
0x1401cea22  mov     rax, [rcx+7E8h]
0x1401cea29  test    rax, rax
0x1401cea2c  jz      short loc_1401CEA71
0x1401cea2e  call    _guard_dispatch_icall
0x1401cea33  test    eax, eax
0x1401cea35  js      short loc_1401CEA71
0x1401cea37  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cea3e  nop     dword ptr [rax+rax+00h]
0x1401cea43  mov     rcx, [rax+30h]
0x1401cea47  mov     rax, [rcx+7F0h]
0x1401cea4e  test    rax, rax
0x1401cea51  jz      short loc_1401CEA68
0x1401cea53  lea     r8, [rbp+arg_10]
0x1401cea57  lea     rdx, [rbp+var_18]
0x1401cea5b  lea     rcx, [rbp+arg_18]
0x1401cea5f  call    _guard_dispatch_icall
0x1401cea64  test    eax, eax
0x1401cea66  jns     short loc_1401CEA71
0x1401cea68  mov     rax, rdi
0x1401cea6b  mov     [rbp+var_18], rax
0x1401cea6f  jmp     short loc_1401CEA75
0x1401cea71  mov     rax, [rbp+var_18]
0x1401cea75  cmp     [rbp+arg_10], edi
0x1401cea78  jz      loc_1401CEBBA
0x1401cea7e  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cea83  mov     rdi, [rbp+var_18]
0x1401cea87  mov     esi, [rbp+arg_18]
0x1401cea8a  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cea91  nop     dword ptr [rax+rax+00h]
0x1401cea96  mov     r8, [rax+30h]
0x1401cea9a  mov     rax, [r8+7F8h]
0x1401ceaa1  test    rax, rax
0x1401ceaa4  jz      short loc_1401CEAB9
0x1401ceaa6  xor     r9d, r9d
0x1401ceaa9  mov     r8d, 0A7h
0x1401ceaaf  mov     rdx, rdi
0x1401ceab2  mov     ecx, esi
0x1401ceab4  call    _guard_dispatch_icall
0x1401ceab9  xor     edi, edi
0x1401ceabb  cmp     [rbp+var_18], rdi
0x1401ceabf  mov     edx, edi
0x1401ceac1  setnz   dl
0x1401ceac4  xor     r9d, r9d
0x1401ceac7  xor     r8d, r8d
0x1401ceaca  lea     ecx, [rdi+0Eh]
0x1401ceacd  call    DrvDxgkLogCodePointPacket
0x1401cead2  call    cs:__imp_W32GetUserSessionState
0x1401cead9  nop     dword ptr [rax+rax+00h]
0x1401ceade  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401ceae5  xor     r8d, r8d
0x1401ceae8  mov     rcx, rax
0x1401ceaeb  lea     edx, [rdi+1]
0x1401ceaee  mov     rsi, rax
0x1401ceaf1  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401ceaf6  mov     [rsi+10h], rax
0x1401ceafa  mov     rdx, rax
0x1401ceafd  test    rax, rax
0x1401ceb00  jz      loc_1401CEBD1
0x1401ceb06  mov     ecx, edi
0x1401ceb08  xor     eax, eax
0x1401ceb0a  lock cmpxchg [rdx+208h], ecx
0x1401ceb12  bt      eax, 18h
0x1401ceb16  jnb     loc_1401CEBD1
0x1401ceb1c  mov     al, [rdx+550h]
0x1401ceb22  test    al, al
0x1401ceb24  js      loc_1401CEBD1
0x1401ceb2a  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401ceb31  nop     dword ptr [rax+rax+00h]
0x1401ceb36  test    rax, rax
0x1401ceb39  jz      loc_1401CEBD1
0x1401ceb3f  cmp     [rax], rdi
0x1401ceb42  jz      loc_1401CEBD1
0x1401ceb48  mov     al, [rax+4B0h]
0x1401ceb4e  cmp     al, 1
0x1401ceb50  jnz     short loc_1401CEBD1
0x1401ceb52  jmp     short loc_1401CEB94
0x1401ceb54  mov     rax, [rdi+10h]
0x1401ceb58  mov     [rsi+4C58h], rax
0x1401ceb5f  mov     rax, [rdi]
0x1401ceb62  mov     qword ptr [rdi+10h], 0
0x1401ceb6a  cmp     dword ptr [rax+8], 1
0x1401ceb6e  jnb     short loc_1401CEB8C
0x1401ceb70  mov     [rbp+var_20], 20000h
0x1401ceb77  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401ceb7e  mov     edx, [rbp+var_20]
0x1401ceb81  mov     r8d, 1236h
0x1401ceb87  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401ceb8c  mov     rcx, [rdi]
0x1401ceb8f  call    HMUnlockObject
0x1401ceb94  mov     rdi, [rsi+4C58h]
0x1401ceb9b  test    rdi, rdi
0x1401ceb9e  jnz     short loc_1401CEB54
0x1401ceba0  lea     rcx, [rsi+4C78h]
0x1401ceba7  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cebac  lea     rcx, [rsi+4C68h]
0x1401cebb3  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cebb8  jmp     short loc_1401CEBD1
0x1401cebba  test    rax, rax
0x1401cebbd  mov     edx, edi
0x1401cebbf  setnz   dl
0x1401cebc2  xor     r9d, r9d
0x1401cebc5  xor     r8d, r8d
0x1401cebc8  lea     ecx, [r9+0Eh]
0x1401cebcc  call    DrvDxgkLogCodePointPacket
0x1401cebd1  call    cs:__imp_W32GetUserSessionState
0x1401cebd8  nop     dword ptr [rax+rax+00h]
0x1401cebdd  mov     r9, [rbp+arg_8]
0x1401cebe1  mov     r8b, 1
0x1401cebe4  mov     edx, 4
0x1401cebe9  mov     rcx, [rax+0DDA8h]
0x1401cebf0  mov     rcx, [rcx+10h]
0x1401cebf4  call    DrvSetMonitorPowerState
0x1401cebf9  cmp     [rbp+var_18], rdi
0x1401cebfd  jz      short loc_1401CEC4E
0x1401cebff  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cec06  nop     dword ptr [rax+rax+00h]
0x1401cec0b  mov     rcx, [rax+30h]
0x1401cec0f  mov     rax, [rcx+800h]
0x1401cec16  test    rax, rax
0x1401cec19  jz      short loc_1401CEC4E
0x1401cec1b  call    _guard_dispatch_icall
0x1401cec20  test    eax, eax
0x1401cec22  js      short loc_1401CEC4E
0x1401cec24  mov     rdi, [rbp+var_18]
0x1401cec28  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cec2f  nop     dword ptr [rax+rax+00h]
0x1401cec34  mov     rdx, [rax+30h]
0x1401cec38  mov     rax, [rdx+808h]
0x1401cec3f  test    rax, rax
0x1401cec42  jz      short loc_1401CEC4C
0x1401cec44  mov     rcx, rdi
0x1401cec47  call    _guard_dispatch_icall
0x1401cec4c  xor     edi, edi
0x1401cec4e  test    r15d, r15d
0x1401cec51  jz      short loc_1401CEC65
0x1401cec53  call    cs:__imp_W32GetUserSessionState
0x1401cec5a  nop     dword ptr [rax+rax+00h]
0x1401cec5f  mov     [rax+0A718h], edi
0x1401cec65  call    ?UserSessionSwitchBlock_End@@YAXXZ; UserSessionSwitchBlock_End(void)
0x1401cec6a  cmp     ebx, 11h
0x1401cec6d  jz      short loc_1401CECD3
0x1401cec6f  cmp     ebx, 16h
0x1401cec72  jz      short loc_1401CECD3
0x1401cec74  mov     rax, 0FFFFF78000000004h
0x1401cec7e  mov     ecx, [rax]
0x1401cec80  mov     rax, 0FFFFF78000000320h
0x1401cec8a  shl     rcx, 20h
0x1401cec8e  mov     rax, [rax]
0x1401cec91  shl     rax, 8
0x1401cec95  mul     rcx
0x1401cec98  mov     [r14+0AE8h], rdx
0x1401cec9f  call    cs:__imp_W32GetUserSessionState
0x1401ceca6  nop     dword ptr [rax+rax+00h]
0x1401cecab  lea     r8, [rbp+var_10]
0x1401cecaf  xor     edx, edx
0x1401cecb1  mov     rcx, [rax+0BC0h]
0x1401cecb8  call    ?GetGlobalTickCountWithSequence@CInputGlobals@@QEBA_KW4INPUT_GLOBALS_TICK_COUNT@@PEA_K@Z; CInputGlobals::GetGlobalTickCountWithSequence(INPUT_GLOBALS_TICK_COUNT,unsigned __int64 *)
0x1401cecbd  cmp     rax, [r14+0AE8h]
0x1401cecc4  mov     rdx, [rbp+var_10]
0x1401cecc8  cmova   rdx, rdi
0x1401ceccc  mov     [r14+0AF0h], rdx
0x1401cecd3  mov     r8d, r12d; int
0x1401cecd6  mov     edx, ebx; enum POWER_MONITOR_REQUEST_REASON
0x1401cecd8  xor     ecx, ecx; enum _MONITOR_DISPLAY_STATE
0x1401cecda  call    ?UpdateDisplayState@@YAXW4_MONITOR_DISPLAY_STATE@@W4POWER_MONITOR_REQUEST_REASON@@HH@Z; UpdateDisplayState(_MONITOR_DISPLAY_STATE,POWER_MONITOR_REQUEST_REASON,int,int)
0x1401cecdf  call    cs:__imp_W32GetUserSessionState
0x1401cece6  nop     dword ptr [rax+rax+00h]
0x1401ceceb  cmp     [rax+0F480h], rdi
0x1401cecf2  jz      short loc_1401CED00
0x1401cecf4  xor     edx, edx
0x1401cecf6  mov     ecx, 405h
0x1401cecfb  call    PostWinlogonMessage
0x1401ced00  test    r13d, r13d
0x1401ced03  jz      short loc_1401CED33
0x1401ced05  xor     r9d, r9d
0x1401ced08  mov     [rsp+60h+var_30], edi
0x1401ced0c  mov     [rsp+60h+var_38], edi
0x1401ced10  lea     rdx, [rbp+var_1C]
0x1401ced14  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1401ced1b  mov     [rbp+var_1C], edi
0x1401ced1e  mov     [rsp+60h+var_40], rdi
0x1401ced23  lea     r8d, [r9+4]
0x1401ced27  call    cs:__imp_ZwUpdateWnfStateData
0x1401ced2e  nop     dword ptr [rax+rax+00h]
0x1401ced33  mov     rbx, [rsp+60h+arg_0]
0x1401ced3b  add     rsp, 60h
0x1401ced3f  pop     r15
0x1401ced41  pop     r14
0x1401ced43  pop     r13
0x1401ced45  pop     r12
0x1401ced47  pop     rdi
0x1401ced48  pop     rsi
0x1401ced49  pop     rbp
0x1401ced4a  retn
```
