# NtUserSetSysColors

- ea: `0x1401de290`
- end: `0x1401de5a1`
- name: `NtUserSetSysColors`
- size: `785`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140012c80`
- `0x140029324`
- `0x140029fe8`
- `0x14002a0e4`
- `0x14002ab14`
- `0x1400411c0`
- `0x140043810`
- `0x1400759e0`
- `0x140076ef0`
- `0x140076f80`
- `0x140080d34`
- `0x140097350`
- `0x14009929c`
- `0x1400b2ae0`
- `0x1400b2bac`
- `0x140181bc4`
- `0x14019050c`
- `0x1401c7338`
- `0x1401c8198`
- `0x1401c82a0`
- `0x1401de290`
- `0x140238ba0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401de441`
- `ntoskrnl!ProbeForRead` at `0x1401de46c`
- `ntoskrnl!ProbeForRead` at `0x1401de441`
- `ntoskrnl!ProbeForRead` at `0x1401de46c`
- `ntoskrnl!ExRaiseStatus` at `0x1401de498`
- `ntoskrnl!ExRaiseStatus` at `0x1401de4d2`
- `ntoskrnl!ExRaiseStatus` at `0x1401de498`
- `ntoskrnl!ExRaiseStatus` at `0x1401de4d2`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401de41d`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401de44d`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401de41d`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401de44d`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401de4f0`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401de4f0`
- `WIN32K!W32GetUserSessionState` at `0x1401de2d0`
- `WIN32K!W32GetUserSessionState` at `0x1401de2d0`

## pseudocode

```c
__int64 __fastcall NtUserSetSysColors(__int64 a1, volatile void *a2, volatile void *a3, int a4)
{
  __int64 v6; // r15
  __int64 UserSessionState; // rbx
  __int64 v8; // rax
  struct tagTHREADINFO *v9; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int v11; // r8d
  UIPrivilegeIsolation *v12; // rcx
  char HasMinimumIntegrityLevel; // al
  int v14; // esi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  int v19; // eax
  void *v20; // r14
  void *v21; // rbx
  __int64 CurrentProcessWow64Process; // rax
  __int64 v23; // rax
  unsigned __int64 v24; // rcx
  void *v25; // rax
  unsigned __int64 v26; // rcx
  void *v27; // rax
  int v28; // ecx
  ULONG_PTR BugCheckParameter2; // [rsp+40h] [rbp-88h] BYREF
  int v30; // [rsp+48h] [rbp-80h]
  PVOID Buffer; // [rsp+58h] [rbp-70h]
  PVOID v32; // [rsp+60h] [rbp-68h]
  _BYTE v33[24]; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v34[32]; // [rsp+80h] [rbp-48h] BYREF

  v6 = (unsigned int)a1;
  BugCheckParameter2 = 0xFFFFFFFF00002000uLL;
  v30 = 0;
  UserSessionState = W32GetUserSessionState(a1, a2, a3);
  v8 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
         UserSessionState,
         0,
         0,
         _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(UserSessionState + 16) = v8;
  if ( v8 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  v9 = PtiCurrent();
  if ( (unsigned int)Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( tagPROCESSINFO::HasUILimit(*((tagPROCESSINFO **)v9 + 57), 8u) )
    {
LABEL_8:
      v14 = 0;
      UserSetLastError(5);
      goto LABEL_9;
    }
    IsEnabledDeviceUsageNoInline = Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline();
    v12 = (UIPrivilegeIsolation *)(*((_QWORD *)v9 + 57) + 864LL);
    if ( IsEnabledDeviceUsageNoInline )
    {
      HasMinimumIntegrityLevel = UIPrivilegeIsolation::HasMinimumIntegrityLevel(
                                   v12,
                                   (const struct tagUIPI_INFO *)0x2000,
                                   v11);
      goto LABEL_7;
    }
    BugCheckParameter2 = 0xFFFFFFFF00002000uLL;
    v30 = 0;
  }
  else
  {
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0x20000000) != 0 )
      v19 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v9 + 57) + 752LL) + 32LL) & 8;
    else
      v19 = 0;
    if ( v19 )
      goto LABEL_8;
    v12 = (UIPrivilegeIsolation *)(*((_QWORD *)v9 + 57) + 864LL);
  }
  HasMinimumIntegrityLevel = UIPrivilegeIsolation::CheckAccessEx(v12, &BugCheckParameter2, 0);
LABEL_7:
  if ( !HasMinimumIntegrityLevel )
    goto LABEL_8;
  v20 = 0;
  Buffer = 0;
  v21 = 0;
  v32 = 0;
  if ( (_DWORD)v6 )
  {
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
    ProbeForRead(a2, 4 * v6, CurrentProcessWow64Process != 0 ? 1 : 4);
    v23 = PsGetCurrentProcessWow64Process();
    ProbeForRead(a3, 4 * v6, v23 != 0 ? 1 : 4);
    v25 = Win32AllocPoolWithQuotaZInitImpl(v24, 4 * v6, 0x72637355u);
    v20 = v25;
    Buffer = v25;
    if ( !v25 )
      ExRaiseStatus(-1073741801);
    RtlCopyVolatileMemory(v25, (const void *)a2, 4 * v6);
    v27 = Win32AllocPoolWithQuotaZInitImpl(v26, 4 * v6, 0x76637355u);
    v21 = v27;
    v32 = v27;
    if ( !v27 )
      ExRaiseStatus(-1073741801);
    RtlCopyVolatileMemory(v27, (const void *)a3, 4 * v6);
  }
  Win32RawLockedItemNoCleanup<unsigned long,0>::Win32RawLockedItemNoCleanup<unsigned long,0>(v34, v20);
  Win32RawLockedItemNoCleanup<unsigned long,0>::Win32RawLockedItemNoCleanup<unsigned long,0>(v33, v21);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(&BugCheckParameter2);
  CreateProfileUserName((ULONG_PTR)&BugCheckParameter2);
  v14 = xxxSetSysColors(v28, v6, (_DWORD)v20, (_DWORD)v21, a4);
  Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>(&BugCheckParameter2);
  Win32RawLockedItemNoCleanup<unsigned long,0>::~Win32RawLockedItemNoCleanup<unsigned long,0>(v33);
  Win32RawLockedItemNoCleanup<unsigned long,0>::~Win32RawLockedItemNoCleanup<unsigned long,0>(v34);
  if ( v20 )
    GreDeleteFastMutex(v20);
  if ( v21 )
    GreDeleteFastMutex(v21);
LABEL_9:
  UserSessionSwitchLeaveCritWithNonPaged(v16, v15, v17);
  return v14;
}

```

## disassembly

```asm
0x1401de290  mov     [rsp+arg_0], rbx
0x1401de295  mov     [rsp+arg_8], rsi
0x1401de29a  mov     [rsp+arg_18], r9d
0x1401de29f  push    rdi
0x1401de2a0  push    r12
0x1401de2a2  push    r13
0x1401de2a4  push    r14
0x1401de2a6  push    r15
0x1401de2a8  sub     rsp, 0A0h
0x1401de2af  mov     r12, r8
0x1401de2b2  mov     r13, rdx
0x1401de2b5  mov     r15d, ecx
0x1401de2b8  mov     esi, 2000h
0x1401de2bd  mov     dword ptr [rsp+0C8h+BugCheckParameter2], esi
0x1401de2c1  or      r14d, 0FFFFFFFFh
0x1401de2c5  mov     dword ptr [rsp+0C8h+BugCheckParameter2+4], r14d
0x1401de2ca  xor     eax, eax
0x1401de2cc  mov     [rsp+0C8h+var_80], eax
0x1401de2d0  call    cs:__imp_W32GetUserSessionState
0x1401de2d7  nop     dword ptr [rax+rax+00h]
0x1401de2dc  mov     rbx, rax
0x1401de2df  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401de2e6  xor     r8d, r8d
0x1401de2e9  xor     edx, edx
0x1401de2eb  mov     rcx, rax
0x1401de2ee  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401de2f3  mov     [rbx+10h], rax
0x1401de2f7  xor     edi, edi
0x1401de2f9  test    rax, rax
0x1401de2fc  jz      short loc_1401DE322
0x1401de2fe  lea     rcx, [rbx+4C40h]
0x1401de305  call    DestroySharedUserCritDeferredUnlockList
0x1401de30a  lea     rcx, [rbx+4C78h]
0x1401de311  call    DestroyDeferredUnlockObjectAssignmentList
0x1401de316  lea     rcx, [rbx+4C68h]
0x1401de31d  call    DestroyDeferredUnlockObjectAssignmentList
0x1401de322  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401de327  mov     rbx, rax
0x1401de32a  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x1401de32f  test    eax, eax
0x1401de331  jz      short loc_1401DE3B1
0x1401de333  mov     edx, 8; unsigned int
0x1401de338  mov     rcx, [rbx+1C8h]; this
0x1401de33f  call    ?HasUILimit@tagPROCESSINFO@@QEBA_NK@Z; tagPROCESSINFO::HasUILimit(ulong)
0x1401de344  test    al, al
0x1401de346  jnz     short loc_1401DE36E
0x1401de348  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x1401de34d  mov     rcx, [rbx+1C8h]
0x1401de354  add     rcx, 360h; this
0x1401de35b  test    eax, eax
0x1401de35d  jz      short loc_1401DE3A0
0x1401de35f  mov     edx, esi; struct tagUIPI_INFO *
0x1401de361  call    ?HasMinimumIntegrityLevel@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@K@Z; UIPrivilegeIsolation::HasMinimumIntegrityLevel(tagUIPI_INFO const &,ulong)
0x1401de366  test    al, al
0x1401de368  jnz     loc_1401DE3FD
0x1401de36e  mov     esi, edi
0x1401de370  mov     ecx, 5
0x1401de375  call    UserSetLastError
0x1401de37a  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401de37f  movsxd  rax, esi
0x1401de382  lea     r11, [rsp+0C8h+var_28]
0x1401de38a  mov     rbx, [r11+30h]
0x1401de38e  mov     rsi, [r11+38h]
0x1401de392  mov     rsp, r11
0x1401de395  pop     r15
0x1401de397  pop     r14
0x1401de399  pop     r13
0x1401de39b  pop     r12
0x1401de39d  pop     rdi
0x1401de39e  retn
0x1401de3a0  mov     dword ptr [rsp+0C8h+BugCheckParameter2], esi
0x1401de3a4  mov     dword ptr [rsp+0C8h+BugCheckParameter2+4], r14d
0x1401de3a9  xor     eax, eax
0x1401de3ab  mov     [rsp+0C8h+var_80], eax
0x1401de3af  jmp     short loc_1401DE3EB
0x1401de3b1  xor     eax, eax
0x1401de3b3  lock cmpxchg [rbx+208h], edi
0x1401de3bb  bt      eax, 1Dh
0x1401de3bf  jnb     short loc_1401DE3D7
0x1401de3c1  mov     rax, [rbx+1C8h]
0x1401de3c8  mov     rcx, [rax+2F0h]
0x1401de3cf  mov     eax, [rcx+20h]
0x1401de3d2  and     eax, 8
0x1401de3d5  jmp     short loc_1401DE3D9
0x1401de3d7  mov     eax, edi
0x1401de3d9  test    eax, eax
0x1401de3db  jnz     short loc_1401DE36E
0x1401de3dd  mov     rcx, [rbx+1C8h]
0x1401de3e4  add     rcx, 360h
0x1401de3eb  xor     r8d, r8d
0x1401de3ee  lea     rdx, [rsp+0C8h+BugCheckParameter2]
0x1401de3f3  call    ?CheckAccessEx@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::CheckAccessEx(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x1401de3f8  jmp     loc_1401DE366
0x1401de3fd  mov     r14, rdi
0x1401de400  mov     [rsp+0C8h+Buffer], rdi
0x1401de405  mov     rbx, rdi
0x1401de408  mov     [rsp+0C8h+var_68], rbx
0x1401de40d  test    r15d, r15d
0x1401de410  jz      loc_1401DE511
0x1401de416  mov     rsi, r15
0x1401de419  shl     rsi, 2
0x1401de41d  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401de424  nop     dword ptr [rax+rax+00h]
0x1401de429  neg     rax
0x1401de42c  sbb     r8d, r8d
0x1401de42f  mov     ebx, 0FFFFFFFDh
0x1401de434  and     r8d, ebx
0x1401de437  add     r8d, 4; Alignment
0x1401de43b  mov     rdx, rsi; Length
0x1401de43e  mov     rcx, r13; Address
0x1401de441  call    cs:__imp_ProbeForRead
0x1401de448  nop     dword ptr [rax+rax+00h]
0x1401de44d  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401de454  nop     dword ptr [rax+rax+00h]
0x1401de459  neg     rax
0x1401de45c  sbb     r8d, r8d
0x1401de45f  and     r8d, ebx
0x1401de462  add     r8d, 4; Alignment
0x1401de466  mov     rdx, rsi; Length
0x1401de469  mov     rcx, r12; Address
0x1401de46c  call    cs:__imp_ProbeForRead
0x1401de473  nop     dword ptr [rax+rax+00h]
0x1401de478  mov     r8d, 72637355h; unsigned int
0x1401de47e  mov     rdx, rsi; unsigned __int64
0x1401de481  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401de486  mov     r14, rax
0x1401de489  mov     [rsp+0C8h+Buffer], rax
0x1401de48e  test    rax, rax
0x1401de491  jnz     short loc_1401DE4A4
0x1401de493  mov     ecx, 0C0000017h; Status
0x1401de498  call    cs:__imp_ExRaiseStatus
0x1401de4a4  mov     r8, rsi; Size
0x1401de4a7  mov     rdx, r13; Src
0x1401de4aa  mov     rcx, rax; void *
0x1401de4ad  call    RtlCopyVolatileMemory
0x1401de4b2  mov     r8d, 76637355h; unsigned int
0x1401de4b8  mov     rdx, rsi; unsigned __int64
0x1401de4bb  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401de4c0  mov     rbx, rax
0x1401de4c3  mov     [rsp+0C8h+var_68], rax
0x1401de4c8  test    rax, rax
0x1401de4cb  jnz     short loc_1401DE4DE
0x1401de4cd  mov     ecx, 0C0000017h; Status
0x1401de4d2  call    cs:__imp_ExRaiseStatus
0x1401de4de  mov     r8, rsi; Size
0x1401de4e1  mov     rdx, r12; Src
0x1401de4e4  mov     rcx, rax; void *
0x1401de4e7  call    RtlCopyVolatileMemory
0x1401de4ec  jmp     short loc_1401DE511
0x1401de4ee  mov     ecx, eax; Status
0x1401de4f0  call    cs:__imp_RtlNtStatusToDosError
0x1401de4f7  nop     dword ptr [rax+rax+00h]
0x1401de4fc  xor     esi, esi
0x1401de4fe  mov     ecx, eax
0x1401de500  call    UserSetLastError
0x1401de505  mov     r14, [rsp+0C8h+Buffer]
0x1401de50a  mov     rbx, [rsp+0C8h+var_68]
0x1401de50f  jmp     short loc_1401DE57E
0x1401de511  mov     rdx, r14
0x1401de514  lea     rcx, [rsp+0C8h+var_48]
0x1401de51c  call    ??0?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@PEAKP6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<ulong,0>::Win32RawLockedItemNoCleanup<ulong,0>(ulong *,void (*)(void *))
0x1401de521  mov     rdx, rbx
0x1401de524  lea     rcx, [rsp+0C8h+var_60]
0x1401de529  call    ??0?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@PEAKP6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<ulong,0>::Win32RawLockedItemNoCleanup<ulong,0>(ulong *,void (*)(void *))
0x1401de52e  lea     rcx, [rsp+0C8h+BugCheckParameter2]
0x1401de533  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401de538  lea     rcx, [rsp+0C8h+BugCheckParameter2]; BugCheckParameter2
0x1401de53d  call    ?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z; CreateProfileUserName(Win32RawOptionalLockedItemAlways<tagPROFILEUSERNAME,&Win32FreePool(void *)> *)
0x1401de542  mov     eax, [rsp+0C8h+arg_18]
0x1401de549  mov     [rsp+0C8h+var_A8], eax
0x1401de54d  mov     r9, rbx
0x1401de550  mov     r8, r14
0x1401de553  mov     edx, r15d
0x1401de556  call    xxxSetSysColors
0x1401de55b  mov     esi, eax
0x1401de55d  lea     rcx, [rsp+0C8h+BugCheckParameter2]
0x1401de562  call    ??1?$Win32RawOptionalLockedItemAlways@X$1?Win32FreePool@@YAXPEAX@Z@@QEAA@XZ; Win32RawOptionalLockedItemAlways<void,&Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&Win32FreePool(void *)>(void)
0x1401de567  lea     rcx, [rsp+0C8h+var_60]
0x1401de56c  call    ??1?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<ulong,0>::~Win32RawLockedItemNoCleanup<ulong,0>(void)
0x1401de571  lea     rcx, [rsp+0C8h+var_48]
0x1401de579  call    ??1?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<ulong,0>::~Win32RawLockedItemNoCleanup<ulong,0>(void)
0x1401de57e  test    r14, r14
0x1401de581  jz      short loc_1401DE58B
0x1401de583  mov     rcx, r14; Buffer
0x1401de586  call    GreDeleteFastMutex
0x1401de58b  test    rbx, rbx
0x1401de58e  jz      loc_1401DE37A
0x1401de594  mov     rcx, rbx; Buffer
0x1401de597  call    GreDeleteFastMutex
0x1401de59c  jmp     loc_1401DE37A
0x14023a5db  push    rbp
0x14023a5dd  sub     rsp, 30h
0x14023a5e1  mov     rbp, rdx
0x14023a5e4  mov     rax, [rcx]
0x14023a5e7  mov     ecx, [rax]
0x14023a5e9  mov     [rbp+30h], ecx
0x14023a5ec  mov     ecx, [rbp+30h]
0x14023a5ef  call    SetLastNtError
0x14023a5f4  mov     dword ptr [rbp+38h], 1
0x14023a5fb  mov     eax, [rbp+38h]
0x14023a5fe  add     rsp, 30h
0x14023a602  pop     rbp
0x14023a603  retn
```
