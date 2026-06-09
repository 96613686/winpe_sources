# xxxResetDisplayDevice

- ea: `0x14009f610`
- end: `0x14009fb3b`
- name: `xxxResetDisplayDevice`
- size: `1323`
- prototype: `__int64 __fastcall(__int64, int *, __int64)`
- caller_count: `4`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1401141a8`
- `0x140197a80`
- `0x1401bf420`
- `0x1401df724`

## callees

- `0x140035ecc`
- `0x14004dcd0`
- `0x14004dfb0`
- `0x14006b610`
- `0x14009f610`
- `0x14009fb50`
- `0x14009fc4c`
- `0x1400a0784`
- `0x1400a07f8`
- `0x1400a0830`
- `0x1400a08bc`
- `0x1400a0914`
- `0x1400a09bc`
- `0x1400a0a00`
- `0x1400a0a8c`
- `0x140180648`
- `0x14018a600`
- `0x14018b328`
- `0x14018e574`
- `0x140236628`
- `0x14023685c`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14009f8bc`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14009f8bc`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14009f8f3`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14009f8f3`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14009f6d7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14009f6d7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f68d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f6b2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f6fb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f720`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f748`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f790`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f7b5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f817`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f85f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f884`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f92f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f95c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f9d6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009facf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009fafc`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f68d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f6b2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f6fb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f720`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f748`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f790`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f7b5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f817`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f85f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f884`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f92f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f95c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009f9d6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009facf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14009fafc`
- `WIN32K!W32GetUserSessionState` at `0x14009f632`
- `WIN32K!W32GetUserSessionState` at `0x14009f9b5`
- `WIN32K!W32GetUserSessionState` at `0x14009f632`
- `WIN32K!W32GetUserSessionState` at `0x14009f9b5`

## pseudocode

```c
__int64 __fastcall xxxResetDisplayDevice(__int64 a1, int *a2, __int64 a3)
{
  volatile signed __int32 *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // r9
  int v9; // eax
  unsigned __int16 v10; // r15
  struct tagTHREADINFO *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  AtomicExecutionCheck *v14; // rcx
  int (*v15)(void); // rax
  void (*v16)(void); // rax
  __int64 v17; // rcx
  __int64 CurrentThreadWin32Thread; // rdi
  __int64 v19; // rcx
  int updated; // esi
  __int64 v21; // rcx
  int (*v22)(void); // rax
  void (*v23)(void); // rax
  int (*v24)(void); // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  CMonitorTopology *v28; // rcx
  int (*v29)(void); // rax
  void (__fastcall *v30)(__int64); // rax
  __int64 v31; // rcx
  int (*v32)(void); // rax
  int v33; // r9d
  __int64 v34; // rcx
  int (*v35)(void); // rax
  __int64 v36; // rcx
  void (__fastcall *v37)(__int64, __int64, __int64); // rax
  int (*v39)(void); // rax
  void (*v40)(void); // rax
  __int64 v41; // rax
  int v42; // edi
  __int64 v43; // rcx
  BOOL v44; // esi
  void (__fastcall *v45)(__int64, BOOL, _QWORD, _QWORD); // rax
  volatile signed __int32 *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  int (*v49)(void); // rax
  __int64 v50; // rcx
  unsigned int (__fastcall *v51)(__int64); // rax
  __int64 v52; // rcx
  _QWORD v53[4]; // [rsp+40h] [rbp-20h] BYREF
  int CurrentProcessSessionId; // [rsp+98h] [rbp+38h] BYREF
  volatile signed __int32 *v55; // [rsp+A8h] [rbp+48h] BYREF

  v6 = 0;
  v8 = *(_QWORD *)(W32GetUserSessionState(a1, a2) + 19704);
  v9 = *a2;
  v10 = *(_WORD *)(v8 + 6996);
  v55 = 0;
  if ( (v9 & 1) == 0 )
  {
    if ( a1 && (v6 = *(volatile signed __int32 **)(a1 + 264)) != 0 )
    {
      v55 = *(volatile signed __int32 **)(a1 + 264);
      *(_QWORD *)(a1 + 264) = 0;
    }
    else
    {
      ApiSetEditionGetCurrentMonitorTopology(&v55);
      v6 = v55;
    }
  }
  v11 = PtiCurrent(v7);
  v53[0] = *((_QWORD *)v11 + 47);
  *((_QWORD *)v11 + 47) = v53;
  v53[2] = _lambda_fd77beed04b6b1a39114e0f43ae1b0ce_::_lambda_invoker_cdecl_;
  v53[1] = v6;
  DestroyMonitorDCs();
  v14 = *(AtomicExecutionCheck **)(W32GetWin32kBaseApiSetTable(v12) + 48);
  v15 = (int (*)(void))*((_QWORD *)v14 + 575);
  if ( v15 )
  {
    if ( v15() >= 0 )
    {
      v14 = *(AtomicExecutionCheck **)(W32GetWin32kBaseApiSetTable(v14) + 48);
      v16 = (void (*)(void))*((_QWORD *)v14 + 576);
      if ( v16 )
        v16();
    }
  }
  AtomicExecutionCheck::EnforceConsistency(v14, v13);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v17);
  ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
  updated = zzzUpdateUserScreen();
  if ( updated >= 0 )
  {
    v19 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v19) + 48);
    v39 = *(int (**)(void))(v19 + 3264);
    if ( v39 )
    {
      if ( v39() >= 0 )
      {
        v19 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v19) + 48);
        v40 = *(void (**)(void))(v19 + 3272);
        if ( v40 )
          v40();
      }
    }
  }
  --*(_DWORD *)(CurrentThreadWin32Thread + 28);
  v21 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v19) + 48);
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
  if ( updated < 0 )
  {
    PopAndFreeW32ThreadLock((__int64)v53);
    return (unsigned int)updated;
  }
  else
  {
    v24 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v21) + 48) + 3280LL);
    if ( v24 )
    {
      if ( v24() >= 0 )
      {
        v42 = *a2;
        v43 = *(_QWORD *)(W32GetUserSessionState(v26, v25) + 19704);
        v44 = v10 != *(_WORD *)(v43 + 6996);
        v45 = *(void (__fastcall **)(__int64, BOOL, _QWORD, _QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v43) + 48)
                                                                   + 3288LL);
        if ( v45 )
          v45(a1, v44, (unsigned int)-__CFSHR__(v42, 2), (unsigned int)-__CFSHR__(v42, 4));
      }
    }
    ResetSystemColors();
    if ( (int)IsCreateBitmapStripSupported() >= 0 )
      CreateBitmapStrip();
    if ( (int)IsDwmAsyncNotifyDisplayModeChangeSupported() >= 0 )
    {
      v41 = ReferenceDwmApiPort();
      DwmAsyncNotifyDisplayModeChange(v41);
    }
    v28 = *(CMonitorTopology **)(W32GetWin32kBaseApiSetTable(v27) + 48);
    v29 = (int (*)(void))*((_QWORD *)v28 + 416);
    if ( v29 )
    {
      if ( v29() >= 0 )
      {
        v28 = *(CMonitorTopology **)(W32GetWin32kBaseApiSetTable(v28) + 48);
        v30 = (void (__fastcall *)(__int64))*((_QWORD *)v28 + 417);
        if ( v30 )
          v30(a1);
      }
    }
    if ( a1 )
    {
      v28 = *(CMonitorTopology **)(a1 + 264);
      if ( v28 )
      {
        CMonitorTopology::Release(v28);
        *(_QWORD *)(a1 + 264) = 0;
      }
    }
    if ( (*a2 & 2) != 0
      && (v49 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v28) + 48) + 3344LL)) != 0
      && v49() >= 0
      && (v51 = *(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v50) + 48) + 3352LL)) != 0
      && v51(a1) )
    {
      if ( (Microsoft_Windows_Win32kEnableBits & 0x4000000) != 0 )
        McTemplateK0_EtwWriteTransfer(v52, (const EVENT_DESCRIPTOR *)ChangeDisplayModeDeferral, 0);
      *(_DWORD *)(**(_QWORD **)(a1 + 8) + 64LL) |= 2u;
      v46 = v55;
      if ( v55 )
      {
        *(_QWORD *)(a1 + 264) = v55;
        _InterlockedIncrement(v46);
      }
      if ( (int)IsPostIAMShellHookMessageExSupported() >= 0 )
        PostIAMShellHookMessageEx(a1, 35, 1);
      if ( (int)IsxxxBroadcastDisplaySettingsChangeSupported() >= 0 )
        xxxBroadcastDisplaySettingsChange(a1, v47, v48, 2);
    }
    else
    {
      if ( (int)IsPostIAMShellHookMessageExSupported() >= 0 )
        PostIAMShellHookMessageEx(a1, 35, 0);
      v32 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v31) + 48) + 3392LL);
      if ( v32 && v32() >= 0 )
        xxxDesktopsRecalcAndBroadcastDisplayChange(a1, (_DWORD)v55, v10, v33, (__int64)a2, a3);
    }
    PopAndFreeW32ThreadLock((__int64)v53);
    v35 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v34) + 48) + 3408LL);
    if ( v35 )
    {
      if ( v35() >= 0 )
      {
        v37 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v36) + 48)
                                                               + 3416LL);
        if ( v37 )
          v37(a1, 1, 1);
      }
    }
    if ( (*a2 & 2) == 0 )
      CacheRotationInfo();
    CurrentProcessSessionId = PsGetCurrentProcessSessionId();
    ZwUpdateWnfStateData(&WNF_DX_DISPLAY_CONFIG_CHANGE_NOTIFICATION, 0, 0, 0, &CurrentProcessSessionId, 0, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x14009f610  mov     [rsp-28h+arg_0], rbx
0x14009f615  mov     [rsp-28h+arg_10], rsi
0x14009f61a  push    rbp
0x14009f61b  push    rdi
0x14009f61c  push    r12
0x14009f61e  push    r14
0x14009f620  push    r15
0x14009f622  mov     rbp, rsp
0x14009f625  sub     rsp, 60h
0x14009f629  mov     r12, r8
0x14009f62c  mov     r14, rdx
0x14009f62f  mov     rbx, rcx
0x14009f632  call    cs:__imp_W32GetUserSessionState
0x14009f639  nop     dword ptr [rax+rax+00h]
0x14009f63e  xor     edi, edi
0x14009f640  mov     r9, [rax+4CF8h]
0x14009f647  mov     eax, [r14]
0x14009f64a  movzx   r15d, word ptr [r9+1B54h]
0x14009f652  mov     [rbp+arg_18], rdi
0x14009f656  test    al, 1
0x14009f658  jz      loc_14009FA83
0x14009f65e  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14009f663  mov     rcx, [rax+178h]
0x14009f66a  mov     [rbp+var_20], rcx
0x14009f66e  lea     rcx, [rbp+var_20]
0x14009f672  mov     [rax+178h], rcx
0x14009f679  lea     rax, ?_lambda_invoker_cdecl_@_lambda_fd77beed04b6b1a39114e0f43ae1b0ce_@@CA@PEAVCMonitorTopology@@@Z; _lambda_fd77beed04b6b1a39114e0f43ae1b0ce_::_lambda_invoker_cdecl_(CMonitorTopology *)
0x14009f680  mov     [rbp+var_10], rax
0x14009f684  mov     [rbp+var_18], rdi
0x14009f688  call    DestroyMonitorDCs
0x14009f68d  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f694  nop     dword ptr [rax+rax+00h]
0x14009f699  mov     rcx, [rax+30h]
0x14009f69d  mov     rax, [rcx+11F8h]
0x14009f6a4  test    rax, rax
0x14009f6a7  jz      short loc_14009F6D2
0x14009f6a9  call    _guard_dispatch_icall
0x14009f6ae  test    eax, eax
0x14009f6b0  js      short loc_14009F6D2
0x14009f6b2  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f6b9  nop     dword ptr [rax+rax+00h]
0x14009f6be  mov     rcx, [rax+30h]; this
0x14009f6c2  mov     rax, [rcx+1200h]
0x14009f6c9  test    rax, rax
0x14009f6cc  jnz     loc_14009F91B
0x14009f6d2  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x14009f6d7  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14009f6de  nop     dword ptr [rax+rax+00h]
0x14009f6e3  mov     rdi, rax
0x14009f6e6  inc     dword ptr [rax+1Ch]
0x14009f6e9  call    ?zzzUpdateUserScreen@@YAJXZ; zzzUpdateUserScreen(void)
0x14009f6ee  mov     esi, eax
0x14009f6f0  test    eax, eax
0x14009f6f2  jns     loc_14009F92F
0x14009f6f8  dec     dword ptr [rdi+1Ch]
0x14009f6fb  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f702  nop     dword ptr [rax+rax+00h]
0x14009f707  mov     rcx, [rax+30h]
0x14009f70b  mov     rax, [rcx+1208h]
0x14009f712  test    rax, rax
0x14009f715  jz      short loc_14009F740
0x14009f717  call    _guard_dispatch_icall
0x14009f71c  test    eax, eax
0x14009f71e  js      short loc_14009F740
0x14009f720  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f727  nop     dword ptr [rax+rax+00h]
0x14009f72c  mov     rcx, [rax+30h]
0x14009f730  mov     rax, [rcx+1210h]
0x14009f737  test    rax, rax
0x14009f73a  jnz     loc_14009F925
0x14009f740  test    esi, esi
0x14009f742  js      loc_14009F9A2
0x14009f748  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f74f  nop     dword ptr [rax+rax+00h]
0x14009f754  mov     rcx, [rax+30h]
0x14009f758  mov     rax, [rcx+0CD0h]
0x14009f75f  test    rax, rax
0x14009f762  jz      short loc_14009F771
0x14009f764  call    _guard_dispatch_icall
0x14009f769  test    eax, eax
0x14009f76b  jns     loc_14009F9B2
0x14009f771  call    ?ResetSystemColors@@YAXXZ; ResetSystemColors(void)
0x14009f776  call    IsCreateBitmapStripSupported
0x14009f77b  test    eax, eax
0x14009f77d  jns     loc_14009F998
0x14009f783  call    IsDwmAsyncNotifyDisplayModeChangeSupported
0x14009f788  test    eax, eax
0x14009f78a  jns     loc_14009F986
0x14009f790  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f797  nop     dword ptr [rax+rax+00h]
0x14009f79c  mov     rcx, [rax+30h]
0x14009f7a0  mov     rax, [rcx+0D00h]
0x14009f7a7  test    rax, rax
0x14009f7aa  jz      short loc_14009F7D9
0x14009f7ac  call    _guard_dispatch_icall
0x14009f7b1  test    eax, eax
0x14009f7b3  js      short loc_14009F7D9
0x14009f7b5  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f7bc  nop     dword ptr [rax+rax+00h]
0x14009f7c1  mov     rcx, [rax+30h]
0x14009f7c5  mov     rax, [rcx+0D08h]
0x14009f7cc  test    rax, rax
0x14009f7cf  jz      short loc_14009F7D9
0x14009f7d1  mov     rcx, rbx
0x14009f7d4  call    _guard_dispatch_icall
0x14009f7d9  test    rbx, rbx
0x14009f7dc  jz      short loc_14009F7EE
0x14009f7de  mov     rcx, [rbx+108h]; this
0x14009f7e5  test    rcx, rcx
0x14009f7e8  jnz     loc_14009FABA
0x14009f7ee  mov     eax, [r14]
0x14009f7f1  mov     edi, 2
0x14009f7f6  test    dil, al
0x14009f7f9  jnz     loc_14009FACF
0x14009f7ff  call    IsPostIAMShellHookMessageExSupported
0x14009f804  test    eax, eax
0x14009f806  js      short loc_14009F817
0x14009f808  xor     r8d, r8d
0x14009f80b  mov     rcx, rbx
0x14009f80e  lea     edx, [r8+23h]
0x14009f812  call    PostIAMShellHookMessageEx
0x14009f817  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f81e  nop     dword ptr [rax+rax+00h]
0x14009f823  mov     rcx, [rax+30h]
0x14009f827  mov     rax, [rcx+0D40h]
0x14009f82e  test    rax, rax
0x14009f831  jz      short loc_14009F856
0x14009f833  call    _guard_dispatch_icall
0x14009f838  test    eax, eax
0x14009f83a  js      short loc_14009F856
0x14009f83c  mov     rdx, [rbp+arg_18]
0x14009f840  movzx   r8d, r15w
0x14009f844  mov     [rsp+60h+var_38], r12
0x14009f849  mov     rcx, rbx
0x14009f84c  mov     [rsp+60h+var_40], r14
0x14009f851  call    xxxDesktopsRecalcAndBroadcastDisplayChange
0x14009f856  lea     rcx, [rbp+var_20]
0x14009f85a  call    PopAndFreeW32ThreadLock
0x14009f85f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f866  nop     dword ptr [rax+rax+00h]
0x14009f86b  mov     rcx, [rax+30h]
0x14009f86f  mov     rax, [rcx+0D50h]
0x14009f876  test    rax, rax
0x14009f879  jz      short loc_14009F8B0
0x14009f87b  call    _guard_dispatch_icall
0x14009f880  test    eax, eax
0x14009f882  js      short loc_14009F8B0
0x14009f884  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f88b  nop     dword ptr [rax+rax+00h]
0x14009f890  mov     rcx, [rax+30h]
0x14009f894  mov     rax, [rcx+0D58h]
0x14009f89b  test    rax, rax
0x14009f89e  jz      short loc_14009F8B0
0x14009f8a0  mov     edx, 1
0x14009f8a5  mov     rcx, rbx
0x14009f8a8  mov     r8d, edx
0x14009f8ab  call    _guard_dispatch_icall
0x14009f8b0  mov     eax, [r14]
0x14009f8b3  test    dil, al
0x14009f8b6  jz      loc_14009FB31
0x14009f8bc  call    cs:__imp_PsGetCurrentProcessSessionId
0x14009f8c3  nop     dword ptr [rax+rax+00h]
0x14009f8c8  mov     [rsp+60h+var_30], 0
0x14009f8d0  lea     rcx, WNF_DX_DISPLAY_CONFIG_CHANGE_NOTIFICATION
0x14009f8d7  mov     [rbp+arg_8], eax
0x14009f8da  xor     r9d, r9d
0x14009f8dd  lea     rax, [rbp+arg_8]
0x14009f8e1  mov     dword ptr [rsp+60h+var_38], 0
0x14009f8e9  xor     r8d, r8d
0x14009f8ec  mov     [rsp+60h+var_40], rax
0x14009f8f1  xor     edx, edx
0x14009f8f3  call    cs:__imp_ZwUpdateWnfStateData
0x14009f8fa  nop     dword ptr [rax+rax+00h]
0x14009f8ff  xor     eax, eax
0x14009f901  lea     r11, [rsp+60h+var_s0]
0x14009f906  mov     rbx, [r11+30h]
0x14009f90a  mov     rsi, [r11+40h]
0x14009f90e  mov     rsp, r11
0x14009f911  pop     r15
0x14009f913  pop     r14
0x14009f915  pop     r12
0x14009f917  pop     rdi
0x14009f918  pop     rbp
0x14009f919  retn
0x14009f91b  call    _guard_dispatch_icall
0x14009f920  jmp     loc_14009F6D2
0x14009f925  call    _guard_dispatch_icall
0x14009f92a  jmp     loc_14009F740
0x14009f92f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f936  nop     dword ptr [rax+rax+00h]
0x14009f93b  mov     rcx, [rax+30h]
0x14009f93f  mov     rax, [rcx+0CC0h]
0x14009f946  test    rax, rax
0x14009f949  jz      loc_14009F6F8
0x14009f94f  call    _guard_dispatch_icall
0x14009f954  test    eax, eax
0x14009f956  js      loc_14009F6F8
0x14009f95c  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f963  nop     dword ptr [rax+rax+00h]
0x14009f968  mov     rcx, [rax+30h]
0x14009f96c  mov     rax, [rcx+0CC8h]
0x14009f973  test    rax, rax
0x14009f976  jz      loc_14009F6F8
0x14009f97c  call    _guard_dispatch_icall
0x14009f981  jmp     loc_14009F6F8
0x14009f986  call    ReferenceDwmApiPort
0x14009f98b  mov     rcx, rax
0x14009f98e  call    DwmAsyncNotifyDisplayModeChange
0x14009f993  jmp     loc_14009F790
0x14009f998  call    CreateBitmapStrip
0x14009f99d  jmp     loc_14009F783
0x14009f9a2  lea     rcx, [rbp+var_20]
0x14009f9a6  call    PopAndFreeW32ThreadLock
0x14009f9ab  mov     eax, esi
0x14009f9ad  jmp     loc_14009F901
0x14009f9b2  mov     edi, [r14]
0x14009f9b5  call    cs:__imp_W32GetUserSessionState
0x14009f9bc  nop     dword ptr [rax+rax+00h]
0x14009f9c1  xor     esi, esi
0x14009f9c3  mov     rcx, [rax+4CF8h]
0x14009f9ca  cmp     r15w, [rcx+1B54h]
0x14009f9d2  setnz   sil
0x14009f9d6  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009f9dd  nop     dword ptr [rax+rax+00h]
0x14009f9e2  mov     rcx, [rax+30h]
0x14009f9e6  mov     rax, [rcx+0CD8h]
0x14009f9ed  test    rax, rax
0x14009f9f0  jz      loc_14009F771
0x14009f9f6  mov     r9d, edi
0x14009f9f9  mov     edx, esi
0x14009f9fb  shr     r9d, 4
0x14009f9ff  mov     rcx, rbx
0x14009fa02  sbb     r9d, r9d
0x14009fa05  shr     edi, 2
0x14009fa08  sbb     edi, edi
0x14009fa0a  mov     r8d, edi
0x14009fa0d  call    _guard_dispatch_icall
0x14009fa12  jmp     loc_14009F771
0x14009fa17  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+3, 4
0x14009fa1e  jz      short loc_14009FA2F
0x14009fa20  xor     r8d, r8d
0x14009fa23  lea     rdx, ChangeDisplayModeDeferral
0x14009fa2a  call    McTemplateK0_EtwWriteTransfer
0x14009fa2f  mov     rax, [rbx+8]
0x14009fa33  mov     rcx, [rax]
0x14009fa36  or      [rcx+40h], edi
0x14009fa39  mov     rax, [rbp+arg_18]
0x14009fa3d  test    rax, rax
0x14009fa40  jz      short loc_14009FA4C
0x14009fa42  mov     [rbx+108h], rax
0x14009fa49  lock inc dword ptr [rax]
0x14009fa4c  call    IsPostIAMShellHookMessageExSupported
0x14009fa51  test    eax, eax
0x14009fa53  js      short loc_14009FA66
0x14009fa55  mov     edx, 23h ; '#'
0x14009fa5a  mov     rcx, rbx
0x14009fa5d  lea     r8d, [rdx-22h]
0x14009fa61  call    PostIAMShellHookMessageEx
0x14009fa66  call    IsxxxBroadcastDisplaySettingsChangeSupported
0x14009fa6b  test    eax, eax
0x14009fa6d  js      loc_14009F856
0x14009fa73  mov     r9d, edi
0x14009fa76  mov     rcx, rbx
0x14009fa79  call    xxxBroadcastDisplaySettingsChange
0x14009fa7e  jmp     loc_14009F856
0x14009fa83  test    rbx, rbx
0x14009fa86  jz      short loc_14009FAA8
0x14009fa88  mov     rdi, [rbx+108h]
0x14009fa8f  test    rdi, rdi
0x14009fa92  jz      short loc_14009FAA8
0x14009fa94  mov     [rbp+arg_18], rdi
0x14009fa98  mov     qword ptr [rbx+108h], 0
0x14009faa3  jmp     loc_14009F65E
0x14009faa8  lea     rcx, [rbp+arg_18]
0x14009faac  call    ApiSetEditionGetCurrentMonitorTopology
0x14009fab1  mov     rdi, [rbp+arg_18]
0x14009fab5  jmp     loc_14009F65E
0x14009faba  call    ?Release@CMonitorTopology@@QEAAXXZ; CMonitorTopology::Release(void)
0x14009fabf  mov     qword ptr [rbx+108h], 0
0x14009faca  jmp     loc_14009F7EE
0x14009facf  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009fad6  nop     dword ptr [rax+rax+00h]
0x14009fadb  mov     rcx, [rax+30h]
0x14009fadf  mov     rax, [rcx+0D10h]
0x14009fae6  test    rax, rax
0x14009fae9  jz      loc_14009F7FF
0x14009faef  call    _guard_dispatch_icall
0x14009faf4  test    eax, eax
0x14009faf6  js      loc_14009F7FF
0x14009fafc  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14009fb03  nop     dword ptr [rax+rax+00h]
0x14009fb08  mov     rcx, [rax+30h]
0x14009fb0c  mov     rax, [rcx+0D18h]
0x14009fb13  test    rax, rax
0x14009fb16  jz      loc_14009F7FF
0x14009fb1c  mov     rcx, rbx
0x14009fb1f  call    _guard_dispatch_icall
0x14009fb24  test    eax, eax
0x14009fb26  jz      loc_14009F7FF
0x14009fb2c  jmp     loc_14009FA17
  ... truncated ...
```
