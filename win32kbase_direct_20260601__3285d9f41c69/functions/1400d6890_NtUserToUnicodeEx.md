# NtUserToUnicodeEx

- ea: `0x1400d6890`
- end: `0x1400d6b7e`
- name: `NtUserToUnicodeEx`
- size: `750`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config`

## callees

- `0x14001bdf0`
- `0x1400325a4`
- `0x140033268`
- `0x140033d94`
- `0x14004c720`
- `0x140076968`
- `0x140076b80`
- `0x140077f50`
- `0x140078090`
- `0x140078120`
- `0x1400d67f0`
- `0x1400d6890`
- `0x1400d6b90`
- `0x140238160`
- `0x1402381f0`
- `0x1402382c0`
- `0x140238800`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400d69c3`
- `ntoskrnl!ProbeForRead` at `0x1400d69c3`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400d69f4`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400d69f4`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6a92`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6a92`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d6933`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d6933`
- `ntoskrnl!ExRaiseStatus` at `0x1400d6a55`
- `ntoskrnl!ExRaiseStatus` at `0x1400d6a55`
- `ntoskrnl!ProbeForWrite` at `0x1400d6a11`
- `ntoskrnl!ProbeForWrite` at `0x1400d6a11`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d6924`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d6924`
- `WIN32K!W32GetUserSessionState` at `0x1400d6915`
- `WIN32K!W32GetUserSessionState` at `0x1400d6915`

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
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 UserSessionState; // r15
  struct _W32THREADNONPAGED *CurrentThreadWin32Thread; // rbx
  __int64 v14; // rcx
  unsigned int v15; // esi
  SIZE_T v16; // r15
  unsigned __int64 v17; // rcx
  __int64 *p_Src; // rbx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v20; // rax
  ULONG_PTR BugCheckParameter2[2]; // [rsp+80h] [rbp-178h] BYREF
  __int64 (__fastcall *v25)(PVOID); // [rsp+90h] [rbp-168h]
  __int64 v26; // [rsp+98h] [rbp-160h]
  __int64 v27; // [rsp+A0h] [rbp-158h]
  __int64 Src; // [rsp+A8h] [rbp-150h] BYREF
  _BYTE v29[256]; // [rsp+B0h] [rbp-148h] BYREF

  v27 = a7;
  memset(v29, 0, sizeof(v29));
  Src = 0;
  v8 = 0;
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  UserSessionState = W32GetUserSessionState(v10, v9, v11);
  CurrentThreadWin32Thread = (struct _W32THREADNONPAGED *)PsGetCurrentThreadWin32Thread();
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    CurrentThreadWin32Thread);
  v14 = *(_QWORD *)CurrentThreadWin32Thread;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
    *(_BYTE *)(v14 + 1708) = 1;
  else
    v14 = 0;
  *(_QWORD *)(UserSessionState + 16) = v14;
  if ( v14 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  PtiCurrent();
  if ( a5 > 0 )
  {
    v26 = 1;
    ProbeForRead(a3, 1u, 1u);
    RtlCopyVolatileMemory(v29, (const void *)a3, 0x100u);
    v16 = 2LL * a5;
    ProbeForWrite(a4, v16, 2u);
    if ( a5 >= 4 )
    {
      p_Src = (__int64 *)Win32AllocPoolWithQuotaZInitImpl(v17, v16, 0x62757355u);
      if ( !p_Src )
        ExRaiseStatus(-1073741801);
      v8 = 1;
      if ( v25 != (__int64 (__fastcall *)(PVOID))-1LL )
      {
        BugCheckParameter4 = PtiCurrent();
        KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)p_Src, (ULONG_PTR)BugCheckParameter4);
      }
      v20 = PtiCurrent();
      BugCheckParameter2[0] = *((_QWORD *)v20 + 47);
      *((_QWORD *)v20 + 47) = BugCheckParameter2;
      BugCheckParameter2[1] = (ULONG_PTR)p_Src;
      v25 = GreDeleteFastMutex;
    }
    else
    {
      p_Src = &Src;
    }
    v15 = xxxToUnicodeEx(a1, a5, 0, a6, v27);
    memmove((void *)a4, p_Src, v16);
    if ( v8 )
      Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  }
  else
  {
    v15 = 0;
    UserSetLastError(87);
  }
  UserSessionSwitchLeaveCritWithNonPaged();
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return v15;
}

```

## disassembly

```asm
0x1400d6890  push    rbx
0x1400d6892  push    rsi
0x1400d6893  push    rdi
0x1400d6894  push    r12
0x1400d6896  push    r13
0x1400d6898  push    r14
0x1400d689a  push    r15
0x1400d689c  sub     rsp, 1C0h
0x1400d68a3  mov     rax, cs:__security_cookie
0x1400d68aa  xor     rax, rsp
0x1400d68ad  mov     [rsp+1F8h+var_48], rax
0x1400d68b5  mov     r13, r8
0x1400d68b8  mov     [rsp+1F8h+var_1B4], edx
0x1400d68bc  mov     [rsp+1F8h+var_1B0], ecx
0x1400d68c0  mov     [rsp+1F8h+Address], r9
0x1400d68c5  movsxd  r12, [rsp+1F8h+arg_20]
0x1400d68cd  mov     rax, [rsp+1F8h+arg_30]
0x1400d68d5  mov     [rsp+1F8h+var_158], rax
0x1400d68dd  xor     edx, edx; Val
0x1400d68df  mov     r8d, 100h; Size
0x1400d68e5  lea     rcx, [rsp+1F8h+var_148]; void *
0x1400d68ed  call    memset
0x1400d68f2  xor     edi, edi
0x1400d68f4  mov     [rsp+1F8h+Src], rdi
0x1400d68fc  mov     [rsp+1F8h+var_188], rdi
0x1400d6901  mov     r14d, edi
0x1400d6904  mov     [rsp+1F8h+var_1B8], edi
0x1400d6908  lea     rcx, [rsp+1F8h+BugCheckParameter2]
0x1400d6910  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400d6915  call    cs:__imp_W32GetUserSessionState
0x1400d691c  nop     dword ptr [rax+rax+00h]
0x1400d6921  mov     r15, rax
0x1400d6924  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400d692b  nop     dword ptr [rax+rax+00h]
0x1400d6930  mov     rbx, rax
0x1400d6933  call    cs:__imp_KeEnterCriticalRegion
0x1400d693a  nop     dword ptr [rax+rax+00h]
0x1400d693f  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400d6942  mov     rcx, [r15]; struct _FAST_ERESOURCE *
0x1400d6945  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400d694a  mov     rcx, [rbx]
0x1400d694d  lea     esi, [rdi+1]
0x1400d6950  test    rcx, rcx
0x1400d6953  jnz     short loc_1400D6959
0x1400d6955  mov     ecx, edi
0x1400d6957  jmp     short loc_1400D6960
0x1400d6959  mov     [rcx+6ACh], sil
0x1400d6960  mov     [r15+10h], rcx
0x1400d6964  test    rcx, rcx
0x1400d6967  jz      short loc_1400D698A
0x1400d6969  lea     rbx, [r15+4C40h]
0x1400d6970  mov     rcx, rbx
0x1400d6973  call    DestroySharedUserCritDeferredUnlockList
0x1400d6978  lea     rcx, [rbx+38h]
0x1400d697c  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d6981  lea     rcx, [rbx+28h]
0x1400d6985  call    DestroyDeferredUnlockObjectAssignmentList
0x1400d698a  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400d698f  test    r12d, r12d
0x1400d6992  jg      short loc_1400D69A5
0x1400d6994  mov     esi, edi
0x1400d6996  mov     ecx, 57h ; 'W'
0x1400d699b  call    UserSetLastError
0x1400d69a0  jmp     loc_1400D6B46
0x1400d69a5  mov     ebx, 100h
0x1400d69aa  mov     [rsp+1F8h+var_160], rbx
0x1400d69b2  mov     [rsp+1F8h+var_160], rsi
0x1400d69ba  mov     r8d, esi; Alignment
0x1400d69bd  mov     rdx, rsi; Length
0x1400d69c0  mov     rcx, r13; Address
0x1400d69c3  call    cs:__imp_ProbeForRead
0x1400d69ca  nop     dword ptr [rax+rax+00h]
0x1400d69cf  mov     r8d, ebx; Size
0x1400d69d2  mov     rdx, r13; Src
0x1400d69d5  lea     rcx, [rsp+1F8h+var_148]; void *
0x1400d69dd  call    RtlCopyVolatileMemory
0x1400d69e2  mov     r15, r12
0x1400d69e5  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400d69ef  cmp     r12, rax
0x1400d69f2  jbe     short loc_1400D6A00
0x1400d69f4  call    cs:__imp_ExRaiseAccessViolation
0x1400d69fb  nop     dword ptr [rax+rax+00h]
0x1400d6a00  add     r15, r15
0x1400d6a03  mov     r8d, 2; Alignment
0x1400d6a09  mov     rdx, r15; Length
0x1400d6a0c  mov     rcx, [rsp+1F8h+Address]; Address
0x1400d6a11  call    cs:__imp_ProbeForWrite
0x1400d6a18  nop     dword ptr [rax+rax+00h]
0x1400d6a1d  cmp     r12d, 4
0x1400d6a21  jge     short loc_1400D6A35
0x1400d6a23  lea     rbx, [rsp+1F8h+Src]
0x1400d6a2b  mov     [rsp+1F8h+var_188], rbx
0x1400d6a30  jmp     loc_1400D6AD9
0x1400d6a35  mov     r8d, 62757355h; unsigned int
0x1400d6a3b  mov     rdx, r15; unsigned __int64
0x1400d6a3e  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400d6a43  mov     rbx, rax
0x1400d6a46  mov     [rsp+1F8h+var_188], rax
0x1400d6a4b  test    rax, rax
0x1400d6a4e  jnz     short loc_1400D6A61
0x1400d6a50  mov     ecx, 0C0000017h; Status
0x1400d6a55  call    cs:__imp_ExRaiseStatus
0x1400d6a61  mov     r14d, esi
0x1400d6a64  mov     [rsp+1F8h+var_1B8], esi
0x1400d6a68  cmp     [rsp+1F8h+var_168], 0FFFFFFFFFFFFFFFFh
0x1400d6a71  jz      short loc_1400D6A9F
0x1400d6a73  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400d6a78  mov     [rsp+1F8h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d6a7d  mov     r9, rbx; BugCheckParameter3
0x1400d6a80  lea     r8, [rsp+1F8h+BugCheckParameter2]; BugCheckParameter2
0x1400d6a88  mov     edx, 12h; BugCheckParameter1
0x1400d6a8d  mov     ecx, 164h; BugCheckCode
0x1400d6a92  call    cs:__imp_KeBugCheckEx
0x1400d6a9f  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400d6aa4  mov     rcx, [rax+178h]
0x1400d6aab  mov     [rsp+1F8h+BugCheckParameter2], rcx
0x1400d6ab3  lea     rcx, [rsp+1F8h+BugCheckParameter2]
0x1400d6abb  mov     [rax+178h], rcx
0x1400d6ac2  mov     [rsp+1F8h+var_170], rbx
0x1400d6aca  lea     rax, GreDeleteFastMutex
0x1400d6ad1  mov     [rsp+1F8h+var_168], rax
0x1400d6ad9  mov     rax, [rsp+1F8h+var_158]
0x1400d6ae1  mov     [rsp+1F8h+var_1C0], rax
0x1400d6ae6  mov     eax, [rsp+1F8h+arg_28]
0x1400d6aed  mov     [rsp+1F8h+var_1C8], eax
0x1400d6af1  mov     [rsp+1F8h+var_1D0], di
0x1400d6af6  mov     dword ptr [rsp+1F8h+BugCheckParameter4], r12d
0x1400d6afb  mov     r9, rbx
0x1400d6afe  lea     r8, [rsp+1F8h+var_148]
0x1400d6b06  mov     edx, [rsp+1F8h+var_1B4]
0x1400d6b0a  mov     ecx, [rsp+1F8h+var_1B0]
0x1400d6b0e  call    xxxToUnicodeEx
0x1400d6b13  mov     esi, eax
0x1400d6b15  mov     rcx, [rsp+1F8h+Address]; void *
0x1400d6b1a  mov     r8, r15; Size
0x1400d6b1d  mov     rdx, rbx; Src
0x1400d6b20  call    memmove
0x1400d6b25  jmp     short loc_1400D6B2E
0x1400d6b27  xor     esi, esi
0x1400d6b29  mov     r14d, [rsp+1F8h+var_1B8]
0x1400d6b2e  test    r14d, r14d
0x1400d6b31  jz      short loc_1400D6B46
0x1400d6b33  xor     edx, edx
0x1400d6b35  lea     rcx, [rsp+1F8h+BugCheckParameter2]; BugCheckParameter2
0x1400d6b3d  call    ?UnlockWorker@?$Win32RawLockedItemBase@UDISPLAYCONFIG_DEVICE_INFO_HEADER@@$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@AEAAX_N0@Z; Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&Win32FreePool(void *),1,1,1>::UnlockWorker(bool,bool)
0x1400d6b42  jmp     short loc_1400D6B46
0x1400d6b44  xor     esi, esi
0x1400d6b46  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400d6b4b  lea     rcx, [rsp+1F8h+BugCheckParameter2]
0x1400d6b53  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400d6b58  mov     eax, esi
0x1400d6b5a  mov     rcx, [rsp+1F8h+var_48]
0x1400d6b62  xor     rcx, rsp; StackCookie
0x1400d6b65  call    __security_check_cookie
0x1400d6b6a  add     rsp, 1C0h
0x1400d6b71  pop     r15
0x1400d6b73  pop     r14
0x1400d6b75  pop     r13
0x1400d6b77  pop     r12
0x1400d6b79  pop     rdi
0x1400d6b7a  pop     rsi
0x1400d6b7b  pop     rbx
0x1400d6b7c  retn
0x14023911d  push    rbp
0x14023911f  sub     rsp, 40h
0x140239123  mov     rbp, rdx
0x140239126  mov     rax, [rcx]
0x140239129  mov     ecx, [rax]
0x14023912b  mov     [rbp+60h], ecx
0x14023912e  mov     ecx, [rbp+60h]
0x140239131  call    SetLastNtError
0x140239136  mov     dword ptr [rbp+68h], 1
0x14023913d  mov     eax, [rbp+68h]
0x140239140  add     rsp, 40h
0x140239144  pop     rbp
0x140239145  retn
0x140239147  push    rbp
0x140239149  sub     rsp, 40h
0x14023914d  mov     rbp, rdx
0x140239150  mov     rax, [rcx]
0x140239153  mov     ecx, [rax]
0x140239155  mov     [rbp+50h], ecx
0x140239158  mov     ecx, [rbp+50h]
0x14023915b  call    SetLastNtError
0x140239160  mov     dword ptr [rbp+58h], 1
0x140239167  mov     eax, [rbp+58h]
0x14023916a  add     rsp, 40h
0x14023916e  pop     rbp
0x14023916f  retn
```
