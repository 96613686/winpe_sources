# SkmiWriteNtPtesWorker

- ea: `0x140080394`
- end: `0x1400809d4`
- name: `SkmiWriteNtPtesWorker`
- size: `1600`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140003780`
- `0x140009940`
- `0x14000c8d0`
- `0x14002b534`
- `0x14002bdf4`
- `0x140080394`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiWriteNtPtesWorker(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 StackBase; // rcx
  unsigned int v6; // r12d
  __int64 *HyperspacePte; // rax
  __int64 v8; // rbx
  __int64 v9; // rsi
  unsigned __int64 v10; // rbx
  __int64 PteTrace; // rax
  __int64 v12; // rbp
  PVOID *v13; // r14
  _QWORD *v14; // rax
  __int64 v15; // r15
  __int64 v16; // r14
  unsigned __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // r13
  PVOID *v20; // rbp
  PVOID v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  int v27; // ecx
  __int64 v28; // rsi
  __int64 v29; // r14
  __int64 v30; // rbx
  __int64 v31; // rbp
  __int64 v32; // rax
  __int64 v33; // r13
  PVOID *v34; // r12
  PVOID v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  int v41; // ecx
  __int64 v42; // rsi
  __int64 v43; // r15
  __int64 v44; // rax
  int v45; // r9d
  __int64 v46; // rbp
  PVOID *v47; // rbx
  PVOID v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  _QWORD *v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rax
  int v55; // r9d
  __int64 v56; // rbp
  PVOID *v57; // rbx
  PVOID v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // rcx
  _QWORD *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v65; // [rsp+30h] [rbp-58h]
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v67; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v68; // [rsp+98h] [rbp+10h]
  ULONG BackTraceHash; // [rsp+A0h] [rbp+18h] BYREF
  __int64 *v70; // [rsp+A8h] [rbp+20h]

  v67 = a1;
  StackBase = 0xFFFFE80000000000uLL;
  if ( *(_QWORD *)a1 > 0xFFFFFFFFFFuLL )
    __fastfail(0x3Fu);
  v6 = *(_DWORD *)(a1 + 8);
  v68 = v6;
  if ( v6 < 0x200 )
  {
    v70 = 0;
    v15 = 0;
  }
  else
  {
    v6 = 0;
    v68 = 0;
    HyperspacePte = (__int64 *)SkmiGetHyperspacePte(0xFFFFE80000000000uLL, a2, a3, a4);
    v8 = *(_QWORD *)(a1 + 16);
    v9 = (__int64)HyperspacePte;
    v70 = HyperspacePte;
    v10 = (v8 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000021uLL;
    PteTrace = SkmiGetPteTrace(0, (_DWORD)HyperspacePte, 0, v10, *HyperspacePte);
    v12 = PteTrace;
    if ( PteTrace )
    {
      v13 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        StackBase = (unsigned __int64)KeGetPcr()->NtTib.StackBase;
        if ( StackBase )
        {
          if ( !RtlCaptureStackBackTrace(StackBase, 8u, v13, &BackTraceHash) )
          {
            *(_QWORD *)(v12 + 40) = retaddr;
            *v13 = (PVOID)SkmiGetInstructionPointer(StackBase, a2);
          }
        }
      }
    }
    if ( (unsigned __int64)v9 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v9 < 0xFFFFF6FB7DBED800uLL )
    {
      v14 = KeGetPcr()->NtTib.StackBase;
      StackBase = v14 ? v14[10] : 0LL;
      a2 = *(_QWORD *)(StackBase + 232);
      if ( a2 )
      {
        StackBase = (unsigned int)SkiKvaShadowMode;
        *(_QWORD *)(a2 + 8 * ((v9 >> 3) & 0x1FF)) = v10;
        if ( (_DWORD)StackBase != 2 && (v10 & 1) != 0 )
          v10 |= 0x8000000000000000uLL;
      }
    }
    *(_QWORD *)v9 = v10;
    v15 = v9 << 25 >> 16;
  }
  v16 = SkmiGetHyperspacePte(StackBase, a2, a3, a4);
  v65 = v16;
  v17 = (*(_QWORD *)a1 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000063uLL;
  v18 = SkmiGetPteTrace(0, v16, 0, (*(_DWORD *)a1 << 12) ^ 0x63u, *(_QWORD *)v16);
  v19 = v18;
  if ( v18 )
  {
    v20 = (PVOID *)(v18 + 32);
    memset_0((void *)(v18 + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v21 = KeGetPcr()->NtTib.StackBase;
      if ( v21 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v21, 8u, v20, &BackTraceHash) )
        {
          *(_QWORD *)(v19 + 40) = retaddr;
          *v20 = (PVOID)SkmiGetInstructionPointer(v23, v22);
        }
      }
    }
  }
  if ( (unsigned __int64)v16 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v16 < 0xFFFFF6FB7DBED800uLL )
  {
    v24 = KeGetPcr()->NtTib.StackBase;
    v25 = v24 ? v24[10] : 0LL;
    v26 = *(_QWORD *)(v25 + 232);
    if ( v26 )
    {
      v27 = SkiKvaShadowMode;
      *(_QWORD *)(v26 + 8 * ((v16 >> 3) & 0x1FF)) = v17;
      if ( v27 != 2 && (v17 & 1) != 0 )
        v17 |= 0x8000000000000000uLL;
    }
  }
  *(_QWORD *)v16 = v17;
  v28 = v67;
  v29 = v16 << 25 >> 16;
  while ( v15 )
  {
    v30 = *(_QWORD *)(v15 + 8LL * v6);
    if ( v30 )
      goto LABEL_39;
LABEL_59:
    v68 = ++v6;
    if ( v6 >= 0x200 )
      goto LABEL_60;
  }
  v30 = *(_QWORD *)(v28 + 24);
LABEL_39:
  v31 = v29 + 8LL * v6;
  if ( ((unsigned __int8)v30 & *(_BYTE *)v31 & 1) != 0 && (v30 & 2) != 0 && (*(_QWORD *)v31 & 0x40) != 0 )
    v30 |= 0x40uLL;
  v32 = SkmiGetPteTrace(0, (unsigned int)v29 + 8 * v6, 0, v30, *(_QWORD *)v31);
  v33 = v32;
  if ( v32 )
  {
    v34 = (PVOID *)(v32 + 32);
    memset_0((void *)(v32 + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v35 = KeGetPcr()->NtTib.StackBase;
      if ( v35 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v35, 8u, v34, (PULONG)&v67) )
        {
          *(_QWORD *)(v33 + 40) = retaddr;
          *v34 = (PVOID)SkmiGetInstructionPointer(v37, v36);
        }
      }
    }
    v6 = v68;
  }
  if ( (unsigned __int64)v31 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v31 < 0xFFFFF6FB7DBED800uLL )
  {
    v38 = KeGetPcr()->NtTib.StackBase;
    v39 = v38 ? v38[10] : 0LL;
    v40 = *(_QWORD *)(v39 + 232);
    if ( v40 )
    {
      v41 = SkiKvaShadowMode;
      *(_QWORD *)(v40 + 8 * ((v31 >> 3) & 0x1FF)) = v30;
      if ( v41 != 2 && (v30 & 1) != 0 )
        v30 |= 0x8000000000000000uLL;
    }
  }
  *(_QWORD *)v31 = v30;
  if ( v15 )
    goto LABEL_59;
LABEL_60:
  v42 = (__int64)v70;
  v43 = (int)ShvlFlushEntireTb(0, 0);
  v44 = SkmiGetPteTrace(0, v65, 0, 0, *(_QWORD *)v65);
  v46 = v44;
  if ( v44 )
  {
    v47 = (PVOID *)(v44 + 32);
    memset_0((void *)(v44 + 32), 0, (unsigned int)(v45 + 64));
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v48 = KeGetPcr()->NtTib.StackBase;
      if ( v48 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v48, 8u, v47, (PULONG)&v67) )
        {
          *(_QWORD *)(v46 + 40) = retaddr;
          *v47 = (PVOID)SkmiGetInstructionPointer(v50, v49);
        }
      }
    }
  }
  if ( (unsigned __int64)v65 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v65 < 0xFFFFF6FB7DBED800uLL )
  {
    v51 = KeGetPcr()->NtTib.StackBase;
    v52 = v51 ? v51[10] : 0LL;
    v53 = *(_QWORD *)(v52 + 232);
    if ( v53 )
      *(_QWORD *)(v53 + 8 * ((v65 >> 3) & 0x1FF)) = 0;
  }
  *(_QWORD *)v65 = 0;
  SkmiReleaseHyperspacePte(v65);
  if ( v42 )
  {
    v54 = SkmiGetPteTrace(0, v42, 0, 0, *(_QWORD *)v42);
    v56 = v54;
    if ( v54 )
    {
      v57 = (PVOID *)(v54 + 32);
      memset_0((void *)(v54 + 32), 0, (unsigned int)(v55 + 64));
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v58 = KeGetPcr()->NtTib.StackBase;
        if ( v58 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v58, 8u, v57, (PULONG)&v67) )
          {
            *(_QWORD *)(v56 + 40) = retaddr;
            *v57 = (PVOID)SkmiGetInstructionPointer(v60, v59);
          }
        }
      }
    }
    if ( (unsigned __int64)v42 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v42 < 0xFFFFF6FB7DBED800uLL )
    {
      v61 = KeGetPcr()->NtTib.StackBase;
      if ( v61 )
        v62 = v61[10];
      else
        v62 = 0;
      v63 = *(_QWORD *)(v62 + 232);
      if ( v63 )
        *(_QWORD *)(v63 + 8 * ((v42 >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)v42 = 0;
    SkmiReleaseHyperspacePte(v42);
  }
  return v43;
}

```

## disassembly

```asm
0x140080394  mov     [rsp+arg_0], rcx
0x140080399  push    rbx
0x14008039a  push    rbp
0x14008039b  push    rsi
0x14008039c  push    rdi
0x14008039d  push    r12
0x14008039f  push    r13
0x1400803a1  push    r14
0x1400803a3  push    r15
0x1400803a5  sub     rsp, 48h
0x1400803a9  mov     r13, rcx
0x1400803ac  mov     rax, 0FFFFEFFFFFFFFFFFh
0x1400803b6  mov     rcx, 0FFFFE80000000000h
0x1400803c0  sub     rax, rcx
0x1400803c3  sar     rax, 3
0x1400803c7  cmp     [r13+0], rax
0x1400803cb  ja      loc_1400809CD
0x1400803d1  mov     r12d, [r13+8]
0x1400803d5  xor     edi, edi
0x1400803d7  mov     [rsp+88h+arg_8], r12d
0x1400803df  mov     rbp, 0FFFFFFFFFF000h
0x1400803e9  mov     r15, 0FFFFF6FB7DBED800h
0x1400803f3  mov     r14, 0FFFFF68000000000h
0x1400803fd  cmp     r12d, 200h
0x140080404  jb      loc_14008054C
0x14008040a  mov     r12d, edi
0x14008040d  mov     [rsp+88h+arg_8], edi
0x140080414  call    SkmiGetHyperspacePte
0x140080419  mov     rbx, [r13+10h]
0x14008041d  mov     rsi, rax
0x140080420  mov     [rsp+88h+arg_18], rax
0x140080428  xor     r8d, r8d
0x14008042b  shl     rbx, 0Ch
0x14008042f  mov     rax, 8000000000000021h
0x140080439  and     rbx, rbp
0x14008043c  mov     rdx, rsi
0x14008043f  xor     rbx, rax
0x140080442  xor     ecx, ecx
0x140080444  mov     rax, [rsi]
0x140080447  mov     r9, rbx
0x14008044a  mov     [rsp+88h+var_68], rax
0x14008044f  call    SkmiGetPteTrace
0x140080454  mov     rbp, rax
0x140080457  test    rax, rax
0x14008045a  jz      short loc_1400804BE
0x14008045c  lea     r14, [rax+20h]
0x140080460  xor     edx, edx; Val
0x140080462  mov     rcx, r14; void *
0x140080465  lea     r8d, [rdi+40h]; Size
0x140080469  call    memset_0
0x14008046e  test    cs:SkmiFlags, 400000h
0x140080478  jz      short loc_1400804B4
0x14008047a  mov     rcx, gs:8; FramesToSkip
0x140080483  test    rcx, rcx
0x140080486  jz      short loc_1400804B4
0x140080488  lea     r9, [rsp+88h+BackTraceHash]; BackTraceHash
0x140080490  mov     r8, r14; BackTrace
0x140080493  lea     edx, [rdi+8]; FramesToCapture
0x140080496  call    RtlCaptureStackBackTrace
0x14008049b  test    ax, ax
0x14008049e  jnz     short loc_1400804B4
0x1400804a0  mov     rax, [rsp+88h]
0x1400804a8  mov     [rbp+28h], rax
0x1400804ac  call    SkmiGetInstructionPointer
0x1400804b1  mov     [r14], rax
0x1400804b4  mov     r14, 0FFFFF68000000000h
0x1400804be  mov     rax, 0FFFFF6FB7DBED000h
0x1400804c8  mov     rax, rax
0x1400804cb  cmp     rsi, rax
0x1400804ce  jb      short loc_140080528
0x1400804d0  mov     rax, r15
0x1400804d3  cmp     rsi, rax
0x1400804d6  jnb     short loc_140080528
0x1400804d8  mov     rax, gs:8
0x1400804e1  test    rax, rax
0x1400804e4  jz      short loc_1400804EC
0x1400804e6  mov     rcx, [rax+50h]
0x1400804ea  jmp     short loc_1400804EF
0x1400804ec  mov     rcx, rdi
0x1400804ef  mov     rdx, [rcx+0E8h]
0x1400804f6  test    rdx, rdx
0x1400804f9  jz      short loc_140080528
0x1400804fb  mov     ecx, cs:SkiKvaShadowMode
0x140080501  mov     rax, rsi
0x140080504  sar     rax, 3
0x140080508  and     eax, 1FFh
0x14008050d  mov     [rdx+rax*8], rbx
0x140080511  cmp     ecx, 2
0x140080514  jz      short loc_140080528
0x140080516  test    bl, 1
0x140080519  jz      short loc_140080528
0x14008051b  mov     rax, 8000000000000000h
0x140080525  or      rbx, rax
0x140080528  mov     r15, rsi
0x14008052b  mov     [rsi], rbx
0x14008052e  shl     r15, 19h
0x140080532  mov     rax, r14
0x140080535  shl     rax, 19h
0x140080539  mov     rbp, 0FFFFFFFFFF000h
0x140080543  sub     r15, rax
0x140080546  sar     r15, 10h
0x14008054a  jmp     short loc_14008055A
0x14008054c  mov     rsi, rdi
0x14008054f  mov     [rsp+88h+arg_18], rdi
0x140080557  mov     r15, rdi
0x14008055a  call    SkmiGetHyperspacePte
0x14008055f  mov     rbx, [r13+0]
0x140080563  mov     r14, rax
0x140080566  mov     [rsp+88h+var_58], rax
0x14008056b  xor     r8d, r8d
0x14008056e  shl     rbx, 0Ch
0x140080572  mov     rax, 8000000000000063h
0x14008057c  and     rbx, rbp
0x14008057f  mov     rdx, r14
0x140080582  xor     rbx, rax
0x140080585  xor     ecx, ecx
0x140080587  mov     rax, [r14]
0x14008058a  mov     r9, rbx
0x14008058d  mov     [rsp+88h+var_68], rax
0x140080592  call    SkmiGetPteTrace
0x140080597  mov     r13, rax
0x14008059a  test    rax, rax
0x14008059d  jz      short loc_1400805FA
0x14008059f  xor     edx, edx; Val
0x1400805a1  lea     rbp, [rax+20h]
0x1400805a5  mov     rcx, rbp; void *
0x1400805a8  lea     r8d, [rdx+40h]; Size
0x1400805ac  call    memset_0
0x1400805b1  test    cs:SkmiFlags, 400000h
0x1400805bb  jz      short loc_1400805FA
0x1400805bd  mov     rcx, gs:8; FramesToSkip
0x1400805c6  test    rcx, rcx
0x1400805c9  jz      short loc_1400805FA
0x1400805cb  lea     r9, [rsp+88h+BackTraceHash]; BackTraceHash
0x1400805d3  mov     r8, rbp; BackTrace
0x1400805d6  mov     edx, 8; FramesToCapture
0x1400805db  call    RtlCaptureStackBackTrace
0x1400805e0  test    ax, ax
0x1400805e3  jnz     short loc_1400805FA
0x1400805e5  mov     rax, [rsp+88h]
0x1400805ed  mov     [r13+28h], rax
0x1400805f1  call    SkmiGetInstructionPointer
0x1400805f6  mov     [rbp+0], rax
0x1400805fa  mov     r13, 0FFFFF6FB7DBED000h
0x140080604  mov     rax, r13
0x140080607  cmp     r14, rax
0x14008060a  jb      short loc_14008066E
0x14008060c  mov     rax, 0FFFFF6FB7DBED800h
0x140080616  mov     rax, rax
0x140080619  cmp     r14, rax
0x14008061c  jnb     short loc_14008066E
0x14008061e  mov     rax, gs:8
0x140080627  test    rax, rax
0x14008062a  jz      short loc_140080632
0x14008062c  mov     rcx, [rax+50h]
0x140080630  jmp     short loc_140080635
0x140080632  mov     rcx, rdi
0x140080635  mov     rdx, [rcx+0E8h]
0x14008063c  test    rdx, rdx
0x14008063f  jz      short loc_14008066E
0x140080641  mov     ecx, cs:SkiKvaShadowMode
0x140080647  mov     rax, r14
0x14008064a  sar     rax, 3
0x14008064e  and     eax, 1FFh
0x140080653  mov     [rdx+rax*8], rbx
0x140080657  cmp     ecx, 2
0x14008065a  jz      short loc_14008066E
0x14008065c  test    bl, 1
0x14008065f  jz      short loc_14008066E
0x140080661  mov     rax, 8000000000000000h
0x14008066b  or      rbx, rax
0x14008066e  mov     rcx, r14
0x140080671  mov     [r14], rbx
0x140080674  shl     rcx, 19h
0x140080678  mov     rax, 0FFFFF68000000000h
0x140080682  mov     rax, rax
0x140080685  shl     rax, 19h
0x140080689  sub     rcx, rax
0x14008068c  sar     rcx, 10h
0x140080690  cmp     r12d, 200h
0x140080697  jnb     loc_140080809
0x14008069d  mov     rsi, [rsp+88h+arg_0]
0x1400806a5  mov     r14, rcx
0x1400806a8  mov     eax, r12d
0x1400806ab  test    r15, r15
0x1400806ae  jz      short loc_1400806BF
0x1400806b0  mov     rbx, [r15+rax*8]
0x1400806b4  test    rbx, rbx
0x1400806b7  jz      loc_1400807E4
0x1400806bd  jmp     short loc_1400806C3
0x1400806bf  mov     rbx, [rsi+18h]
0x1400806c3  lea     rbp, [r14+rax*8]
0x1400806c7  mov     rax, [rbp+0]
0x1400806cb  mov     rcx, rax
0x1400806ce  and     rcx, rbx
0x1400806d1  test    cl, 1
0x1400806d4  jz      short loc_1400806E3
0x1400806d6  test    bl, 2
0x1400806d9  jz      short loc_1400806E3
0x1400806db  test    al, 40h
0x1400806dd  jz      short loc_1400806E3
0x1400806df  or      rbx, 40h
0x1400806e3  mov     rax, [rbp+0]
0x1400806e7  mov     r9, rbx
0x1400806ea  xor     r8d, r8d
0x1400806ed  mov     [rsp+88h+var_68], rax
0x1400806f2  mov     rdx, rbp
0x1400806f5  xor     ecx, ecx
0x1400806f7  call    SkmiGetPteTrace
0x1400806fc  mov     r13, rax
0x1400806ff  test    rax, rax
0x140080702  jz      short loc_140080767
0x140080704  xor     edx, edx; Val
0x140080706  lea     r12, [rax+20h]
0x14008070a  mov     rcx, r12; void *
0x14008070d  lea     r8d, [rdx+40h]; Size
0x140080711  call    memset_0
0x140080716  test    cs:SkmiFlags, 400000h
0x140080720  jz      short loc_14008075F
0x140080722  mov     rcx, gs:8; FramesToSkip
0x14008072b  test    rcx, rcx
0x14008072e  jz      short loc_14008075F
0x140080730  lea     r9, [rsp+88h+arg_0]; BackTraceHash
0x140080738  mov     r8, r12; BackTrace
0x14008073b  mov     edx, 8; FramesToCapture
0x140080740  call    RtlCaptureStackBackTrace
0x140080745  test    ax, ax
0x140080748  jnz     short loc_14008075F
0x14008074a  mov     rax, [rsp+88h]
0x140080752  mov     [r13+28h], rax
0x140080756  call    SkmiGetInstructionPointer
0x14008075b  mov     [r12], rax
0x14008075f  mov     r12d, [rsp+88h+arg_8]
0x140080767  mov     r13, 0FFFFF6FB7DBED000h
0x140080771  mov     rax, r13
0x140080774  cmp     rbp, rax
0x140080777  jb      short loc_1400807DB
0x140080779  mov     rax, 0FFFFF6FB7DBED800h
0x140080783  mov     rax, rax
0x140080786  cmp     rbp, rax
0x140080789  jnb     short loc_1400807DB
0x14008078b  mov     rax, gs:8
0x140080794  test    rax, rax
0x140080797  jz      short loc_14008079F
0x140080799  mov     rcx, [rax+50h]
0x14008079d  jmp     short loc_1400807A2
0x14008079f  mov     rcx, rdi
0x1400807a2  mov     rdx, [rcx+0E8h]
0x1400807a9  test    rdx, rdx
0x1400807ac  jz      short loc_1400807DB
0x1400807ae  mov     ecx, cs:SkiKvaShadowMode
0x1400807b4  mov     rax, rbp
0x1400807b7  sar     rax, 3
0x1400807bb  and     eax, 1FFh
0x1400807c0  mov     [rdx+rax*8], rbx
0x1400807c4  cmp     ecx, 2
0x1400807c7  jz      short loc_1400807DB
0x1400807c9  test    bl, 1
0x1400807cc  jz      short loc_1400807DB
0x1400807ce  mov     rax, 8000000000000000h
0x1400807d8  or      rbx, rax
0x1400807db  mov     [rbp+0], rbx
0x1400807df  test    r15, r15
0x1400807e2  jz      short loc_1400807FC
0x1400807e4  inc     r12d
0x1400807e7  mov     [rsp+88h+arg_8], r12d
0x1400807ef  cmp     r12d, 200h
0x1400807f6  jb      loc_1400806A8
0x1400807fc  mov     rsi, [rsp+88h+arg_18]
0x140080804  mov     r14, [rsp+88h+var_58]
0x140080809  xor     edx, edx
0x14008080b  xor     ecx, ecx
0x14008080d  call    ShvlFlushEntireTb
0x140080812  mov     rcx, [r14]
0x140080815  xor     r9d, r9d
0x140080818  mov     [rsp+88h+var_68], rcx
0x14008081d  xor     r8d, r8d
0x140080820  xor     ecx, ecx
0x140080822  movsxd  r15, eax
0x140080825  mov     rdx, r14
0x140080828  call    SkmiGetPteTrace
0x14008082d  mov     rbp, rax
0x140080830  test    rax, rax
0x140080833  jz      short loc_14008088F
0x140080835  lea     rbx, [rax+20h]
0x140080839  xor     edx, edx; Val
0x14008083b  mov     rcx, rbx; void *
0x14008083e  lea     r8d, [r9+40h]; Size
0x140080842  call    memset_0
0x140080847  test    cs:SkmiFlags, 400000h
0x140080851  jz      short loc_14008088F
0x140080853  mov     rcx, gs:8; FramesToSkip
0x14008085c  test    rcx, rcx
0x14008085f  jz      short loc_14008088F
0x140080861  lea     r9, [rsp+88h+arg_0]; BackTraceHash
0x140080869  mov     r8, rbx; BackTrace
0x14008086c  mov     edx, 8; FramesToCapture
0x140080871  call    RtlCaptureStackBackTrace
0x140080876  test    ax, ax
0x140080879  jnz     short loc_14008088F
  ... truncated ...
```
