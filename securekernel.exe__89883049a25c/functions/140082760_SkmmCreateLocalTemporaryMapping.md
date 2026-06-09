# SkmmCreateLocalTemporaryMapping

- ea: `0x140082760`
- end: `0x140082981`
- name: `SkmmCreateLocalTemporaryMapping`
- size: `545`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x140082988`
- `0x14008ac3c`
- `0x14009ac38`
- `0x1400a5dac`

## callees

- `0x140003780`
- `0x140009940`
- `0x1400119c4`
- `0x14002aeac`
- `0x14002b534`
- `0x140036860`
- `0x140081290`
- `0x140082760`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmCreateLocalTemporaryMapping(__int64 a1, ULONG_PTR a2, __int64 a3, __int64 a4)
{
  int v4; // esi
  __int64 HyperspacePte; // rdi
  int v7; // ecx
  int v8; // edx
  int v9; // r8d
  __int64 v10; // rax
  unsigned __int64 v11; // rbx
  __int64 PteTrace; // rax
  __int64 v13; // rbp
  PVOID *v14; // rsi
  PVOID StackBase; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21; // ecx
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+50h] [rbp+8h] BYREF

  v4 = a3;
  HyperspacePte = SkmiGetHyperspacePte(a1, a2, a3, a4);
  if ( v4 == 128 )
  {
    v7 = 0x10000;
  }
  else
  {
    v8 = ((v4 & 2) != 0 ? 4 : 1) | 2;
    if ( (v4 & 0x10) == 0 )
      v8 = (v4 & 2) != 0 ? 4 : 1;
    v7 = v8 | 0x20000;
    if ( (v4 & 0x40) == 0 )
      v7 = v8;
    if ( (v4 & 0x20) != 0 )
    {
      if ( (v4 & 0x400) != 0 )
        v7 |= 0x18u;
      else
        v7 |= 0x10u;
    }
  }
  v9 = v7 | 0x40000;
  if ( (v4 & 0x1000) == 0 )
    v9 = v7;
  if ( v9 == 0x10000 )
    v10 = 4;
  else
    v10 = v9 & 0x1F;
  v11 = (a2 << 12) ^ (SkmiProtectionToPte[v10] ^ (a2 << 12)) & 0xFFF0000000000FFFuLL;
  if ( (v4 & 0x400) != 0 )
  {
    SkmiIncrementIoPageReferenceCount(a2, 0);
    v11 |= 0x80000000000000uLL;
  }
  else if ( !(unsigned int)SkmiIncrementSharedPageReferenceCount(a2) )
  {
    SkeBugCheckEx(0x1Au, 0x56534Du, 0x92Eu, a2, 0);
  }
  PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, v11, *(_QWORD *)HyperspacePte);
  v13 = PteTrace;
  if ( PteTrace )
  {
    v14 = (PVOID *)(PteTrace + 32);
    memset_0((void *)(PteTrace + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      StackBase = KeGetPcr()->NtTib.StackBase;
      if ( StackBase )
      {
        if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v14, &BackTraceHash) )
        {
          *(_QWORD *)(v13 + 40) = retaddr;
          *v14 = (PVOID)SkmiGetInstructionPointer(v17, v16);
        }
      }
    }
  }
  if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
    && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
  {
    v18 = KeGetPcr()->NtTib.StackBase;
    if ( v18 )
      v19 = v18[10];
    else
      v19 = 0;
    v20 = *(_QWORD *)(v19 + 232);
    if ( v20 )
    {
      v21 = SkiKvaShadowMode;
      *(_QWORD *)(v20 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v11;
      if ( v21 != 2 && (v11 & 1) != 0 )
        v11 |= 0x8000000000000000uLL;
    }
  }
  *(_QWORD *)HyperspacePte = v11;
  return HyperspacePte << 25 >> 16;
}

```

## disassembly

```asm
0x140082760  mov     [rsp+arg_8], rbx
0x140082765  mov     [rsp+arg_10], rbp
0x14008276a  push    rsi
0x14008276b  push    rdi
0x14008276c  push    r14
0x14008276e  sub     rsp, 30h
0x140082772  mov     esi, r8d
0x140082775  mov     rbp, rdx
0x140082778  call    SkmiGetHyperspacePte
0x14008277d  xor     r14d, r14d
0x140082780  mov     rdi, rax
0x140082783  mov     r10d, 10000h
0x140082789  cmp     esi, 80h
0x14008278f  jnz     short loc_140082796
0x140082791  mov     ecx, r10d
0x140082794  jmp     short loc_1400827D0
0x140082796  mov     eax, esi
0x140082798  and     al, 2
0x14008279a  neg     al
0x14008279c  sbb     ecx, ecx
0x14008279e  and     ecx, 3
0x1400827a1  inc     ecx
0x1400827a3  mov     edx, ecx
0x1400827a5  or      edx, 2
0x1400827a8  test    sil, 10h
0x1400827ac  cmovz   edx, ecx
0x1400827af  mov     ecx, edx
0x1400827b1  bts     ecx, 11h
0x1400827b5  test    sil, 40h
0x1400827b9  cmovz   ecx, edx
0x1400827bc  test    sil, 20h
0x1400827c0  jz      short loc_1400827D0
0x1400827c2  bt      esi, 0Ah
0x1400827c6  jnb     short loc_1400827CD
0x1400827c8  or      ecx, 18h
0x1400827cb  jmp     short loc_1400827D0
0x1400827cd  or      ecx, 10h
0x1400827d0  mov     r8d, ecx
0x1400827d3  mov     r9d, esi
0x1400827d6  bts     r8d, 12h
0x1400827db  and     r9d, 1000h
0x1400827e2  cmovz   r8d, ecx
0x1400827e6  cmp     r8d, r10d
0x1400827e9  jnz     short loc_1400827F2
0x1400827eb  mov     eax, 4
0x1400827f0  jmp     short loc_1400827F8
0x1400827f2  mov     eax, r8d
0x1400827f5  and     eax, 1Fh
0x1400827f8  mov     rcx, rbp
0x1400827fb  lea     rdx, SkmiProtectionToPte
0x140082802  shl     rcx, 0Ch
0x140082806  mov     rbx, rcx
0x140082809  xor     rbx, [rdx+rax*8]
0x14008280d  mov     rax, 0FFF0000000000FFFh
0x140082817  and     rbx, rax
0x14008281a  xor     rbx, rcx
0x14008281d  mov     rcx, rbp; BugCheckParameter3
0x140082820  bt      esi, 0Ah
0x140082824  jb      short loc_140082858
0x140082826  mov     edx, r8d
0x140082829  and     edx, 0FFFFFFFBh
0x14008282c  test    r9d, r9d
0x14008282f  cmovz   edx, r8d
0x140082833  call    SkmiIncrementSharedPageReferenceCount
0x140082838  test    eax, eax
0x14008283a  jnz     short loc_14008286C
0x14008283c  mov     r9, rbp; BugCheckParameter3
0x14008283f  mov     [rsp+48h+BugCheckParameter4], r14; BugCheckParameter4
0x140082844  mov     edx, 56534Dh; BugCheckParameter1
0x140082849  lea     ecx, [rax+1Ah]; BugCheckCode
0x14008284c  mov     r8d, 92Eh; BugCheckParameter2
0x140082852  call    SkeBugCheckEx
0x140082858  xor     edx, edx; BugCheckParameter4
0x14008285a  call    SkmiIncrementIoPageReferenceCount
0x14008285f  mov     rax, 80000000000000h
0x140082869  or      rbx, rax
0x14008286c  mov     rax, [rdi]
0x14008286f  mov     r9, rbx
0x140082872  xor     r8d, r8d
0x140082875  mov     [rsp+48h+BugCheckParameter4], rax
0x14008287a  mov     rdx, rdi
0x14008287d  xor     ecx, ecx
0x14008287f  call    SkmiGetPteTrace
0x140082884  mov     rbp, rax
0x140082887  test    rax, rax
0x14008288a  jz      short loc_1400828E0
0x14008288c  xor     edx, edx; Val
0x14008288e  lea     rsi, [rax+20h]
0x140082892  mov     rcx, rsi; void *
0x140082895  lea     r8d, [rdx+40h]; Size
0x140082899  call    memset_0
0x14008289e  test    cs:SkmiFlags, 400000h
0x1400828a8  jz      short loc_1400828E0
0x1400828aa  mov     rcx, gs:8; FramesToSkip
0x1400828b3  test    rcx, rcx
0x1400828b6  jz      short loc_1400828E0
0x1400828b8  lea     r9, [rsp+48h+BackTraceHash]; BackTraceHash
0x1400828bd  mov     r8, rsi; BackTrace
0x1400828c0  mov     edx, 8; FramesToCapture
0x1400828c5  call    RtlCaptureStackBackTrace
0x1400828ca  test    ax, ax
0x1400828cd  jnz     short loc_1400828E0
0x1400828cf  mov     rax, [rsp+48h]
0x1400828d4  mov     [rbp+28h], rax
0x1400828d8  call    SkmiGetInstructionPointer
0x1400828dd  mov     [rsi], rax
0x1400828e0  mov     rax, 0FFFFF6FB7DBED000h
0x1400828ea  cmp     rdi, rax
0x1400828ed  jb      short loc_14008294E
0x1400828ef  mov     rax, 0FFFFF6FB7DBED800h
0x1400828f9  cmp     rdi, rax
0x1400828fc  jnb     short loc_14008294E
0x1400828fe  mov     rax, gs:8
0x140082907  test    rax, rax
0x14008290a  jz      short loc_140082912
0x14008290c  mov     rcx, [rax+50h]
0x140082910  jmp     short loc_140082915
0x140082912  mov     rcx, r14
0x140082915  mov     rdx, [rcx+0E8h]
0x14008291c  test    rdx, rdx
0x14008291f  jz      short loc_14008294E
0x140082921  mov     ecx, cs:SkiKvaShadowMode
0x140082927  mov     rax, rdi
0x14008292a  sar     rax, 3
0x14008292e  and     eax, 1FFh
0x140082933  mov     [rdx+rax*8], rbx
0x140082937  cmp     ecx, 2
0x14008293a  jz      short loc_14008294E
0x14008293c  test    bl, 1
0x14008293f  jz      short loc_14008294E
0x140082941  mov     rax, 8000000000000000h
0x14008294b  or      rbx, rax
0x14008294e  mov     [rdi], rbx
0x140082951  shl     rdi, 19h
0x140082955  mov     rcx, 0FFFFF68000000000h
0x14008295f  mov     rbx, [rsp+48h+arg_8]
0x140082964  mov     rbp, [rsp+48h+arg_10]
0x140082969  shl     rcx, 19h
0x14008296d  sub     rdi, rcx
0x140082970  sar     rdi, 10h
0x140082974  mov     rax, rdi
0x140082977  add     rsp, 30h
0x14008297b  pop     r14
0x14008297d  pop     rdi
0x14008297e  pop     rsi
0x14008297f  retn
```
