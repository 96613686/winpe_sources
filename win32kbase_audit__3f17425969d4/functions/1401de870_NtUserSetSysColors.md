# NtUserSetSysColors

- ea: `0x1401de870`
- end: `0x1401deb81`
- name: `NtUserSetSysColors`
- size: `785`
- prototype: `__int64 __fastcall(__int64, volatile void *, volatile void *, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140022c58`
- `0x140022ca0`
- `0x140029710`
- `0x14004dfb0`
- `0x14004f4c0`
- `0x14004f550`
- `0x140059304`
- `0x14006f3a4`
- `0x1400700d8`
- `0x1400701d4`
- `0x140070518`
- `0x14007b930`
- `0x14007df80`
- `0x14009ca40`
- `0x14009e98c`
- `0x140184054`
- `0x140192a2c`
- `0x1401c7d70`
- `0x1401c8bd8`
- `0x1401c8cd0`
- `0x1401de870`
- `0x140238970`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401dea21`
- `ntoskrnl!ProbeForRead` at `0x1401dea4c`
- `ntoskrnl!ProbeForRead` at `0x1401dea21`
- `ntoskrnl!ProbeForRead` at `0x1401dea4c`
- `ntoskrnl!ExRaiseStatus` at `0x1401dea78`
- `ntoskrnl!ExRaiseStatus` at `0x1401deab2`
- `ntoskrnl!ExRaiseStatus` at `0x1401dea78`
- `ntoskrnl!ExRaiseStatus` at `0x1401deab2`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401de9fd`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dea2d`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401de9fd`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dea2d`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401dead0`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401dead0`
- `WIN32K!W32GetUserSessionState` at `0x1401de8b0`
- `WIN32K!W32GetUserSessionState` at `0x1401de8b0`

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
  __int64 v15; // rcx
  int v17; // eax
  void *v18; // r14
  void *v19; // rbx
  __int64 CurrentProcessWow64Process; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // rcx
  void *v23; // rax
  unsigned __int64 v24; // rcx
  void *v25; // rax
  int v26; // ecx
  ULONG_PTR BugCheckParameter2; // [rsp+40h] [rbp-88h] BYREF
  int v28; // [rsp+48h] [rbp-80h]
  PVOID Buffer; // [rsp+58h] [rbp-70h]
  PVOID v30; // [rsp+60h] [rbp-68h]
  _BYTE v31[24]; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v32[32]; // [rsp+80h] [rbp-48h] BYREF

  v6 = (unsigned int)a1;
  BugCheckParameter2 = 0xFFFFFFFF00002000uLL;
  v28 = 0;
  UserSessionState = W32GetUserSessionState(a1, a2);
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
    v28 = 0;
  }
  else
  {
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v9 + 130, 0, 0) & 0x20000000) != 0 )
      v17 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v9 + 57) + 752LL) + 32LL) & 8;
    else
      v17 = 0;
    if ( v17 )
      goto LABEL_8;
    v12 = (UIPrivilegeIsolation *)(*((_QWORD *)v9 + 57) + 864LL);
  }
  HasMinimumIntegrityLevel = UIPrivilegeIsolation::CheckAccessEx(v12, &BugCheckParameter2, 0);
LABEL_7:
  if ( !HasMinimumIntegrityLevel )
    goto LABEL_8;
  v18 = 0;
  Buffer = 0;
  v19 = 0;
  v30 = 0;
  if ( (_DWORD)v6 )
  {
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
    ProbeForRead(a2, 4 * v6, CurrentProcessWow64Process != 0 ? 1 : 4);
    v21 = PsGetCurrentProcessWow64Process();
    ProbeForRead(a3, 4 * v6, v21 != 0 ? 1 : 4);
    v23 = Win32AllocPoolWithQuotaZInitImpl(v22, 4 * v6, 0x72637355u);
    v18 = v23;
    Buffer = v23;
    if ( !v23 )
      ExRaiseStatus(-1073741801);
    RtlCopyVolatileMemory(v23, (const void *)a2, 4 * v6);
    v25 = Win32AllocPoolWithQuotaZInitImpl(v24, 4 * v6, 0x76637355u);
    v19 = v25;
    v30 = v25;
    if ( !v25 )
      ExRaiseStatus(-1073741801);
    RtlCopyVolatileMemory(v25, (const void *)a3, 4 * v6);
  }
  Win32RawLockedItemNoCleanup<unsigned long,0>::Win32RawLockedItemNoCleanup<unsigned long,0>(v32, v18);
  Win32RawLockedItemNoCleanup<unsigned long,0>::Win32RawLockedItemNoCleanup<unsigned long,0>(v31, v19);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(&BugCheckParameter2);
  CreateProfileUserName((ULONG_PTR)&BugCheckParameter2);
  v14 = xxxSetSysColors(v26, v6, (_DWORD)v18, (_DWORD)v19, a4);
  Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>(&BugCheckParameter2);
  Win32RawLockedItemNoCleanup<unsigned long,0>::~Win32RawLockedItemNoCleanup<unsigned long,0>(v31);
  Win32RawLockedItemNoCleanup<unsigned long,0>::~Win32RawLockedItemNoCleanup<unsigned long,0>(v32);
  if ( v18 )
    GreDeleteFastMutex(v18);
  if ( v19 )
    GreDeleteFastMutex(v19);
LABEL_9:
  UserSessionSwitchLeaveCritWithNonPaged(v15);
  return v14;
}

```

## disassembly

```asm
0x1401de870  mov     [rsp+arg_0], rbx
0x1401de875  mov     [rsp+arg_8], rsi
0x1401de87a  mov     [rsp+arg_18], r9d
0x1401de87f  push    rdi
0x1401de880  push    r12
0x1401de882  push    r13
0x1401de884  push    r14
0x1401de886  push    r15
0x1401de888  sub     rsp, 0A0h
0x1401de88f  mov     r12, r8
0x1401de892  mov     r13, rdx
0x1401de895  mov     r15d, ecx
0x1401de898  mov     esi, 2000h
0x1401de89d  mov     dword ptr [rsp+0C8h+BugCheckParameter2], esi
0x1401de8a1  or      r14d, 0FFFFFFFFh
0x1401de8a5  mov     dword ptr [rsp+0C8h+BugCheckParameter2+4], r14d
0x1401de8aa  xor     eax, eax
0x1401de8ac  mov     [rsp+0C8h+var_80], eax
0x1401de8b0  call    cs:__imp_W32GetUserSessionState
0x1401de8b7  nop     dword ptr [rax+rax+00h]
0x1401de8bc  mov     rbx, rax
0x1401de8bf  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401de8c6  xor     r8d, r8d
0x1401de8c9  xor     edx, edx
0x1401de8cb  mov     rcx, rax
0x1401de8ce  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401de8d3  mov     [rbx+10h], rax
0x1401de8d7  xor     edi, edi
0x1401de8d9  test    rax, rax
0x1401de8dc  jz      short loc_1401DE902
0x1401de8de  lea     rcx, [rbx+4C40h]
0x1401de8e5  call    DestroySharedUserCritDeferredUnlockList
0x1401de8ea  lea     rcx, [rbx+4C78h]
0x1401de8f1  call    DestroyDeferredUnlockObjectAssignmentList
0x1401de8f6  lea     rcx, [rbx+4C68h]
0x1401de8fd  call    DestroyDeferredUnlockObjectAssignmentList
0x1401de902  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401de907  mov     rbx, rax
0x1401de90a  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x1401de90f  test    eax, eax
0x1401de911  jz      short loc_1401DE991
0x1401de913  mov     edx, 8; unsigned int
0x1401de918  mov     rcx, [rbx+1C8h]; this
0x1401de91f  call    ?HasUILimit@tagPROCESSINFO@@QEBA_NK@Z; tagPROCESSINFO::HasUILimit(ulong)
0x1401de924  test    al, al
0x1401de926  jnz     short loc_1401DE94E
0x1401de928  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x1401de92d  mov     rcx, [rbx+1C8h]
0x1401de934  add     rcx, 360h; this
0x1401de93b  test    eax, eax
0x1401de93d  jz      short loc_1401DE980
0x1401de93f  mov     edx, esi; struct tagUIPI_INFO *
0x1401de941  call    ?HasMinimumIntegrityLevel@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@K@Z; UIPrivilegeIsolation::HasMinimumIntegrityLevel(tagUIPI_INFO const &,ulong)
0x1401de946  test    al, al
0x1401de948  jnz     loc_1401DE9DD
0x1401de94e  mov     esi, edi
0x1401de950  mov     ecx, 5
0x1401de955  call    UserSetLastError
0x1401de95a  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401de95f  movsxd  rax, esi
0x1401de962  lea     r11, [rsp+0C8h+var_28]
0x1401de96a  mov     rbx, [r11+30h]
0x1401de96e  mov     rsi, [r11+38h]
0x1401de972  mov     rsp, r11
0x1401de975  pop     r15
0x1401de977  pop     r14
0x1401de979  pop     r13
0x1401de97b  pop     r12
0x1401de97d  pop     rdi
0x1401de97e  retn
0x1401de980  mov     dword ptr [rsp+0C8h+BugCheckParameter2], esi
0x1401de984  mov     dword ptr [rsp+0C8h+BugCheckParameter2+4], r14d
0x1401de989  xor     eax, eax
0x1401de98b  mov     [rsp+0C8h+var_80], eax
0x1401de98f  jmp     short loc_1401DE9CB
0x1401de991  xor     eax, eax
0x1401de993  lock cmpxchg [rbx+208h], edi
0x1401de99b  bt      eax, 1Dh
0x1401de99f  jnb     short loc_1401DE9B7
0x1401de9a1  mov     rax, [rbx+1C8h]
0x1401de9a8  mov     rcx, [rax+2F0h]
0x1401de9af  mov     eax, [rcx+20h]
0x1401de9b2  and     eax, 8
0x1401de9b5  jmp     short loc_1401DE9B9
0x1401de9b7  mov     eax, edi
0x1401de9b9  test    eax, eax
0x1401de9bb  jnz     short loc_1401DE94E
0x1401de9bd  mov     rcx, [rbx+1C8h]
0x1401de9c4  add     rcx, 360h
0x1401de9cb  xor     r8d, r8d
0x1401de9ce  lea     rdx, [rsp+0C8h+BugCheckParameter2]
0x1401de9d3  call    ?CheckAccessEx@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::CheckAccessEx(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x1401de9d8  jmp     loc_1401DE946
0x1401de9dd  mov     r14, rdi
0x1401de9e0  mov     [rsp+0C8h+Buffer], rdi
0x1401de9e5  mov     rbx, rdi
0x1401de9e8  mov     [rsp+0C8h+var_68], rbx
0x1401de9ed  test    r15d, r15d
0x1401de9f0  jz      loc_1401DEAF1
0x1401de9f6  mov     rsi, r15
0x1401de9f9  shl     rsi, 2
0x1401de9fd  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dea04  nop     dword ptr [rax+rax+00h]
0x1401dea09  neg     rax
0x1401dea0c  sbb     r8d, r8d
0x1401dea0f  mov     ebx, 0FFFFFFFDh
0x1401dea14  and     r8d, ebx
0x1401dea17  add     r8d, 4; Alignment
0x1401dea1b  mov     rdx, rsi; Length
0x1401dea1e  mov     rcx, r13; Address
0x1401dea21  call    cs:__imp_ProbeForRead
0x1401dea28  nop     dword ptr [rax+rax+00h]
0x1401dea2d  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dea34  nop     dword ptr [rax+rax+00h]
0x1401dea39  neg     rax
0x1401dea3c  sbb     r8d, r8d
0x1401dea3f  and     r8d, ebx
0x1401dea42  add     r8d, 4; Alignment
0x1401dea46  mov     rdx, rsi; Length
0x1401dea49  mov     rcx, r12; Address
0x1401dea4c  call    cs:__imp_ProbeForRead
0x1401dea53  nop     dword ptr [rax+rax+00h]
0x1401dea58  mov     r8d, 72637355h; unsigned int
0x1401dea5e  mov     rdx, rsi; unsigned __int64
0x1401dea61  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401dea66  mov     r14, rax
0x1401dea69  mov     [rsp+0C8h+Buffer], rax
0x1401dea6e  test    rax, rax
0x1401dea71  jnz     short loc_1401DEA84
0x1401dea73  mov     ecx, 0C0000017h; Status
0x1401dea78  call    cs:__imp_ExRaiseStatus
0x1401dea84  mov     r8, rsi; Size
0x1401dea87  mov     rdx, r13; Src
0x1401dea8a  mov     rcx, rax; void *
0x1401dea8d  call    RtlCopyVolatileMemory
0x1401dea92  mov     r8d, 76637355h; unsigned int
0x1401dea98  mov     rdx, rsi; unsigned __int64
0x1401dea9b  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401deaa0  mov     rbx, rax
0x1401deaa3  mov     [rsp+0C8h+var_68], rax
0x1401deaa8  test    rax, rax
0x1401deaab  jnz     short loc_1401DEABE
0x1401deaad  mov     ecx, 0C0000017h; Status
0x1401deab2  call    cs:__imp_ExRaiseStatus
0x1401deabe  mov     r8, rsi; Size
0x1401deac1  mov     rdx, r12; Src
0x1401deac4  mov     rcx, rax; void *
0x1401deac7  call    RtlCopyVolatileMemory
0x1401deacc  jmp     short loc_1401DEAF1
0x1401deace  mov     ecx, eax; Status
0x1401dead0  call    cs:__imp_RtlNtStatusToDosError
0x1401dead7  nop     dword ptr [rax+rax+00h]
0x1401deadc  xor     esi, esi
0x1401deade  mov     ecx, eax
0x1401deae0  call    UserSetLastError
0x1401deae5  mov     r14, [rsp+0C8h+Buffer]
0x1401deaea  mov     rbx, [rsp+0C8h+var_68]
0x1401deaef  jmp     short loc_1401DEB5E
0x1401deaf1  mov     rdx, r14
0x1401deaf4  lea     rcx, [rsp+0C8h+var_48]
0x1401deafc  call    ??0?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@PEAKP6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<ulong,0>::Win32RawLockedItemNoCleanup<ulong,0>(ulong *,void (*)(void *))
0x1401deb01  mov     rdx, rbx
0x1401deb04  lea     rcx, [rsp+0C8h+var_60]
0x1401deb09  call    ??0?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@PEAKP6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<ulong,0>::Win32RawLockedItemNoCleanup<ulong,0>(ulong *,void (*)(void *))
0x1401deb0e  lea     rcx, [rsp+0C8h+BugCheckParameter2]
0x1401deb13  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401deb18  lea     rcx, [rsp+0C8h+BugCheckParameter2]; BugCheckParameter2
0x1401deb1d  call    ?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z; CreateProfileUserName(Win32RawOptionalLockedItemAlways<tagPROFILEUSERNAME,&Win32FreePool(void *)> *)
0x1401deb22  mov     eax, [rsp+0C8h+arg_18]
0x1401deb29  mov     [rsp+0C8h+var_A8], eax
0x1401deb2d  mov     r9, rbx
0x1401deb30  mov     r8, r14
0x1401deb33  mov     edx, r15d
0x1401deb36  call    xxxSetSysColors
0x1401deb3b  mov     esi, eax
0x1401deb3d  lea     rcx, [rsp+0C8h+BugCheckParameter2]
0x1401deb42  call    ??1?$Win32RawOptionalLockedItemAlways@X$1?Win32FreePool@@YAXPEAX@Z@@QEAA@XZ; Win32RawOptionalLockedItemAlways<void,&Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&Win32FreePool(void *)>(void)
0x1401deb47  lea     rcx, [rsp+0C8h+var_60]
0x1401deb4c  call    ??1?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<ulong,0>::~Win32RawLockedItemNoCleanup<ulong,0>(void)
0x1401deb51  lea     rcx, [rsp+0C8h+var_48]
0x1401deb59  call    ??1?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<ulong,0>::~Win32RawLockedItemNoCleanup<ulong,0>(void)
0x1401deb5e  test    r14, r14
0x1401deb61  jz      short loc_1401DEB6B
0x1401deb63  mov     rcx, r14; Buffer
0x1401deb66  call    GreDeleteFastMutex
0x1401deb6b  test    rbx, rbx
0x1401deb6e  jz      loc_1401DE95A
0x1401deb74  mov     rcx, rbx; Buffer
0x1401deb77  call    GreDeleteFastMutex
0x1401deb7c  jmp     loc_1401DE95A
0x14023a3f4  push    rbp
0x14023a3f6  sub     rsp, 30h
0x14023a3fa  mov     rbp, rdx
0x14023a3fd  mov     rax, [rcx]
0x14023a400  mov     ecx, [rax]
0x14023a402  mov     [rbp+30h], ecx
0x14023a405  mov     ecx, [rbp+30h]
0x14023a408  call    SetLastNtError
0x14023a40d  mov     dword ptr [rbp+38h], 1
0x14023a414  mov     eax, [rbp+38h]
0x14023a417  add     rsp, 30h
0x14023a41b  pop     rbp
0x14023a41c  retn
```
