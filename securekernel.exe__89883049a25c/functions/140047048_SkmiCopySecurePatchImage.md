# SkmiCopySecurePatchImage

- ea: `0x140047048`
- end: `0x14004723b`
- name: `SkmiCopySecurePatchImage`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140048bfc`

## callees

- `0x140003780`
- `0x14002b534`
- `0x140046cb0`
- `0x140047048`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCopySecurePatchImage(__int64 a1, __int64 a2, __int64 a3, unsigned __int64 a4)
{
  __int64 result; // rax
  __int64 v8; // rdi
  _QWORD *v9; // r15
  _QWORD *v10; // rsi
  unsigned int i; // ebp
  unsigned __int64 v12; // rbx
  __int64 PteTrace; // rax
  __int64 v14; // r10
  __int64 v15; // r12
  PVOID *v16; // r14
  PVOID StackBase; // rcx
  USHORT v18; // ax
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // ecx
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+90h] [rbp+18h] BYREF

  result = SkmiCopyPatchImage(*(_QWORD *)(a3 + 48), a4, a1, a2, *(_QWORD *)(a3 + 144) + 24LL);
  if ( (int)result >= 0 )
  {
    v8 = ((*(_QWORD *)(a3 + 48) >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    v9 = *(_QWORD **)(a1 + 8);
    v10 = (_QWORD *)(((a4 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL);
    for ( i = 0; i < *(_DWORD *)(a1 + 4); ++i )
    {
      if ( (*v9 & 0xE0) != 0 )
      {
        v12 = *v10 & 0xFFFFFFFFFF000LL
            | ((unsigned __int64)(word_140156D90 & 1) << 8)
            | SkmiProtectionToPte[(*v9 >> 5) & 0x1FLL] & 0xFFF0000000000EFFuLL;
        PteTrace = SkmiGetPteTrace(
                     0,
                     v8,
                     0,
                     *(_DWORD *)v10 & 0xFFFFF000
                   | ((word_140156D90 & 1) << 8)
                   | SkmiProtectionToPte[(*v9 >> 5) & 0x1FLL] & 0xEFF,
                     *(_QWORD *)v8);
        v15 = PteTrace;
        if ( PteTrace )
        {
          v16 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, 0x40u);
          v14 = 0;
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            StackBase = KeGetPcr()->NtTib.StackBase;
            if ( StackBase )
            {
              v18 = RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v16, &BackTraceHash);
              v14 = 0;
              if ( !v18 )
              {
                *(_QWORD *)(v15 + 40) = retaddr;
                *v16 = (PVOID)SkmiGetInstructionPointer(v20, v19);
              }
            }
          }
        }
        if ( (unsigned __int64)v8 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v8 < 0xFFFFF6FB7DBED800uLL )
        {
          v21 = KeGetPcr()->NtTib.StackBase;
          if ( v21 )
            v22 = v21[10];
          else
            v22 = v14;
          v23 = *(_QWORD *)(v22 + 232);
          if ( v23 )
          {
            v24 = SkiKvaShadowMode;
            *(_QWORD *)(v23 + 8 * ((v8 >> 3) & 0x1FF)) = v12;
            if ( v24 != 2 && (v12 & 1) != 0 )
              v12 |= 0x8000000000000000uLL;
          }
        }
        *(_QWORD *)v8 = v12;
      }
      v8 += 8;
      ++v10;
      ++v9;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140047048  push    rbx
0x14004704a  push    rbp
0x14004704b  push    rsi
0x14004704c  push    rdi
0x14004704d  push    r12
0x14004704f  push    r13
0x140047051  push    r14
0x140047053  push    r15
0x140047055  sub     rsp, 38h
0x140047059  mov     rax, [r8+90h]
0x140047060  mov     rdi, r8
0x140047063  mov     rsi, r9
0x140047066  mov     r13, rcx
0x140047069  add     rax, 18h
0x14004706d  mov     r9, rdx
0x140047070  mov     r8, rcx
0x140047073  mov     [rsp+78h+var_58], rax
0x140047078  mov     rcx, [rdi+30h]
0x14004707c  mov     rdx, rsi
0x14004707f  call    SkmiCopyPatchImage
0x140047084  xor     r10d, r10d
0x140047087  test    eax, eax
0x140047089  js      loc_140047229
0x14004708f  mov     rdi, [rdi+30h]
0x140047093  mov     rdx, 7FFFFFFFF8h
0x14004709d  shr     rdi, 9
0x1400470a1  and     rdi, rdx
0x1400470a4  mov     rcx, 0FFFFF68000000000h
0x1400470ae  mov     rax, rcx
0x1400470b1  shr     rsi, 9
0x1400470b5  add     rdi, rax
0x1400470b8  and     rsi, rdx
0x1400470bb  mov     rax, rcx
0x1400470be  mov     r15, [r13+8]
0x1400470c2  add     rsi, rax
0x1400470c5  mov     ebp, r10d
0x1400470c8  cmp     [r13+4], r10d
0x1400470cc  jbe     loc_140047227
0x1400470d2  mov     rbx, [r15]
0x1400470d5  test    bl, 0E0h
0x1400470d8  jz      loc_14004720F
0x1400470de  shr     rbx, 5
0x1400470e2  lea     rax, SkmiProtectionToPte
0x1400470e9  and     ebx, 1Fh
0x1400470ec  mov     rcx, 0FFFFFFFFFF000h
0x1400470f6  xor     r8d, r8d
0x1400470f9  mov     rdx, rdi
0x1400470fc  mov     rbx, [rax+rbx*8]
0x140047100  mov     rax, 0FFF0000000000EFFh
0x14004710a  and     rbx, rax
0x14004710d  movzx   eax, byte ptr cs:word_140156D90
0x140047114  and     eax, 1
0x140047117  shl     rax, 8
0x14004711b  or      rbx, rax
0x14004711e  mov     rax, [rsi]
0x140047121  and     rax, rcx
0x140047124  xor     ecx, ecx
0x140047126  or      rbx, rax
0x140047129  mov     rax, [rdi]
0x14004712c  mov     r9, rbx
0x14004712f  mov     [rsp+78h+var_58], rax
0x140047134  call    SkmiGetPteTrace
0x140047139  mov     r12, rax
0x14004713c  test    rax, rax
0x14004713f  jz      short loc_14004719E
0x140047141  xor     edx, edx; Val
0x140047143  lea     r14, [rax+20h]
0x140047147  mov     rcx, r14; void *
0x14004714a  lea     r8d, [rdx+40h]; Size
0x14004714e  call    memset_0
0x140047153  xor     r10d, r10d
0x140047156  test    cs:SkmiFlags, 400000h
0x140047160  jz      short loc_14004719E
0x140047162  mov     rcx, gs:8; FramesToSkip
0x14004716b  test    rcx, rcx
0x14004716e  jz      short loc_14004719E
0x140047170  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x140047178  mov     r8, r14; BackTrace
0x14004717b  lea     edx, [r10+8]; FramesToCapture
0x14004717f  call    RtlCaptureStackBackTrace
0x140047184  xor     r10d, r10d
0x140047187  test    ax, ax
0x14004718a  jnz     short loc_14004719E
0x14004718c  mov     rax, [rsp+78h]
0x140047191  mov     [r12+28h], rax
0x140047196  call    SkmiGetInstructionPointer
0x14004719b  mov     [r14], rax
0x14004719e  mov     rax, 0FFFFF6FB7DBED000h
0x1400471a8  cmp     rdi, rax
0x1400471ab  jb      short loc_14004720C
0x1400471ad  mov     rax, 0FFFFF6FB7DBED800h
0x1400471b7  cmp     rdi, rax
0x1400471ba  jnb     short loc_14004720C
0x1400471bc  mov     rax, gs:8
0x1400471c5  test    rax, rax
0x1400471c8  jz      short loc_1400471D0
0x1400471ca  mov     rcx, [rax+50h]
0x1400471ce  jmp     short loc_1400471D3
0x1400471d0  mov     rcx, r10
0x1400471d3  mov     rdx, [rcx+0E8h]
0x1400471da  test    rdx, rdx
0x1400471dd  jz      short loc_14004720C
0x1400471df  mov     ecx, cs:SkiKvaShadowMode
0x1400471e5  mov     rax, rdi
0x1400471e8  sar     rax, 3
0x1400471ec  and     eax, 1FFh
0x1400471f1  mov     [rdx+rax*8], rbx
0x1400471f5  cmp     ecx, 2
0x1400471f8  jz      short loc_14004720C
0x1400471fa  test    bl, 1
0x1400471fd  jz      short loc_14004720C
0x1400471ff  mov     rax, 8000000000000000h
0x140047209  or      rbx, rax
0x14004720c  mov     [rdi], rbx
0x14004720f  add     rdi, 8
0x140047213  add     rsi, 8
0x140047217  add     r15, 8
0x14004721b  inc     ebp
0x14004721d  cmp     ebp, [r13+4]
0x140047221  jb      loc_1400470D2
0x140047227  xor     eax, eax
0x140047229  add     rsp, 38h
0x14004722d  pop     r15
0x14004722f  pop     r14
0x140047231  pop     r13
0x140047233  pop     r12
0x140047235  pop     rdi
0x140047236  pop     rsi
0x140047237  pop     rbp
0x140047238  pop     rbx
0x140047239  retn
```
