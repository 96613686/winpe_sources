# SkmmCreateProcessAddressSpace

- ea: `0x14005b200`
- end: `0x14005b80b`
- name: `SkmmCreateProcessAddressSpace`
- size: `1547`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x140014dd0`
- `0x14006b310`

## callees

- `0x140003780`
- `0x140009940`
- `0x14000c8d0`
- `0x140024724`
- `0x14002b534`
- `0x140031460`
- `0x1400355f4`
- `0x14005b200`
- `0x14007115c`
- `0x140081290`
- `0x14008662c`
- `0x1400f2fc0`
- `0x1400f9780`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmCreateProcessAddressSpace(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int ProcessShadow; // ebx
  __int64 HyperspacePte; // r14
  unsigned __int64 v13; // rbx
  __int64 PteTrace; // rax
  __int64 v15; // r13
  PVOID *v16; // rsi
  ULONG v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *StackBase; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rbx
  unsigned __int64 v25; // r12
  __int64 v26; // rax
  unsigned __int64 v27; // r10
  __int64 v28; // r8
  __int64 v29; // r13
  PVOID *v30; // rsi
  PVOID v31; // rcx
  USHORT v32; // ax
  __int64 v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rbx
  __int64 v39; // rsi
  __int64 v40; // rax
  __int64 v41; // r13
  PVOID *v42; // r12
  PVOID v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rcx
  _QWORD *v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rcx
  size_t v50; // r14
  __int64 v51; // r9
  __int64 v52; // rsi
  __int64 v53; // rbx
  __int64 v54; // rax
  __int64 v55; // r13
  PVOID *v56; // r14
  PVOID v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rcx
  _QWORD *v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rdx
  int v63; // ecx
  __int64 v64; // rax
  bool v65; // zf
  __int64 v66; // [rsp+30h] [rbp-30h] BYREF
  __int64 v67; // [rsp+38h] [rbp-28h]
  __int64 CurrentIrql; // [rsp+40h] [rbp-20h]
  size_t Size; // [rsp+48h] [rbp-18h]
  __int64 v70; // [rsp+50h] [rbp-10h]
  size_t v71; // [rsp+58h] [rbp-8h]
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+38h]
  __int64 *BackTraceHash; // [rsp+B8h] [rbp+58h] BYREF

  v66 = 0;
  BackTraceHash = 0;
  result = SkmiObtainPartition(a3, &BackTraceHash, 0, a4);
  if ( (int)result < 0 )
    return result;
  v6 = BackTraceHash;
  if ( (unsigned int)SkmiAllocatePhysicalPage(BackTraceHash, 0, &v66) )
  {
    CurrentIrql = KeGetCurrentIrql();
    __writecr8(2u);
    HyperspacePte = SkmiGetHyperspacePte(v8, v7, v9, v10);
    v13 = ((v66 & 0xFFFFFFFFFFLL) << 12) | 0x8000000000000063uLL;
    PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, ((_DWORD)v66 << 12) | 0x63u, *(_QWORD *)HyperspacePte);
    v15 = PteTrace;
    if ( PteTrace )
    {
      v16 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0
        && KeGetPcr()->NtTib.StackBase
        && !RtlCaptureStackBackTrace(v17, 8u, v16, (PULONG)&BackTraceHash) )
      {
        *(_QWORD *)(v15 + 40) = retaddr;
        *v16 = (PVOID)SkmiGetInstructionPointer(v19, v18);
      }
    }
    if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
      && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
    {
      StackBase = KeGetPcr()->NtTib.StackBase;
      v21 = StackBase ? StackBase[10] : 0LL;
      v22 = *(_QWORD *)(v21 + 232);
      if ( v22 )
        *(_QWORD *)(v22 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v13;
    }
    *(_QWORD *)HyperspacePte = v13;
    v23 = HyperspacePte << 25 >> 16;
    v67 = v23;
    Size = 2048;
    memset_0((void *)v23, 0, 0x800u);
    v71 = 2048;
    memmove((void *)(v23 + 2048), (const void *)0xFFFFF6FB7DBED800LL, 0x800u);
    v70 = 493;
    v24 = v23 + 3944;
    v25 = ((v66 & 0xFFFFFFFFFFLL) << 12) | 0x8000000000000063uLL;
    v26 = SkmiGetPteTrace(0, v24, 0, ((_DWORD)v66 << 12) | 0x63u, *(_QWORD *)v24);
    v28 = 0;
    v29 = v26;
    if ( v26 )
    {
      v30 = (PVOID *)(v26 + 32);
      memset_0((void *)(v26 + 32), 0, 0x40u);
      v28 = 0;
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v31 = KeGetPcr()->NtTib.StackBase;
        if ( v31 )
        {
          v32 = RtlCaptureStackBackTrace((ULONG)v31, 8u, v30, (PULONG)&BackTraceHash);
          v28 = 0;
          if ( !v32 )
          {
            *(_QWORD *)(v29 + 40) = retaddr;
            *v30 = (PVOID)SkmiGetInstructionPointer(v34, v33);
          }
        }
      }
      v27 = 0x8000000000000063uLL;
    }
    if ( (unsigned __int64)v24 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v24 < 0xFFFFF6FB7DBED800uLL )
    {
      v35 = KeGetPcr()->NtTib.StackBase;
      v36 = v35 ? v35[10] : v28;
      v37 = *(_QWORD *)(v36 + 232);
      if ( v37 )
        *(_QWORD *)(v37 + 8 * ((v24 >> 3) & 0x1FF)) = v25;
    }
    *(_QWORD *)v24 = v25;
    if ( a2 )
    {
      v38 = v67 + 8 * (((__int64)((((unsigned __int64)qword_140156B70 >> 36) & 0xFF8) - 0x90482413000LL) >> 3) & 0x1FF);
      v39 = v27 | *(_QWORD *)(a2 + 64) & 0xFFFFFFFFFF000LL;
      v40 = SkmiGetPteTrace(
              0,
              v67
            + 8 * (((__int64)((((unsigned __int64)qword_140156B70 >> 36) & 0xFF8) - 0x90482413000LL) >> 3) & 0x1FF),
              0,
              v39,
              *(_QWORD *)v38);
      v41 = v40;
      if ( v40 )
      {
        v42 = (PVOID *)(v40 + 32);
        memset_0((void *)(v40 + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v43 = KeGetPcr()->NtTib.StackBase;
          if ( v43 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v43, 8u, v42, (PULONG)&BackTraceHash) )
            {
              *(_QWORD *)(v41 + 40) = retaddr;
              *v42 = (PVOID)SkmiGetInstructionPointer(v45, v44);
            }
          }
        }
      }
      if ( (unsigned __int64)v38 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v38 < 0xFFFFF6FB7DBED800uLL )
      {
        v46 = KeGetPcr()->NtTib.StackBase;
        v47 = v46 ? v46[10] : 0LL;
        v48 = *(_QWORD *)(v47 + 232);
        if ( v48 )
          *(_QWORD *)(v48 + 8 * ((v38 >> 3) & 0x1FF)) = v39;
      }
      *(_QWORD *)v38 = v39;
    }
    SkmiReleaseHyperspacePte(HyperspacePte);
    LOBYTE(v49) = CurrentIrql;
    SkeLowerIrql(v49);
    if ( SkiKvaShadowMode )
    {
      ProcessShadow = SkmmAllocateProcessShadow(a1, a3);
      if ( ProcessShadow < 0 )
      {
        SkmiFreePhysicalPage(v6, v66);
        goto LABEL_68;
      }
      v50 = Size;
      memset_0(*(void **)(a1 + 232), 0, Size);
      v51 = *(_QWORD *)(a1 + 232);
      v52 = v51 + 8 * v70;
      v53 = *(_QWORD *)v52;
      memmove((void *)(v51 + v50), (const void *)(v50 + *(_QWORD *)(PsIumSystemProcess + 232)), v71);
      v54 = SkmiGetPteTrace(0, v52, 0, v53, *(_QWORD *)v52);
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
      if ( (unsigned __int64)v52 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v52 < 0xFFFFF6FB7DBED800uLL )
      {
        v60 = KeGetPcr()->NtTib.StackBase;
        v61 = v60 ? v60[10] : 0LL;
        v62 = *(_QWORD *)(v61 + 232);
        if ( v62 )
        {
          v63 = SkiKvaShadowMode;
          *(_QWORD *)(v62 + 8 * ((v52 >> 3) & 0x1FF)) = v53;
          if ( v63 != 2 && (v53 & 1) != 0 )
            v53 |= 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)v52 = v53;
    }
    if ( v6 )
    {
      if ( _InterlockedIncrement64(v6 + 4) <= 1 )
        __fastfail(0xEu);
    }
    else
    {
      v6 = SkmiSystemPartition;
    }
    v64 = v66 << 12;
    v65 = SkiFlushPcid == 0;
    *(_QWORD *)(a1 + 72) = v6;
    if ( !v65 )
      v64 |= 2uLL;
    *(_QWORD *)(a1 + 64) = v64;
    ProcessShadow = 0;
    *(_QWORD *)(a1 + 152) = a1 + 144;
    *(_QWORD *)(a1 + 144) = a1 + 144;
    goto LABEL_68;
  }
  ProcessShadow = -1073741670;
LABEL_68:
  if ( v6 )
    SkmiDereferencePartition(v6);
  return (unsigned int)ProcessShadow;
}

```

## disassembly

```asm
0x14005b200  mov     [rsp-38h+arg_0], rbx
0x14005b205  mov     [rsp-38h+arg_10], r8
0x14005b20a  mov     [rsp-38h+arg_8], rdx
0x14005b20f  push    rbp
0x14005b210  push    rsi
0x14005b211  push    rdi
0x14005b212  push    r12
0x14005b214  push    r13
0x14005b216  push    r14
0x14005b218  push    r15
0x14005b21a  mov     rbp, rsp
0x14005b21d  sub     rsp, 60h
0x14005b221  mov     rax, r8
0x14005b224  lea     rdx, [rbp+BackTraceHash]
0x14005b228  mov     r15, rcx
0x14005b22b  xor     r12d, r12d
0x14005b22e  mov     rcx, rax
0x14005b231  mov     [rbp+var_30], r12
0x14005b235  xor     r8d, r8d
0x14005b238  mov     [rbp+BackTraceHash], r12
0x14005b23c  call    SkmiObtainPartition
0x14005b241  test    eax, eax
0x14005b243  js      loc_14005B7F2
0x14005b249  mov     rdi, [rbp+BackTraceHash]
0x14005b24d  lea     r8, [rbp+var_30]
0x14005b251  mov     rcx, rdi
0x14005b254  xor     edx, edx
0x14005b256  call    SkmiAllocatePhysicalPage
0x14005b25b  test    eax, eax
0x14005b25d  jnz     short loc_14005B269
0x14005b25f  mov     ebx, 0C000009Ah
0x14005b264  jmp     loc_14005B7E3
0x14005b269  mov     rax, cr8
0x14005b26d  mov     [rbp+var_20], rax
0x14005b271  mov     eax, 2
0x14005b276  mov     cr8, rax
0x14005b27a  call    SkmiGetHyperspacePte
0x14005b27f  mov     rbx, [rbp+var_30]
0x14005b283  mov     r14, rax
0x14005b286  mov     rax, 0FFFFFFFFFFh
0x14005b290  xor     r8d, r8d
0x14005b293  and     rbx, rax
0x14005b296  mov     rdx, r14
0x14005b299  mov     rax, 8000000000000063h
0x14005b2a3  shl     rbx, 0Ch
0x14005b2a7  mov     rcx, [r14]
0x14005b2aa  or      rbx, rax
0x14005b2ad  mov     [rsp+60h+var_40], rcx
0x14005b2b2  mov     r9, rbx
0x14005b2b5  xor     ecx, ecx
0x14005b2b7  call    SkmiGetPteTrace
0x14005b2bc  mov     r13, rax
0x14005b2bf  test    rax, rax
0x14005b2c2  jz      short loc_14005B316
0x14005b2c4  xor     edx, edx; Val
0x14005b2c6  lea     rsi, [rax+20h]
0x14005b2ca  mov     rcx, rsi; void *
0x14005b2cd  lea     r8d, [rdx+40h]; Size
0x14005b2d1  call    memset_0
0x14005b2d6  test    cs:SkmiFlags, 400000h
0x14005b2e0  jz      short loc_14005B316
0x14005b2e2  mov     rax, gs:8
0x14005b2eb  test    rax, rax
0x14005b2ee  jz      short loc_14005B316
0x14005b2f0  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14005b2f4  mov     r8, rsi; BackTrace
0x14005b2f7  mov     edx, 8; FramesToCapture
0x14005b2fc  call    RtlCaptureStackBackTrace
0x14005b301  test    ax, ax
0x14005b304  jnz     short loc_14005B316
0x14005b306  mov     rax, [rbp+38h]
0x14005b30a  mov     [r13+28h], rax
0x14005b30e  call    SkmiGetInstructionPointer
0x14005b313  mov     [rsi], rax
0x14005b316  mov     rax, 0FFFFF6FB7DBED000h
0x14005b320  mov     rax, rax
0x14005b323  mov     r8, 0FFFFF6FB7DBED800h
0x14005b32d  mov     r13d, 1FFh
0x14005b333  cmp     r14, rax
0x14005b336  jb      short loc_14005B371
0x14005b338  mov     rax, r8
0x14005b33b  cmp     r14, rax
0x14005b33e  jnb     short loc_14005B371
0x14005b340  mov     rax, gs:8
0x14005b349  test    rax, rax
0x14005b34c  jz      short loc_14005B354
0x14005b34e  mov     rcx, [rax+50h]
0x14005b352  jmp     short loc_14005B357
0x14005b354  mov     rcx, r12
0x14005b357  mov     rdx, [rcx+0E8h]
0x14005b35e  test    rdx, rdx
0x14005b361  jz      short loc_14005B371
0x14005b363  mov     rax, r14
0x14005b366  sar     rax, 3
0x14005b36a  and     rax, r13
0x14005b36d  mov     [rdx+rax*8], rbx
0x14005b371  mov     [r14], rbx
0x14005b374  mov     rbx, r14
0x14005b377  shl     rbx, 19h
0x14005b37b  mov     rax, 0FFFFF68000000000h
0x14005b385  shl     rax, 19h
0x14005b389  sub     rbx, rax
0x14005b38c  sar     rbx, 10h
0x14005b390  mov     [rbp+var_28], rbx
0x14005b394  mov     rax, r8
0x14005b397  sar     rax, 3
0x14005b39b  xor     edx, edx; Val
0x14005b39d  and     rax, r13
0x14005b3a0  mov     rcx, rbx; void *
0x14005b3a3  lea     rsi, ds:0[rax*8]
0x14005b3ab  mov     r8, rsi; Size
0x14005b3ae  mov     [rbp+Size], rsi
0x14005b3b2  call    memset_0
0x14005b3b7  mov     eax, 1000h
0x14005b3bc  mov     rcx, 0FFFFF6FB7DBED800h
0x14005b3c6  sub     rax, rsi
0x14005b3c9  mov     [rbp+var_8], rax
0x14005b3cd  mov     rdx, rcx; Src
0x14005b3d0  lea     rcx, [rbx+rsi]; void *
0x14005b3d4  mov     r8, rax; Size
0x14005b3d7  call    memmove
0x14005b3dc  mov     rax, 0FFFFF6FB7DBEDF68h
0x14005b3e6  mov     r12, [rbp+var_30]
0x14005b3ea  mov     r10, 8000000000000063h
0x14005b3f4  sar     rax, 3
0x14005b3f8  xor     r8d, r8d
0x14005b3fb  and     rax, r13
0x14005b3fe  xor     ecx, ecx
0x14005b400  mov     [rbp+var_10], rax
0x14005b404  lea     rbx, [rbx+rax*8]
0x14005b408  mov     rax, 0FFFFFFFFFFh
0x14005b412  and     r12, rax
0x14005b415  mov     rdx, rbx
0x14005b418  mov     rax, [rbx]
0x14005b41b  shl     r12, 0Ch
0x14005b41f  or      r12, r10
0x14005b422  mov     [rsp+60h+var_40], rax
0x14005b427  mov     r9, r12
0x14005b42a  call    SkmiGetPteTrace
0x14005b42f  xor     r8d, r8d
0x14005b432  mov     r13, rax
0x14005b435  test    rax, rax
0x14005b438  jz      short loc_14005B49C
0x14005b43a  xor     edx, edx; Val
0x14005b43c  lea     rsi, [rax+20h]
0x14005b440  mov     rcx, rsi; void *
0x14005b443  lea     r8d, [rdx+40h]; Size
0x14005b447  call    memset_0
0x14005b44c  xor     r8d, r8d
0x14005b44f  test    cs:SkmiFlags, 400000h
0x14005b459  jz      short loc_14005B492
0x14005b45b  mov     rcx, gs:8; FramesToSkip
0x14005b464  test    rcx, rcx
0x14005b467  jz      short loc_14005B492
0x14005b469  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14005b46d  mov     r8, rsi; BackTrace
0x14005b470  mov     edx, 8; FramesToCapture
0x14005b475  call    RtlCaptureStackBackTrace
0x14005b47a  xor     r8d, r8d
0x14005b47d  test    ax, ax
0x14005b480  jnz     short loc_14005B492
0x14005b482  mov     rax, [rbp+38h]
0x14005b486  mov     [r13+28h], rax
0x14005b48a  call    SkmiGetInstructionPointer
0x14005b48f  mov     [rsi], rax
0x14005b492  mov     r10, 8000000000000063h
0x14005b49c  mov     rdx, 0FFFFF6FB7DBED000h
0x14005b4a6  mov     rax, rdx
0x14005b4a9  cmp     rbx, rax
0x14005b4ac  jb      short loc_14005B4FD
0x14005b4ae  mov     rax, 0FFFFF6FB7DBED800h
0x14005b4b8  mov     rax, rax
0x14005b4bb  cmp     rbx, rax
0x14005b4be  jnb     short loc_14005B4FD
0x14005b4c0  mov     rax, gs:8
0x14005b4c9  test    rax, rax
0x14005b4cc  jz      short loc_14005B4D4
0x14005b4ce  mov     rcx, [rax+50h]
0x14005b4d2  jmp     short loc_14005B4D7
0x14005b4d4  mov     rcx, r8
0x14005b4d7  mov     rdx, [rcx+0E8h]
0x14005b4de  test    rdx, rdx
0x14005b4e1  jz      short loc_14005B4F3
0x14005b4e3  mov     rax, rbx
0x14005b4e6  sar     rax, 3
0x14005b4ea  and     eax, 1FFh
0x14005b4ef  mov     [rdx+rax*8], r12
0x14005b4f3  mov     rdx, 0FFFFF6FB7DBED000h
0x14005b4fd  mov     rsi, [rbp+arg_8]
0x14005b501  mov     [rbx], r12
0x14005b504  xor     r12d, r12d
0x14005b507  test    rsi, rsi
0x14005b50a  jz      loc_14005B61D
0x14005b510  mov     rcx, cs:qword_140156B70
0x14005b517  shr     rcx, 24h
0x14005b51b  and     ecx, 0FF8h
0x14005b521  mov     rax, rdx
0x14005b524  mov     rsi, [rsi+40h]
0x14005b528  add     rcx, rax
0x14005b52b  mov     rax, [rbp+var_28]
0x14005b52f  xor     r8d, r8d
0x14005b532  sar     rcx, 3
0x14005b536  and     ecx, 1FFh
0x14005b53c  lea     rbx, [rax+rcx*8]
0x14005b540  mov     rax, 0FFFFFFFFFF000h
0x14005b54a  and     rsi, rax
0x14005b54d  mov     rdx, rbx
0x14005b550  mov     rax, [rbx]
0x14005b553  or      rsi, r10
0x14005b556  mov     r9, rsi
0x14005b559  mov     [rsp+60h+var_40], rax
0x14005b55e  xor     ecx, ecx
0x14005b560  call    SkmiGetPteTrace
0x14005b565  mov     r13, rax
0x14005b568  test    rax, rax
0x14005b56b  jz      short loc_14005B5C3
0x14005b56d  xor     edx, edx; Val
0x14005b56f  lea     r12, [rax+20h]
0x14005b573  mov     rcx, r12; void *
0x14005b576  lea     r8d, [rdx+40h]; Size
0x14005b57a  call    memset_0
0x14005b57f  test    cs:SkmiFlags, 400000h
0x14005b589  jz      short loc_14005B5C0
0x14005b58b  mov     rcx, gs:8; FramesToSkip
0x14005b594  test    rcx, rcx
0x14005b597  jz      short loc_14005B5C0
0x14005b599  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14005b59d  mov     r8, r12; BackTrace
0x14005b5a0  mov     edx, 8; FramesToCapture
0x14005b5a5  call    RtlCaptureStackBackTrace
0x14005b5aa  test    ax, ax
0x14005b5ad  jnz     short loc_14005B5C0
0x14005b5af  mov     rax, [rbp+38h]
0x14005b5b3  mov     [r13+28h], rax
0x14005b5b7  call    SkmiGetInstructionPointer
0x14005b5bc  mov     [r12], rax
0x14005b5c0  xor     r12d, r12d
0x14005b5c3  mov     rax, 0FFFFF6FB7DBED000h
0x14005b5cd  mov     rax, rax
0x14005b5d0  cmp     rbx, rax
0x14005b5d3  jb      short loc_14005B61A
0x14005b5d5  mov     rax, 0FFFFF6FB7DBED800h
0x14005b5df  mov     rax, rax
0x14005b5e2  cmp     rbx, rax
0x14005b5e5  jnb     short loc_14005B61A
0x14005b5e7  mov     rax, gs:8
0x14005b5f0  test    rax, rax
0x14005b5f3  jz      short loc_14005B5FB
0x14005b5f5  mov     rcx, [rax+50h]
0x14005b5f9  jmp     short loc_14005B5FE
0x14005b5fb  mov     rcx, r12
0x14005b5fe  mov     rdx, [rcx+0E8h]
0x14005b605  test    rdx, rdx
0x14005b608  jz      short loc_14005B61A
0x14005b60a  mov     rax, rbx
0x14005b60d  sar     rax, 3
0x14005b611  and     eax, 1FFh
0x14005b616  mov     [rdx+rax*8], rsi
0x14005b61a  mov     [rbx], rsi
0x14005b61d  mov     rcx, r14
0x14005b620  call    SkmiReleaseHyperspacePte
0x14005b625  mov     cl, byte ptr [rbp+var_20]
0x14005b628  call    SkeLowerIrql
0x14005b62d  cmp     cs:SkiKvaShadowMode, r12d
0x14005b634  jz      loc_14005B77E
0x14005b63a  mov     rdx, [rbp+arg_10]
0x14005b63e  mov     rcx, r15
0x14005b641  call    SkmmAllocateProcessShadow
0x14005b646  mov     ebx, eax
0x14005b648  test    eax, eax
0x14005b64a  js      loc_14005B7A0
0x14005b650  mov     r14, [rbp+Size]
0x14005b654  xor     edx, edx; Val
0x14005b656  mov     rcx, [r15+0E8h]; void *
0x14005b65d  mov     r8, r14; Size
0x14005b660  call    memset_0
0x14005b665  mov     r9, [r15+0E8h]
0x14005b66c  mov     rax, [rbp+var_10]
0x14005b670  mov     r8, [rbp+var_8]; Size
0x14005b674  lea     rcx, [r9+r14]; void *
0x14005b678  lea     rsi, [r9+rax*8]
0x14005b67c  mov     rbx, [rsi]
0x14005b67f  mov     rax, cs:PsIumSystemProcess
0x14005b686  mov     rdx, [rax+0E8h]
0x14005b68d  add     rdx, r14; Src
0x14005b690  call    memmove
0x14005b695  mov     rax, [rsi]
0x14005b698  mov     r9, rbx
0x14005b69b  xor     r8d, r8d
0x14005b69e  mov     [rsp+60h+var_40], rax
0x14005b6a3  mov     rdx, rsi
0x14005b6a6  xor     ecx, ecx
0x14005b6a8  call    SkmiGetPteTrace
0x14005b6ad  mov     r13, rax
0x14005b6b0  test    rax, rax
0x14005b6b3  jz      short loc_14005B707
0x14005b6b5  xor     edx, edx; Val
0x14005b6b7  lea     r14, [rax+20h]
0x14005b6bb  mov     rcx, r14; void *
0x14005b6be  lea     r8d, [rdx+40h]; Size
  ... truncated ...
```
