# NtUserSetDisplayConfig

- ea: `0x1401dd0e0`
- end: `0x1401dd79a`
- name: `NtUserSetDisplayConfig`
- size: `1722`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140012c80`
- `0x140029324`
- `0x14002a0e4`
- `0x14002aa70`
- `0x14002ab14`
- `0x140043810`
- `0x1400757c8`
- `0x1400759e0`
- `0x140076ef0`
- `0x140076f80`
- `0x1400b2ae0`
- `0x1400b2bac`
- `0x1400efd28`
- `0x140111e68`
- `0x1401175e4`
- `0x14013de9c`
- `0x140175a7c`
- `0x1401881e4`
- `0x1401952f0`
- `0x1401af6e0`
- `0x1401c7338`
- `0x1401c8198`
- `0x1401c82a0`
- `0x1401dd0e0`
- `0x140238ba0`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401dd308`
- `ntoskrnl!ProbeForRead` at `0x1401dd511`
- `ntoskrnl!ProbeForRead` at `0x1401dd308`
- `ntoskrnl!ProbeForRead` at `0x1401dd511`
- `ntoskrnl!KeBugCheckEx` at `0x1401dd3a2`
- `ntoskrnl!KeBugCheckEx` at `0x1401dd3a2`
- `ntoskrnl!ExRaiseStatus` at `0x1401dd4a8`
- `ntoskrnl!ExRaiseStatus` at `0x1401dd4a8`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401dd145`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401dd145`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dd2e4`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dd4ef`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dd2e4`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dd4ef`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401dd6df`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401dd70b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401dd6df`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401dd70b`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dd1a8`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dd534`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dd1a8`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dd534`
- `WIN32K!W32GetUserSessionState` at `0x1401dd158`
- `WIN32K!W32GetUserSessionState` at `0x1401dd158`

## pseudocode

```c
__int64 __fastcall NtUserSetDisplayConfig(unsigned int a1, __int64 *a2, unsigned int a3, struct _GUID *a4, __int64 a5)
{
  __int64 v6; // r15
  __int64 *v7; // r12
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 UserSessionState; // rbx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // ebx
  unsigned int v16; // esi
  struct tagTHREADINFO *v17; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int v19; // r8d
  UIPrivilegeIsolation *v20; // rcx
  char HasMinimumIntegrityLevel; // al
  char v22; // si
  __int64 *v23; // rdx
  unsigned __int64 v24; // rcx
  int v25; // eax
  unsigned int v26; // r15d
  unsigned int v27; // r14d
  __int64 CurrentProcessWow64Process; // rax
  unsigned int v29; // esi
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v31; // rax
  __int64 *v32; // r15
  unsigned int i; // r12d
  __int64 v34; // rax
  unsigned int v35; // eax
  __int64 v36; // rcx
  __int64 (*v37)(void); // rax
  int v38; // eax
  void (*v39)(void); // rax
  __int64 *v41; // [rsp+70h] [rbp-C8h]
  unsigned int v42; // [rsp+7Ch] [rbp-BCh]
  ULONG TimeIncrement; // [rsp+A0h] [rbp-98h]
  _DWORD v44[2]; // [rsp+A8h] [rbp-90h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-88h]
  __int64 *v46; // [rsp+B8h] [rbp-80h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+C0h] [rbp-78h] BYREF
  __int64 (__fastcall *v48)(PVOID); // [rsp+D0h] [rbp-68h]
  struct _GUID v49[2]; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v50; // [rsp+F8h] [rbp-40h]

  v6 = a1;
  v7 = 0;
  v41 = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  v42 = 0;
  memset(v49, 0, 28);
  v50 = MEMORY[0xFFFFF78000000320];
  TimeIncrement = KeQueryTimeIncrement();
  UserSessionState = W32GetUserSessionState(v9, v8, v10);
  v12 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          UserSessionState,
          0,
          0,
          _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(UserSessionState + 16) = v12;
  if ( v12 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  if ( !*(_DWORD *)(W32GetUserGdiSessionState(v14, v13) + 32) )
  {
    v15 = -1073741823;
    v16 = 0x80000000;
LABEL_65:
    v26 = a3;
    goto LABEL_66;
  }
  v17 = PtiCurrent();
  IsEnabledDeviceUsageNoInline = Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline();
  v20 = (UIPrivilegeIsolation *)(*((_QWORD *)v17 + 57) + 864LL);
  if ( IsEnabledDeviceUsageNoInline )
  {
    HasMinimumIntegrityLevel = UIPrivilegeIsolation::HasMinimumIntegrityLevel(
                                 v20,
                                 (const struct tagUIPI_INFO *)0x2000,
                                 v19);
  }
  else
  {
    v44[0] = 0x2000;
    v44[1] = -1;
    LODWORD(v45) = 0;
    HasMinimumIntegrityLevel = UIPrivilegeIsolation::CheckAccessEx(v20, v44, 0);
  }
  v22 = HasMinimumIntegrityLevel;
  if ( (unsigned int)Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( tagPROCESSINFO::HasUILimit(*((tagPROCESSINFO **)v17 + 57), 0x10u) || !v22 )
    {
      v16 = -2147483647;
      goto LABEL_64;
    }
  }
  else
  {
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v17 + 130, 0, 0) & 0x20000000) != 0 )
    {
      v24 = *(_QWORD *)(*((_QWORD *)v17 + 57) + 752LL);
      v25 = *(_DWORD *)(v24 + 32) & 0x10;
    }
    else
    {
      v25 = 0;
    }
    if ( v25 || !v22 )
    {
      v15 = -1073741790;
      v16 = -2147483647;
      v26 = a3;
      goto LABEL_61;
    }
  }
  v15 = -1073741811;
  if ( (unsigned int)v6 > 0x400 )
  {
    v16 = -2147483646;
    goto LABEL_65;
  }
  v46 = 0;
  v27 = 0;
  if ( (_DWORD)v6 )
  {
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
    ProbeForRead(a2, 216 * v6, CurrentProcessWow64Process != 0 ? 1 : 4);
    v29 = 0;
    v24 = 0;
    v23 = a2;
    while ( (unsigned int)v24 < (unsigned int)v6 )
    {
      if ( *v23 < 0 )
        ++v29;
      v24 = (unsigned int)(v24 + 1);
      v23 += 27;
    }
    if ( v29 )
    {
      v7 = (__int64 *)Win32AllocPoolWithQuotaZInitImpl(v24, 216LL * v29, 0x63447355u);
      v41 = v7;
      if ( !v7 )
        ExRaiseStatus(-1073741801);
      if ( v48 != (__int64 (__fastcall *)(PVOID))-1LL )
      {
        BugCheckParameter4 = PtiCurrent();
        KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v7, (ULONG_PTR)BugCheckParameter4);
      }
      v31 = PtiCurrent();
      BugCheckParameter2[0] = *((_QWORD *)v31 + 47);
      v24 = (unsigned __int64)BugCheckParameter2;
      *((_QWORD *)v31 + 47) = BugCheckParameter2;
      BugCheckParameter2[1] = (ULONG_PTR)v7;
      v48 = GreDeleteFastMutex;
    }
    v32 = v7;
    v46 = v7;
    for ( i = 0; i < a1; ++i )
    {
      if ( *a2 < 0 )
      {
        if ( v27 >= v29 )
        {
          v16 = -2147483645;
          v7 = v41;
          v26 = a3;
          goto LABEL_61;
        }
        RtlCopyVolatileMemory(v32, a2, 0xD8u);
        if ( *v32 >= 0 )
        {
          v15 = -1073741790;
          v16 = -2147483644;
          v7 = v41;
          v26 = a3;
          goto LABEL_61;
        }
        ++v27;
        v32 += 27;
        v46 = v32;
      }
      a2 += 27;
    }
    if ( v27 != v29 )
    {
      v16 = -2147483645;
      v7 = v41;
      v26 = a3;
      goto LABEL_61;
    }
    v7 = v41;
  }
  v42 = v27;
  if ( a4 )
  {
    v34 = PsGetCurrentProcessWow64Process();
    ProbeForRead(a4, 0x1Cu, v34 != 0 ? 1 : 4);
    v49[0] = *a4;
    *(_OWORD *)&v49[0].Data4[4] = *(_OWORD *)&a4->Data4[4];
  }
  if ( *(_DWORD *)(W32GetUserGdiSessionState(v24, v23) + 36) )
  {
    v15 = -1073741823;
    v16 = -2147483643;
    goto LABEL_65;
  }
  if ( !(unsigned int)UserIsWddmConnectedSession() )
  {
    v16 = -2147483642;
LABEL_64:
    v15 = -1073741790;
    goto LABEL_65;
  }
  if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v49) && !(unsigned int)DrvIsDisplayStateCurrent(1, v49) )
  {
    v15 = -1071774921;
    v16 = -2147483641;
    goto LABEL_65;
  }
  LOBYTE(v44[0]) = 0;
  CDisplayScenarioContextScope::ContextScopeConstructor(
    (CDisplayScenarioContextScope *)v44,
    (const struct _GUID *)&v49[0].Data4[4],
    0x1Du,
    0);
  v16 = 18;
  v26 = a3;
  v35 = xxxUserSetDisplayConfig(v27, v7, a3, 0, 0, 1, a5, 0, 0, v45, 0);
  v15 = v35;
  if ( v35 == -2147483643 )
  {
    v15 = -1073741789;
  }
  else if ( v35 != -1073741789 && (a3 & 0x10000) == 0 )
  {
    if ( v35 == -1071774970 )
      v15 = -2147023286;
    else
      v15 = QdcSdcTranslateStatusDefault(v35);
  }
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v44);
LABEL_61:
  if ( v16 != 18 )
LABEL_66:
    LogDiagSDC(v42, (_DWORD)v7, v26, v15, 0, v16, v50 * TimeIncrement, 0, 0);
  if ( v15 < 0 )
  {
    if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v49) && !(unsigned int)DrvIsDisplayStateCurrent(0, v49) )
      v15 = -1071774921;
  }
  else
  {
    v36 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v24) + 48);
    v37 = *(__int64 (**)(void))(v36 + 3528);
    if ( v37 )
      v38 = v37();
    else
      v38 = -1073741637;
    if ( v38 >= 0 )
    {
      v39 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v36) + 48) + 3536LL);
      if ( v39 )
        v39();
    }
  }
  if ( v7 )
    Win32RawLockedItemBase<DISPLAYCONFIG_PATH_INFO_INTERNAL,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  UserSessionSwitchLeaveCritWithNonPaged();
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1401dd0e0  mov     rax, rsp
0x1401dd0e3  mov     [rax+20h], r9
0x1401dd0e7  mov     [rax+18h], r8d
0x1401dd0eb  mov     [rax+8], ecx
0x1401dd0ee  push    rbx
0x1401dd0ef  push    rsi
0x1401dd0f0  push    rdi
0x1401dd0f1  push    r12
0x1401dd0f3  push    r13
0x1401dd0f5  push    r14
0x1401dd0f7  push    r15
0x1401dd0f9  sub     rsp, 100h
0x1401dd100  mov     r13, rdx
0x1401dd103  mov     r15d, ecx
0x1401dd106  xor     edi, edi
0x1401dd108  mov     r12d, edi
0x1401dd10b  mov     [rsp+138h+var_C8], rdi
0x1401dd110  lea     rcx, [rax-78h]
0x1401dd114  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dd119  mov     [rsp+138h+var_BC], edi
0x1401dd11d  xorps   xmm1, xmm1
0x1401dd120  movups  xmmword ptr [rsp+138h+var_60.Data1], xmm1
0x1401dd128  movups  xmmword ptr [rsp+138h+var_60.Data4+4], xmm1
0x1401dd130  mov     rax, 0FFFFF78000000320h
0x1401dd13a  mov     rax, [rax]
0x1401dd13d  mov     [rsp+138h+var_40], rax
0x1401dd145  call    cs:__imp_KeQueryTimeIncrement
0x1401dd14c  nop     dword ptr [rax+rax+00h]
0x1401dd151  mov     [rsp+138h+var_98], eax
0x1401dd158  call    cs:__imp_W32GetUserSessionState
0x1401dd15f  nop     dword ptr [rax+rax+00h]
0x1401dd164  mov     rbx, rax
0x1401dd167  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401dd16e  xor     r8d, r8d
0x1401dd171  xor     edx, edx
0x1401dd173  mov     rcx, rax
0x1401dd176  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401dd17b  mov     [rbx+10h], rax
0x1401dd17f  test    rax, rax
0x1401dd182  jz      short loc_1401DD1A8
0x1401dd184  lea     rcx, [rbx+4C40h]
0x1401dd18b  call    DestroySharedUserCritDeferredUnlockList
0x1401dd190  lea     rcx, [rbx+4C78h]
0x1401dd197  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dd19c  lea     rcx, [rbx+4C68h]
0x1401dd1a3  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dd1a8  call    cs:__imp_W32GetUserGdiSessionState
0x1401dd1af  nop     dword ptr [rax+rax+00h]
0x1401dd1b4  cmp     [rax+20h], edi
0x1401dd1b7  jnz     short loc_1401DD1C8
0x1401dd1b9  mov     ebx, 0C0000001h
0x1401dd1be  mov     esi, 80000000h
0x1401dd1c3  jmp     loc_1401DD694
0x1401dd1c8  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dd1cd  mov     rbx, rax
0x1401dd1d0  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x1401dd1d5  mov     rcx, [rbx+1C8h]
0x1401dd1dc  add     rcx, 360h; this
0x1401dd1e3  test    eax, eax
0x1401dd1e5  jz      short loc_1401DD1F3
0x1401dd1e7  mov     edx, 2000h; struct tagUIPI_INFO *
0x1401dd1ec  call    ?HasMinimumIntegrityLevel@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@K@Z; UIPrivilegeIsolation::HasMinimumIntegrityLevel(tagUIPI_INFO const &,ulong)
0x1401dd1f1  jmp     short loc_1401DD222
0x1401dd1f3  mov     [rsp+138h+var_90], 2000h
0x1401dd1fe  mov     [rsp+138h+var_8C], 0FFFFFFFFh
0x1401dd209  xor     eax, eax
0x1401dd20b  mov     dword ptr [rsp+138h+var_88], eax
0x1401dd212  xor     r8d, r8d
0x1401dd215  lea     rdx, [rsp+138h+var_90]
0x1401dd21d  call    ?CheckAccessEx@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::CheckAccessEx(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x1401dd222  mov     sil, al
0x1401dd225  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x1401dd22a  test    eax, eax
0x1401dd22c  jnz     short loc_1401DD274
0x1401dd22e  lock cmpxchg [rbx+208h], edi
0x1401dd236  bt      eax, 1Dh
0x1401dd23a  jnb     short loc_1401DD252
0x1401dd23c  mov     rax, [rbx+1C8h]
0x1401dd243  mov     rcx, [rax+2F0h]
0x1401dd24a  mov     eax, [rcx+20h]
0x1401dd24d  and     eax, 10h
0x1401dd250  jmp     short loc_1401DD254
0x1401dd252  mov     eax, edi
0x1401dd254  test    eax, eax
0x1401dd256  jnz     short loc_1401DD25D
0x1401dd258  test    sil, sil
0x1401dd25b  jnz     short loc_1401DD296
0x1401dd25d  mov     ebx, 0C0000022h
0x1401dd262  mov     esi, 80000001h
0x1401dd267  mov     r15d, [rsp+138h+arg_10]
0x1401dd26f  jmp     loc_1401DD67D
0x1401dd274  mov     edx, 10h; unsigned int
0x1401dd279  mov     rcx, [rbx+1C8h]; this
0x1401dd280  call    ?HasUILimit@tagPROCESSINFO@@QEBA_NK@Z; tagPROCESSINFO::HasUILimit(ulong)
0x1401dd285  test    al, al
0x1401dd287  jnz     loc_1401DD68A
0x1401dd28d  test    sil, sil
0x1401dd290  jz      loc_1401DD68A
0x1401dd296  mov     [rsp+138h+var_D4], edi
0x1401dd29a  mov     ebx, 0C000000Dh
0x1401dd29f  mov     [rsp+138h+var_9C], ebx
0x1401dd2a6  cmp     r15d, 400h
0x1401dd2ad  jbe     short loc_1401DD2B9
0x1401dd2af  mov     esi, 80000002h
0x1401dd2b4  jmp     loc_1401DD694
0x1401dd2b9  mov     [rsp+138h+var_B8], rdi
0x1401dd2c1  mov     [rsp+138h+var_80], rdi
0x1401dd2c9  mov     [rsp+138h+var_C0], edi
0x1401dd2cd  mov     r14d, edi
0x1401dd2d0  mov     [rsp+138h+var_B0], edi
0x1401dd2d7  mov     [rsp+138h+var_D8], edi
0x1401dd2db  test    r15d, r15d
0x1401dd2de  jz      loc_1401DD4DD
0x1401dd2e4  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dd2eb  nop     dword ptr [rax+rax+00h]
0x1401dd2f0  neg     rax
0x1401dd2f3  sbb     r8d, r8d
0x1401dd2f6  and     r8d, 0FFFFFFFDh
0x1401dd2fa  add     r8d, 4; Alignment
0x1401dd2fe  imul    rdx, r15, 0D8h; Length
0x1401dd305  mov     rcx, r13; Address
0x1401dd308  call    cs:__imp_ProbeForRead
0x1401dd30f  nop     dword ptr [rax+rax+00h]
0x1401dd314  mov     esi, edi
0x1401dd316  mov     [rsp+138h+var_C0], edi
0x1401dd31a  mov     ecx, edi; unsigned __int64
0x1401dd31c  mov     rdx, r13
0x1401dd31f  mov     r8d, 0D8h
0x1401dd325  mov     [rsp+138h+var_B8], rdx
0x1401dd32d  mov     [rsp+138h+var_D8], ecx
0x1401dd331  cmp     ecx, r15d
0x1401dd334  jnb     short loc_1401DD34B
0x1401dd336  mov     rax, [rdx]
0x1401dd339  test    rax, rax
0x1401dd33c  jns     short loc_1401DD344
0x1401dd33e  inc     esi
0x1401dd340  mov     [rsp+138h+var_C0], esi
0x1401dd344  inc     ecx
0x1401dd346  add     rdx, r8
0x1401dd349  jmp     short loc_1401DD325
0x1401dd34b  test    esi, esi
0x1401dd34d  jz      loc_1401DD3EE
0x1401dd353  mov     eax, esi
0x1401dd355  imul    rdx, rax, 0D8h; unsigned __int64
0x1401dd35c  mov     r8d, 63447355h; unsigned int
0x1401dd362  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401dd367  mov     r12, rax
0x1401dd36a  mov     [rsp+138h+var_C8], rax
0x1401dd36f  test    rax, rax
0x1401dd372  jz      loc_1401DD4A3
0x1401dd378  cmp     [rsp+138h+var_68], 0FFFFFFFFFFFFFFFFh
0x1401dd381  jz      short loc_1401DD3AE
0x1401dd383  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dd388  mov     [rsp+138h+BugCheckParameter4], rax; BugCheckParameter4
0x1401dd38d  mov     r9, r12; BugCheckParameter3
0x1401dd390  lea     r8, [rsp+138h+BugCheckParameter2]; BugCheckParameter2
0x1401dd398  mov     edx, 12h; BugCheckParameter1
0x1401dd39d  mov     ecx, 164h; BugCheckCode
0x1401dd3a2  call    cs:__imp_KeBugCheckEx
0x1401dd3ae  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dd3b3  mov     rcx, [rax+178h]
0x1401dd3ba  mov     [rsp+138h+BugCheckParameter2], rcx
0x1401dd3c2  lea     rcx, [rsp+138h+BugCheckParameter2]
0x1401dd3ca  mov     [rax+178h], rcx
0x1401dd3d1  mov     [rsp+138h+var_70], r12
0x1401dd3d9  lea     rax, GreDeleteFastMutex
0x1401dd3e0  mov     [rsp+138h+var_68], rax
0x1401dd3e8  mov     r8d, 0D8h; Size
0x1401dd3ee  mov     r15, r12
0x1401dd3f1  mov     [rsp+138h+var_80], r12
0x1401dd3f9  mov     r12d, edi
0x1401dd3fc  mov     [rsp+138h+var_D8], edi
0x1401dd400  mov     [rsp+138h+var_B8], r13
0x1401dd408  cmp     r12d, [rsp+138h+arg_0]
0x1401dd410  jnb     loc_1401DD4B4
0x1401dd416  mov     rax, [r13+0]
0x1401dd41a  test    rax, rax
0x1401dd41d  jns     short loc_1401DD493
0x1401dd41f  cmp     r14d, esi
0x1401dd422  jb      short loc_1401DD443
0x1401dd424  mov     [rsp+138h+var_D0], ebx
0x1401dd428  mov     esi, 80000003h
0x1401dd42d  mov     [rsp+138h+var_D4], esi
0x1401dd431  mov     r12, [rsp+138h+var_C8]
0x1401dd436  mov     r15d, [rsp+138h+arg_10]
0x1401dd43e  jmp     loc_1401DD67D
0x1401dd443  mov     rdx, r13; Src
0x1401dd446  mov     rcx, r15; void *
0x1401dd449  call    RtlCopyVolatileMemory
0x1401dd44e  cmp     [r15], rdi
0x1401dd451  jl      short loc_1401DD477
0x1401dd453  mov     ebx, 0C0000022h
0x1401dd458  mov     [rsp+138h+var_D0], ebx
0x1401dd45c  mov     esi, 80000004h
0x1401dd461  mov     [rsp+138h+var_D4], esi
0x1401dd465  mov     r12, [rsp+138h+var_C8]
0x1401dd46a  mov     r15d, [rsp+138h+arg_10]
0x1401dd472  jmp     loc_1401DD67D
0x1401dd477  inc     r14d
0x1401dd47a  mov     [rsp+138h+var_B0], r14d
0x1401dd482  mov     r8d, 0D8h
0x1401dd488  add     r15, r8
0x1401dd48b  mov     [rsp+138h+var_80], r15
0x1401dd493  inc     r12d
0x1401dd496  mov     [rsp+138h+var_D8], r12d
0x1401dd49b  add     r13, r8
0x1401dd49e  jmp     loc_1401DD400
0x1401dd4a3  mov     ecx, 0C0000017h; Status
0x1401dd4a8  call    cs:__imp_ExRaiseStatus
0x1401dd4b4  cmp     r14d, esi
0x1401dd4b7  jz      short loc_1401DD4D8
0x1401dd4b9  mov     [rsp+138h+var_D0], ebx
0x1401dd4bd  mov     esi, 80000003h
0x1401dd4c2  mov     [rsp+138h+var_D4], esi
0x1401dd4c6  mov     r12, [rsp+138h+var_C8]
0x1401dd4cb  mov     r15d, [rsp+138h+arg_10]
0x1401dd4d3  jmp     loc_1401DD67D
0x1401dd4d8  mov     r12, [rsp+138h+var_C8]
0x1401dd4dd  mov     [rsp+138h+var_BC], r14d
0x1401dd4e2  mov     rbx, [rsp+138h+Address]
0x1401dd4ea  test    rbx, rbx
0x1401dd4ed  jz      short loc_1401DD534
0x1401dd4ef  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dd4f6  nop     dword ptr [rax+rax+00h]
0x1401dd4fb  neg     rax
0x1401dd4fe  sbb     r8d, r8d
0x1401dd501  and     r8d, 0FFFFFFFDh
0x1401dd505  add     r8d, 4; Alignment
0x1401dd509  mov     edx, 1Ch; Length
0x1401dd50e  mov     rcx, rbx; Address
0x1401dd511  call    cs:__imp_ProbeForRead
0x1401dd518  nop     dword ptr [rax+rax+00h]
0x1401dd51d  movups  xmm0, xmmword ptr [rbx]
0x1401dd520  movups  xmmword ptr [rsp+138h+var_60.Data1], xmm0
0x1401dd528  movups  xmm1, xmmword ptr [rbx+0Ch]
0x1401dd52c  movups  xmmword ptr [rsp+138h+var_60.Data4+4], xmm1
0x1401dd534  call    cs:__imp_W32GetUserGdiSessionState
0x1401dd53b  nop     dword ptr [rax+rax+00h]
0x1401dd540  cmp     [rax+24h], edi
0x1401dd543  jz      short loc_1401DD554
0x1401dd545  mov     ebx, 0C0000001h
0x1401dd54a  mov     esi, 80000005h
0x1401dd54f  jmp     loc_1401DD694
0x1401dd554  call    UserIsWddmConnectedSession
0x1401dd559  test    eax, eax
0x1401dd55b  jnz     short loc_1401DD567
0x1401dd55d  mov     esi, 80000006h
0x1401dd562  jmp     loc_1401DD68F
0x1401dd567  test    rbx, rbx
0x1401dd56a  jz      short loc_1401DD5A6
0x1401dd56c  lea     rcx, [rsp+138h+var_60]
0x1401dd574  call    DrvNeedDisplayStateCheck
0x1401dd579  test    eax, eax
0x1401dd57b  jz      short loc_1401DD5A6
0x1401dd57d  lea     rdx, [rsp+138h+var_60]
0x1401dd585  mov     ecx, 1
0x1401dd58a  call    DrvIsDisplayStateCurrent
0x1401dd58f  test    eax, eax
0x1401dd591  jnz     short loc_1401DD5A6
0x1401dd593  mov     r14d, 0C01E0337h
0x1401dd599  mov     ebx, r14d
0x1401dd59c  mov     esi, 80000007h
0x1401dd5a1  jmp     loc_1401DD69A
0x1401dd5a6  mov     byte ptr [rsp+138h+var_90], dil
0x1401dd5ae  xor     r9d, r9d; unsigned int
0x1401dd5b1  lea     r8d, [r9+1Dh]; unsigned int
0x1401dd5b5  lea     rdx, [rsp+138h+var_60.Data4+4]; struct _GUID *
0x1401dd5bd  lea     rcx, [rsp+138h+var_90]; this
0x1401dd5c5  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x1401dd5ca  mov     esi, 12h
0x1401dd5cf  mov     [rsp+138h+var_E8], rdi
0x1401dd5d4  mov     rax, [rsp+138h+var_88]
0x1401dd5dc  mov     [rsp+138h+var_F0], rax
0x1401dd5e1  mov     [rsp+138h+var_F8], rdi
0x1401dd5e6  mov     [rsp+138h+var_100], rdi
0x1401dd5eb  mov     rax, [rsp+138h+arg_20]
0x1401dd5f3  mov     [rsp+138h+var_108], rax
0x1401dd5f8  mov     byte ptr [rsp+138h+var_110], 1
0x1401dd5fd  mov     [rsp+138h+BugCheckParameter4], rdi
0x1401dd602  xor     r9d, r9d
0x1401dd605  mov     r15d, [rsp+138h+arg_10]
0x1401dd60d  mov     r8d, r15d
0x1401dd610  mov     rdx, r12
0x1401dd613  mov     ecx, r14d
0x1401dd616  call    xxxUserSetDisplayConfig
0x1401dd61b  mov     ebx, eax
0x1401dd61d  cmp     eax, 80000005h
0x1401dd622  jz      short loc_1401DD64B
0x1401dd624  cmp     eax, 0C0000023h
0x1401dd629  jz      short loc_1401DD650
0x1401dd62b  bt      r15d, 10h
0x1401dd630  jb      short loc_1401DD650
0x1401dd632  cmp     eax, 0C01E0306h
0x1401dd637  jz      short loc_1401DD644
0x1401dd639  mov     ecx, eax
0x1401dd63b  call    _QdcSdcTranslateStatusDefault
0x1401dd640  mov     ebx, eax
0x1401dd642  jmp     short loc_1401DD650
0x1401dd644  mov     ebx, 8007064Ah
0x1401dd649  jmp     short loc_1401DD650
  ... truncated ...
```
