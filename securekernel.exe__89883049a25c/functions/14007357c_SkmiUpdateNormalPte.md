# SkmiUpdateNormalPte

- ea: `0x14007357c`
- end: `0x140073888`
- name: `SkmiUpdateNormalPte`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400720b8`
- `0x140072594`

## callees

- `0x140003780`
- `0x140009890`
- `0x140009940`
- `0x14000c8d0`
- `0x14002b534`
- `0x14007357c`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiUpdateNormalPte(unsigned __int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 HyperspacePte; // rsi
  unsigned __int64 v7; // rbx
  __int64 PteTrace; // rax
  __int64 v9; // rbp
  PVOID *v10; // r14
  ULONG v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  _QWORD *StackBase; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // ecx
  signed __int64 *v19; // r15
  signed __int64 v20; // rbx
  __int64 v21; // r12
  __int64 DataTraceEntry; // rcx
  signed __int64 v23; // r9
  signed __int64 v24; // rax
  signed __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rbp
  PVOID *v28; // r14
  PVOID v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  signed __int64 v32; // rax
  __int64 v33; // rax
  int v34; // r9d
  __int64 v35; // rdi
  PVOID *v36; // rbx
  PVOID v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdx
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+88h] [rbp+10h] BYREF

  HyperspacePte = SkmiGetHyperspacePte(a1, a2, a3, a4);
  v7 = a1 & 0xFFFFFFFFFF000LL ^ 0x8000000000000063uLL;
  PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, a1 & 0xFFFFF000 ^ 0x63, *(_QWORD *)HyperspacePte);
  v9 = PteTrace;
  if ( PteTrace )
  {
    v10 = (PVOID *)(PteTrace + 32);
    memset_0((void *)(PteTrace + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0
      && KeGetPcr()->NtTib.StackBase
      && !RtlCaptureStackBackTrace(v11, 8u, v10, &BackTraceHash) )
    {
      *(_QWORD *)(v9 + 40) = retaddr;
      *v10 = (PVOID)SkmiGetInstructionPointer(v13, v12);
    }
  }
  v14 = 511;
  if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
    && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
  {
    StackBase = KeGetPcr()->NtTib.StackBase;
    v16 = StackBase ? StackBase[10] : 0LL;
    v17 = *(_QWORD *)(v16 + 232);
    if ( v17 )
    {
      v18 = SkiKvaShadowMode;
      *(_QWORD *)(v17 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v7;
      if ( v18 != 2 )
        v7 |= 0x8000000000000000uLL;
    }
  }
  *(_QWORD *)HyperspacePte = v7;
  v19 = (signed __int64 *)((HyperspacePte << 25 >> 16) + 8 * ((a1 >> 3) & 0x1FF));
  _m_prefetchw(v19);
  v20 = *v19;
  v21 = a3 << 12;
  while ( 1 )
  {
    DataTraceEntry = SkmiAllocateDataTraceEntry(0, v19, v14, v21 ^ (v20 ^ v21) & 0xFFF0000000000FFFuLL);
    v24 = _InterlockedCompareExchange64(v19, v23, v20);
    v25 = v24;
    if ( DataTraceEntry )
    {
      if ( v24 == v20 )
      {
        v26 = SkmiGetPteTrace(DataTraceEntry, (_DWORD)v19, 0, v23, v20);
        v27 = v26;
        if ( v26 )
        {
          v28 = (PVOID *)(v26 + 32);
          memset_0((void *)(v26 + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v29 = KeGetPcr()->NtTib.StackBase;
            if ( v29 )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)v29, 8u, v28, &BackTraceHash) )
                break;
            }
          }
        }
      }
    }
    v32 = v20;
    v20 = v25;
    if ( v25 == v32 )
      goto LABEL_24;
  }
  *(_QWORD *)(v27 + 40) = retaddr;
  *v28 = (PVOID)SkmiGetInstructionPointer(v31, v30);
LABEL_24:
  v33 = SkmiGetPteTrace(0, HyperspacePte, 0, 0, *(_QWORD *)HyperspacePte);
  v35 = v33;
  if ( v33 )
  {
    v36 = (PVOID *)(v33 + 32);
    memset_0((void *)(v33 + 32), 0, (unsigned int)(v34 + 64));
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      v37 = KeGetPcr()->NtTib.StackBase;
      if ( v37 )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)v37, 8u, v36, &BackTraceHash) )
        {
          *(_QWORD *)(v35 + 40) = retaddr;
          *v36 = (PVOID)SkmiGetInstructionPointer(v39, v38);
        }
      }
    }
  }
  if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
    && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
  {
    v40 = KeGetPcr()->NtTib.StackBase;
    if ( v40 )
      v41 = v40[10];
    else
      v41 = 0;
    v42 = *(_QWORD *)(v41 + 232);
    if ( v42 )
      *(_QWORD *)(v42 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = 0;
  }
  *(_QWORD *)HyperspacePte = 0;
  return SkmiReleaseHyperspacePte(HyperspacePte);
}

```

## disassembly

```asm
0x14007357c  push    rbx
0x14007357e  push    rbp
0x14007357f  push    rsi
0x140073580  push    rdi
0x140073581  push    r12
0x140073583  push    r13
0x140073585  push    r14
0x140073587  push    r15
0x140073589  sub     rsp, 38h
0x14007358d  mov     r12, r8
0x140073590  mov     rdi, rcx
0x140073593  call    SkmiGetHyperspacePte
0x140073598  mov     rsi, rax
0x14007359b  mov     rbx, rdi
0x14007359e  and     rbx, 0FFFFFFFFFFFFF000h
0x1400735a5  mov     rax, 0FFFFFFFFFF000h
0x1400735af  and     rbx, rax
0x1400735b2  xor     r8d, r8d
0x1400735b5  mov     rax, 8000000000000063h
0x1400735bf  mov     rdx, rsi
0x1400735c2  xor     rbx, rax
0x1400735c5  xor     ecx, ecx
0x1400735c7  mov     rax, [rsi]
0x1400735ca  mov     r9, rbx
0x1400735cd  mov     [rsp+78h+var_58], rax
0x1400735d2  call    SkmiGetPteTrace
0x1400735d7  xor     r13d, r13d
0x1400735da  mov     rbp, rax
0x1400735dd  test    rax, rax
0x1400735e0  jz      short loc_140073638
0x1400735e2  lea     r14, [rax+20h]
0x1400735e6  xor     edx, edx; Val
0x1400735e8  mov     rcx, r14; void *
0x1400735eb  lea     r8d, [r13+40h]; Size
0x1400735ef  call    memset_0
0x1400735f4  test    cs:SkmiFlags, 400000h
0x1400735fe  jz      short loc_140073638
0x140073600  mov     rax, gs:8
0x140073609  test    rax, rax
0x14007360c  jz      short loc_140073638
0x14007360e  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x140073616  mov     r8, r14; BackTrace
0x140073619  lea     edx, [r13+8]; FramesToCapture
0x14007361d  call    RtlCaptureStackBackTrace
0x140073622  test    ax, ax
0x140073625  jnz     short loc_140073638
0x140073627  mov     rax, [rsp+78h]
0x14007362c  mov     [rbp+28h], rax
0x140073630  call    SkmiGetInstructionPointer
0x140073635  mov     [r14], rax
0x140073638  mov     rax, 0FFFFF6FB7DBED000h
0x140073642  mov     rax, rax
0x140073645  mov     rcx, 0FFFFF6FB7DBED800h
0x14007364f  mov     r8d, 1FFh
0x140073655  cmp     rsi, rax
0x140073658  jb      short loc_1400736B0
0x14007365a  mov     rax, rcx
0x14007365d  cmp     rsi, rax
0x140073660  jnb     short loc_1400736B0
0x140073662  mov     rax, gs:8
0x14007366b  test    rax, rax
0x14007366e  jz      short loc_140073676
0x140073670  mov     rcx, [rax+50h]
0x140073674  jmp     short loc_140073679
0x140073676  mov     rcx, r13
0x140073679  mov     rdx, [rcx+0E8h]
0x140073680  test    rdx, rdx
0x140073683  jz      short loc_1400736B0
0x140073685  mov     ecx, cs:SkiKvaShadowMode
0x14007368b  mov     rax, rsi
0x14007368e  sar     rax, 3
0x140073692  and     rax, r8
0x140073695  mov     [rdx+rax*8], rbx
0x140073699  cmp     ecx, 2
0x14007369c  jz      short loc_1400736B0
0x14007369e  test    bl, 1
0x1400736a1  jz      short loc_1400736B0
0x1400736a3  mov     rax, 8000000000000000h
0x1400736ad  or      rbx, rax
0x1400736b0  mov     rcx, rsi
0x1400736b3  mov     [rsi], rbx
0x1400736b6  shl     rcx, 19h
0x1400736ba  mov     rax, 0FFFFF68000000000h
0x1400736c4  shl     rax, 19h
0x1400736c8  sub     rcx, rax
0x1400736cb  shr     rdi, 3
0x1400736cf  sar     rcx, 10h
0x1400736d3  and     rdi, r8
0x1400736d6  lea     r15, [rcx+rdi*8]
0x1400736da  prefetchw byte ptr [r15]
0x1400736de  mov     rbx, [r15]
0x1400736e1  shl     r12, 0Ch
0x1400736e5  mov     rax, 0FFF0000000000FFFh
0x1400736ef  mov     r9, r12
0x1400736f2  xor     r9, rbx
0x1400736f5  mov     rdx, r15
0x1400736f8  and     r9, rax
0x1400736fb  xor     ecx, ecx
0x1400736fd  xor     r9, r12
0x140073700  call    SkmiAllocateDataTraceEntry
0x140073705  mov     rcx, rax
0x140073708  mov     rax, rbx
0x14007370b  lock cmpxchg [r15], r9
0x140073710  mov     rdi, rax
0x140073713  test    rcx, rcx
0x140073716  jz      short loc_14007377B
0x140073718  cmp     rax, rbx
0x14007371b  jnz     short loc_14007377B
0x14007371d  xor     r8d, r8d
0x140073720  mov     [rsp+78h+var_58], rbx
0x140073725  mov     rdx, r15
0x140073728  call    SkmiGetPteTrace
0x14007372d  mov     rbp, rax
0x140073730  test    rax, rax
0x140073733  jz      short loc_14007377B
0x140073735  xor     edx, edx; Val
0x140073737  lea     r14, [rax+20h]
0x14007373b  mov     rcx, r14; void *
0x14007373e  lea     r8d, [rdx+40h]; Size
0x140073742  call    memset_0
0x140073747  test    cs:SkmiFlags, 400000h
0x140073751  jz      short loc_14007377B
0x140073753  mov     rcx, gs:8; FramesToSkip
0x14007375c  test    rcx, rcx
0x14007375f  jz      short loc_14007377B
0x140073761  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x140073769  mov     r8, r14; BackTrace
0x14007376c  mov     edx, 8; FramesToCapture
0x140073771  call    RtlCaptureStackBackTrace
0x140073776  test    ax, ax
0x140073779  jz      short loc_14007378C
0x14007377b  mov     rax, rbx
0x14007377e  mov     rbx, rdi
0x140073781  cmp     rdi, rax
0x140073784  jnz     loc_1400736E5
0x14007378a  jmp     short loc_14007379D
0x14007378c  mov     rax, [rsp+78h]
0x140073791  mov     [rbp+28h], rax
0x140073795  call    SkmiGetInstructionPointer
0x14007379a  mov     [r14], rax
0x14007379d  mov     rax, [rsi]
0x1400737a0  xor     r9d, r9d
0x1400737a3  xor     r8d, r8d
0x1400737a6  mov     [rsp+78h+var_58], rax
0x1400737ab  mov     rdx, rsi
0x1400737ae  xor     ecx, ecx
0x1400737b0  call    SkmiGetPteTrace
0x1400737b5  mov     rdi, rax
0x1400737b8  test    rax, rax
0x1400737bb  jz      short loc_140073814
0x1400737bd  lea     rbx, [rax+20h]
0x1400737c1  xor     edx, edx; Val
0x1400737c3  mov     rcx, rbx; void *
0x1400737c6  lea     r8d, [r9+40h]; Size
0x1400737ca  call    memset_0
0x1400737cf  test    cs:SkmiFlags, 400000h
0x1400737d9  jz      short loc_140073814
0x1400737db  mov     rcx, gs:8; FramesToSkip
0x1400737e4  test    rcx, rcx
0x1400737e7  jz      short loc_140073814
0x1400737e9  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x1400737f1  mov     r8, rbx; BackTrace
0x1400737f4  mov     edx, 8; FramesToCapture
0x1400737f9  call    RtlCaptureStackBackTrace
0x1400737fe  test    ax, ax
0x140073801  jnz     short loc_140073814
0x140073803  mov     rax, [rsp+78h]
0x140073808  mov     [rdi+28h], rax
0x14007380c  call    SkmiGetInstructionPointer
0x140073811  mov     [rbx], rax
0x140073814  mov     rax, 0FFFFF6FB7DBED000h
0x14007381e  mov     rax, rax
0x140073821  cmp     rsi, rax
0x140073824  jb      short loc_14007386B
0x140073826  mov     rax, 0FFFFF6FB7DBED800h
0x140073830  mov     rax, rax
0x140073833  cmp     rsi, rax
0x140073836  jnb     short loc_14007386B
0x140073838  mov     rax, gs:8
0x140073841  test    rax, rax
0x140073844  jz      short loc_14007384C
0x140073846  mov     rcx, [rax+50h]
0x14007384a  jmp     short loc_14007384F
0x14007384c  mov     rcx, r13
0x14007384f  mov     rdx, [rcx+0E8h]
0x140073856  test    rdx, rdx
0x140073859  jz      short loc_14007386B
0x14007385b  mov     rax, rsi
0x14007385e  sar     rax, 3
0x140073862  and     eax, 1FFh
0x140073867  mov     [rdx+rax*8], r13
0x14007386b  mov     rcx, rsi
0x14007386e  mov     [rsi], r13
0x140073871  call    SkmiReleaseHyperspacePte
0x140073876  add     rsp, 38h
0x14007387a  pop     r15
0x14007387c  pop     r14
0x14007387e  pop     r13
0x140073880  pop     r12
0x140073882  pop     rdi
0x140073883  pop     rsi
0x140073884  pop     rbp
0x140073885  pop     rbx
0x140073886  retn
```
