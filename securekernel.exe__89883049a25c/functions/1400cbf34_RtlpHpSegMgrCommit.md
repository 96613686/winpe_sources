# RtlpHpSegMgrCommit

- ea: `0x1400cbf34`
- end: `0x1400cc1d3`
- name: `RtlpHpSegMgrCommit`
- size: `671`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400cbd94`
- `0x1400cc354`
- `0x1400ccd44`

## callees

- `0x1400326d4`
- `0x1400c7998`
- `0x1400c8264`
- `0x1400c90a0`
- `0x1400c9304`
- `0x1400cbf34`
- `0x1400cc1dc`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall RtlpHpSegMgrCommit(
        int *a1,
        unsigned __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        unsigned int a6,
        int a7)
{
  unsigned __int64 v7; // rsi
  int v9; // r12d
  unsigned __int64 v11; // r15
  int v13; // ebx
  unsigned int v14; // ebx
  int v15; // r12d
  volatile signed __int16 *v16; // r10
  unsigned __int64 v17; // r15
  unsigned int v18; // r13d
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned __int64 v22; // rcx
  signed __int16 v23; // ax
  signed __int16 v24; // cx
  __int16 v25; // dx
  signed __int16 v26; // dx
  signed __int16 v27; // tt
  int v29; // [rsp+20h] [rbp-58h]
  int v30; // [rsp+30h] [rbp-48h]
  __int64 v31; // [rsp+38h] [rbp-40h] BYREF
  __int128 v32; // [rsp+40h] [rbp-38h] BYREF
  volatile signed __int16 *v33; // [rsp+50h] [rbp-28h] BYREF
  __int64 v34; // [rsp+58h] [rbp-20h] BYREF
  __int128 v35; // [rsp+60h] [rbp-18h] BYREF
  char v36; // [rsp+C0h] [rbp+48h] BYREF

  v7 = a5;
  v9 = *a1;
  v11 = a3;
  v33 = 0;
  v36 = 0;
  v34 = 0;
  if ( a5 > 0 && !(unsigned int)RtlpHpSegHeapCheckCommitLimit(a5 << 12) )
    return (unsigned int)-1073741523;
  v14 = a6;
  v30 = a6 & 0x40000000;
  if ( (*((_BYTE *)a1 + 13) & 7) != 0 )
  {
    v32 = *(_OWORD *)(a1 + 10);
    RtlpHpQueryVA(a2 & 0xFFFFFFFFFFE00000uLL, &v32, &v33, 0);
    if ( (int)v7 <= 0 || (_DWORD)v11 || (unsigned int)-v9 >= 0x200000 || a2 <= (a2 & 0xFFFFFFFFFFE00000uLL) )
    {
      v15 = a7;
    }
    else
    {
      v15 = a7;
      if ( (a7 & 2) == 0 )
        v15 = a7 | 1;
    }
    v14 = a6;
    v16 = &v33[v11 >> 9];
  }
  else
  {
    v15 = a7;
    v16 = 0;
  }
  v17 = a2 + (unsigned int)((_DWORD)v11 << 12);
  v33 = v16;
  v18 = a4 << 12;
  while ( 1 )
  {
    *(_QWORD *)&v32 = v17;
    v31 = v18;
    if ( v16 )
      break;
LABEL_21:
    v35 = *(_OWORD *)(a1 + 10);
    if ( (int)v7 <= 0 )
      v21 = RtlpHpFreeVA(&v32, &v31, v14, &v35);
    else
      v21 = RtlpHpAllocVA((unsigned int)&v32, (unsigned int)&v31, 0, v14, v29, (__int64)&v35);
    v16 = v33;
    v13 = v21;
    if ( !v33 )
      return (unsigned int)v13;
    if ( (*v33 & 0x4000) != 0 && v21 >= 0 )
    {
      v22 = 1;
      if ( (int)v7 <= 0 )
        v22 = -1;
      _InterlockedAdd64((volatile signed __int64 *)((char *)a1 + *((__int16 *)a1 + 10) + 8), v22);
      _InterlockedAdd64((volatile signed __int64 *)((char *)a1 + *((__int16 *)a1 + 10)), v7);
    }
    v23 = *v16;
    while ( 1 )
    {
      LOWORD(a5) = v23;
      v24 = v23;
      if ( (v23 & 0x4000) != 0 )
      {
        if ( v13 < 0 || (int)v7 <= 0 )
          v25 = 0;
        else
          v25 = 0x8000;
        v24 = v25 | v23 & 0x3FFF;
      }
      if ( (int)v7 <= 0 )
      {
        v24 += v7;
      }
      else if ( v13 < 0 )
      {
        v24 -= v7;
      }
      if ( v24 == v23 )
        break;
      v26 = v23;
      v27 = v23;
      v23 = _InterlockedCompareExchange16(v16, v24, v23);
      if ( v27 == v23 )
      {
        if ( (v26 & 0x4000) != 0 )
        {
          RtlpHpReleaseLockExclusive(&v34);
          v16 = v33;
        }
        break;
      }
    }
    if ( (a6 & 0x20000000) == 0 || v13 >= 0 || (v15 & 2) != 0 )
      return (unsigned int)v13;
    v15 |= 1u;
    v14 = a6 & 0xDFFFFFFF;
    a6 &= ~0x20000000u;
  }
  v19 = RtlpHpSegMgrCommitInitiate((_DWORD)a1, (_DWORD)v16, v7, v15, (__int64)&v34, (__int64)&v36);
  if ( v19 != -1073741568 )
  {
    if ( v19 == -1073741566 )
    {
      v31 = 0x200000;
      *(_QWORD *)&v32 = v17 & 0xFFFFFFFFFFE00000uLL;
      v20 = v14 | 0x20000000;
      if ( (int)v7 <= 0 )
        v20 = v14;
      v14 = v20;
      a6 = v20;
    }
    goto LABEL_21;
  }
  _InterlockedAdd64((volatile signed __int64 *)((char *)a1 + *((__int16 *)a1 + 10)), v7);
  if ( v30 )
    memset_0((void *)v17, 0, v18);
  return 0;
}

```

## disassembly

```asm
0x1400cbf34  push    rbp
0x1400cbf36  push    rbx
0x1400cbf37  push    rsi
0x1400cbf38  push    rdi
0x1400cbf39  push    r12
0x1400cbf3b  push    r13
0x1400cbf3d  push    r14
0x1400cbf3f  push    r15
0x1400cbf41  mov     rbp, rsp
0x1400cbf44  sub     rsp, 78h
0x1400cbf48  movsxd  rsi, [rbp+arg_20]
0x1400cbf4c  mov     r13d, r9d
0x1400cbf4f  mov     r12d, [rcx]
0x1400cbf52  mov     rdi, rdx
0x1400cbf55  mov     r15d, r8d
0x1400cbf58  mov     r14, rcx
0x1400cbf5b  mov     [rbp+var_28], 0
0x1400cbf63  mov     [rbp+arg_0], 0
0x1400cbf67  mov     [rbp+var_20], 0
0x1400cbf6f  test    esi, esi
0x1400cbf71  jle     short loc_1400CBF92
0x1400cbf73  mov     rdx, [r14+38h]
0x1400cbf77  mov     eax, esi
0x1400cbf79  shl     eax, 0Ch
0x1400cbf7c  movsxd  rcx, eax; __int64
0x1400cbf7f  call    RtlpHpSegHeapCheckCommitLimit
0x1400cbf84  test    eax, eax
0x1400cbf86  jnz     short loc_1400CBF92
0x1400cbf88  mov     ebx, 0C000012Dh
0x1400cbf8d  jmp     loc_1400CC1BF
0x1400cbf92  mov     ebx, [rbp+arg_28]
0x1400cbf95  mov     eax, ebx
0x1400cbf97  and     eax, 40000000h
0x1400cbf9c  mov     [rbp+var_48], eax
0x1400cbf9f  mov     al, [r14+0Dh]
0x1400cbfa3  and     al, 7
0x1400cbfa5  cmp     al, 1
0x1400cbfa7  jb      short loc_1400CC012
0x1400cbfa9  movups  xmm0, xmmword ptr [r14+28h]
0x1400cbfae  mov     rbx, rdi
0x1400cbfb1  lea     r8, [rbp+var_28]
0x1400cbfb5  and     rbx, 0FFFFFFFFFFE00000h
0x1400cbfbc  lea     rdx, [rbp+var_38]
0x1400cbfc0  mov     rcx, rbx
0x1400cbfc3  xor     r9d, r9d
0x1400cbfc6  movdqu  [rbp+var_38], xmm0
0x1400cbfcb  call    RtlpHpQueryVA
0x1400cbfd0  mov     rcx, [rbp+var_28]
0x1400cbfd4  test    esi, esi
0x1400cbfd6  jle     short loc_1400CBFFE
0x1400cbfd8  test    r15d, r15d
0x1400cbfdb  jnz     short loc_1400CBFFE
0x1400cbfdd  neg     r12d
0x1400cbfe0  cmp     r12d, 200000h
0x1400cbfe7  jnb     short loc_1400CBFFE
0x1400cbfe9  cmp     rdi, rbx
0x1400cbfec  jbe     short loc_1400CBFFE
0x1400cbfee  mov     r12d, [rbp+arg_30]
0x1400cbff2  test    r12b, 2
0x1400cbff6  jnz     short loc_1400CC002
0x1400cbff8  or      r12d, 1
0x1400cbffc  jmp     short loc_1400CC002
0x1400cbffe  mov     r12d, [rbp+arg_30]
0x1400cc002  mov     ebx, [rbp+arg_28]
0x1400cc005  mov     rax, r15
0x1400cc008  shr     rax, 9
0x1400cc00c  lea     r10, [rcx+rax*2]
0x1400cc010  jmp     short loc_1400CC019
0x1400cc012  mov     r12d, [rbp+arg_30]
0x1400cc016  xor     r10d, r10d
0x1400cc019  shl     r15d, 0Ch
0x1400cc01d  add     r15, rdi
0x1400cc020  mov     [rbp+var_28], r10
0x1400cc024  shl     r13d, 0Ch
0x1400cc028  mov     edi, r13d
0x1400cc02b  mov     qword ptr [rbp+var_38], r15
0x1400cc02f  mov     [rbp+var_40], rdi
0x1400cc033  test    r10, r10
0x1400cc036  jz      short loc_1400CC092
0x1400cc038  lea     rax, [rbp+arg_0]
0x1400cc03c  mov     r9d, r12d
0x1400cc03f  mov     [rsp+78h+var_50], rax
0x1400cc044  mov     r8d, esi
0x1400cc047  lea     rax, [rbp+var_20]
0x1400cc04b  mov     rdx, r10
0x1400cc04e  mov     rcx, r14
0x1400cc051  mov     [rsp+78h+var_58], rax
0x1400cc056  call    RtlpHpSegMgrCommitInitiate
0x1400cc05b  cmp     eax, 0C0000100h
0x1400cc060  jz      loc_1400CC19D
0x1400cc066  cmp     eax, 0C0000102h
0x1400cc06b  jnz     short loc_1400CC092
0x1400cc06d  mov     rax, r15
0x1400cc070  mov     [rbp+var_40], 200000h
0x1400cc078  and     rax, 0FFFFFFFFFFE00000h
0x1400cc07e  mov     qword ptr [rbp+var_38], rax
0x1400cc082  mov     eax, ebx
0x1400cc084  bts     eax, 1Dh
0x1400cc088  test    esi, esi
0x1400cc08a  cmovle  eax, ebx
0x1400cc08d  mov     ebx, eax
0x1400cc08f  mov     [rbp+arg_28], eax
0x1400cc092  lea     rdx, [rbp+var_40]
0x1400cc096  lea     rcx, [rbp+var_38]
0x1400cc09a  movups  xmm0, xmmword ptr [r14+28h]
0x1400cc09f  movdqu  [rbp+var_18], xmm0
0x1400cc0a4  test    esi, esi
0x1400cc0a6  jle     short loc_1400CC0BE
0x1400cc0a8  lea     rax, [rbp+var_18]
0x1400cc0ac  mov     r9d, ebx
0x1400cc0af  xor     r8d, r8d
0x1400cc0b2  mov     [rsp+78h+var_50], rax
0x1400cc0b7  call    RtlpHpAllocVA
0x1400cc0bc  jmp     short loc_1400CC0CA
0x1400cc0be  lea     r9, [rbp+var_18]
0x1400cc0c2  mov     r8d, ebx
0x1400cc0c5  call    RtlpHpFreeVA
0x1400cc0ca  mov     r10, [rbp+var_28]
0x1400cc0ce  mov     ebx, eax
0x1400cc0d0  test    r10, r10
0x1400cc0d3  jz      loc_1400CC1BF
0x1400cc0d9  movzx   eax, word ptr [r10]
0x1400cc0dd  bt      ax, 0Eh
0x1400cc0e2  jnb     short loc_1400CC10F
0x1400cc0e4  test    ebx, ebx
0x1400cc0e6  js      short loc_1400CC10F
0x1400cc0e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400cc0ec  mov     ecx, 1
0x1400cc0f1  test    esi, esi
0x1400cc0f3  cmovle  rcx, rax
0x1400cc0f7  movsx   rax, word ptr [r14+14h]
0x1400cc0fc  lock add [rax+r14+8], rcx
0x1400cc102  movsx   rax, word ptr [r14+14h]
0x1400cc107  mov     rcx, rsi
0x1400cc10a  lock add [rax+r14], rcx
0x1400cc10f  movzx   eax, word ptr [r10]
0x1400cc113  bt      ax, 0Eh
0x1400cc118  mov     word ptr [rbp+arg_20], ax
0x1400cc11c  movzx   ecx, word ptr [rbp+arg_20]
0x1400cc120  movzx   edx, ax
0x1400cc123  jnb     short loc_1400CC143
0x1400cc125  test    ebx, ebx
0x1400cc127  js      short loc_1400CC134
0x1400cc129  test    esi, esi
0x1400cc12b  jle     short loc_1400CC134
0x1400cc12d  mov     edx, 8000h
0x1400cc132  jmp     short loc_1400CC136
0x1400cc134  xor     edx, edx
0x1400cc136  mov     r8d, 3FFFh
0x1400cc13c  and     cx, r8w
0x1400cc140  or      cx, dx
0x1400cc143  test    esi, esi
0x1400cc145  jle     short loc_1400CC150
0x1400cc147  test    ebx, ebx
0x1400cc149  jns     short loc_1400CC153
0x1400cc14b  sub     cx, si
0x1400cc14e  jmp     short loc_1400CC153
0x1400cc150  add     cx, si
0x1400cc153  cmp     cx, ax
0x1400cc156  jz      short loc_1400CC177
0x1400cc158  movzx   edx, ax
0x1400cc15b  lock cmpxchg [r10], cx
0x1400cc161  jnz     short loc_1400CC113
0x1400cc163  bt      dx, 0Eh
0x1400cc168  jnb     short loc_1400CC177
0x1400cc16a  lea     rcx, [rbp+var_20]
0x1400cc16e  call    RtlpHpReleaseLockExclusive
0x1400cc173  mov     r10, [rbp+var_28]
0x1400cc177  test    [rbp+arg_28], 20000000h
0x1400cc17e  jz      short loc_1400CC1BF
0x1400cc180  test    ebx, ebx
0x1400cc182  jns     short loc_1400CC1BF
0x1400cc184  test    r12b, 2
0x1400cc188  jnz     short loc_1400CC1BF
0x1400cc18a  mov     ebx, [rbp+arg_28]
0x1400cc18d  or      r12d, 1
0x1400cc191  btr     ebx, 1Dh
0x1400cc195  mov     [rbp+arg_28], ebx
0x1400cc198  jmp     loc_1400CC02B
0x1400cc19d  movsx   rax, word ptr [r14+14h]
0x1400cc1a2  mov     rdx, rsi
0x1400cc1a5  lock add [rax+r14], rdx
0x1400cc1aa  cmp     [rbp+var_48], 0
0x1400cc1ae  jz      short loc_1400CC1BD
0x1400cc1b0  mov     r8, rdi; Size
0x1400cc1b3  xor     edx, edx; Val
0x1400cc1b5  mov     rcx, r15; void *
0x1400cc1b8  call    memset_0
0x1400cc1bd  xor     ebx, ebx
0x1400cc1bf  mov     eax, ebx
0x1400cc1c1  add     rsp, 78h
0x1400cc1c5  pop     r15
0x1400cc1c7  pop     r14
0x1400cc1c9  pop     r13
0x1400cc1cb  pop     r12
0x1400cc1cd  pop     rdi
0x1400cc1ce  pop     rsi
0x1400cc1cf  pop     rbx
0x1400cc1d0  pop     rbp
0x1400cc1d1  retn
```
