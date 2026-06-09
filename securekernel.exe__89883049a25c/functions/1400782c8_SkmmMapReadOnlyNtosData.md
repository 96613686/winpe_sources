# SkmmMapReadOnlyNtosData

- ea: `0x1400782c8`
- end: `0x140078722`
- name: `SkmmMapReadOnlyNtosData`
- size: `1114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `14`
- tags: ``

## callers

- `0x140014dd0`
- `0x14006dcfc`
- `0x1400889ec`

## callees

- `0x140003780`
- `0x14000b980`
- `0x14000c580`
- `0x14000e810`
- `0x14000ff70`
- `0x140020360`
- `0x140020424`
- `0x140025024`
- `0x14002b534`
- `0x14004eb04`
- `0x14004fe2c`
- `0x1400782c8`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmMapReadOnlyNtosData(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v5; // r14d
  unsigned __int64 v6; // rdi
  __int64 result; // rax
  __int64 v8; // r12
  unsigned __int64 v9; // rbx
  char v10; // al
  __int64 v11; // r10
  char v12; // r13
  __int64 v13; // rcx
  ULONG v14; // r15d
  __int64 v15; // r12
  __int64 PteTrace; // rax
  __int64 v17; // r13
  PVOID *v18; // r15
  PVOID StackBase; // rcx
  USHORT v20; // ax
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned __int64 v23; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // edx
  char v28; // al
  __int64 v29; // r8
  __int64 v30; // rdi
  __int64 v31; // rsi
  unsigned __int64 v32; // rbx
  __int64 v33; // rax
  int v34; // r9d
  __int64 v35; // r10
  __int64 v36; // r13
  PVOID *v37; // r12
  PVOID v38; // rcx
  USHORT v39; // ax
  __int64 v40; // rdx
  __int64 v41; // rcx
  _QWORD *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  _QWORD *v45; // rdx
  __int64 v46; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v47; // [rsp+38h] [rbp-C8h] BYREF
  ULONG_PTR BugCheckParameter3; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v49; // [rsp+48h] [rbp-B8h]
  _BYTE v50[256]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v51; // [rsp+150h] [rbp+50h]
  char v52; // [rsp+154h] [rbp+54h]
  char v53; // [rsp+155h] [rbp+55h]
  _UNKNOWN *retaddr; // [rsp+1A8h] [rbp+A8h]
  char v55; // [rsp+1B0h] [rbp+B0h]
  ULONG v56; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD *v57; // [rsp+1C0h] [rbp+C0h]
  ULONG BackTraceHash; // [rsp+1C8h] [rbp+C8h] BYREF

  v57 = a3;
  memset_0(v50, 0, 0x108u);
  v5 = 0;
  v47 = 0;
  v56 = 0;
  BugCheckParameter3 = 0;
  v6 = ((unsigned __int64)(a1 & 0xFFF) + a2 + 4095) >> 12;
  v49 = v6;
  if ( v6 != (unsigned int)v6 )
    return 3221225485LL;
  result = SkmiReserveMappingAddress(0, v6, &v47);
  if ( (int)result >= 0 )
  {
    v8 = ((v47 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    v9 = ((unsigned __int64)(word_140156D90 & 1) << 8) | 0x8000000000000063uLL;
    v46 = v8;
    v10 = SkAcquireSpinLockShared(&SkmiNteLock);
    LODWORD(v11) = 0;
    v55 = v10;
    v12 = v10;
    if ( v6 )
    {
      while ( 1 )
      {
        BackTraceHash = SkmiIncrementNtPageReferenceCount(a1, &BugCheckParameter3, &v56);
        v14 = BackTraceHash;
        if ( (BackTraceHash & 0x80000000) != 0 )
          break;
        if ( (v56 & 2) == 0 )
        {
          SkmiDecrementPageReferenceCount(BugCheckParameter3);
          v14 = -1073741819;
          BackTraceHash = -1073741819;
          break;
        }
        v9 = v9 & 0xFFF0000000000FFFuLL | ((BugCheckParameter3 & 0xFFFFFFFFFFLL) << 12);
        v15 = v8 + 8LL * v5;
        PteTrace = SkmiGetPteTrace(0, v15, 0, v9, *(_QWORD *)v15);
        v17 = PteTrace;
        if ( PteTrace )
        {
          v18 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, (unsigned int)(v11 + 64));
          v11 = 0;
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            StackBase = KeGetPcr()->NtTib.StackBase;
            if ( StackBase )
            {
              v20 = RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v18, &BackTraceHash);
              v11 = 0;
              if ( !v20 )
              {
                *(_QWORD *)(v17 + 40) = retaddr;
                *v18 = (PVOID)SkmiGetInstructionPointer(v22, v21);
              }
            }
          }
        }
        v23 = v9;
        if ( (unsigned __int64)v15 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v15 < 0xFFFFF6FB7DBED800uLL )
        {
          v24 = KeGetPcr()->NtTib.StackBase;
          if ( v24 )
            v25 = v24[10];
          else
            v25 = v11;
          v26 = *(_QWORD *)(v25 + 232);
          if ( v26 )
          {
            v27 = SkiKvaShadowMode;
            *(_QWORD *)(v26 + 8 * ((v15 >> 3) & 0x1FF)) = v9;
            if ( v27 != 2 && (v9 & 1) != 0 )
              v23 = v9 | 0x8000000000000000uLL;
          }
        }
        ++v5;
        *(_QWORD *)v15 = v23;
        a1 += 4096;
        if ( v5 >= v6 )
        {
          v12 = v55;
          goto LABEL_47;
        }
        v8 = v46;
      }
      v51 = 0;
      v28 = 0;
      v52 = 0;
      LOBYTE(v13) = -1;
      v53 = -1;
      v29 = 0;
      if ( v5 )
      {
        SkmiBatchFlushTbRange(v47, v5, v50);
        v30 = v5;
        do
        {
          --v30;
          --v5;
          v31 = v8 + 8 * v30;
          v32 = *(_QWORD *)v31;
          v33 = SkmiGetPteTrace(0, (int)v8 + 8 * (int)v30, 0, 0, *(_QWORD *)v31);
          v36 = v33;
          if ( v33 )
          {
            v37 = (PVOID *)(v33 + 32);
            memset_0((void *)(v33 + 32), 0, (unsigned int)(v34 + 64));
            v35 = 0;
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              v38 = KeGetPcr()->NtTib.StackBase;
              if ( v38 )
              {
                v39 = RtlCaptureStackBackTrace((ULONG)v38, 8u, v37, &v56);
                v35 = 0;
                if ( !v39 )
                {
                  *(_QWORD *)(v36 + 40) = retaddr;
                  *v37 = (PVOID)SkmiGetInstructionPointer(v41, v40);
                }
              }
            }
            v8 = v46;
          }
          if ( (unsigned __int64)v31 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v31 < 0xFFFFF6FB7DBED800uLL )
          {
            v42 = KeGetPcr()->NtTib.StackBase;
            v43 = v42 ? v42[10] : v35;
            v44 = *(_QWORD *)(v43 + 232);
            if ( v44 )
              *(_QWORD *)(v44 + 8 * ((v31 >> 3) & 0x1FF)) = v35;
          }
          *(_QWORD *)v31 = v35;
          SkmiDecrementPageReferenceCount((v32 >> 12) & 0xFFFFFFFFFFLL);
        }
        while ( v5 );
        LOBYTE(v13) = v53;
        v28 = v52;
        v29 = v51;
        v6 = v49;
        v14 = BackTraceHash;
      }
      if ( v28 )
      {
        SkeFlushEntireTb(v13, 0);
      }
      else if ( (_DWORD)v29 )
      {
        SkeFlushRangeListTb(v13, 0, v29, v50);
      }
      SkmmFreeReservedMapping(v47, v6 << 12);
      v12 = v55;
    }
    else
    {
LABEL_47:
      v45 = v57;
      v14 = v11;
      *v57 = v47 + (a1 & 0xFFF);
    }
    LOBYTE(v45) = v12;
    RtlpReleasePropStoreLockShared(&SkmiNteLock, v45);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x1400782c8  mov     [rsp-8+arg_10], r8
0x1400782cd  push    rbp
0x1400782ce  push    rbx
0x1400782cf  push    rsi
0x1400782d0  push    rdi
0x1400782d1  push    r12
0x1400782d3  push    r13
0x1400782d5  push    r14
0x1400782d7  push    r15
0x1400782d9  lea     rbp, [rsp-68h]
0x1400782de  sub     rsp, 168h
0x1400782e5  mov     rdi, rdx
0x1400782e8  mov     rsi, rcx
0x1400782eb  xor     edx, edx; Val
0x1400782ed  lea     rcx, [rsp+1A0h+var_150]; void *
0x1400782f2  mov     r8d, 108h; Size
0x1400782f8  call    memset_0
0x1400782fd  xor     r14d, r14d
0x140078300  mov     eax, esi
0x140078302  and     eax, 0FFFh
0x140078307  mov     [rsp+1A0h+var_168], r14
0x14007830c  add     rdi, 0FFFh
0x140078313  mov     [rbp+0A0h+arg_8], r14d
0x14007831a  add     rdi, rax
0x14007831d  mov     [rsp+1A0h+BugCheckParameter3], r14
0x140078322  shr     rdi, 0Ch
0x140078326  mov     eax, edi
0x140078328  mov     [rsp+1A0h+var_158], rdi
0x14007832d  cmp     rdi, rax
0x140078330  jz      short loc_14007833C
0x140078332  mov     eax, 0C000000Dh
0x140078337  jmp     loc_14007870D
0x14007833c  lea     r8, [rsp+1A0h+var_168]
0x140078341  mov     rdx, rdi
0x140078344  xor     ecx, ecx
0x140078346  call    SkmiReserveMappingAddress
0x14007834b  test    eax, eax
0x14007834d  js      loc_14007870D
0x140078353  mov     r12, [rsp+1A0h+var_168]
0x140078358  mov     rax, 7FFFFFFFF8h
0x140078362  shr     r12, 9
0x140078366  and     r12, rax
0x140078369  mov     rax, 0FFFFF68000000000h
0x140078373  movzx   ebx, byte ptr cs:word_140156D90
0x14007837a  lea     rcx, SkmiNteLock
0x140078381  add     r12, rax
0x140078384  and     ebx, 1
0x140078387  mov     rax, 8000000000000063h
0x140078391  shl     rbx, 8
0x140078395  or      rbx, rax
0x140078398  mov     [rsp+1A0h+var_170], r12
0x14007839d  call    SkAcquireSpinLockShared
0x1400783a2  xor     r10d, r10d
0x1400783a5  mov     [rbp+0A0h+arg_0], al
0x1400783ab  mov     r13b, al
0x1400783ae  test    rdi, rdi
0x1400783b1  jz      loc_1400786E2
0x1400783b7  lea     r8, [rbp+0A0h+arg_8]
0x1400783be  mov     rcx, rsi
0x1400783c1  lea     rdx, [rsp+1A0h+BugCheckParameter3]
0x1400783c6  mov     r13, 0FFFFFFFFFFh
0x1400783d0  call    SkmiIncrementNtPageReferenceCount
0x1400783d5  xor     r10d, r10d
0x1400783d8  mov     [rbp+0A0h+BackTraceHash], eax
0x1400783de  mov     r15d, eax
0x1400783e1  test    eax, eax
0x1400783e3  js      loc_14007854E
0x1400783e9  test    byte ptr [rbp+0A0h+arg_8], 2
0x1400783f0  mov     rcx, [rsp+1A0h+BugCheckParameter3]; BugCheckParameter3
0x1400783f5  jz      loc_140078539
0x1400783fb  and     rcx, r13
0x1400783fe  mov     rax, rbx
0x140078401  shl     rcx, 0Ch
0x140078405  mov     rdx, 0FFF0000000000FFFh
0x14007840f  and     rax, rdx
0x140078412  mov     rbx, rcx
0x140078415  or      rbx, rax
0x140078418  xor     r8d, r8d
0x14007841b  mov     eax, r14d
0x14007841e  mov     r9, rbx
0x140078421  xor     ecx, ecx
0x140078423  lea     r12, [r12+rax*8]
0x140078427  mov     rax, [r12]
0x14007842b  mov     rdx, r12
0x14007842e  mov     [rsp+1A0h+var_180], rax
0x140078433  call    SkmiGetPteTrace
0x140078438  mov     r13, rax
0x14007843b  test    rax, rax
0x14007843e  jz      short loc_14007849D
0x140078440  lea     r15, [rax+20h]
0x140078444  xor     edx, edx; Val
0x140078446  mov     rcx, r15; void *
0x140078449  lea     r8d, [r10+40h]; Size
0x14007844d  call    memset_0
0x140078452  xor     r10d, r10d
0x140078455  test    cs:SkmiFlags, 400000h
0x14007845f  jz      short loc_14007849D
0x140078461  mov     rcx, gs:8; FramesToSkip
0x14007846a  test    rcx, rcx
0x14007846d  jz      short loc_14007849D
0x14007846f  lea     r9, [rbp+0A0h+BackTraceHash]; BackTraceHash
0x140078476  mov     r8, r15; BackTrace
0x140078479  lea     edx, [r10+8]; FramesToCapture
0x14007847d  call    RtlCaptureStackBackTrace
0x140078482  xor     r10d, r10d
0x140078485  test    ax, ax
0x140078488  jnz     short loc_14007849D
0x14007848a  mov     rax, [rbp+0A8h]
0x140078491  mov     [r13+28h], rax
0x140078495  call    SkmiGetInstructionPointer
0x14007849a  mov     [r15], rax
0x14007849d  mov     rax, rbx
0x1400784a0  mov     rcx, 0FFFFF6FB7DBED000h
0x1400784aa  mov     rcx, rcx
0x1400784ad  cmp     r12, rcx
0x1400784b0  jb      short loc_140078515
0x1400784b2  mov     rcx, 0FFFFF6FB7DBED800h
0x1400784bc  mov     rcx, rcx
0x1400784bf  cmp     r12, rcx
0x1400784c2  jnb     short loc_140078515
0x1400784c4  mov     rcx, gs:8
0x1400784cd  test    rcx, rcx
0x1400784d0  jz      short loc_1400784D8
0x1400784d2  mov     rdx, [rcx+50h]
0x1400784d6  jmp     short loc_1400784DB
0x1400784d8  mov     rdx, r10
0x1400784db  mov     r8, [rdx+0E8h]
0x1400784e2  test    r8, r8
0x1400784e5  jz      short loc_140078515
0x1400784e7  mov     edx, cs:SkiKvaShadowMode
0x1400784ed  mov     rcx, r12
0x1400784f0  sar     rcx, 3
0x1400784f4  and     ecx, 1FFh
0x1400784fa  mov     [r8+rcx*8], rbx
0x1400784fe  cmp     edx, 2
0x140078501  jz      short loc_140078515
0x140078503  test    bl, 1
0x140078506  jz      short loc_140078515
0x140078508  mov     rcx, 8000000000000000h
0x140078512  or      rax, rcx
0x140078515  inc     r14d
0x140078518  mov     [r12], rax
0x14007851c  mov     eax, r14d
0x14007851f  add     rsi, 1000h
0x140078526  cmp     rax, rdi
0x140078529  jnb     loc_1400786DB
0x14007852f  mov     r12, [rsp+1A0h+var_170]
0x140078534  jmp     loc_1400783B7
0x140078539  call    SkmiDecrementPageReferenceCount
0x14007853e  mov     r15d, 0C0000005h
0x140078544  xor     r10d, r10d
0x140078547  mov     [rbp+0A0h+BackTraceHash], r15d
0x14007854e  mov     [rbp+0A0h+var_50], r10d
0x140078552  mov     al, r10b
0x140078555  mov     [rbp+0A0h+var_4C], al
0x140078558  mov     cl, 0FFh
0x14007855a  mov     [rbp+0A0h+var_4B], cl
0x14007855d  mov     r8d, r10d
0x140078560  test    r14d, r14d
0x140078563  jz      loc_1400786A3
0x140078569  mov     rcx, [rsp+1A0h+var_168]
0x14007856e  lea     r8, [rsp+1A0h+var_150]
0x140078573  mov     edx, r14d
0x140078576  call    SkmiBatchFlushTbRange
0x14007857b  xor     r10d, r10d
0x14007857e  mov     edi, r14d
0x140078581  mov     r15, 0FFFFF6FB7DBED000h
0x14007858b  dec     rdi
0x14007858e  xor     r9d, r9d
0x140078591  xor     r8d, r8d
0x140078594  xor     ecx, ecx
0x140078596  dec     r14d
0x140078599  lea     rsi, [r12+rdi*8]
0x14007859d  mov     rbx, [rsi]
0x1400785a0  mov     rdx, rsi
0x1400785a3  mov     rax, [rsi]
0x1400785a6  mov     [rsp+1A0h+var_180], rax
0x1400785ab  call    SkmiGetPteTrace
0x1400785b0  mov     r13, rax
0x1400785b3  test    rax, rax
0x1400785b6  jz      short loc_14007861B
0x1400785b8  lea     r12, [rax+20h]
0x1400785bc  xor     edx, edx; Val
0x1400785be  mov     rcx, r12; void *
0x1400785c1  lea     r8d, [r9+40h]; Size
0x1400785c5  call    memset_0
0x1400785ca  xor     r10d, r10d
0x1400785cd  test    cs:SkmiFlags, 400000h
0x1400785d7  jz      short loc_140078616
0x1400785d9  mov     rcx, gs:8; FramesToSkip
0x1400785e2  test    rcx, rcx
0x1400785e5  jz      short loc_140078616
0x1400785e7  lea     r9, [rbp+0A0h+arg_8]; BackTraceHash
0x1400785ee  mov     r8, r12; BackTrace
0x1400785f1  lea     edx, [r10+8]; FramesToCapture
0x1400785f5  call    RtlCaptureStackBackTrace
0x1400785fa  xor     r10d, r10d
0x1400785fd  test    ax, ax
0x140078600  jnz     short loc_140078616
0x140078602  mov     rax, [rbp+0A8h]
0x140078609  mov     [r13+28h], rax
0x14007860d  call    SkmiGetInstructionPointer
0x140078612  mov     [r12], rax
0x140078616  mov     r12, [rsp+1A0h+var_170]
0x14007861b  mov     rax, r15
0x14007861e  cmp     rsi, rax
0x140078621  jb      short loc_140078668
0x140078623  mov     rax, 0FFFFF6FB7DBED800h
0x14007862d  mov     rax, rax
0x140078630  cmp     rsi, rax
0x140078633  jnb     short loc_140078668
0x140078635  mov     rax, gs:8
0x14007863e  test    rax, rax
0x140078641  jz      short loc_140078649
0x140078643  mov     rcx, [rax+50h]
0x140078647  jmp     short loc_14007864C
0x140078649  mov     rcx, r10
0x14007864c  mov     rdx, [rcx+0E8h]
0x140078653  test    rdx, rdx
0x140078656  jz      short loc_140078668
0x140078658  mov     rax, rsi
0x14007865b  sar     rax, 3
0x14007865f  and     eax, 1FFh
0x140078664  mov     [rdx+rax*8], r10
0x140078668  shr     rbx, 0Ch
0x14007866c  mov     rcx, 0FFFFFFFFFFh
0x140078676  and     rcx, rbx; BugCheckParameter3
0x140078679  mov     [rsi], r10
0x14007867c  call    SkmiDecrementPageReferenceCount
0x140078681  xor     r10d, r10d
0x140078684  test    r14d, r14d
0x140078687  jnz     loc_14007858B
0x14007868d  mov     cl, [rbp+0A0h+var_4B]
0x140078690  mov     al, [rbp+0A0h+var_4C]
0x140078693  mov     r8d, [rbp+0A0h+var_50]
0x140078697  mov     rdi, [rsp+1A0h+var_158]
0x14007869c  mov     r15d, [rbp+0A0h+BackTraceHash]
0x1400786a3  test    al, al
0x1400786a5  jz      short loc_1400786B0
0x1400786a7  xor     edx, edx
0x1400786a9  call    SkeFlushEntireTb
0x1400786ae  jmp     short loc_1400786C1
0x1400786b0  test    r8d, r8d
0x1400786b3  jz      short loc_1400786C1
0x1400786b5  lea     r9, [rsp+1A0h+var_150]
0x1400786ba  xor     edx, edx
0x1400786bc  call    SkeFlushRangeListTb
0x1400786c1  mov     rcx, [rsp+1A0h+var_168]
0x1400786c6  shl     rdi, 0Ch
0x1400786ca  mov     rdx, rdi
0x1400786cd  call    SkmmFreeReservedMapping
0x1400786d2  mov     r13b, [rbp+0A0h+arg_0]
0x1400786d9  jmp     short loc_1400786FB
0x1400786db  mov     r13b, [rbp+0A0h+arg_0]
0x1400786e2  mov     rdx, [rbp+0A0h+arg_10]
0x1400786e9  mov     eax, esi
0x1400786eb  and     eax, 0FFFh
0x1400786f0  mov     r15d, r10d
0x1400786f3  add     rax, [rsp+1A0h+var_168]
0x1400786f8  mov     [rdx], rax
0x1400786fb  mov     dl, r13b
0x1400786fe  lea     rcx, SkmiNteLock
0x140078705  call    RtlpReleasePropStoreLockShared
0x14007870a  mov     eax, r15d
0x14007870d  add     rsp, 168h
0x140078714  pop     r15
0x140078716  pop     r14
0x140078718  pop     r13
0x14007871a  pop     r12
0x14007871c  pop     rdi
0x14007871d  pop     rsi
0x14007871e  pop     rbx
0x14007871f  pop     rbp
0x140078720  retn
```
