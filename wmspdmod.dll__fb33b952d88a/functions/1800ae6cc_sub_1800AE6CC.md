# sub_1800AE6CC

- ea: `0x1800ae6cc`
- end: `0x1800ae84c`
- name: `sub_1800AE6CC`
- size: `384`
- prototype: `double __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x180085fa4`
- `0x180088120`
- `0x1800888c8`
- `0x180088a04`
- `0x18008942c`
- `0x18009df18`
- `0x18009e7c8`
- `0x1800b1ae4`
- `0x1800b77a8`
- `0x1800b96b0`
- `0x1800bb5d0`
- `0x1800c57c4`

## callees

- `0x180001330`
- `0x180001fc0`
- `0x1800ae6cc`
- `0x1800ae854`

## pseudocode

```c
__int64 __fastcall sub_1800AE6CC(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // r15
  int i; // esi
  __int64 result; // rax
  int v8; // ecx
  __int64 v9; // rax
  float v10; // xmm1_4
  int v11; // ecx
  float v12; // xmm1_4
  float v13[8]; // [rsp+20h] [rbp-69h] BYREF
  float v14[8]; // [rsp+40h] [rbp-49h] BYREF
  float v15[8]; // [rsp+60h] [rbp-29h] BYREF
  float v16[8]; // [rsp+80h] [rbp-9h] BYREF

  if ( (a3 & 1) == 0 )
  {
    v4 = 0;
    for ( i = a3 / 2; (int)v4 < i; v4 = (unsigned int)(v4 + 1) )
    {
      v14[v4] = o_cosf();
      v13[v4] = o_cosf();
    }
    sub_1800AE854(v14, v15, (unsigned int)i);
    result = sub_1800AE854(v13, v16, (unsigned int)i);
    v8 = 1;
    v13[0] = v16[0] - 1.0;
    v14[0] = v15[0] + 1.0;
    if ( i <= 1 )
    {
      v11 = 0;
      if ( i <= 0 )
        return result;
    }
    else
    {
      do
      {
        v9 = (unsigned int)v8++;
        v10 = v16[v9] - v15[v9 + 7];
        v14[v9] = v14[v9 + 7] + v15[v9];
        v13[v9] = v10;
      }
      while ( v8 < i );
      v11 = 0;
    }
    do
    {
      v12 = (float)(v14[v11] - v13[v11]) * 0.5;
      *(float *)(a2 + 4LL * v11) = (float)(v14[v11] + v13[v11]) * 0.5;
      LODWORD(result) = a3 - v11++;
      result = (int)result;
      *(float *)(a2 + 4LL * (int)result - 4) = v12;
    }
    while ( v11 < i );
  }
  return result;
}

```

## disassembly

```asm
0x1800ae6cc  test    r8b, 1
0x1800ae6d0  jnz     locret_1800AE84A
0x1800ae6d6  mov     [rsp-8+arg_0], rbx
0x1800ae6db  push    rbp
0x1800ae6dc  push    rsi
0x1800ae6dd  push    rdi
0x1800ae6de  push    r12
0x1800ae6e0  push    r13
0x1800ae6e2  push    r14
0x1800ae6e4  push    r15
0x1800ae6e6  lea     rbp, [rsp-27h]
0x1800ae6eb  sub     rsp, 0B0h
0x1800ae6f2  mov     rax, cs:__security_cookie
0x1800ae6f9  xor     rax, rsp
0x1800ae6fc  mov     [rbp+57h+var_40], rax
0x1800ae700  mov     eax, r8d
0x1800ae703  mov     r13, rdx
0x1800ae706  cdq
0x1800ae707  xor     r15d, r15d
0x1800ae70a  sub     eax, edx
0x1800ae70c  mov     r14d, r8d
0x1800ae70f  sar     eax, 1
0x1800ae711  mov     r12, rcx
0x1800ae714  mov     esi, eax
0x1800ae716  test    eax, eax
0x1800ae718  jle     short loc_1800AE75E
0x1800ae71a  lea     eax, [r15+r15]
0x1800ae71e  movsxd  rbx, eax
0x1800ae721  movss   xmm0, dword ptr [r12+rbx*4]
0x1800ae727  mulss   xmm0, cs:dword_1800E3774
0x1800ae72f  call    _o_cosf
0x1800ae734  movss   [rbp+r15*4+57h+var_A0], xmm0
0x1800ae73b  movss   xmm0, dword ptr [r12+rbx*4+4]
0x1800ae742  mulss   xmm0, cs:dword_1800E3774
0x1800ae74a  call    _o_cosf
0x1800ae74f  movss   [rbp+r15*4+57h+var_C0], xmm0
0x1800ae756  inc     r15d
0x1800ae759  cmp     r15d, esi
0x1800ae75c  jl      short loc_1800AE71A
0x1800ae75e  mov     r8d, esi
0x1800ae761  lea     rdx, [rbp+57h+var_80]
0x1800ae765  lea     rcx, [rbp+57h+var_A0]
0x1800ae769  call    sub_1800AE854
0x1800ae76e  mov     r8d, esi
0x1800ae771  lea     rcx, [rbp+57h+var_C0]
0x1800ae775  lea     rdx, [rbp+57h+var_60]
0x1800ae779  call    sub_1800AE854
0x1800ae77e  movss   xmm0, [rbp+57h+var_60]
0x1800ae783  mov     ecx, 1
0x1800ae788  movss   xmm5, [rbp+57h+var_80]
0x1800ae78d  subss   xmm0, cs:dword_1800E36C4
0x1800ae795  addss   xmm5, cs:dword_1800E36C4
0x1800ae79d  movss   [rbp+57h+var_C0], xmm0
0x1800ae7a2  movss   [rbp+57h+var_A0], xmm5
0x1800ae7a7  cmp     esi, ecx
0x1800ae7a9  jle     short loc_1800AE7DB
0x1800ae7ab  mov     eax, ecx
0x1800ae7ad  inc     ecx
0x1800ae7af  movss   xmm0, [rbp+rax*4+57h+var_84]
0x1800ae7b5  movss   xmm1, [rbp+rax*4+57h+var_60]
0x1800ae7bb  addss   xmm0, [rbp+rax*4+57h+var_80]
0x1800ae7c1  subss   xmm1, [rbp+rax*4+57h+var_64]
0x1800ae7c7  movss   [rbp+rax*4+57h+var_A0], xmm0
0x1800ae7cd  movss   [rbp+rax*4+57h+var_C0], xmm1
0x1800ae7d3  cmp     ecx, esi
0x1800ae7d5  jl      short loc_1800AE7AB
0x1800ae7d7  xor     ecx, ecx
0x1800ae7d9  jmp     short loc_1800AE7E1
0x1800ae7db  xor     ecx, ecx
0x1800ae7dd  test    esi, esi
0x1800ae7df  jle     short loc_1800AE824
0x1800ae7e1  movss   xmm2, cs:dword_1800E3674
0x1800ae7e9  movsxd  rax, ecx
0x1800ae7ec  movss   xmm1, [rbp+rax*4+57h+var_A0]
0x1800ae7f2  movaps  xmm0, xmm1
0x1800ae7f5  addss   xmm0, [rbp+rax*4+57h+var_C0]
0x1800ae7fb  subss   xmm1, [rbp+rax*4+57h+var_C0]
0x1800ae801  mulss   xmm0, xmm2
0x1800ae805  mulss   xmm1, xmm2
0x1800ae809  movss   dword ptr [r13+rax*4+0], xmm0
0x1800ae810  mov     eax, r14d
0x1800ae813  sub     eax, ecx
0x1800ae815  inc     ecx
0x1800ae817  cdqe
0x1800ae819  movss   dword ptr [r13+rax*4-4], xmm1
0x1800ae820  cmp     ecx, esi
0x1800ae822  jl      short loc_1800AE7E9
0x1800ae824  mov     rcx, [rbp+57h+var_40]
0x1800ae828  xor     rcx, rsp; StackCookie
0x1800ae82b  call    __security_check_cookie
0x1800ae830  mov     rbx, [rsp+0E0h+arg_0]
0x1800ae838  add     rsp, 0B0h
0x1800ae83f  pop     r15
0x1800ae841  pop     r14
0x1800ae843  pop     r13
0x1800ae845  pop     r12
0x1800ae847  pop     rdi
0x1800ae848  pop     rsi
0x1800ae849  pop     rbp
0x1800ae84a  retn
```
