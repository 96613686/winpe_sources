# SkmmDebugReadWriteMemory

- ea: `0x1400671bc`
- end: `0x1400676bf`
- name: `SkmmDebugReadWriteMemory`
- size: `1283`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int64, char, int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x140014dd0`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140003780`
- `0x140009940`
- `0x14000c8d0`
- `0x14000e460`
- `0x140012750`
- `0x14001d414`
- `0x14001e4d8`
- `0x14002b534`
- `0x140030f10`
- `0x140050634`
- `0x1400671bc`
- `0x1400801fc`
- `0x140081290`
- `0x1400855c0`
- `0x1400d4e8c`
- `0x1400f9780`
- `0x1400f9a80`
- `0x1400fc554`

## pseudocode

```c
__int64 __fastcall SkmmDebugReadWriteMemory(unsigned int *a1, unsigned __int64 a2, char a3, int a4, int a5, _QWORD *a6)
{
  unsigned __int64 v7; // r12
  unsigned int v9; // eax
  char v11; // r15
  __int64 v12; // r13
  _DWORD *v13; // rsi
  __int64 v14; // rdx
  int v15; // edi
  char *v16; // r9
  unsigned __int64 v17; // r10
  unsigned int v18; // eax
  unsigned int v19; // edx
  __int64 *ValidPteAddress; // rax
  __int64 v21; // rdi
  __int16 v22; // r13
  unsigned __int64 v23; // rdi
  __int64 HyperspacePte; // r12
  __int64 PteTrace; // rax
  PVOID *v26; // r13
  PVOID StackBase; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rdi
  __int64 v32; // rax
  int v33; // r9d
  PVOID *v34; // r13
  PVOID v35; // rcx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // [rsp+30h] [rbp-88h] BYREF
  __int64 v41; // [rsp+38h] [rbp-80h]
  unsigned int Size; // [rsp+40h] [rbp-78h]
  int Size_4; // [rsp+44h] [rbp-74h]
  ULONG BackTraceHash; // [rsp+48h] [rbp-70h] BYREF
  unsigned int *v45; // [rsp+50h] [rbp-68h]
  void *Src; // [rsp+58h] [rbp-60h]
  _DWORD *v47; // [rsp+60h] [rbp-58h]
  __int64 v48; // [rsp+68h] [rbp-50h] BYREF
  __int64 v49; // [rsp+70h] [rbp-48h]
  unsigned __int64 i; // [rsp+78h] [rbp-40h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+0h]
  unsigned __int64 v52; // [rsp+C8h] [rbp+10h]
  char v53; // [rsp+D0h] [rbp+18h]

  v53 = a3;
  v52 = a2;
  v7 = a2;
  *a6 = 0;
  v48 = 0;
  v9 = *a1;
  if ( (*a1 & 0x10) == 0 )
    return 3221225506LL;
  v11 = -1;
  v12 = 0;
  v45 = 0;
  v13 = 0;
  v47 = 0;
  if ( !a3 && (v9 & 0x200) != 0 )
  {
    if ( (a1[83] & 1) != 0 )
    {
      v45 = a1;
      v47 = 0;
    }
    else
    {
      v13 = a1 + 134;
      v47 = a1 + 134;
      SkmiLockVad(a1 + 134);
      v45 = 0;
      a3 = v53;
    }
  }
  v15 = SkmmMapDataTransfer(a4, a5, (unsigned int)(a3 != 0) + 1, (unsigned int)&v48, 0);
  if ( v15 >= 0 )
  {
    v41 = SkiAttachProcess(a1);
    v16 = *(char **)(v48 + 24);
    v14 = *(unsigned int *)(v48 + 40);
    v17 = v7 >> 12;
    for ( i = v7 >> 12; ; v17 = i )
    {
      Size_4 = v14;
      Src = v16;
      if ( !(_DWORD)v14 )
        break;
      v18 = v14;
      if ( 4096 - (v7 & 0xFFF) <= (unsigned int)v14 )
        v18 = 4096 - (v7 & 0xFFF);
      Size = v18;
      if ( v45 )
      {
        v19 = v45[142];
        if ( v17 < (v45[140] | ((unsigned __int64)(v19 & 0xFFF) << 32))
          || v17 > (v45[141] | ((unsigned __int64)(v19 & 0xFFF000) << 20)) )
        {
          v15 = -2147483635;
          v12 = v41;
          goto LABEL_58;
        }
        while ( 1 )
        {
          v11 = SkAcquireSpinLockExclusive(a1 + 2);
          ValidPteAddress = (__int64 *)SkmiGetValidPteAddress(v7, 0);
          if ( !ValidPteAddress || (v21 = *ValidPteAddress, (v40 = v21) == 0) )
          {
LABEL_21:
            v15 = -2147483635;
            goto LABEL_55;
          }
          if ( (v21 & 1) != 0 )
            goto LABEL_23;
          if ( (v21 & 0x802) == 0x802 )
            break;
          LOBYTE(v14) = v11;
          SkReleaseSpinLockExclusive(a1 + 2, v14);
          v11 = -1;
          if ( (int)SkmmAccessFault(0x10000, v7, 0) < 0 )
            goto LABEL_21;
        }
        SKMI_UNSWIZZLE_INVALID_PTE(&v40);
        v21 = v40;
LABEL_23:
        v22 = v7;
        v40 = (unsigned int)v7;
        v23 = v21 & 0xFFFFFFFFFF000LL | 0x8000000000000063uLL;
        HyperspacePte = SkmiGetHyperspacePte();
        PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, v23, *(_QWORD *)HyperspacePte);
        v49 = PteTrace;
        if ( PteTrace )
        {
          v26 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            StackBase = KeGetPcr()->NtTib.StackBase;
            if ( StackBase )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v26, &BackTraceHash) )
              {
                *(_QWORD *)(v49 + 40) = retaddr;
                *v26 = (PVOID)SkmiGetInstructionPointer();
              }
            }
          }
          v22 = v40;
        }
        if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
          && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
        {
          v28 = KeGetPcr()->NtTib.StackBase;
          v29 = v28 ? v28[10] : 0LL;
          v30 = *(_QWORD *)(v29 + 232);
          if ( v30 )
            *(_QWORD *)(v30 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v23;
        }
        *(_QWORD *)HyperspacePte = v23;
        v31 = Size;
        memmove((void *)((v22 & 0xFFF) + (HyperspacePte << 25 >> 16)), Src, Size);
        v32 = SkmiGetPteTrace(0, HyperspacePte, 0, 0, *(_QWORD *)HyperspacePte);
        v49 = v32;
        if ( v32 )
        {
          v34 = (PVOID *)(v32 + 32);
          memset_0((void *)(v32 + 32), 0, (unsigned int)(v33 + 64));
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v35 = KeGetPcr()->NtTib.StackBase;
            if ( v35 )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)v35, 8u, v34, &BackTraceHash) )
              {
                *(_QWORD *)(v49 + 40) = retaddr;
                *v34 = (PVOID)SkmiGetInstructionPointer();
              }
            }
          }
        }
        if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
          && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
        {
          v36 = KeGetPcr()->NtTib.StackBase;
          v37 = v36 ? v36[10] : 0LL;
          v38 = *(_QWORD *)(v37 + 232);
          if ( v38 )
            *(_QWORD *)(v38 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = 0;
        }
        *(_QWORD *)HyperspacePte = 0;
        SkmiReleaseHyperspacePte(HyperspacePte);
        LOBYTE(v39) = v11;
        SkReleaseSpinLockExclusive(a1 + 2, v39);
        v7 = v52;
      }
      else
      {
        v31 = v18;
        if ( v53 )
          RtlCopyFromUser(v16, (void *)v7, v18);
        else
          RtlCopyToUser((void *)v7, v16, v18);
      }
      *a6 += v31;
      v7 += v31;
      v52 = v7;
      v16 = (char *)Src + v31;
      v14 = Size_4 - Size;
    }
    v15 = 0;
    v11 = -1;
LABEL_55:
    v12 = v41;
  }
  if ( v11 != -1 )
  {
    LOBYTE(v14) = v11;
    SkReleaseSpinLockExclusive(a1 + 2, v14);
  }
LABEL_58:
  if ( v12 )
    SkiAttachProcess(v12);
  if ( v48 )
    SkmmUnmapDataTransfer(v48);
  if ( v13 )
    SkmiUnlockVad(v13);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400671bc  mov     r11, rsp
0x1400671bf  mov     [r11+18h], r8b
0x1400671c3  mov     [r11+10h], rdx
0x1400671c7  mov     [r11+8], rcx
0x1400671cb  push    rbx
0x1400671cc  push    rsi
0x1400671cd  push    rdi
0x1400671ce  push    r12
0x1400671d0  push    r13
0x1400671d2  push    r14
0x1400671d4  push    r15
0x1400671d6  sub     rsp, 80h
0x1400671dd  mov     rdi, r9
0x1400671e0  mov     r12, rdx
0x1400671e3  mov     r14, rcx
0x1400671e6  xor     ebx, ebx
0x1400671e8  mov     rax, [rsp+0B8h+arg_28]
0x1400671f0  mov     [rax], rbx
0x1400671f3  mov     [r11-50h], rbx
0x1400671f7  mov     eax, [rcx]
0x1400671f9  test    al, 10h
0x1400671fb  jnz     short loc_140067207
0x1400671fd  mov     eax, 0C0000022h
0x140067202  jmp     loc_1400676AB
0x140067207  mov     r15b, 0FFh
0x14006720a  mov     r13, rbx
0x14006720d  mov     [rsp+0B8h+var_68], rbx
0x140067212  mov     rsi, rbx
0x140067215  mov     [rsp+0B8h+var_58], rbx
0x14006721a  test    r8b, r8b
0x14006721d  jnz     short loc_14006725C
0x14006721f  bt      eax, 9
0x140067223  jnb     short loc_14006725C
0x140067225  mov     eax, [rcx+14Ch]
0x14006722b  test    al, 1
0x14006722d  jnz     short loc_140067252
0x14006722f  lea     rsi, [rcx+218h]
0x140067236  mov     [rsp+0B8h+var_58], rsi
0x14006723b  mov     rcx, rsi
0x14006723e  call    SkmiLockVad
0x140067243  mov     [rsp+0B8h+var_68], rbx
0x140067248  mov     r8b, [rsp+0B8h+arg_10]
0x140067250  jmp     short loc_14006725C
0x140067252  mov     [rsp+0B8h+var_68], r14
0x140067257  mov     [rsp+0B8h+var_58], rbx
0x14006725c  mov     al, r8b
0x14006725f  neg     al
0x140067261  sbb     r8d, r8d
0x140067264  neg     r8d
0x140067267  inc     r8d
0x14006726a  mov     [rsp+0B8h+var_98], rbx
0x14006726f  lea     r9, [rsp+0B8h+var_50]
0x140067274  mov     rdx, [rsp+0B8h+arg_20]
0x14006727c  mov     rcx, rdi
0x14006727f  call    SkmmMapDataTransfer
0x140067284  mov     edi, eax
0x140067286  test    eax, eax
0x140067288  js      loc_14006766E
0x14006728e  mov     rcx, r14
0x140067291  call    SkiAttachProcess
0x140067296  mov     [rsp+0B8h+var_80], rax
0x14006729b  mov     rcx, [rsp+0B8h+var_50]
0x1400672a0  mov     r9, [rcx+18h]
0x1400672a4  mov     edx, [rcx+28h]
0x1400672a7  mov     r10, r12
0x1400672aa  shr     r10, 0Ch
0x1400672ae  mov     [rsp+0B8h+var_40], r10
0x1400672b3  mov     dword ptr [rsp+0B8h+Size+4], edx
0x1400672b7  mov     [rsp+0B8h+Src], r9
0x1400672bc  test    edx, edx
0x1400672be  jz      loc_140067664
0x1400672c4  mov     eax, r12d
0x1400672c7  and     eax, 0FFFh
0x1400672cc  mov     ecx, 1000h
0x1400672d1  sub     ecx, eax
0x1400672d3  mov     eax, edx
0x1400672d5  cmp     ecx, edx
0x1400672d7  cmovbe  eax, ecx
0x1400672da  mov     dword ptr [rsp+0B8h+Size], eax
0x1400672de  mov     r8, [rsp+0B8h+var_68]
0x1400672e3  test    r8, r8
0x1400672e6  jz      loc_1400675F1
0x1400672ec  mov     edx, [r8+238h]
0x1400672f3  mov     ecx, edx
0x1400672f5  and     ecx, 0FFFh
0x1400672fb  shl     rcx, 20h
0x1400672ff  mov     eax, [r8+230h]
0x140067306  or      rcx, rax
0x140067309  cmp     r10, rcx
0x14006730c  jb      loc_1400675E2
0x140067312  and     edx, 0FFF000h
0x140067318  shl     rdx, 14h
0x14006731c  mov     eax, [r8+234h]
0x140067323  or      rdx, rax
0x140067326  cmp     r10, rdx
0x140067329  ja      loc_1400675E2
0x14006732f  lea     rcx, [r14+8]
0x140067333  call    SkAcquireSpinLockExclusive
0x140067338  mov     r15b, al
0x14006733b  xor     edx, edx
0x14006733d  mov     rcx, r12
0x140067340  call    SkmiGetValidPteAddress
0x140067345  test    rax, rax
0x140067348  jz      short loc_140067390
0x14006734a  mov     rdi, [rax]
0x14006734d  mov     [rsp+0B8h+var_88], rdi
0x140067352  test    rdi, rdi
0x140067355  jz      short loc_140067390
0x140067357  test    dil, 1
0x14006735b  jnz     short loc_1400673A9
0x14006735d  mov     eax, 802h
0x140067362  and     rdi, rax
0x140067365  cmp     rdi, rax
0x140067368  jz      short loc_14006739A
0x14006736a  mov     dl, r15b
0x14006736d  lea     rcx, [r14+8]
0x140067371  call    SkReleaseSpinLockExclusive
0x140067376  mov     r15b, 0FFh
0x140067379  xor     r9d, r9d
0x14006737c  xor     r8d, r8d; char
0x14006737f  mov     rdx, r12; int
0x140067382  mov     ecx, 10000h; __int64
0x140067387  call    SkmmAccessFault
0x14006738c  test    eax, eax
0x14006738e  jns     short loc_14006732F
0x140067390  mov     edi, 8000000Dh
0x140067395  jmp     loc_140067669
0x14006739a  lea     rcx, [rsp+0B8h+var_88]
0x14006739f  call    SKMI_UNSWIZZLE_INVALID_PTE
0x1400673a4  mov     rdi, [rsp+0B8h+var_88]
0x1400673a9  mov     rax, 0FFFFFFFFFF000h
0x1400673b3  and     rdi, rax
0x1400673b6  mov     r13d, r12d
0x1400673b9  mov     [rsp+0B8h+var_88], r13
0x1400673be  mov     rax, 8000000000000063h
0x1400673c8  or      rdi, rax
0x1400673cb  call    SkmiGetHyperspacePte
0x1400673d0  mov     r12, rax
0x1400673d3  mov     rcx, [rax]
0x1400673d6  mov     [rsp+0B8h+var_98], rcx
0x1400673db  mov     r9, rdi
0x1400673de  xor     r8d, r8d
0x1400673e1  mov     rdx, rax
0x1400673e4  xor     ecx, ecx
0x1400673e6  call    SkmiGetPteTrace
0x1400673eb  mov     [rsp+0B8h+var_48], rax
0x1400673f0  test    rax, rax
0x1400673f3  jz      short loc_140067457
0x1400673f5  lea     r13, [rax+20h]
0x1400673f9  xor     edx, edx; Val
0x1400673fb  lea     r8d, [rdx+40h]; Size
0x1400673ff  mov     rcx, r13; void *
0x140067402  call    memset_0
0x140067407  test    cs:SkmiFlags, 400000h
0x140067411  jz      short loc_140067452
0x140067413  mov     rcx, gs:8; FramesToSkip
0x14006741c  test    rcx, rcx
0x14006741f  jz      short loc_140067452
0x140067421  lea     r9, [rsp+0B8h+BackTraceHash]; BackTraceHash
0x140067426  mov     r8, r13; BackTrace
0x140067429  mov     edx, 8; FramesToCapture
0x14006742e  call    RtlCaptureStackBackTrace
0x140067433  test    ax, ax
0x140067436  jnz     short loc_140067452
0x140067438  mov     rax, [rsp+0B8h]
0x140067440  mov     rcx, [rsp+0B8h+var_48]
0x140067445  mov     [rcx+28h], rax
0x140067449  call    SkmiGetInstructionPointer
0x14006744e  mov     [r13+0], rax
0x140067452  mov     r13, [rsp+0B8h+var_88]
0x140067457  mov     rax, 0FFFFF6FB7DBED000h
0x140067461  mov     rax, rax
0x140067464  cmp     r12, rax
0x140067467  jb      short loc_1400674AE
0x140067469  mov     rax, 0FFFFF6FB7DBED800h
0x140067473  mov     rax, rax
0x140067476  cmp     r12, rax
0x140067479  jnb     short loc_1400674AE
0x14006747b  mov     rax, gs:8
0x140067484  test    rax, rax
0x140067487  jz      short loc_14006748F
0x140067489  mov     rcx, [rax+50h]
0x14006748d  jmp     short loc_140067492
0x14006748f  mov     rcx, rbx
0x140067492  mov     rdx, [rcx+0E8h]
0x140067499  test    rdx, rdx
0x14006749c  jz      short loc_1400674AE
0x14006749e  mov     rax, r12
0x1400674a1  sar     rax, 3
0x1400674a5  and     eax, 1FFh
0x1400674aa  mov     [rdx+rax*8], rdi
0x1400674ae  mov     [r12], rdi
0x1400674b2  mov     edi, dword ptr [rsp+0B8h+Size]
0x1400674b6  mov     rcx, r12
0x1400674b9  shl     rcx, 19h
0x1400674bd  mov     rax, 0FFFFF68000000000h
0x1400674c7  shl     rax, 19h
0x1400674cb  sub     rcx, rax
0x1400674ce  sar     rcx, 10h
0x1400674d2  and     r13d, 0FFFh
0x1400674d9  add     rcx, r13; void *
0x1400674dc  mov     r8d, edi; Size
0x1400674df  mov     rdx, [rsp+0B8h+Src]; Src
0x1400674e4  call    memmove
0x1400674e9  mov     rax, [r12]
0x1400674ed  mov     [rsp+0B8h+var_98], rax
0x1400674f2  xor     r9d, r9d
0x1400674f5  xor     r8d, r8d
0x1400674f8  mov     rdx, r12
0x1400674fb  xor     ecx, ecx
0x1400674fd  call    SkmiGetPteTrace
0x140067502  mov     [rsp+0B8h+var_48], rax
0x140067507  test    rax, rax
0x14006750a  jz      short loc_140067569
0x14006750c  lea     r13, [rax+20h]
0x140067510  xor     edx, edx; Val
0x140067512  lea     r8d, [r9+40h]; Size
0x140067516  mov     rcx, r13; void *
0x140067519  call    memset_0
0x14006751e  test    cs:SkmiFlags, 400000h
0x140067528  jz      short loc_140067569
0x14006752a  mov     rcx, gs:8; FramesToSkip
0x140067533  test    rcx, rcx
0x140067536  jz      short loc_140067569
0x140067538  lea     r9, [rsp+0B8h+BackTraceHash]; BackTraceHash
0x14006753d  mov     r8, r13; BackTrace
0x140067540  mov     edx, 8; FramesToCapture
0x140067545  call    RtlCaptureStackBackTrace
0x14006754a  test    ax, ax
0x14006754d  jnz     short loc_140067569
0x14006754f  mov     rax, [rsp+0B8h]
0x140067557  mov     rcx, [rsp+0B8h+var_48]
0x14006755c  mov     [rcx+28h], rax
0x140067560  call    SkmiGetInstructionPointer
0x140067565  mov     [r13+0], rax
0x140067569  mov     rax, 0FFFFF6FB7DBED000h
0x140067573  mov     rax, rax
0x140067576  cmp     r12, rax
0x140067579  jb      short loc_1400675C0
0x14006757b  mov     rax, 0FFFFF6FB7DBED800h
0x140067585  mov     rax, rax
0x140067588  cmp     r12, rax
0x14006758b  jnb     short loc_1400675C0
0x14006758d  mov     rax, gs:8
0x140067596  test    rax, rax
0x140067599  jz      short loc_1400675A1
0x14006759b  mov     rcx, [rax+50h]
0x14006759f  jmp     short loc_1400675A4
0x1400675a1  mov     rcx, rbx
0x1400675a4  mov     rdx, [rcx+0E8h]
0x1400675ab  test    rdx, rdx
0x1400675ae  jz      short loc_1400675C0
0x1400675b0  mov     rax, r12
0x1400675b3  sar     rax, 3
0x1400675b7  and     eax, 1FFh
0x1400675bc  mov     [rdx+rax*8], rbx
0x1400675c0  mov     [r12], rbx
0x1400675c4  mov     rcx, r12
0x1400675c7  call    SkmiReleaseHyperspacePte
0x1400675cc  mov     dl, r15b
0x1400675cf  lea     rcx, [r14+8]
0x1400675d3  call    SkReleaseSpinLockExclusive
0x1400675d8  mov     r12, [rsp+0B8h+arg_8]
0x1400675e0  jmp     short loc_140067618
0x1400675e2  mov     edi, 8000000Dh
0x1400675e7  mov     r13, [rsp+0B8h+var_80]
0x1400675ec  jmp     loc_140067680
0x1400675f1  mov     edi, eax
0x1400675f3  mov     r8d, edi; Size
0x1400675f6  cmp     [rsp+0B8h+arg_10], bl
0x1400675fd  jz      short loc_14006760C
0x1400675ff  mov     rdx, r12; Src
0x140067602  mov     rcx, r9; void *
0x140067605  call    RtlCopyFromUser
0x14006760a  jmp     short loc_140067618
0x14006760c  mov     rdx, r9; Src
0x14006760f  mov     rcx, r12; void *
0x140067612  call    RtlCopyToUser
0x140067617  nop
0x140067618  mov     rax, [rsp+0B8h+arg_28]
0x140067620  add     [rax], rdi
0x140067623  add     r12, rdi
0x140067626  mov     [rsp+0B8h+arg_8], r12
0x14006762e  mov     r9, [rsp+0B8h+Src]
0x140067633  add     r9, rdi
0x140067636  mov     edx, dword ptr [rsp+0B8h+Size+4]
0x14006763a  sub     edx, dword ptr [rsp+0B8h+Size]
0x14006763e  mov     r10, [rsp+0B8h+var_40]
0x140067643  jmp     loc_1400672B3
0x140067648  mov     edi, 8000000Dh
0x14006764d  mov     r15b, 0FFh
0x140067650  mov     r14, [rsp+0B8h+arg_0]
0x140067658  mov     rsi, [rsp+0B8h+var_58]
0x14006765d  mov     r13, [rsp+0B8h+var_80]
0x140067662  jmp     short loc_14006766E
0x140067664  mov     edi, ebx
0x140067666  mov     r15b, 0FFh
0x140067669  mov     r13, [rsp+0B8h+var_80]
0x14006766e  cmp     r15b, 0FFh
0x140067672  jz      short loc_140067680
  ... truncated ...
```
