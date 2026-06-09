# SkmiCommitPte

- ea: `0x14007fd10`
- end: `0x1400801ba`
- name: `SkmiCommitPte`
- size: `1194`
- prototype: ``
- caller_count: `7`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14002e800`
- `0x14002eabc`
- `0x140037fe4`
- `0x14004d96c`
- `0x14004e088`
- `0x14004ece0`
- `0x140059270`

## callees

- `0x140003780`
- `0x140020360`
- `0x14002b534`
- `0x14003148c`
- `0x140038588`
- `0x140039f74`
- `0x140050b48`
- `0x14007fd10`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCommitPte(unsigned __int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  unsigned __int64 v6; // rbx
  unsigned int j; // ecx
  unsigned int v8; // edi
  unsigned int v9; // esi
  unsigned __int64 *v11; // rsi
  __int64 i; // rax
  __int64 v13; // rdi
  unsigned __int64 v14; // rax
  __int64 PteTrace; // rax
  _QWORD *StackBase; // rcx
  int v17; // r9d
  unsigned __int64 v18; // r11
  __int64 v19; // r13
  PVOID *v20; // r15
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // r13
  PVOID *v26; // r15
  PVOID v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned __int64 v30; // rax
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // edx
  int v35; // [rsp+30h] [rbp-40h]
  ULONG BackTraceHash; // [rsp+34h] [rbp-3Ch] BYREF
  unsigned __int64 v37; // [rsp+38h] [rbp-38h] BYREF
  __int64 v38; // [rsp+40h] [rbp-30h]
  __int128 v39; // [rsp+48h] [rbp-28h]
  __int128 v40; // [rsp+58h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+A8h] [rbp+38h]

  v39 = 0;
  v40 = 0;
  v5 = 4;
  v6 = (-(__int64)(a1 < 0xFFFFF6C000000000uLL) & 4) + 99;
  v37 = v6;
  do
  {
    *(&v38 + v5--) = a1;
    a1 = ((a1 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  }
  while ( v5 );
  if ( !a2 )
  {
LABEL_13:
    v11 = 0;
    if ( a3 )
      v38 = *(_QWORD *)(a3 + 72);
    else
      v38 = 0;
    for ( i = 0; ; i = (unsigned int)(v35 + 1) )
    {
      v35 = i;
      if ( (unsigned int)i >= 3 )
      {
        if ( !**((_QWORD **)&v40 + 1) && v11 )
          *v11 = (*v11 + 1) ^ (*v11 ^ (*v11 + 1)) & 0xFFFFF00000000000uLL;
        return 1;
      }
      v13 = *((_QWORD *)&v39 + i);
      v14 = *(_QWORD *)v13;
      if ( (*(_QWORD *)v13 & 0x80000000000000LL) != 0 )
      {
        PteTrace = SkmiGetPteTrace(0, v13, 0, 0, *(_QWORD *)v13);
        v19 = PteTrace;
        if ( PteTrace )
        {
          v20 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, (unsigned int)(v17 + 64));
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            StackBase = KeGetPcr()->NtTib.StackBase;
            if ( StackBase )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v20, &BackTraceHash) )
              {
                *(_QWORD *)(v19 + 40) = retaddr;
                *v20 = (PVOID)SkmiGetInstructionPointer(StackBase, v21);
              }
            }
          }
          v18 = 0xFFFFF6FB7DBED800uLL;
        }
        if ( (unsigned __int64)v13 >= 0xFFFFF6FB7DBED000uLL && v13 < v18 )
        {
          v22 = KeGetPcr()->NtTib.StackBase;
          StackBase = v22 ? (_QWORD *)v22[10] : 0LL;
          v23 = StackBase[29];
          if ( v23 )
            *(_QWORD *)(v23 + 8 * ((v13 >> 3) & 0x1FF)) = 0;
        }
        *(_QWORD *)v13 = 0;
        LOBYTE(StackBase) = -1;
        SkeFlushEntireTb(StackBase, a3);
      }
      else if ( (v14 & 1) != 0 )
      {
        if ( (SkmiFlags & 1) != 0 )
          v11 = (unsigned __int64 *)(8 * ((v14 >> 12) & 0xFFFFFFFFFFLL) - 0x180000000000LL);
        continue;
      }
      if ( v11 )
        *v11 = (*v11 + 1) ^ (*v11 ^ (*v11 + 1)) & 0xFFFFF00000000000uLL;
      if ( a2 )
      {
        v6 = v6 & 0xFFF0000000000FFFuLL
           | ((*(_QWORD *)(a2 + 8LL * (unsigned int)--*(_DWORD *)(a2 + 32) + 8) & 0xFFFFFFFFFFLL) << 12);
        v37 = v6;
        SkmiZeroSinglePage((v6 >> 12) & 0xFFFFFFFFFFLL);
      }
      else
      {
        if ( !(unsigned int)SkmiAllocateZeroedPage(v38, &v37) )
        {
          SkmiReleasePte(v13, a3, 0);
          return 0;
        }
        v6 = v37;
      }
      v24 = SkmiGetPteTrace(0, v13, 0, v6, *(_QWORD *)v13);
      v25 = v24;
      if ( v24 )
      {
        v26 = (PVOID *)(v24 + 32);
        memset_0((void *)(v24 + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v27 = KeGetPcr()->NtTib.StackBase;
          if ( v27 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v27, 8u, v26, &BackTraceHash) )
            {
              *(_QWORD *)(v25 + 40) = retaddr;
              *v26 = (PVOID)SkmiGetInstructionPointer(v29, v28);
            }
          }
        }
      }
      v30 = v6;
      if ( (unsigned __int64)v13 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v13 < 0xFFFFF6FB7DBED800uLL )
      {
        v31 = KeGetPcr()->NtTib.StackBase;
        if ( v31 )
          v32 = v31[10];
        else
          v32 = 0;
        v33 = *(_QWORD *)(v32 + 232);
        if ( v33 )
        {
          v34 = SkiKvaShadowMode;
          *(_QWORD *)(v33 + 8 * ((v13 >> 3) & 0x1FF)) = v6;
          if ( v34 != 2 && (v6 & 1) != 0 )
            v30 = v6 | 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)v13 = v30;
      if ( (SkmiFlags & 1) != 0 )
        v11 = (unsigned __int64 *)(8 * ((v6 >> 12) & 0xFFFFFFFFFFLL) - 0x180000000000LL);
    }
  }
  for ( j = 0; j < 3; ++j )
  {
    if ( (**((_QWORD **)&v39 + j) & 1) == 0 )
      break;
  }
  v8 = *(_DWORD *)(a2 + 32);
  v9 = 3 - j;
  while ( 1 )
  {
    if ( v8 >= v9 )
      goto LABEL_13;
    if ( !(unsigned int)SkmiTryAllocatePhysicalPage(*(_QWORD *)a2, 0, 1, a2 + 8 * (v8 + 1LL)) )
      break;
    *(_DWORD *)(a2 + 32) = ++v8;
  }
  *(_DWORD *)(a2 + 36) = 1;
  return 0;
}

```

## disassembly

```asm
0x14007fd10  mov     [rsp-38h+arg_18], rbx
0x14007fd15  push    rbp
0x14007fd16  push    rsi
0x14007fd17  push    rdi
0x14007fd18  push    r12
0x14007fd1a  push    r13
0x14007fd1c  push    r14
0x14007fd1e  push    r15
0x14007fd20  mov     rbp, rsp
0x14007fd23  sub     rsp, 70h
0x14007fd27  xorps   xmm0, xmm0
0x14007fd2a  mov     r12, r8
0x14007fd2d  movups  [rbp+var_28], xmm0
0x14007fd31  mov     r14, rdx
0x14007fd34  mov     r8, 0FFFFF68000000000h
0x14007fd3e  movups  [rbp+var_18], xmm0
0x14007fd42  mov     rax, r8
0x14007fd45  mov     rdx, 4000000000h
0x14007fd4f  add     rax, rdx
0x14007fd52  mov     edx, 4
0x14007fd57  cmp     rcx, rax
0x14007fd5a  sbb     rbx, rbx
0x14007fd5d  and     rbx, rdx
0x14007fd60  add     rbx, 63h ; 'c'
0x14007fd64  mov     [rbp+var_38], rbx
0x14007fd68  xor     r15d, r15d
0x14007fd6b  mov     [rbp+rdx*8+var_30], rcx
0x14007fd70  dec     rdx
0x14007fd73  shr     rcx, 9
0x14007fd77  mov     rax, 7FFFFFFFF8h
0x14007fd81  and     rcx, rax
0x14007fd84  mov     rax, r8
0x14007fd87  add     rcx, rax
0x14007fd8a  test    rdx, rdx
0x14007fd8d  jnz     short loc_14007FD6B
0x14007fd8f  test    r14, r14
0x14007fd92  jz      short loc_14007FDED
0x14007fd94  mov     ecx, r15d
0x14007fd97  mov     eax, ecx
0x14007fd99  mov     rax, qword ptr [rbp+rax*8+var_28]
0x14007fd9e  mov     rax, [rax]
0x14007fda1  test    al, 1
0x14007fda3  jz      short loc_14007FDAC
0x14007fda5  inc     ecx
0x14007fda7  cmp     ecx, 3
0x14007fdaa  jb      short loc_14007FD97
0x14007fdac  mov     edi, [r14+20h]
0x14007fdb0  mov     esi, 3
0x14007fdb5  sub     esi, ecx
0x14007fdb7  cmp     edi, esi
0x14007fdb9  jnb     short loc_14007FDED
0x14007fdbb  mov     rcx, [r14]
0x14007fdbe  xor     edx, edx
0x14007fdc0  mov     eax, edi
0x14007fdc2  inc     rax
0x14007fdc5  lea     r8d, [rdx+1]
0x14007fdc9  lea     r9, [r14+rax*8]
0x14007fdcd  call    SkmiTryAllocatePhysicalPage
0x14007fdd2  test    eax, eax
0x14007fdd4  jz      short loc_14007FDDE
0x14007fdd6  inc     edi
0x14007fdd8  mov     [r14+20h], edi
0x14007fddc  jmp     short loc_14007FDB7
0x14007fdde  mov     dword ptr [r14+24h], 1
0x14007fde6  xor     eax, eax
0x14007fde8  jmp     loc_1400801A1
0x14007fded  mov     rsi, r15
0x14007fdf0  test    r12, r12
0x14007fdf3  jnz     short loc_14007FDFB
0x14007fdf5  mov     [rbp+var_30], r15
0x14007fdf9  jmp     short loc_14007FE04
0x14007fdfb  mov     rax, [r12+48h]
0x14007fe00  mov     [rbp+var_30], rax
0x14007fe04  mov     eax, r15d
0x14007fe07  mov     r9, 0FFFFFFFFFFh
0x14007fe11  mov     r11, 0FFFFF6FB7DBED800h
0x14007fe1b  mov     r10, 0FFFFF00000000000h
0x14007fe25  mov     rdx, 0FFFFEFFFFFFFFFFFh
0x14007fe2f  mov     r8, 0FFFFE80000000000h
0x14007fe39  mov     [rbp+var_40], eax
0x14007fe3c  cmp     eax, 3
0x14007fe3f  jnb     loc_140080178
0x14007fe45  mov     rdi, qword ptr [rbp+rax*8+var_28]
0x14007fe4a  mov     rax, [rdi]
0x14007fe4d  bt      rax, 37h ; '7'
0x14007fe52  jnb     loc_14007FFA4
0x14007fe58  mov     rax, [rdi]
0x14007fe5b  xor     r9d, r9d
0x14007fe5e  xor     r8d, r8d
0x14007fe61  mov     [rsp+70h+var_50], rax
0x14007fe66  mov     rdx, rdi
0x14007fe69  xor     ecx, ecx
0x14007fe6b  call    SkmiGetPteTrace
0x14007fe70  mov     r13, rax
0x14007fe73  test    rax, rax
0x14007fe76  jz      short loc_14007FED7
0x14007fe78  lea     r15, [rax+20h]
0x14007fe7c  xor     edx, edx; Val
0x14007fe7e  mov     rcx, r15; void *
0x14007fe81  lea     r8d, [r9+40h]; Size
0x14007fe85  call    memset_0
0x14007fe8a  test    cs:SkmiFlags, 400000h
0x14007fe94  jz      short loc_14007FECA
0x14007fe96  mov     rcx, gs:8; FramesToSkip
0x14007fe9f  test    rcx, rcx
0x14007fea2  jz      short loc_14007FECA
0x14007fea4  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14007fea8  mov     r8, r15; BackTrace
0x14007feab  mov     edx, 8; FramesToCapture
0x14007feb0  call    RtlCaptureStackBackTrace
0x14007feb5  test    ax, ax
0x14007feb8  jnz     short loc_14007FECA
0x14007feba  mov     rax, [rbp+38h]
0x14007febe  mov     [r13+28h], rax
0x14007fec2  call    SkmiGetInstructionPointer
0x14007fec7  mov     [r15], rax
0x14007feca  mov     r11, 0FFFFF6FB7DBED800h
0x14007fed4  xor     r15d, r15d
0x14007fed7  mov     rax, 0FFFFF6FB7DBED000h
0x14007fee1  mov     rax, rax
0x14007fee4  cmp     rdi, rax
0x14007fee7  jb      short loc_14007FF24
0x14007fee9  mov     rax, r11
0x14007feec  cmp     rdi, rax
0x14007feef  jnb     short loc_14007FF24
0x14007fef1  mov     rax, gs:8
0x14007fefa  test    rax, rax
0x14007fefd  jz      short loc_14007FF05
0x14007feff  mov     rcx, [rax+50h]
0x14007ff03  jmp     short loc_14007FF08
0x14007ff05  mov     rcx, r15
0x14007ff08  mov     rdx, [rcx+0E8h]
0x14007ff0f  test    rdx, rdx
0x14007ff12  jz      short loc_14007FF24
0x14007ff14  mov     rax, rdi
0x14007ff17  sar     rax, 3
0x14007ff1b  and     eax, 1FFh
0x14007ff20  mov     [rdx+rax*8], r15
0x14007ff24  mov     rdx, r12
0x14007ff27  mov     [rdi], r15
0x14007ff2a  mov     cl, 0FFh
0x14007ff2c  call    SkeFlushEntireTb
0x14007ff31  mov     r9, 0FFFFFFFFFFh
0x14007ff3b  mov     r10, 0FFFFF00000000000h
0x14007ff45  test    rsi, rsi
0x14007ff48  jz      short loc_14007FF60
0x14007ff4a  mov     rax, [rsi]
0x14007ff4d  lea     rcx, [rax+1]
0x14007ff51  mov     rdx, rcx
0x14007ff54  xor     rdx, rax
0x14007ff57  and     rdx, r10
0x14007ff5a  xor     rdx, rcx
0x14007ff5d  mov     [rsi], rdx
0x14007ff60  test    r14, r14
0x14007ff63  jz      short loc_14007FFE0
0x14007ff65  dec     dword ptr [r14+20h]
0x14007ff69  mov     rdx, 0FFF0000000000FFFh
0x14007ff73  mov     eax, [r14+20h]
0x14007ff77  mov     rcx, [r14+rax*8+8]
0x14007ff7c  mov     rax, rbx
0x14007ff7f  and     rcx, r9
0x14007ff82  and     rax, rdx
0x14007ff85  shl     rcx, 0Ch
0x14007ff89  mov     rbx, rcx
0x14007ff8c  or      rbx, rax
0x14007ff8f  mov     rcx, rbx
0x14007ff92  mov     [rbp+var_38], rbx
0x14007ff96  shr     rcx, 0Ch
0x14007ff9a  and     rcx, r9
0x14007ff9d  call    SkmiZeroSinglePage
0x14007ffa2  jmp     short loc_14007FFF9
0x14007ffa4  test    al, 1
0x14007ffa6  jz      short loc_14007FF45
0x14007ffa8  mov     ecx, cs:SkmiFlags
0x14007ffae  test    cl, 1
0x14007ffb1  jz      loc_140080154
0x14007ffb7  shr     rax, 0Ch
0x14007ffbb  and     rax, r9
0x14007ffbe  mov     rdx, rdx
0x14007ffc1  mov     rcx, r8
0x14007ffc4  sub     rdx, rcx
0x14007ffc7  sar     rdx, 3
0x14007ffcb  cmp     rax, rdx
0x14007ffce  ja      loc_14008015E
0x14007ffd4  mov     rcx, r8
0x14007ffd7  lea     rsi, [rcx+rax*8]
0x14007ffdb  jmp     loc_14008014A
0x14007ffe0  mov     rcx, [rbp+var_30]
0x14007ffe4  lea     rdx, [rbp+var_38]
0x14007ffe8  call    SkmiAllocateZeroedPage
0x14007ffed  test    eax, eax
0x14007ffef  jz      loc_140080165
0x14007fff5  mov     rbx, [rbp+var_38]
0x14007fff9  mov     rax, [rdi]
0x14007fffc  mov     r9, rbx
0x14007ffff  xor     r8d, r8d
0x140080002  mov     [rsp+70h+var_50], rax
0x140080007  mov     rdx, rdi
0x14008000a  xor     ecx, ecx
0x14008000c  call    SkmiGetPteTrace
0x140080011  mov     r13, rax
0x140080014  test    rax, rax
0x140080017  jz      short loc_14008006E
0x140080019  xor     edx, edx; Val
0x14008001b  lea     r15, [rax+20h]
0x14008001f  mov     rcx, r15; void *
0x140080022  lea     r8d, [rdx+40h]; Size
0x140080026  call    memset_0
0x14008002b  test    cs:SkmiFlags, 400000h
0x140080035  jz      short loc_14008006B
0x140080037  mov     rcx, gs:8; FramesToSkip
0x140080040  test    rcx, rcx
0x140080043  jz      short loc_14008006B
0x140080045  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x140080049  mov     r8, r15; BackTrace
0x14008004c  mov     edx, 8; FramesToCapture
0x140080051  call    RtlCaptureStackBackTrace
0x140080056  test    ax, ax
0x140080059  jnz     short loc_14008006B
0x14008005b  mov     rax, [rbp+38h]
0x14008005f  mov     [r13+28h], rax
0x140080063  call    SkmiGetInstructionPointer
0x140080068  mov     [r15], rax
0x14008006b  xor     r15d, r15d
0x14008006e  mov     rax, rbx
0x140080071  mov     rcx, 0FFFFF6FB7DBED000h
0x14008007b  mov     rcx, rcx
0x14008007e  mov     r11, 0FFFFF6FB7DBED800h
0x140080088  cmp     rdi, rcx
0x14008008b  jb      short loc_1400800E6
0x14008008d  mov     rcx, r11
0x140080090  cmp     rdi, rcx
0x140080093  jnb     short loc_1400800E6
0x140080095  mov     rcx, gs:8
0x14008009e  test    rcx, rcx
0x1400800a1  jz      short loc_1400800A9
0x1400800a3  mov     rdx, [rcx+50h]
0x1400800a7  jmp     short loc_1400800AC
0x1400800a9  mov     rdx, r15
0x1400800ac  mov     r8, [rdx+0E8h]
0x1400800b3  test    r8, r8
0x1400800b6  jz      short loc_1400800E6
0x1400800b8  mov     edx, cs:SkiKvaShadowMode
0x1400800be  mov     rcx, rdi
0x1400800c1  sar     rcx, 3
0x1400800c5  and     ecx, 1FFh
0x1400800cb  mov     [r8+rcx*8], rbx
0x1400800cf  cmp     edx, 2
0x1400800d2  jz      short loc_1400800E6
0x1400800d4  test    bl, 1
0x1400800d7  jz      short loc_1400800E6
0x1400800d9  mov     rcx, 8000000000000000h
0x1400800e3  or      rax, rcx
0x1400800e6  mov     [rdi], rax
0x1400800e9  mov     r9, 0FFFFFFFFFFh
0x1400800f3  mov     eax, cs:SkmiFlags
0x1400800f9  test    al, 1
0x1400800fb  jz      short loc_140080136
0x1400800fd  mov     rdx, rbx
0x140080100  mov     rax, 0FFFFEFFFFFFFFFFFh
0x14008010a  shr     rdx, 0Ch
0x14008010e  and     rdx, r9
0x140080111  mov     rcx, rax
0x140080114  mov     r8, 0FFFFE80000000000h
0x14008011e  mov     rax, r8
0x140080121  sub     rcx, rax
0x140080124  sar     rcx, 3
0x140080128  cmp     rdx, rcx
0x14008012b  ja      short loc_14008015E
0x14008012d  mov     rax, r8
0x140080130  lea     rsi, [rax+rdx*8]
0x140080134  jmp     short loc_140080140
0x140080136  mov     r8, 0FFFFE80000000000h
0x140080140  mov     r10, 0FFFFF00000000000h
0x14008014a  mov     rdx, 0FFFFEFFFFFFFFFFFh
0x140080154  mov     eax, [rbp+var_40]
0x140080157  inc     eax
0x140080159  jmp     loc_14007FE39
0x14008015e  mov     ecx, 3Fh ; '?'
0x140080163  int     29h; Win8: RtlFailFast(ecx)
0x140080165  xor     r8d, r8d
0x140080168  mov     rdx, r12
0x14008016b  mov     rcx, rdi
0x14008016e  call    SkmiReleasePte
0x140080173  jmp     loc_14007FDE6
0x140080178  mov     rax, qword ptr [rbp+var_18+8]
0x14008017c  cmp     [rax], r15
0x14008017f  jnz     short loc_14008019C
0x140080181  test    rsi, rsi
0x140080184  jz      short loc_14008019C
0x140080186  mov     rcx, [rsi]
0x140080189  lea     rdx, [rcx+1]
0x14008018d  mov     r8, rdx
0x140080190  xor     r8, rcx
0x140080193  and     r8, r10
0x140080196  xor     r8, rdx
0x140080199  mov     [rsi], r8
0x14008019c  mov     eax, 1
0x1400801a1  mov     rbx, [rsp+70h+arg_18]
0x1400801a9  add     rsp, 70h
  ... truncated ...
```
