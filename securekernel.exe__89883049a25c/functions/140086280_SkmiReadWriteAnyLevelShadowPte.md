# SkmiReadWriteAnyLevelShadowPte

- ea: `0x140086280`
- end: `0x140086626`
- name: `SkmiReadWriteAnyLevelShadowPte`
- size: `934`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140033828`
- `0x140033968`

## callees

- `0x140003780`
- `0x140009940`
- `0x14000c8d0`
- `0x14002b534`
- `0x140081290`
- `0x140086280`
- `0x1400f2fc0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
unsigned __int64 __fastcall SkmiReadWriteAnyLevelShadowPte(unsigned __int64 a1, int a2, char a3, unsigned __int64 a4)
{
  _QWORD *StackBase; // rax
  __int64 v5; // r10
  unsigned __int8 CurrentIrql; // r13
  unsigned __int64 v9; // rdi
  __int64 HyperspacePte; // r15
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // ebx
  unsigned __int64 i; // r8
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 PteTrace; // rax
  __int64 v18; // rbp
  PVOID *v19; // r14
  ULONG v20; // ecx
  USHORT v21; // ax
  __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  int v27; // edx
  __int64 v28; // r14
  unsigned __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // r10
  __int64 v32; // rbp
  PVOID *v33; // rsi
  ULONG v34; // ecx
  USHORT v35; // ax
  __int64 v36; // rdx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  int v41; // ecx
  __int64 v42; // rcx
  int v45; // [rsp+38h] [rbp-70h]
  ULONG BackTraceHash; // [rsp+40h] [rbp-68h] BYREF
  _OWORD v47[2]; // [rsp+48h] [rbp-60h] BYREF
  _UNKNOWN *retaddr; // [rsp+A8h] [rbp+0h]

  StackBase = KeGetPcr()->NtTib.StackBase;
  LOBYTE(v5) = 0;
  CurrentIrql = -1;
  v9 = 0;
  HyperspacePte = 0;
  memset(v47, 0, sizeof(v47));
  if ( StackBase )
    v11 = StackBase[10];
  else
    v11 = 0;
  v12 = *(_QWORD *)(v11 + 232);
  v13 = a2;
  for ( i = 0xFFFFF68000000000uLL; v13 < 4; ++v13 )
  {
    *((_QWORD *)v47 + v13) = a1;
    a1 = ((a1 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  }
  v15 = 2;
  while ( 1 )
  {
    v16 = *((_QWORD *)v47 + --v13);
    v45 = v16;
    if ( v13 != 3 )
    {
      if ( CurrentIrql == 0xFF )
      {
        CurrentIrql = KeGetCurrentIrql();
        __writecr8(2u);
      }
      else
      {
        SkmiReleaseHyperspacePte(HyperspacePte);
      }
      HyperspacePte = SkmiGetHyperspacePte(v15, v12, i, a4);
      v9 = v9 & 0xFFFFFFFFFF000LL ^ 0x8000000000000063uLL;
      PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, v9, *(_QWORD *)HyperspacePte);
      v5 = 0;
      v18 = PteTrace;
      if ( PteTrace )
      {
        v19 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, 0x40u);
        v5 = 0;
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          if ( KeGetPcr()->NtTib.StackBase )
          {
            v21 = RtlCaptureStackBackTrace(v20, 8u, v19, &BackTraceHash);
            v5 = 0;
            if ( !v21 )
            {
              *(_QWORD *)(v18 + 40) = retaddr;
              *v19 = (PVOID)SkmiGetInstructionPointer(v23, v22);
            }
          }
        }
        LODWORD(v16) = v45;
      }
      v24 = v9;
      if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
        && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL
        && ((v25 = KeGetPcr()->NtTib.StackBase) == 0 ? (v26 = v5) : (v26 = v25[10]), (i = *(_QWORD *)(v26 + 232)) != 0) )
      {
        v27 = SkiKvaShadowMode;
        *(_QWORD *)(i + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v9;
        v15 = 2;
        if ( v27 != 2 && (v9 & 1) != 0 )
          v24 = v9 | 0x8000000000000000uLL;
      }
      else
      {
        v15 = 2;
      }
      *(_QWORD *)HyperspacePte = v24;
      v12 = HyperspacePte << 25 >> 16;
    }
    v28 = v12 + 8LL * (((unsigned int)v16 >> 3) & 0x1FF);
    if ( a3 != (_BYTE)v5 && v13 == a2 )
      break;
    v9 = *(_QWORD *)v28;
    if ( v13 <= a2 )
      goto LABEL_51;
  }
  if ( v13 || (a4 & 1) == 0 )
    v29 = a4;
  else
    v29 = ((unsigned __int64)HIBYTE(word_140156D90) << 8)
        ^ (a4
         ^ ((unsigned __int64)HIBYTE(word_140156D90) << 8))
        & 0xFFFFFFFFFFFFFEFFuLL;
  v30 = SkmiGetPteTrace(0, v28, 0, v29, *(_QWORD *)v28);
  v32 = v30;
  if ( v30 )
  {
    v33 = (PVOID *)(v30 + 32);
    memset_0((void *)(v30 + 32), 0, 0x40u);
    v31 = 0;
    if ( (SkmiFlags & 0x400000) != 0 )
    {
      if ( KeGetPcr()->NtTib.StackBase )
      {
        v35 = RtlCaptureStackBackTrace(v34, 8u, v33, &BackTraceHash);
        v31 = 0;
        if ( !v35 )
        {
          *(_QWORD *)(v32 + 40) = retaddr;
          *v33 = (PVOID)SkmiGetInstructionPointer(v37, v36);
        }
      }
    }
  }
  if ( (unsigned __int64)v28 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v28 < 0xFFFFF6FB7DBED800uLL )
  {
    v38 = KeGetPcr()->NtTib.StackBase;
    v39 = v38 ? v38[10] : v31;
    v40 = *(_QWORD *)(v39 + 232);
    if ( v40 )
    {
      v41 = SkiKvaShadowMode;
      *(_QWORD *)(v40 + 8 * ((v28 >> 3) & 0x1FF)) = v29;
      if ( v41 != 2 && (v29 & 1) != 0 )
        v29 |= 0x8000000000000000uLL;
    }
  }
  *(_QWORD *)v28 = v29;
LABEL_51:
  if ( CurrentIrql != 0xFF )
  {
    SkmiReleaseHyperspacePte(HyperspacePte);
    LOBYTE(v42) = CurrentIrql;
    SkeLowerIrql(v42);
  }
  return v9;
}

```

## disassembly

```asm
0x140086280  mov     [rsp+arg_10], rbx
0x140086285  push    rbp
0x140086286  push    rsi
0x140086287  push    rdi
0x140086288  push    r12
0x14008628a  push    r13
0x14008628c  push    r14
0x14008628e  push    r15
0x140086290  sub     rsp, 70h
0x140086294  mov     rax, cs:__security_cookie
0x14008629b  xor     rax, rsp
0x14008629e  mov     [rsp+0A8h+var_40], rax
0x1400862a3  mov     rax, gs:8
0x1400862ac  xor     r10d, r10d
0x1400862af  mov     [rsp+0A8h+var_78], r8b
0x1400862b4  xorps   xmm0, xmm0
0x1400862b7  mov     rsi, r9
0x1400862ba  mov     r12d, edx
0x1400862bd  mov     r13b, 0FFh
0x1400862c0  mov     edi, r10d
0x1400862c3  mov     r15d, r10d
0x1400862c6  movups  [rsp+0A8h+var_60], xmm0
0x1400862cb  movups  [rsp+0A8h+var_50], xmm0
0x1400862d0  test    rax, rax
0x1400862d3  jz      short loc_1400862DB
0x1400862d5  mov     rax, [rax+50h]
0x1400862d9  jmp     short loc_1400862DE
0x1400862db  mov     rax, r10
0x1400862de  mov     rdx, [rax+0E8h]
0x1400862e5  mov     ebx, r12d
0x1400862e8  mov     r8, 0FFFFF68000000000h
0x1400862f2  cmp     r12d, 4
0x1400862f6  jge     short loc_14008631E
0x1400862f8  movsxd  rax, ebx
0x1400862fb  mov     qword ptr [rsp+rax*8+0A8h+var_60], rcx
0x140086300  mov     rax, 7FFFFFFFF8h
0x14008630a  shr     rcx, 9
0x14008630e  and     rcx, rax
0x140086311  mov     rax, r8
0x140086314  add     rcx, rax
0x140086317  inc     ebx
0x140086319  cmp     ebx, 4
0x14008631c  jl      short loc_1400862F8
0x14008631e  mov     ecx, 2
0x140086323  dec     ebx
0x140086325  movsxd  rax, ebx
0x140086328  mov     r14, qword ptr [rsp+rax*8+0A8h+var_60]
0x14008632d  mov     [rsp+0A8h+var_70], r14
0x140086332  cmp     ebx, 3
0x140086335  jz      loc_14008649F
0x14008633b  cmp     r13b, 0FFh
0x14008633f  jz      short loc_14008634B
0x140086341  mov     rcx, r15
0x140086344  call    SkmiReleaseHyperspacePte
0x140086349  jmp     short loc_140086353
0x14008634b  mov     r13, cr8
0x14008634f  mov     cr8, rcx
0x140086353  call    SkmiGetHyperspacePte
0x140086358  mov     r15, rax
0x14008635b  xor     r8d, r8d
0x14008635e  mov     rax, 0FFFFFFFFFF000h
0x140086368  mov     rdx, r15
0x14008636b  and     rdi, rax
0x14008636e  xor     ecx, ecx
0x140086370  mov     rax, 8000000000000063h
0x14008637a  xor     rdi, rax
0x14008637d  mov     rax, [r15]
0x140086380  mov     r9, rdi
0x140086383  mov     [rsp+0A8h+var_88], rax
0x140086388  call    SkmiGetPteTrace
0x14008638d  xor     r10d, r10d
0x140086390  mov     rbp, rax
0x140086393  test    rax, rax
0x140086396  jz      short loc_1400863F9
0x140086398  lea     r14, [rax+20h]
0x14008639c  xor     edx, edx; Val
0x14008639e  mov     rcx, r14; void *
0x1400863a1  lea     r8d, [r10+40h]; Size
0x1400863a5  call    memset_0
0x1400863aa  xor     r10d, r10d
0x1400863ad  test    cs:SkmiFlags, 400000h
0x1400863b7  jz      short loc_1400863F4
0x1400863b9  mov     rax, gs:8
0x1400863c2  test    rax, rax
0x1400863c5  jz      short loc_1400863F4
0x1400863c7  lea     r9, [rsp+0A8h+BackTraceHash]; BackTraceHash
0x1400863cc  mov     r8, r14; BackTrace
0x1400863cf  lea     edx, [r10+8]; FramesToCapture
0x1400863d3  call    RtlCaptureStackBackTrace
0x1400863d8  xor     r10d, r10d
0x1400863db  test    ax, ax
0x1400863de  jnz     short loc_1400863F4
0x1400863e0  mov     rax, [rsp+0A8h]
0x1400863e8  mov     [rbp+28h], rax
0x1400863ec  call    SkmiGetInstructionPointer
0x1400863f1  mov     [r14], rax
0x1400863f4  mov     r14, [rsp+0A8h+var_70]
0x1400863f9  mov     rax, rdi
0x1400863fc  mov     rcx, 0FFFFF6FB7DBED000h
0x140086406  mov     rcx, rcx
0x140086409  cmp     r15, rcx
0x14008640c  jb      short loc_140086478
0x14008640e  mov     rcx, 0FFFFF6FB7DBED800h
0x140086418  mov     rcx, rcx
0x14008641b  cmp     r15, rcx
0x14008641e  jnb     short loc_140086478
0x140086420  mov     rcx, gs:8
0x140086429  test    rcx, rcx
0x14008642c  jz      short loc_140086434
0x14008642e  mov     rdx, [rcx+50h]
0x140086432  jmp     short loc_140086437
0x140086434  mov     rdx, r10
0x140086437  mov     r8, [rdx+0E8h]
0x14008643e  test    r8, r8
0x140086441  jz      short loc_140086478
0x140086443  mov     edx, cs:SkiKvaShadowMode
0x140086449  mov     rcx, r15
0x14008644c  sar     rcx, 3
0x140086450  and     ecx, 1FFh
0x140086456  mov     [r8+rcx*8], rdi
0x14008645a  mov     ecx, 2
0x14008645f  cmp     edx, ecx
0x140086461  jz      short loc_14008647D
0x140086463  test    dil, 1
0x140086467  jz      short loc_14008647D
0x140086469  mov     rdx, 8000000000000000h
0x140086473  or      rax, rdx
0x140086476  jmp     short loc_14008647D
0x140086478  mov     ecx, 2
0x14008647d  mov     rdx, r15
0x140086480  mov     [r15], rax
0x140086483  shl     rdx, 19h
0x140086487  mov     rax, 0FFFFF68000000000h
0x140086491  mov     rax, rax
0x140086494  shl     rax, 19h
0x140086498  sub     rdx, rax
0x14008649b  sar     rdx, 10h
0x14008649f  mov     eax, r14d
0x1400864a2  shr     rax, 3
0x1400864a6  and     eax, 1FFh
0x1400864ab  lea     r14, [rdx+rax*8]
0x1400864af  cmp     [rsp+0A8h+var_78], r10b
0x1400864b4  jz      short loc_1400864BB
0x1400864b6  cmp     ebx, r12d
0x1400864b9  jz      short loc_1400864CC
0x1400864bb  mov     rdi, [r14]
0x1400864be  cmp     ebx, r12d
0x1400864c1  jg      loc_140086323
0x1400864c7  jmp     loc_1400865E7
0x1400864cc  test    ebx, ebx
0x1400864ce  jnz     short loc_1400864F1
0x1400864d0  test    sil, 1
0x1400864d4  jz      short loc_1400864F1
0x1400864d6  movzx   eax, byte ptr cs:word_140156D90+1
0x1400864dd  shl     rax, 8
0x1400864e1  mov     rbx, rax
0x1400864e4  xor     rbx, rsi
0x1400864e7  btr     rbx, 8
0x1400864ec  xor     rbx, rax
0x1400864ef  jmp     short loc_1400864F4
0x1400864f1  mov     rbx, rsi
0x1400864f4  mov     rax, [r14]
0x1400864f7  mov     r9, rbx
0x1400864fa  xor     r8d, r8d
0x1400864fd  mov     [rsp+0A8h+var_88], rax
0x140086502  mov     rdx, r14
0x140086505  xor     ecx, ecx
0x140086507  call    SkmiGetPteTrace
0x14008650c  mov     rbp, rax
0x14008650f  test    rax, rax
0x140086512  jz      short loc_140086570
0x140086514  xor     edx, edx; Val
0x140086516  lea     rsi, [rax+20h]
0x14008651a  mov     rcx, rsi; void *
0x14008651d  lea     r8d, [rdx+40h]; Size
0x140086521  call    memset_0
0x140086526  xor     r10d, r10d
0x140086529  test    cs:SkmiFlags, 400000h
0x140086533  jz      short loc_140086570
0x140086535  mov     rax, gs:8
0x14008653e  test    rax, rax
0x140086541  jz      short loc_140086570
0x140086543  lea     r9, [rsp+0A8h+BackTraceHash]; BackTraceHash
0x140086548  mov     r8, rsi; BackTrace
0x14008654b  lea     edx, [r10+8]; FramesToCapture
0x14008654f  call    RtlCaptureStackBackTrace
0x140086554  xor     r10d, r10d
0x140086557  test    ax, ax
0x14008655a  jnz     short loc_140086570
0x14008655c  mov     rax, [rsp+0A8h]
0x140086564  mov     [rbp+28h], rax
0x140086568  call    SkmiGetInstructionPointer
0x14008656d  mov     [rsi], rax
0x140086570  mov     rax, 0FFFFF6FB7DBED000h
0x14008657a  mov     rax, rax
0x14008657d  cmp     r14, rax
0x140086580  jb      short loc_1400865E4
0x140086582  mov     rax, 0FFFFF6FB7DBED800h
0x14008658c  mov     rax, rax
0x14008658f  cmp     r14, rax
0x140086592  jnb     short loc_1400865E4
0x140086594  mov     rax, gs:8
0x14008659d  test    rax, rax
0x1400865a0  jz      short loc_1400865A8
0x1400865a2  mov     rcx, [rax+50h]
0x1400865a6  jmp     short loc_1400865AB
0x1400865a8  mov     rcx, r10
0x1400865ab  mov     rdx, [rcx+0E8h]
0x1400865b2  test    rdx, rdx
0x1400865b5  jz      short loc_1400865E4
0x1400865b7  mov     ecx, cs:SkiKvaShadowMode
0x1400865bd  mov     rax, r14
0x1400865c0  sar     rax, 3
0x1400865c4  and     eax, 1FFh
0x1400865c9  mov     [rdx+rax*8], rbx
0x1400865cd  cmp     ecx, 2
0x1400865d0  jz      short loc_1400865E4
0x1400865d2  test    bl, 1
0x1400865d5  jz      short loc_1400865E4
0x1400865d7  mov     rax, 8000000000000000h
0x1400865e1  or      rbx, rax
0x1400865e4  mov     [r14], rbx
0x1400865e7  cmp     r13b, 0FFh
0x1400865eb  jz      short loc_1400865FD
0x1400865ed  mov     rcx, r15
0x1400865f0  call    SkmiReleaseHyperspacePte
0x1400865f5  mov     cl, r13b
0x1400865f8  call    SkeLowerIrql
0x1400865fd  mov     rax, rdi
0x140086600  mov     rcx, [rsp+0A8h+var_40]
0x140086605  xor     rcx, rsp; StackCookie
0x140086608  call    __security_check_cookie
0x14008660d  mov     rbx, [rsp+0A8h+arg_10]
0x140086615  add     rsp, 70h
0x140086619  pop     r15
0x14008661b  pop     r14
0x14008661d  pop     r13
0x14008661f  pop     r12
0x140086621  pop     rdi
0x140086622  pop     rsi
0x140086623  pop     rbp
0x140086624  retn
```
