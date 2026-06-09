# xxxResetDisplayDevice

- ea: `0x1401946b0`
- end: `0x140194b62`
- name: `xxxResetDisplayDevice`
- size: `1202`
- prototype: ``
- caller_count: `4`
- callee_count: `24`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140111338`
- `0x140195420`
- `0x1401be2f0`
- `0x1401debe4`

## callees

- `0x1400768a0`
- `0x140076b80`
- `0x140090d1c`
- `0x1400984d0`
- `0x1400b0c7c`
- `0x1400b0cc0`
- `0x1400b0d4c`
- `0x1400cc720`
- `0x140108438`
- `0x140156e68`
- `0x14015b9bc`
- `0x1401672e0`
- `0x14017b1e4`
- `0x14017e298`
- `0x14017e948`
- `0x140187358`
- `0x140188cc0`
- `0x1401899e8`
- `0x14018cca4`
- `0x1401946b0`
- `0x1401cb1a8`
- `0x140235ca8`
- `0x140235edc`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140194b03`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140194b03`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140194b3a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140194b3a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401947ac`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401947ac`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194761`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194786`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401947c9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401947ee`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194812`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194837`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019486c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401948b5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194916`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019493b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019499e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401949cb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194a9c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194ac1`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194761`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194786`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401947c9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401947ee`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194812`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194837`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019486c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401948b5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194916`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019493b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14019499e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401949cb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194a9c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140194ac1`
- `WIN32K!W32GetUserSessionState` at `0x1401946d2`
- `WIN32K!W32GetUserSessionState` at `0x140194894`
- `WIN32K!W32GetUserSessionState` at `0x1401946d2`
- `WIN32K!W32GetUserSessionState` at `0x140194894`

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
  __int64 v26; // rcx
  int v27; // edi
  __int64 v28; // rcx
  BOOL v29; // esi
  void (__fastcall *v30)(__int64, BOOL, _QWORD, _QWORD); // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  int (*v33)(void); // rax
  __int64 v34; // rcx
  void (__fastcall *v35)(__int64); // rax
  CMonitorTopology *v36; // rcx
  int (*v37)(void); // rax
  __int64 v38; // rcx
  unsigned int (__fastcall *v39)(__int64); // rax
  __int64 v40; // rcx
  volatile signed __int32 *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  int v44; // r9d
  __int64 v45; // rcx
  int (*v46)(void); // rax
  __int64 v47; // rcx
  void (__fastcall *v48)(__int64, __int64, __int64); // rax
  _QWORD v49[4]; // [rsp+40h] [rbp-20h] BYREF
  volatile signed __int32 *v50; // [rsp+A8h] [rbp+48h] BYREF

  v6 = 0;
  v7 = *(_QWORD *)(W32GetUserSessionState(a1) + 19704);
  v8 = *a2;
  v9 = *(_WORD *)(v7 + 6996);
  v50 = 0;
  if ( (v8 & 1) == 0 )
  {
    if ( !(unsigned int)Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline()
      && a1
      && (v6 = *(volatile signed __int32 **)(a1 + 264)) != 0 )
    {
      v50 = *(volatile signed __int32 **)(a1 + 264);
      *(_QWORD *)(a1 + 264) = 0;
    }
    else
    {
      ApiSetEditionGetCurrentMonitorTopology(&v50);
      v6 = v50;
    }
  }
  v10 = PtiCurrent();
  v49[0] = *((_QWORD *)v10 + 47);
  *((_QWORD *)v10 + 47) = v49;
  v49[2] = _lambda_fd77beed04b6b1a39114e0f43ae1b0ce_::_lambda_invoker_cdecl_;
  v49[1] = v6;
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
        v27 = *a2;
        v28 = *(_QWORD *)(W32GetUserSessionState(v26) + 19704);
        v29 = v9 != *(_WORD *)(v28 + 6996);
        v30 = *(void (__fastcall **)(__int64, BOOL, _QWORD, _QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v28) + 48)
                                                                   + 3288LL);
        if ( v30 )
          v30(a1, v29, (unsigned int)-__CFSHR__(v27, 2), (unsigned int)-__CFSHR__(v27, 4));
      }
    }
    ResetSystemColors();
    if ( (int)IsCreateBitmapStripSupported() >= 0 )
      CreateBitmapStrip();
    if ( (int)IsDwmAsyncNotifyDisplayModeChangeSupported() >= 0 )
    {
      v32 = ReferenceDwmApiPort();
      DwmAsyncNotifyDisplayModeChange(v32);
    }
    v33 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v31) + 48) + 3328LL);
    if ( v33 )
    {
      if ( v33() >= 0 )
      {
        v35 = *(void (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v34) + 48) + 3336LL);
        if ( v35 )
          v35(a1);
      }
    }
    if ( (unsigned int)Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline() )
      goto LABEL_51;
    if ( a1 )
    {
      v36 = *(CMonitorTopology **)(a1 + 264);
      if ( v36 )
      {
        CMonitorTopology::Release(v36);
        *(_QWORD *)(a1 + 264) = 0;
      }
    }
    if ( (*a2 & 2) != 0
      && (v37 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v36) + 48) + 3344LL)) != 0
      && v37() >= 0
      && (v39 = *(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v38) + 48) + 3352LL)) != 0
      && v39(a1) )
    {
      if ( (Microsoft_Windows_Win32kEnableBits & 0x4000000) != 0 )
        McTemplateK0_EtwWriteTransfer(v40, ChangeDisplayModeDeferral, 0);
      *(_DWORD *)(**(_QWORD **)(a1 + 8) + 64LL) |= 2u;
      v41 = v50;
      if ( v50 )
      {
        *(_QWORD *)(a1 + 264) = v50;
        _InterlockedIncrement(v41);
      }
      if ( (int)IsPostIAMShellHookMessageExSupported() >= 0 )
        PostIAMShellHookMessageEx(a1, 35);
      if ( (int)IsxxxBroadcastDisplaySettingsChangeSupported() >= 0 )
        xxxBroadcastDisplaySettingsChange(a1, v42, v43, 2);
    }
    else
    {
LABEL_51:
      if ( (int)IsPostIAMShellHookMessageExSupported() >= 0 )
        PostIAMShellHookMessageEx(a1, 35);
      if ( (int)IsxxxDesktopsRecalcAndBroadcastDisplayChangeSupported() >= 0 )
        xxxDesktopsRecalcAndBroadcastDisplayChange(a1, (_DWORD)v50, v9, v44, (__int64)a2, a3);
    }
    PopAndFreeW32ThreadLock(v49);
    v46 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v45) + 48) + 3408LL);
    if ( v46 )
    {
      if ( v46() >= 0 )
      {
        v48 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v47) + 48)
                                                               + 3416LL);
        if ( v48 )
          v48(a1, 1, 1);
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
    PopAndFreeW32ThreadLock(v49);
    return (unsigned int)updated;
  }
}

```

## disassembly

```asm
0x1401946b0  mov     [rsp-28h+arg_0], rbx
0x1401946b5  mov     [rsp-28h+arg_10], rsi
0x1401946ba  push    rbp
0x1401946bb  push    rdi
0x1401946bc  push    r12
0x1401946be  push    r14
0x1401946c0  push    r15
0x1401946c2  mov     rbp, rsp
0x1401946c5  sub     rsp, 60h
0x1401946c9  mov     r12, r8
0x1401946cc  mov     r14, rdx
0x1401946cf  mov     rbx, rcx
0x1401946d2  call    cs:__imp_W32GetUserSessionState
0x1401946d9  nop     dword ptr [rax+rax+00h]
0x1401946de  xor     edi, edi
0x1401946e0  mov     r9, [rax+4CF8h]
0x1401946e7  mov     eax, [r14]
0x1401946ea  movzx   r15d, word ptr [r9+1B54h]
0x1401946f2  mov     [rbp+arg_18], rdi
0x1401946f6  test    al, 1
0x1401946f8  jnz     short loc_140194732
0x1401946fa  call    Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline
0x1401946ff  test    eax, eax
0x140194701  jnz     short loc_140194725
0x140194703  test    rbx, rbx
0x140194706  jz      short loc_140194725
0x140194708  mov     rdi, [rbx+108h]
0x14019470f  test    rdi, rdi
0x140194712  jz      short loc_140194725
0x140194714  mov     [rbp+arg_18], rdi
0x140194718  mov     qword ptr [rbx+108h], 0
0x140194723  jmp     short loc_140194732
0x140194725  lea     rcx, [rbp+arg_18]
0x140194729  call    ApiSetEditionGetCurrentMonitorTopology
0x14019472e  mov     rdi, [rbp+arg_18]
0x140194732  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140194737  mov     rcx, [rax+178h]
0x14019473e  mov     [rbp+var_20], rcx
0x140194742  lea     rcx, [rbp+var_20]
0x140194746  mov     [rax+178h], rcx
0x14019474d  lea     rax, ?_lambda_invoker_cdecl_@_lambda_fd77beed04b6b1a39114e0f43ae1b0ce_@@CA@PEAVCMonitorTopology@@@Z; _lambda_fd77beed04b6b1a39114e0f43ae1b0ce_::_lambda_invoker_cdecl_(CMonitorTopology *)
0x140194754  mov     [rbp+var_10], rax
0x140194758  mov     [rbp+var_18], rdi
0x14019475c  call    DestroyMonitorDCs
0x140194761  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194768  nop     dword ptr [rax+rax+00h]
0x14019476d  mov     rcx, [rax+30h]
0x140194771  mov     rax, [rcx+11F8h]
0x140194778  test    rax, rax
0x14019477b  jz      short loc_1401947A7
0x14019477d  call    _guard_dispatch_icall
0x140194782  test    eax, eax
0x140194784  js      short loc_1401947A7
0x140194786  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14019478d  nop     dword ptr [rax+rax+00h]
0x140194792  mov     rcx, [rax+30h]
0x140194796  mov     rax, [rcx+1200h]
0x14019479d  test    rax, rax
0x1401947a0  jz      short loc_1401947A7
0x1401947a2  call    _guard_dispatch_icall
0x1401947a7  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x1401947ac  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1401947b3  nop     dword ptr [rax+rax+00h]
0x1401947b8  mov     rdi, rax
0x1401947bb  inc     dword ptr [rax+1Ch]
0x1401947be  call    ?zzzUpdateUserScreen@@YAJXZ; zzzUpdateUserScreen(void)
0x1401947c3  mov     esi, eax
0x1401947c5  test    eax, eax
0x1401947c7  js      short loc_14019480F
0x1401947c9  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401947d0  nop     dword ptr [rax+rax+00h]
0x1401947d5  mov     rcx, [rax+30h]
0x1401947d9  mov     rax, [rcx+0CC0h]
0x1401947e0  test    rax, rax
0x1401947e3  jz      short loc_14019480F
0x1401947e5  call    _guard_dispatch_icall
0x1401947ea  test    eax, eax
0x1401947ec  js      short loc_14019480F
0x1401947ee  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401947f5  nop     dword ptr [rax+rax+00h]
0x1401947fa  mov     rcx, [rax+30h]
0x1401947fe  mov     rax, [rcx+0CC8h]
0x140194805  test    rax, rax
0x140194808  jz      short loc_14019480F
0x14019480a  call    _guard_dispatch_icall
0x14019480f  dec     dword ptr [rdi+1Ch]
0x140194812  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194819  nop     dword ptr [rax+rax+00h]
0x14019481e  mov     rcx, [rax+30h]
0x140194822  mov     rax, [rcx+1208h]
0x140194829  test    rax, rax
0x14019482c  jz      short loc_140194858
0x14019482e  call    _guard_dispatch_icall
0x140194833  test    eax, eax
0x140194835  js      short loc_140194858
0x140194837  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14019483e  nop     dword ptr [rax+rax+00h]
0x140194843  mov     rcx, [rax+30h]
0x140194847  mov     rax, [rcx+1210h]
0x14019484e  test    rax, rax
0x140194851  jz      short loc_140194858
0x140194853  call    _guard_dispatch_icall
0x140194858  test    esi, esi
0x14019485a  jns     short loc_14019486C
0x14019485c  lea     rcx, [rbp+var_20]
0x140194860  call    PopAndFreeW32ThreadLock
0x140194865  mov     eax, esi
0x140194867  jmp     loc_140194B48
0x14019486c  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194873  nop     dword ptr [rax+rax+00h]
0x140194878  mov     rcx, [rax+30h]
0x14019487c  mov     rax, [rcx+0CD0h]
0x140194883  test    rax, rax
0x140194886  jz      short loc_1401948ED
0x140194888  call    _guard_dispatch_icall
0x14019488d  test    eax, eax
0x14019488f  js      short loc_1401948ED
0x140194891  mov     edi, [r14]
0x140194894  call    cs:__imp_W32GetUserSessionState
0x14019489b  nop     dword ptr [rax+rax+00h]
0x1401948a0  xor     esi, esi
0x1401948a2  mov     rcx, [rax+4CF8h]
0x1401948a9  cmp     r15w, [rcx+1B54h]
0x1401948b1  setnz   sil
0x1401948b5  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401948bc  nop     dword ptr [rax+rax+00h]
0x1401948c1  mov     rcx, [rax+30h]
0x1401948c5  mov     rax, [rcx+0CD8h]
0x1401948cc  test    rax, rax
0x1401948cf  jz      short loc_1401948ED
0x1401948d1  mov     r9d, edi
0x1401948d4  mov     edx, esi
0x1401948d6  shr     r9d, 4
0x1401948da  mov     rcx, rbx
0x1401948dd  sbb     r9d, r9d
0x1401948e0  shr     edi, 2
0x1401948e3  sbb     edi, edi
0x1401948e5  mov     r8d, edi
0x1401948e8  call    _guard_dispatch_icall
0x1401948ed  call    ?ResetSystemColors@@YAXXZ; ResetSystemColors(void)
0x1401948f2  call    IsCreateBitmapStripSupported
0x1401948f7  test    eax, eax
0x1401948f9  js      short loc_140194900
0x1401948fb  call    CreateBitmapStrip
0x140194900  call    IsDwmAsyncNotifyDisplayModeChangeSupported
0x140194905  test    eax, eax
0x140194907  js      short loc_140194916
0x140194909  call    ReferenceDwmApiPort
0x14019490e  mov     rcx, rax
0x140194911  call    DwmAsyncNotifyDisplayModeChange
0x140194916  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14019491d  nop     dword ptr [rax+rax+00h]
0x140194922  mov     rcx, [rax+30h]
0x140194926  mov     rax, [rcx+0D00h]
0x14019492d  test    rax, rax
0x140194930  jz      short loc_14019495F
0x140194932  call    _guard_dispatch_icall
0x140194937  test    eax, eax
0x140194939  js      short loc_14019495F
0x14019493b  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194942  nop     dword ptr [rax+rax+00h]
0x140194947  mov     rcx, [rax+30h]
0x14019494b  mov     rax, [rcx+0D08h]
0x140194952  test    rax, rax
0x140194955  jz      short loc_14019495F
0x140194957  mov     rcx, rbx
0x14019495a  call    _guard_dispatch_icall
0x14019495f  call    Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline
0x140194964  mov     edi, 2
0x140194969  test    eax, eax
0x14019496b  jnz     loc_140194A58
0x140194971  test    rbx, rbx
0x140194974  jz      short loc_140194992
0x140194976  mov     rcx, [rbx+108h]; this
0x14019497d  test    rcx, rcx
0x140194980  jz      short loc_140194992
0x140194982  call    ?Release@CMonitorTopology@@QEAAXXZ; CMonitorTopology::Release(void)
0x140194987  mov     qword ptr [rbx+108h], 0
0x140194992  mov     eax, [r14]
0x140194995  test    dil, al
0x140194998  jz      loc_140194A58
0x14019499e  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401949a5  nop     dword ptr [rax+rax+00h]
0x1401949aa  mov     rcx, [rax+30h]
0x1401949ae  mov     rax, [rcx+0D10h]
0x1401949b5  test    rax, rax
0x1401949b8  jz      loc_140194A58
0x1401949be  call    _guard_dispatch_icall
0x1401949c3  test    eax, eax
0x1401949c5  js      loc_140194A58
0x1401949cb  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1401949d2  nop     dword ptr [rax+rax+00h]
0x1401949d7  mov     rcx, [rax+30h]
0x1401949db  mov     rax, [rcx+0D18h]
0x1401949e2  test    rax, rax
0x1401949e5  jz      short loc_140194A58
0x1401949e7  mov     rcx, rbx
0x1401949ea  call    _guard_dispatch_icall
0x1401949ef  test    eax, eax
0x1401949f1  jz      short loc_140194A58
0x1401949f3  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+3, 4
0x1401949fa  jz      short loc_140194A0B
0x1401949fc  xor     r8d, r8d
0x1401949ff  lea     rdx, ChangeDisplayModeDeferral
0x140194a06  call    McTemplateK0_EtwWriteTransfer
0x140194a0b  mov     rax, [rbx+8]
0x140194a0f  mov     rcx, [rax]
0x140194a12  or      [rcx+40h], edi
0x140194a15  mov     rax, [rbp+arg_18]
0x140194a19  test    rax, rax
0x140194a1c  jz      short loc_140194A28
0x140194a1e  mov     [rbx+108h], rax
0x140194a25  lock inc dword ptr [rax]
0x140194a28  call    IsPostIAMShellHookMessageExSupported
0x140194a2d  test    eax, eax
0x140194a2f  js      short loc_140194A42
0x140194a31  mov     edx, 23h ; '#'
0x140194a36  mov     rcx, rbx
0x140194a39  lea     r8d, [rdx-22h]
0x140194a3d  call    PostIAMShellHookMessageEx
0x140194a42  call    IsxxxBroadcastDisplaySettingsChangeSupported
0x140194a47  test    eax, eax
0x140194a49  js      short loc_140194A93
0x140194a4b  mov     r9d, edi
0x140194a4e  mov     rcx, rbx
0x140194a51  call    xxxBroadcastDisplaySettingsChange
0x140194a56  jmp     short loc_140194A93
0x140194a58  call    IsPostIAMShellHookMessageExSupported
0x140194a5d  test    eax, eax
0x140194a5f  js      short loc_140194A70
0x140194a61  xor     r8d, r8d
0x140194a64  mov     rcx, rbx
0x140194a67  lea     edx, [r8+23h]
0x140194a6b  call    PostIAMShellHookMessageEx
0x140194a70  call    IsxxxDesktopsRecalcAndBroadcastDisplayChangeSupported
0x140194a75  test    eax, eax
0x140194a77  js      short loc_140194A93
0x140194a79  mov     rdx, [rbp+arg_18]
0x140194a7d  movzx   r8d, r15w
0x140194a81  mov     [rsp+60h+var_38], r12
0x140194a86  mov     rcx, rbx
0x140194a89  mov     [rsp+60h+var_40], r14
0x140194a8e  call    xxxDesktopsRecalcAndBroadcastDisplayChange
0x140194a93  lea     rcx, [rbp+var_20]
0x140194a97  call    PopAndFreeW32ThreadLock
0x140194a9c  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194aa3  nop     dword ptr [rax+rax+00h]
0x140194aa8  mov     rcx, [rax+30h]
0x140194aac  mov     rax, [rcx+0D50h]
0x140194ab3  test    rax, rax
0x140194ab6  jz      short loc_140194AED
0x140194ab8  call    _guard_dispatch_icall
0x140194abd  test    eax, eax
0x140194abf  js      short loc_140194AED
0x140194ac1  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140194ac8  nop     dword ptr [rax+rax+00h]
0x140194acd  mov     rcx, [rax+30h]
0x140194ad1  mov     rax, [rcx+0D58h]
0x140194ad8  test    rax, rax
0x140194adb  jz      short loc_140194AED
0x140194add  mov     edx, 1
0x140194ae2  mov     rcx, rbx
0x140194ae5  mov     r8d, edx
0x140194ae8  call    _guard_dispatch_icall
0x140194aed  call    Feature_RemoveDeferredRotation__private_IsEnabledDeviceUsageNoInline
0x140194af2  test    eax, eax
0x140194af4  jnz     short loc_140194AFE
0x140194af6  mov     eax, [r14]
0x140194af9  test    dil, al
0x140194afc  jnz     short loc_140194B03
0x140194afe  call    CacheRotationInfo
0x140194b03  call    cs:__imp_PsGetCurrentProcessSessionId
0x140194b0a  nop     dword ptr [rax+rax+00h]
0x140194b0f  mov     [rsp+60h+var_30], 0
0x140194b17  lea     rcx, WNF_DX_DISPLAY_CONFIG_CHANGE_NOTIFICATION
0x140194b1e  mov     [rbp+arg_8], eax
0x140194b21  xor     r9d, r9d
0x140194b24  lea     rax, [rbp+arg_8]
0x140194b28  mov     dword ptr [rsp+60h+var_38], 0
0x140194b30  xor     r8d, r8d
0x140194b33  mov     [rsp+60h+var_40], rax
0x140194b38  xor     edx, edx
0x140194b3a  call    cs:__imp_ZwUpdateWnfStateData
0x140194b41  nop     dword ptr [rax+rax+00h]
0x140194b46  xor     eax, eax
0x140194b48  lea     r11, [rsp+60h+var_s0]
0x140194b4d  mov     rbx, [r11+30h]
0x140194b51  mov     rsi, [r11+40h]
0x140194b55  mov     rsp, r11
0x140194b58  pop     r15
0x140194b5a  pop     r14
0x140194b5c  pop     r12
0x140194b5e  pop     rdi
0x140194b5f  pop     rbp
0x140194b60  retn
```
