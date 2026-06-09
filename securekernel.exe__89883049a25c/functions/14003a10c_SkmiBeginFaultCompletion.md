# SkmiBeginFaultCompletion

- ea: `0x14003a10c`
- end: `0x14003a789`
- name: `SkmiBeginFaultCompletion`
- size: `1661`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1400843c8`
- `0x1400855c0`

## callees

- `0x140003780`
- `0x140008118`
- `0x14000d020`
- `0x140014d64`
- `0x1400202b0`
- `0x1400202ec`
- `0x1400295a8`
- `0x14002b514`
- `0x14002b534`
- `0x140030f10`
- `0x14003213c`
- `0x14003a10c`
- `0x14003a790`
- `0x14003a8c8`
- `0x14003a940`
- `0x14003a9c0`
- `0x140053250`
- `0x14007c9b8`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiBeginFaultCompletion(__int64 a1, unsigned __int64 a2, __int64 a3, _QWORD *a4, int a5)
{
  __int64 v9; // rbx
  __int64 PteTrace; // rax
  __int64 v11; // rdi
  PVOID *v12; // r14
  ULONG v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *StackBase; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // ecx
  int v21; // r12d
  __int64 v22; // r15
  __int64 v23; // rax
  __int64 v24; // r11
  __int64 v25; // r14
  PVOID *v26; // rdi
  ULONG v27; // ecx
  USHORT v28; // ax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r11
  __int64 v33; // rdi
  PVOID *v34; // r14
  ULONG v35; // ecx
  USHORT v36; // ax
  __int64 v37; // rdx
  __int64 v38; // rcx
  _QWORD *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rdx
  int v42; // ecx
  __int64 v43; // rcx
  __int64 v44; // rax
  unsigned int v45; // edi
  __int64 v46; // r10
  ULONG_PTR v47; // rdi
  __int64 v48; // r11
  ULONG_PTR v49; // rdi
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // r8
  unsigned int v52; // r11d
  ULONG_PTR v53; // rdi
  __int64 v54; // r8
  unsigned __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rax
  __int64 v60; // r11
  __int64 v61; // r15
  PVOID *v62; // r12
  ULONG v63; // ecx
  USHORT v64; // ax
  __int64 v65; // rcx
  _QWORD *v66; // rax
  __int64 v67; // rcx
  int v68; // ecx
  ULONG v69[2]; // [rsp+30h] [rbp-18h] BYREF
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+40h]
  ULONG BackTraceHash; // [rsp+A0h] [rbp+58h] BYREF

  BackTraceHash = 0;
  v9 = SkmiLockFaultChain(a2);
  if ( (*(_DWORD *)(a3 + 32) & 2) != 0 )
  {
    if ( !v9 )
      return 3221225494LL;
    PteTrace = SkmiGetPteTrace(0, a2, 0, v9, *(_QWORD *)a2);
    v11 = PteTrace;
    if ( PteTrace )
    {
      v12 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0
        && KeGetPcr()->NtTib.StackBase
        && !RtlCaptureStackBackTrace(v13, 8u, v12, &BackTraceHash) )
      {
        *(_QWORD *)(v11 + 40) = retaddr;
        *v12 = (PVOID)SkmiGetInstructionPointer(v15, v14);
      }
    }
    if ( a2 < 0xFFFFF6FB7DBED000uLL || a2 >= 0xFFFFF6FB7DBED800uLL )
    {
LABEL_17:
      *(_QWORD *)a2 = v9;
      return 3221225494LL;
    }
    StackBase = KeGetPcr()->NtTib.StackBase;
    if ( !StackBase )
    {
      v17 = 0;
      goto LABEL_13;
    }
LABEL_11:
    v17 = StackBase[10];
LABEL_13:
    v18 = *(_QWORD *)(v17 + 232);
    if ( v18 )
    {
      v19 = SkiKvaShadowMode;
      *(_QWORD *)(v18 + 8 * (((__int64)a2 >> 3) & 0x1FF)) = v9;
      if ( v19 != 2 && (v9 & 1) != 0 )
        v9 |= 0x8000000000000000uLL;
    }
    goto LABEL_17;
  }
  *(_QWORD *)v69 = v9;
  SKMI_UNSWIZZLE_INVALID_PTE(v69);
  v21 = a5;
  v22 = SkmiState + (*(__int64 *)v69 >> 16);
  if ( !a5 && *(_QWORD *)a3 != a3 )
  {
    v9 = SkmiDisconnectFromFaultChainWithLock(a3, SkmiState + (*(__int64 *)v69 >> 16));
    v23 = SkmiGetPteTrace(0, a2, 0, v9, *(_QWORD *)a2);
    v25 = v23;
    if ( v23 )
    {
      v26 = (PVOID *)(v23 + 32);
      memset_0((void *)(v23 + 32), 0, (unsigned int)(v21 + 64));
      v24 = 0;
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        if ( KeGetPcr()->NtTib.StackBase )
        {
          v28 = RtlCaptureStackBackTrace(v27, v21 + 8, v26, &BackTraceHash);
          v24 = 0;
          if ( !v28 )
          {
            *(_QWORD *)(v25 + 40) = retaddr;
            *v26 = (PVOID)SkmiGetInstructionPointer(v30, v29);
          }
        }
      }
    }
    if ( a2 < 0xFFFFF6FB7DBED000uLL || a2 >= 0xFFFFF6FB7DBED800uLL )
      goto LABEL_17;
    StackBase = KeGetPcr()->NtTib.StackBase;
    if ( !StackBase )
    {
      v17 = v24;
      goto LABEL_13;
    }
    goto LABEL_11;
  }
  if ( (*(_DWORD *)(v22 + 32) & 1) != 0 )
  {
    v31 = SkmiGetPteTrace(0, a2, 0, v9, *(_QWORD *)a2);
    v33 = v31;
    if ( v31 )
    {
      v34 = (PVOID *)(v31 + 32);
      memset_0((void *)(v31 + 32), 0, 0x40u);
      v32 = 0;
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        if ( KeGetPcr()->NtTib.StackBase )
        {
          v36 = RtlCaptureStackBackTrace(v35, 8u, v34, &BackTraceHash);
          v32 = 0;
          if ( !v36 )
          {
            *(_QWORD *)(v33 + 40) = retaddr;
            *v34 = (PVOID)SkmiGetInstructionPointer(v38, v37);
          }
        }
      }
    }
    if ( a2 >= 0xFFFFF6FB7DBED000uLL && a2 < 0xFFFFF6FB7DBED800uLL )
    {
      v39 = KeGetPcr()->NtTib.StackBase;
      v40 = v39 ? v39[10] : v32;
      v41 = *(_QWORD *)(v40 + 232);
      if ( v41 )
      {
        v42 = SkiKvaShadowMode;
        *(_QWORD *)(v41 + 8 * (((__int64)a2 >> 3) & 0x1FF)) = v9;
        if ( v42 != 2 && (v9 & 1) != 0 )
          v9 |= 0x8000000000000000uLL;
      }
    }
    *(_QWORD *)a2 = v9;
    return 259;
  }
  v43 = *(_QWORD *)(a3 + 40);
  if ( v43 )
    SkmiPushDataTraceState(v43, &BackTraceHash);
  v44 = *(_QWORD *)(v22 + 16) & 0x800LL;
  if ( v44 && (*(_QWORD *)(v22 + 16) & 0x400LL) != 0 )
  {
    SkAcquireSpinLockSharedAtDpcLevel(a1 + 192);
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 192));
    SkTrackSpinLockRelease();
    v45 = -1073741802;
LABEL_71:
    if ( (*(_DWORD *)(a3 + 32) & 1) == 0 )
      v9 = SkmiDisconnectFromFaultChainWithLock(a3, v22);
    v59 = SkmiGetPteTrace(0, a2, 0, v9, *(_QWORD *)a2);
    v61 = v59;
    if ( v59 )
    {
      v62 = (PVOID *)(v59 + 32);
      memset_0((void *)(v59 + 32), 0, 0x40u);
      v60 = 0;
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        if ( KeGetPcr()->NtTib.StackBase )
        {
          v64 = RtlCaptureStackBackTrace(v63, 8u, v62, v69);
          v60 = 0;
          if ( !v64 )
          {
            *(_QWORD *)(v61 + 40) = retaddr;
            *v62 = (PVOID)SkmiGetInstructionPointer(v65, v56);
          }
        }
      }
    }
    if ( a2 >= 0xFFFFF6FB7DBED000uLL && a2 < 0xFFFFF6FB7DBED800uLL )
    {
      v66 = KeGetPcr()->NtTib.StackBase;
      v67 = v66 ? v66[10] : v60;
      v56 = *(_QWORD *)(v67 + 232);
      if ( v56 )
      {
        v68 = SkiKvaShadowMode;
        *(_QWORD *)(v56 + 8 * (((__int64)a2 >> 3) & 0x1FF)) = v9;
        if ( v68 != 2 && (v9 & 1) != 0 )
          v9 |= 0x8000000000000000uLL;
      }
    }
    *(_QWORD *)a2 = v9;
    goto LABEL_88;
  }
  v46 = *(_QWORD *)(v22 + 40);
  v47 = *a4 & 0xFFFFFFFFFFFFFLL;
  if ( v46 )
  {
    if ( (*(_DWORD *)(v22 + 32) & 4) != 0 )
    {
      v48 = *(unsigned int *)(v22 + 36);
      if ( (*(_QWORD *)(*(_QWORD *)(v46 + 8) + 8 * v48) & 0x400LL) != 0 && (*(_QWORD *)(v22 + 16) & 0x400LL) != 0 )
      {
        SKMI_IMAGE_SECURITY(519, v48, v46, v47, 0);
LABEL_55:
        v45 = -1073741818;
        goto LABEL_71;
      }
    }
    if ( (int)SkmiLockImagePage(*(_QWORD *)(v22 + 40), *(unsigned int *)(v22 + 36), v47, 2) < 0 )
    {
      v45 = -1073741818;
      goto LABEL_71;
    }
    SkmiIncrementImagePageReferenceCount(v47);
    SkmiUnlockImagePage(*(_QWORD *)(v22 + 40), *(unsigned int *)(v22 + 36), 0);
    v49 = v47 << 12;
    v50 = (v49
         ^ (SkmiProtectionToPte[(*(_DWORD *)(v22 + 16) >> 5) & 0x1F]
          ^ v49)
         & 0xFFF0000000000FFFuLL)
        & 0xFFFFFFFFFFFFFFDBuLL
        | 4;
    if ( v21 )
      v50 = v49 ^ (SkmiProtectionToPte[(*(_DWORD *)(v22 + 16) >> 5) & 0x1F] ^ v49) & 0xFFF0000000000FFFuLL | 4;
    *(_QWORD *)(a3 + 16) = v50 | 0x80000000000000LL;
    v45 = 0;
  }
  else
  {
    if ( !v44 )
    {
      *(_DWORD *)(a3 + 32) |= 1u;
      v9 = SkmiMoveToHeadOfFaultChain(a3, v22);
      v45 = 259;
      goto LABEL_71;
    }
    *(_QWORD *)v69 = *(_QWORD *)(v22 + 16);
    SKMI_UNSWIZZLE_INVALID_PTE(v69);
    if ( ((*(_QWORD *)v69 >> 12) & 0xFFFFFFFFFFLL) != v47 )
    {
      SKMI_SECURITY(513);
      goto LABEL_55;
    }
    v53 = v47 << 12;
    v54 = (v51 >> 5) & 0x1F;
    v55 = (v53 ^ (SkmiProtectionToPte[v54] ^ v53) & 0xFFF0000000000FFFuLL) & 0xFFFFFFFFFFFFFFDBuLL | 4;
    if ( v21 )
      v55 = v53 ^ (SkmiProtectionToPte[v54] ^ v53) & 0xFFF0000000000FFFuLL | 4;
    *(_QWORD *)(a3 + 16) = v55;
    if ( *(_QWORD *)(a1 + 144) != a1 + 144 )
    {
      SkmiModifyBlockedFaultPte(a1, a2, v22);
      v52 = 0;
    }
    v45 = v52;
  }
  SkmiCompleteFaultChain(a2, a3);
LABEL_88:
  if ( *(_QWORD *)(a3 + 40) )
    SkmiPopDataTraceState(BackTraceHash, v56, v57, v58);
  return v45;
}

```

## disassembly

```asm
0x14003a10c  push    rbp
0x14003a10e  push    rbx
0x14003a10f  push    rsi
0x14003a110  push    rdi
0x14003a111  push    r12
0x14003a113  push    r13
0x14003a115  push    r14
0x14003a117  push    r15
0x14003a119  mov     rbp, rsp
0x14003a11c  sub     rsp, 48h
0x14003a120  mov     r13, rcx
0x14003a123  xor     r15d, r15d
0x14003a126  mov     rcx, rdx
0x14003a129  mov     [rbp+BackTraceHash], r15d
0x14003a12d  mov     rdi, r9
0x14003a130  mov     r14, r8
0x14003a133  mov     rsi, rdx
0x14003a136  call    SkmiLockFaultChain
0x14003a13b  mov     rbx, rax
0x14003a13e  mov     eax, [r14+20h]
0x14003a142  test    al, 2
0x14003a144  jz      loc_14003A245
0x14003a14a  test    rbx, rbx
0x14003a14d  jz      loc_14003A23B
0x14003a153  mov     rax, [rsi]
0x14003a156  mov     r9, rbx
0x14003a159  xor     r8d, r8d
0x14003a15c  mov     [rsp+48h+var_28], rax
0x14003a161  mov     rdx, rsi
0x14003a164  xor     ecx, ecx
0x14003a166  call    SkmiGetPteTrace
0x14003a16b  mov     rdi, rax
0x14003a16e  test    rax, rax
0x14003a171  jz      short loc_14003A1C4
0x14003a173  lea     r14, [rax+20h]
0x14003a177  xor     edx, edx; Val
0x14003a179  mov     rcx, r14; void *
0x14003a17c  lea     r8d, [r15+40h]; Size
0x14003a180  call    memset_0
0x14003a185  test    cs:SkmiFlags, 400000h
0x14003a18f  jz      short loc_14003A1C4
0x14003a191  mov     rax, gs:8
0x14003a19a  test    rax, rax
0x14003a19d  jz      short loc_14003A1C4
0x14003a19f  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14003a1a3  mov     r8, r14; BackTrace
0x14003a1a6  lea     edx, [r15+8]; FramesToCapture
0x14003a1aa  call    RtlCaptureStackBackTrace
0x14003a1af  test    ax, ax
0x14003a1b2  jnz     short loc_14003A1C4
0x14003a1b4  mov     rax, [rbp+40h]
0x14003a1b8  mov     [rdi+28h], rax
0x14003a1bc  call    SkmiGetInstructionPointer
0x14003a1c1  mov     [r14], rax
0x14003a1c4  mov     rax, 0FFFFF6FB7DBED000h
0x14003a1ce  mov     rax, rax
0x14003a1d1  cmp     rsi, rax
0x14003a1d4  jb      short loc_14003A238
0x14003a1d6  mov     rax, 0FFFFF6FB7DBED800h
0x14003a1e0  mov     rax, rax
0x14003a1e3  cmp     rsi, rax
0x14003a1e6  jnb     short loc_14003A238
0x14003a1e8  mov     rax, gs:8
0x14003a1f1  test    rax, rax
0x14003a1f4  jz      short loc_14003A1FC
0x14003a1f6  mov     rcx, [rax+50h]
0x14003a1fa  jmp     short loc_14003A1FF
0x14003a1fc  mov     rcx, r15
0x14003a1ff  mov     rdx, [rcx+0E8h]
0x14003a206  test    rdx, rdx
0x14003a209  jz      short loc_14003A238
0x14003a20b  mov     ecx, cs:SkiKvaShadowMode
0x14003a211  mov     rax, rsi
0x14003a214  sar     rax, 3
0x14003a218  and     eax, 1FFh
0x14003a21d  mov     [rdx+rax*8], rbx
0x14003a221  cmp     ecx, 2
0x14003a224  jz      short loc_14003A238
0x14003a226  test    bl, 1
0x14003a229  jz      short loc_14003A238
0x14003a22b  mov     rax, 8000000000000000h
0x14003a235  or      rbx, rax
0x14003a238  mov     [rsi], rbx
0x14003a23b  mov     eax, 0C0000016h
0x14003a240  jmp     loc_14003A777
0x14003a245  lea     rcx, [rbp+var_18]
0x14003a249  mov     qword ptr [rbp+var_18], rbx
0x14003a24d  call    SKMI_UNSWIZZLE_INVALID_PTE
0x14003a252  mov     r15, qword ptr [rbp+var_18]
0x14003a256  xor     r11d, r11d
0x14003a259  mov     r12d, [rbp+arg_20]
0x14003a25d  sar     r15, 10h
0x14003a261  add     r15, cs:SkmiState
0x14003a268  test    r12d, r12d
0x14003a26b  jnz     loc_14003A347
0x14003a271  cmp     [r14], r14
0x14003a274  jz      loc_14003A347
0x14003a27a  mov     rdx, r15
0x14003a27d  mov     rcx, r14
0x14003a280  call    SkmiDisconnectFromFaultChainWithLock
0x14003a285  mov     rbx, rax
0x14003a288  xor     r8d, r8d
0x14003a28b  mov     rax, [rsi]
0x14003a28e  mov     r9, rbx
0x14003a291  mov     rdx, rsi
0x14003a294  mov     [rsp+48h+var_28], rax
0x14003a299  xor     ecx, ecx
0x14003a29b  call    SkmiGetPteTrace
0x14003a2a0  mov     r14, rax
0x14003a2a3  test    rax, rax
0x14003a2a6  jz      short loc_14003A301
0x14003a2a8  lea     rdi, [rax+20h]
0x14003a2ac  xor     edx, edx; Val
0x14003a2ae  mov     rcx, rdi; void *
0x14003a2b1  lea     r8d, [r12+40h]; Size
0x14003a2b6  call    memset_0
0x14003a2bb  xor     r11d, r11d
0x14003a2be  test    cs:SkmiFlags, 400000h
0x14003a2c8  jz      short loc_14003A301
0x14003a2ca  mov     rax, gs:8
0x14003a2d3  test    rax, rax
0x14003a2d6  jz      short loc_14003A301
0x14003a2d8  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14003a2dc  mov     r8, rdi; BackTrace
0x14003a2df  lea     edx, [r12+8]; FramesToCapture
0x14003a2e4  call    RtlCaptureStackBackTrace
0x14003a2e9  xor     r11d, r11d
0x14003a2ec  test    ax, ax
0x14003a2ef  jnz     short loc_14003A301
0x14003a2f1  mov     rax, [rbp+40h]
0x14003a2f5  mov     [r14+28h], rax
0x14003a2f9  call    SkmiGetInstructionPointer
0x14003a2fe  mov     [rdi], rax
0x14003a301  mov     rax, 0FFFFF6FB7DBED000h
0x14003a30b  mov     rax, rax
0x14003a30e  cmp     rsi, rax
0x14003a311  jb      loc_14003A238
0x14003a317  mov     rax, 0FFFFF6FB7DBED800h
0x14003a321  mov     rax, rax
0x14003a324  cmp     rsi, rax
0x14003a327  jnb     loc_14003A238
0x14003a32d  mov     rax, gs:8
0x14003a336  test    rax, rax
0x14003a339  jnz     loc_14003A1F6
0x14003a33f  mov     rcx, r11
0x14003a342  jmp     loc_14003A1FF
0x14003a347  mov     eax, [r15+20h]
0x14003a34b  test    al, 1
0x14003a34d  jz      loc_14003A44B
0x14003a353  mov     rax, [rsi]
0x14003a356  mov     r9, rbx
0x14003a359  xor     r8d, r8d
0x14003a35c  mov     [rsp+48h+var_28], rax
0x14003a361  mov     rdx, rsi
0x14003a364  xor     ecx, ecx
0x14003a366  call    SkmiGetPteTrace
0x14003a36b  mov     rdi, rax
0x14003a36e  test    rax, rax
0x14003a371  jz      short loc_14003A3CA
0x14003a373  xor     edx, edx; Val
0x14003a375  lea     r14, [rax+20h]
0x14003a379  mov     rcx, r14; void *
0x14003a37c  lea     r8d, [rdx+40h]; Size
0x14003a380  call    memset_0
0x14003a385  xor     r11d, r11d
0x14003a388  test    cs:SkmiFlags, 400000h
0x14003a392  jz      short loc_14003A3CA
0x14003a394  mov     rax, gs:8
0x14003a39d  test    rax, rax
0x14003a3a0  jz      short loc_14003A3CA
0x14003a3a2  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14003a3a6  mov     r8, r14; BackTrace
0x14003a3a9  lea     edx, [r11+8]; FramesToCapture
0x14003a3ad  call    RtlCaptureStackBackTrace
0x14003a3b2  xor     r11d, r11d
0x14003a3b5  test    ax, ax
0x14003a3b8  jnz     short loc_14003A3CA
0x14003a3ba  mov     rax, [rbp+40h]
0x14003a3be  mov     [rdi+28h], rax
0x14003a3c2  call    SkmiGetInstructionPointer
0x14003a3c7  mov     [r14], rax
0x14003a3ca  mov     rax, 0FFFFF6FB7DBED000h
0x14003a3d4  mov     rax, rax
0x14003a3d7  cmp     rsi, rax
0x14003a3da  jb      short loc_14003A43E
0x14003a3dc  mov     rax, 0FFFFF6FB7DBED800h
0x14003a3e6  mov     rax, rax
0x14003a3e9  cmp     rsi, rax
0x14003a3ec  jnb     short loc_14003A43E
0x14003a3ee  mov     rax, gs:8
0x14003a3f7  test    rax, rax
0x14003a3fa  jz      short loc_14003A402
0x14003a3fc  mov     rcx, [rax+50h]
0x14003a400  jmp     short loc_14003A405
0x14003a402  mov     rcx, r11
0x14003a405  mov     rdx, [rcx+0E8h]
0x14003a40c  test    rdx, rdx
0x14003a40f  jz      short loc_14003A43E
0x14003a411  mov     ecx, cs:SkiKvaShadowMode
0x14003a417  mov     rax, rsi
0x14003a41a  sar     rax, 3
0x14003a41e  and     eax, 1FFh
0x14003a423  mov     [rdx+rax*8], rbx
0x14003a427  cmp     ecx, 2
0x14003a42a  jz      short loc_14003A43E
0x14003a42c  test    bl, 1
0x14003a42f  jz      short loc_14003A43E
0x14003a431  mov     rax, 8000000000000000h
0x14003a43b  or      rbx, rax
0x14003a43e  mov     [rsi], rbx
0x14003a441  mov     eax, 103h
0x14003a446  jmp     loc_14003A777
0x14003a44b  mov     rcx, [r14+28h]
0x14003a44f  test    rcx, rcx
0x14003a452  jz      short loc_14003A45D
0x14003a454  lea     rdx, [rbp+BackTraceHash]
0x14003a458  call    SkmiPushDataTraceState
0x14003a45d  mov     r8, [r15+10h]
0x14003a461  mov     rax, r8
0x14003a464  mov     rdx, r8
0x14003a467  and     eax, 800h
0x14003a46c  shr     rdx, 0Ah
0x14003a470  test    rax, rax
0x14003a473  jz      short loc_14003A49E
0x14003a475  test    dl, 1
0x14003a478  jz      short loc_14003A49E
0x14003a47a  lea     rdi, [r13+0C0h]
0x14003a481  mov     rcx, rdi
0x14003a484  call    SkAcquireSpinLockSharedAtDpcLevel
0x14003a489  lock dec dword ptr [rdi]
0x14003a48c  call    SkTrackSpinLockRelease
0x14003a491  mov     edi, 0C0000016h
0x14003a496  xor     r11d, r11d
0x14003a499  jmp     loc_14003A661
0x14003a49e  mov     rdi, [rdi]
0x14003a4a1  mov     rcx, 0FFFFFFFFFFFFFh
0x14003a4ab  mov     r10, [r15+28h]
0x14003a4af  and     rdi, rcx
0x14003a4b2  test    r10, r10
0x14003a4b5  jz      loc_14003A59A
0x14003a4bb  mov     eax, [r15+20h]
0x14003a4bf  test    al, 4
0x14003a4c1  jz      short loc_14003A503
0x14003a4c3  mov     rax, [r10+8]
0x14003a4c7  mov     r11d, [r15+24h]
0x14003a4cb  test    qword ptr [rax+r11*8], 400h
0x14003a4d3  setnz   cl
0x14003a4d6  test    dl, 1
0x14003a4d9  setnz   al
0x14003a4dc  test    al, cl
0x14003a4de  jz      short loc_14003A503
0x14003a4e0  mov     r9, rdi
0x14003a4e3  mov     [rsp+48h+var_28], 0
0x14003a4ec  mov     r8, r10
0x14003a4ef  mov     edx, r11d
0x14003a4f2  mov     ecx, 207h
0x14003a4f7  call    SKMI_IMAGE_SECURITY
0x14003a4fc  mov     edi, 0C0000006h
0x14003a501  jmp     short loc_14003A496
0x14003a503  mov     edx, [r15+24h]
0x14003a507  mov     r9d, 2
0x14003a50d  mov     r8, rdi
0x14003a510  mov     rcx, r10
0x14003a513  call    SkmiLockImagePage
0x14003a518  xor     r11d, r11d
0x14003a51b  test    eax, eax
0x14003a51d  jns     short loc_14003A529
0x14003a51f  mov     edi, 0C0000006h
0x14003a524  jmp     loc_14003A661
0x14003a529  xor     edx, edx
0x14003a52b  mov     rcx, rdi; BugCheckParameter3
0x14003a52e  call    SkmiIncrementImagePageReferenceCount
0x14003a533  mov     edx, [r15+24h]
0x14003a537  xor     r8d, r8d
0x14003a53a  mov     rcx, [r15+28h]
0x14003a53e  call    SkmiUnlockImagePage
0x14003a543  mov     eax, [r15+10h]
0x14003a547  lea     rdx, SkmiProtectionToPte
0x14003a54e  shr     rax, 5
0x14003a552  and     eax, 1Fh
0x14003a555  shl     rdi, 0Ch
0x14003a559  mov     rcx, rdi
0x14003a55c  xor     rcx, [rdx+rax*8]
0x14003a560  mov     rax, 0FFF0000000000FFFh
0x14003a56a  and     rcx, rax
0x14003a56d  xor     rcx, rdi
0x14003a570  or      rcx, 4
0x14003a574  mov     rax, rcx
0x14003a577  and     rax, 0FFFFFFFFFFFFFFDFh
0x14003a57b  test    r12d, r12d
0x14003a57e  cmovnz  rax, rcx
0x14003a582  mov     rcx, 80000000000000h
0x14003a58c  or      rax, rcx
0x14003a58f  mov     [r14+10h], rax
0x14003a593  xor     edi, edi
0x14003a595  jmp     loc_14003A639
0x14003a59a  test    rax, rax
0x14003a59d  jz      loc_14003A649
0x14003a5a3  lea     rcx, [rbp+var_18]
0x14003a5a7  mov     qword ptr [rbp+var_18], r8
  ... truncated ...
```
