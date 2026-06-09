# NtUserSetManipulationInputTarget

- ea: `0x14012fc10`
- end: `0x14012ff42`
- name: `NtUserSetManipulationInputTarget`
- size: `818`
- prototype: `__int64 __fastcall(unsigned int, void *, unsigned int, void *Src, void *, int)`
- caller_count: `0`
- callee_count: `17`
- tags: ``

## callees

- `0x140012c80`
- `0x140029324`
- `0x140029fe8`
- `0x14002ab14`
- `0x14002ccb4`
- `0x140043810`
- `0x1400757c8`
- `0x1400759e0`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x1400a6854`
- `0x14012fc10`
- `0x1401c6588`
- `0x140238b10`
- `0x140238ba0`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14012fde1`
- `ntoskrnl!ProbeForRead` at `0x14012fde1`
- `ntoskrnl!KeBugCheckEx` at `0x14012fe47`
- `ntoskrnl!KeBugCheckEx` at `0x14012fe47`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14012fc8b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14012fc8b`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14012fdc1`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14012fdc1`
- `ntoskrnl!RtlNtStatusToDosError` at `0x14012fee5`
- `ntoskrnl!RtlNtStatusToDosError` at `0x14012fee5`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14012fc7c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14012fc7c`
- `WIN32K!W32GetUserSessionState` at `0x14012fc6d`
- `WIN32K!W32GetUserSessionState` at `0x14012fe91`
- `WIN32K!W32GetUserSessionState` at `0x14012fc6d`
- `WIN32K!W32GetUserSessionState` at `0x14012fe91`

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
  __int64 v10; // rcx
  __int64 UserSessionState; // rdi
  __int64 v12; // rcx
  struct _W32THREADNONPAGED *CurrentThreadWin32Thread; // rbx
  __int64 v14; // rcx
  __int64 v15; // rcx
  void *v16; // rbx
  __int64 v17; // rcx
  __int64 CurrentProcessWow64Process; // rax
  unsigned __int64 v19; // rcx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  ULONG_PTR BugCheckParameter2[2]; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 (__fastcall *v26)(PVOID); // [rsp+60h] [rbp-1A8h]
  void *v27; // [rsp+68h] [rbp-1A0h]
  _OWORD v28[9]; // [rsp+70h] [rbp-198h] BYREF
  _OWORD v29[9]; // [rsp+100h] [rbp-108h] BYREF

  v7 = a3;
  memset(v29, 0, sizeof(v29));
  UserSessionState = W32GetUserSessionState(v10);
  CurrentThreadWin32Thread = (struct _W32THREADNONPAGED *)PsGetCurrentThreadWin32Thread(v12);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    CurrentThreadWin32Thread);
  v14 = *(_QWORD *)CurrentThreadWin32Thread;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
    *(_BYTE *)(v14 + 1708) = 1;
  *(_QWORD *)(UserSessionState + 16) = v14;
  if ( v14 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  if ( !(unsigned int)IsCurrentProcessDwm() )
  {
    v15 = 5;
LABEL_7:
    LODWORD(v16) = 0;
    UserSetLastError(v15);
    goto LABEL_15;
  }
  if ( !(_DWORD)v7 )
  {
    v15 = 87;
    goto LABEL_7;
  }
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  memset(v28, 0, sizeof(v28));
  RtlCopyFromUser(v28, Srca, 0x90u);
  v29[0] = v28[0];
  v29[1] = v28[1];
  v29[2] = v28[2];
  v29[3] = v28[3];
  v29[4] = v28[4];
  v29[5] = v28[5];
  v29[6] = v28[6];
  v29[7] = v28[7];
  v29[8] = v28[8];
  CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
  ProbeForRead(Src, 4 * v7, CurrentProcessWow64Process != 0 ? 1 : 4);
  v16 = Win32AllocPoolWithQuotaZInitImpl(v19, 4 * v7, 0x6E616D55u);
  v27 = v16;
  if ( v16 )
  {
    if ( v26 != (__int64 (__fastcall *)(PVOID))-1LL )
    {
      BugCheckParameter4 = PtiCurrent();
      KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v16, (ULONG_PTR)BugCheckParameter4);
    }
    v21 = PtiCurrent();
    BugCheckParameter2[0] = *((_QWORD *)v21 + 47);
    *((_QWORD *)v21 + 47) = BugCheckParameter2;
    BugCheckParameter2[1] = (ULONG_PTR)v16;
    v26 = GreDeleteFastMutex;
    RtlCopyVolatileMemory(v16, Src, 4 * v7);
    v23 = W32GetUserSessionState(v22);
    LODWORD(v16) = CTouchProcessor::SetManipulationInputTarget(
                     *(CTouchProcessor **)(v23 + 3208),
                     a1,
                     v7,
                     (unsigned int *)v16,
                     a2,
                     (struct TELEMETRY_POINTER_FRAME_TIMES *)v29,
                     a6);
    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  }
  else
  {
    UserSetLastError(8);
    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  }
LABEL_15:
  UserSessionSwitchLeaveCritWithNonPaged(v17);
  return (int)v16;
}

```

## disassembly

```asm
0x14012fc10  mov     rax, rsp
0x14012fc13  push    rbx
0x14012fc14  push    rsi
0x14012fc15  push    rdi
0x14012fc16  push    r12
0x14012fc18  push    r13
0x14012fc1a  push    r14
0x14012fc1c  push    r15
0x14012fc1e  sub     rsp, 1D0h
0x14012fc25  movaps  xmmword ptr [rax-48h], xmm6
0x14012fc29  movaps  xmmword ptr [rax-58h], xmm7
0x14012fc2d  movaps  xmmword ptr [rax-68h], xmm8
0x14012fc32  mov     rax, cs:__security_cookie
0x14012fc39  xor     rax, rsp
0x14012fc3c  mov     [rsp+208h+var_78], rax
0x14012fc44  mov     r14, r9
0x14012fc47  mov     esi, r8d
0x14012fc4a  mov     r12, rdx
0x14012fc4d  mov     r15d, ecx
0x14012fc50  mov     r13, [rsp+208h+Src]
0x14012fc58  xor     edx, edx; Val
0x14012fc5a  mov     r8d, 90h; Size
0x14012fc60  lea     rcx, [rsp+208h+var_108]; void *
0x14012fc68  call    memset
0x14012fc6d  call    cs:__imp_W32GetUserSessionState
0x14012fc74  nop     dword ptr [rax+rax+00h]
0x14012fc79  mov     rdi, rax
0x14012fc7c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14012fc83  nop     dword ptr [rax+rax+00h]
0x14012fc88  mov     rbx, rax
0x14012fc8b  call    cs:__imp_KeEnterCriticalRegion
0x14012fc92  nop     dword ptr [rax+rax+00h]
0x14012fc97  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x14012fc9a  mov     rcx, [rdi]; struct _FAST_ERESOURCE *
0x14012fc9d  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14012fca2  mov     rcx, [rbx]
0x14012fca5  test    rcx, rcx
0x14012fca8  jz      short loc_14012FCB1
0x14012fcaa  mov     byte ptr [rcx+6ACh], 1
0x14012fcb1  mov     [rdi+10h], rcx
0x14012fcb5  test    rcx, rcx
0x14012fcb8  jz      short loc_14012FCDB
0x14012fcba  lea     rbx, [rdi+4C40h]
0x14012fcc1  mov     rcx, rbx
0x14012fcc4  call    DestroySharedUserCritDeferredUnlockList
0x14012fcc9  lea     rcx, [rbx+38h]
0x14012fccd  call    DestroyDeferredUnlockObjectAssignmentList
0x14012fcd2  lea     rcx, [rbx+28h]
0x14012fcd6  call    DestroyDeferredUnlockObjectAssignmentList
0x14012fcdb  call    ?IsCurrentProcessDwm@@YAHXZ; IsCurrentProcessDwm(void)
0x14012fce0  test    eax, eax
0x14012fce2  jnz     short loc_14012FCF3
0x14012fce4  lea     ecx, [rax+5]
0x14012fce7  xor     ebx, ebx
0x14012fce9  call    UserSetLastError
0x14012fcee  jmp     loc_14012FF03
0x14012fcf3  test    esi, esi
0x14012fcf5  jnz     short loc_14012FCFC
0x14012fcf7  lea     ecx, [rsi+57h]
0x14012fcfa  jmp     short loc_14012FCE7
0x14012fcfc  lea     rcx, [rsp+208h+BugCheckParameter2]
0x14012fd01  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14012fd06  nop
0x14012fd07  mov     ebx, 90h
0x14012fd0c  mov     r8d, ebx; Size
0x14012fd0f  xor     edx, edx; Val
0x14012fd11  lea     rcx, [rsp+208h+var_198]; void *
0x14012fd16  call    memset
0x14012fd1b  mov     r8d, ebx; Size
0x14012fd1e  mov     rdx, r13; Src
0x14012fd21  lea     rcx, [rsp+208h+var_198]; void *
0x14012fd26  call    RtlCopyFromUser
0x14012fd2b  movups  xmm0, [rsp+208h+var_198]
0x14012fd30  movups  xmm1, [rsp+208h+var_188]
0x14012fd38  movups  xmm2, [rsp+208h+var_178]
0x14012fd40  movups  xmm3, [rsp+208h+var_168]
0x14012fd48  movups  xmm4, [rsp+208h+var_158]
0x14012fd50  movups  xmm5, [rsp+208h+var_148]
0x14012fd58  movups  xmm6, [rsp+208h+var_138]
0x14012fd60  movups  xmm7, [rsp+208h+var_128]
0x14012fd68  movups  xmm8, [rsp+208h+var_118]
0x14012fd71  movups  [rsp+208h+var_108], xmm0
0x14012fd79  movups  [rsp+208h+var_F8], xmm1
0x14012fd81  movups  [rsp+208h+var_E8], xmm2
0x14012fd89  movups  [rsp+208h+var_D8], xmm3
0x14012fd91  movups  [rsp+208h+var_C8], xmm4
0x14012fd99  movups  [rsp+208h+var_B8], xmm5
0x14012fda1  movups  [rsp+208h+var_A8], xmm6
0x14012fda9  movups  [rsp+208h+var_98], xmm7
0x14012fdb1  movups  [rsp+208h+var_88], xmm8
0x14012fdba  mov     rdi, rsi
0x14012fdbd  shl     rdi, 2
0x14012fdc1  call    cs:__imp_PsGetCurrentProcessWow64Process
0x14012fdc8  nop     dword ptr [rax+rax+00h]
0x14012fdcd  neg     rax
0x14012fdd0  sbb     r8d, r8d
0x14012fdd3  and     r8d, 0FFFFFFFDh
0x14012fdd7  add     r8d, 4; Alignment
0x14012fddb  mov     rdx, rdi; Length
0x14012fdde  mov     rcx, r14; Address
0x14012fde1  call    cs:__imp_ProbeForRead
0x14012fde8  nop     dword ptr [rax+rax+00h]
0x14012fded  mov     r8d, 6E616D55h; unsigned int
0x14012fdf3  mov     rdx, rdi; unsigned __int64
0x14012fdf6  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14012fdfb  mov     rbx, rax
0x14012fdfe  mov     [rsp+208h+var_1A0], rax
0x14012fe03  test    rax, rax
0x14012fe06  jnz     short loc_14012FE23
0x14012fe08  mov     [rsp+208h+var_1BC], ebx
0x14012fe0c  lea     ecx, [rax+8]
0x14012fe0f  call    UserSetLastError
0x14012fe14  lea     rcx, [rsp+208h+BugCheckParameter2]
0x14012fe19  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x14012fe1e  jmp     loc_14012FF03
0x14012fe23  cmp     [rsp+208h+var_1A8], 0FFFFFFFFFFFFFFFFh
0x14012fe29  jz      short loc_14012FE54
0x14012fe2b  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14012fe30  mov     [rsp+208h+BugCheckParameter4], rax; BugCheckParameter4
0x14012fe35  mov     r9, rbx; BugCheckParameter3
0x14012fe38  lea     r8, [rsp+208h+BugCheckParameter2]; BugCheckParameter2
0x14012fe3d  mov     edx, 12h; BugCheckParameter1
0x14012fe42  mov     ecx, 164h; BugCheckCode
0x14012fe47  call    cs:__imp_KeBugCheckEx
0x14012fe54  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14012fe59  mov     rcx, [rax+178h]
0x14012fe60  mov     [rsp+208h+BugCheckParameter2], rcx
0x14012fe65  lea     rcx, [rsp+208h+BugCheckParameter2]
0x14012fe6a  mov     [rax+178h], rcx
0x14012fe71  mov     [rsp+208h+var_1B0], rbx
0x14012fe76  lea     rax, GreDeleteFastMutex
0x14012fe7d  mov     [rsp+208h+var_1A8], rax
0x14012fe82  mov     r8, rdi; Size
0x14012fe85  mov     rdx, r14; Src
0x14012fe88  mov     rcx, rbx; void *
0x14012fe8b  call    RtlCopyVolatileMemory
0x14012fe90  nop
0x14012fe91  call    cs:__imp_W32GetUserSessionState
0x14012fe98  nop     dword ptr [rax+rax+00h]
0x14012fe9d  mov     ecx, [rsp+208h+arg_28]
0x14012fea4  mov     [rsp+208h+var_1D8], ecx; int
0x14012fea8  lea     rcx, [rsp+208h+var_108]
0x14012feb0  mov     [rsp+208h+var_1E0], rcx; struct TELEMETRY_POINTER_FRAME_TIMES *
0x14012feb5  mov     [rsp+208h+BugCheckParameter4], r12; void *
0x14012feba  mov     r9, rbx; unsigned int *
0x14012febd  mov     r8d, esi; unsigned int
0x14012fec0  mov     edx, r15d; unsigned int
0x14012fec3  mov     rcx, [rax+0C88h]; this
0x14012feca  call    ?SetManipulationInputTarget@CTouchProcessor@@QEAAHIIPEAIPEAXPEAUTELEMETRY_POINTER_FRAME_TIMES@@H@Z; CTouchProcessor::SetManipulationInputTarget(uint,uint,uint *,void *,TELEMETRY_POINTER_FRAME_TIMES *,int)
0x14012fecf  mov     ebx, eax
0x14012fed1  lea     rcx, [rsp+208h+BugCheckParameter2]
0x14012fed6  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x14012fedb  jmp     short loc_14012FF03
0x14012fedd  xor     ebx, ebx
0x14012fedf  mov     [rsp+208h+var_1BC], ebx
0x14012fee3  mov     ecx, eax; Status
0x14012fee5  call    cs:__imp_RtlNtStatusToDosError
0x14012feec  nop     dword ptr [rax+rax+00h]
0x14012fef1  mov     ecx, eax
0x14012fef3  call    UserSetLastError
0x14012fef8  lea     rcx, [rsp+208h+BugCheckParameter2]
0x14012fefd  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x14012ff02  nop
0x14012ff03  call    UserSessionSwitchLeaveCritWithNonPaged
0x14012ff08  movsxd  rax, ebx
0x14012ff0b  mov     rcx, [rsp+208h+var_78]
0x14012ff13  xor     rcx, rsp; StackCookie
0x14012ff16  call    __security_check_cookie
0x14012ff1b  lea     r11, [rsp+208h+var_38]
0x14012ff23  movaps  xmm6, xmmword ptr [r11-10h]
0x14012ff28  movaps  xmm7, xmmword ptr [r11-20h]
0x14012ff2d  movaps  xmm8, xmmword ptr [r11-30h]
0x14012ff32  mov     rsp, r11
0x14012ff35  pop     r15
0x14012ff37  pop     r14
0x14012ff39  pop     r13
0x14012ff3b  pop     r12
0x14012ff3d  pop     rdi
0x14012ff3e  pop     rsi
0x14012ff3f  pop     rbx
0x14012ff40  retn
0x140239d09  push    rbp
0x140239d0b  sub     rsp, 40h
0x140239d0f  mov     rbp, rdx
0x140239d12  mov     rax, [rcx]
0x140239d15  mov     ecx, [rax]
0x140239d17  mov     [rbp+40h], ecx
0x140239d1a  mov     ecx, [rbp+40h]
0x140239d1d  call    SetLastNtError
0x140239d22  mov     dword ptr [rbp+48h], 1
0x140239d29  mov     eax, [rbp+48h]
0x140239d2c  add     rsp, 40h
0x140239d30  pop     rbp
0x140239d31  retn
```
