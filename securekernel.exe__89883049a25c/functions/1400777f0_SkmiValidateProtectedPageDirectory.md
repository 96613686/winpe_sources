# SkmiValidateProtectedPageDirectory

- ea: `0x1400777f0`
- end: `0x140077ddc`
- name: `SkmiValidateProtectedPageDirectory`
- size: `1516`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140079724`

## callees

- `0x140003780`
- `0x140009940`
- `0x14000b980`
- `0x14000c8d0`
- `0x140011780`
- `0x140014c80`
- `0x1400202b0`
- `0x1400202ec`
- `0x14002aeac`
- `0x14002b534`
- `0x1400777f0`
- `0x140081290`
- `0x1400f2fc0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiValidateProtectedPageDirectory(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 *a3,
        _BYTE *a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7)
{
  unsigned __int64 v8; // r9
  unsigned __int64 *v9; // r11
  unsigned __int64 v10; // r10
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // r8
  int v14; // eax
  int v15; // r8d
  unsigned __int64 *v16; // rax
  __int64 HyperspacePte; // rsi
  __int64 v18; // r14
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned __int64 v25; // r14
  __int64 PteTrace; // rax
  __int64 v27; // r15
  PVOID *v28; // rbx
  PVOID StackBase; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  ULONG v35; // r10d
  unsigned __int64 v36; // rbx
  __int64 v37; // r8
  __int64 v38; // rdx
  int v39; // r9d
  __int64 v40; // r8
  unsigned __int64 v41; // r8
  int v42; // eax
  unsigned __int64 v43; // rax
  __int64 v44; // rcx
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  int v50; // r9d
  __int64 v51; // r14
  PVOID *v52; // rbx
  PVOID v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rcx
  _QWORD *v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rdx
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v60; // [rsp+38h] [rbp-8h] BYREF
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+38h]
  unsigned __int64 v62; // [rsp+80h] [rbp+40h]
  unsigned __int64 v63; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int64 *v64; // [rsp+90h] [rbp+50h]

  v64 = a3;
  v63 = a2;
  v62 = a1;
  v8 = a1;
  v9 = (unsigned __int64 *)a2;
  v10 = *(_QWORD *)(((a2 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL);
  v11 = 0;
  v12 = 0;
  if ( a3 )
    v12 = *a3;
  *(_QWORD *)BackTraceHash = v12;
  if ( (v10 & 0x80u) != 0LL )
  {
    if ( (v12 & 1) == 0
      || (v12 & 0x80) == 0
      || ((v10 ^ v12) & 0xFFFFFFFFFF000LL) != 0
      || ((v10 & 0x801) != 1
        ? (v13 = v10 >> 59)
        : (v63 = v10 & 0xFFFFFFFFFFFFFDFFuLL, v13 = (unsigned int)SKMI_GET_PROTECTION_FROM_VALID_PTE(&v63, a2, a3)),
          v14 = SKMI_GET_PROTECTION_FROM_VALID_PTE(BackTraceHash, a2, v13),
          v15 != v14) )
    {
      v16 = a5;
      *a4 = 1;
      *v16 = v8;
      *a6 = v12;
      *a7 = v10;
    }
    return 0;
  }
  HyperspacePte = 0;
  v18 = 0;
  if ( (v12 & 1) != 0 )
  {
    if ( (v12 & 0x80) == 0 )
    {
      v19 = (v12 >> 12) & 0xFFFFFFFFFFLL;
      if ( !(unsigned int)SkmiIncrementSharedPageReferenceCount(v19) )
      {
        SKMI_PAGE_SECURITY(2577, v19, 0, 0);
        return 3221225539LL;
      }
      HyperspacePte = SkmiGetHyperspacePte(v21, v20, v22, v23);
      v25 = v12 & 0xFFFFFFFFFF000LL | 0x8000000000000021uLL;
      PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, v12 & 0xFFFFF000 | 0x21, *(_QWORD *)HyperspacePte);
      v27 = PteTrace;
      if ( PteTrace )
      {
        v28 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          StackBase = KeGetPcr()->NtTib.StackBase;
          if ( StackBase )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v28, BackTraceHash) )
            {
              *(_QWORD *)(v27 + 40) = retaddr;
              *v28 = (PVOID)SkmiGetInstructionPointer(v31, v30);
            }
          }
        }
      }
      if ( (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED000uLL )
      {
        v11 = 0;
      }
      else
      {
        v11 = 0;
        if ( (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
        {
          v32 = KeGetPcr()->NtTib.StackBase;
          v33 = v32 ? v32[10] : 0LL;
          v34 = *(_QWORD *)(v33 + 232);
          if ( v34 )
            *(_QWORD *)(v34 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v25;
        }
      }
      *(_QWORD *)HyperspacePte = v25;
      a3 = v64;
      v8 = v62;
      v9 = (unsigned __int64 *)v63;
      v18 = HyperspacePte << 25 >> 16;
    }
  }
  else
  {
    a3 = 0;
    v64 = 0;
  }
  v35 = 0;
  BackTraceHash[0] = 0;
  while ( 1 )
  {
    v36 = *v9;
    if ( (*v9 & 0x800) != 0 )
      goto LABEL_70;
    if ( a3 )
    {
      if ( v18 )
        v11 = *(_QWORD *)v18;
      else
        v11 = (v12 + ((unsigned __int64)v35 << 12))
            ^ ((v12 + ((unsigned __int64)v35 << 12))
             ^ v12)
            & 0xFFF0000000000FFFuLL;
    }
    v60 = v11;
    v37 = v36 & 0x801;
    if ( (v11 & 1) == 0 )
    {
      if ( (v37 == 1 || (v36 & 0x100) != 0) && (v36 & 0x901) != 0x100 )
      {
        if ( v37 == 1 )
        {
          v60 = v36 & 0xFFFFFFFFFFFFFDFFuLL;
          LODWORD(v43) = SKMI_GET_PROTECTION_FROM_VALID_PTE(&v60, 0xFFFFFFFFFF000LL, 1);
        }
        else
        {
          v43 = v36 >> 59;
        }
        if ( (_DWORD)v43 != 31 )
        {
          v44 = 0;
          while ( ((v36 >> 12) & 0xFFFFFFFFFFLL) != SkmiKernelScpPfns[v44] )
          {
            v44 = (unsigned int)(v44 + 1);
            if ( (unsigned int)v44 >= 2 )
              goto LABEL_60;
          }
        }
      }
      goto LABEL_61;
    }
    if ( v37 != 1 && (v36 & 0x100) == 0
      || (v36 & 0x901) == 0x100
      || ((v36 ^ v11) & 0xFFFFFFFFFF000LL) != 0
      || (v11 & 0x20) == 0 )
    {
LABEL_60:
      *a4 = 1;
      goto LABEL_61;
    }
    v39 = SKMI_GET_PROTECTION_FROM_VALID_PTE(&v60, 0xFFFFFFFFFF000LL, v37);
    if ( v40 == 1 )
    {
      v60 = v36 & 0xFFFFFFFFFFFFFDFFuLL;
      LODWORD(v41) = SKMI_GET_PROTECTION_FROM_VALID_PTE(&v60, v38, 1);
    }
    else
    {
      v41 = v36 >> 59;
    }
    v42 = v39 | 2;
    if ( (v36 & 0x200000000000000LL) == 0 )
      v42 = v39;
    if ( v42 != (_DWORD)v41 )
      break;
LABEL_61:
    if ( *a4 )
      goto LABEL_62;
LABEL_69:
    v8 = v62;
    v11 = 0;
LABEL_70:
    ++v9;
    v48 = v18 + 8;
    v8 += 4096LL;
    v63 = (unsigned __int64)v9;
    ++v35;
    v62 = v8;
    BackTraceHash[0] = v35;
    if ( !v18 )
      v48 = 0;
    v18 = v48;
    if ( v35 >= 0x200 )
      goto LABEL_77;
    a3 = v64;
  }
  *a4 = 1;
LABEL_62:
  if ( SkmiSecurePteExemption )
  {
    KeGetCurrentIrql();
    __writecr8(5u);
    SkAcquireSpinLockSharedAtDpcLevel(&dword_1401567E8);
    if ( SkmiSecurePteExemption )
    {
      v45 = *(_QWORD *)(SkmiSecurePteExemption + 24);
      v46 = v62;
      if ( v62 >= v45 )
      {
        v46 = (v62 - v45) >> 12;
        if ( v46 < *(unsigned int *)(SkmiSecurePteExemption + 72) )
          *a4 = 0;
      }
    }
    _InterlockedDecrement(&dword_1401567E8);
    SkTrackSpinLockRelease(v46, v45);
    LOBYTE(v47) = 4;
    SkeLowerIrql(v47);
    v35 = BackTraceHash[0];
    v9 = (unsigned __int64 *)v63;
  }
  if ( !*a4 )
    goto LABEL_69;
  if ( !v18 )
    v11 = v12;
  *a5 = v62;
  *a6 = v11;
  *a7 = v36;
LABEL_77:
  if ( HyperspacePte )
  {
    v49 = SkmiGetPteTrace(0, HyperspacePte, 0, 0, *(_QWORD *)HyperspacePte);
    v51 = v49;
    if ( v49 )
    {
      v52 = (PVOID *)(v49 + 32);
      memset_0((void *)(v49 + 32), 0, (unsigned int)(v50 + 64));
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v53 = KeGetPcr()->NtTib.StackBase;
        if ( v53 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v53, 8u, v52, (PULONG)&v63) )
          {
            *(_QWORD *)(v51 + 40) = retaddr;
            *v52 = (PVOID)SkmiGetInstructionPointer(v55, v54);
          }
        }
      }
    }
    if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
      && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
    {
      v56 = KeGetPcr()->NtTib.StackBase;
      v57 = v56 ? v56[10] : 0LL;
      v58 = *(_QWORD *)(v57 + 232);
      if ( v58 )
        *(_QWORD *)(v58 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)HyperspacePte = 0;
    SkmiReleaseHyperspacePte(HyperspacePte);
    SkmiDecrementPageReferenceCount((v12 >> 12) & 0xFFFFFFFFFFLL);
  }
  return 0;
}

```

## disassembly

```asm
0x1400777f0  mov     rax, rsp
0x1400777f3  mov     [rax+20h], rbx
0x1400777f7  mov     [rax+18h], r8
0x1400777fb  mov     [rax+10h], rdx
0x1400777ff  mov     [rax+8], rcx
0x140077803  push    rbp
0x140077804  push    rsi
0x140077805  push    rdi
0x140077806  push    r12
0x140077808  push    r13
0x14007780a  push    r14
0x14007780c  push    r15
0x14007780e  mov     rbp, rsp
0x140077811  sub     rsp, 40h
0x140077815  mov     r13, r9
0x140077818  mov     rax, rdx
0x14007781b  mov     r9, rcx
0x14007781e  shr     rax, 9
0x140077822  mov     rcx, 7FFFFFFFF8h
0x14007782c  mov     r11, rdx
0x14007782f  and     rax, rcx
0x140077832  mov     rcx, 0FFFFF68000000000h
0x14007783c  mov     r10, rcx
0x14007783f  mov     r10, [rax+r10]
0x140077843  xor     r15d, r15d
0x140077846  mov     edi, r15d
0x140077849  test    r8, r8
0x14007784c  jz      short loc_140077851
0x14007784e  mov     rdi, [r8]
0x140077851  mov     al, 80h
0x140077853  mov     qword ptr [rbp+BackTraceHash], rdi
0x140077857  test    al, r10b
0x14007785a  jz      loc_1400778E0
0x140077860  test    dil, 1
0x140077864  jz      short loc_1400778C1
0x140077866  test    al, dil
0x140077869  jz      short loc_1400778C1
0x14007786b  mov     rax, rdi
0x14007786e  mov     rcx, 0FFFFFFFFFF000h
0x140077878  xor     rax, r10
0x14007787b  test    rcx, rax
0x14007787e  jnz     short loc_1400778C1
0x140077880  mov     rax, r10
0x140077883  and     eax, 801h
0x140077888  cmp     rax, 1
0x14007788c  jnz     short loc_1400778A8
0x14007788e  mov     rax, r10
0x140077891  lea     rcx, [rbp+arg_8]
0x140077895  btr     rax, 9
0x14007789a  mov     [rbp+arg_8], rax
0x14007789e  call    SKMI_GET_PROTECTION_FROM_VALID_PTE
0x1400778a3  mov     r8d, eax
0x1400778a6  jmp     short loc_1400778AF
0x1400778a8  mov     r8, r10
0x1400778ab  shr     r8, 3Bh
0x1400778af  lea     rcx, [rbp+BackTraceHash]
0x1400778b3  call    SKMI_GET_PROTECTION_FROM_VALID_PTE
0x1400778b8  cmp     r8d, eax
0x1400778bb  jz      loc_140077DC1
0x1400778c1  mov     rax, [rbp+arg_20]
0x1400778c5  mov     byte ptr [r13+0], 1
0x1400778ca  mov     [rax], r9
0x1400778cd  mov     rax, [rbp+arg_28]
0x1400778d1  mov     [rax], rdi
0x1400778d4  mov     rax, [rbp+arg_30]
0x1400778d8  mov     [rax], r10
0x1400778db  jmp     loc_140077DC1
0x1400778e0  mov     rsi, r15
0x1400778e3  mov     r14, r15
0x1400778e6  mov     rdx, 0FFFFFFFFFF000h
0x1400778f0  mov     rcx, 0FFFFFFFFFFh
0x1400778fa  test    dil, 1
0x1400778fe  jz      loc_140077A75
0x140077904  test    al, dil
0x140077907  jnz     loc_140077A7C
0x14007790d  mov     rbx, rdi
0x140077910  mov     edx, 1
0x140077915  shr     rbx, 0Ch
0x140077919  and     rbx, rcx
0x14007791c  mov     rcx, rbx; BugCheckParameter3
0x14007791f  call    SkmiIncrementSharedPageReferenceCount
0x140077924  test    eax, eax
0x140077926  jnz     short loc_140077945
0x140077928  xor     r9d, r9d
0x14007792b  xor     r8d, r8d
0x14007792e  mov     rdx, rbx
0x140077931  mov     ecx, 0A11h
0x140077936  call    SKMI_PAGE_SECURITY
0x14007793b  mov     eax, 0C0000043h
0x140077940  jmp     loc_140077DC3
0x140077945  call    SkmiGetHyperspacePte
0x14007794a  mov     rsi, rax
0x14007794d  mov     r14, rdi
0x140077950  mov     rax, 0FFFFFFFFFF000h
0x14007795a  xor     r8d, r8d
0x14007795d  and     r14, rax
0x140077960  mov     rdx, rsi
0x140077963  mov     rax, 8000000000000021h
0x14007796d  xor     ecx, ecx
0x14007796f  or      r14, rax
0x140077972  mov     rax, [rsi]
0x140077975  mov     r9, r14
0x140077978  mov     [rsp+40h+var_20], rax
0x14007797d  call    SkmiGetPteTrace
0x140077982  mov     r15, rax
0x140077985  test    rax, rax
0x140077988  jz      short loc_1400779DC
0x14007798a  xor     edx, edx; Val
0x14007798c  lea     rbx, [rax+20h]
0x140077990  mov     rcx, rbx; void *
0x140077993  lea     r8d, [rdx+40h]; Size
0x140077997  call    memset_0
0x14007799c  test    cs:SkmiFlags, 400000h
0x1400779a6  jz      short loc_1400779DC
0x1400779a8  mov     rcx, gs:8; FramesToSkip
0x1400779b1  test    rcx, rcx
0x1400779b4  jz      short loc_1400779DC
0x1400779b6  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x1400779ba  mov     r8, rbx; BackTrace
0x1400779bd  mov     edx, 8; FramesToCapture
0x1400779c2  call    RtlCaptureStackBackTrace
0x1400779c7  test    ax, ax
0x1400779ca  jnz     short loc_1400779DC
0x1400779cc  mov     rax, [rbp+38h]
0x1400779d0  mov     [r15+28h], rax
0x1400779d4  call    SkmiGetInstructionPointer
0x1400779d9  mov     [rbx], rax
0x1400779dc  mov     rax, 0FFFFF6FB7DBED000h
0x1400779e6  mov     rax, rax
0x1400779e9  cmp     rsi, rax
0x1400779ec  jb      short loc_140077A38
0x1400779ee  mov     rax, 0FFFFF6FB7DBED800h
0x1400779f8  mov     rax, rax
0x1400779fb  xor     r15d, r15d
0x1400779fe  cmp     rsi, rax
0x140077a01  jnb     short loc_140077A3B
0x140077a03  mov     rax, gs:8
0x140077a0c  test    rax, rax
0x140077a0f  jz      short loc_140077A17
0x140077a11  mov     rcx, [rax+50h]
0x140077a15  jmp     short loc_140077A1A
0x140077a17  mov     rcx, r15
0x140077a1a  mov     rdx, [rcx+0E8h]
0x140077a21  test    rdx, rdx
0x140077a24  jz      short loc_140077A3B
0x140077a26  mov     rax, rsi
0x140077a29  sar     rax, 3
0x140077a2d  and     eax, 1FFh
0x140077a32  mov     [rdx+rax*8], r14
0x140077a36  jmp     short loc_140077A3B
0x140077a38  xor     r15d, r15d
0x140077a3b  mov     [rsi], r14
0x140077a3e  mov     r14, rsi
0x140077a41  shl     r14, 19h
0x140077a45  mov     rax, 0FFFFF68000000000h
0x140077a4f  mov     rax, rax
0x140077a52  mov     r8, [rbp+arg_10]
0x140077a56  mov     rdx, 0FFFFFFFFFF000h
0x140077a60  mov     r9, [rbp+arg_0]
0x140077a64  mov     r11, [rbp+arg_8]
0x140077a68  shl     rax, 19h
0x140077a6c  sub     r14, rax
0x140077a6f  sar     r14, 10h
0x140077a73  jmp     short loc_140077A7C
0x140077a75  mov     r8, r15
0x140077a78  mov     [rbp+arg_10], r15
0x140077a7c  mov     r10d, r15d
0x140077a7f  mov     [rbp+BackTraceHash], r15d
0x140077a83  mov     r12, 0FFFFFFFFFFFFFDFFh
0x140077a8a  mov     rbx, [r11]
0x140077a8d  bt      rbx, 0Bh
0x140077a92  jb      loc_140077C67
0x140077a98  test    r8, r8
0x140077a9b  jz      short loc_140077AC7
0x140077a9d  test    r14, r14
0x140077aa0  jnz     short loc_140077AC4
0x140077aa2  mov     ecx, r10d
0x140077aa5  mov     r15, rdi
0x140077aa8  shl     rcx, 0Ch
0x140077aac  mov     rax, 0FFF0000000000FFFh
0x140077ab6  add     rcx, rdi
0x140077ab9  xor     r15, rcx
0x140077abc  and     r15, rax
0x140077abf  xor     r15, rcx
0x140077ac2  jmp     short loc_140077AC7
0x140077ac4  mov     r15, [r14]
0x140077ac7  mov     r8, rbx
0x140077aca  mov     [rbp+var_8], r15
0x140077ace  and     r8d, 801h
0x140077ad5  test    r15b, 1
0x140077ad9  jz      loc_140077B77
0x140077adf  cmp     r8, 1
0x140077ae3  jz      short loc_140077AF0
0x140077ae5  bt      rbx, 8
0x140077aea  jnb     loc_140077BE2
0x140077af0  mov     rax, rbx
0x140077af3  and     eax, 901h
0x140077af8  cmp     rax, 100h
0x140077afe  jz      loc_140077BE2
0x140077b04  mov     rax, r15
0x140077b07  xor     rax, rbx
0x140077b0a  test    rdx, rax
0x140077b0d  jnz     loc_140077BE2
0x140077b13  test    r15b, 20h
0x140077b17  jz      loc_140077BE2
0x140077b1d  lea     rcx, [rbp+var_8]
0x140077b21  call    SKMI_GET_PROTECTION_FROM_VALID_PTE
0x140077b26  mov     r9d, eax
0x140077b29  cmp     r8, 1
0x140077b2d  jnz     short loc_140077B47
0x140077b2f  mov     rcx, rbx
0x140077b32  and     rcx, r12
0x140077b35  mov     [rbp+var_8], rcx
0x140077b39  lea     rcx, [rbp+var_8]
0x140077b3d  call    SKMI_GET_PROTECTION_FROM_VALID_PTE
0x140077b42  mov     r8d, eax
0x140077b45  jmp     short loc_140077B4E
0x140077b47  mov     r8, rbx
0x140077b4a  shr     r8, 3Bh
0x140077b4e  mov     rax, 200000000000000h
0x140077b58  mov     rcx, rbx
0x140077b5b  and     rcx, rax
0x140077b5e  mov     eax, r9d
0x140077b61  or      eax, 2
0x140077b64  test    rcx, rcx
0x140077b67  cmovz   eax, r9d
0x140077b6b  cmp     eax, r8d
0x140077b6e  jz      short loc_140077BE7
0x140077b70  mov     byte ptr [r13+0], 1
0x140077b75  jmp     short loc_140077BEE
0x140077b77  cmp     r8, 1
0x140077b7b  jz      short loc_140077B84
0x140077b7d  bt      rbx, 8
0x140077b82  jnb     short loc_140077BE7
0x140077b84  mov     rax, rbx
0x140077b87  and     eax, 901h
0x140077b8c  cmp     rax, 100h
0x140077b92  jz      short loc_140077BE7
0x140077b94  mov     rax, rbx
0x140077b97  cmp     r8, 1
0x140077b9b  jnz     short loc_140077BAF
0x140077b9d  and     rax, r12
0x140077ba0  lea     rcx, [rbp+var_8]
0x140077ba4  mov     [rbp+var_8], rax
0x140077ba8  call    SKMI_GET_PROTECTION_FROM_VALID_PTE
0x140077bad  jmp     short loc_140077BB3
0x140077baf  shr     rax, 3Bh
0x140077bb3  cmp     eax, 1Fh
0x140077bb6  jz      short loc_140077BE7
0x140077bb8  mov     rdx, rbx
0x140077bbb  xor     ecx, ecx
0x140077bbd  shr     rdx, 0Ch
0x140077bc1  mov     rax, 0FFFFFFFFFFh
0x140077bcb  and     rdx, rax
0x140077bce  lea     r8, SkmiKernelScpPfns
0x140077bd5  cmp     rdx, [r8+rcx*8]
0x140077bd9  jz      short loc_140077BE7
0x140077bdb  inc     ecx
0x140077bdd  cmp     ecx, 2
0x140077be0  jb      short loc_140077BCE
0x140077be2  mov     byte ptr [r13+0], 1
0x140077be7  cmp     byte ptr [r13+0], 0
0x140077bec  jz      short loc_140077C60
0x140077bee  cmp     cs:SkmiSecurePteExemption, 0
0x140077bf6  jz      short loc_140077C59
0x140077bf8  mov     rax, cr8
0x140077bfc  mov     eax, 5
0x140077c01  mov     cr8, rax
0x140077c05  lea     rcx, dword_1401567E8
0x140077c0c  call    SkAcquireSpinLockSharedAtDpcLevel
0x140077c11  mov     rax, cs:SkmiSecurePteExemption
0x140077c18  test    rax, rax
0x140077c1b  jz      short loc_140077C3E
0x140077c1d  mov     rdx, [rax+18h]
0x140077c21  mov     rcx, [rbp+arg_0]
0x140077c25  cmp     rcx, rdx
0x140077c28  jb      short loc_140077C3E
0x140077c2a  mov     eax, [rax+48h]
0x140077c2d  sub     rcx, rdx
0x140077c30  shr     rcx, 0Ch
0x140077c34  cmp     rcx, rax
0x140077c37  jnb     short loc_140077C3E
0x140077c39  mov     byte ptr [r13+0], 0
0x140077c3e  lock dec cs:dword_1401567E8
0x140077c45  call    SkTrackSpinLockRelease
0x140077c4a  mov     cl, 4
0x140077c4c  call    SkeLowerIrql
0x140077c51  mov     r10d, [rbp+BackTraceHash]
0x140077c55  mov     r11, [rbp+arg_8]
0x140077c59  cmp     byte ptr [r13+0], 0
0x140077c5e  jnz     short loc_140077CAB
0x140077c60  mov     r9, [rbp+arg_0]
0x140077c64  xor     r15d, r15d
0x140077c67  add     r11, 8
0x140077c6b  lea     rax, [r14+8]
0x140077c6f  add     r9, 1000h
0x140077c76  mov     [rbp+arg_8], r11
0x140077c7a  inc     r10d
0x140077c7d  mov     [rbp+arg_0], r9
0x140077c81  test    r14, r14
  ... truncated ...
```
