# NtUserToUnicodeEx

- ea: `0x1400c9c70`
- end: `0x1400c9f5e`
- name: `NtUserToUnicodeEx`
- size: `750`
- prototype: `__int64 __fastcall(unsigned int, __int64, volatile void *, volatile void *, int, int, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config`

## callees

- `0x140029710`
- `0x14004dd98`
- `0x14004dfb0`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x14006f3a4`
- `0x1400700d8`
- `0x140070518`
- `0x14007df80`
- `0x1400c9b60`
- `0x1400c9c70`
- `0x1400c9f70`
- `0x1402388e0`
- `0x140238970`
- `0x140238a40`
- `0x140238f80`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400c9da3`
- `ntoskrnl!ProbeForRead` at `0x1400c9da3`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400c9dd4`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400c9dd4`
- `ntoskrnl!KeBugCheckEx` at `0x1400c9e72`
- `ntoskrnl!KeBugCheckEx` at `0x1400c9e72`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c9d13`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c9d13`
- `ntoskrnl!ExRaiseStatus` at `0x1400c9e35`
- `ntoskrnl!ExRaiseStatus` at `0x1400c9e35`
- `ntoskrnl!ProbeForWrite` at `0x1400c9df1`
- `ntoskrnl!ProbeForWrite` at `0x1400c9df1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c9d04`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c9d04`
- `WIN32K!W32GetUserSessionState` at `0x1400c9cf5`
- `WIN32K!W32GetUserSessionState` at `0x1400c9cf5`

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
  __int64 UserSessionState; // r15
  struct _W32THREADNONPAGED *CurrentThreadWin32Thread; // rbx
  __int64 v11; // rcx
  unsigned int v12; // esi
  __int64 v13; // rcx
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
  UserSessionState = W32GetUserSessionState();
  CurrentThreadWin32Thread = (struct _W32THREADNONPAGED *)PsGetCurrentThreadWin32Thread();
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    CurrentThreadWin32Thread);
  v11 = *(_QWORD *)CurrentThreadWin32Thread;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
    *(_BYTE *)(v11 + 1708) = 1;
  else
    v11 = 0;
  *(_QWORD *)(UserSessionState + 16) = v11;
  if ( v11 )
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
    v12 = xxxToUnicodeEx(a1, a5, 0, a6, v25);
    memmove((void *)a4, p_Src, v14);
    if ( v8 )
      Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&void Win32FreePool(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  }
  else
  {
    v12 = 0;
    UserSetLastError(87);
  }
  UserSessionSwitchLeaveCritWithNonPaged(v13);
  Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  return v12;
}

```

## disassembly

```asm
0x1400c9c70  push    rbx
0x1400c9c72  push    rsi
0x1400c9c73  push    rdi
0x1400c9c74  push    r12
0x1400c9c76  push    r13
0x1400c9c78  push    r14
0x1400c9c7a  push    r15
0x1400c9c7c  sub     rsp, 1C0h
0x1400c9c83  mov     rax, cs:__security_cookie
0x1400c9c8a  xor     rax, rsp
0x1400c9c8d  mov     [rsp+1F8h+var_48], rax
0x1400c9c95  mov     r13, r8
0x1400c9c98  mov     [rsp+1F8h+var_1B4], edx
0x1400c9c9c  mov     [rsp+1F8h+var_1B0], ecx
0x1400c9ca0  mov     [rsp+1F8h+Address], r9
0x1400c9ca5  movsxd  r12, [rsp+1F8h+arg_20]
0x1400c9cad  mov     rax, [rsp+1F8h+arg_30]
0x1400c9cb5  mov     [rsp+1F8h+var_158], rax
0x1400c9cbd  xor     edx, edx; Val
0x1400c9cbf  mov     r8d, 100h; Size
0x1400c9cc5  lea     rcx, [rsp+1F8h+var_148]; void *
0x1400c9ccd  call    memset
0x1400c9cd2  xor     edi, edi
0x1400c9cd4  mov     [rsp+1F8h+Src], rdi
0x1400c9cdc  mov     [rsp+1F8h+var_188], rdi
0x1400c9ce1  mov     r14d, edi
0x1400c9ce4  mov     [rsp+1F8h+var_1B8], edi
0x1400c9ce8  lea     rcx, [rsp+1F8h+BugCheckParameter2]
0x1400c9cf0  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400c9cf5  call    cs:__imp_W32GetUserSessionState
0x1400c9cfc  nop     dword ptr [rax+rax+00h]
0x1400c9d01  mov     r15, rax
0x1400c9d04  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c9d0b  nop     dword ptr [rax+rax+00h]
0x1400c9d10  mov     rbx, rax
0x1400c9d13  call    cs:__imp_KeEnterCriticalRegion
0x1400c9d1a  nop     dword ptr [rax+rax+00h]
0x1400c9d1f  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400c9d22  mov     rcx, [r15]; struct _FAST_ERESOURCE *
0x1400c9d25  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400c9d2a  mov     rcx, [rbx]
0x1400c9d2d  lea     esi, [rdi+1]
0x1400c9d30  test    rcx, rcx
0x1400c9d33  jnz     short loc_1400C9D39
0x1400c9d35  mov     ecx, edi
0x1400c9d37  jmp     short loc_1400C9D40
0x1400c9d39  mov     [rcx+6ACh], sil
0x1400c9d40  mov     [r15+10h], rcx
0x1400c9d44  test    rcx, rcx
0x1400c9d47  jz      short loc_1400C9D6A
0x1400c9d49  lea     rbx, [r15+4C40h]
0x1400c9d50  mov     rcx, rbx
0x1400c9d53  call    DestroySharedUserCritDeferredUnlockList
0x1400c9d58  lea     rcx, [rbx+38h]
0x1400c9d5c  call    DestroyDeferredUnlockObjectAssignmentList
0x1400c9d61  lea     rcx, [rbx+28h]
0x1400c9d65  call    DestroyDeferredUnlockObjectAssignmentList
0x1400c9d6a  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400c9d6f  test    r12d, r12d
0x1400c9d72  jg      short loc_1400C9D85
0x1400c9d74  mov     esi, edi
0x1400c9d76  mov     ecx, 57h ; 'W'
0x1400c9d7b  call    UserSetLastError
0x1400c9d80  jmp     loc_1400C9F26
0x1400c9d85  mov     ebx, 100h
0x1400c9d8a  mov     [rsp+1F8h+var_160], rbx
0x1400c9d92  mov     [rsp+1F8h+var_160], rsi
0x1400c9d9a  mov     r8d, esi; Alignment
0x1400c9d9d  mov     rdx, rsi; Length
0x1400c9da0  mov     rcx, r13; Address
0x1400c9da3  call    cs:__imp_ProbeForRead
0x1400c9daa  nop     dword ptr [rax+rax+00h]
0x1400c9daf  mov     r8d, ebx; Size
0x1400c9db2  mov     rdx, r13; Src
0x1400c9db5  lea     rcx, [rsp+1F8h+var_148]; void *
0x1400c9dbd  call    RtlCopyVolatileMemory
0x1400c9dc2  mov     r15, r12
0x1400c9dc5  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400c9dcf  cmp     r12, rax
0x1400c9dd2  jbe     short loc_1400C9DE0
0x1400c9dd4  call    cs:__imp_ExRaiseAccessViolation
0x1400c9ddb  nop     dword ptr [rax+rax+00h]
0x1400c9de0  add     r15, r15
0x1400c9de3  mov     r8d, 2; Alignment
0x1400c9de9  mov     rdx, r15; Length
0x1400c9dec  mov     rcx, [rsp+1F8h+Address]; Address
0x1400c9df1  call    cs:__imp_ProbeForWrite
0x1400c9df8  nop     dword ptr [rax+rax+00h]
0x1400c9dfd  cmp     r12d, 4
0x1400c9e01  jge     short loc_1400C9E15
0x1400c9e03  lea     rbx, [rsp+1F8h+Src]
0x1400c9e0b  mov     [rsp+1F8h+var_188], rbx
0x1400c9e10  jmp     loc_1400C9EB9
0x1400c9e15  mov     r8d, 62757355h; unsigned int
0x1400c9e1b  mov     rdx, r15; unsigned __int64
0x1400c9e1e  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400c9e23  mov     rbx, rax
0x1400c9e26  mov     [rsp+1F8h+var_188], rax
0x1400c9e2b  test    rax, rax
0x1400c9e2e  jnz     short loc_1400C9E41
0x1400c9e30  mov     ecx, 0C0000017h; Status
0x1400c9e35  call    cs:__imp_ExRaiseStatus
0x1400c9e41  mov     r14d, esi
0x1400c9e44  mov     [rsp+1F8h+var_1B8], esi
0x1400c9e48  cmp     [rsp+1F8h+var_168], 0FFFFFFFFFFFFFFFFh
0x1400c9e51  jz      short loc_1400C9E7F
0x1400c9e53  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400c9e58  mov     [rsp+1F8h+BugCheckParameter4], rax; BugCheckParameter4
0x1400c9e5d  mov     r9, rbx; BugCheckParameter3
0x1400c9e60  lea     r8, [rsp+1F8h+BugCheckParameter2]; BugCheckParameter2
0x1400c9e68  mov     edx, 12h; BugCheckParameter1
0x1400c9e6d  mov     ecx, 164h; BugCheckCode
0x1400c9e72  call    cs:__imp_KeBugCheckEx
0x1400c9e7f  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400c9e84  mov     rcx, [rax+178h]
0x1400c9e8b  mov     [rsp+1F8h+BugCheckParameter2], rcx
0x1400c9e93  lea     rcx, [rsp+1F8h+BugCheckParameter2]
0x1400c9e9b  mov     [rax+178h], rcx
0x1400c9ea2  mov     [rsp+1F8h+var_170], rbx
0x1400c9eaa  lea     rax, GreDeleteFastMutex
0x1400c9eb1  mov     [rsp+1F8h+var_168], rax
0x1400c9eb9  mov     rax, [rsp+1F8h+var_158]
0x1400c9ec1  mov     [rsp+1F8h+var_1C0], rax
0x1400c9ec6  mov     eax, [rsp+1F8h+arg_28]
0x1400c9ecd  mov     [rsp+1F8h+var_1C8], eax
0x1400c9ed1  mov     [rsp+1F8h+var_1D0], di
0x1400c9ed6  mov     dword ptr [rsp+1F8h+BugCheckParameter4], r12d
0x1400c9edb  mov     r9, rbx
0x1400c9ede  lea     r8, [rsp+1F8h+var_148]
0x1400c9ee6  mov     edx, [rsp+1F8h+var_1B4]
0x1400c9eea  mov     ecx, [rsp+1F8h+var_1B0]
0x1400c9eee  call    xxxToUnicodeEx
0x1400c9ef3  mov     esi, eax
0x1400c9ef5  mov     rcx, [rsp+1F8h+Address]; void *
0x1400c9efa  mov     r8, r15; Size
0x1400c9efd  mov     rdx, rbx; Src
0x1400c9f00  call    memmove
0x1400c9f05  jmp     short loc_1400C9F0E
0x1400c9f07  xor     esi, esi
0x1400c9f09  mov     r14d, [rsp+1F8h+var_1B8]
0x1400c9f0e  test    r14d, r14d
0x1400c9f11  jz      short loc_1400C9F26
0x1400c9f13  xor     edx, edx
0x1400c9f15  lea     rcx, [rsp+1F8h+BugCheckParameter2]; BugCheckParameter2
0x1400c9f1d  call    ?UnlockWorker@?$Win32RawLockedItemBase@UDISPLAYCONFIG_DEVICE_INFO_HEADER@@$1?Win32FreePool@@YAXPEAX@Z$00$00$00@@AEAAX_N0@Z; Win32RawLockedItemBase<DISPLAYCONFIG_DEVICE_INFO_HEADER,&Win32FreePool(void *),1,1,1>::UnlockWorker(bool,bool)
0x1400c9f22  jmp     short loc_1400C9F26
0x1400c9f24  xor     esi, esi
0x1400c9f26  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400c9f2b  lea     rcx, [rsp+1F8h+BugCheckParameter2]
0x1400c9f33  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400c9f38  mov     eax, esi
0x1400c9f3a  mov     rcx, [rsp+1F8h+var_48]
0x1400c9f42  xor     rcx, rsp; StackCookie
0x1400c9f45  call    __security_check_cookie
0x1400c9f4a  add     rsp, 1C0h
0x1400c9f51  pop     r15
0x1400c9f53  pop     r14
0x1400c9f55  pop     r13
0x1400c9f57  pop     r12
0x1400c9f59  pop     rdi
0x1400c9f5a  pop     rsi
0x1400c9f5b  pop     rbx
0x1400c9f5c  retn
0x140239701  push    rbp
0x140239703  sub     rsp, 40h
0x140239707  mov     rbp, rdx
0x14023970a  mov     rax, [rcx]
0x14023970d  mov     ecx, [rax]
0x14023970f  mov     [rbp+60h], ecx
0x140239712  mov     ecx, [rbp+60h]
0x140239715  call    SetLastNtError
0x14023971a  mov     dword ptr [rbp+68h], 1
0x140239721  mov     eax, [rbp+68h]
0x140239724  add     rsp, 40h
0x140239728  pop     rbp
0x140239729  retn
0x14023972b  push    rbp
0x14023972d  sub     rsp, 40h
0x140239731  mov     rbp, rdx
0x140239734  mov     rax, [rcx]
0x140239737  mov     ecx, [rax]
0x140239739  mov     [rbp+50h], ecx
0x14023973c  mov     ecx, [rbp+50h]
0x14023973f  call    SetLastNtError
0x140239744  mov     dword ptr [rbp+58h], 1
0x14023974b  mov     eax, [rbp+58h]
0x14023974e  add     rsp, 40h
0x140239752  pop     rbp
0x140239753  retn
```
