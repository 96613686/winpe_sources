# NtUserSetDisplayConfig

- ea: `0x1401dd6c0`
- end: `0x1401ddd7a`
- name: `NtUserSetDisplayConfig`
- size: `1722`
- prototype: `__int64 __fastcall(unsigned int, __int64 *, unsigned int, struct _GUID *, __int64)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140022c58`
- `0x140022ca0`
- `0x140029710`
- `0x14004dd98`
- `0x14004dfb0`
- `0x14004f4c0`
- `0x14004f550`
- `0x14006e970`
- `0x14006f3a4`
- `0x1400701d4`
- `0x140070518`
- `0x14007df80`
- `0x1400f2ff8`
- `0x140114808`
- `0x14011a7d4`
- `0x14014065c`
- `0x14017847c`
- `0x14018ac84`
- `0x140197a80`
- `0x1401b0394`
- `0x1401c7d70`
- `0x1401c8bd8`
- `0x1401c8cd0`
- `0x1401dd6c0`
- `0x140238970`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401dd8e8`
- `ntoskrnl!ProbeForRead` at `0x1401ddaf1`
- `ntoskrnl!ProbeForRead` at `0x1401dd8e8`
- `ntoskrnl!ProbeForRead` at `0x1401ddaf1`
- `ntoskrnl!KeBugCheckEx` at `0x1401dd982`
- `ntoskrnl!KeBugCheckEx` at `0x1401dd982`
- `ntoskrnl!ExRaiseStatus` at `0x1401dda88`
- `ntoskrnl!ExRaiseStatus` at `0x1401dda88`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401dd725`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401dd725`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dd8c4`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401ddacf`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dd8c4`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401ddacf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ddcbf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ddceb`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ddcbf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ddceb`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dd788`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401ddb14`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dd788`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401ddb14`
- `WIN32K!W32GetUserSessionState` at `0x1401dd738`
- `WIN32K!W32GetUserSessionState` at `0x1401dd738`

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
  int v13; // ebx
  unsigned int v14; // esi
  struct tagTHREADINFO *v15; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int v17; // r8d
  UIPrivilegeIsolation *v18; // rcx
  char HasMinimumIntegrityLevel; // al
  char v20; // si
  unsigned __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // r15d
  unsigned int v24; // r14d
  __int64 CurrentProcessWow64Process; // rax
  unsigned int v26; // esi
  __int64 *v27; // rdx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v29; // rax
  __int64 *v30; // r15
  unsigned int i; // r12d
  __int64 v32; // rax
  unsigned int v33; // eax
  __int64 (*v34)(void); // rax
  int v35; // eax
  void (*v36)(void); // rax
  __int64 *v38; // [rsp+70h] [rbp-C8h]
  unsigned int v39; // [rsp+7Ch] [rbp-BCh]
  ULONG TimeIncrement; // [rsp+A0h] [rbp-98h]
  _DWORD v41[2]; // [rsp+A8h] [rbp-90h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-88h]
  __int64 *v43; // [rsp+B8h] [rbp-80h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+C0h] [rbp-78h] BYREF
  __int64 (__fastcall *v45)(PVOID); // [rsp+D0h] [rbp-68h]
  struct _GUID v46[2]; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v47; // [rsp+F8h] [rbp-40h]

  v6 = a1;
  v7 = 0;
  v38 = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  v39 = 0;
  memset(v46, 0, 28);
  v47 = MEMORY[0xFFFFF78000000320];
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
  if ( !*(_DWORD *)(W32GetUserGdiSessionState() + 32) )
  {
    v13 = -1073741823;
    v14 = 0x80000000;
LABEL_65:
    v23 = a3;
    goto LABEL_66;
  }
  v15 = PtiCurrent();
  IsEnabledDeviceUsageNoInline = Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline();
  v18 = (UIPrivilegeIsolation *)(*((_QWORD *)v15 + 57) + 864LL);
  if ( IsEnabledDeviceUsageNoInline )
  {
    HasMinimumIntegrityLevel = UIPrivilegeIsolation::HasMinimumIntegrityLevel(
                                 v18,
                                 (const struct tagUIPI_INFO *)0x2000,
                                 v17);
  }
  else
  {
    v41[0] = 0x2000;
    v41[1] = -1;
    LODWORD(v42) = 0;
    HasMinimumIntegrityLevel = UIPrivilegeIsolation::CheckAccessEx(v18, v41, 0);
  }
  v20 = HasMinimumIntegrityLevel;
  if ( (unsigned int)Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( tagPROCESSINFO::HasUILimit(*((tagPROCESSINFO **)v15 + 57), 0x10u) || !v20 )
    {
      v14 = -2147483647;
      goto LABEL_64;
    }
  }
  else
  {
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v15 + 130, 0, 0) & 0x20000000) != 0 )
    {
      v21 = *(_QWORD *)(*((_QWORD *)v15 + 57) + 752LL);
      v22 = *(_DWORD *)(v21 + 32) & 0x10;
    }
    else
    {
      v22 = 0;
    }
    if ( v22 || !v20 )
    {
      v13 = -1073741790;
      v14 = -2147483647;
      v23 = a3;
      goto LABEL_61;
    }
  }
  v13 = -1073741811;
  if ( (unsigned int)v6 > 0x400 )
  {
    v14 = -2147483646;
    goto LABEL_65;
  }
  v43 = 0;
  v24 = 0;
  if ( (_DWORD)v6 )
  {
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
    ProbeForRead(a2, 216 * v6, CurrentProcessWow64Process != 0 ? 1 : 4);
    v26 = 0;
    v21 = 0;
    v27 = a2;
    while ( (unsigned int)v21 < (unsigned int)v6 )
    {
      if ( *v27 < 0 )
        ++v26;
      v21 = (unsigned int)(v21 + 1);
      v27 += 27;
    }
    if ( v26 )
    {
      v7 = (__int64 *)Win32AllocPoolWithQuotaZInitImpl(v21, 216LL * v26, 0x63447355u);
      v38 = v7;
      if ( !v7 )
        ExRaiseStatus(-1073741801);
      if ( v45 != (__int64 (__fastcall *)(PVOID))-1LL )
      {
        BugCheckParameter4 = PtiCurrent();
        KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v7, (ULONG_PTR)BugCheckParameter4);
      }
      v29 = PtiCurrent();
      BugCheckParameter2[0] = *((_QWORD *)v29 + 47);
      v21 = (unsigned __int64)BugCheckParameter2;
      *((_QWORD *)v29 + 47) = BugCheckParameter2;
      BugCheckParameter2[1] = (ULONG_PTR)v7;
      v45 = GreDeleteFastMutex;
    }
    v30 = v7;
    v43 = v7;
    for ( i = 0; i < a1; ++i )
    {
      if ( *a2 < 0 )
      {
        if ( v24 >= v26 )
        {
          v14 = -2147483645;
          v7 = v38;
          v23 = a3;
          goto LABEL_61;
        }
        RtlCopyVolatileMemory(v30, a2, 0xD8u);
        if ( *v30 >= 0 )
        {
          v13 = -1073741790;
          v14 = -2147483644;
          v7 = v38;
          v23 = a3;
          goto LABEL_61;
        }
        ++v24;
        v30 += 27;
        v43 = v30;
      }
      a2 += 27;
    }
    if ( v24 != v26 )
    {
      v14 = -2147483645;
      v7 = v38;
      v23 = a3;
      goto LABEL_61;
    }
    v7 = v38;
  }
  v39 = v24;
  if ( a4 )
  {
    v32 = PsGetCurrentProcessWow64Process();
    ProbeForRead(a4, 0x1Cu, v32 != 0 ? 1 : 4);
    v46[0] = *a4;
    *(_OWORD *)&v46[0].Data4[4] = *(_OWORD *)&a4->Data4[4];
  }
  if ( *(_DWORD *)(W32GetUserGdiSessionState() + 36) )
  {
    v13 = -1073741823;
    v14 = -2147483643;
    goto LABEL_65;
  }
  if ( !(unsigned int)UserIsWddmConnectedSession() )
  {
    v14 = -2147483642;
LABEL_64:
    v13 = -1073741790;
    goto LABEL_65;
  }
  if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v46) && !(unsigned int)DrvIsDisplayStateCurrent(1, v46) )
  {
    v13 = -1071774921;
    v14 = -2147483641;
    goto LABEL_65;
  }
  LOBYTE(v41[0]) = 0;
  CDisplayScenarioContextScope::ContextScopeConstructor(
    (CDisplayScenarioContextScope *)v41,
    (const struct _GUID *)&v46[0].Data4[4],
    0x1Du,
    0);
  v14 = 18;
  v23 = a3;
  v33 = xxxUserSetDisplayConfig(v24, v7, a3, 0, 0, 1, a5, 0, 0, v42, 0);
  v13 = v33;
  if ( v33 == -2147483643 )
  {
    v13 = -1073741789;
  }
  else if ( v33 != -1073741789 && (a3 & 0x10000) == 0 )
  {
    if ( v33 == -1071774970 )
      v13 = -2147023286;
    else
      v13 = QdcSdcTranslateStatusDefault(v33);
  }
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v41);
LABEL_61:
  if ( v14 != 18 )
LABEL_66:
    LogDiagSDC(v39, (_DWORD)v7, v23, v13, 0, v14, v47 * TimeIncrement, 0, 0);
  if ( v13 < 0 )
  {
    if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v46) && !(unsigned int)DrvIsDisplayStateCurrent(0, v46) )
      v13 = -1071774921;
  }
  else
  {
    v21 = *(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48);
    v34 = *(__int64 (**)(void))(v21 + 3528);
    if ( v34 )
      v35 = v34();
    else
      v35 = -1073741637;
    if ( v35 >= 0 )
    {
      v21 = *(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48);
      v36 = *(void (**)(void))(v21 + 3536);
      if ( v36 )
        v36();
    }
  }
  if ( v7 )
    Win32RawLockedItemBase<DISPLAYCONFIG_PATH_INFO_INTERNAL,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  UserSessionSwitchLeaveCritWithNonPaged(v21);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1401dd6c0  mov     rax, rsp
0x1401dd6c3  mov     [rax+20h], r9
0x1401dd6c7  mov     [rax+18h], r8d
0x1401dd6cb  mov     [rax+8], ecx
0x1401dd6ce  push    rbx
0x1401dd6cf  push    rsi
0x1401dd6d0  push    rdi
0x1401dd6d1  push    r12
0x1401dd6d3  push    r13
0x1401dd6d5  push    r14
0x1401dd6d7  push    r15
0x1401dd6d9  sub     rsp, 100h
0x1401dd6e0  mov     r13, rdx
0x1401dd6e3  mov     r15d, ecx
0x1401dd6e6  xor     edi, edi
0x1401dd6e8  mov     r12d, edi
0x1401dd6eb  mov     [rsp+138h+var_C8], rdi
0x1401dd6f0  lea     rcx, [rax-78h]
0x1401dd6f4  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dd6f9  mov     [rsp+138h+var_BC], edi
0x1401dd6fd  xorps   xmm1, xmm1
0x1401dd700  movups  xmmword ptr [rsp+138h+var_60.Data1], xmm1
0x1401dd708  movups  xmmword ptr [rsp+138h+var_60.Data4+4], xmm1
0x1401dd710  mov     rax, 0FFFFF78000000320h
0x1401dd71a  mov     rax, [rax]
0x1401dd71d  mov     [rsp+138h+var_40], rax
0x1401dd725  call    cs:__imp_KeQueryTimeIncrement
0x1401dd72c  nop     dword ptr [rax+rax+00h]
0x1401dd731  mov     [rsp+138h+var_98], eax
0x1401dd738  call    cs:__imp_W32GetUserSessionState
0x1401dd73f  nop     dword ptr [rax+rax+00h]
0x1401dd744  mov     rbx, rax
0x1401dd747  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401dd74e  xor     r8d, r8d
0x1401dd751  xor     edx, edx
0x1401dd753  mov     rcx, rax
0x1401dd756  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401dd75b  mov     [rbx+10h], rax
0x1401dd75f  test    rax, rax
0x1401dd762  jz      short loc_1401DD788
0x1401dd764  lea     rcx, [rbx+4C40h]
0x1401dd76b  call    DestroySharedUserCritDeferredUnlockList
0x1401dd770  lea     rcx, [rbx+4C78h]
0x1401dd777  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dd77c  lea     rcx, [rbx+4C68h]
0x1401dd783  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dd788  call    cs:__imp_W32GetUserGdiSessionState
0x1401dd78f  nop     dword ptr [rax+rax+00h]
0x1401dd794  cmp     [rax+20h], edi
0x1401dd797  jnz     short loc_1401DD7A8
0x1401dd799  mov     ebx, 0C0000001h
0x1401dd79e  mov     esi, 80000000h
0x1401dd7a3  jmp     loc_1401DDC74
0x1401dd7a8  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dd7ad  mov     rbx, rax
0x1401dd7b0  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x1401dd7b5  mov     rcx, [rbx+1C8h]
0x1401dd7bc  add     rcx, 360h; this
0x1401dd7c3  test    eax, eax
0x1401dd7c5  jz      short loc_1401DD7D3
0x1401dd7c7  mov     edx, 2000h; struct tagUIPI_INFO *
0x1401dd7cc  call    ?HasMinimumIntegrityLevel@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@K@Z; UIPrivilegeIsolation::HasMinimumIntegrityLevel(tagUIPI_INFO const &,ulong)
0x1401dd7d1  jmp     short loc_1401DD802
0x1401dd7d3  mov     [rsp+138h+var_90], 2000h
0x1401dd7de  mov     [rsp+138h+var_8C], 0FFFFFFFFh
0x1401dd7e9  xor     eax, eax
0x1401dd7eb  mov     dword ptr [rsp+138h+var_88], eax
0x1401dd7f2  xor     r8d, r8d
0x1401dd7f5  lea     rdx, [rsp+138h+var_90]
0x1401dd7fd  call    ?CheckAccessEx@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::CheckAccessEx(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x1401dd802  mov     sil, al
0x1401dd805  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x1401dd80a  test    eax, eax
0x1401dd80c  jnz     short loc_1401DD854
0x1401dd80e  lock cmpxchg [rbx+208h], edi
0x1401dd816  bt      eax, 1Dh
0x1401dd81a  jnb     short loc_1401DD832
0x1401dd81c  mov     rax, [rbx+1C8h]
0x1401dd823  mov     rcx, [rax+2F0h]
0x1401dd82a  mov     eax, [rcx+20h]
0x1401dd82d  and     eax, 10h
0x1401dd830  jmp     short loc_1401DD834
0x1401dd832  mov     eax, edi
0x1401dd834  test    eax, eax
0x1401dd836  jnz     short loc_1401DD83D
0x1401dd838  test    sil, sil
0x1401dd83b  jnz     short loc_1401DD876
0x1401dd83d  mov     ebx, 0C0000022h
0x1401dd842  mov     esi, 80000001h
0x1401dd847  mov     r15d, [rsp+138h+arg_10]
0x1401dd84f  jmp     loc_1401DDC5D
0x1401dd854  mov     edx, 10h; unsigned int
0x1401dd859  mov     rcx, [rbx+1C8h]; this
0x1401dd860  call    ?HasUILimit@tagPROCESSINFO@@QEBA_NK@Z; tagPROCESSINFO::HasUILimit(ulong)
0x1401dd865  test    al, al
0x1401dd867  jnz     loc_1401DDC6A
0x1401dd86d  test    sil, sil
0x1401dd870  jz      loc_1401DDC6A
0x1401dd876  mov     [rsp+138h+var_D4], edi
0x1401dd87a  mov     ebx, 0C000000Dh
0x1401dd87f  mov     [rsp+138h+var_9C], ebx
0x1401dd886  cmp     r15d, 400h
0x1401dd88d  jbe     short loc_1401DD899
0x1401dd88f  mov     esi, 80000002h
0x1401dd894  jmp     loc_1401DDC74
0x1401dd899  mov     [rsp+138h+var_B8], rdi
0x1401dd8a1  mov     [rsp+138h+var_80], rdi
0x1401dd8a9  mov     [rsp+138h+var_C0], edi
0x1401dd8ad  mov     r14d, edi
0x1401dd8b0  mov     [rsp+138h+var_B0], edi
0x1401dd8b7  mov     [rsp+138h+var_D8], edi
0x1401dd8bb  test    r15d, r15d
0x1401dd8be  jz      loc_1401DDABD
0x1401dd8c4  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dd8cb  nop     dword ptr [rax+rax+00h]
0x1401dd8d0  neg     rax
0x1401dd8d3  sbb     r8d, r8d
0x1401dd8d6  and     r8d, 0FFFFFFFDh
0x1401dd8da  add     r8d, 4; Alignment
0x1401dd8de  imul    rdx, r15, 0D8h; Length
0x1401dd8e5  mov     rcx, r13; Address
0x1401dd8e8  call    cs:__imp_ProbeForRead
0x1401dd8ef  nop     dword ptr [rax+rax+00h]
0x1401dd8f4  mov     esi, edi
0x1401dd8f6  mov     [rsp+138h+var_C0], edi
0x1401dd8fa  mov     ecx, edi; unsigned __int64
0x1401dd8fc  mov     rdx, r13
0x1401dd8ff  mov     r8d, 0D8h
0x1401dd905  mov     [rsp+138h+var_B8], rdx
0x1401dd90d  mov     [rsp+138h+var_D8], ecx
0x1401dd911  cmp     ecx, r15d
0x1401dd914  jnb     short loc_1401DD92B
0x1401dd916  mov     rax, [rdx]
0x1401dd919  test    rax, rax
0x1401dd91c  jns     short loc_1401DD924
0x1401dd91e  inc     esi
0x1401dd920  mov     [rsp+138h+var_C0], esi
0x1401dd924  inc     ecx
0x1401dd926  add     rdx, r8
0x1401dd929  jmp     short loc_1401DD905
0x1401dd92b  test    esi, esi
0x1401dd92d  jz      loc_1401DD9CE
0x1401dd933  mov     eax, esi
0x1401dd935  imul    rdx, rax, 0D8h; unsigned __int64
0x1401dd93c  mov     r8d, 63447355h; unsigned int
0x1401dd942  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401dd947  mov     r12, rax
0x1401dd94a  mov     [rsp+138h+var_C8], rax
0x1401dd94f  test    rax, rax
0x1401dd952  jz      loc_1401DDA83
0x1401dd958  cmp     [rsp+138h+var_68], 0FFFFFFFFFFFFFFFFh
0x1401dd961  jz      short loc_1401DD98E
0x1401dd963  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dd968  mov     [rsp+138h+BugCheckParameter4], rax; BugCheckParameter4
0x1401dd96d  mov     r9, r12; BugCheckParameter3
0x1401dd970  lea     r8, [rsp+138h+BugCheckParameter2]; BugCheckParameter2
0x1401dd978  mov     edx, 12h; BugCheckParameter1
0x1401dd97d  mov     ecx, 164h; BugCheckCode
0x1401dd982  call    cs:__imp_KeBugCheckEx
0x1401dd98e  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dd993  mov     rcx, [rax+178h]
0x1401dd99a  mov     [rsp+138h+BugCheckParameter2], rcx
0x1401dd9a2  lea     rcx, [rsp+138h+BugCheckParameter2]
0x1401dd9aa  mov     [rax+178h], rcx
0x1401dd9b1  mov     [rsp+138h+var_70], r12
0x1401dd9b9  lea     rax, GreDeleteFastMutex
0x1401dd9c0  mov     [rsp+138h+var_68], rax
0x1401dd9c8  mov     r8d, 0D8h; Size
0x1401dd9ce  mov     r15, r12
0x1401dd9d1  mov     [rsp+138h+var_80], r12
0x1401dd9d9  mov     r12d, edi
0x1401dd9dc  mov     [rsp+138h+var_D8], edi
0x1401dd9e0  mov     [rsp+138h+var_B8], r13
0x1401dd9e8  cmp     r12d, [rsp+138h+arg_0]
0x1401dd9f0  jnb     loc_1401DDA94
0x1401dd9f6  mov     rax, [r13+0]
0x1401dd9fa  test    rax, rax
0x1401dd9fd  jns     short loc_1401DDA73
0x1401dd9ff  cmp     r14d, esi
0x1401dda02  jb      short loc_1401DDA23
0x1401dda04  mov     [rsp+138h+var_D0], ebx
0x1401dda08  mov     esi, 80000003h
0x1401dda0d  mov     [rsp+138h+var_D4], esi
0x1401dda11  mov     r12, [rsp+138h+var_C8]
0x1401dda16  mov     r15d, [rsp+138h+arg_10]
0x1401dda1e  jmp     loc_1401DDC5D
0x1401dda23  mov     rdx, r13; Src
0x1401dda26  mov     rcx, r15; void *
0x1401dda29  call    RtlCopyVolatileMemory
0x1401dda2e  cmp     [r15], rdi
0x1401dda31  jl      short loc_1401DDA57
0x1401dda33  mov     ebx, 0C0000022h
0x1401dda38  mov     [rsp+138h+var_D0], ebx
0x1401dda3c  mov     esi, 80000004h
0x1401dda41  mov     [rsp+138h+var_D4], esi
0x1401dda45  mov     r12, [rsp+138h+var_C8]
0x1401dda4a  mov     r15d, [rsp+138h+arg_10]
0x1401dda52  jmp     loc_1401DDC5D
0x1401dda57  inc     r14d
0x1401dda5a  mov     [rsp+138h+var_B0], r14d
0x1401dda62  mov     r8d, 0D8h
0x1401dda68  add     r15, r8
0x1401dda6b  mov     [rsp+138h+var_80], r15
0x1401dda73  inc     r12d
0x1401dda76  mov     [rsp+138h+var_D8], r12d
0x1401dda7b  add     r13, r8
0x1401dda7e  jmp     loc_1401DD9E0
0x1401dda83  mov     ecx, 0C0000017h; Status
0x1401dda88  call    cs:__imp_ExRaiseStatus
0x1401dda94  cmp     r14d, esi
0x1401dda97  jz      short loc_1401DDAB8
0x1401dda99  mov     [rsp+138h+var_D0], ebx
0x1401dda9d  mov     esi, 80000003h
0x1401ddaa2  mov     [rsp+138h+var_D4], esi
0x1401ddaa6  mov     r12, [rsp+138h+var_C8]
0x1401ddaab  mov     r15d, [rsp+138h+arg_10]
0x1401ddab3  jmp     loc_1401DDC5D
0x1401ddab8  mov     r12, [rsp+138h+var_C8]
0x1401ddabd  mov     [rsp+138h+var_BC], r14d
0x1401ddac2  mov     rbx, [rsp+138h+Address]
0x1401ddaca  test    rbx, rbx
0x1401ddacd  jz      short loc_1401DDB14
0x1401ddacf  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401ddad6  nop     dword ptr [rax+rax+00h]
0x1401ddadb  neg     rax
0x1401ddade  sbb     r8d, r8d
0x1401ddae1  and     r8d, 0FFFFFFFDh
0x1401ddae5  add     r8d, 4; Alignment
0x1401ddae9  mov     edx, 1Ch; Length
0x1401ddaee  mov     rcx, rbx; Address
0x1401ddaf1  call    cs:__imp_ProbeForRead
0x1401ddaf8  nop     dword ptr [rax+rax+00h]
0x1401ddafd  movups  xmm0, xmmword ptr [rbx]
0x1401ddb00  movups  xmmword ptr [rsp+138h+var_60.Data1], xmm0
0x1401ddb08  movups  xmm1, xmmword ptr [rbx+0Ch]
0x1401ddb0c  movups  xmmword ptr [rsp+138h+var_60.Data4+4], xmm1
0x1401ddb14  call    cs:__imp_W32GetUserGdiSessionState
0x1401ddb1b  nop     dword ptr [rax+rax+00h]
0x1401ddb20  cmp     [rax+24h], edi
0x1401ddb23  jz      short loc_1401DDB34
0x1401ddb25  mov     ebx, 0C0000001h
0x1401ddb2a  mov     esi, 80000005h
0x1401ddb2f  jmp     loc_1401DDC74
0x1401ddb34  call    UserIsWddmConnectedSession
0x1401ddb39  test    eax, eax
0x1401ddb3b  jnz     short loc_1401DDB47
0x1401ddb3d  mov     esi, 80000006h
0x1401ddb42  jmp     loc_1401DDC6F
0x1401ddb47  test    rbx, rbx
0x1401ddb4a  jz      short loc_1401DDB86
0x1401ddb4c  lea     rcx, [rsp+138h+var_60]
0x1401ddb54  call    DrvNeedDisplayStateCheck
0x1401ddb59  test    eax, eax
0x1401ddb5b  jz      short loc_1401DDB86
0x1401ddb5d  lea     rdx, [rsp+138h+var_60]
0x1401ddb65  mov     ecx, 1
0x1401ddb6a  call    DrvIsDisplayStateCurrent
0x1401ddb6f  test    eax, eax
0x1401ddb71  jnz     short loc_1401DDB86
0x1401ddb73  mov     r14d, 0C01E0337h
0x1401ddb79  mov     ebx, r14d
0x1401ddb7c  mov     esi, 80000007h
0x1401ddb81  jmp     loc_1401DDC7A
0x1401ddb86  mov     byte ptr [rsp+138h+var_90], dil
0x1401ddb8e  xor     r9d, r9d; unsigned int
0x1401ddb91  lea     r8d, [r9+1Dh]; unsigned int
0x1401ddb95  lea     rdx, [rsp+138h+var_60.Data4+4]; struct _GUID *
0x1401ddb9d  lea     rcx, [rsp+138h+var_90]; this
0x1401ddba5  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x1401ddbaa  mov     esi, 12h
0x1401ddbaf  mov     [rsp+138h+var_E8], rdi
0x1401ddbb4  mov     rax, [rsp+138h+var_88]
0x1401ddbbc  mov     [rsp+138h+var_F0], rax
0x1401ddbc1  mov     [rsp+138h+var_F8], rdi
0x1401ddbc6  mov     [rsp+138h+var_100], rdi
0x1401ddbcb  mov     rax, [rsp+138h+arg_20]
0x1401ddbd3  mov     [rsp+138h+var_108], rax
0x1401ddbd8  mov     byte ptr [rsp+138h+var_110], 1
0x1401ddbdd  mov     [rsp+138h+BugCheckParameter4], rdi
0x1401ddbe2  xor     r9d, r9d
0x1401ddbe5  mov     r15d, [rsp+138h+arg_10]
0x1401ddbed  mov     r8d, r15d
0x1401ddbf0  mov     rdx, r12
0x1401ddbf3  mov     ecx, r14d
0x1401ddbf6  call    xxxUserSetDisplayConfig
0x1401ddbfb  mov     ebx, eax
0x1401ddbfd  cmp     eax, 80000005h
0x1401ddc02  jz      short loc_1401DDC2B
0x1401ddc04  cmp     eax, 0C0000023h
0x1401ddc09  jz      short loc_1401DDC30
0x1401ddc0b  bt      r15d, 10h
0x1401ddc10  jb      short loc_1401DDC30
0x1401ddc12  cmp     eax, 0C01E0306h
0x1401ddc17  jz      short loc_1401DDC24
0x1401ddc19  mov     ecx, eax
0x1401ddc1b  call    _QdcSdcTranslateStatusDefault
0x1401ddc20  mov     ebx, eax
0x1401ddc22  jmp     short loc_1401DDC30
0x1401ddc24  mov     ebx, 8007064Ah
0x1401ddc29  jmp     short loc_1401DDC30
  ... truncated ...
```
