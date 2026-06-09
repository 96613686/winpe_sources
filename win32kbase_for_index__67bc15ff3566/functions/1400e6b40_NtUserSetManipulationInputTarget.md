# NtUserSetManipulationInputTarget

- ea: `0x1400e6b40`
- end: `0x1400e6e72`
- name: `NtUserSetManipulationInputTarget`
- size: `818`
- prototype: `__int64 __fastcall(unsigned int, void *, unsigned int, void *Src, void *Srca, int)`
- caller_count: `0`
- callee_count: `17`
- tags: ``

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
- `0x1400d77a4`
- `0x1400e6b40`
- `0x1400e8854`
- `0x1401c7158`
- `0x1402388e0`
- `0x140238970`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400e6d11`
- `ntoskrnl!ProbeForRead` at `0x1400e6d11`
- `ntoskrnl!KeBugCheckEx` at `0x1400e6d77`
- `ntoskrnl!KeBugCheckEx` at `0x1400e6d77`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e6bbb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e6bbb`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400e6cf1`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400e6cf1`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400e6e15`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400e6e15`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e6bac`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e6bac`
- `WIN32K!W32GetUserSessionState` at `0x1400e6b9d`
- `WIN32K!W32GetUserSessionState` at `0x1400e6dc1`
- `WIN32K!W32GetUserSessionState` at `0x1400e6b9d`
- `WIN32K!W32GetUserSessionState` at `0x1400e6dc1`

## pseudocode

```c
__int64 __fastcall NtUserSetManipulationInputTarget(
        unsigned int a1,
        void *a2,
        unsigned int a3,
        void *Src,
        void *Srca,
        int a6)
{
  __int64 v7; // rsi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 UserSessionState; // rdi
  struct _W32THREADNONPAGED *CurrentThreadWin32Thread; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  void *v17; // rbx
  __int64 v18; // rcx
  __int64 CurrentProcessWow64Process; // rax
  unsigned __int64 v20; // rcx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rax
  ULONG_PTR BugCheckParameter2[2]; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 (__fastcall *v29)(PVOID); // [rsp+60h] [rbp-1A8h]
  void *v30; // [rsp+68h] [rbp-1A0h]
  _OWORD v31[9]; // [rsp+70h] [rbp-198h] BYREF
  _OWORD v32[9]; // [rsp+100h] [rbp-108h] BYREF

  v7 = a3;
  memset(v32, 0, sizeof(v32));
  UserSessionState = W32GetUserSessionState(v11, v10, v12);
  CurrentThreadWin32Thread = (struct _W32THREADNONPAGED *)PsGetCurrentThreadWin32Thread();
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    CurrentThreadWin32Thread);
  v15 = *(_QWORD *)CurrentThreadWin32Thread;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
    *(_BYTE *)(v15 + 1708) = 1;
  *(_QWORD *)(UserSessionState + 16) = v15;
  if ( v15 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  if ( !(unsigned int)IsCurrentProcessDwm() )
  {
    v16 = 5;
LABEL_7:
    LODWORD(v17) = 0;
    UserSetLastError(v16);
    goto LABEL_15;
  }
  if ( !(_DWORD)v7 )
  {
    v16 = 87;
    goto LABEL_7;
  }
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  memset(v31, 0, sizeof(v31));
  RtlCopyFromUser(v31, Srca, 0x90u);
  v32[0] = v31[0];
  v32[1] = v31[1];
  v32[2] = v31[2];
  v32[3] = v31[3];
  v32[4] = v31[4];
  v32[5] = v31[5];
  v32[6] = v31[6];
  v32[7] = v31[7];
  v32[8] = v31[8];
  CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
  ProbeForRead(Src, 4 * v7, CurrentProcessWow64Process != 0 ? 1 : 4);
  v17 = Win32AllocPoolWithQuotaZInitImpl(v20, 4 * v7, 0x6E616D55u);
  v30 = v17;
  if ( v17 )
  {
    if ( v29 != (__int64 (__fastcall *)(PVOID))-1LL )
    {
      BugCheckParameter4 = PtiCurrent();
      KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v17, (ULONG_PTR)BugCheckParameter4);
    }
    v22 = PtiCurrent();
    BugCheckParameter2[0] = *((_QWORD *)v22 + 47);
    *((_QWORD *)v22 + 47) = BugCheckParameter2;
    BugCheckParameter2[1] = (ULONG_PTR)v17;
    v29 = GreDeleteFastMutex;
    RtlCopyVolatileMemory(v17, Src, 4 * v7);
    v26 = W32GetUserSessionState(v24, v23, v25);
    LODWORD(v17) = CTouchProcessor::SetManipulationInputTarget(
                     *(CTouchProcessor **)(v26 + 3208),
                     a1,
                     v7,
                     (unsigned int *)v17,
                     a2,
                     (struct TELEMETRY_POINTER_FRAME_TIMES *)v32,
                     a6);
    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  }
  else
  {
    UserSetLastError(8);
    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  }
LABEL_15:
  UserSessionSwitchLeaveCritWithNonPaged(v18);
  return (int)v17;
}

```

## disassembly

```asm
0x1400e6b40  mov     rax, rsp
0x1400e6b43  push    rbx
0x1400e6b44  push    rsi
0x1400e6b45  push    rdi
0x1400e6b46  push    r12
0x1400e6b48  push    r13
0x1400e6b4a  push    r14
0x1400e6b4c  push    r15
0x1400e6b4e  sub     rsp, 1D0h
0x1400e6b55  movaps  xmmword ptr [rax-48h], xmm6
0x1400e6b59  movaps  xmmword ptr [rax-58h], xmm7
0x1400e6b5d  movaps  xmmword ptr [rax-68h], xmm8
0x1400e6b62  mov     rax, cs:__security_cookie
0x1400e6b69  xor     rax, rsp
0x1400e6b6c  mov     [rsp+208h+var_78], rax
0x1400e6b74  mov     r14, r9
0x1400e6b77  mov     esi, r8d
0x1400e6b7a  mov     r12, rdx
0x1400e6b7d  mov     r15d, ecx
0x1400e6b80  mov     r13, [rsp+208h+Src]
0x1400e6b88  xor     edx, edx; Val
0x1400e6b8a  mov     r8d, 90h; Size
0x1400e6b90  lea     rcx, [rsp+208h+var_108]; void *
0x1400e6b98  call    memset
0x1400e6b9d  call    cs:__imp_W32GetUserSessionState
0x1400e6ba4  nop     dword ptr [rax+rax+00h]
0x1400e6ba9  mov     rdi, rax
0x1400e6bac  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e6bb3  nop     dword ptr [rax+rax+00h]
0x1400e6bb8  mov     rbx, rax
0x1400e6bbb  call    cs:__imp_KeEnterCriticalRegion
0x1400e6bc2  nop     dword ptr [rax+rax+00h]
0x1400e6bc7  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400e6bca  mov     rcx, [rdi]; struct _FAST_ERESOURCE *
0x1400e6bcd  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400e6bd2  mov     rcx, [rbx]
0x1400e6bd5  test    rcx, rcx
0x1400e6bd8  jz      short loc_1400E6BE1
0x1400e6bda  mov     byte ptr [rcx+6ACh], 1
0x1400e6be1  mov     [rdi+10h], rcx
0x1400e6be5  test    rcx, rcx
0x1400e6be8  jz      short loc_1400E6C0B
0x1400e6bea  lea     rbx, [rdi+4C40h]
0x1400e6bf1  mov     rcx, rbx
0x1400e6bf4  call    DestroySharedUserCritDeferredUnlockList
0x1400e6bf9  lea     rcx, [rbx+38h]
0x1400e6bfd  call    DestroyDeferredUnlockObjectAssignmentList
0x1400e6c02  lea     rcx, [rbx+28h]
0x1400e6c06  call    DestroyDeferredUnlockObjectAssignmentList
0x1400e6c0b  call    ?IsCurrentProcessDwm@@YAHXZ; IsCurrentProcessDwm(void)
0x1400e6c10  test    eax, eax
0x1400e6c12  jnz     short loc_1400E6C23
0x1400e6c14  lea     ecx, [rax+5]
0x1400e6c17  xor     ebx, ebx
0x1400e6c19  call    UserSetLastError
0x1400e6c1e  jmp     loc_1400E6E33
0x1400e6c23  test    esi, esi
0x1400e6c25  jnz     short loc_1400E6C2C
0x1400e6c27  lea     ecx, [rsi+57h]
0x1400e6c2a  jmp     short loc_1400E6C17
0x1400e6c2c  lea     rcx, [rsp+208h+BugCheckParameter2]
0x1400e6c31  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400e6c36  nop
0x1400e6c37  mov     ebx, 90h
0x1400e6c3c  mov     r8d, ebx; Size
0x1400e6c3f  xor     edx, edx; Val
0x1400e6c41  lea     rcx, [rsp+208h+var_198]; void *
0x1400e6c46  call    memset
0x1400e6c4b  mov     r8d, ebx; Size
0x1400e6c4e  mov     rdx, r13; Src
0x1400e6c51  lea     rcx, [rsp+208h+var_198]; void *
0x1400e6c56  call    RtlCopyFromUser
0x1400e6c5b  movups  xmm0, [rsp+208h+var_198]
0x1400e6c60  movups  xmm1, [rsp+208h+var_188]
0x1400e6c68  movups  xmm2, [rsp+208h+var_178]
0x1400e6c70  movups  xmm3, [rsp+208h+var_168]
0x1400e6c78  movups  xmm4, [rsp+208h+var_158]
0x1400e6c80  movups  xmm5, [rsp+208h+var_148]
0x1400e6c88  movups  xmm6, [rsp+208h+var_138]
0x1400e6c90  movups  xmm7, [rsp+208h+var_128]
0x1400e6c98  movups  xmm8, [rsp+208h+var_118]
0x1400e6ca1  movups  [rsp+208h+var_108], xmm0
0x1400e6ca9  movups  [rsp+208h+var_F8], xmm1
0x1400e6cb1  movups  [rsp+208h+var_E8], xmm2
0x1400e6cb9  movups  [rsp+208h+var_D8], xmm3
0x1400e6cc1  movups  [rsp+208h+var_C8], xmm4
0x1400e6cc9  movups  [rsp+208h+var_B8], xmm5
0x1400e6cd1  movups  [rsp+208h+var_A8], xmm6
0x1400e6cd9  movups  [rsp+208h+var_98], xmm7
0x1400e6ce1  movups  [rsp+208h+var_88], xmm8
0x1400e6cea  mov     rdi, rsi
0x1400e6ced  shl     rdi, 2
0x1400e6cf1  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400e6cf8  nop     dword ptr [rax+rax+00h]
0x1400e6cfd  neg     rax
0x1400e6d00  sbb     r8d, r8d
0x1400e6d03  and     r8d, 0FFFFFFFDh
0x1400e6d07  add     r8d, 4; Alignment
0x1400e6d0b  mov     rdx, rdi; Length
0x1400e6d0e  mov     rcx, r14; Address
0x1400e6d11  call    cs:__imp_ProbeForRead
0x1400e6d18  nop     dword ptr [rax+rax+00h]
0x1400e6d1d  mov     r8d, 6E616D55h; unsigned int
0x1400e6d23  mov     rdx, rdi; unsigned __int64
0x1400e6d26  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400e6d2b  mov     rbx, rax
0x1400e6d2e  mov     [rsp+208h+var_1A0], rax
0x1400e6d33  test    rax, rax
0x1400e6d36  jnz     short loc_1400E6D53
0x1400e6d38  mov     [rsp+208h+var_1BC], ebx
0x1400e6d3c  lea     ecx, [rax+8]
0x1400e6d3f  call    UserSetLastError
0x1400e6d44  lea     rcx, [rsp+208h+BugCheckParameter2]
0x1400e6d49  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400e6d4e  jmp     loc_1400E6E33
0x1400e6d53  cmp     [rsp+208h+var_1A8], 0FFFFFFFFFFFFFFFFh
0x1400e6d59  jz      short loc_1400E6D84
0x1400e6d5b  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400e6d60  mov     [rsp+208h+BugCheckParameter4], rax; BugCheckParameter4
0x1400e6d65  mov     r9, rbx; BugCheckParameter3
0x1400e6d68  lea     r8, [rsp+208h+BugCheckParameter2]; BugCheckParameter2
0x1400e6d6d  mov     edx, 12h; BugCheckParameter1
0x1400e6d72  mov     ecx, 164h; BugCheckCode
0x1400e6d77  call    cs:__imp_KeBugCheckEx
0x1400e6d84  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400e6d89  mov     rcx, [rax+178h]
0x1400e6d90  mov     [rsp+208h+BugCheckParameter2], rcx
0x1400e6d95  lea     rcx, [rsp+208h+BugCheckParameter2]
0x1400e6d9a  mov     [rax+178h], rcx
0x1400e6da1  mov     [rsp+208h+var_1B0], rbx
0x1400e6da6  lea     rax, GreDeleteFastMutex
0x1400e6dad  mov     [rsp+208h+var_1A8], rax
0x1400e6db2  mov     r8, rdi; Size
0x1400e6db5  mov     rdx, r14; Src
0x1400e6db8  mov     rcx, rbx; void *
0x1400e6dbb  call    RtlCopyVolatileMemory
0x1400e6dc0  nop
0x1400e6dc1  call    cs:__imp_W32GetUserSessionState
0x1400e6dc8  nop     dword ptr [rax+rax+00h]
0x1400e6dcd  mov     ecx, [rsp+208h+arg_28]
0x1400e6dd4  mov     [rsp+208h+var_1D8], ecx; int
0x1400e6dd8  lea     rcx, [rsp+208h+var_108]
0x1400e6de0  mov     [rsp+208h+var_1E0], rcx; struct TELEMETRY_POINTER_FRAME_TIMES *
0x1400e6de5  mov     [rsp+208h+BugCheckParameter4], r12; void *
0x1400e6dea  mov     r9, rbx; unsigned int *
0x1400e6ded  mov     r8d, esi; unsigned int
0x1400e6df0  mov     edx, r15d; unsigned int
0x1400e6df3  mov     rcx, [rax+0C88h]; this
0x1400e6dfa  call    ?SetManipulationInputTarget@CTouchProcessor@@QEAAHIIPEAIPEAXPEAUTELEMETRY_POINTER_FRAME_TIMES@@H@Z; CTouchProcessor::SetManipulationInputTarget(uint,uint,uint *,void *,TELEMETRY_POINTER_FRAME_TIMES *,int)
0x1400e6dff  mov     ebx, eax
0x1400e6e01  lea     rcx, [rsp+208h+BugCheckParameter2]
0x1400e6e06  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400e6e0b  jmp     short loc_1400E6E33
0x1400e6e0d  xor     ebx, ebx
0x1400e6e0f  mov     [rsp+208h+var_1BC], ebx
0x1400e6e13  mov     ecx, eax; Status
0x1400e6e15  call    cs:__imp_RtlNtStatusToDosError
0x1400e6e1c  nop     dword ptr [rax+rax+00h]
0x1400e6e21  mov     ecx, eax
0x1400e6e23  call    UserSetLastError
0x1400e6e28  lea     rcx, [rsp+208h+BugCheckParameter2]
0x1400e6e2d  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1400e6e32  nop
0x1400e6e33  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400e6e38  movsxd  rax, ebx
0x1400e6e3b  mov     rcx, [rsp+208h+var_78]
0x1400e6e43  xor     rcx, rsp; StackCookie
0x1400e6e46  call    __security_check_cookie
0x1400e6e4b  lea     r11, [rsp+208h+var_38]
0x1400e6e53  movaps  xmm6, xmmword ptr [r11-10h]
0x1400e6e58  movaps  xmm7, xmmword ptr [r11-20h]
0x1400e6e5d  movaps  xmm8, xmmword ptr [r11-30h]
0x1400e6e62  mov     rsp, r11
0x1400e6e65  pop     r15
0x1400e6e67  pop     r14
0x1400e6e69  pop     r13
0x1400e6e6b  pop     r12
0x1400e6e6d  pop     rdi
0x1400e6e6e  pop     rsi
0x1400e6e6f  pop     rbx
0x1400e6e70  retn
0x14023988a  push    rbp
0x14023988c  sub     rsp, 40h
0x140239890  mov     rbp, rdx
0x140239893  mov     rax, [rcx]
0x140239896  mov     ecx, [rax]
0x140239898  mov     [rbp+40h], ecx
0x14023989b  mov     ecx, [rbp+40h]
0x14023989e  call    SetLastNtError
0x1402398a3  mov     dword ptr [rbp+48h], 1
0x1402398aa  mov     eax, [rbp+48h]
0x1402398ad  add     rsp, 40h
0x1402398b1  pop     rbp
0x1402398b2  retn
```
