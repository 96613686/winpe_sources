# NtUserSetManipulationInputTarget

- ea: `0x1401301f0`
- end: `0x140130522`
- name: `NtUserSetManipulationInputTarget`
- size: `818`
- prototype: `__int64 __fastcall(unsigned int, void *, unsigned int, void *Src, void *, int)`
- caller_count: `0`
- callee_count: `17`
- tags: ``

## callees

- `0x14001bdf0`
- `0x1400325a4`
- `0x140033268`
- `0x140033d94`
- `0x140035f34`
- `0x14004c720`
- `0x140076968`
- `0x140076b80`
- `0x140077f50`
- `0x140078090`
- `0x140078120`
- `0x14009d654`
- `0x1401301f0`
- `0x1401c6028`
- `0x140238160`
- `0x1402381f0`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401303c1`
- `ntoskrnl!ProbeForRead` at `0x1401303c1`
- `ntoskrnl!KeBugCheckEx` at `0x140130427`
- `ntoskrnl!KeBugCheckEx` at `0x140130427`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14013026b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14013026b`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401303a1`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401303a1`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401304c5`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1401304c5`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14013025c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14013025c`
- `WIN32K!W32GetUserSessionState` at `0x14013024d`
- `WIN32K!W32GetUserSessionState` at `0x140130471`
- `WIN32K!W32GetUserSessionState` at `0x14013024d`
- `WIN32K!W32GetUserSessionState` at `0x140130471`

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
  __int64 v14; // rcx
  struct _W32THREADNONPAGED *CurrentThreadWin32Thread; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 CurrentProcessWow64Process; // rax
  unsigned __int64 v23; // rcx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rax
  ULONG_PTR BugCheckParameter2[2]; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 (__fastcall *v32)(PVOID); // [rsp+60h] [rbp-1A8h]
  void *v33; // [rsp+68h] [rbp-1A0h]
  _OWORD v34[9]; // [rsp+70h] [rbp-198h] BYREF
  _OWORD v35[9]; // [rsp+100h] [rbp-108h] BYREF

  v7 = a3;
  memset(v35, 0, sizeof(v35));
  UserSessionState = W32GetUserSessionState(v11, v10, v12);
  CurrentThreadWin32Thread = (struct _W32THREADNONPAGED *)PsGetCurrentThreadWin32Thread(v14);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    CurrentThreadWin32Thread);
  v16 = *(_QWORD *)CurrentThreadWin32Thread;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
    *(_BYTE *)(v16 + 1708) = 1;
  *(_QWORD *)(UserSessionState + 16) = v16;
  if ( v16 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  if ( !(unsigned int)IsCurrentProcessDwm() )
  {
    v17 = 5;
LABEL_7:
    LODWORD(v18) = 0;
    UserSetLastError(v17);
    goto LABEL_15;
  }
  if ( !(_DWORD)v7 )
  {
    v17 = 87;
    goto LABEL_7;
  }
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  memset(v34, 0, sizeof(v34));
  RtlCopyFromUser(v34, Srca, 0x90u);
  v35[0] = v34[0];
  v35[1] = v34[1];
  v35[2] = v34[2];
  v35[3] = v34[3];
  v35[4] = v34[4];
  v35[5] = v34[5];
  v35[6] = v34[6];
  v35[7] = v34[7];
  v35[8] = v34[8];
  CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
  ProbeForRead(Src, 4 * v7, CurrentProcessWow64Process != 0 ? 1 : 4);
  v18 = Win32AllocPoolWithQuotaZInitImpl(v23, 4 * v7, 0x6E616D55u);
  v33 = v18;
  if ( v18 )
  {
    if ( v32 != (__int64 (__fastcall *)(PVOID))-1LL )
    {
      BugCheckParameter4 = PtiCurrent();
      KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v18, (ULONG_PTR)BugCheckParameter4);
    }
    v25 = PtiCurrent();
    BugCheckParameter2[0] = *((_QWORD *)v25 + 47);
    *((_QWORD *)v25 + 47) = BugCheckParameter2;
    BugCheckParameter2[1] = (ULONG_PTR)v18;
    v32 = GreDeleteFastMutex;
    RtlCopyVolatileMemory(v18, Src, 4 * v7);
    v29 = W32GetUserSessionState(v27, v26, v28);
    LODWORD(v18) = CTouchProcessor::SetManipulationInputTarget(
                     *(CTouchProcessor **)(v29 + 3208),
                     a1,
                     v7,
                     (unsigned int *)v18,
                     a2,
                     (struct TELEMETRY_POINTER_FRAME_TIMES *)v35,
                     a6);
    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  }
  else
  {
    UserSetLastError(8);
    Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  }
LABEL_15:
  UserSessionSwitchLeaveCritWithNonPaged(v20, v19, v21);
  return (int)v18;
}

```

## disassembly

```asm
0x1401301f0  mov     rax, rsp
0x1401301f3  push    rbx
0x1401301f4  push    rsi
0x1401301f5  push    rdi
0x1401301f6  push    r12
0x1401301f8  push    r13
0x1401301fa  push    r14
0x1401301fc  push    r15
0x1401301fe  sub     rsp, 1D0h
0x140130205  movaps  xmmword ptr [rax-48h], xmm6
0x140130209  movaps  xmmword ptr [rax-58h], xmm7
0x14013020d  movaps  xmmword ptr [rax-68h], xmm8
0x140130212  mov     rax, cs:__security_cookie
0x140130219  xor     rax, rsp
0x14013021c  mov     [rsp+208h+var_78], rax
0x140130224  mov     r14, r9
0x140130227  mov     esi, r8d
0x14013022a  mov     r12, rdx
0x14013022d  mov     r15d, ecx
0x140130230  mov     r13, [rsp+208h+Src]
0x140130238  xor     edx, edx; Val
0x14013023a  mov     r8d, 90h; Size
0x140130240  lea     rcx, [rsp+208h+var_108]; void *
0x140130248  call    memset
0x14013024d  call    cs:__imp_W32GetUserSessionState
0x140130254  nop     dword ptr [rax+rax+00h]
0x140130259  mov     rdi, rax
0x14013025c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140130263  nop     dword ptr [rax+rax+00h]
0x140130268  mov     rbx, rax
0x14013026b  call    cs:__imp_KeEnterCriticalRegion
0x140130272  nop     dword ptr [rax+rax+00h]
0x140130277  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x14013027a  mov     rcx, [rdi]; struct _FAST_ERESOURCE *
0x14013027d  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x140130282  mov     rcx, [rbx]
0x140130285  test    rcx, rcx
0x140130288  jz      short loc_140130291
0x14013028a  mov     byte ptr [rcx+6ACh], 1
0x140130291  mov     [rdi+10h], rcx
0x140130295  test    rcx, rcx
0x140130298  jz      short loc_1401302BB
0x14013029a  lea     rbx, [rdi+4C40h]
0x1401302a1  mov     rcx, rbx
0x1401302a4  call    DestroySharedUserCritDeferredUnlockList
0x1401302a9  lea     rcx, [rbx+38h]
0x1401302ad  call    DestroyDeferredUnlockObjectAssignmentList
0x1401302b2  lea     rcx, [rbx+28h]
0x1401302b6  call    DestroyDeferredUnlockObjectAssignmentList
0x1401302bb  call    ?IsCurrentProcessDwm@@YAHXZ; IsCurrentProcessDwm(void)
0x1401302c0  test    eax, eax
0x1401302c2  jnz     short loc_1401302D3
0x1401302c4  lea     ecx, [rax+5]
0x1401302c7  xor     ebx, ebx
0x1401302c9  call    UserSetLastError
0x1401302ce  jmp     loc_1401304E3
0x1401302d3  test    esi, esi
0x1401302d5  jnz     short loc_1401302DC
0x1401302d7  lea     ecx, [rsi+57h]
0x1401302da  jmp     short loc_1401302C7
0x1401302dc  lea     rcx, [rsp+208h+BugCheckParameter2]
0x1401302e1  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401302e6  nop
0x1401302e7  mov     ebx, 90h
0x1401302ec  mov     r8d, ebx; Size
0x1401302ef  xor     edx, edx; Val
0x1401302f1  lea     rcx, [rsp+208h+var_198]; void *
0x1401302f6  call    memset
0x1401302fb  mov     r8d, ebx; Size
0x1401302fe  mov     rdx, r13; Src
0x140130301  lea     rcx, [rsp+208h+var_198]; void *
0x140130306  call    RtlCopyFromUser
0x14013030b  movups  xmm0, [rsp+208h+var_198]
0x140130310  movups  xmm1, [rsp+208h+var_188]
0x140130318  movups  xmm2, [rsp+208h+var_178]
0x140130320  movups  xmm3, [rsp+208h+var_168]
0x140130328  movups  xmm4, [rsp+208h+var_158]
0x140130330  movups  xmm5, [rsp+208h+var_148]
0x140130338  movups  xmm6, [rsp+208h+var_138]
0x140130340  movups  xmm7, [rsp+208h+var_128]
0x140130348  movups  xmm8, [rsp+208h+var_118]
0x140130351  movups  [rsp+208h+var_108], xmm0
0x140130359  movups  [rsp+208h+var_F8], xmm1
0x140130361  movups  [rsp+208h+var_E8], xmm2
0x140130369  movups  [rsp+208h+var_D8], xmm3
0x140130371  movups  [rsp+208h+var_C8], xmm4
0x140130379  movups  [rsp+208h+var_B8], xmm5
0x140130381  movups  [rsp+208h+var_A8], xmm6
0x140130389  movups  [rsp+208h+var_98], xmm7
0x140130391  movups  [rsp+208h+var_88], xmm8
0x14013039a  mov     rdi, rsi
0x14013039d  shl     rdi, 2
0x1401303a1  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401303a8  nop     dword ptr [rax+rax+00h]
0x1401303ad  neg     rax
0x1401303b0  sbb     r8d, r8d
0x1401303b3  and     r8d, 0FFFFFFFDh
0x1401303b7  add     r8d, 4; Alignment
0x1401303bb  mov     rdx, rdi; Length
0x1401303be  mov     rcx, r14; Address
0x1401303c1  call    cs:__imp_ProbeForRead
0x1401303c8  nop     dword ptr [rax+rax+00h]
0x1401303cd  mov     r8d, 6E616D55h; unsigned int
0x1401303d3  mov     rdx, rdi; unsigned __int64
0x1401303d6  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401303db  mov     rbx, rax
0x1401303de  mov     [rsp+208h+var_1A0], rax
0x1401303e3  test    rax, rax
0x1401303e6  jnz     short loc_140130403
0x1401303e8  mov     [rsp+208h+var_1BC], ebx
0x1401303ec  lea     ecx, [rax+8]
0x1401303ef  call    UserSetLastError
0x1401303f4  lea     rcx, [rsp+208h+BugCheckParameter2]
0x1401303f9  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401303fe  jmp     loc_1401304E3
0x140130403  cmp     [rsp+208h+var_1A8], 0FFFFFFFFFFFFFFFFh
0x140130409  jz      short loc_140130434
0x14013040b  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140130410  mov     [rsp+208h+BugCheckParameter4], rax; BugCheckParameter4
0x140130415  mov     r9, rbx; BugCheckParameter3
0x140130418  lea     r8, [rsp+208h+BugCheckParameter2]; BugCheckParameter2
0x14013041d  mov     edx, 12h; BugCheckParameter1
0x140130422  mov     ecx, 164h; BugCheckCode
0x140130427  call    cs:__imp_KeBugCheckEx
0x140130434  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140130439  mov     rcx, [rax+178h]
0x140130440  mov     [rsp+208h+BugCheckParameter2], rcx
0x140130445  lea     rcx, [rsp+208h+BugCheckParameter2]
0x14013044a  mov     [rax+178h], rcx
0x140130451  mov     [rsp+208h+var_1B0], rbx
0x140130456  lea     rax, GreDeleteFastMutex
0x14013045d  mov     [rsp+208h+var_1A8], rax
0x140130462  mov     r8, rdi; Size
0x140130465  mov     rdx, r14; Src
0x140130468  mov     rcx, rbx; void *
0x14013046b  call    RtlCopyVolatileMemory
0x140130470  nop
0x140130471  call    cs:__imp_W32GetUserSessionState
0x140130478  nop     dword ptr [rax+rax+00h]
0x14013047d  mov     ecx, [rsp+208h+arg_28]
0x140130484  mov     [rsp+208h+var_1D8], ecx; int
0x140130488  lea     rcx, [rsp+208h+var_108]
0x140130490  mov     [rsp+208h+var_1E0], rcx; struct TELEMETRY_POINTER_FRAME_TIMES *
0x140130495  mov     [rsp+208h+BugCheckParameter4], r12; void *
0x14013049a  mov     r9, rbx; unsigned int *
0x14013049d  mov     r8d, esi; unsigned int
0x1401304a0  mov     edx, r15d; unsigned int
0x1401304a3  mov     rcx, [rax+0C88h]; this
0x1401304aa  call    ?SetManipulationInputTarget@CTouchProcessor@@QEAAHIIPEAIPEAXPEAUTELEMETRY_POINTER_FRAME_TIMES@@H@Z; CTouchProcessor::SetManipulationInputTarget(uint,uint,uint *,void *,TELEMETRY_POINTER_FRAME_TIMES *,int)
0x1401304af  mov     ebx, eax
0x1401304b1  lea     rcx, [rsp+208h+BugCheckParameter2]
0x1401304b6  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401304bb  jmp     short loc_1401304E3
0x1401304bd  xor     ebx, ebx
0x1401304bf  mov     [rsp+208h+var_1BC], ebx
0x1401304c3  mov     ecx, eax; Status
0x1401304c5  call    cs:__imp_RtlNtStatusToDosError
0x1401304cc  nop     dword ptr [rax+rax+00h]
0x1401304d1  mov     ecx, eax
0x1401304d3  call    UserSetLastError
0x1401304d8  lea     rcx, [rsp+208h+BugCheckParameter2]
0x1401304dd  call    ??1?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::~Win32RawLockedNtObject<tagDESKTOP>(void)
0x1401304e2  nop
0x1401304e3  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401304e8  movsxd  rax, ebx
0x1401304eb  mov     rcx, [rsp+208h+var_78]
0x1401304f3  xor     rcx, rsp; StackCookie
0x1401304f6  call    __security_check_cookie
0x1401304fb  lea     r11, [rsp+208h+var_38]
0x140130503  movaps  xmm6, xmmword ptr [r11-10h]
0x140130508  movaps  xmm7, xmmword ptr [r11-20h]
0x14013050d  movaps  xmm8, xmmword ptr [r11-30h]
0x140130512  mov     rsp, r11
0x140130515  pop     r15
0x140130517  pop     r14
0x140130519  pop     r13
0x14013051b  pop     r12
0x14013051d  pop     rdi
0x14013051e  pop     rsi
0x14013051f  pop     rbx
0x140130520  retn
0x140239364  push    rbp
0x140239366  sub     rsp, 40h
0x14023936a  mov     rbp, rdx
0x14023936d  mov     rax, [rcx]
0x140239370  mov     ecx, [rax]
0x140239372  mov     [rbp+40h], ecx
0x140239375  mov     ecx, [rbp+40h]
0x140239378  call    SetLastNtError
0x14023937d  mov     dword ptr [rbp+48h], 1
0x140239384  mov     eax, [rbp+48h]
0x140239387  add     rsp, 40h
0x14023938b  pop     rbp
0x14023938c  retn
```
