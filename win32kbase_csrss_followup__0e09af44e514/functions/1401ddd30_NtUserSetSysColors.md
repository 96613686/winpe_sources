# NtUserSetSysColors

- ea: `0x1401ddd30`
- end: `0x1401de041`
- name: `NtUserSetSysColors`
- size: `785`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14001bdf0`
- `0x1400325a4`
- `0x140033268`
- `0x140033364`
- `0x140033d94`
- `0x14004a0d0`
- `0x14004c720`
- `0x1400687c0`
- `0x14006888c`
- `0x140076b80`
- `0x140078090`
- `0x140078120`
- `0x140081ed4`
- `0x14008e150`
- `0x14009009c`
- `0x1401824e4`
- `0x14019061c`
- `0x1401c6dd8`
- `0x1401c7c38`
- `0x1401c7d40`
- `0x1401ddd30`
- `0x1402381f0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401ddee1`
- `ntoskrnl!ProbeForRead` at `0x1401ddf0c`
- `ntoskrnl!ProbeForRead` at `0x1401ddee1`
- `ntoskrnl!ProbeForRead` at `0x1401ddf0c`
- `ntoskrnl!ExRaiseStatus` at `0x1401ddf38`
- `ntoskrnl!ExRaiseStatus` at `0x1401ddf72`
- `ntoskrnl!ExRaiseStatus` at `0x1401ddf38`
- `ntoskrnl!ExRaiseStatus` at `0x1401ddf72`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401ddebd`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401ddeed`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401ddebd`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401ddeed`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401ddf90`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401ddf90`
- `WIN32K!W32GetUserSessionState` at `0x1401ddd70`
- `WIN32K!W32GetUserSessionState` at `0x1401ddd70`

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
  UserSessionState = W32GetUserSessionState(a1);
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
0x1401ddd30  mov     [rsp+arg_0], rbx
0x1401ddd35  mov     [rsp+arg_8], rsi
0x1401ddd3a  mov     [rsp+arg_18], r9d
0x1401ddd3f  push    rdi
0x1401ddd40  push    r12
0x1401ddd42  push    r13
0x1401ddd44  push    r14
0x1401ddd46  push    r15
0x1401ddd48  sub     rsp, 0A0h
0x1401ddd4f  mov     r12, r8
0x1401ddd52  mov     r13, rdx
0x1401ddd55  mov     r15d, ecx
0x1401ddd58  mov     esi, 2000h
0x1401ddd5d  mov     dword ptr [rsp+0C8h+BugCheckParameter2], esi
0x1401ddd61  or      r14d, 0FFFFFFFFh
0x1401ddd65  mov     dword ptr [rsp+0C8h+BugCheckParameter2+4], r14d
0x1401ddd6a  xor     eax, eax
0x1401ddd6c  mov     [rsp+0C8h+var_80], eax
0x1401ddd70  call    cs:__imp_W32GetUserSessionState
0x1401ddd77  nop     dword ptr [rax+rax+00h]
0x1401ddd7c  mov     rbx, rax
0x1401ddd7f  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401ddd86  xor     r8d, r8d
0x1401ddd89  xor     edx, edx
0x1401ddd8b  mov     rcx, rax
0x1401ddd8e  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401ddd93  mov     [rbx+10h], rax
0x1401ddd97  xor     edi, edi
0x1401ddd99  test    rax, rax
0x1401ddd9c  jz      short loc_1401DDDC2
0x1401ddd9e  lea     rcx, [rbx+4C40h]
0x1401ddda5  call    DestroySharedUserCritDeferredUnlockList
0x1401dddaa  lea     rcx, [rbx+4C78h]
0x1401dddb1  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dddb6  lea     rcx, [rbx+4C68h]
0x1401dddbd  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dddc2  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401dddc7  mov     rbx, rax
0x1401dddca  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x1401dddcf  test    eax, eax
0x1401dddd1  jz      short loc_1401DDE51
0x1401dddd3  mov     edx, 8; unsigned int
0x1401dddd8  mov     rcx, [rbx+1C8h]; this
0x1401ddddf  call    ?HasUILimit@tagPROCESSINFO@@QEBA_NK@Z; tagPROCESSINFO::HasUILimit(ulong)
0x1401ddde4  test    al, al
0x1401ddde6  jnz     short loc_1401DDE0E
0x1401ddde8  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x1401ddded  mov     rcx, [rbx+1C8h]
0x1401dddf4  add     rcx, 360h; this
0x1401dddfb  test    eax, eax
0x1401dddfd  jz      short loc_1401DDE40
0x1401dddff  mov     edx, esi; struct tagUIPI_INFO *
0x1401dde01  call    ?HasMinimumIntegrityLevel@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@K@Z; UIPrivilegeIsolation::HasMinimumIntegrityLevel(tagUIPI_INFO const &,ulong)
0x1401dde06  test    al, al
0x1401dde08  jnz     loc_1401DDE9D
0x1401dde0e  mov     esi, edi
0x1401dde10  mov     ecx, 5
0x1401dde15  call    UserSetLastError
0x1401dde1a  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401dde1f  movsxd  rax, esi
0x1401dde22  lea     r11, [rsp+0C8h+var_28]
0x1401dde2a  mov     rbx, [r11+30h]
0x1401dde2e  mov     rsi, [r11+38h]
0x1401dde32  mov     rsp, r11
0x1401dde35  pop     r15
0x1401dde37  pop     r14
0x1401dde39  pop     r13
0x1401dde3b  pop     r12
0x1401dde3d  pop     rdi
0x1401dde3e  retn
0x1401dde40  mov     dword ptr [rsp+0C8h+BugCheckParameter2], esi
0x1401dde44  mov     dword ptr [rsp+0C8h+BugCheckParameter2+4], r14d
0x1401dde49  xor     eax, eax
0x1401dde4b  mov     [rsp+0C8h+var_80], eax
0x1401dde4f  jmp     short loc_1401DDE8B
0x1401dde51  xor     eax, eax
0x1401dde53  lock cmpxchg [rbx+208h], edi
0x1401dde5b  bt      eax, 1Dh
0x1401dde5f  jnb     short loc_1401DDE77
0x1401dde61  mov     rax, [rbx+1C8h]
0x1401dde68  mov     rcx, [rax+2F0h]
0x1401dde6f  mov     eax, [rcx+20h]
0x1401dde72  and     eax, 8
0x1401dde75  jmp     short loc_1401DDE79
0x1401dde77  mov     eax, edi
0x1401dde79  test    eax, eax
0x1401dde7b  jnz     short loc_1401DDE0E
0x1401dde7d  mov     rcx, [rbx+1C8h]
0x1401dde84  add     rcx, 360h
0x1401dde8b  xor     r8d, r8d
0x1401dde8e  lea     rdx, [rsp+0C8h+BugCheckParameter2]
0x1401dde93  call    ?CheckAccessEx@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::CheckAccessEx(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x1401dde98  jmp     loc_1401DDE06
0x1401dde9d  mov     r14, rdi
0x1401ddea0  mov     [rsp+0C8h+Buffer], rdi
0x1401ddea5  mov     rbx, rdi
0x1401ddea8  mov     [rsp+0C8h+var_68], rbx
0x1401ddead  test    r15d, r15d
0x1401ddeb0  jz      loc_1401DDFB1
0x1401ddeb6  mov     rsi, r15
0x1401ddeb9  shl     rsi, 2
0x1401ddebd  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401ddec4  nop     dword ptr [rax+rax+00h]
0x1401ddec9  neg     rax
0x1401ddecc  sbb     r8d, r8d
0x1401ddecf  mov     ebx, 0FFFFFFFDh
0x1401dded4  and     r8d, ebx
0x1401dded7  add     r8d, 4; Alignment
0x1401ddedb  mov     rdx, rsi; Length
0x1401ddede  mov     rcx, r13; Address
0x1401ddee1  call    cs:__imp_ProbeForRead
0x1401ddee8  nop     dword ptr [rax+rax+00h]
0x1401ddeed  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401ddef4  nop     dword ptr [rax+rax+00h]
0x1401ddef9  neg     rax
0x1401ddefc  sbb     r8d, r8d
0x1401ddeff  and     r8d, ebx
0x1401ddf02  add     r8d, 4; Alignment
0x1401ddf06  mov     rdx, rsi; Length
0x1401ddf09  mov     rcx, r12; Address
0x1401ddf0c  call    cs:__imp_ProbeForRead
0x1401ddf13  nop     dword ptr [rax+rax+00h]
0x1401ddf18  mov     r8d, 72637355h; unsigned int
0x1401ddf1e  mov     rdx, rsi; unsigned __int64
0x1401ddf21  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401ddf26  mov     r14, rax
0x1401ddf29  mov     [rsp+0C8h+Buffer], rax
0x1401ddf2e  test    rax, rax
0x1401ddf31  jnz     short loc_1401DDF44
0x1401ddf33  mov     ecx, 0C0000017h; Status
0x1401ddf38  call    cs:__imp_ExRaiseStatus
0x1401ddf44  mov     r8, rsi; Size
0x1401ddf47  mov     rdx, r13; Src
0x1401ddf4a  mov     rcx, rax; void *
0x1401ddf4d  call    RtlCopyVolatileMemory
0x1401ddf52  mov     r8d, 76637355h; unsigned int
0x1401ddf58  mov     rdx, rsi; unsigned __int64
0x1401ddf5b  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401ddf60  mov     rbx, rax
0x1401ddf63  mov     [rsp+0C8h+var_68], rax
0x1401ddf68  test    rax, rax
0x1401ddf6b  jnz     short loc_1401DDF7E
0x1401ddf6d  mov     ecx, 0C0000017h; Status
0x1401ddf72  call    cs:__imp_ExRaiseStatus
0x1401ddf7e  mov     r8, rsi; Size
0x1401ddf81  mov     rdx, r12; Src
0x1401ddf84  mov     rcx, rax; void *
0x1401ddf87  call    RtlCopyVolatileMemory
0x1401ddf8c  jmp     short loc_1401DDFB1
0x1401ddf8e  mov     ecx, eax; Status
0x1401ddf90  call    cs:__imp_RtlNtStatusToDosError
0x1401ddf97  nop     dword ptr [rax+rax+00h]
0x1401ddf9c  xor     esi, esi
0x1401ddf9e  mov     ecx, eax
0x1401ddfa0  call    UserSetLastError
0x1401ddfa5  mov     r14, [rsp+0C8h+Buffer]
0x1401ddfaa  mov     rbx, [rsp+0C8h+var_68]
0x1401ddfaf  jmp     short loc_1401DE01E
0x1401ddfb1  mov     rdx, r14
0x1401ddfb4  lea     rcx, [rsp+0C8h+var_48]
0x1401ddfbc  call    ??0?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@PEAKP6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<ulong,0>::Win32RawLockedItemNoCleanup<ulong,0>(ulong *,void (*)(void *))
0x1401ddfc1  mov     rdx, rbx
0x1401ddfc4  lea     rcx, [rsp+0C8h+var_60]
0x1401ddfc9  call    ??0?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@PEAKP6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<ulong,0>::Win32RawLockedItemNoCleanup<ulong,0>(ulong *,void (*)(void *))
0x1401ddfce  lea     rcx, [rsp+0C8h+BugCheckParameter2]
0x1401ddfd3  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401ddfd8  lea     rcx, [rsp+0C8h+BugCheckParameter2]; BugCheckParameter2
0x1401ddfdd  call    ?CreateProfileUserName@@YAPEAU_UNICODE_STRING@@PEAU?$Win32RawOptionalLockedItemAlways@UtagPROFILEUSERNAME@@$1?Win32FreePool@@YAXPEAX@Z@@@Z; CreateProfileUserName(Win32RawOptionalLockedItemAlways<tagPROFILEUSERNAME,&Win32FreePool(void *)> *)
0x1401ddfe2  mov     eax, [rsp+0C8h+arg_18]
0x1401ddfe9  mov     [rsp+0C8h+var_A8], eax
0x1401ddfed  mov     r9, rbx
0x1401ddff0  mov     r8, r14
0x1401ddff3  mov     edx, r15d
0x1401ddff6  call    xxxSetSysColors
0x1401ddffb  mov     esi, eax
0x1401ddffd  lea     rcx, [rsp+0C8h+BugCheckParameter2]
0x1401de002  call    ??1?$Win32RawOptionalLockedItemAlways@X$1?Win32FreePool@@YAXPEAX@Z@@QEAA@XZ; Win32RawOptionalLockedItemAlways<void,&Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&Win32FreePool(void *)>(void)
0x1401de007  lea     rcx, [rsp+0C8h+var_60]
0x1401de00c  call    ??1?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<ulong,0>::~Win32RawLockedItemNoCleanup<ulong,0>(void)
0x1401de011  lea     rcx, [rsp+0C8h+var_48]
0x1401de019  call    ??1?$Win32RawLockedItemNoCleanup@K$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<ulong,0>::~Win32RawLockedItemNoCleanup<ulong,0>(void)
0x1401de01e  test    r14, r14
0x1401de021  jz      short loc_1401DE02B
0x1401de023  mov     rcx, r14; Buffer
0x1401de026  call    GreDeleteFastMutex
0x1401de02b  test    rbx, rbx
0x1401de02e  jz      loc_1401DDE1A
0x1401de034  mov     rcx, rbx; Buffer
0x1401de037  call    GreDeleteFastMutex
0x1401de03c  jmp     loc_1401DDE1A
0x140239c51  push    rbp
0x140239c53  sub     rsp, 30h
0x140239c57  mov     rbp, rdx
0x140239c5a  mov     rax, [rcx]
0x140239c5d  mov     ecx, [rax]
0x140239c5f  mov     [rbp+30h], ecx
0x140239c62  mov     ecx, [rbp+30h]
0x140239c65  call    SetLastNtError
0x140239c6a  mov     dword ptr [rbp+38h], 1
0x140239c71  mov     eax, [rbp+38h]
0x140239c74  add     rsp, 30h
0x140239c78  pop     rbp
0x140239c79  retn
```
