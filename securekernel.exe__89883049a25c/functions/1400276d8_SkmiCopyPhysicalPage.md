# SkmiCopyPhysicalPage

- ea: `0x1400276d8`
- end: `0x140027ab8`
- name: `SkmiCopyPhysicalPage`
- size: `992`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140026960`
- `0x140061d60`
- `0x14007204c`
- `0x140072594`
- `0x140072fc4`

## callees

- `0x140009940`
- `0x14000c8d0`
- `0x1400276d8`
- `0x14002b534`
- `0x140081290`
- `0x1400f3000`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCopyPhysicalPage(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 HyperspacePte; // rsi
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r9
  _BYTE *StackBase; // rax
  unsigned __int64 v12; // r8
  bool v13; // zf
  unsigned __int64 *v14; // r14
  _QWORD *v15; // rax
  unsigned __int64 v16; // rbx
  __int64 v17; // r8
  unsigned __int64 v18; // rdi
  _BYTE *v19; // rax
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  unsigned __int64 *v22; // r14
  ULONG v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // ecx
  unsigned __int64 retaddr; // [rsp+68h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+70h] [rbp+8h] BYREF

  HyperspacePte = SkmiGetHyperspacePte(a1, a2, a3, a4);
  v7 = 0xFFFFF6FFFFFFFFFFuLL;
  v8 = 0xFFFFF60000000000uLL;
  v9 = (a2 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000063uLL;
  v10 = 0xFFFFF67FFFFFFFFFuLL;
  if ( SkmiDataTraces )
  {
    if ( (StackBase = KeGetPcr()->NtTib.StackBase, v12 = *(_QWORD *)HyperspacePte, StackBase) && StackBase[344]
      || HyperspacePte
      && (HyperspacePte < 0xFFFFF68000000000uLL || HyperspacePte > 0xFFFFF6FFFFFFFFFFuLL)
      && (HyperspacePte < 0xFFFFF60000000000uLL || HyperspacePte > 0xFFFFF67FFFFFFFFFuLL)
      && (v12 & 0x10000000000000LL) != 0 )
    {
      v8 = _InterlockedExchangeAdd(&SkmiDataTraceIndex, 1u) & (unsigned int)(SkmiDataTraceSize - 1);
      v13 = SkmiDataTraces + 96 * v8 == 0;
      v14 = (unsigned __int64 *)(SkmiDataTraces + 96 * v8);
      *v14 = 0;
      v14[1] = 0;
      if ( !v13 )
      {
        v14[2] = v12;
        *v14 = HyperspacePte;
        v14[3] = v9;
        *((_BYTE *)v14 + 8) = 1;
        memset_0(v14 + 4, 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0
          && KeGetPcr()->NtTib.StackBase
          && !RtlCaptureStackBackTrace(v7, 8u, (PVOID *)v14 + 4, &BackTraceHash) )
        {
          v14[5] = retaddr;
          v14[4] = SkmiGetInstructionPointer(v7, v8);
        }
      }
    }
  }
  if ( HyperspacePte >= 0xFFFFF6FB7DBED000uLL && HyperspacePte < 0xFFFFF6FB7DBED800uLL )
  {
    v15 = KeGetPcr()->NtTib.StackBase;
    v7 = v15 ? v15[10] : 0LL;
    v8 = *(_QWORD *)(v7 + 232);
    if ( v8 )
    {
      v7 = (unsigned int)SkiKvaShadowMode;
      *(_QWORD *)(v8 + 8 * (((__int64)HyperspacePte >> 3) & 0x1FF)) = v9;
      if ( (_DWORD)v7 != 2 && (v9 & 1) != 0 )
        v9 |= 0x8000000000000000uLL;
    }
  }
  *(_QWORD *)HyperspacePte = v9;
  v16 = SkmiGetHyperspacePte(v7, v8, 0x8000000000000000uLL, v10);
  v18 = (a1 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000021uLL;
  if ( SkmiDataTraces )
  {
    if ( (v19 = KeGetPcr()->NtTib.StackBase, v20 = *(_QWORD *)v16, v19) && v19[344]
      || v16
      && (v16 < 0xFFFFF68000000000uLL || v16 > 0xFFFFF6FFFFFFFFFFuLL)
      && (v16 < 0xFFFFF60000000000uLL || v16 > 0xFFFFF67FFFFFFFFFuLL)
      && (v20 & 0x10000000000000LL) != 0 )
    {
      v21 = _InterlockedExchangeAdd(&SkmiDataTraceIndex, 1u) & (unsigned int)(SkmiDataTraceSize - 1);
      v13 = SkmiDataTraces + 96 * v21 == 0;
      v22 = (unsigned __int64 *)(SkmiDataTraces + 96 * v21);
      *v22 = 0;
      v22[1] = 0;
      if ( !v13 )
      {
        *v22 = v16;
        v22[2] = v20;
        v22[3] = v18;
        *((_BYTE *)v22 + 8) = 1;
        memset_0(v22 + 4, 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0
          && KeGetPcr()->NtTib.StackBase
          && !RtlCaptureStackBackTrace(v23, 8u, (PVOID *)v22 + 4, &BackTraceHash) )
        {
          v22[5] = retaddr;
          v22[4] = SkmiGetInstructionPointer(v25, v24);
        }
      }
    }
  }
  if ( v16 >= 0xFFFFF6FB7DBED000uLL && v16 < 0xFFFFF6FB7DBED800uLL )
  {
    v26 = KeGetPcr()->NtTib.StackBase;
    if ( v26 )
      v27 = v26[10];
    else
      v27 = 0;
    v28 = *(_QWORD *)(v27 + 232);
    if ( v28 )
    {
      v29 = SkiKvaShadowMode;
      *(_QWORD *)(v28 + 8 * (((__int64)v16 >> 3) & 0x1FF)) = v18;
      if ( v29 != 2 && (v18 & 1) != 0 )
        v18 |= 0x8000000000000000uLL;
    }
  }
  *(_QWORD *)v16 = v18;
  SkeCopyPage((__int64)(HyperspacePte << 25) >> 16, (__int64)(v16 << 25) >> 16, v17);
  SkmiReleaseHyperspacePte(v16);
  return SkmiReleaseHyperspacePte(HyperspacePte);
}

```

## disassembly

```asm
0x1400276d8  push    rbx
0x1400276da  push    rbp
0x1400276db  push    rsi
0x1400276dc  push    rdi
0x1400276dd  push    r12
0x1400276df  push    r13
0x1400276e1  push    r14
0x1400276e3  push    r15
0x1400276e5  sub     rsp, 28h
0x1400276e9  mov     rbx, rdx
0x1400276ec  mov     rdi, rcx
0x1400276ef  call    SkmiGetHyperspacePte
0x1400276f4  shl     rbx, 0Ch
0x1400276f8  mov     rsi, rax
0x1400276fb  mov     rax, 0FFFFFFFFFF000h
0x140027705  mov     r15, 0FFFFF68000000000h
0x14002770f  and     rbx, rax
0x140027712  mov     rcx, 0FFFFF6FFFFFFFFFFh
0x14002771c  mov     rax, 8000000000000063h
0x140027726  mov     rdx, 0FFFFF60000000000h
0x140027730  xor     rbx, rax
0x140027733  mov     r9, 0FFFFF67FFFFFFFFFh
0x14002773d  xor     r13d, r13d
0x140027740  cmp     cs:SkmiDataTraces, r13
0x140027747  jz      loc_140027841
0x14002774d  mov     rax, gs:8
0x140027756  mov     r8, [rsi]
0x140027759  test    rax, rax
0x14002775c  jz      short loc_140027767
0x14002775e  cmp     [rax+158h], r13b
0x140027765  jnz     short loc_1400277A3
0x140027767  test    rsi, rsi
0x14002776a  jz      loc_140027841
0x140027770  mov     rax, r15
0x140027773  cmp     rsi, rax
0x140027776  jb      short loc_140027784
0x140027778  mov     rax, rcx
0x14002777b  cmp     rsi, rax
0x14002777e  jbe     loc_140027841
0x140027784  mov     rax, rdx
0x140027787  cmp     rsi, rax
0x14002778a  jb      short loc_140027798
0x14002778c  mov     rax, r9
0x14002778f  cmp     rsi, rax
0x140027792  jbe     loc_140027841
0x140027798  bt      r8, 34h ; '4'
0x14002779d  jnb     loc_140027841
0x1400277a3  mov     eax, 1
0x1400277a8  lock xadd cs:SkmiDataTraceIndex, eax
0x1400277b0  mov     edx, cs:SkmiDataTraceSize
0x1400277b6  dec     edx
0x1400277b8  and     rdx, rax
0x1400277bb  lea     r14, [rdx+rdx*2]
0x1400277bf  shl     r14, 5
0x1400277c3  add     r14, cs:SkmiDataTraces
0x1400277ca  mov     [r14], r13
0x1400277cd  mov     [r14+8], r13
0x1400277d1  jz      short loc_140027841
0x1400277d3  xor     edx, edx; Val
0x1400277d5  mov     [r14+10h], r8
0x1400277d9  lea     r15, [r14+20h]
0x1400277dd  mov     [r14], rsi
0x1400277e0  mov     rcx, r15; void *
0x1400277e3  mov     [r14+18h], rbx
0x1400277e7  mov     byte ptr [r14+8], 1
0x1400277ec  lea     r8d, [rdx+40h]; Size
0x1400277f0  call    memset_0
0x1400277f5  test    cs:SkmiFlags, 400000h
0x1400277ff  jz      short loc_140027837
0x140027801  mov     rax, gs:8
0x14002780a  test    rax, rax
0x14002780d  jz      short loc_140027837
0x14002780f  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x140027814  mov     r8, r15; BackTrace
0x140027817  mov     edx, 8; FramesToCapture
0x14002781c  call    RtlCaptureStackBackTrace
0x140027821  test    ax, ax
0x140027824  jnz     short loc_140027837
0x140027826  mov     rax, [rsp+68h]
0x14002782b  mov     [r14+28h], rax
0x14002782f  call    SkmiGetInstructionPointer
0x140027834  mov     [r15], rax
0x140027837  mov     r15, 0FFFFF68000000000h
0x140027841  mov     rax, 0FFFFF6FB7DBED000h
0x14002784b  mov     rax, rax
0x14002784e  mov     r14, 0FFFFF6FB7DBED800h
0x140027858  mov     r8, 8000000000000000h
0x140027862  cmp     rsi, rax
0x140027865  jb      short loc_1400278B5
0x140027867  mov     rax, r14
0x14002786a  cmp     rsi, rax
0x14002786d  jnb     short loc_1400278B5
0x14002786f  mov     rax, gs:8
0x140027878  test    rax, rax
0x14002787b  jz      short loc_140027883
0x14002787d  mov     rcx, [rax+50h]
0x140027881  jmp     short loc_140027886
0x140027883  mov     rcx, r13
0x140027886  mov     rdx, [rcx+0E8h]
0x14002788d  test    rdx, rdx
0x140027890  jz      short loc_1400278B5
0x140027892  mov     ecx, cs:SkiKvaShadowMode
0x140027898  mov     rax, rsi
0x14002789b  sar     rax, 3
0x14002789f  and     eax, 1FFh
0x1400278a4  mov     [rdx+rax*8], rbx
0x1400278a8  cmp     ecx, 2
0x1400278ab  jz      short loc_1400278B5
0x1400278ad  test    bl, 1
0x1400278b0  jz      short loc_1400278B5
0x1400278b2  or      rbx, r8
0x1400278b5  mov     [rsi], rbx
0x1400278b8  mov     r12, r15
0x1400278bb  mov     rbp, rsi
0x1400278be  shl     r12, 19h
0x1400278c2  shl     rbp, 19h
0x1400278c6  sub     rbp, r12
0x1400278c9  sar     rbp, 10h
0x1400278cd  call    SkmiGetHyperspacePte
0x1400278d2  shl     rdi, 0Ch
0x1400278d6  mov     rbx, rax
0x1400278d9  mov     rax, 0FFFFFFFFFF000h
0x1400278e3  and     rdi, rax
0x1400278e6  mov     rax, 8000000000000021h
0x1400278f0  xor     rdi, rax
0x1400278f3  cmp     cs:SkmiDataTraces, r13
0x1400278fa  jz      loc_140027A12
0x140027900  mov     rax, gs:8
0x140027909  mov     r9, [rbx]
0x14002790c  test    rax, rax
0x14002790f  jz      short loc_14002791A
0x140027911  cmp     [rax+158h], r13b
0x140027918  jnz     short loc_140027974
0x14002791a  test    rbx, rbx
0x14002791d  jz      loc_140027A12
0x140027923  mov     rax, r15
0x140027926  cmp     rbx, rax
0x140027929  jb      short loc_140027941
0x14002792b  mov     rax, 0FFFFF6FFFFFFFFFFh
0x140027935  mov     rax, rax
0x140027938  cmp     rbx, rax
0x14002793b  jbe     loc_140027A12
0x140027941  mov     rax, 0FFFFF60000000000h
0x14002794b  mov     rax, rax
0x14002794e  cmp     rbx, rax
0x140027951  jb      short loc_140027969
0x140027953  mov     rax, 0FFFFF67FFFFFFFFFh
0x14002795d  mov     rax, rax
0x140027960  cmp     rbx, rax
0x140027963  jbe     loc_140027A12
0x140027969  bt      r9, 34h ; '4'
0x14002796e  jnb     loc_140027A12
0x140027974  mov     eax, 1
0x140027979  lock xadd cs:SkmiDataTraceIndex, eax
0x140027981  mov     edx, cs:SkmiDataTraceSize
0x140027987  dec     edx
0x140027989  and     rdx, rax
0x14002798c  lea     r14, [rdx+rdx*2]
0x140027990  shl     r14, 5
0x140027994  add     r14, cs:SkmiDataTraces
0x14002799b  mov     [r14], r13
0x14002799e  mov     [r14+8], r13
0x1400279a2  jz      short loc_140027A08
0x1400279a4  xor     edx, edx; Val
0x1400279a6  mov     [r14], rbx
0x1400279a9  lea     r15, [r14+20h]
0x1400279ad  mov     [r14+10h], r9
0x1400279b1  mov     rcx, r15; void *
0x1400279b4  mov     [r14+18h], rdi
0x1400279b8  mov     byte ptr [r14+8], 1
0x1400279bd  lea     r8d, [rdx+40h]; Size
0x1400279c1  call    memset_0
0x1400279c6  test    cs:SkmiFlags, 400000h
0x1400279d0  jz      short loc_140027A08
0x1400279d2  mov     rax, gs:8
0x1400279db  test    rax, rax
0x1400279de  jz      short loc_140027A08
0x1400279e0  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x1400279e5  mov     r8, r15; BackTrace
0x1400279e8  mov     edx, 8; FramesToCapture
0x1400279ed  call    RtlCaptureStackBackTrace
0x1400279f2  test    ax, ax
0x1400279f5  jnz     short loc_140027A08
0x1400279f7  mov     rax, [rsp+68h]
0x1400279fc  mov     [r14+28h], rax
0x140027a00  call    SkmiGetInstructionPointer
0x140027a05  mov     [r15], rax
0x140027a08  mov     r14, 0FFFFF6FB7DBED800h
0x140027a12  mov     rax, 0FFFFF6FB7DBED000h
0x140027a1c  mov     rax, rax
0x140027a1f  cmp     rbx, rax
0x140027a22  jb      short loc_140027A7D
0x140027a24  mov     rax, r14
0x140027a27  cmp     rbx, rax
0x140027a2a  jnb     short loc_140027A7D
0x140027a2c  mov     rax, gs:8
0x140027a35  test    rax, rax
0x140027a38  jz      short loc_140027A40
0x140027a3a  mov     rcx, [rax+50h]
0x140027a3e  jmp     short loc_140027A43
0x140027a40  mov     rcx, r13
0x140027a43  mov     rdx, [rcx+0E8h]
0x140027a4a  test    rdx, rdx
0x140027a4d  jz      short loc_140027A7D
0x140027a4f  mov     ecx, cs:SkiKvaShadowMode
0x140027a55  mov     rax, rbx
0x140027a58  sar     rax, 3
0x140027a5c  and     eax, 1FFh
0x140027a61  mov     [rdx+rax*8], rdi
0x140027a65  cmp     ecx, 2
0x140027a68  jz      short loc_140027A7D
0x140027a6a  test    dil, 1
0x140027a6e  jz      short loc_140027A7D
0x140027a70  mov     rax, 8000000000000000h
0x140027a7a  or      rdi, rax
0x140027a7d  mov     rdx, rbx
0x140027a80  mov     [rbx], rdi
0x140027a83  shl     rdx, 19h
0x140027a87  mov     rcx, rbp
0x140027a8a  sub     rdx, r12
0x140027a8d  sar     rdx, 10h
0x140027a91  call    SkeCopyPage
0x140027a96  mov     rcx, rbx
0x140027a99  call    SkmiReleaseHyperspacePte
0x140027a9e  mov     rcx, rsi
0x140027aa1  call    SkmiReleaseHyperspacePte
0x140027aa6  add     rsp, 28h
0x140027aaa  pop     r15
0x140027aac  pop     r14
0x140027aae  pop     r13
0x140027ab0  pop     r12
0x140027ab2  pop     rdi
0x140027ab3  pop     rsi
0x140027ab4  pop     rbp
0x140027ab5  pop     rbx
0x140027ab6  retn
```
