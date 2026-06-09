# SkmiConfigureNormalBootDriverTablePage

- ea: `0x14007b0fc`
- end: `0x14007b406`
- name: `SkmiConfigureNormalBootDriverTablePage`
- size: `778`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007af88`
- `0x14007b060`

## callees

- `0x140003780`
- `0x140008ec4`
- `0x14002b534`
- `0x140050ba4`
- `0x14007b0fc`
- `0x14007c380`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiConfigureNormalBootDriverTablePage(unsigned __int64 a1, __int64 a2, int a3, int a4)
{
  unsigned int v6; // ebp
  ULONG_PTR v7; // rdi
  unsigned __int64 v9; // rbx
  __int64 PteTrace; // rax
  __int64 v11; // rdx
  __int64 v12; // r15
  PVOID *v13; // r14
  ULONG v14; // ecx
  __int64 v15; // rcx
  _QWORD *StackBase; // rax
  __int64 v17; // rcx
  int v18; // ecx
  __int64 result; // rax
  __int64 *v20; // r14
  unsigned __int64 v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rdi
  PVOID *v24; // rbx
  PVOID v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]
  ULONG_PTR v30; // [rsp+88h] [rbp+10h] BYREF
  ULONG BackTraceHash; // [rsp+90h] [rbp+18h] BYREF

  v6 = (a3 != 0) + 1;
  v7 = (*(_QWORD *)a2 >> 12) & 0xFFFFFFFFFFLL;
  v28 = a3 != 0 ? 24LL : 8LL;
  v9 = *(__int64 *)((char *)SkmiProtectionToPte + v28) & 0xFFF0000000000EFFuLL | (((16 * v7) | word_140156D90 & 1) << 8);
  PteTrace = SkmiGetPteTrace(
               0,
               a2,
               0,
               *(_DWORD *)((_BYTE *)SkmiProtectionToPte + v28) & 0xEFF
             | (((16 * (unsigned int)(*(_QWORD *)a2 >> 12)) | word_140156D90 & 1) << 8),
               *(_QWORD *)a2);
  v12 = PteTrace;
  if ( PteTrace )
  {
    v13 = (PVOID *)(PteTrace + 32);
    memset_0((void *)(PteTrace + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0
      && KeGetPcr()->NtTib.StackBase
      && !RtlCaptureStackBackTrace(v14, 8u, v13, &BackTraceHash) )
    {
      *(_QWORD *)(v12 + 40) = retaddr;
      *v13 = (PVOID)SkmiGetInstructionPointer(v15, v11);
    }
  }
  if ( (unsigned __int64)a2 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)a2 < 0xFFFFF6FB7DBED800uLL )
  {
    StackBase = KeGetPcr()->NtTib.StackBase;
    v17 = StackBase ? StackBase[10] : 0LL;
    v11 = *(_QWORD *)(v17 + 232);
    if ( v11 )
    {
      v18 = SkiKvaShadowMode;
      *(_QWORD *)(v11 + 8 * ((a2 >> 3) & 0x1FF)) = v9;
      if ( v18 != 2 && (v9 & 1) != 0 )
        v9 |= 0x8000000000000000uLL;
    }
  }
  *(_QWORD *)a2 = v9;
  if ( !a4 )
    return 0;
  if ( (unsigned int)SkmiRelocateBootPage(a2, v11, v6) )
  {
    v7 = (*(_QWORD *)a2 >> 12) & 0xFFFFFFFFFFLL;
LABEL_21:
    v20 = (__int64 *)(((a1 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL);
    v21 = (v7 << 12) | *(__int64 *)((char *)SkmiProtectionToPte + v28) & 0xFFF0000000000FFFuLL;
    *(_QWORD *)(8 * v7 - 0x180000000000LL) = *(_QWORD *)(8 * v7 - 0x180000000000LL) & 0x1FFFFFFFFFFFFFFFLL
                                           | 0x6000000000000000LL;
    v22 = SkmiGetPteTrace(0, (unsigned int)(a1 >> 9) & 0xFFFFFFF8, 0, v21, *v20);
    v23 = v22;
    if ( v22 )
    {
      v24 = (PVOID *)(v22 + 32);
      memset_0((void *)(v22 + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v25 = KeGetPcr()->NtTib.StackBase;
        if ( v25 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v25, 8u, v24, &BackTraceHash) )
          {
            *(_QWORD *)(v23 + 40) = retaddr;
            *v24 = (PVOID)SkmiGetInstructionPointer(v27, v26);
          }
        }
      }
    }
    *v20 = v21;
    return 0;
  }
  v30 = v7;
  if ( !(unsigned int)SkmiClaimPhysicalPages((ULONG_PTR)&v30, 1, 0x48005u) )
    return 3221225496LL;
  result = SkmiProtectSinglePage(v7);
  if ( (int)result >= 0 )
    goto LABEL_21;
  return result;
}

```

## disassembly

```asm
0x14007b0fc  mov     [rsp+arg_0], rbx
0x14007b101  push    rbp
0x14007b102  push    rsi
0x14007b103  push    rdi
0x14007b104  push    r12
0x14007b106  push    r13
0x14007b108  push    r14
0x14007b10a  push    r15
0x14007b10c  sub     rsp, 40h
0x14007b110  mov     r10, [rdx]
0x14007b113  mov     r12, rcx
0x14007b116  movzx   ebx, byte ptr cs:word_140156D90
0x14007b11d  mov     eax, r8d
0x14007b120  neg     eax
0x14007b122  mov     [rsp+78h+var_58], r10
0x14007b127  mov     rsi, rdx
0x14007b12a  mov     rax, 0FFFFFFFFFFh
0x14007b134  sbb     ebp, ebp
0x14007b136  lea     rdx, SkmiProtectionToPte
0x14007b13d  neg     ebp
0x14007b13f  mov     rdi, r10
0x14007b142  shr     rdi, 0Ch
0x14007b146  inc     ebp
0x14007b148  and     rdi, rax
0x14007b14b  mov     r13d, r9d
0x14007b14e  neg     r8d
0x14007b151  mov     rax, rdi
0x14007b154  sbb     rcx, rcx
0x14007b157  shl     rax, 4
0x14007b15b  and     ecx, 10h
0x14007b15e  and     ebx, 1
0x14007b161  add     rcx, 8
0x14007b165  or      rbx, rax
0x14007b168  mov     [rsp+78h+var_48], rcx
0x14007b16d  xor     r8d, r8d
0x14007b170  shl     rbx, 8
0x14007b174  mov     rax, [rcx+rdx]
0x14007b178  mov     rcx, 0FFF0000000000EFFh
0x14007b182  and     rax, rcx
0x14007b185  mov     rdx, rsi
0x14007b188  or      rbx, rax
0x14007b18b  xor     ecx, ecx
0x14007b18d  mov     r9, rbx
0x14007b190  call    SkmiGetPteTrace
0x14007b195  xor     r14d, r14d
0x14007b198  mov     r15, rax
0x14007b19b  test    rax, rax
0x14007b19e  jz      short loc_14007B1FA
0x14007b1a0  xor     edx, edx; Val
0x14007b1a2  lea     r14, [rax+20h]
0x14007b1a6  mov     rcx, r14; void *
0x14007b1a9  lea     r8d, [rdx+40h]; Size
0x14007b1ad  call    memset_0
0x14007b1b2  test    cs:SkmiFlags, 400000h
0x14007b1bc  jz      short loc_14007B1F7
0x14007b1be  mov     rax, gs:8
0x14007b1c7  test    rax, rax
0x14007b1ca  jz      short loc_14007B1F7
0x14007b1cc  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x14007b1d4  mov     r8, r14; BackTrace
0x14007b1d7  mov     edx, 8; FramesToCapture
0x14007b1dc  call    RtlCaptureStackBackTrace
0x14007b1e1  test    ax, ax
0x14007b1e4  jnz     short loc_14007B1F7
0x14007b1e6  mov     rax, [rsp+78h]
0x14007b1eb  mov     [r15+28h], rax
0x14007b1ef  call    SkmiGetInstructionPointer
0x14007b1f4  mov     [r14], rax
0x14007b1f7  xor     r14d, r14d
0x14007b1fa  mov     rax, 0FFFFF6FB7DBED000h
0x14007b204  cmp     rsi, rax
0x14007b207  jb      short loc_14007B268
0x14007b209  mov     rax, 0FFFFF6FB7DBED800h
0x14007b213  cmp     rsi, rax
0x14007b216  jnb     short loc_14007B268
0x14007b218  mov     rax, gs:8
0x14007b221  test    rax, rax
0x14007b224  jz      short loc_14007B22C
0x14007b226  mov     rcx, [rax+50h]
0x14007b22a  jmp     short loc_14007B22F
0x14007b22c  mov     rcx, r14
0x14007b22f  mov     rdx, [rcx+0E8h]
0x14007b236  test    rdx, rdx
0x14007b239  jz      short loc_14007B268
0x14007b23b  mov     ecx, cs:SkiKvaShadowMode
0x14007b241  mov     rax, rsi
0x14007b244  sar     rax, 3
0x14007b248  and     eax, 1FFh
0x14007b24d  mov     [rdx+rax*8], rbx
0x14007b251  cmp     ecx, 2
0x14007b254  jz      short loc_14007B268
0x14007b256  test    bl, 1
0x14007b259  jz      short loc_14007B268
0x14007b25b  mov     rax, 8000000000000000h
0x14007b265  or      rbx, rax
0x14007b268  mov     [rsi], rbx
0x14007b26b  test    r13d, r13d
0x14007b26e  jz      loc_14007B3EB
0x14007b274  mov     r8d, ebp
0x14007b277  mov     rcx, rsi
0x14007b27a  call    SkmiRelocateBootPage
0x14007b27f  test    eax, eax
0x14007b281  jz      short loc_14007B299
0x14007b283  mov     rdi, [rsi]
0x14007b286  mov     rax, 0FFFFFFFFFFh
0x14007b290  shr     rdi, 0Ch
0x14007b294  and     rdi, rax
0x14007b297  jmp     short loc_14007B2DD
0x14007b299  mov     edx, 1
0x14007b29e  mov     [rsp+78h+arg_8], rdi
0x14007b2a6  mov     r8d, 48005h
0x14007b2ac  lea     rcx, [rsp+78h+arg_8]
0x14007b2b4  call    SkmiClaimPhysicalPages
0x14007b2b9  test    eax, eax
0x14007b2bb  jnz     short loc_14007B2C7
0x14007b2bd  mov     eax, 0C0000018h
0x14007b2c2  jmp     loc_14007B3ED
0x14007b2c7  bts     ebp, 8
0x14007b2cb  mov     rcx, rdi; BugCheckParameter3
0x14007b2ce  mov     edx, ebp
0x14007b2d0  call    SkmiProtectSinglePage
0x14007b2d5  test    eax, eax
0x14007b2d7  js      loc_14007B3ED
0x14007b2dd  mov     rcx, 0FFFFEFFFFFFFFFFFh
0x14007b2e7  mov     rdx, 0FFFFE80000000000h
0x14007b2f1  mov     rax, rdx
0x14007b2f4  sub     rcx, rax
0x14007b2f7  sar     rcx, 3
0x14007b2fb  cmp     rdi, rcx
0x14007b2fe  jbe     short loc_14007B307
0x14007b300  mov     ecx, 3Fh ; '?'
0x14007b305  int     29h; Win8: RtlFailFast(ecx)
0x14007b307  shr     r12, 9
0x14007b30b  mov     r14, 7FFFFFFFF8h
0x14007b315  and     r14, r12
0x14007b318  mov     rax, 0FFFFF60000000000h
0x14007b322  mov     rsi, [rsp+78h+var_48]
0x14007b327  add     r14, rax
0x14007b32a  lea     rax, SkmiProtectionToPte
0x14007b331  mov     rsi, [rsi+rax]
0x14007b335  mov     rax, 0FFF0000000000FFFh
0x14007b33f  and     rsi, rax
0x14007b342  mov     rax, rdi
0x14007b345  shl     rax, 0Ch
0x14007b349  or      rsi, rax
0x14007b34c  mov     rcx, rdx
0x14007b34f  mov     rax, [rcx+rdi*8]
0x14007b353  mov     rdx, 1FFFFFFFFFFFFFFFh
0x14007b35d  and     rax, rdx
0x14007b360  mov     r9, rsi
0x14007b363  mov     rdx, 6000000000000000h
0x14007b36d  xor     r8d, r8d
0x14007b370  or      rax, rdx
0x14007b373  mov     rdx, r14
0x14007b376  mov     [rcx+rdi*8], rax
0x14007b37a  xor     ecx, ecx
0x14007b37c  mov     rax, [r14]
0x14007b37f  mov     [rsp+78h+var_58], rax
0x14007b384  call    SkmiGetPteTrace
0x14007b389  xor     ebp, ebp
0x14007b38b  mov     rdi, rax
0x14007b38e  test    rax, rax
0x14007b391  jz      short loc_14007B3E8
0x14007b393  lea     rbx, [rax+20h]
0x14007b397  xor     edx, edx; Val
0x14007b399  mov     rcx, rbx; void *
0x14007b39c  lea     r8d, [rbp+40h]; Size
0x14007b3a0  call    memset_0
0x14007b3a5  test    cs:SkmiFlags, 400000h
0x14007b3af  jz      short loc_14007B3E8
0x14007b3b1  mov     rcx, gs:8; FramesToSkip
0x14007b3ba  test    rcx, rcx
0x14007b3bd  jz      short loc_14007B3E8
0x14007b3bf  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x14007b3c7  mov     r8, rbx; BackTrace
0x14007b3ca  lea     edx, [rbp+8]; FramesToCapture
0x14007b3cd  call    RtlCaptureStackBackTrace
0x14007b3d2  test    ax, ax
0x14007b3d5  jnz     short loc_14007B3E8
0x14007b3d7  mov     rax, [rsp+78h]
0x14007b3dc  mov     [rdi+28h], rax
0x14007b3e0  call    SkmiGetInstructionPointer
0x14007b3e5  mov     [rbx], rax
0x14007b3e8  mov     [r14], rsi
0x14007b3eb  xor     eax, eax
0x14007b3ed  mov     rbx, [rsp+78h+arg_0]
0x14007b3f5  add     rsp, 40h
0x14007b3f9  pop     r15
0x14007b3fb  pop     r14
0x14007b3fd  pop     r13
0x14007b3ff  pop     r12
0x14007b401  pop     rdi
0x14007b402  pop     rsi
0x14007b403  pop     rbp
0x14007b404  retn
```
