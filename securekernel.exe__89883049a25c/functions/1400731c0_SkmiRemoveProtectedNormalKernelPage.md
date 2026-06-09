# SkmiRemoveProtectedNormalKernelPage

- ea: `0x1400731c0`
- end: `0x140073576`
- name: `SkmiRemoveProtectedNormalKernelPage`
- size: `950`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140002a04`

## callees

- `0x140003780`
- `0x1400091e0`
- `0x14000e810`
- `0x14000ff70`
- `0x140010b90`
- `0x1400130a0`
- `0x140014c80`
- `0x14002b534`
- `0x1400731c0`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiRemoveProtectedNormalKernelPage(ULONG_PTR BugCheckParameter3, unsigned __int64 a2, char a3)
{
  char v6; // r12
  unsigned __int64 v7; // rsi
  __int64 *v8; // r8
  signed __int64 v9; // rax
  unsigned __int64 v10; // rax
  signed __int64 v11; // rtt
  unsigned __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 PteTrace; // rax
  __int64 v15; // rdx
  __int64 v16; // rbp
  PVOID *v17; // r14
  ULONG v18; // ecx
  __int64 v19; // rcx
  int v20; // ecx
  unsigned int v21; // edi
  __int64 v22; // rax
  __int64 v23; // rbp
  PVOID *v24; // r14
  ULONG v25; // ecx
  __int64 v26; // rcx
  unsigned __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r15
  PVOID *v34; // r14
  __int64 v35; // rcx
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h]
  __int64 BackTraceHash; // [rsp+68h] [rbp+10h] BYREF

  v6 = SkAcquireSpinLockShared(&SkmiNteLock);
  v7 = ((a2 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL;
  v8 = (__int64 *)(((v7 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL);
  _m_prefetchw(v8);
  do
  {
    while ( 1 )
    {
      BackTraceHash = *v8;
      if ( (BackTraceHash & 0x80u) != 0LL )
      {
        SKMI_PAGE_SECURITY(264, BugCheckParameter3, (__int64)v8, &BackTraceHash);
        v21 = -1073741790;
        goto LABEL_38;
      }
      _m_prefetchw((const void *)v7);
      v9 = *(_QWORD *)v7;
      BackTraceHash = *(_QWORD *)v7;
      if ( (BackTraceHash & 0xA00) != 0x200 || (v9 & 0x801) != 1 && (v9 & 0x100) == 0 || (v9 & 0x400000000000000LL) != 0 )
      {
        v20 = 258;
LABEL_21:
        SKMI_PAGE_SECURITY(v20, BugCheckParameter3, v7, &BackTraceHash);
LABEL_22:
        v21 = -1073741819;
        goto LABEL_38;
      }
      if ( (SkmiFlags & 0x800000) != 0 && (v9 & 0x901) != 0x100 && (a3 & 1) == 0 )
      {
        v20 = 265;
        goto LABEL_21;
      }
      if ( (v9 & 0x400) == 0 )
        break;
      _mm_pause();
    }
    v11 = v9;
    v10 = _InterlockedCompareExchange64((volatile signed __int64 *)v7, v9 | 0x400, v9);
    v12 = v10;
    BackTraceHash = v10;
  }
  while ( v11 != v10 );
  v13 = (v10 >> 12) & 0xFFFFFFFFFFLL;
  if ( BugCheckParameter3 != v13 )
  {
    SKMI_PAGE_SECURITY(262, BugCheckParameter3, v7, &BackTraceHash);
    PteTrace = SkmiGetPteTrace(0, v7, 0, v12, *(_QWORD *)v7);
    v16 = PteTrace;
    if ( PteTrace )
    {
      v17 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0
        && KeGetPcr()->NtTib.StackBase
        && !RtlCaptureStackBackTrace(v18, 8u, v17, (PULONG)&BackTraceHash) )
      {
        *(_QWORD *)(v16 + 40) = retaddr;
        *v17 = (PVOID)SkmiGetInstructionPointer(v19, v15);
      }
    }
    *(_QWORD *)v7 = v12;
    goto LABEL_22;
  }
  if ( (*(_QWORD *)(8 * v13 - 0x180000000000LL) & 0xFFFFFFFFFFFLL) != 0 )
  {
    SKMI_PAGE_SECURITY(268, BugCheckParameter3, v7, &BackTraceHash);
    v22 = SkmiGetPteTrace(0, v7, 0, v12, *(_QWORD *)v7);
    v23 = v22;
    if ( v22 )
    {
      v24 = (PVOID *)(v22 + 32);
      memset_0((void *)(v22 + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0
        && KeGetPcr()->NtTib.StackBase
        && !RtlCaptureStackBackTrace(v25, 8u, v24, (PULONG)&BackTraceHash) )
      {
        *(_QWORD *)(v23 + 40) = retaddr;
        *v24 = (PVOID)SkmiGetInstructionPointer(v26, v15);
      }
    }
    *(_QWORD *)v7 = v12;
    v21 = -1073741757;
  }
  else
  {
    v27 = (-(__int64)((a3 & 1) != 0) & 0xC000000000000A21uLL) + 0x4000000000000000LL;
    v28 = SkmiGetPteTrace(0, v7, 0, (a3 & 1) != 0 ? 0xA21 : 0, *(_QWORD *)v7);
    v21 = 0;
    v33 = v28;
    if ( v28 )
    {
      v34 = (PVOID *)(v28 + 32);
      memset_0((void *)(v28 + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0
        && KeGetPcr()->NtTib.StackBase
        && !RtlCaptureStackBackTrace(v30, 8u, v34, (PULONG)&BackTraceHash) )
      {
        *(_QWORD *)(v33 + 40) = retaddr;
        *v34 = (PVOID)SkmiGetInstructionPointer(v30, v29);
      }
    }
    *(_QWORD *)v7 = v27;
    LOBYTE(v35) = SkmiAcquireNteAssertionLock(v30, v29, v31, v32);
    SkmiReleaseNteAssertionLock(v35);
    SkmiReleasePhysicalPage(BugCheckParameter3);
  }
LABEL_38:
  LOBYTE(v15) = v6;
  RtlpReleasePropStoreLockShared(&SkmiNteLock, v15);
  return v21;
}

```

## disassembly

```asm
0x1400731c0  mov     [rsp+arg_0], rbx
0x1400731c5  mov     [rsp+arg_10], rbp
0x1400731ca  push    rsi
0x1400731cb  push    rdi
0x1400731cc  push    r12
0x1400731ce  push    r14
0x1400731d0  push    r15
0x1400731d2  sub     rsp, 30h
0x1400731d6  mov     rbp, rcx
0x1400731d9  mov     edi, r8d
0x1400731dc  lea     rcx, SkmiNteLock
0x1400731e3  mov     rsi, rdx
0x1400731e6  call    SkAcquireSpinLockShared
0x1400731eb  mov     rcx, 7FFFFFFFF8h
0x1400731f5  shr     rsi, 9
0x1400731f9  and     rsi, rcx
0x1400731fc  mov     r12b, al
0x1400731ff  mov     rax, 0FFFFF60000000000h
0x140073209  add     rsi, rax
0x14007320c  mov     r8, rsi
0x14007320f  shr     r8, 9
0x140073213  and     r8, rcx
0x140073216  mov     rax, 0FFFFF68000000000h
0x140073220  add     r8, rax
0x140073223  prefetchw byte ptr [r8]
0x140073227  mov     edx, 100h
0x14007322c  mov     r9d, 400h
0x140073232  mov     rax, [r8]
0x140073235  mov     [rsp+58h+BackTraceHash], rax
0x14007323a  test    al, al
0x14007323c  js      loc_140073536
0x140073242  prefetchw byte ptr [rsi]
0x140073245  mov     rax, [rsi]
0x140073248  mov     rcx, rax
0x14007324b  mov     [rsp+58h+BackTraceHash], rax
0x140073250  and     ecx, 0A00h
0x140073256  cmp     rcx, 200h
0x14007325d  jnz     loc_14007352C
0x140073263  mov     rcx, rax
0x140073266  and     ecx, 801h
0x14007326c  cmp     rcx, 1
0x140073270  jz      short loc_14007327B
0x140073272  test    rdx, rax
0x140073275  jz      loc_14007352C
0x14007327b  bt      rax, 3Ah ; ':'
0x140073280  jb      loc_14007352C
0x140073286  test    cs:SkmiFlags, 800000h
0x140073290  jz      short loc_1400732AA
0x140073292  mov     rcx, rax
0x140073295  and     ecx, 901h
0x14007329b  cmp     rcx, rdx
0x14007329e  jz      short loc_1400732AA
0x1400732a0  test    dil, 1
0x1400732a4  jz      loc_14007337E
0x1400732aa  test    r9, rax
0x1400732ad  jnz     loc_140073377
0x1400732b3  mov     rcx, rax
0x1400732b6  or      rcx, r9
0x1400732b9  lock cmpxchg [rsi], rcx
0x1400732be  mov     rbx, rax
0x1400732c1  mov     [rsp+58h+BackTraceHash], rax
0x1400732c6  jnz     loc_140073232
0x1400732cc  mov     rdx, rax
0x1400732cf  mov     rax, 0FFFFFFFFFFh
0x1400732d9  shr     rdx, 0Ch
0x1400732dd  and     rdx, rax
0x1400732e0  cmp     rbp, rdx
0x1400732e3  jz      loc_14007339D
0x1400732e9  lea     r9, [rsp+58h+BackTraceHash]
0x1400732ee  mov     r8, rsi
0x1400732f1  mov     rdx, rbp
0x1400732f4  mov     ecx, 106h
0x1400732f9  call    SKMI_PAGE_SECURITY
0x1400732fe  mov     rax, [rsi]
0x140073301  mov     r9, rbx
0x140073304  xor     r8d, r8d
0x140073307  mov     [rsp+58h+var_38], rax
0x14007330c  mov     rdx, rsi
0x14007330f  xor     ecx, ecx
0x140073311  call    SkmiGetPteTrace
0x140073316  mov     rbp, rax
0x140073319  test    rax, rax
0x14007331c  jz      short loc_140073372
0x14007331e  xor     edx, edx; Val
0x140073320  lea     r14, [rax+20h]
0x140073324  mov     rcx, r14; void *
0x140073327  lea     r8d, [rdx+40h]; Size
0x14007332b  call    memset_0
0x140073330  test    cs:SkmiFlags, 400000h
0x14007333a  jz      short loc_140073372
0x14007333c  mov     rax, gs:8
0x140073345  test    rax, rax
0x140073348  jz      short loc_140073372
0x14007334a  lea     r9, [rsp+58h+BackTraceHash]; BackTraceHash
0x14007334f  mov     r8, r14; BackTrace
0x140073352  mov     edx, 8; FramesToCapture
0x140073357  call    RtlCaptureStackBackTrace
0x14007335c  test    ax, ax
0x14007335f  jnz     short loc_140073372
0x140073361  mov     rax, [rsp+58h]
0x140073366  mov     [rbp+28h], rax
0x14007336a  call    SkmiGetInstructionPointer
0x14007336f  mov     [r14], rax
0x140073372  mov     [rsi], rbx
0x140073375  jmp     short loc_140073393
0x140073377  pause
0x140073379  jmp     loc_140073232
0x14007337e  mov     ecx, 109h
0x140073383  mov     rdx, rbp
0x140073386  lea     r9, [rsp+58h+BackTraceHash]
0x14007338b  mov     r8, rsi
0x14007338e  call    SKMI_PAGE_SECURITY
0x140073393  mov     edi, 0C0000005h
0x140073398  jmp     loc_14007354D
0x14007339d  mov     rcx, 0FFFFEFFFFFFFFFFFh
0x1400733a7  mov     r8, 0FFFFE80000000000h
0x1400733b1  mov     rax, r8
0x1400733b4  sub     rcx, rax
0x1400733b7  sar     rcx, 3
0x1400733bb  cmp     rdx, rcx
0x1400733be  ja      loc_140073525
0x1400733c4  mov     rax, r8
0x1400733c7  mov     rcx, [rax+rdx*8]
0x1400733cb  mov     rax, 0FFFFFFFFFFFh
0x1400733d5  test    rax, rcx
0x1400733d8  jz      loc_140073474
0x1400733de  lea     r9, [rsp+58h+BackTraceHash]
0x1400733e3  mov     r8, rsi
0x1400733e6  mov     rdx, rbp
0x1400733e9  mov     ecx, 10Ch
0x1400733ee  call    SKMI_PAGE_SECURITY
0x1400733f3  mov     rax, [rsi]
0x1400733f6  mov     r9, rbx
0x1400733f9  xor     r8d, r8d
0x1400733fc  mov     [rsp+58h+var_38], rax
0x140073401  mov     rdx, rsi
0x140073404  xor     ecx, ecx
0x140073406  call    SkmiGetPteTrace
0x14007340b  mov     rbp, rax
0x14007340e  test    rax, rax
0x140073411  jz      short loc_140073467
0x140073413  xor     edx, edx; Val
0x140073415  lea     r14, [rax+20h]
0x140073419  mov     rcx, r14; void *
0x14007341c  lea     r8d, [rdx+40h]; Size
0x140073420  call    memset_0
0x140073425  test    cs:SkmiFlags, 400000h
0x14007342f  jz      short loc_140073467
0x140073431  mov     rax, gs:8
0x14007343a  test    rax, rax
0x14007343d  jz      short loc_140073467
0x14007343f  lea     r9, [rsp+58h+BackTraceHash]; BackTraceHash
0x140073444  mov     r8, r14; BackTrace
0x140073447  mov     edx, 8; FramesToCapture
0x14007344c  call    RtlCaptureStackBackTrace
0x140073451  test    ax, ax
0x140073454  jnz     short loc_140073467
0x140073456  mov     rax, [rsp+58h]
0x14007345b  mov     [rbp+28h], rax
0x14007345f  call    SkmiGetInstructionPointer
0x140073464  mov     [r14], rax
0x140073467  mov     [rsi], rbx
0x14007346a  mov     edi, 0C0000043h
0x14007346f  jmp     loc_14007354D
0x140073474  mov     rax, 0C000000000000A21h
0x14007347e  and     dil, 1
0x140073482  neg     dil
0x140073485  mov     rdx, rsi
0x140073488  sbb     rbx, rbx
0x14007348b  xor     r8d, r8d
0x14007348e  and     rbx, rax
0x140073491  xor     ecx, ecx
0x140073493  mov     rax, 4000000000000000h
0x14007349d  add     rbx, rax
0x1400734a0  mov     rax, [rsi]
0x1400734a3  mov     r9, rbx
0x1400734a6  mov     [rsp+58h+var_38], rax
0x1400734ab  call    SkmiGetPteTrace
0x1400734b0  xor     edi, edi
0x1400734b2  mov     r15, rax
0x1400734b5  test    rax, rax
0x1400734b8  jz      short loc_14007350C
0x1400734ba  lea     r14, [rax+20h]
0x1400734be  xor     edx, edx; Val
0x1400734c0  mov     rcx, r14; void *
0x1400734c3  lea     r8d, [rdi+40h]; Size
0x1400734c7  call    memset_0
0x1400734cc  test    cs:SkmiFlags, 400000h
0x1400734d6  jz      short loc_14007350C
0x1400734d8  mov     rax, gs:8
0x1400734e1  test    rax, rax
0x1400734e4  jz      short loc_14007350C
0x1400734e6  lea     r9, [rsp+58h+BackTraceHash]; BackTraceHash
0x1400734eb  mov     r8, r14; BackTrace
0x1400734ee  lea     edx, [rdi+8]; FramesToCapture
0x1400734f1  call    RtlCaptureStackBackTrace
0x1400734f6  test    ax, ax
0x1400734f9  jnz     short loc_14007350C
0x1400734fb  mov     rax, [rsp+58h]
0x140073500  mov     [r15+28h], rax
0x140073504  call    SkmiGetInstructionPointer
0x140073509  mov     [r14], rax
0x14007350c  mov     [rsi], rbx
0x14007350f  call    SkmiAcquireNteAssertionLock
0x140073514  mov     cl, al
0x140073516  call    SkmiReleaseNteAssertionLock
0x14007351b  mov     rcx, rbp; BugCheckParameter3
0x14007351e  call    SkmiReleasePhysicalPage
0x140073523  jmp     short loc_14007354D
0x140073525  mov     ecx, 3Fh ; '?'
0x14007352a  int     29h; Win8: RtlFailFast(ecx)
0x14007352c  mov     ecx, 102h
0x140073531  jmp     loc_140073383
0x140073536  lea     r9, [rsp+58h+BackTraceHash]
0x14007353b  mov     rdx, rbp
0x14007353e  mov     ecx, 108h
0x140073543  call    SKMI_PAGE_SECURITY
0x140073548  mov     edi, 0C0000022h
0x14007354d  mov     dl, r12b
0x140073550  lea     rcx, SkmiNteLock
0x140073557  call    RtlpReleasePropStoreLockShared
0x14007355c  mov     rbx, [rsp+58h+arg_0]
0x140073561  mov     eax, edi
0x140073563  mov     rbp, [rsp+58h+arg_10]
0x140073568  add     rsp, 30h
0x14007356c  pop     r15
0x14007356e  pop     r14
0x140073570  pop     r12
0x140073572  pop     rdi
0x140073573  pop     rsi
0x140073574  retn
```
