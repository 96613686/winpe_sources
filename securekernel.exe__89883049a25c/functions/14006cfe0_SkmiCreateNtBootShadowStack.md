# SkmiCreateNtBootShadowStack

- ea: `0x14006cfe0`
- end: `0x14006d7e7`
- name: `SkmiCreateNtBootShadowStack`
- size: `2055`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14006cd8c`

## callees

- `0x140003780`
- `0x140008ec4`
- `0x140009940`
- `0x14000c8d0`
- `0x140011130`
- `0x14002b534`
- `0x140031460`
- `0x140050ba4`
- `0x14006cfe0`
- `0x140076948`
- `0x140081290`
- `0x1400f2fc0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCreateNtBootShadowStack(unsigned __int64 a1, int a2, __int64 a3)
{
  __int64 result; // rax
  unsigned __int64 v5; // rdi
  __int64 PteTrace; // rax
  __int64 v7; // rsi
  PVOID *v8; // rbx
  ULONG v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *StackBase; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rax
  int v17; // r9d
  unsigned __int64 v18; // r10
  __int64 v19; // r14
  PVOID *v20; // rsi
  PVOID v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 *v27; // r15
  __int64 v28; // rax
  __int64 v29; // rsi
  PVOID *v30; // rbx
  PVOID v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rsi
  PVOID *v36; // rbx
  PVOID v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rdi
  int v41; // eax
  unsigned __int64 v42; // rcx
  ULONG_PTR v43; // rbx
  unsigned __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // r14
  PVOID *v47; // rsi
  PVOID v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rsi
  ULONG_PTR v52; // rax
  unsigned __int64 v53; // rsi
  __int64 v54; // rax
  __int64 v55; // r14
  PVOID *v56; // rbx
  PVOID v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rcx
  _QWORD *v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rdx
  unsigned __int8 CurrentIrql; // r15
  __int64 HyperspacePte; // rbx
  ULONG_PTR v65; // rsi
  __int64 v66; // rax
  __int64 v67; // r14
  PVOID *v68; // rdi
  PVOID v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rcx
  _QWORD *v72; // rax
  __int64 v73; // rcx
  __int64 v74; // rdx
  __int64 v75; // rax
  int v76; // r9d
  __int64 v77; // rsi
  PVOID *v78; // rdi
  PVOID v79; // rcx
  __int64 v80; // rdx
  __int64 v81; // rcx
  _QWORD *v82; // rax
  __int64 v83; // rcx
  __int64 v84; // rdx
  __int64 v85; // rcx
  ULONG_PTR BugCheckParameter3; // [rsp+40h] [rbp-10h] BYREF
  __int64 v87; // [rsp+48h] [rbp-8h] BYREF
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+38h]
  ULONG_PTR BackTraceHash; // [rsp+A8h] [rbp+58h] BYREF

  v87 = 0;
  BugCheckParameter3 = 0;
  result = SkmiReserveNar(a1, 12288, 0, 2, 0, 0, (__int64)&v87);
  if ( (int)result < 0 )
    return result;
  v5 = (((a1 + 0x8000000000LL) >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  PteTrace = SkmiGetPteTrace(0, (unsigned int)((a1 + 0x8000000000LL) >> 9) & 0xFFFFFFF8, 0, 0, *(_QWORD *)v5);
  v7 = PteTrace;
  if ( PteTrace )
  {
    v8 = (PVOID *)(PteTrace + 32);
    memset_0((void *)(PteTrace + 32), 0, 0x40u);
    if ( _bittest(&SkmiFlags, 0x16u) )
    {
      if ( KeGetPcr()->NtTib.StackBase && !RtlCaptureStackBackTrace(v9, 8u, v8, (PULONG)&BackTraceHash) )
      {
        *(_QWORD *)(v7 + 40) = retaddr;
        *v8 = (PVOID)SkmiGetInstructionPointer(v11, v10);
      }
    }
  }
  if ( v5 >= 0xFFFFF6FB7DBED000uLL && v5 < 0xFFFFF6FB7DBED800uLL )
  {
    StackBase = KeGetPcr()->NtTib.StackBase;
    v13 = StackBase ? StackBase[10] : 0LL;
    v14 = *(_QWORD *)(v13 + 232);
    if ( v14 )
      *(_QWORD *)(v14 + 8 * (((__int64)v5 >> 3) & 0x1FF)) = 0;
  }
  v15 = v5 + 16;
  *(_QWORD *)v5 = 0;
  v16 = SkmiGetPteTrace(
          0,
          ((unsigned int)((a1 + 0x8000000000LL) >> 9) & 0xFFFFFFF8) + 16,
          0,
          0,
          *(_QWORD *)((((a1 + 0x8000000000LL) >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL + 16));
  v19 = v16;
  if ( v16 )
  {
    v20 = (PVOID *)(v16 + 32);
    memset_0((void *)(v16 + 32), 0, (unsigned int)(v17 + 64));
    if ( _bittest(&SkmiFlags, 0x16u) )
    {
      v21 = KeGetPcr()->NtTib.StackBase;
      if ( v21 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v21, 8u, v20, (PULONG)&BackTraceHash) )
        {
          *(_QWORD *)(v19 + 40) = retaddr;
          *v20 = (PVOID)SkmiGetInstructionPointer(v23, v22);
        }
      }
    }
    v18 = 0xFFFFF6FB7DBED800uLL;
  }
  if ( (unsigned __int64)v15 >= 0xFFFFF6FB7DBED000uLL && v15 < v18 )
  {
    v24 = KeGetPcr()->NtTib.StackBase;
    v25 = v24 ? v24[10] : 0LL;
    v26 = *(_QWORD *)(v25 + 232);
    if ( v26 )
      *(_QWORD *)(v26 + 8 * ((v15 >> 3) & 0x1FF)) = 0;
  }
  *(_QWORD *)v15 = 0;
  v27 = (__int64 *)(((a1 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL);
  v28 = SkmiGetPteTrace(0, (unsigned int)(a1 >> 9) & 0xFFFFFFF8, 0, 0, *v27);
  v29 = v28;
  if ( v28 )
  {
    v30 = (PVOID *)(v28 + 32);
    memset_0((void *)(v28 + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v31 = KeGetPcr()->NtTib.StackBase;
      if ( v31 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v31, 8u, v30, (PULONG)&BackTraceHash) )
        {
          *(_QWORD *)(v29 + 40) = retaddr;
          *v30 = (PVOID)SkmiGetInstructionPointer(v33, v32);
        }
      }
    }
  }
  *v27 = 0x4000000000000000LL;
  v34 = SkmiGetPteTrace(
          0,
          ((unsigned int)(a1 >> 9) & 0xFFFFFFF8) + 16,
          0,
          0,
          *(_QWORD *)(((a1 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL + 16));
  v35 = v34;
  if ( v34 )
  {
    v36 = (PVOID *)(v34 + 32);
    memset_0((void *)(v34 + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v37 = KeGetPcr()->NtTib.StackBase;
      if ( v37 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v37, 8u, v36, (PULONG)&BackTraceHash) )
        {
          *(_QWORD *)(v35 + 40) = retaddr;
          *v36 = (PVOID)SkmiGetInstructionPointer(v39, v38);
        }
      }
    }
  }
  BugCheckParameter3 = -1;
  v27[2] = 0x4000000000000000LL;
  v40 = v5 + 8;
  if ( (*(_DWORD *)(SkeLoaderBlock + 1440) & 0x8000) != 0 )
  {
    v42 = *(_QWORD *)v40;
LABEL_43:
    BugCheckParameter3 = (v42 >> 12) & 0xFFFFFFFFFFLL;
    BackTraceHash = BugCheckParameter3;
    result = SkmiClaimPhysicalPages((ULONG_PTR)&BackTraceHash, 1, 0x48005u);
    if ( (int)result < 0 )
      return result;
    result = SkmiProtectSinglePage(BugCheckParameter3);
    if ( (int)result < 0 )
      return result;
    v43 = BugCheckParameter3;
    goto LABEL_46;
  }
  v41 = SkmiAllocatePhysicalPage(0, 3, &BugCheckParameter3);
  v42 = *(_QWORD *)v40;
  if ( !v41 )
    goto LABEL_43;
  v43 = BugCheckParameter3;
  *(_QWORD *)v40 = v42 & 0xFFF0000000000FFFuLL | ((BugCheckParameter3 & 0xFFFFFFFFFFLL) << 12);
  if ( v43 > 0xFFFFFFFFFFLL )
    __fastfail(0x3Fu);
  *(_QWORD *)(8 * v43 - 0x180000000000LL) = *(_QWORD *)(8 * v43 - 0x180000000000LL) & 0x1FFFFFFFFFFFFFFFLL
                                          | 0xA000000000000000uLL;
LABEL_46:
  v44 = ((v43 & 0xFFFFFFFFFFLL) << 12) | 0x8000000000000061uLL;
  v45 = SkmiGetPteTrace(
          0,
          ((unsigned int)(a1 >> 9) & 0xFFFFFFF8) + 8,
          0,
          v44,
          *(_QWORD *)(((a1 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL + 8));
  v46 = v45;
  if ( v45 )
  {
    v47 = (PVOID *)(v45 + 32);
    memset_0((void *)(v45 + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v48 = KeGetPcr()->NtTib.StackBase;
      if ( v48 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v48, 8u, v47, (PULONG)&BackTraceHash) )
        {
          *(_QWORD *)(v46 + 40) = retaddr;
          *v47 = (PVOID)SkmiGetInstructionPointer(v50, v49);
        }
      }
    }
  }
  v51 = word_140156D90 & 1;
  v52 = BugCheckParameter3 & 0xFFFFFFFFFFLL;
  v27[1] = v44;
  v53 = (((16 * v52) | v51) << 8) | 0x8000000000000061uLL;
  v54 = SkmiGetPteTrace(0, v40, 0, v53, *(_QWORD *)v40);
  v55 = v54;
  if ( v54 )
  {
    v56 = (PVOID *)(v54 + 32);
    memset_0((void *)(v54 + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v57 = KeGetPcr()->NtTib.StackBase;
      if ( v57 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v57, 8u, v56, (PULONG)&BackTraceHash) )
        {
          *(_QWORD *)(v55 + 40) = retaddr;
          *v56 = (PVOID)SkmiGetInstructionPointer(v59, v58);
        }
      }
    }
  }
  if ( (unsigned __int64)v40 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v40 < 0xFFFFF6FB7DBED800uLL )
  {
    v60 = KeGetPcr()->NtTib.StackBase;
    v61 = v60 ? v60[10] : 0LL;
    v62 = *(_QWORD *)(v61 + 232);
    if ( v62 )
      *(_QWORD *)(v62 + 8 * ((v40 >> 3) & 0x1FF)) = v53;
  }
  *(_QWORD *)v40 = v53;
  CurrentIrql = KeGetCurrentIrql();
  __writecr8(2u);
  HyperspacePte = SkmiGetHyperspacePte();
  v65 = ((BugCheckParameter3 & 0xFFFFFFFFFFLL) << 12) | 0x8000000000000063uLL;
  v66 = SkmiGetPteTrace(0, HyperspacePte, 0, ((_DWORD)BugCheckParameter3 << 12) | 0x63u, *(_QWORD *)HyperspacePte);
  v67 = v66;
  if ( v66 )
  {
    v68 = (PVOID *)(v66 + 32);
    memset_0((void *)(v66 + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v69 = KeGetPcr()->NtTib.StackBase;
      if ( v69 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v69, 8u, v68, (PULONG)&BackTraceHash) )
        {
          *(_QWORD *)(v67 + 40) = retaddr;
          *v68 = (PVOID)SkmiGetInstructionPointer(v71, v70);
        }
      }
    }
  }
  if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
    && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
  {
    v72 = KeGetPcr()->NtTib.StackBase;
    v73 = v72 ? v72[10] : 0LL;
    v74 = *(_QWORD *)(v73 + 232);
    if ( v74 )
      *(_QWORD *)(v74 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v65;
  }
  *(_QWORD *)HyperspacePte = v65;
  SkmiInitializeNtKernelShadowStack(a1 + 0x2000, HyperspacePte << 25 >> 16, a2, 0, a3);
  v75 = SkmiGetPteTrace(0, HyperspacePte, 0, 0, *(_QWORD *)HyperspacePte);
  v77 = v75;
  if ( v75 )
  {
    v78 = (PVOID *)(v75 + 32);
    memset_0((void *)(v75 + 32), 0, (unsigned int)(v76 + 64));
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v79 = KeGetPcr()->NtTib.StackBase;
      if ( v79 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v79, 8u, v78, (PULONG)&BackTraceHash) )
        {
          *(_QWORD *)(v77 + 40) = retaddr;
          *v78 = (PVOID)SkmiGetInstructionPointer(v81, v80);
        }
      }
    }
  }
  if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
    && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
  {
    v82 = KeGetPcr()->NtTib.StackBase;
    if ( v82 )
      v83 = v82[10];
    else
      v83 = 0;
    v84 = *(_QWORD *)(v83 + 232);
    if ( v84 )
      *(_QWORD *)(v84 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = 0;
  }
  *(_QWORD *)HyperspacePte = 0;
  SkmiReleaseHyperspacePte(HyperspacePte);
  LOBYTE(v85) = CurrentIrql;
  SkeLowerIrql(v85);
  return 0;
}

```

## disassembly

```asm
0x14006cfe0  mov     r11, rsp
0x14006cfe3  mov     [r11+8], rbx
0x14006cfe7  mov     [r11+18h], r8
0x14006cfeb  mov     [rsp-38h+arg_8], edx
0x14006cfef  push    rbp
0x14006cff0  push    rsi
0x14006cff1  push    rdi
0x14006cff2  push    r12
0x14006cff4  push    r13
0x14006cff6  push    r14
0x14006cff8  push    r15
0x14006cffa  mov     rbp, rsp
0x14006cffd  sub     rsp, 50h
0x14006d001  xor     r12d, r12d
0x14006d004  lea     rax, [rbp+var_8]
0x14006d008  mov     [r11-58h], rax
0x14006d00c  xor     r8d, r8d; int
0x14006d00f  mov     [r11-60h], r12
0x14006d013  mov     edx, 3000h; int
0x14006d018  mov     r13, rcx
0x14006d01b  mov     [rbp+var_8], r12
0x14006d01f  lea     r9d, [r12+2]; int
0x14006d024  mov     [rbp+BugCheckParameter3], r12
0x14006d028  mov     [r11-68h], r12
0x14006d02c  call    SkmiReserveNar
0x14006d031  test    eax, eax
0x14006d033  js      loc_14006D7CE
0x14006d039  mov     rax, 7FFFFFFFF8h
0x14006d043  mov     rdi, 8000000000h
0x14006d04d  add     rdi, r13
0x14006d050  shr     rdi, 9
0x14006d054  and     rdi, rax
0x14006d057  mov     rax, 0FFFFF68000000000h
0x14006d061  mov     rax, rax
0x14006d064  add     rdi, rax
0x14006d067  xor     r9d, r9d
0x14006d06a  xor     r8d, r8d
0x14006d06d  mov     rdx, rdi
0x14006d070  xor     ecx, ecx
0x14006d072  mov     rax, [rdi]
0x14006d075  mov     [rsp+50h+var_30], rax
0x14006d07a  call    SkmiGetPteTrace
0x14006d07f  mov     rsi, rax
0x14006d082  test    rax, rax
0x14006d085  jz      short loc_14006D0D8
0x14006d087  lea     rbx, [rax+20h]
0x14006d08b  xor     edx, edx; Val
0x14006d08d  mov     rcx, rbx; void *
0x14006d090  lea     r8d, [r12+40h]; Size
0x14006d095  call    memset_0
0x14006d09a  bt      cs:SkmiFlags, 16h
0x14006d0a2  jnb     short loc_14006D0D8
0x14006d0a4  mov     rax, gs:8
0x14006d0ad  test    rax, rax
0x14006d0b0  jz      short loc_14006D0D8
0x14006d0b2  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14006d0b6  mov     r8, rbx; BackTrace
0x14006d0b9  lea     edx, [r12+8]; FramesToCapture
0x14006d0be  call    RtlCaptureStackBackTrace
0x14006d0c3  test    ax, ax
0x14006d0c6  jnz     short loc_14006D0D8
0x14006d0c8  mov     rax, [rbp+38h]
0x14006d0cc  mov     [rsi+28h], rax
0x14006d0d0  call    SkmiGetInstructionPointer
0x14006d0d5  mov     [rbx], rax
0x14006d0d8  mov     rax, 0FFFFF6FB7DBED000h
0x14006d0e2  mov     rax, rax
0x14006d0e5  mov     r10, 0FFFFF6FB7DBED800h
0x14006d0ef  cmp     rdi, rax
0x14006d0f2  jb      short loc_14006D12F
0x14006d0f4  mov     rax, r10
0x14006d0f7  cmp     rdi, rax
0x14006d0fa  jnb     short loc_14006D12F
0x14006d0fc  mov     rax, gs:8
0x14006d105  test    rax, rax
0x14006d108  jz      short loc_14006D110
0x14006d10a  mov     rcx, [rax+50h]
0x14006d10e  jmp     short loc_14006D113
0x14006d110  mov     rcx, r12
0x14006d113  mov     rdx, [rcx+0E8h]
0x14006d11a  test    rdx, rdx
0x14006d11d  jz      short loc_14006D12F
0x14006d11f  mov     rax, rdi
0x14006d122  sar     rax, 3
0x14006d126  and     eax, 1FFh
0x14006d12b  mov     [rdx+rax*8], r12
0x14006d12f  lea     rbx, [rdi+10h]
0x14006d133  mov     [rdi], r12
0x14006d136  mov     rax, [rbx]
0x14006d139  xor     r9d, r9d
0x14006d13c  xor     r8d, r8d
0x14006d13f  mov     [rsp+50h+var_30], rax
0x14006d144  mov     rdx, rbx
0x14006d147  xor     ecx, ecx
0x14006d149  call    SkmiGetPteTrace
0x14006d14e  mov     r14, rax
0x14006d151  test    rax, rax
0x14006d154  jz      short loc_14006D1B0
0x14006d156  lea     rsi, [rax+20h]
0x14006d15a  xor     edx, edx; Val
0x14006d15c  mov     rcx, rsi; void *
0x14006d15f  lea     r8d, [r9+40h]; Size
0x14006d163  call    memset_0
0x14006d168  bt      cs:SkmiFlags, 16h
0x14006d170  jnb     short loc_14006D1A6
0x14006d172  mov     rcx, gs:8; FramesToSkip
0x14006d17b  test    rcx, rcx
0x14006d17e  jz      short loc_14006D1A6
0x14006d180  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14006d184  mov     r8, rsi; BackTrace
0x14006d187  mov     edx, 8; FramesToCapture
0x14006d18c  call    RtlCaptureStackBackTrace
0x14006d191  test    ax, ax
0x14006d194  jnz     short loc_14006D1A6
0x14006d196  mov     rax, [rbp+38h]
0x14006d19a  mov     [r14+28h], rax
0x14006d19e  call    SkmiGetInstructionPointer
0x14006d1a3  mov     [rsi], rax
0x14006d1a6  mov     r10, 0FFFFF6FB7DBED800h
0x14006d1b0  mov     rax, 0FFFFF6FB7DBED000h
0x14006d1ba  mov     rax, rax
0x14006d1bd  cmp     rbx, rax
0x14006d1c0  jb      short loc_14006D1FD
0x14006d1c2  mov     rax, r10
0x14006d1c5  cmp     rbx, rax
0x14006d1c8  jnb     short loc_14006D1FD
0x14006d1ca  mov     rax, gs:8
0x14006d1d3  test    rax, rax
0x14006d1d6  jz      short loc_14006D1DE
0x14006d1d8  mov     rcx, [rax+50h]
0x14006d1dc  jmp     short loc_14006D1E1
0x14006d1de  mov     rcx, r12
0x14006d1e1  mov     rdx, [rcx+0E8h]
0x14006d1e8  test    rdx, rdx
0x14006d1eb  jz      short loc_14006D1FD
0x14006d1ed  mov     rax, rbx
0x14006d1f0  sar     rax, 3
0x14006d1f4  and     eax, 1FFh
0x14006d1f9  mov     [rdx+rax*8], r12
0x14006d1fd  mov     r15, r13
0x14006d200  mov     [rbx], r12
0x14006d203  shr     r15, 9
0x14006d207  mov     rcx, 7FFFFFFFF8h
0x14006d211  and     r15, rcx
0x14006d214  mov     rcx, 0FFFFF60000000000h
0x14006d21e  add     r15, rcx
0x14006d221  mov     r9, 4000000000000000h
0x14006d22b  xor     r8d, r8d
0x14006d22e  mov     rdx, r15
0x14006d231  xor     ecx, ecx
0x14006d233  mov     rax, [r15]
0x14006d236  mov     [rsp+50h+var_30], rax
0x14006d23b  call    SkmiGetPteTrace
0x14006d240  mov     rsi, rax
0x14006d243  test    rax, rax
0x14006d246  jz      short loc_14006D29A
0x14006d248  xor     edx, edx; Val
0x14006d24a  lea     rbx, [rax+20h]
0x14006d24e  mov     rcx, rbx; void *
0x14006d251  lea     r8d, [rdx+40h]; Size
0x14006d255  call    memset_0
0x14006d25a  test    cs:SkmiFlags, 400000h
0x14006d264  jz      short loc_14006D29A
0x14006d266  mov     rcx, gs:8; FramesToSkip
0x14006d26f  test    rcx, rcx
0x14006d272  jz      short loc_14006D29A
0x14006d274  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14006d278  mov     r8, rbx; BackTrace
0x14006d27b  mov     edx, 8; FramesToCapture
0x14006d280  call    RtlCaptureStackBackTrace
0x14006d285  test    ax, ax
0x14006d288  jnz     short loc_14006D29A
0x14006d28a  mov     rax, [rbp+38h]
0x14006d28e  mov     [rsi+28h], rax
0x14006d292  call    SkmiGetInstructionPointer
0x14006d297  mov     [rbx], rax
0x14006d29a  mov     rax, 4000000000000000h
0x14006d2a4  lea     r14, [r15+10h]
0x14006d2a8  mov     [r15], rax
0x14006d2ab  mov     r9, 4000000000000000h
0x14006d2b5  mov     rax, [r14]
0x14006d2b8  xor     r8d, r8d
0x14006d2bb  mov     rdx, r14
0x14006d2be  mov     [rsp+50h+var_30], rax
0x14006d2c3  xor     ecx, ecx
0x14006d2c5  call    SkmiGetPteTrace
0x14006d2ca  mov     rsi, rax
0x14006d2cd  test    rax, rax
0x14006d2d0  jz      short loc_14006D324
0x14006d2d2  xor     edx, edx; Val
0x14006d2d4  lea     rbx, [rax+20h]
0x14006d2d8  mov     rcx, rbx; void *
0x14006d2db  lea     r8d, [rdx+40h]; Size
0x14006d2df  call    memset_0
0x14006d2e4  test    cs:SkmiFlags, 400000h
0x14006d2ee  jz      short loc_14006D324
0x14006d2f0  mov     rcx, gs:8; FramesToSkip
0x14006d2f9  test    rcx, rcx
0x14006d2fc  jz      short loc_14006D324
0x14006d2fe  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14006d302  mov     r8, rbx; BackTrace
0x14006d305  mov     edx, 8; FramesToCapture
0x14006d30a  call    RtlCaptureStackBackTrace
0x14006d30f  test    ax, ax
0x14006d312  jnz     short loc_14006D324
0x14006d314  mov     rax, [rbp+38h]
0x14006d318  mov     [rsi+28h], rax
0x14006d31c  call    SkmiGetInstructionPointer
0x14006d321  mov     [rbx], rax
0x14006d324  mov     rax, 4000000000000000h
0x14006d32e  mov     [rbp+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x14006d336  mov     [r14], rax
0x14006d339  add     rdi, 8
0x14006d33d  mov     rax, cs:SkeLoaderBlock
0x14006d344  test    dword ptr [rax+5A0h], 8000h
0x14006d34e  jnz     loc_14006D3ED
0x14006d354  lea     r8, [rbp+BugCheckParameter3]
0x14006d358  mov     edx, 3
0x14006d35d  xor     ecx, ecx
0x14006d35f  call    SkmiAllocatePhysicalPage
0x14006d364  mov     rcx, [rdi]
0x14006d367  test    eax, eax
0x14006d369  jz      loc_14006D3F0
0x14006d36f  mov     rbx, [rbp+BugCheckParameter3]
0x14006d373  mov     r12, 0FFFFFFFFFFh
0x14006d37d  mov     rax, rbx
0x14006d380  mov     rdx, 0FFF0000000000FFFh
0x14006d38a  and     rax, r12
0x14006d38d  and     rcx, rdx
0x14006d390  shl     rax, 0Ch
0x14006d394  or      rax, rcx
0x14006d397  mov     [rdi], rax
0x14006d39a  mov     rcx, 0FFFFEFFFFFFFFFFFh
0x14006d3a4  mov     rdx, 0FFFFE80000000000h
0x14006d3ae  mov     rax, rdx
0x14006d3b1  sub     rcx, rax
0x14006d3b4  sar     rcx, 3
0x14006d3b8  cmp     rbx, rcx
0x14006d3bb  jbe     short loc_14006D3C4
0x14006d3bd  mov     ecx, 3Fh ; '?'
0x14006d3c2  int     29h; Win8: RtlFailFast(ecx)
0x14006d3c4  mov     rax, rdx
0x14006d3c7  lea     rcx, [rax+rbx*8]
0x14006d3cb  mov     rdx, 1FFFFFFFFFFFFFFFh
0x14006d3d5  mov     rax, [rcx]
0x14006d3d8  and     rax, rdx
0x14006d3db  mov     rdx, 0A000000000000000h
0x14006d3e5  or      rax, rdx
0x14006d3e8  mov     [rcx], rax
0x14006d3eb  jmp     short loc_14006D43F
0x14006d3ed  mov     rcx, [rdi]
0x14006d3f0  shr     rcx, 0Ch
0x14006d3f4  mov     r12, 0FFFFFFFFFFh
0x14006d3fe  and     rcx, r12
0x14006d401  mov     edx, 1
0x14006d406  mov     [rbp+BugCheckParameter3], rcx
0x14006d40a  mov     r8d, 48005h
0x14006d410  mov     [rbp+BackTraceHash], rcx
0x14006d414  lea     rcx, [rbp+BackTraceHash]
0x14006d418  call    SkmiClaimPhysicalPages
0x14006d41d  test    eax, eax
0x14006d41f  js      loc_14006D7CE
0x14006d425  mov     rcx, [rbp+BugCheckParameter3]; BugCheckParameter3
0x14006d429  mov     edx, 103h
0x14006d42e  call    SkmiProtectSinglePage
0x14006d433  test    eax, eax
0x14006d435  js      loc_14006D7CE
0x14006d43b  mov     rbx, [rbp+BugCheckParameter3]
0x14006d43f  and     rbx, r12
0x14006d442  lea     rdx, [r15+8]
0x14006d446  mov     rax, 8000000000000061h
0x14006d450  shl     rbx, 0Ch
0x14006d454  or      rbx, rax
0x14006d457  xor     r8d, r8d
0x14006d45a  mov     rax, [r15+8]
0x14006d45e  mov     r9, rbx
0x14006d461  xor     ecx, ecx
0x14006d463  mov     [rsp+50h+var_30], rax
0x14006d468  call    SkmiGetPteTrace
0x14006d46d  mov     r14, rax
0x14006d470  test    rax, rax
0x14006d473  jz      short loc_14006D4C7
0x14006d475  xor     edx, edx; Val
0x14006d477  lea     rsi, [rax+20h]
0x14006d47b  mov     rcx, rsi; void *
0x14006d47e  lea     r8d, [rdx+40h]; Size
0x14006d482  call    memset_0
0x14006d487  test    cs:SkmiFlags, 400000h
0x14006d491  jz      short loc_14006D4C7
0x14006d493  mov     rcx, gs:8; FramesToSkip
0x14006d49c  test    rcx, rcx
0x14006d49f  jz      short loc_14006D4C7
0x14006d4a1  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14006d4a5  mov     r8, rsi; BackTrace
0x14006d4a8  mov     edx, 8; FramesToCapture
0x14006d4ad  call    RtlCaptureStackBackTrace
0x14006d4b2  test    ax, ax
0x14006d4b5  jnz     short loc_14006D4C7
0x14006d4b7  mov     rax, [rbp+38h]
0x14006d4bb  mov     [r14+28h], rax
  ... truncated ...
```
