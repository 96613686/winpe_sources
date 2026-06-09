# xxxResetDisplayDevice

- ea: `0x140194580`
- end: `0x140194a32`
- name: `xxxResetDisplayDevice`
- size: `1202`
- prototype: ``
- caller_count: `4`
- callee_count: `24`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140111808`
- `0x1401952f0`
- `0x1401be850`
- `0x1401df144`

## callees

- `0x14005c210`
- `0x140065ff8`
- `0x140075700`
- `0x1400759e0`
- `0x140099f1c`
- `0x1400a16d0`
- `0x1400ca38c`
- `0x1400ca3d0`
- `0x1400ca45c`
- `0x1401566b0`
- `0x14015afcc`
- `0x140166a40`
- `0x14017a684`
- `0x14017d828`
- `0x14017ded8`
- `0x1401861f8`
- `0x140187b60`
- `0x140188888`
- `0x14018bcb4`
- `0x140194580`
- `0x1401cb708`
- `0x140236658`
- `0x14023688c`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1401949d3`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1401949d3`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140194a0a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140194a0a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14019467c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14019467c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194631`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194656`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194699`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401946be`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401946e2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194707`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019473c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194785`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401947e6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019480b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019486e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019489b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019496c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194991`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194631`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194656`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194699`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401946be`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401946e2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194707`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019473c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194785`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401947e6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019480b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019486e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019489b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019496c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194991`
- `WIN32K!W32GetUserSessionState` at `0x1401945a2`
- `WIN32K!W32GetUserSessionState` at `0x140194764`
- `WIN32K!W32GetUserSessionState` at `0x1401945a2`
- `WIN32K!W32GetUserSessionState` at `0x140194764`

## pseudocode

```c
__int64 __fastcall xxxResetDisplayDevice(__int64 a1, int *a2, __int64 a3)
{
  volatile signed __int32 *v6; // rdi
  __int64 v7; // r9
  int v8; // eax
  unsigned __int16 v9; // r15
  struct tagTHREADINFO *v10; // rax
  __int64 v11; // rcx
  AtomicExecutionCheck *v12; // rcx
  int (*v13)(void); // rax
  void (*v14)(void); // rax
  __int64 v15; // rcx
  __int64 CurrentThreadWin32Thread; // rdi
  __int64 v17; // rcx
  int updated; // esi
  int (*v19)(void); // rax
  void (*v20)(void); // rax
  __int64 v21; // rcx
  int (*v22)(void); // rax
  void (*v23)(void); // rax
  int (*v25)(void); // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // edi
  __int64 v30; // rcx
  BOOL v31; // esi
  void (__fastcall *v32)(__int64, BOOL, _QWORD, _QWORD); // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  int (*v35)(void); // rax
  __int64 v36; // rcx
  void (__fastcall *v37)(__int64); // rax
  CMonitorTopology *v38; // rcx
  int (*v39)(void); // rax
  __int64 v40; // rcx
  unsigned int (__fastcall *v41)(__int64); // rax
  __int64 v42; // rcx
  volatile signed __int32 *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  int v46; // r9d
  __int64 v47; // rcx
  int (*v48)(void); // rax
  __int64 v49; // rcx
  void (__fastcall *v50)(__int64, __int64, __int64); // rax
  _QWORD v51[4]; // [rsp+40h] [rbp-20h] BYREF
  volatile signed __int32 *v52; // [rsp+A8h] [rbp+48h] BYREF

  v6 = 0;
  v7 = *(_QWORD *)(W32GetUserSessionState(a1, a2, a3) + 19704);
  v8 = *a2;
  v9 = *(_WORD *)(v7 + 6996);
  v52 = 0;
  if ( (v8 & 1) == 0 )
  {
    if ( !(unsigned int)Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline()
      && a1
      && (v6 = *(volatile signed __int32 **)(a1 + 264)) != 0 )
    {
      v52 = *(volatile signed __int32 **)(a1 + 264);
      *(_QWORD *)(a1 + 264) = 0;
    }
    else
    {
      ApiSetEditionGetCurrentMonitorTopology(&v52);
      v6 = v52;
    }
  }
  v10 = PtiCurrent();
  v51[0] = *((_QWORD *)v10 + 47);
  *((_QWORD *)v10 + 47) = v51;
  v51[2] = _lambda_fd77beed04b6b1a39114e0f43ae1b0ce_::_lambda_invoker_cdecl_;
  v51[1] = v6;
  DestroyMonitorDCs();
  v12 = *(AtomicExecutionCheck **)(W32GetWin32kBaseApiSetTable(v11) + 48);
  v13 = (int (*)(void))*((_QWORD *)v12 + 575);
  if ( v13 )
  {
    if ( v13() >= 0 )
    {
      v12 = *(AtomicExecutionCheck **)(W32GetWin32kBaseApiSetTable(v12) + 48);
      v14 = (void (*)(void))*((_QWORD *)v12 + 576);
      if ( v14 )
        v14();
    }
  }
  AtomicExecutionCheck::EnforceConsistency(v12);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v15);
  ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
  updated = zzzUpdateUserScreen();
  if ( updated >= 0 )
  {
    v17 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v17) + 48);
    v19 = *(int (**)(void))(v17 + 3264);
    if ( v19 )
    {
      if ( v19() >= 0 )
      {
        v17 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v17) + 48);
        v20 = *(void (**)(void))(v17 + 3272);
        if ( v20 )
          v20();
      }
    }
  }
  --*(_DWORD *)(CurrentThreadWin32Thread + 28);
  v21 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v17) + 48);
  v22 = *(int (**)(void))(v21 + 4616);
  if ( v22 )
  {
    if ( v22() >= 0 )
    {
      v21 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v21) + 48);
      v23 = *(void (**)(void))(v21 + 4624);
      if ( v23 )
        v23();
    }
  }
  if ( updated >= 0 )
  {
    v25 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v21) + 48) + 3280LL);
    if ( v25 )
    {
      if ( v25() >= 0 )
      {
        v29 = *a2;
        v30 = *(_QWORD *)(W32GetUserSessionState(v27, v26, v28) + 19704);
        v31 = v9 != *(_WORD *)(v30 + 6996);
        v32 = *(void (__fastcall **)(__int64, BOOL, _QWORD, _QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v30) + 48)
                                                                   + 3288LL);
        if ( v32 )
          v32(a1, v31, (unsigned int)-__CFSHR__(v29, 2), (unsigned int)-__CFSHR__(v29, 4));
      }
    }
    ResetSystemColors();
    if ( (int)IsCreateBitmapStripSupported() >= 0 )
      CreateBitmapStrip();
    if ( (int)IsDwmAsyncNotifyDisplayModeChangeSupported() >= 0 )
    {
      v34 = ReferenceDwmApiPort();
      DwmAsyncNotifyDisplayModeChange(v34);
    }
    v35 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v33) + 48) + 3328LL);
    if ( v35 )
    {
      if ( v35() >= 0 )
      {
        v37 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v36) + 48) + 3336LL);
        if ( v37 )
          v37(a1);
      }
    }
    if ( (unsigned int)Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline() )
      goto LABEL_51;
    if ( a1 )
    {
      v38 = *(CMonitorTopology **)(a1 + 264);
      if ( v38 )
      {
        CMonitorTopology::Release(v38);
        *(_QWORD *)(a1 + 264) = 0;
      }
    }
    if ( (*a2 & 2) != 0
      && (v39 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v38) + 48) + 3344LL)) != 0
      && v39() >= 0
      && (v41 = *(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v40) + 48) + 3352LL)) != 0
      && v41(a1) )
    {
      if ( (Microsoft_Windows_Win32kEnableBits & 0x4000000) != 0 )
        McTemplateK0_EtwWriteTransfer(v42, ChangeDisplayModeDeferral, 0);
      *(_DWORD *)(**(_QWORD **)(a1 + 8) + 64LL) |= 2u;
      v43 = v52;
      if ( v52 )
      {
        *(_QWORD *)(a1 + 264) = v52;
        _InterlockedIncrement(v43);
      }
      if ( (int)IsPostIAMShellHookMessageExSupported() >= 0 )
        PostIAMShellHookMessageEx(a1, 35);
      if ( (int)IsxxxBroadcastDisplaySettingsChangeSupported() >= 0 )
        xxxBroadcastDisplaySettingsChange(a1, v44, v45, 2);
    }
    else
    {
LABEL_51:
      if ( (int)IsPostIAMShellHookMessageExSupported() >= 0 )
        PostIAMShellHookMessageEx(a1, 35);
      if ( (int)IsxxxDesktopsRecalcAndBroadcastDisplayChangeSupported() >= 0 )
        xxxDesktopsRecalcAndBroadcastDisplayChange(a1, (_DWORD)v52, v9, v46, (__int64)a2, a3);
    }
    PopAndFreeW32ThreadLock(v51);
    v48 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v47) + 48) + 3408LL);
    if ( v48 )
    {
      if ( v48() >= 0 )
      {
        v50 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v49) + 48)
                                                               + 3416LL);
        if ( v50 )
          v50(a1, 1, 1);
      }
    }
    if ( (unsigned int)Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline() || (*a2 & 2) == 0 )
      CacheRotationInfo();
    PsGetCurrentProcessSessionId();
    ZwUpdateWnfStateData(&WNF_DX_DISPLAY_CONFIG_CHANGE_NOTIFICATION, 0, 0);
    return 0;
  }
  else
  {
    PopAndFreeW32ThreadLock(v51);
    return (unsigned int)updated;
  }
}

```

## disassembly

```asm
0x140194580  mov     [rsp-28h+arg_0], rbx
0x140194585  mov     [rsp-28h+arg_10], rsi
0x14019458a  push    rbp
0x14019458b  push    rdi
0x14019458c  push    r12
0x14019458e  push    r14
0x140194590  push    r15
0x140194592  mov     rbp, rsp
0x140194595  sub     rsp, 60h
0x140194599  mov     r12, r8
0x14019459c  mov     r14, rdx
0x14019459f  mov     rbx, rcx
0x1401945a2  call    cs:__imp_W32GetUserSessionState
0x1401945a9  nop     dword ptr [rax+rax+00h]
0x1401945ae  xor     edi, edi
0x1401945b0  mov     r9, [rax+4CF8h]
0x1401945b7  mov     eax, [r14]
0x1401945ba  movzx   r15d, word ptr [r9+1B54h]
0x1401945c2  mov     [rbp+arg_18], rdi
0x1401945c6  test    al, 1
0x1401945c8  jnz     short loc_140194602
0x1401945ca  call    Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline
0x1401945cf  test    eax, eax
0x1401945d1  jnz     short loc_1401945F5
0x1401945d3  test    rbx, rbx
0x1401945d6  jz      short loc_1401945F5
0x1401945d8  mov     rdi, [rbx+108h]
0x1401945df  test    rdi, rdi
0x1401945e2  jz      short loc_1401945F5
0x1401945e4  mov     [rbp+arg_18], rdi
0x1401945e8  mov     qword ptr [rbx+108h], 0
0x1401945f3  jmp     short loc_140194602
0x1401945f5  lea     rcx, [rbp+arg_18]
0x1401945f9  call    ApiSetEditionGetCurrentMonitorTopology
0x1401945fe  mov     rdi, [rbp+arg_18]
0x140194602  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194607  mov     rcx, [rax+178h]
0x14019460e  mov     [rbp+var_20], rcx
0x140194612  lea     rcx, [rbp+var_20]
0x140194616  mov     [rax+178h], rcx
0x14019461d  lea     rax, ?_lambda_invoker_cdecl_@_lambda_fd77beed04b6b1a39114e0f43ae1b0ce_@@CA@PEAVCMonitorTopology@@@Z; _lambda_fd77beed04b6b1a39114e0f43ae1b0ce_::_lambda_invoker_cdecl_(CMonitorTopology *)
0x140194624  mov     [rbp+var_10], rax
0x140194628  mov     [rbp+var_18], rdi
0x14019462c  call    DestroyMonitorDCs
0x140194631  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194638  nop     dword ptr [rax+rax+00h]
0x14019463d  mov     rcx, [rax+30h]
0x140194641  mov     rax, [rcx+11F8h]
0x140194648  test    rax, rax
0x14019464b  jz      short loc_140194677
0x14019464d  call    _guard_dispatch_icall
0x140194652  test    eax, eax
0x140194654  js      short loc_140194677
0x140194656  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14019465d  nop     dword ptr [rax+rax+00h]
0x140194662  mov     rcx, [rax+30h]
0x140194666  mov     rax, [rcx+1200h]
0x14019466d  test    rax, rax
0x140194670  jz      short loc_140194677
0x140194672  call    _guard_dispatch_icall
0x140194677  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x14019467c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140194683  nop     dword ptr [rax+rax+00h]
0x140194688  mov     rdi, rax
0x14019468b  inc     dword ptr [rax+1Ch]
0x14019468e  call    ?zzzUpdateUserScreen@@YAJXZ; zzzUpdateUserScreen(void)
0x140194693  mov     esi, eax
0x140194695  test    eax, eax
0x140194697  js      short loc_1401946DF
0x140194699  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401946a0  nop     dword ptr [rax+rax+00h]
0x1401946a5  mov     rcx, [rax+30h]
0x1401946a9  mov     rax, [rcx+0CC0h]
0x1401946b0  test    rax, rax
0x1401946b3  jz      short loc_1401946DF
0x1401946b5  call    _guard_dispatch_icall
0x1401946ba  test    eax, eax
0x1401946bc  js      short loc_1401946DF
0x1401946be  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401946c5  nop     dword ptr [rax+rax+00h]
0x1401946ca  mov     rcx, [rax+30h]
0x1401946ce  mov     rax, [rcx+0CC8h]
0x1401946d5  test    rax, rax
0x1401946d8  jz      short loc_1401946DF
0x1401946da  call    _guard_dispatch_icall
0x1401946df  dec     dword ptr [rdi+1Ch]
0x1401946e2  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401946e9  nop     dword ptr [rax+rax+00h]
0x1401946ee  mov     rcx, [rax+30h]
0x1401946f2  mov     rax, [rcx+1208h]
0x1401946f9  test    rax, rax
0x1401946fc  jz      short loc_140194728
0x1401946fe  call    _guard_dispatch_icall
0x140194703  test    eax, eax
0x140194705  js      short loc_140194728
0x140194707  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14019470e  nop     dword ptr [rax+rax+00h]
0x140194713  mov     rcx, [rax+30h]
0x140194717  mov     rax, [rcx+1210h]
0x14019471e  test    rax, rax
0x140194721  jz      short loc_140194728
0x140194723  call    _guard_dispatch_icall
0x140194728  test    esi, esi
0x14019472a  jns     short loc_14019473C
0x14019472c  lea     rcx, [rbp+var_20]
0x140194730  call    PopAndFreeW32ThreadLock
0x140194735  mov     eax, esi
0x140194737  jmp     loc_140194A18
0x14019473c  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194743  nop     dword ptr [rax+rax+00h]
0x140194748  mov     rcx, [rax+30h]
0x14019474c  mov     rax, [rcx+0CD0h]
0x140194753  test    rax, rax
0x140194756  jz      short loc_1401947BD
0x140194758  call    _guard_dispatch_icall
0x14019475d  test    eax, eax
0x14019475f  js      short loc_1401947BD
0x140194761  mov     edi, [r14]
0x140194764  call    cs:__imp_W32GetUserSessionState
0x14019476b  nop     dword ptr [rax+rax+00h]
0x140194770  xor     esi, esi
0x140194772  mov     rcx, [rax+4CF8h]
0x140194779  cmp     r15w, [rcx+1B54h]
0x140194781  setnz   sil
0x140194785  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14019478c  nop     dword ptr [rax+rax+00h]
0x140194791  mov     rcx, [rax+30h]
0x140194795  mov     rax, [rcx+0CD8h]
0x14019479c  test    rax, rax
0x14019479f  jz      short loc_1401947BD
0x1401947a1  mov     r9d, edi
0x1401947a4  mov     edx, esi
0x1401947a6  shr     r9d, 4
0x1401947aa  mov     rcx, rbx
0x1401947ad  sbb     r9d, r9d
0x1401947b0  shr     edi, 2
0x1401947b3  sbb     edi, edi
0x1401947b5  mov     r8d, edi
0x1401947b8  call    _guard_dispatch_icall
0x1401947bd  call    ?ResetSystemColors@@YAXXZ; ResetSystemColors(void)
0x1401947c2  call    IsCreateBitmapStripSupported
0x1401947c7  test    eax, eax
0x1401947c9  js      short loc_1401947D0
0x1401947cb  call    CreateBitmapStrip
0x1401947d0  call    IsDwmAsyncNotifyDisplayModeChangeSupported
0x1401947d5  test    eax, eax
0x1401947d7  js      short loc_1401947E6
0x1401947d9  call    ReferenceDwmApiPort
0x1401947de  mov     rcx, rax
0x1401947e1  call    DwmAsyncNotifyDisplayModeChange
0x1401947e6  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401947ed  nop     dword ptr [rax+rax+00h]
0x1401947f2  mov     rcx, [rax+30h]
0x1401947f6  mov     rax, [rcx+0D00h]
0x1401947fd  test    rax, rax
0x140194800  jz      short loc_14019482F
0x140194802  call    _guard_dispatch_icall
0x140194807  test    eax, eax
0x140194809  js      short loc_14019482F
0x14019480b  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194812  nop     dword ptr [rax+rax+00h]
0x140194817  mov     rcx, [rax+30h]
0x14019481b  mov     rax, [rcx+0D08h]
0x140194822  test    rax, rax
0x140194825  jz      short loc_14019482F
0x140194827  mov     rcx, rbx
0x14019482a  call    _guard_dispatch_icall
0x14019482f  call    Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline
0x140194834  mov     edi, 2
0x140194839  test    eax, eax
0x14019483b  jnz     loc_140194928
0x140194841  test    rbx, rbx
0x140194844  jz      short loc_140194862
0x140194846  mov     rcx, [rbx+108h]; this
0x14019484d  test    rcx, rcx
0x140194850  jz      short loc_140194862
0x140194852  call    ?Release@CMonitorTopology@@QEAAXXZ; CMonitorTopology::Release(void)
0x140194857  mov     qword ptr [rbx+108h], 0
0x140194862  mov     eax, [r14]
0x140194865  test    dil, al
0x140194868  jz      loc_140194928
0x14019486e  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194875  nop     dword ptr [rax+rax+00h]
0x14019487a  mov     rcx, [rax+30h]
0x14019487e  mov     rax, [rcx+0D10h]
0x140194885  test    rax, rax
0x140194888  jz      loc_140194928
0x14019488e  call    _guard_dispatch_icall
0x140194893  test    eax, eax
0x140194895  js      loc_140194928
0x14019489b  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401948a2  nop     dword ptr [rax+rax+00h]
0x1401948a7  mov     rcx, [rax+30h]
0x1401948ab  mov     rax, [rcx+0D18h]
0x1401948b2  test    rax, rax
0x1401948b5  jz      short loc_140194928
0x1401948b7  mov     rcx, rbx
0x1401948ba  call    _guard_dispatch_icall
0x1401948bf  test    eax, eax
0x1401948c1  jz      short loc_140194928
0x1401948c3  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+3, 4
0x1401948ca  jz      short loc_1401948DB
0x1401948cc  xor     r8d, r8d
0x1401948cf  lea     rdx, ChangeDisplayModeDeferral
0x1401948d6  call    McTemplateK0_EtwWriteTransfer
0x1401948db  mov     rax, [rbx+8]
0x1401948df  mov     rcx, [rax]
0x1401948e2  or      [rcx+40h], edi
0x1401948e5  mov     rax, [rbp+arg_18]
0x1401948e9  test    rax, rax
0x1401948ec  jz      short loc_1401948F8
0x1401948ee  mov     [rbx+108h], rax
0x1401948f5  lock inc dword ptr [rax]
0x1401948f8  call    IsPostIAMShellHookMessageExSupported
0x1401948fd  test    eax, eax
0x1401948ff  js      short loc_140194912
0x140194901  mov     edx, 23h ; '#'
0x140194906  mov     rcx, rbx
0x140194909  lea     r8d, [rdx-22h]
0x14019490d  call    PostIAMShellHookMessageEx
0x140194912  call    IsxxxBroadcastDisplaySettingsChangeSupported
0x140194917  test    eax, eax
0x140194919  js      short loc_140194963
0x14019491b  mov     r9d, edi
0x14019491e  mov     rcx, rbx
0x140194921  call    xxxBroadcastDisplaySettingsChange
0x140194926  jmp     short loc_140194963
0x140194928  call    IsPostIAMShellHookMessageExSupported
0x14019492d  test    eax, eax
0x14019492f  js      short loc_140194940
0x140194931  xor     r8d, r8d
0x140194934  mov     rcx, rbx
0x140194937  lea     edx, [r8+23h]
0x14019493b  call    PostIAMShellHookMessageEx
0x140194940  call    IsxxxDesktopsRecalcAndBroadcastDisplayChangeSupported
0x140194945  test    eax, eax
0x140194947  js      short loc_140194963
0x140194949  mov     rdx, [rbp+arg_18]
0x14019494d  movzx   r8d, r15w
0x140194951  mov     [rsp+60h+var_38], r12
0x140194956  mov     rcx, rbx
0x140194959  mov     [rsp+60h+var_40], r14
0x14019495e  call    xxxDesktopsRecalcAndBroadcastDisplayChange
0x140194963  lea     rcx, [rbp+var_20]
0x140194967  call    PopAndFreeW32ThreadLock
0x14019496c  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194973  nop     dword ptr [rax+rax+00h]
0x140194978  mov     rcx, [rax+30h]
0x14019497c  mov     rax, [rcx+0D50h]
0x140194983  test    rax, rax
0x140194986  jz      short loc_1401949BD
0x140194988  call    _guard_dispatch_icall
0x14019498d  test    eax, eax
0x14019498f  js      short loc_1401949BD
0x140194991  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194998  nop     dword ptr [rax+rax+00h]
0x14019499d  mov     rcx, [rax+30h]
0x1401949a1  mov     rax, [rcx+0D58h]
0x1401949a8  test    rax, rax
0x1401949ab  jz      short loc_1401949BD
0x1401949ad  mov     edx, 1
0x1401949b2  mov     rcx, rbx
0x1401949b5  mov     r8d, edx
0x1401949b8  call    _guard_dispatch_icall
0x1401949bd  call    Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline
0x1401949c2  test    eax, eax
0x1401949c4  jnz     short loc_1401949CE
0x1401949c6  mov     eax, [r14]
0x1401949c9  test    dil, al
0x1401949cc  jnz     short loc_1401949D3
0x1401949ce  call    CacheRotationInfo
0x1401949d3  call    cs:__imp_PsGetCurrentProcessSessionId
0x1401949da  nop     dword ptr [rax+rax+00h]
0x1401949df  mov     [rsp+60h+var_30], 0
0x1401949e7  lea     rcx, WNF_DX_DISPLAY_CONFIG_CHANGE_NOTIFICATION
0x1401949ee  mov     [rbp+arg_8], eax
0x1401949f1  xor     r9d, r9d
0x1401949f4  lea     rax, [rbp+arg_8]
0x1401949f8  mov     dword ptr [rsp+60h+var_38], 0
0x140194a00  xor     r8d, r8d
0x140194a03  mov     [rsp+60h+var_40], rax
0x140194a08  xor     edx, edx
0x140194a0a  call    cs:__imp_ZwUpdateWnfStateData
0x140194a11  nop     dword ptr [rax+rax+00h]
0x140194a16  xor     eax, eax
0x140194a18  lea     r11, [rsp+60h+var_s0]
0x140194a1d  mov     rbx, [r11+30h]
0x140194a21  mov     rsi, [r11+40h]
0x140194a25  mov     rsp, r11
0x140194a28  pop     r15
0x140194a2a  pop     r14
0x140194a2c  pop     r12
0x140194a2e  pop     rdi
0x140194a2f  pop     rbp
0x140194a30  retn
```
