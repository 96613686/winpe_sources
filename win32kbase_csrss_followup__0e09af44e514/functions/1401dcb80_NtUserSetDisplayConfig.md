# NtUserSetDisplayConfig

- ea: `0x1401dcb80`
- end: `0x1401dd23a`
- name: `NtUserSetDisplayConfig`
- size: `1722`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14001bdf0`
- `0x1400325a4`
- `0x140033364`
- `0x140033cf0`
- `0x140033d94`
- `0x14004c720`
- `0x1400687c0`
- `0x14006888c`
- `0x140076968`
- `0x140076b80`
- `0x140078090`
- `0x140078120`
- `0x1400ed3a8`
- `0x140111998`
- `0x1401179a4`
- `0x14013e47c`
- `0x1401767dc`
- `0x140189344`
- `0x140195420`
- `0x1401af180`
- `0x1401c6dd8`
- `0x1401c7c38`
- `0x1401c7d40`
- `0x1401dcb80`
- `0x1402381f0`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401dcda8`
- `ntoskrnl!ProbeForRead` at `0x1401dcfb1`
- `ntoskrnl!ProbeForRead` at `0x1401dcda8`
- `ntoskrnl!ProbeForRead` at `0x1401dcfb1`
- `ntoskrnl!KeBugCheckEx` at `0x1401dce42`
- `ntoskrnl!KeBugCheckEx` at `0x1401dce42`
- `ntoskrnl!ExRaiseStatus` at `0x1401dcf48`
- `ntoskrnl!ExRaiseStatus` at `0x1401dcf48`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401dcbe5`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401dcbe5`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dcd84`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dcf8f`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dcd84`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dcf8f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401dd17f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401dd1ab`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401dd17f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401dd1ab`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dcc48`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dcfd4`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dcc48`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401dcfd4`
- `WIN32K!W32GetUserSessionState` at `0x1401dcbf8`
- `WIN32K!W32GetUserSessionState` at `0x1401dcbf8`

## pseudocode

```c
__int64 __fastcall NtUserSetDisplayConfig(unsigned int a1, __int64 *a2, unsigned int a3, struct _GUID *a4, __int64 a5)
{
  __int64 v6; // r15
  __int64 *v7; // r12
  __int64 v8; // rcx
  __int64 UserSessionState; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // ebx
  unsigned int v14; // esi
  struct tagTHREADINFO *v15; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int v17; // r8d
  UIPrivilegeIsolation *v18; // rcx
  char HasMinimumIntegrityLevel; // al
  char v20; // si
  __int64 *v21; // rdx
  unsigned __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // r15d
  unsigned int v25; // r14d
  __int64 CurrentProcessWow64Process; // rax
  unsigned int v27; // esi
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v29; // rax
  __int64 *v30; // r15
  unsigned int i; // r12d
  __int64 v32; // rax
  unsigned int v33; // eax
  __int64 v34; // rcx
  __int64 (*v35)(void); // rax
  int v36; // eax
  void (*v37)(void); // rax
  __int64 *v39; // [rsp+70h] [rbp-C8h]
  unsigned int v40; // [rsp+7Ch] [rbp-BCh]
  ULONG TimeIncrement; // [rsp+A0h] [rbp-98h]
  _DWORD v42[2]; // [rsp+A8h] [rbp-90h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-88h]
  __int64 *v44; // [rsp+B8h] [rbp-80h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+C0h] [rbp-78h] BYREF
  __int64 (__fastcall *v46)(PVOID); // [rsp+D0h] [rbp-68h]
  struct _GUID v47[2]; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v48; // [rsp+F8h] [rbp-40h]

  v6 = a1;
  v7 = 0;
  v39 = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  v40 = 0;
  memset(v47, 0, 28);
  v48 = MEMORY[0xFFFFF78000000320];
  TimeIncrement = KeQueryTimeIncrement();
  UserSessionState = W32GetUserSessionState(v8);
  v10 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
          UserSessionState,
          0,
          0,
          _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(UserSessionState + 16) = v10;
  if ( v10 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  if ( !*(_DWORD *)(W32GetUserGdiSessionState(v12, v11) + 32) )
  {
    v13 = -1073741823;
    v14 = 0x80000000;
LABEL_65:
    v24 = a3;
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
    v42[0] = 0x2000;
    v42[1] = -1;
    LODWORD(v43) = 0;
    HasMinimumIntegrityLevel = UIPrivilegeIsolation::CheckAccessEx(v18, v42, 0);
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
      v22 = *(_QWORD *)(*((_QWORD *)v15 + 57) + 752LL);
      v23 = *(_DWORD *)(v22 + 32) & 0x10;
    }
    else
    {
      v23 = 0;
    }
    if ( v23 || !v20 )
    {
      v13 = -1073741790;
      v14 = -2147483647;
      v24 = a3;
      goto LABEL_61;
    }
  }
  v13 = -1073741811;
  if ( (unsigned int)v6 > 0x400 )
  {
    v14 = -2147483646;
    goto LABEL_65;
  }
  v44 = 0;
  v25 = 0;
  if ( (_DWORD)v6 )
  {
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
    ProbeForRead(a2, 216 * v6, CurrentProcessWow64Process != 0 ? 1 : 4);
    v27 = 0;
    v22 = 0;
    v21 = a2;
    while ( (unsigned int)v22 < (unsigned int)v6 )
    {
      if ( *v21 < 0 )
        ++v27;
      v22 = (unsigned int)(v22 + 1);
      v21 += 27;
    }
    if ( v27 )
    {
      v7 = (__int64 *)Win32AllocPoolWithQuotaZInitImpl(v22, 216LL * v27, 0x63447355u);
      v39 = v7;
      if ( !v7 )
        ExRaiseStatus(-1073741801);
      if ( v46 != (__int64 (__fastcall *)(PVOID))-1LL )
      {
        BugCheckParameter4 = PtiCurrent();
        KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v7, (ULONG_PTR)BugCheckParameter4);
      }
      v29 = PtiCurrent();
      BugCheckParameter2[0] = *((_QWORD *)v29 + 47);
      v22 = (unsigned __int64)BugCheckParameter2;
      *((_QWORD *)v29 + 47) = BugCheckParameter2;
      BugCheckParameter2[1] = (ULONG_PTR)v7;
      v46 = GreDeleteFastMutex;
    }
    v30 = v7;
    v44 = v7;
    for ( i = 0; i < a1; ++i )
    {
      if ( *a2 < 0 )
      {
        if ( v25 >= v27 )
        {
          v14 = -2147483645;
          v7 = v39;
          v24 = a3;
          goto LABEL_61;
        }
        RtlCopyVolatileMemory(v30, a2, 0xD8u);
        if ( *v30 >= 0 )
        {
          v13 = -1073741790;
          v14 = -2147483644;
          v7 = v39;
          v24 = a3;
          goto LABEL_61;
        }
        ++v25;
        v30 += 27;
        v44 = v30;
      }
      a2 += 27;
    }
    if ( v25 != v27 )
    {
      v14 = -2147483645;
      v7 = v39;
      v24 = a3;
      goto LABEL_61;
    }
    v7 = v39;
  }
  v40 = v25;
  if ( a4 )
  {
    v32 = PsGetCurrentProcessWow64Process();
    ProbeForRead(a4, 0x1Cu, v32 != 0 ? 1 : 4);
    v47[0] = *a4;
    *(_OWORD *)&v47[0].Data4[4] = *(_OWORD *)&a4->Data4[4];
  }
  if ( *(_DWORD *)(W32GetUserGdiSessionState(v22, v21) + 36) )
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
  if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v47) && !(unsigned int)DrvIsDisplayStateCurrent(1, v47) )
  {
    v13 = -1071774921;
    v14 = -2147483641;
    goto LABEL_65;
  }
  LOBYTE(v42[0]) = 0;
  CDisplayScenarioContextScope::ContextScopeConstructor(
    (CDisplayScenarioContextScope *)v42,
    (const struct _GUID *)&v47[0].Data4[4],
    0x1Du,
    0);
  v14 = 18;
  v24 = a3;
  v33 = xxxUserSetDisplayConfig(v25, v7, a3, 0, 0, 1, a5, 0, 0, v43, 0);
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
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v42);
LABEL_61:
  if ( v14 != 18 )
LABEL_66:
    LogDiagSDC(v40, (_DWORD)v7, v24, v13, 0, v14, v48 * TimeIncrement, 0, 0);
  if ( v13 < 0 )
  {
    if ( a4 && (unsigned int)DrvNeedDisplayStateCheck(v47) && !(unsigned int)DrvIsDisplayStateCurrent(0, v47) )
      v13 = -1071774921;
  }
  else
  {
    v34 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v22) + 48);
    v35 = *(__int64 (**)(void))(v34 + 3528);
    if ( v35 )
      v36 = v35();
    else
      v36 = -1073741637;
    if ( v36 >= 0 )
    {
      v37 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v34) + 48) + 3536LL);
      if ( v37 )
        v37();
    }
  }
  if ( v7 )
    Win32RawLockedItemBase<DISPLAYCONFIG_PATH_INFO_INTERNAL,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  UserSessionSwitchLeaveCritWithNonPaged();
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1401dcb80  mov     rax, rsp
0x1401dcb83  mov     [rax+20h], r9
0x1401dcb87  mov     [rax+18h], r8d
0x1401dcb8b  mov     [rax+8], ecx
0x1401dcb8e  push    rbx
0x1401dcb8f  push    rsi
0x1401dcb90  push    rdi
0x1401dcb91  push    r12
0x1401dcb93  push    r13
0x1401dcb95  push    r14
0x1401dcb97  push    r15
0x1401dcb99  sub     rsp, 100h
0x1401dcba0  mov     r13, rdx
0x1401dcba3  mov     r15d, ecx
0x1401dcba6  xor     edi, edi
0x1401dcba8  mov     r12d, edi
0x1401dcbab  mov     [rsp+138h+var_C8], rdi
0x1401dcbb0  lea     rcx, [rax-78h]
0x1401dcbb4  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401dcbb9  mov     [rsp+138h+var_BC], edi
0x1401dcbbd  xorps   xmm1, xmm1
0x1401dcbc0  movups  xmmword ptr [rsp+138h+var_60.Data1], xmm1
0x1401dcbc8  movups  xmmword ptr [rsp+138h+var_60.Data4+4], xmm1
0x1401dcbd0  mov     rax, 0FFFFF78000000320h
0x1401dcbda  mov     rax, [rax]
0x1401dcbdd  mov     [rsp+138h+var_40], rax
0x1401dcbe5  call    cs:__imp_KeQueryTimeIncrement
0x1401dcbec  nop     dword ptr [rax+rax+00h]
0x1401dcbf1  mov     [rsp+138h+var_98], eax
0x1401dcbf8  call    cs:__imp_W32GetUserSessionState
0x1401dcbff  nop     dword ptr [rax+rax+00h]
0x1401dcc04  mov     rbx, rax
0x1401dcc07  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401dcc0e  xor     r8d, r8d
0x1401dcc11  xor     edx, edx
0x1401dcc13  mov     rcx, rax
0x1401dcc16  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401dcc1b  mov     [rbx+10h], rax
0x1401dcc1f  test    rax, rax
0x1401dcc22  jz      short loc_1401DCC48
0x1401dcc24  lea     rcx, [rbx+4C40h]
0x1401dcc2b  call    DestroySharedUserCritDeferredUnlockList
0x1401dcc30  lea     rcx, [rbx+4C78h]
0x1401dcc37  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dcc3c  lea     rcx, [rbx+4C68h]
0x1401dcc43  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dcc48  call    cs:__imp_W32GetUserGdiSessionState
0x1401dcc4f  nop     dword ptr [rax+rax+00h]
0x1401dcc54  cmp     [rax+20h], edi
0x1401dcc57  jnz     short loc_1401DCC68
0x1401dcc59  mov     ebx, 0C0000001h
0x1401dcc5e  mov     esi, 80000000h
0x1401dcc63  jmp     loc_1401DD134
0x1401dcc68  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dcc6d  mov     rbx, rax
0x1401dcc70  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x1401dcc75  mov     rcx, [rbx+1C8h]
0x1401dcc7c  add     rcx, 360h; this
0x1401dcc83  test    eax, eax
0x1401dcc85  jz      short loc_1401DCC93
0x1401dcc87  mov     edx, 2000h; struct tagUIPI_INFO *
0x1401dcc8c  call    ?HasMinimumIntegrityLevel@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@K@Z; UIPrivilegeIsolation::HasMinimumIntegrityLevel(tagUIPI_INFO const &,ulong)
0x1401dcc91  jmp     short loc_1401DCCC2
0x1401dcc93  mov     [rsp+138h+var_90], 2000h
0x1401dcc9e  mov     [rsp+138h+var_8C], 0FFFFFFFFh
0x1401dcca9  xor     eax, eax
0x1401dccab  mov     dword ptr [rsp+138h+var_88], eax
0x1401dccb2  xor     r8d, r8d
0x1401dccb5  lea     rdx, [rsp+138h+var_90]
0x1401dccbd  call    ?CheckAccessEx@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::CheckAccessEx(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x1401dccc2  mov     sil, al
0x1401dccc5  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x1401dccca  test    eax, eax
0x1401dcccc  jnz     short loc_1401DCD14
0x1401dccce  lock cmpxchg [rbx+208h], edi
0x1401dccd6  bt      eax, 1Dh
0x1401dccda  jnb     short loc_1401DCCF2
0x1401dccdc  mov     rax, [rbx+1C8h]
0x1401dcce3  mov     rcx, [rax+2F0h]
0x1401dccea  mov     eax, [rcx+20h]
0x1401dcced  and     eax, 10h
0x1401dccf0  jmp     short loc_1401DCCF4
0x1401dccf2  mov     eax, edi
0x1401dccf4  test    eax, eax
0x1401dccf6  jnz     short loc_1401DCCFD
0x1401dccf8  test    sil, sil
0x1401dccfb  jnz     short loc_1401DCD36
0x1401dccfd  mov     ebx, 0C0000022h
0x1401dcd02  mov     esi, 80000001h
0x1401dcd07  mov     r15d, [rsp+138h+arg_10]
0x1401dcd0f  jmp     loc_1401DD11D
0x1401dcd14  mov     edx, 10h; unsigned int
0x1401dcd19  mov     rcx, [rbx+1C8h]; this
0x1401dcd20  call    ?HasUILimit@tagPROCESSINFO@@QEBA_NK@Z; tagPROCESSINFO::HasUILimit(ulong)
0x1401dcd25  test    al, al
0x1401dcd27  jnz     loc_1401DD12A
0x1401dcd2d  test    sil, sil
0x1401dcd30  jz      loc_1401DD12A
0x1401dcd36  mov     [rsp+138h+var_D4], edi
0x1401dcd3a  mov     ebx, 0C000000Dh
0x1401dcd3f  mov     [rsp+138h+var_9C], ebx
0x1401dcd46  cmp     r15d, 400h
0x1401dcd4d  jbe     short loc_1401DCD59
0x1401dcd4f  mov     esi, 80000002h
0x1401dcd54  jmp     loc_1401DD134
0x1401dcd59  mov     [rsp+138h+var_B8], rdi
0x1401dcd61  mov     [rsp+138h+var_80], rdi
0x1401dcd69  mov     [rsp+138h+var_C0], edi
0x1401dcd6d  mov     r14d, edi
0x1401dcd70  mov     [rsp+138h+var_B0], edi
0x1401dcd77  mov     [rsp+138h+var_D8], edi
0x1401dcd7b  test    r15d, r15d
0x1401dcd7e  jz      loc_1401DCF7D
0x1401dcd84  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dcd8b  nop     dword ptr [rax+rax+00h]
0x1401dcd90  neg     rax
0x1401dcd93  sbb     r8d, r8d
0x1401dcd96  and     r8d, 0FFFFFFFDh
0x1401dcd9a  add     r8d, 4; Alignment
0x1401dcd9e  imul    rdx, r15, 0D8h; Length
0x1401dcda5  mov     rcx, r13; Address
0x1401dcda8  call    cs:__imp_ProbeForRead
0x1401dcdaf  nop     dword ptr [rax+rax+00h]
0x1401dcdb4  mov     esi, edi
0x1401dcdb6  mov     [rsp+138h+var_C0], edi
0x1401dcdba  mov     ecx, edi; unsigned __int64
0x1401dcdbc  mov     rdx, r13
0x1401dcdbf  mov     r8d, 0D8h
0x1401dcdc5  mov     [rsp+138h+var_B8], rdx
0x1401dcdcd  mov     [rsp+138h+var_D8], ecx
0x1401dcdd1  cmp     ecx, r15d
0x1401dcdd4  jnb     short loc_1401DCDEB
0x1401dcdd6  mov     rax, [rdx]
0x1401dcdd9  test    rax, rax
0x1401dcddc  jns     short loc_1401DCDE4
0x1401dcdde  inc     esi
0x1401dcde0  mov     [rsp+138h+var_C0], esi
0x1401dcde4  inc     ecx
0x1401dcde6  add     rdx, r8
0x1401dcde9  jmp     short loc_1401DCDC5
0x1401dcdeb  test    esi, esi
0x1401dcded  jz      loc_1401DCE8E
0x1401dcdf3  mov     eax, esi
0x1401dcdf5  imul    rdx, rax, 0D8h; unsigned __int64
0x1401dcdfc  mov     r8d, 63447355h; unsigned int
0x1401dce02  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401dce07  mov     r12, rax
0x1401dce0a  mov     [rsp+138h+var_C8], rax
0x1401dce0f  test    rax, rax
0x1401dce12  jz      loc_1401DCF43
0x1401dce18  cmp     [rsp+138h+var_68], 0FFFFFFFFFFFFFFFFh
0x1401dce21  jz      short loc_1401DCE4E
0x1401dce23  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dce28  mov     [rsp+138h+BugCheckParameter4], rax; BugCheckParameter4
0x1401dce2d  mov     r9, r12; BugCheckParameter3
0x1401dce30  lea     r8, [rsp+138h+BugCheckParameter2]; BugCheckParameter2
0x1401dce38  mov     edx, 12h; BugCheckParameter1
0x1401dce3d  mov     ecx, 164h; BugCheckCode
0x1401dce42  call    cs:__imp_KeBugCheckEx
0x1401dce4e  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dce53  mov     rcx, [rax+178h]
0x1401dce5a  mov     [rsp+138h+BugCheckParameter2], rcx
0x1401dce62  lea     rcx, [rsp+138h+BugCheckParameter2]
0x1401dce6a  mov     [rax+178h], rcx
0x1401dce71  mov     [rsp+138h+var_70], r12
0x1401dce79  lea     rax, GreDeleteFastMutex
0x1401dce80  mov     [rsp+138h+var_68], rax
0x1401dce88  mov     r8d, 0D8h; Size
0x1401dce8e  mov     r15, r12
0x1401dce91  mov     [rsp+138h+var_80], r12
0x1401dce99  mov     r12d, edi
0x1401dce9c  mov     [rsp+138h+var_D8], edi
0x1401dcea0  mov     [rsp+138h+var_B8], r13
0x1401dcea8  cmp     r12d, [rsp+138h+arg_0]
0x1401dceb0  jnb     loc_1401DCF54
0x1401dceb6  mov     rax, [r13+0]
0x1401dceba  test    rax, rax
0x1401dcebd  jns     short loc_1401DCF33
0x1401dcebf  cmp     r14d, esi
0x1401dcec2  jb      short loc_1401DCEE3
0x1401dcec4  mov     [rsp+138h+var_D0], ebx
0x1401dcec8  mov     esi, 80000003h
0x1401dcecd  mov     [rsp+138h+var_D4], esi
0x1401dced1  mov     r12, [rsp+138h+var_C8]
0x1401dced6  mov     r15d, [rsp+138h+arg_10]
0x1401dcede  jmp     loc_1401DD11D
0x1401dcee3  mov     rdx, r13; Src
0x1401dcee6  mov     rcx, r15; void *
0x1401dcee9  call    RtlCopyVolatileMemory
0x1401dceee  cmp     [r15], rdi
0x1401dcef1  jl      short loc_1401DCF17
0x1401dcef3  mov     ebx, 0C0000022h
0x1401dcef8  mov     [rsp+138h+var_D0], ebx
0x1401dcefc  mov     esi, 80000004h
0x1401dcf01  mov     [rsp+138h+var_D4], esi
0x1401dcf05  mov     r12, [rsp+138h+var_C8]
0x1401dcf0a  mov     r15d, [rsp+138h+arg_10]
0x1401dcf12  jmp     loc_1401DD11D
0x1401dcf17  inc     r14d
0x1401dcf1a  mov     [rsp+138h+var_B0], r14d
0x1401dcf22  mov     r8d, 0D8h
0x1401dcf28  add     r15, r8
0x1401dcf2b  mov     [rsp+138h+var_80], r15
0x1401dcf33  inc     r12d
0x1401dcf36  mov     [rsp+138h+var_D8], r12d
0x1401dcf3b  add     r13, r8
0x1401dcf3e  jmp     loc_1401DCEA0
0x1401dcf43  mov     ecx, 0C0000017h; Status
0x1401dcf48  call    cs:__imp_ExRaiseStatus
0x1401dcf54  cmp     r14d, esi
0x1401dcf57  jz      short loc_1401DCF78
0x1401dcf59  mov     [rsp+138h+var_D0], ebx
0x1401dcf5d  mov     esi, 80000003h
0x1401dcf62  mov     [rsp+138h+var_D4], esi
0x1401dcf66  mov     r12, [rsp+138h+var_C8]
0x1401dcf6b  mov     r15d, [rsp+138h+arg_10]
0x1401dcf73  jmp     loc_1401DD11D
0x1401dcf78  mov     r12, [rsp+138h+var_C8]
0x1401dcf7d  mov     [rsp+138h+var_BC], r14d
0x1401dcf82  mov     rbx, [rsp+138h+Address]
0x1401dcf8a  test    rbx, rbx
0x1401dcf8d  jz      short loc_1401DCFD4
0x1401dcf8f  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dcf96  nop     dword ptr [rax+rax+00h]
0x1401dcf9b  neg     rax
0x1401dcf9e  sbb     r8d, r8d
0x1401dcfa1  and     r8d, 0FFFFFFFDh
0x1401dcfa5  add     r8d, 4; Alignment
0x1401dcfa9  mov     edx, 1Ch; Length
0x1401dcfae  mov     rcx, rbx; Address
0x1401dcfb1  call    cs:__imp_ProbeForRead
0x1401dcfb8  nop     dword ptr [rax+rax+00h]
0x1401dcfbd  movups  xmm0, xmmword ptr [rbx]
0x1401dcfc0  movups  xmmword ptr [rsp+138h+var_60.Data1], xmm0
0x1401dcfc8  movups  xmm1, xmmword ptr [rbx+0Ch]
0x1401dcfcc  movups  xmmword ptr [rsp+138h+var_60.Data4+4], xmm1
0x1401dcfd4  call    cs:__imp_W32GetUserGdiSessionState
0x1401dcfdb  nop     dword ptr [rax+rax+00h]
0x1401dcfe0  cmp     [rax+24h], edi
0x1401dcfe3  jz      short loc_1401DCFF4
0x1401dcfe5  mov     ebx, 0C0000001h
0x1401dcfea  mov     esi, 80000005h
0x1401dcfef  jmp     loc_1401DD134
0x1401dcff4  call    UserIsWddmConnectedSession
0x1401dcff9  test    eax, eax
0x1401dcffb  jnz     short loc_1401DD007
0x1401dcffd  mov     esi, 80000006h
0x1401dd002  jmp     loc_1401DD12F
0x1401dd007  test    rbx, rbx
0x1401dd00a  jz      short loc_1401DD046
0x1401dd00c  lea     rcx, [rsp+138h+var_60]
0x1401dd014  call    DrvNeedDisplayStateCheck
0x1401dd019  test    eax, eax
0x1401dd01b  jz      short loc_1401DD046
0x1401dd01d  lea     rdx, [rsp+138h+var_60]
0x1401dd025  mov     ecx, 1
0x1401dd02a  call    DrvIsDisplayStateCurrent
0x1401dd02f  test    eax, eax
0x1401dd031  jnz     short loc_1401DD046
0x1401dd033  mov     r14d, 0C01E0337h
0x1401dd039  mov     ebx, r14d
0x1401dd03c  mov     esi, 80000007h
0x1401dd041  jmp     loc_1401DD13A
0x1401dd046  mov     byte ptr [rsp+138h+var_90], dil
0x1401dd04e  xor     r9d, r9d; unsigned int
0x1401dd051  lea     r8d, [r9+1Dh]; unsigned int
0x1401dd055  lea     rdx, [rsp+138h+var_60.Data4+4]; struct _GUID *
0x1401dd05d  lea     rcx, [rsp+138h+var_90]; this
0x1401dd065  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x1401dd06a  mov     esi, 12h
0x1401dd06f  mov     [rsp+138h+var_E8], rdi
0x1401dd074  mov     rax, [rsp+138h+var_88]
0x1401dd07c  mov     [rsp+138h+var_F0], rax
0x1401dd081  mov     [rsp+138h+var_F8], rdi
0x1401dd086  mov     [rsp+138h+var_100], rdi
0x1401dd08b  mov     rax, [rsp+138h+arg_20]
0x1401dd093  mov     [rsp+138h+var_108], rax
0x1401dd098  mov     byte ptr [rsp+138h+var_110], 1
0x1401dd09d  mov     [rsp+138h+BugCheckParameter4], rdi
0x1401dd0a2  xor     r9d, r9d
0x1401dd0a5  mov     r15d, [rsp+138h+arg_10]
0x1401dd0ad  mov     r8d, r15d
0x1401dd0b0  mov     rdx, r12
0x1401dd0b3  mov     ecx, r14d
0x1401dd0b6  call    xxxUserSetDisplayConfig
0x1401dd0bb  mov     ebx, eax
0x1401dd0bd  cmp     eax, 80000005h
0x1401dd0c2  jz      short loc_1401DD0EB
0x1401dd0c4  cmp     eax, 0C0000023h
0x1401dd0c9  jz      short loc_1401DD0F0
0x1401dd0cb  bt      r15d, 10h
0x1401dd0d0  jb      short loc_1401DD0F0
0x1401dd0d2  cmp     eax, 0C01E0306h
0x1401dd0d7  jz      short loc_1401DD0E4
0x1401dd0d9  mov     ecx, eax
0x1401dd0db  call    _QdcSdcTranslateStatusDefault
0x1401dd0e0  mov     ebx, eax
0x1401dd0e2  jmp     short loc_1401DD0F0
0x1401dd0e4  mov     ebx, 8007064Ah
0x1401dd0e9  jmp     short loc_1401DD0F0
  ... truncated ...
```
