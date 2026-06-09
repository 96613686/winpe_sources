# VsmmHvpControlGpaAccessTrackingQueryHv

- ea: `0x1400d1a24`
- end: `0x1400d1c60`
- name: `VsmmHvpControlGpaAccessTrackingQueryHv`
- size: `572`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned __int64, __int64, _QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400d13a8`

## callees

- `0x140021650`
- `0x140021800`
- `0x14002f524`
- `0x140078f20`
- `0x1400d1a24`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400d1bb1`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400d1bb1`
- `winhvr!WinHvGetGpaRangesAccessState` at `0x1400d1b0f`
- `winhvr!WinHvGetGpaRangesAccessState` at `0x1400d1b0f`

## string_xrefs

- `0x1400d1b31`: `VsmmHvpControlGpaAccessTrackingQueryHv`
- `0x1400d1bed`: `VsmmHvpControlGpaAccessTrackingQueryHv`

## pseudocode

```c
__int64 __fastcall VsmmHvpControlGpaAccessTrackingQueryHv(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int64 a4,
        __int64 a5,
        _QWORD *a6,
        unsigned int a7)
{
  __int64 v8; // r10
  _QWORD *v9; // r15
  char *v10; // r12
  unsigned __int8 v11; // di
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r14
  int GpaRangesAccessState; // esi
  __int64 v15; // rcx
  __int64 v16; // r15
  unsigned __int64 v17; // rsi
  unsigned int v19; // [rsp+44h] [rbp-2C4h]
  __int64 v20; // [rsp+48h] [rbp-2C0h]
  __int64 v21; // [rsp+50h] [rbp-2B8h]
  __int64 v22; // [rsp+58h] [rbp-2B0h] BYREF
  _QWORD *v23; // [rsp+60h] [rbp-2A8h]
  __int64 v24; // [rsp+68h] [rbp-2A0h]
  char *v25; // [rsp+70h] [rbp-298h]
  signed __int64 Src[8]; // [rsp+80h] [rbp-288h] BYREF
  _BYTE v27[512]; // [rsp+C0h] [rbp-248h] BYREF

  v19 = a3;
  v21 = a2;
  v8 = a1;
  v24 = a1;
  v9 = a6;
  v23 = a6;
  v22 = 0;
  v10 = *(char **)(a5 + 8);
  v20 = 0;
  v11 = 0;
  if ( (a7 & 2) != 0 )
    v11 = ((a7 & 1) != 0) + 1;
  if ( a3 )
  {
    v12 = 0;
    if ( (a7 & 4) != 0 )
      v12 = 5;
  }
  else if ( (a7 & 1) != 0 )
  {
    v12 = a7 & 0xC;
  }
  else
  {
    v12 = ((unsigned __int64)a7 >> 2) & 3;
  }
  while ( a4 )
  {
    v13 = a4;
    if ( a4 > 0x200 )
      v13 = 512;
    GpaRangesAccessState = WinHvGetGpaRangesAccessState(*(_QWORD *)(v8 + 648), v12, a2, a3, v13, v27, &v22);
    if ( GpaRangesAccessState < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmHvpControlGpaAccessTrackingQueryHv",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmhv.c",
        2345);
      return (unsigned int)GpaRangesAccessState;
    }
    if ( (a7 & 2) != 0 )
    {
      memset(Src, 0, sizeof(Src));
      v15 = 0;
      v16 = v20;
      do
      {
        if ( (v11 & v27[v15]) != 0 )
        {
          _bittestandset64(Src, (unsigned int)v15);
          ++v16;
        }
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < v13 );
      v20 = v16;
      v9 = v23;
      v17 = 8 * ((v13 + 63) >> 6);
      if ( v17 && ((unsigned __int8)v10 & 7) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyToUser(v10, Src, 8 * ((v13 + 63) >> 6));
      v10 += v17;
      v25 = v10;
    }
    a3 = v19;
    a2 = (v13 << (9 * (unsigned __int8)v19)) + v21;
    v21 = a2;
    a4 -= v13;
    v8 = v24;
  }
  if ( (a7 & 2) != 0 && v9 )
    *v9 += v20;
  return 0;
}

```

## disassembly

```asm
0x1400d1a24  push    rbx
0x1400d1a26  push    rsi
0x1400d1a27  push    rdi
0x1400d1a28  push    r12
0x1400d1a2a  push    r13
0x1400d1a2c  push    r14
0x1400d1a2e  push    r15
0x1400d1a30  sub     rsp, 2D0h
0x1400d1a37  mov     rax, cs:__security_cookie
0x1400d1a3e  xor     rax, rsp
0x1400d1a41  mov     [rsp+308h+var_48], rax
0x1400d1a49  mov     r13, r9
0x1400d1a4c  mov     [rsp+308h+var_2C4], r8d
0x1400d1a51  mov     [rsp+308h+var_2B8], rdx
0x1400d1a56  mov     r10, rcx
0x1400d1a59  mov     [rsp+308h+var_2A0], rcx
0x1400d1a5e  mov     rax, [rsp+308h+arg_20]
0x1400d1a66  mov     r15, [rsp+308h+arg_28]
0x1400d1a6e  mov     [rsp+308h+var_2A8], r15
0x1400d1a73  mov     [rsp+308h+var_2B0], 0
0x1400d1a7c  mov     r12, [rax+8]
0x1400d1a80  mov     [rsp+308h+var_2C0], 0
0x1400d1a89  xor     dil, dil
0x1400d1a8c  mov     eax, [rsp+308h+arg_30]
0x1400d1a93  mov     ecx, eax
0x1400d1a95  and     ecx, 2
0x1400d1a98  mov     [rsp+308h+var_2C8], ecx
0x1400d1a9c  jz      short loc_1400D1AA7
0x1400d1a9e  test    al, 1
0x1400d1aa0  setnz   dil
0x1400d1aa4  inc     dil
0x1400d1aa7  test    r8d, r8d
0x1400d1aaa  jnz     short loc_1400D1AC1
0x1400d1aac  mov     rbx, rax
0x1400d1aaf  test    al, 1
0x1400d1ab1  jnz     short loc_1400D1ABC
0x1400d1ab3  shr     rbx, 2
0x1400d1ab7  and     ebx, 3
0x1400d1aba  jmp     short loc_1400D1ACB
0x1400d1abc  and     ebx, 0Ch
0x1400d1abf  jmp     short loc_1400D1ACB
0x1400d1ac1  xor     ebx, ebx
0x1400d1ac3  test    al, 4
0x1400d1ac5  lea     eax, [rbx+5]
0x1400d1ac8  cmovnz  ebx, eax
0x1400d1acb  mov     eax, 200h
0x1400d1ad0  test    r13, r13
0x1400d1ad3  jz      loc_1400D1C24
0x1400d1ad9  mov     r14, r13
0x1400d1adc  cmp     r13, rax
0x1400d1adf  cmova   r14, rax
0x1400d1ae3  lea     rax, [rsp+308h+var_2B0]
0x1400d1ae8  mov     [rsp+308h+var_2D8], rax
0x1400d1aed  lea     rax, [rsp+308h+var_248]
0x1400d1af5  mov     [rsp+308h+var_2E0], rax
0x1400d1afa  mov     [rsp+308h+var_2E8], r14
0x1400d1aff  mov     r9d, r8d
0x1400d1b02  mov     r8, rdx
0x1400d1b05  mov     rdx, rbx
0x1400d1b08  mov     rcx, [r10+288h]
0x1400d1b0f  call    cs:__imp_WinHvGetGpaRangesAccessState
0x1400d1b16  nop     dword ptr [rax+rax+00h]
0x1400d1b1b  mov     esi, eax
0x1400d1b1d  test    eax, eax
0x1400d1b1f  jns     short loc_1400D1B42
0x1400d1b21  mov     r9d, eax
0x1400d1b24  mov     r8d, 929h
0x1400d1b2a  lea     rdx, aOnecoreVmVidSy_37; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhv.c"
0x1400d1b31  lea     rcx, aVsmmhvpcontrol; "VsmmHvpControlGpaAccessTrackingQueryHv"
0x1400d1b38  call    VidTraceErrorStatusInternal0
0x1400d1b3d  jmp     loc_1400D1C3A
0x1400d1b42  cmp     [rsp+308h+var_2C8], 0
0x1400d1b47  jz      loc_1400D1BFB
0x1400d1b4d  xor     edx, edx; Val
0x1400d1b4f  lea     r8d, [rdx+40h]; Size
0x1400d1b53  lea     rcx, [rsp+308h+Src]; void *
0x1400d1b5b  call    memset
0x1400d1b60  xor     ecx, ecx
0x1400d1b62  test    r14, r14
0x1400d1b65  jz      short loc_1400D1B9A
0x1400d1b67  mov     r15, [rsp+308h+var_2C0]
0x1400d1b6c  mov     edx, ecx
0x1400d1b6e  test    [rsp+rcx+308h+var_248], dil
0x1400d1b76  jz      short loc_1400D1B87
0x1400d1b78  lea     rax, [rsp+308h+Src]
0x1400d1b80  bts     [rax], rdx
0x1400d1b84  inc     r15
0x1400d1b87  inc     ecx
0x1400d1b89  mov     eax, ecx
0x1400d1b8b  cmp     rax, r14
0x1400d1b8e  jb      short loc_1400D1B6C
0x1400d1b90  mov     [rsp+308h+var_2C0], r15
0x1400d1b95  mov     r15, [rsp+308h+var_2A8]
0x1400d1b9a  lea     rsi, [r14+3Fh]
0x1400d1b9e  shr     rsi, 6
0x1400d1ba2  shl     rsi, 3
0x1400d1ba6  test    rsi, rsi
0x1400d1ba9  jz      short loc_1400D1BBE
0x1400d1bab  test    r12b, 7
0x1400d1baf  jz      short loc_1400D1BBE
0x1400d1bb1  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400d1bb8  nop     dword ptr [rax+rax+00h]
0x1400d1bbd  int     3; Trap to Debugger
0x1400d1bbe  mov     r8, rsi; Size
0x1400d1bc1  lea     rdx, [rsp+308h+Src]; Src
0x1400d1bc9  mov     rcx, r12; void *
0x1400d1bcc  call    RtlCopyToUser
0x1400d1bd1  add     r12, rsi
0x1400d1bd4  mov     [rsp+308h+var_298], r12
0x1400d1bd9  jmp     short loc_1400D1BFB
0x1400d1bdb  mov     esi, eax
0x1400d1bdd  mov     r9d, eax
0x1400d1be0  mov     r8d, 94Bh
0x1400d1be6  lea     rdx, aOnecoreVmVidSy_37; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhv.c"
0x1400d1bed  lea     rcx, aVsmmhvpcontrol; "VsmmHvpControlGpaAccessTrackingQueryHv"
0x1400d1bf4  call    VidTraceErrorStatusInternal0
0x1400d1bf9  jmp     short loc_1400D1C3A
0x1400d1bfb  mov     r8d, [rsp+308h+var_2C4]
0x1400d1c00  lea     ecx, [r8+r8*8]
0x1400d1c04  mov     rax, r14
0x1400d1c07  shl     rax, cl
0x1400d1c0a  mov     rdx, [rsp+308h+var_2B8]
0x1400d1c0f  add     rdx, rax
0x1400d1c12  mov     [rsp+308h+var_2B8], rdx
0x1400d1c17  sub     r13, r14
0x1400d1c1a  mov     r10, [rsp+308h+var_2A0]
0x1400d1c1f  jmp     loc_1400D1ACB
0x1400d1c24  cmp     [rsp+308h+var_2C8], 0
0x1400d1c29  jz      short loc_1400D1C38
0x1400d1c2b  test    r15, r15
0x1400d1c2e  jz      short loc_1400D1C38
0x1400d1c30  mov     rax, [rsp+308h+var_2C0]
0x1400d1c35  add     [r15], rax
0x1400d1c38  xor     esi, esi
0x1400d1c3a  mov     eax, esi
0x1400d1c3c  mov     rcx, [rsp+308h+var_48]
0x1400d1c44  xor     rcx, rsp; StackCookie
0x1400d1c47  call    __security_check_cookie
0x1400d1c4c  add     rsp, 2D0h
0x1400d1c53  pop     r15
0x1400d1c55  pop     r14
0x1400d1c57  pop     r13
0x1400d1c59  pop     r12
0x1400d1c5b  pop     rdi
0x1400d1c5c  pop     rsi
0x1400d1c5d  pop     rbx
0x1400d1c5e  retn
```
