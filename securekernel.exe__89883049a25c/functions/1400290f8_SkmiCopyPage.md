# SkmiCopyPage

- ea: `0x1400290f8`
- end: `0x140029300`
- name: `SkmiCopyPage`
- size: `520`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400280b0`
- `0x14002d9b0`

## callees

- `0x140009940`
- `0x14000c8d0`
- `0x1400290f8`
- `0x14002b534`
- `0x140081290`
- `0x1400f3000`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCopyPage(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 HyperspacePte; // rdi
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rbx
  _BYTE *StackBase; // rax
  __int64 v10; // rdx
  bool v11; // zf
  unsigned __int64 *v12; // rsi
  ULONG v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // ecx
  unsigned __int64 retaddr; // [rsp+48h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+50h] [rbp+8h] BYREF

  HyperspacePte = SkmiGetHyperspacePte(a1, a2, a3, a4);
  v8 = (a1 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000021uLL;
  if ( SkmiDataTraces )
  {
    if ( (StackBase = KeGetPcr()->NtTib.StackBase, v7 = *(_QWORD *)HyperspacePte, StackBase) && StackBase[344]
      || HyperspacePte
      && (HyperspacePte < 0xFFFFF68000000000uLL || HyperspacePte > 0xFFFFF6FFFFFFFFFFuLL)
      && (HyperspacePte < 0xFFFFF60000000000uLL || HyperspacePte > 0xFFFFF67FFFFFFFFFuLL)
      && (v7 & 0x10000000000000LL) != 0 )
    {
      v10 = _InterlockedExchangeAdd(&SkmiDataTraceIndex, 1u) & (unsigned int)(SkmiDataTraceSize - 1);
      v11 = SkmiDataTraces + 96 * v10 == 0;
      v12 = (unsigned __int64 *)(SkmiDataTraces + 96 * v10);
      *v12 = 0;
      v12[1] = 0;
      if ( !v11 )
      {
        v12[2] = v7;
        *v12 = HyperspacePte;
        v12[3] = v8;
        *((_BYTE *)v12 + 8) = 1;
        memset_0(v12 + 4, 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0
          && KeGetPcr()->NtTib.StackBase
          && !RtlCaptureStackBackTrace(v13, 8u, (PVOID *)v12 + 4, &BackTraceHash) )
        {
          v12[5] = retaddr;
          v12[4] = SkmiGetInstructionPointer(v15, v14);
        }
      }
    }
  }
  if ( HyperspacePte >= 0xFFFFF6FB7DBED000uLL && HyperspacePte < 0xFFFFF6FB7DBED800uLL )
  {
    v16 = KeGetPcr()->NtTib.StackBase;
    if ( v16 )
      v17 = v16[10];
    else
      v17 = 0;
    v18 = *(_QWORD *)(v17 + 232);
    if ( v18 )
    {
      v19 = SkiKvaShadowMode;
      *(_QWORD *)(v18 + 8 * (((__int64)HyperspacePte >> 3) & 0x1FF)) = v8;
      if ( v19 != 2 && (v8 & 1) != 0 )
        v8 |= 0x8000000000000000uLL;
    }
  }
  *(_QWORD *)HyperspacePte = v8;
  SkeCopyPage(a2, (__int64)(HyperspacePte << 25) >> 16, v7);
  return SkmiReleaseHyperspacePte(HyperspacePte);
}

```

## disassembly

```asm
0x1400290f8  mov     [rsp+arg_8], rbx
0x1400290fd  mov     [rsp+arg_10], rbp
0x140029102  push    rsi
0x140029103  push    rdi
0x140029104  push    r12
0x140029106  push    r14
0x140029108  push    r15
0x14002910a  sub     rsp, 20h
0x14002910e  mov     rbp, rdx
0x140029111  mov     rbx, rcx
0x140029114  call    SkmiGetHyperspacePte
0x140029119  shl     rbx, 0Ch
0x14002911d  mov     rdi, rax
0x140029120  mov     rax, 0FFFFFFFFFF000h
0x14002912a  mov     r12, 0FFFFF68000000000h
0x140029134  and     rbx, rax
0x140029137  xor     r15d, r15d
0x14002913a  mov     rax, 8000000000000021h
0x140029144  xor     rbx, rax
0x140029147  cmp     cs:SkmiDataTraces, r15
0x14002914e  jz      loc_140029252
0x140029154  mov     rax, gs:8
0x14002915d  mov     r8, [rdi]
0x140029160  test    rax, rax
0x140029163  jz      short loc_14002916E
0x140029165  cmp     [rax+158h], r15b
0x14002916c  jnz     short loc_1400291BF
0x14002916e  test    rdi, rdi
0x140029171  jz      loc_140029252
0x140029177  mov     rax, r12
0x14002917a  cmp     rdi, rax
0x14002917d  jb      short loc_140029192
0x14002917f  mov     rax, 0FFFFF6FFFFFFFFFFh
0x140029189  cmp     rdi, rax
0x14002918c  jbe     loc_140029252
0x140029192  mov     rax, 0FFFFF60000000000h
0x14002919c  cmp     rdi, rax
0x14002919f  jb      short loc_1400291B4
0x1400291a1  mov     rax, 0FFFFF67FFFFFFFFFh
0x1400291ab  cmp     rdi, rax
0x1400291ae  jbe     loc_140029252
0x1400291b4  bt      r8, 34h ; '4'
0x1400291b9  jnb     loc_140029252
0x1400291bf  mov     eax, 1
0x1400291c4  lock xadd cs:SkmiDataTraceIndex, eax
0x1400291cc  mov     edx, cs:SkmiDataTraceSize
0x1400291d2  dec     edx
0x1400291d4  and     rdx, rax
0x1400291d7  lea     rsi, [rdx+rdx*2]
0x1400291db  shl     rsi, 5
0x1400291df  add     rsi, cs:SkmiDataTraces
0x1400291e6  mov     [rsi], r15
0x1400291e9  mov     [rsi+8], r15
0x1400291ed  jz      short loc_140029252
0x1400291ef  xor     edx, edx; Val
0x1400291f1  mov     [rsi+10h], r8
0x1400291f5  lea     r14, [rsi+20h]
0x1400291f9  mov     [rsi], rdi
0x1400291fc  mov     rcx, r14; void *
0x1400291ff  mov     [rsi+18h], rbx
0x140029203  mov     byte ptr [rsi+8], 1
0x140029207  lea     r8d, [rdx+40h]; Size
0x14002920b  call    memset_0
0x140029210  test    cs:SkmiFlags, 400000h
0x14002921a  jz      short loc_140029252
0x14002921c  mov     rax, gs:8
0x140029225  test    rax, rax
0x140029228  jz      short loc_140029252
0x14002922a  lea     r9, [rsp+48h+BackTraceHash]; BackTraceHash
0x14002922f  mov     r8, r14; BackTrace
0x140029232  mov     edx, 8; FramesToCapture
0x140029237  call    RtlCaptureStackBackTrace
0x14002923c  test    ax, ax
0x14002923f  jnz     short loc_140029252
0x140029241  mov     rax, [rsp+48h]
0x140029246  mov     [rsi+28h], rax
0x14002924a  call    SkmiGetInstructionPointer
0x14002924f  mov     [r14], rax
0x140029252  mov     rax, 0FFFFF6FB7DBED000h
0x14002925c  cmp     rdi, rax
0x14002925f  jb      short loc_1400292C0
0x140029261  mov     rax, 0FFFFF6FB7DBED800h
0x14002926b  cmp     rdi, rax
0x14002926e  jnb     short loc_1400292C0
0x140029270  mov     rax, gs:8
0x140029279  test    rax, rax
0x14002927c  jz      short loc_140029284
0x14002927e  mov     rcx, [rax+50h]
0x140029282  jmp     short loc_140029287
0x140029284  mov     rcx, r15
0x140029287  mov     rdx, [rcx+0E8h]
0x14002928e  test    rdx, rdx
0x140029291  jz      short loc_1400292C0
0x140029293  mov     ecx, cs:SkiKvaShadowMode
0x140029299  mov     rax, rdi
0x14002929c  sar     rax, 3
0x1400292a0  and     eax, 1FFh
0x1400292a5  mov     [rdx+rax*8], rbx
0x1400292a9  cmp     ecx, 2
0x1400292ac  jz      short loc_1400292C0
0x1400292ae  test    bl, 1
0x1400292b1  jz      short loc_1400292C0
0x1400292b3  mov     rax, 8000000000000000h
0x1400292bd  or      rbx, rax
0x1400292c0  mov     rdx, rdi
0x1400292c3  mov     [rdi], rbx
0x1400292c6  shl     rdx, 19h
0x1400292ca  mov     rax, r12
0x1400292cd  shl     rax, 19h
0x1400292d1  mov     rcx, rbp
0x1400292d4  sub     rdx, rax
0x1400292d7  sar     rdx, 10h
0x1400292db  call    SkeCopyPage
0x1400292e0  mov     rcx, rdi
0x1400292e3  call    SkmiReleaseHyperspacePte
0x1400292e8  mov     rbx, [rsp+48h+arg_8]
0x1400292ed  mov     rbp, [rsp+48h+arg_10]
0x1400292f2  add     rsp, 20h
0x1400292f6  pop     r15
0x1400292f8  pop     r14
0x1400292fa  pop     r12
0x1400292fc  pop     rdi
0x1400292fd  pop     rsi
0x1400292fe  retn
```
