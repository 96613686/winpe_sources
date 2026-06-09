# PowerOffMonitor

- ea: `0x1401cdb70`
- end: `0x1401cdfcc`
- name: `PowerOffMonitor`
- size: `1116`
- prototype: `__int64 __fastcall(enum POWER_MONITOR_REQUEST_REASON)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400a65c8`
- `0x1400a76b8`

## callees

- `0x14001bdf0`
- `0x140033364`
- `0x140074bf0`
- `0x140078090`
- `0x1400a5774`
- `0x1400a5860`
- `0x1400d0fc4`
- `0x14011e110`
- `0x140161a70`
- `0x14016b5a0`
- `0x1401a9f9c`
- `0x1401cce70`
- `0x1401cd144`
- `0x1401cdb70`
- `0x1401d0f90`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401cddaa`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401cddaa`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401cdc32`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401cdfa7`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401cdc32`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401cdfa7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cdc92`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cdcb7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cdd0a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cde7f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cdea8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cdc92`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cdcb7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cdd0a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cde7f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401cdea8`
- `WIN32K!W32GetUserSessionState` at `0x1401cdb8e`
- `WIN32K!W32GetUserSessionState` at `0x1401cdbe6`
- `WIN32K!W32GetUserSessionState` at `0x1401cdc49`
- `WIN32K!W32GetUserSessionState` at `0x1401cdc61`
- `WIN32K!W32GetUserSessionState` at `0x1401cdc76`
- `WIN32K!W32GetUserSessionState` at `0x1401cdd52`
- `WIN32K!W32GetUserSessionState` at `0x1401cde51`
- `WIN32K!W32GetUserSessionState` at `0x1401cded3`
- `WIN32K!W32GetUserSessionState` at `0x1401cdf1f`
- `WIN32K!W32GetUserSessionState` at `0x1401cdf5f`
- `WIN32K!W32GetUserSessionState` at `0x1401cdb8e`
- `WIN32K!W32GetUserSessionState` at `0x1401cdbe6`
- `WIN32K!W32GetUserSessionState` at `0x1401cdc49`
- `WIN32K!W32GetUserSessionState` at `0x1401cdc61`
- `WIN32K!W32GetUserSessionState` at `0x1401cdc76`
- `WIN32K!W32GetUserSessionState` at `0x1401cdd52`
- `WIN32K!W32GetUserSessionState` at `0x1401cde51`
- `WIN32K!W32GetUserSessionState` at `0x1401cded3`
- `WIN32K!W32GetUserSessionState` at `0x1401cdf1f`
- `WIN32K!W32GetUserSessionState` at `0x1401cdf5f`

## pseudocode

```c
void __fastcall PowerOffMonitor(__int64 a1, __int64 a2, __int64 a3)
{
  enum POWER_MONITOR_REQUEST_REASON v3; // ebx
  _DWORD *UserSessionState; // rax
  _DWORD *v5; // r14
  int v6; // r12d
  int v7; // r13d
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r8
  int v12; // r9d
  int v13; // r15d
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  int (__fastcall *v22)(__int64, __int64, __int64); // rax
  int (__fastcall *v23)(unsigned int *, __int64 *, int *); // rax
  __int64 v24; // rax
  __int64 v25; // rdi
  unsigned int v26; // esi
  __int64 v27; // rdx
  __int64 v28; // rcx
  void (__fastcall *v29)(_QWORD, __int64, __int64, _QWORD, __int64, int, int); // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rsi
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v39; // rax
  _QWORD *v40; // rdi
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  int (*v46)(void); // rax
  __int64 v47; // rdi
  void (__fastcall *v48)(__int64); // rax
  unsigned __int64 v49; // rcx
  unsigned __int128 v50; // rax
  __int64 v51; // rax
  unsigned __int64 GlobalTickCountWithSequence; // rax
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // [rsp+20h] [rbp-40h]
  int v58; // [rsp+28h] [rbp-38h]
  int v59; // [rsp+30h] [rbp-30h]
  int v60; // [rsp+40h] [rbp-20h] BYREF
  int v61; // [rsp+44h] [rbp-1Ch] BYREF
  __int64 v62; // [rsp+48h] [rbp-18h] BYREF
  __int64 v63; // [rsp+50h] [rbp-10h] BYREF
  int v65; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v66; // [rsp+B8h] [rbp+58h] BYREF

  v3 = (int)a1;
  UserSessionState = (_DWORD *)W32GetUserSessionState(a1, a2, a3);
  v5 = UserSessionState;
  v66 = 0;
  v62 = 0;
  v65 = 0;
  v6 = UserSessionState[675];
  v63 = 0;
  if ( v6 || UserSessionState[680] || UserSessionState[681] )
  {
    v7 = 0;
    InputTraceLogging::Power::PowerOffMonitor(v3);
    if ( !*(_WORD *)(W32GetUserSessionState(v9, v8, v10) + 68736) )
    {
      v13 = 0;
      if ( v3 != MonitorRequestReasonGracePeriod && v3 != MonitorRequestReasonNearProximity )
      {
        v59 = 0;
        v58 = 0;
        v60 = 2;
        v57 = 0;
        ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v60, 4);
        v7 = 1;
      }
      UserSessionSwitchBlock_Start();
      if ( *(_DWORD *)(W32GetUserSessionState(v15, v14, v16) + 42776)
        || !*(_QWORD *)(W32GetUserSessionState(v18, v17, v19) + 19216)
        || (v13 = 1,
            *(_DWORD *)(W32GetUserSessionState(v18, v17, v19) + 42776) = 1,
            v18 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v21, v20) + 48),
            (v22 = *(int (__fastcall **)(__int64, __int64, __int64))(v18 + 2024)) == 0)
        || v22(v18, v17, v19) < 0
        || (v18 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v18, v17) + 48),
            (v23 = *(int (__fastcall **)(unsigned int *, __int64 *, int *))(v18 + 2032)) != 0)
        && v23(&v66, &v62, &v65) >= 0 )
      {
        v24 = v62;
      }
      else
      {
        v24 = 0;
        v62 = 0;
      }
      if ( v65 )
      {
        UserSessionSwitchLeaveCritWithNonPaged(v18, v17, v19);
        v25 = v62;
        v26 = v66;
        v29 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, int, int))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v28, v27) + 48)
                                                                                         + 2040LL);
        if ( v29 )
          v29(v26, v25, 167, 0, v57, v58, v59);
        DrvDxgkLogCodePointPacket(14, v62 != 0, 0, 0);
        v33 = W32GetUserSessionState(v31, v30, v32);
        v34 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
                v33,
                1,
                0,
                _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
        *(_QWORD *)(v33 + 16) = v34;
        v37 = v34;
        if ( v34 )
        {
          v35 = 0;
          if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v34 + 520), 0, 0) & 0x1000000) != 0
            && *(char *)(v34 + 1360) >= 0 )
          {
            CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
            if ( CurrentProcessWin32Process )
            {
              if ( *(_QWORD *)CurrentProcessWin32Process && *(_BYTE *)(CurrentProcessWin32Process + 1200) == 1 )
              {
                while ( 1 )
                {
                  v40 = *(_QWORD **)(v33 + 19544);
                  if ( !v40 )
                    break;
                  *(_QWORD *)(v33 + 19544) = v40[2];
                  v39 = *v40;
                  v40[2] = 0;
                  if ( !*(_DWORD *)(v39 + 8) )
                  {
                    v60 = 0x20000;
                    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
                  }
                  HMUnlockObject(*v40);
                }
                DestroyDeferredUnlockObjectAssignmentList(v33 + 19576);
                DestroyDeferredUnlockObjectAssignmentList(v33 + 19560);
              }
            }
          }
        }
      }
      else
      {
        DrvDxgkLogCodePointPacket(14, v24 != 0, 0, 0);
      }
      v41 = W32GetUserSessionState(v35, v37, v36);
      LOBYTE(v42) = 1;
      DrvSetMonitorPowerState(*(_QWORD *)(*(_QWORD *)(v41 + 56744) + 16LL), 4, v42, a2);
      if ( v62 )
      {
        v44 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v44, v43) + 48);
        v46 = *(int (**)(void))(v44 + 2048);
        if ( v46 )
        {
          if ( v46() >= 0 )
          {
            v47 = v62;
            v43 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v44, v43) + 48);
            v48 = *(void (__fastcall **)(__int64))(v43 + 2056);
            if ( v48 )
              v48(v47);
          }
        }
      }
      if ( v13 )
        *(_DWORD *)(W32GetUserSessionState(v44, v43, v45) + 42776) = 0;
      UserSessionSwitchBlock_End();
    }
    if ( v3 != MonitorRequestReasonGracePeriod && v3 != MonitorRequestReasonNearProximity )
    {
      v49 = (unsigned __int64)MEMORY[0xFFFFF78000000004] << 32;
      v50 = v49 * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
      *((_QWORD *)v5 + 349) = *((_QWORD *)&v50 + 1);
      v51 = W32GetUserSessionState(v49, *((_QWORD *)&v50 + 1), v11);
      GlobalTickCountWithSequence = CInputGlobals::GetGlobalTickCountWithSequence(*(_QWORD *)(v51 + 3008), 0, &v63);
      v53 = v63;
      if ( GlobalTickCountWithSequence > *((_QWORD *)v5 + 349) )
        v53 = 0;
      *((_QWORD *)v5 + 350) = v53;
    }
    UpdateDisplayState(PowerMonitorOff, v3, v6, v12);
    if ( *(_QWORD *)(W32GetUserSessionState(v55, v54, v56) + 62592) )
      PostWinlogonMessage(1029, 0);
    if ( v7 )
    {
      v61 = 0;
      ZwUpdateWnfStateData(&WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE, &v61, 4);
    }
  }
  else if ( v3 == MonitorRequestReasonNearProximity )
  {
    SetProximityBlocking();
  }
}

```

## disassembly

```asm
0x1401cdb70  mov     [rsp-38h+arg_0], rbx
0x1401cdb75  mov     [rsp-38h+arg_8], rdx
0x1401cdb7a  push    rbp
0x1401cdb7b  push    rsi
0x1401cdb7c  push    rdi
0x1401cdb7d  push    r12
0x1401cdb7f  push    r13
0x1401cdb81  push    r14
0x1401cdb83  push    r15
0x1401cdb85  mov     rbp, rsp
0x1401cdb88  sub     rsp, 60h
0x1401cdb8c  mov     ebx, ecx
0x1401cdb8e  call    cs:__imp_W32GetUserSessionState
0x1401cdb95  nop     dword ptr [rax+rax+00h]
0x1401cdb9a  xor     edi, edi
0x1401cdb9c  mov     r14, rax
0x1401cdb9f  mov     [rbp+arg_18], edi
0x1401cdba2  mov     [rbp+var_18], rdi
0x1401cdba6  mov     [rbp+arg_10], edi
0x1401cdba9  mov     r12d, [rax+0A8Ch]
0x1401cdbb0  mov     [rbp+var_10], rdi
0x1401cdbb4  test    r12d, r12d
0x1401cdbb7  jnz     short loc_1401CDBDC
0x1401cdbb9  cmp     [rax+0AA0h], edi
0x1401cdbbf  jnz     short loc_1401CDBDC
0x1401cdbc1  cmp     [rax+0AA4h], edi
0x1401cdbc7  jnz     short loc_1401CDBDC
0x1401cdbc9  cmp     ebx, 16h
0x1401cdbcc  jnz     loc_1401CDFB3
0x1401cdbd2  call    ?SetProximityBlocking@@YAXXZ; SetProximityBlocking(void)
0x1401cdbd7  jmp     loc_1401CDFB3
0x1401cdbdc  mov     ecx, ebx; enum POWER_MONITOR_REQUEST_REASON
0x1401cdbde  mov     r13d, edi
0x1401cdbe1  call    ?PowerOffMonitor@Power@InputTraceLogging@@SAXW4POWER_MONITOR_REQUEST_REASON@@@Z; InputTraceLogging::Power::PowerOffMonitor(POWER_MONITOR_REQUEST_REASON)
0x1401cdbe6  call    cs:__imp_W32GetUserSessionState
0x1401cdbed  nop     dword ptr [rax+rax+00h]
0x1401cdbf2  cmp     [rax+10C80h], di
0x1401cdbf9  jnz     loc_1401CDEEA
0x1401cdbff  mov     r15d, edi
0x1401cdc02  cmp     ebx, 11h
0x1401cdc05  jz      short loc_1401CDC44
0x1401cdc07  cmp     ebx, 16h
0x1401cdc0a  jz      short loc_1401CDC44
0x1401cdc0c  xor     r9d, r9d
0x1401cdc0f  mov     [rsp+60h+var_30], edi
0x1401cdc13  mov     [rsp+60h+var_38], edi
0x1401cdc17  lea     rdx, [rbp+var_20]
0x1401cdc1b  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1401cdc22  mov     [rbp+var_20], 2
0x1401cdc29  mov     [rsp+60h+var_40], rdi
0x1401cdc2e  lea     r8d, [r9+4]
0x1401cdc32  call    cs:__imp_ZwUpdateWnfStateData
0x1401cdc39  nop     dword ptr [rax+rax+00h]
0x1401cdc3e  mov     r13d, 1
0x1401cdc44  call    ?UserSessionSwitchBlock_Start@@YAJXZ; UserSessionSwitchBlock_Start(void)
0x1401cdc49  call    cs:__imp_W32GetUserSessionState
0x1401cdc50  nop     dword ptr [rax+rax+00h]
0x1401cdc55  cmp     [rax+0A718h], edi
0x1401cdc5b  jnz     loc_1401CDCF1
0x1401cdc61  call    cs:__imp_W32GetUserSessionState
0x1401cdc68  nop     dword ptr [rax+rax+00h]
0x1401cdc6d  cmp     [rax+4B10h], rdi
0x1401cdc74  jz      short loc_1401CDCF1
0x1401cdc76  call    cs:__imp_W32GetUserSessionState
0x1401cdc7d  nop     dword ptr [rax+rax+00h]
0x1401cdc82  mov     r15d, 1
0x1401cdc88  mov     dword ptr [rax+0A718h], 1
0x1401cdc92  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cdc99  nop     dword ptr [rax+rax+00h]
0x1401cdc9e  mov     rcx, [rax+30h]
0x1401cdca2  mov     rax, [rcx+7E8h]
0x1401cdca9  test    rax, rax
0x1401cdcac  jz      short loc_1401CDCF1
0x1401cdcae  call    _guard_dispatch_icall
0x1401cdcb3  test    eax, eax
0x1401cdcb5  js      short loc_1401CDCF1
0x1401cdcb7  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cdcbe  nop     dword ptr [rax+rax+00h]
0x1401cdcc3  mov     rcx, [rax+30h]
0x1401cdcc7  mov     rax, [rcx+7F0h]
0x1401cdcce  test    rax, rax
0x1401cdcd1  jz      short loc_1401CDCE8
0x1401cdcd3  lea     r8, [rbp+arg_10]
0x1401cdcd7  lea     rdx, [rbp+var_18]
0x1401cdcdb  lea     rcx, [rbp+arg_18]
0x1401cdcdf  call    _guard_dispatch_icall
0x1401cdce4  test    eax, eax
0x1401cdce6  jns     short loc_1401CDCF1
0x1401cdce8  mov     rax, rdi
0x1401cdceb  mov     [rbp+var_18], rax
0x1401cdcef  jmp     short loc_1401CDCF5
0x1401cdcf1  mov     rax, [rbp+var_18]
0x1401cdcf5  cmp     [rbp+arg_10], edi
0x1401cdcf8  jz      loc_1401CDE3A
0x1401cdcfe  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401cdd03  mov     rdi, [rbp+var_18]
0x1401cdd07  mov     esi, [rbp+arg_18]
0x1401cdd0a  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cdd11  nop     dword ptr [rax+rax+00h]
0x1401cdd16  mov     r8, [rax+30h]
0x1401cdd1a  mov     rax, [r8+7F8h]
0x1401cdd21  test    rax, rax
0x1401cdd24  jz      short loc_1401CDD39
0x1401cdd26  xor     r9d, r9d
0x1401cdd29  mov     r8d, 0A7h
0x1401cdd2f  mov     rdx, rdi
0x1401cdd32  mov     ecx, esi
0x1401cdd34  call    _guard_dispatch_icall
0x1401cdd39  xor     edi, edi
0x1401cdd3b  cmp     [rbp+var_18], rdi
0x1401cdd3f  mov     edx, edi
0x1401cdd41  setnz   dl
0x1401cdd44  xor     r9d, r9d
0x1401cdd47  xor     r8d, r8d
0x1401cdd4a  lea     ecx, [rdi+0Eh]
0x1401cdd4d  call    DrvDxgkLogCodePointPacket
0x1401cdd52  call    cs:__imp_W32GetUserSessionState
0x1401cdd59  nop     dword ptr [rax+rax+00h]
0x1401cdd5e  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401cdd65  xor     r8d, r8d
0x1401cdd68  mov     rcx, rax
0x1401cdd6b  lea     edx, [rdi+1]
0x1401cdd6e  mov     rsi, rax
0x1401cdd71  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401cdd76  mov     [rsi+10h], rax
0x1401cdd7a  mov     rdx, rax
0x1401cdd7d  test    rax, rax
0x1401cdd80  jz      loc_1401CDE51
0x1401cdd86  mov     ecx, edi
0x1401cdd88  xor     eax, eax
0x1401cdd8a  lock cmpxchg [rdx+208h], ecx
0x1401cdd92  bt      eax, 18h
0x1401cdd96  jnb     loc_1401CDE51
0x1401cdd9c  mov     al, [rdx+550h]
0x1401cdda2  test    al, al
0x1401cdda4  js      loc_1401CDE51
0x1401cddaa  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401cddb1  nop     dword ptr [rax+rax+00h]
0x1401cddb6  test    rax, rax
0x1401cddb9  jz      loc_1401CDE51
0x1401cddbf  cmp     [rax], rdi
0x1401cddc2  jz      loc_1401CDE51
0x1401cddc8  mov     al, [rax+4B0h]
0x1401cddce  cmp     al, 1
0x1401cddd0  jnz     short loc_1401CDE51
0x1401cddd2  jmp     short loc_1401CDE14
0x1401cddd4  mov     rax, [rdi+10h]
0x1401cddd8  mov     [rsi+4C58h], rax
0x1401cdddf  mov     rax, [rdi]
0x1401cdde2  mov     qword ptr [rdi+10h], 0
0x1401cddea  cmp     dword ptr [rax+8], 1
0x1401cddee  jnb     short loc_1401CDE0C
0x1401cddf0  mov     [rbp+var_20], 20000h
0x1401cddf7  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401cddfe  mov     edx, [rbp+var_20]
0x1401cde01  mov     r8d, 1236h
0x1401cde07  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401cde0c  mov     rcx, [rdi]
0x1401cde0f  call    HMUnlockObject
0x1401cde14  mov     rdi, [rsi+4C58h]
0x1401cde1b  test    rdi, rdi
0x1401cde1e  jnz     short loc_1401CDDD4
0x1401cde20  lea     rcx, [rsi+4C78h]
0x1401cde27  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cde2c  lea     rcx, [rsi+4C68h]
0x1401cde33  call    DestroyDeferredUnlockObjectAssignmentList
0x1401cde38  jmp     short loc_1401CDE51
0x1401cde3a  test    rax, rax
0x1401cde3d  mov     edx, edi
0x1401cde3f  setnz   dl
0x1401cde42  xor     r9d, r9d
0x1401cde45  xor     r8d, r8d
0x1401cde48  lea     ecx, [r9+0Eh]
0x1401cde4c  call    DrvDxgkLogCodePointPacket
0x1401cde51  call    cs:__imp_W32GetUserSessionState
0x1401cde58  nop     dword ptr [rax+rax+00h]
0x1401cde5d  mov     r9, [rbp+arg_8]
0x1401cde61  mov     r8b, 1
0x1401cde64  mov     edx, 4
0x1401cde69  mov     rcx, [rax+0DDA8h]
0x1401cde70  mov     rcx, [rcx+10h]
0x1401cde74  call    DrvSetMonitorPowerState
0x1401cde79  cmp     [rbp+var_18], rdi
0x1401cde7d  jz      short loc_1401CDECE
0x1401cde7f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cde86  nop     dword ptr [rax+rax+00h]
0x1401cde8b  mov     rcx, [rax+30h]
0x1401cde8f  mov     rax, [rcx+800h]
0x1401cde96  test    rax, rax
0x1401cde99  jz      short loc_1401CDECE
0x1401cde9b  call    _guard_dispatch_icall
0x1401cdea0  test    eax, eax
0x1401cdea2  js      short loc_1401CDECE
0x1401cdea4  mov     rdi, [rbp+var_18]
0x1401cdea8  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401cdeaf  nop     dword ptr [rax+rax+00h]
0x1401cdeb4  mov     rdx, [rax+30h]
0x1401cdeb8  mov     rax, [rdx+808h]
0x1401cdebf  test    rax, rax
0x1401cdec2  jz      short loc_1401CDECC
0x1401cdec4  mov     rcx, rdi
0x1401cdec7  call    _guard_dispatch_icall
0x1401cdecc  xor     edi, edi
0x1401cdece  test    r15d, r15d
0x1401cded1  jz      short loc_1401CDEE5
0x1401cded3  call    cs:__imp_W32GetUserSessionState
0x1401cdeda  nop     dword ptr [rax+rax+00h]
0x1401cdedf  mov     [rax+0A718h], edi
0x1401cdee5  call    ?UserSessionSwitchBlock_End@@YAXXZ; UserSessionSwitchBlock_End(void)
0x1401cdeea  cmp     ebx, 11h
0x1401cdeed  jz      short loc_1401CDF53
0x1401cdeef  cmp     ebx, 16h
0x1401cdef2  jz      short loc_1401CDF53
0x1401cdef4  mov     rax, 0FFFFF78000000004h
0x1401cdefe  mov     ecx, [rax]
0x1401cdf00  mov     rax, 0FFFFF78000000320h
0x1401cdf0a  shl     rcx, 20h
0x1401cdf0e  mov     rax, [rax]
0x1401cdf11  shl     rax, 8
0x1401cdf15  mul     rcx
0x1401cdf18  mov     [r14+0AE8h], rdx
0x1401cdf1f  call    cs:__imp_W32GetUserSessionState
0x1401cdf26  nop     dword ptr [rax+rax+00h]
0x1401cdf2b  lea     r8, [rbp+var_10]
0x1401cdf2f  xor     edx, edx
0x1401cdf31  mov     rcx, [rax+0BC0h]
0x1401cdf38  call    ?GetGlobalTickCountWithSequence@CInputGlobals@@QEBA_KW4INPUT_GLOBALS_TICK_COUNT@@PEA_K@Z; CInputGlobals::GetGlobalTickCountWithSequence(INPUT_GLOBALS_TICK_COUNT,unsigned __int64 *)
0x1401cdf3d  cmp     rax, [r14+0AE8h]
0x1401cdf44  mov     rdx, [rbp+var_10]
0x1401cdf48  cmova   rdx, rdi
0x1401cdf4c  mov     [r14+0AF0h], rdx
0x1401cdf53  mov     r8d, r12d; int
0x1401cdf56  mov     edx, ebx; enum POWER_MONITOR_REQUEST_REASON
0x1401cdf58  xor     ecx, ecx; enum _MONITOR_DISPLAY_STATE
0x1401cdf5a  call    ?UpdateDisplayState@@YAXW4_MONITOR_DISPLAY_STATE@@W4POWER_MONITOR_REQUEST_REASON@@HH@Z; UpdateDisplayState(_MONITOR_DISPLAY_STATE,POWER_MONITOR_REQUEST_REASON,int,int)
0x1401cdf5f  call    cs:__imp_W32GetUserSessionState
0x1401cdf66  nop     dword ptr [rax+rax+00h]
0x1401cdf6b  cmp     [rax+0F480h], rdi
0x1401cdf72  jz      short loc_1401CDF80
0x1401cdf74  xor     edx, edx
0x1401cdf76  mov     ecx, 405h
0x1401cdf7b  call    PostWinlogonMessage
0x1401cdf80  test    r13d, r13d
0x1401cdf83  jz      short loc_1401CDFB3
0x1401cdf85  xor     r9d, r9d
0x1401cdf88  mov     [rsp+60h+var_30], edi
0x1401cdf8c  mov     [rsp+60h+var_38], edi
0x1401cdf90  lea     rdx, [rbp+var_1C]
0x1401cdf94  lea     rcx, WNF_PO_PRIMARY_DISPLAY_LOGICAL_STATE
0x1401cdf9b  mov     [rbp+var_1C], edi
0x1401cdf9e  mov     [rsp+60h+var_40], rdi
0x1401cdfa3  lea     r8d, [r9+4]
0x1401cdfa7  call    cs:__imp_ZwUpdateWnfStateData
0x1401cdfae  nop     dword ptr [rax+rax+00h]
0x1401cdfb3  mov     rbx, [rsp+60h+arg_0]
0x1401cdfbb  add     rsp, 60h
0x1401cdfbf  pop     r15
0x1401cdfc1  pop     r14
0x1401cdfc3  pop     r13
0x1401cdfc5  pop     r12
0x1401cdfc7  pop     rdi
0x1401cdfc8  pop     rsi
0x1401cdfc9  pop     rbp
0x1401cdfca  retn
```
