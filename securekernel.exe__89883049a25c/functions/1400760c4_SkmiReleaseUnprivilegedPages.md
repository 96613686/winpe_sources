# SkmiReleaseUnprivilegedPages

- ea: `0x1400760c4`
- end: `0x1400764d4`
- name: `SkmiReleaseUnprivilegedPages`
- size: `1040`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001120`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140003780`
- `0x14000b980`
- `0x14000d020`
- `0x14002b534`
- `0x1400760c4`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiReleaseUnprivilegedPages(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rbp
  int v4; // ecx
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r13
  __int64 v8; // r9
  unsigned __int16 *v9; // r14
  char *v10; // rdx
  unsigned __int64 v11; // r11
  unsigned __int16 *v12; // rbx
  __int64 v13; // r10
  __int64 v14; // r8
  char v15; // al
  unsigned __int64 v16; // rdx
  __int64 *v17; // rcx
  unsigned __int64 v18; // r8
  BOOL v19; // r12d
  __int64 v20; // rbx
  unsigned __int64 v21; // rsi
  ULONG_PTR v22; // rsi
  unsigned int v23; // eax
  unsigned __int64 v24; // r15
  __int64 v25; // r15
  __int64 PteTrace; // rax
  __int64 v27; // r13
  PVOID *v28; // rsi
  PVOID StackBase; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r15
  PVOID *v33; // rsi
  PVOID v34; // rcx
  __int64 v35; // rcx
  unsigned __int64 v36; // [rsp+30h] [rbp-58h]
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]
  char v38; // [rsp+90h] [rbp+8h]
  ULONG BackTraceHash; // [rsp+98h] [rbp+10h] BYREF
  unsigned __int64 v40; // [rsp+A0h] [rbp+18h]
  __int64 *v41; // [rsp+A8h] [rbp+20h]

  v3 = a3;
  if ( !a3 )
    v3 = *(unsigned int *)(a1 + 72);
  if ( v3 + ((unsigned int)(a2 - *(_DWORD *)(a1 + 24)) >> 12) > *(_QWORD *)(a1 + 64) )
  {
    v4 = 432;
    goto LABEL_5;
  }
  v6 = ((a2 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL;
  v7 = ((a2 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000008LL + 8 * v3;
  v36 = v7;
  if ( (*(_BYTE *)(a1 + 78) & 8) != 0 )
  {
    v8 = ((a2 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL;
    v9 = (unsigned __int16 *)(((a2 >> 20) & 0xFFFFFFE) + qword_140156AE0);
    v10 = (char *)(((v6 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL);
    v11 = v3;
    v12 = v9;
    if ( v6 <= v7 )
    {
      while ( 1 )
      {
        v13 = (unsigned int)v11;
        v14 = (v8 >> 3) & 0x1FF;
        if ( (unsigned int)(512 - v14) <= v11 )
          v13 = (unsigned int)(512 - v14);
        if ( *v10 < 0 && (*(_QWORD *)v10 & 0x900LL) == 0x900 && (int)v13 + (int)v14 < (unsigned int)*v12 )
          break;
        v8 += 8 * v13;
        v11 -= (unsigned int)v13;
        v10 += 8;
        ++v12;
        if ( v8 > v7 )
          goto LABEL_17;
      }
      v4 = 435;
LABEL_5:
      SKMI_SECURITY(v4);
      return 3221225496LL;
    }
  }
  else
  {
    v9 = 0;
  }
LABEL_17:
  v15 = SkAcquireSpinLockExclusive(&SkmiNteLock);
  v38 = v15;
  if ( v6 > v7 )
    goto LABEL_50;
  v17 = 0;
  LODWORD(v18) = 0;
  v41 = 0;
  v40 = 0;
  v19 = v9 != 0;
  LODWORD(v20) = 0;
  do
  {
    if ( v19 )
    {
      v16 = ((v6 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
      v19 = 0;
      v17 = (__int64 *)(v16 & -(__int64)(*(char *)v16 < 0));
      v41 = v17;
    }
    if ( v17 )
    {
      v21 = *v17;
      v20 = ((__int64)v6 >> 3) & 0x1FF;
      v18 = (unsigned int)(512 - v20);
      v40 = v18;
      if ( v18 > v3 )
      {
        LODWORD(v18) = v3;
        v40 = (unsigned int)v3;
      }
    }
    else
    {
      v21 = *(_QWORD *)v6;
    }
    if ( (v21 & 0x900) == 0x900 && v21 < 0x800000000000000LL )
    {
      v22 = (v21 >> 12) & 0xFFFFFFFFFFLL;
      if ( v17 )
      {
        v23 = *v9;
        if ( (unsigned int)v20 < v23 )
        {
          v24 = *v9;
          *v9 = v20;
          if ( (unsigned int)v20 < (unsigned __int64)v23 )
          {
            do
            {
              SkmiDecrementPageReferenceCount(v22 + (unsigned int)v20);
              LODWORD(v20) = v20 + 1;
            }
            while ( (unsigned int)v20 < v24 );
            v17 = v41;
          }
        }
        if ( !*v9 )
        {
          v25 = qword_14016A250 & 0xFFFFFFFFFF000LL | 0xAA1;
          PteTrace = SkmiGetPteTrace(0, (_DWORD)v17, 0, qword_14016A250 & 0xFFFFF000 | 0xAA1, *v17);
          v27 = PteTrace;
          if ( PteTrace )
          {
            v28 = (PVOID *)(PteTrace + 32);
            memset_0((void *)(PteTrace + 32), 0, 0x40u);
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              StackBase = KeGetPcr()->NtTib.StackBase;
              if ( StackBase )
              {
                if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v28, &BackTraceHash) )
                {
                  *(_QWORD *)(v27 + 40) = retaddr;
                  *v28 = (PVOID)SkmiGetInstructionPointer(v30, v16);
                }
              }
            }
          }
          v17 = v41;
          v7 = v36;
          *v41 = v25;
        }
        LODWORD(v18) = v40;
LABEL_52:
        v3 -= (unsigned int)v18;
        v6 += 8LL * (unsigned int)v18;
LABEL_53:
        v19 = 1;
        ++v9;
        continue;
      }
      SkmiDecrementPageReferenceCount(v22);
      v31 = SkmiGetPteTrace(0, v6, 0, 2593, *(_QWORD *)v6);
      v32 = v31;
      if ( v31 )
      {
        v33 = (PVOID *)(v31 + 32);
        memset_0((void *)(v31 + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v34 = KeGetPcr()->NtTib.StackBase;
          if ( v34 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v34, 8u, v33, &BackTraceHash) )
            {
              *(_QWORD *)(v32 + 40) = retaddr;
              *v33 = (PVOID)SkmiGetInstructionPointer(v35, v16);
            }
          }
        }
      }
      v17 = v41;
      *(_QWORD *)v6 = 2593;
    }
    else if ( v17 )
    {
      goto LABEL_52;
    }
    LODWORD(v18) = v40;
    v6 += 8LL;
    if ( v9 && (v6 & 0xFF8) == 0 )
      goto LABEL_53;
  }
  while ( v6 <= v7 );
  v15 = v38;
LABEL_50:
  LOBYTE(v16) = v15;
  SkReleaseSpinLockExclusive(&SkmiNteLock, v16);
  return 0;
}

```

## disassembly

```asm
0x1400760c4  push    rbx
0x1400760c6  push    rbp
0x1400760c7  push    rsi
0x1400760c8  push    rdi
0x1400760c9  push    r12
0x1400760cb  push    r13
0x1400760cd  push    r14
0x1400760cf  push    r15
0x1400760d1  sub     rsp, 48h
0x1400760d5  mov     eax, edx
0x1400760d7  xor     esi, esi
0x1400760d9  sub     eax, [rcx+18h]
0x1400760dc  mov     rbp, r8
0x1400760df  shr     eax, 0Ch
0x1400760e2  test    r8, r8
0x1400760e5  jnz     short loc_1400760EA
0x1400760e7  mov     ebp, [rcx+48h]
0x1400760ea  add     rax, rbp
0x1400760ed  cmp     rax, [rcx+40h]
0x1400760f1  jbe     short loc_140076107
0x1400760f3  mov     ecx, 1B0h
0x1400760f8  call    SKMI_SECURITY
0x1400760fd  mov     eax, 0C0000018h
0x140076102  jmp     loc_1400764A5
0x140076107  mov     rdi, rdx
0x14007610a  mov     r10, 7FFFFFFFF8h
0x140076114  shr     rdi, 9
0x140076118  and     rdi, r10
0x14007611b  mov     r8, 0FFFFF60000000000h
0x140076125  mov     al, [rcx+4Eh]
0x140076128  add     rdi, r8
0x14007612b  mov     rcx, 0FFFFF68000000000h
0x140076135  mov     r15d, 900h
0x14007613b  lea     r13, [rdi-8]
0x14007613f  lea     r13, [r13+rbp*8+0]
0x140076144  mov     [rsp+88h+var_58], r13
0x140076149  test    al, 8
0x14007614b  jz      loc_1400761E4
0x140076151  mov     r14, cs:qword_140156AE0
0x140076158  mov     r9, rdi
0x14007615b  shr     rdx, 14h
0x14007615f  and     edx, 0FFFFFFEh
0x140076165  add     r14, rdx
0x140076168  mov     rdx, rdi
0x14007616b  shr     rdx, 9
0x14007616f  and     rdx, r10
0x140076172  mov     rax, rcx
0x140076175  add     rdx, rax
0x140076178  mov     r11, rbp
0x14007617b  mov     rbx, r14
0x14007617e  cmp     rdi, r13
0x140076181  ja      short loc_1400761E7
0x140076183  mov     r8, r9
0x140076186  mov     eax, 200h
0x14007618b  sar     r8, 3
0x14007618f  mov     r10d, r11d
0x140076192  and     r8d, 1FFh
0x140076199  sub     eax, r8d
0x14007619c  mov     ecx, eax
0x14007619e  cmp     rcx, r11
0x1400761a1  cmovbe  r10d, eax
0x1400761a5  mov     al, [rdx]
0x1400761a7  test    al, al
0x1400761a9  jns     short loc_1400761C1
0x1400761ab  mov     rax, [rdx]
0x1400761ae  and     rax, r15
0x1400761b1  cmp     rax, r15
0x1400761b4  jnz     short loc_1400761C1
0x1400761b6  movzx   eax, word ptr [rbx]
0x1400761b9  lea     ecx, [r10+r8]
0x1400761bd  cmp     ecx, eax
0x1400761bf  jb      short loc_1400761DA
0x1400761c1  mov     eax, r10d
0x1400761c4  lea     r9, [r9+r10*8]
0x1400761c8  sub     r11, rax
0x1400761cb  add     rdx, 8
0x1400761cf  add     rbx, 2
0x1400761d3  cmp     r9, r13
0x1400761d6  jbe     short loc_140076183
0x1400761d8  jmp     short loc_1400761E7
0x1400761da  mov     ecx, 1B3h
0x1400761df  jmp     loc_1400760F8
0x1400761e4  mov     r14, rsi
0x1400761e7  lea     rcx, SkmiNteLock
0x1400761ee  call    SkAcquireSpinLockExclusive
0x1400761f3  mov     [rsp+88h+arg_0], al
0x1400761fa  cmp     rdi, r13
0x1400761fd  ja      loc_140076495
0x140076203  test    r14, r14
0x140076206  mov     rcx, rsi
0x140076209  mov     r8d, esi
0x14007620c  mov     [rsp+88h+arg_18], rcx
0x140076214  mov     r12d, esi
0x140076217  mov     [rsp+88h+arg_10], r8
0x14007621f  setnz   r12b
0x140076223  mov     ebx, esi
0x140076225  test    r12d, r12d
0x140076228  jz      short loc_140076265
0x14007622a  mov     rax, 7FFFFFFFF8h
0x140076234  mov     rdx, rdi
0x140076237  shr     rdx, 9
0x14007623b  and     rdx, rax
0x14007623e  mov     rax, 0FFFFF68000000000h
0x140076248  mov     rax, rax
0x14007624b  add     rdx, rax
0x14007624e  mov     r12d, esi
0x140076251  mov     al, [rdx]
0x140076253  and     al, 80h
0x140076255  neg     al
0x140076257  sbb     rcx, rcx
0x14007625a  and     rcx, rdx
0x14007625d  mov     [rsp+88h+arg_18], rcx
0x140076265  test    rcx, rcx
0x140076268  jz      short loc_14007629D
0x14007626a  mov     rsi, [rcx]
0x14007626d  mov     r8d, 200h
0x140076273  mov     rbx, rdi
0x140076276  sar     rbx, 3
0x14007627a  and     ebx, 1FFh
0x140076280  sub     r8d, ebx
0x140076283  mov     [rsp+88h+arg_10], r8
0x14007628b  cmp     r8, rbp
0x14007628e  jbe     short loc_1400762A0
0x140076290  mov     r8d, ebp
0x140076293  mov     [rsp+88h+arg_10], r8
0x14007629b  jmp     short loc_1400762A0
0x14007629d  mov     rsi, [rdi]
0x1400762a0  mov     rax, rsi
0x1400762a3  and     rax, r15
0x1400762a6  cmp     rax, r15
0x1400762a9  jnz     loc_1400764B7
0x1400762af  mov     rax, 800000000000000h
0x1400762b9  cmp     rsi, rax
0x1400762bc  jnb     loc_1400764B7
0x1400762c2  shr     rsi, 0Ch
0x1400762c6  mov     rax, 0FFFFFFFFFFh
0x1400762d0  and     rsi, rax
0x1400762d3  test    rcx, rcx
0x1400762d6  jz      loc_1400763CD
0x1400762dc  movzx   eax, word ptr [r14]
0x1400762e0  cmp     ebx, eax
0x1400762e2  jnb     short loc_14007630D
0x1400762e4  mov     r15d, eax
0x1400762e7  mov     [r14], bx
0x1400762eb  mov     eax, ebx
0x1400762ed  cmp     rax, r15
0x1400762f0  jnb     short loc_14007630D
0x1400762f2  mov     ecx, ebx
0x1400762f4  add     rcx, rsi; BugCheckParameter3
0x1400762f7  call    SkmiDecrementPageReferenceCount
0x1400762fc  inc     ebx
0x1400762fe  mov     eax, ebx
0x140076300  cmp     rax, r15
0x140076303  jb      short loc_1400762F2
0x140076305  mov     rcx, [rsp+88h+arg_18]
0x14007630d  xor     esi, esi
0x14007630f  cmp     [r14], si
0x140076313  jnz     loc_1400763C0
0x140076319  mov     r15, cs:qword_14016A250
0x140076320  mov     rax, 0FFFFFFFFFF000h
0x14007632a  and     r15, rax
0x14007632d  mov     rdx, rcx
0x140076330  mov     rax, [rcx]
0x140076333  or      r15, 0AA1h
0x14007633a  mov     r9, r15
0x14007633d  mov     [rsp+88h+var_68], rax
0x140076342  xor     r8d, r8d
0x140076345  xor     ecx, ecx
0x140076347  call    SkmiGetPteTrace
0x14007634c  mov     r13, rax
0x14007634f  test    rax, rax
0x140076352  jz      short loc_1400763B0
0x140076354  xor     edx, edx; Val
0x140076356  lea     rsi, [rax+20h]
0x14007635a  mov     rcx, rsi; void *
0x14007635d  lea     r8d, [rdx+40h]; Size
0x140076361  call    memset_0
0x140076366  test    cs:SkmiFlags, 400000h
0x140076370  jz      short loc_1400763AE
0x140076372  mov     rcx, gs:8; FramesToSkip
0x14007637b  test    rcx, rcx
0x14007637e  jz      short loc_1400763AE
0x140076380  lea     r9, [rsp+88h+BackTraceHash]; BackTraceHash
0x140076388  mov     r8, rsi; BackTrace
0x14007638b  mov     edx, 8; FramesToCapture
0x140076390  call    RtlCaptureStackBackTrace
0x140076395  test    ax, ax
0x140076398  jnz     short loc_1400763AE
0x14007639a  mov     rax, [rsp+88h]
0x1400763a2  mov     [r13+28h], rax
0x1400763a6  call    SkmiGetInstructionPointer
0x1400763ab  mov     [rsi], rax
0x1400763ae  xor     esi, esi
0x1400763b0  mov     rcx, [rsp+88h+arg_18]
0x1400763b8  mov     r13, [rsp+88h+var_58]
0x1400763bd  mov     [rcx], r15
0x1400763c0  mov     r8, [rsp+88h+arg_10]
0x1400763c8  jmp     loc_1400764BE
0x1400763cd  mov     rcx, rsi; BugCheckParameter3
0x1400763d0  call    SkmiDecrementPageReferenceCount
0x1400763d5  mov     rax, [rdi]
0x1400763d8  mov     r9d, 0A21h
0x1400763de  xor     r8d, r8d
0x1400763e1  mov     [rsp+88h+var_68], rax
0x1400763e6  mov     rdx, rdi
0x1400763e9  xor     ecx, ecx
0x1400763eb  call    SkmiGetPteTrace
0x1400763f0  xor     esi, esi
0x1400763f2  mov     r15, rax
0x1400763f5  test    rax, rax
0x1400763f8  jz      short loc_140076456
0x1400763fa  xor     edx, edx; Val
0x1400763fc  lea     rsi, [rax+20h]
0x140076400  mov     rcx, rsi; void *
0x140076403  lea     r8d, [rdx+40h]; Size
0x140076407  call    memset_0
0x14007640c  test    cs:SkmiFlags, 400000h
0x140076416  jz      short loc_140076454
0x140076418  mov     rcx, gs:8; FramesToSkip
0x140076421  test    rcx, rcx
0x140076424  jz      short loc_140076454
0x140076426  lea     r9, [rsp+88h+BackTraceHash]; BackTraceHash
0x14007642e  mov     r8, rsi; BackTrace
0x140076431  mov     edx, 8; FramesToCapture
0x140076436  call    RtlCaptureStackBackTrace
0x14007643b  test    ax, ax
0x14007643e  jnz     short loc_140076454
0x140076440  mov     rax, [rsp+88h]
0x140076448  mov     [r15+28h], rax
0x14007644c  call    SkmiGetInstructionPointer
0x140076451  mov     [rsi], rax
0x140076454  xor     esi, esi
0x140076456  mov     rcx, [rsp+88h+arg_18]
0x14007645e  mov     qword ptr [rdi], 0A21h
0x140076465  mov     r8, [rsp+88h+arg_10]
0x14007646d  add     rdi, 8
0x140076471  test    r14, r14
0x140076474  jz      short loc_14007647F
0x140076476  test    rdi, 0FF8h
0x14007647d  jz      short loc_1400764C8
0x14007647f  mov     r15d, 900h
0x140076485  cmp     rdi, r13
0x140076488  jbe     loc_140076225
0x14007648e  mov     al, [rsp+88h+arg_0]
0x140076495  mov     dl, al
0x140076497  lea     rcx, SkmiNteLock
0x14007649e  call    SkReleaseSpinLockExclusive
0x1400764a3  xor     eax, eax
0x1400764a5  add     rsp, 48h
0x1400764a9  pop     r15
0x1400764ab  pop     r14
0x1400764ad  pop     r13
0x1400764af  pop     r12
0x1400764b1  pop     rdi
0x1400764b2  pop     rsi
0x1400764b3  pop     rbp
0x1400764b4  pop     rbx
0x1400764b5  retn
0x1400764b7  xor     esi, esi
0x1400764b9  test    rcx, rcx
0x1400764bc  jz      short loc_140076465
0x1400764be  mov     eax, r8d
0x1400764c1  sub     rbp, rax
0x1400764c4  lea     rdi, [rdi+rax*8]
0x1400764c8  mov     r12d, 1
0x1400764ce  add     r14, 2
0x1400764d2  jmp     short loc_14007647F
```
