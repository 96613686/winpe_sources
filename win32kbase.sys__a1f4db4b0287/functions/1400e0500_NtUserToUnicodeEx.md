# NtUserToUnicodeEx

- ea: `0x1400e0500`
- end: `0x1400e07ee`
- name: `NtUserToUnicodeEx`
- size: `750`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config`

## callees

- `0x140012c80`
- `0x140029324`
- `0x140029fe8`
- `0x14002ab14`
- `0x140043810`
- `0x1400757c8`
- `0x1400759e0`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x1400e0460`
- `0x1400e0500`
- `0x1400e0800`
- `0x140238b10`
- `0x140238ba0`
- `0x140238c40`
- `0x140239180`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400e0633`
- `ntoskrnl!ProbeForRead` at `0x1400e0633`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400e0664`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400e0664`
- `ntoskrnl!KeBugCheckEx` at `0x1400e0702`
- `ntoskrnl!KeBugCheckEx` at `0x1400e0702`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e05a3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e05a3`
- `ntoskrnl!ExRaiseStatus` at `0x1400e06c5`
- `ntoskrnl!ExRaiseStatus` at `0x1400e06c5`
- `ntoskrnl!ProbeForWrite` at `0x1400e0681`
- `ntoskrnl!ProbeForWrite` at `0x1400e0681`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e0594`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e0594`
- `WIN32K!W32GetUserSessionState` at `0x1400e0585`
- `WIN32K!W32GetUserSessionState` at `0x1400e0585`

## pseudocode

```c
__int64 __fastcall NtUserToUnicodeEx(
        unsigned int a1,
        __int64 a2,
        volatile void *a3,
        volatile void *a4,
        int a5,
        int a6,
        __int64 a7)
{
  int v8; // r14d
  __int64 v9; // rcx
  __int64 UserSessionState; // r15
  struct _W32THREADNONPAGED *CurrentThreadWin32Thread; // rbx
  __int64 v12; // rcx
  unsigned int v13; // esi
  SIZE_T v14; // r15
  unsigned __int64 v15; // rcx
  __int64 *p_Src; // rbx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v18; // rax
  ULONG_PTR BugCheckParameter2[2]; // [rsp+80h] [rbp-178h] BYREF
  __int64 (__fastcall *v23)(PVOID); // [rsp+90h] [rbp-168h]
  __int64 v24; // [rsp+98h] [rbp-160h]
  __int64 v25; // [rsp+A0h] [rbp-158h]
  __int64 Src; // [rsp+A8h] [rbp-150h] BYREF
  _BYTE v27[256]; // [rsp+B0h] [rbp-148h] BYREF

  v25 = a7;
  memset(v27, 0, sizeof(v27));
  Src = 0;
  v8 = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  UserSessionState = W32GetUserSessionState(v9);
  CurrentThreadWin32Thread = (struct _W32THREADNONPAGED *)PsGetCurrentThreadWin32Thread();
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    CurrentThreadWin32Thread);
  v12 = *(_QWORD *)CurrentThreadWin32Thread;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
    *(_BYTE *)(v12 + 1708) = 1;
  else
    v12 = 0;
  *(_QWORD *)(UserSessionState + 16) = v12;
  if ( v12 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  PtiCurrent();
  if ( a5 > 0 )
  {
    v24 = 1;
    ProbeForRead(a3, 1u, 1u);
    RtlCopyVolatileMemory(v27, (const void *)a3, 0x100u);
    v14 = 2LL * a5;
    ProbeForWrite(a4, v14, 2u);
    if ( a5 >= 4 )
    {
      p_Src = (__int64 *)Win32AllocPoolWithQuotaZInitImpl(v15, v14, 0x62757355u);
      if ( !p_Src )
        ExRaiseStatus(-1073741801);
      v8 = 1;
      if ( v23 != (__int64 (__fastcall *)(PVOID))-1LL )
      {
        BugCheckParameter4 = PtiCurrent();
        KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)p_Src, (ULONG_PTR)BugCheckParameter4);
      }
      v18 = PtiCurrent();
      BugCheckParameter2[0] = *((_QWORD *)v18 + 47);
      *((_QWORD *)v18 + 47) = BugCheckParameter2;
      BugCheckParameter2[1] = (ULONG_PTR)p_Src;
      v23 = GreDeleteFastMutex;
    }
    else
    {
      p_Src = &Src;
    }
    v13 = xxxToUnicodeEx(a1, a5, 0, a6, v25);
    memmove((void *)a4, p_Src, v14);
    if ( v8 )
      Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  }
  else
  {
    v13 = 0;
    UserSetLastError(87);
  }
  UserSessionSwitchLeaveCritWithNonPaged();
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return v13;
}

```

## disassembly

```asm
0x1400e0500  push    rbx
0x1400e0502  push    rsi
0x1400e0503  push    rdi
0x1400e0504  push    r12
0x1400e0506  push    r13
0x1400e0508  push    r14
0x1400e050a  push    r15
0x1400e050c  sub     rsp, 1C0h
0x1400e0513  mov     rax, cs:__security_cookie
0x1400e051a  xor     rax, rsp
0x1400e051d  mov     [rsp+1F8h+var_48], rax
0x1400e0525  mov     r13, r8
0x1400e0528  mov     [rsp+1F8h+var_1B4], edx
0x1400e052c  mov     [rsp+1F8h+var_1B0], ecx
0x1400e0530  mov     [rsp+1F8h+Address], r9
0x1400e0535  movsxd  r12, [rsp+1F8h+arg_20]
0x1400e053d  mov     rax, [rsp+1F8h+arg_30]
0x1400e0545  mov     [rsp+1F8h+var_158], rax
0x1400e054d  xor     edx, edx; Val
0x1400e054f  mov     r8d, 100h; Size
0x1400e0555  lea     rcx, [rsp+1F8h+var_148]; void *
0x1400e055d  call    memset
0x1400e0562  xor     edi, edi
0x1400e0564  mov     [rsp+1F8h+Src], rdi
0x1400e056c  mov     [rsp+1F8h+var_188], rdi
0x1400e0571  mov     r14d, edi
0x1400e0574  mov     [rsp+1F8h+var_1B8], edi
0x1400e0578  lea     rcx, [rsp+1F8h+BugCheckParameter2]
0x1400e0580  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400e0585  call    cs:__imp_W32GetUserSessionState
0x1400e058c  nop     dword ptr [rax+rax+00h]
0x1400e0591  mov     r15, rax
0x1400e0594  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e059b  nop     dword ptr [rax+rax+00h]
0x1400e05a0  mov     rbx, rax
0x1400e05a3  call    cs:__imp_KeEnterCriticalRegion
0x1400e05aa  nop     dword ptr [rax+rax+00h]
0x1400e05af  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400e05b2  mov     rcx, [r15]; struct _FAST_ERESOURCE *
0x1400e05b5  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400e05ba  mov     rcx, [rbx]
0x1400e05bd  lea     esi, [rdi+1]
0x1400e05c0  test    rcx, rcx
0x1400e05c3  jnz     short loc_1400E05C9
0x1400e05c5  mov     ecx, edi
0x1400e05c7  jmp     short loc_1400E05D0
0x1400e05c9  mov     [rcx+6ACh], sil
0x1400e05d0  mov     [r15+10h], rcx
0x1400e05d4  test    rcx, rcx
0x1400e05d7  jz      short loc_1400E05FA
0x1400e05d9  lea     rbx, [r15+4C40h]
0x1400e05e0  mov     rcx, rbx
0x1400e05e3  call    DestroySharedUserCritDeferredUnlockList
0x1400e05e8  lea     rcx, [rbx+38h]
0x1400e05ec  call    DestroyDeferredUnlockObjectAssignmentList
0x1400e05f1  lea     rcx, [rbx+28h]
0x1400e05f5  call    DestroyDeferredUnlockObjectAssignmentList
0x1400e05fa  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400e05ff  test    r12d, r12d
0x1400e0602  jg      short loc_1400E0615
0x1400e0604  mov     esi, edi
0x1400e0606  mov     ecx, 57h ; 'W'
0x1400e060b  call    UserSetLastError
0x1400e0610  jmp     loc_1400E07B6
0x1400e0615  mov     ebx, 100h
0x1400e061a  mov     [rsp+1F8h+var_160], rbx
0x1400e0622  mov     [rsp+1F8h+var_160], rsi
0x1400e062a  mov     r8d, esi; Alignment
0x1400e062d  mov     rdx, rsi; Length
0x1400e0630  mov     rcx, r13; Address
0x1400e0633  call    cs:__imp_ProbeForRead
0x1400e063a  nop     dword ptr [rax+rax+00h]
0x1400e063f  mov     r8d, ebx; Size
0x1400e0642  mov     rdx, r13; Src
0x1400e0645  lea     rcx, [rsp+1F8h+var_148]; void *
0x1400e064d  call    RtlCopyVolatileMemory
0x1400e0652  mov     r15, r12
0x1400e0655  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400e065f  cmp     r12, rax
0x1400e0662  jbe     short loc_1400E0670
0x1400e0664  call    cs:__imp_ExRaiseAccessViolation
0x1400e066b  nop     dword ptr [rax+rax+00h]
0x1400e0670  add     r15, r15
0x1400e0673  mov     r8d, 2; Alignment
0x1400e0679  mov     rdx, r15; Length
0x1400e067c  mov     rcx, [rsp+1F8h+Address]; Address
0x1400e0681  call    cs:__imp_ProbeForWrite
0x1400e0688  nop     dword ptr [rax+rax+00h]
0x1400e068d  cmp     r12d, 4
0x1400e0691  jge     short loc_1400E06A5
0x1400e0693  lea     rbx, [rsp+1F8h+Src]
0x1400e069b  mov     [rsp+1F8h+var_188], rbx
0x1400e06a0  jmp     loc_1400E0749
0x1400e06a5  mov     r8d, 62757355h; unsigned int
0x1400e06ab  mov     rdx, r15; unsigned __int64
0x1400e06ae  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400e06b3  mov     rbx, rax
0x1400e06b6  mov     [rsp+1F8h+var_188], rax
0x1400e06bb  test    rax, rax
0x1400e06be  jnz     short loc_1400E06D1
0x1400e06c0  mov     ecx, 0C0000017h; Status
0x1400e06c5  call    cs:__imp_ExRaiseStatus
0x1400e06d1  mov     r14d, esi
0x1400e06d4  mov     [rsp+1F8h+var_1B8], esi
0x1400e06d8  cmp     [rsp+1F8h+var_168], 0FFFFFFFFFFFFFFFFh
0x1400e06e1  jz      short loc_1400E070F
0x1400e06e3  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400e06e8  mov     [rsp+1F8h+BugCheckParameter4], rax; BugCheckParameter4
0x1400e06ed  mov     r9, rbx; BugCheckParameter3
0x1400e06f0  lea     r8, [rsp+1F8h+BugCheckParameter2]; BugCheckParameter2
0x1400e06f8  mov     edx, 12h; BugCheckParameter1
0x1400e06fd  mov     ecx, 164h; BugCheckCode
0x1400e0702  call    cs:__imp_KeBugCheckEx
0x1400e070f  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400e0714  mov     rcx, [rax+178h]
0x1400e071b  mov     [rsp+1F8h+BugCheckParameter2], rcx
0x1400e0723  lea     rcx, [rsp+1F8h+BugCheckParameter2]
0x1400e072b  mov     [rax+178h], rcx
0x1400e0732  mov     [rsp+1F8h+var_170], rbx
0x1400e073a  lea     rax, GreDeleteFastMutex
0x1400e0741  mov     [rsp+1F8h+var_168], rax
0x1400e0749  mov     rax, [rsp+1F8h+var_158]
0x1400e0751  mov     [rsp+1F8h+var_1C0], rax
0x1400e0756  mov     eax, [rsp+1F8h+arg_28]
0x1400e075d  mov     [rsp+1F8h+var_1C8], eax
0x1400e0761  mov     [rsp+1F8h+var_1D0], di
0x1400e0766  mov     dword ptr [rsp+1F8h+BugCheckParameter4], r12d
0x1400e076b  mov     r9, rbx
0x1400e076e  lea     r8, [rsp+1F8h+var_148]
0x1400e0776  mov     edx, [rsp+1F8h+var_1B4]
0x1400e077a  mov     ecx, [rsp+1F8h+var_1B0]
0x1400e077e  call    xxxToUnicodeEx
0x1400e0783  mov     esi, eax
0x1400e0785  mov     rcx, [rsp+1F8h+Address]; void *
0x1400e078a  mov     r8, r15; Size
0x1400e078d  mov     rdx, rbx; Src
0x1400e0790  call    memmove
0x1400e0795  jmp     short loc_1400E079E
0x1400e0797  xor     esi, esi
0x1400e0799  mov     r14d, [rsp+1F8h+var_1B8]
0x1400e079e  test    r14d, r14d
0x1400e07a1  jz      short loc_1400E07B6
0x1400e07a3  xor     edx, edx
0x1400e07a5  lea     rcx, [rsp+1F8h+BugCheckParameter2]; BugCheckParameter2
0x1400e07ad  call    ?UnlockWorker@?$Win32RawLockedItemBase@UDISPLAYCONFIG_DEVICE_INFO_HEADER@@$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@AEAAX_N0@Z; Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&Win32FreePool(void *),1,1,1>::UnlockWorker(bool,bool)
0x1400e07b2  jmp     short loc_1400E07B6
0x1400e07b4  xor     esi, esi
0x1400e07b6  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400e07bb  lea     rcx, [rsp+1F8h+BugCheckParameter2]
0x1400e07c3  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400e07c8  mov     eax, esi
0x1400e07ca  mov     rcx, [rsp+1F8h+var_48]
0x1400e07d2  xor     rcx, rsp; StackCookie
0x1400e07d5  call    __security_check_cookie
0x1400e07da  add     rsp, 1C0h
0x1400e07e1  pop     r15
0x1400e07e3  pop     r14
0x1400e07e5  pop     r13
0x1400e07e7  pop     r12
0x1400e07e9  pop     rdi
0x1400e07ea  pop     rsi
0x1400e07eb  pop     rbx
0x1400e07ec  retn
0x140239ac2  push    rbp
0x140239ac4  sub     rsp, 40h
0x140239ac8  mov     rbp, rdx
0x140239acb  mov     rax, [rcx]
0x140239ace  mov     ecx, [rax]
0x140239ad0  mov     [rbp+60h], ecx
0x140239ad3  mov     ecx, [rbp+60h]
0x140239ad6  call    SetLastNtError
0x140239adb  mov     dword ptr [rbp+68h], 1
0x140239ae2  mov     eax, [rbp+68h]
0x140239ae5  add     rsp, 40h
0x140239ae9  pop     rbp
0x140239aea  retn
0x140239aec  push    rbp
0x140239aee  sub     rsp, 40h
0x140239af2  mov     rbp, rdx
0x140239af5  mov     rax, [rcx]
0x140239af8  mov     ecx, [rax]
0x140239afa  mov     [rbp+50h], ecx
0x140239afd  mov     ecx, [rbp+50h]
0x140239b00  call    SetLastNtError
0x140239b05  mov     dword ptr [rbp+58h], 1
0x140239b0c  mov     eax, [rbp+58h]
0x140239b0f  add     rsp, 40h
0x140239b13  pop     rbp
0x140239b14  retn
```
