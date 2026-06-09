# std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>::_Emplace_reallocate<winrt::com_ptr<IStream> const &>(winrt::com_ptr<IStream> * const,winrt::com_ptr<IStream> const &)

- ea: `0x18000e22c`
- end: `0x18000e474`
- name: `??$_Emplace_reallocate@AEBU?$com_ptr@UIStream@@@winrt@@@?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@AEAAPEAU?$com_ptr@UIStream@@@winrt@@QEAU23@AEBU23@@Z`
- size: `584`
- prototype: `char *__fastcall(char **, char *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800137e8`

## callees

- `0x180001e90`
- `0x1800022a4`
- `0x18000c5ac`
- `0x18000e22c`
- `0x180010464`
- `0x180015130`
- `0x180018f38`
- `0x18001b010`

## pseudocode

```c
char *__fastcall std::vector<winrt::com_ptr<IStream>>::_Emplace_reallocate<winrt::com_ptr<IStream> const &>(
        char **a1,
        char *a2,
        __int64 *a3)
{
  char *v6; // r12
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  _QWORD *v9; // r8
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // r15
  _QWORD *v12; // rdi
  void *v13; // rax
  __int64 v14; // r14
  __int64 *v15; // r12
  __int64 v16; // rcx
  char *v17; // rdx
  char *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r14
  _QWORD *v21; // rdx
  __int64 v22; // rax
  _QWORD *v23; // rcx
  __int64 v24; // rax
  char *v25; // rsi
  char *v26; // rbp
  char *v27; // rcx
  char *v28; // rax
  _QWORD v30[3]; // [rsp+20h] [rbp-78h] BYREF
  char *v31; // [rsp+38h] [rbp-60h]
  _QWORD *v32; // [rsp+40h] [rbp-58h]
  __int64 v33; // [rsp+A0h] [rbp+8h]

  v6 = *a1;
  v7 = (a1[1] - *a1) >> 3;
  if ( v7 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<winrt::com_ptr<IStream>>::_Xlength();
  v8 = (a1[2] - v6) >> 3;
  v9 = (_QWORD *)(v8 >> 1);
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_39;
  v33 = v7 + 1;
  v10 = v7 + 1;
  if ( (unsigned __int64)v9 + v8 >= v7 + 1 )
    v10 = (unsigned __int64)v9 + v8;
  if ( v10 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_39;
  v11 = 8 * v10;
  if ( !(8 * v10) )
  {
    v12 = 0;
    goto LABEL_13;
  }
  if ( v11 < 0x1000 )
  {
    v12 = operator new(8 * v10);
    goto LABEL_13;
  }
  if ( v11 + 39 < v11 )
LABEL_39:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  if ( !v13 )
    goto LABEL_34;
  v12 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v13;
LABEL_13:
  v14 = (a2 - v6) >> 3;
  v15 = &v12[v14];
  v30[0] = a1;
  v30[2] = v10;
  v32 = v15 + 1;
  v16 = *a3;
  *v15 = *a3;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  v31 = (char *)&v12[v14];
  v17 = a1[1];
  v18 = *a1;
  if ( a2 == v17 )
  {
    v9 = v12;
    while ( v18 != v17 )
    {
      v19 = *(_QWORD *)v18;
      *(_QWORD *)v18 = 0;
      *v9++ = v19;
      v18 += 8;
    }
    v20 = v14;
  }
  else
  {
    v21 = v12;
    while ( v18 != a2 )
    {
      v22 = *(_QWORD *)v18;
      *(_QWORD *)v18 = 0;
      *v21++ = v22;
      v18 += 8;
    }
    v31 = (char *)v12;
    v20 = v14;
    v17 = a1[1];
    v23 = &v12[v20 + 1];
    while ( a2 != v17 )
    {
      v24 = *(_QWORD *)a2;
      *(_QWORD *)a2 = 0;
      *v23++ = v24;
      a2 += 8;
    }
  }
  v30[1] = 0;
  v25 = *a1;
  if ( *a1 )
  {
    v26 = a1[1];
    while ( v25 != v26 )
    {
      if ( *(_QWORD *)v25 )
        winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(v25);
      v25 += 8;
    }
    v27 = *a1;
    if ( (unsigned __int64)(8 * ((a1[2] - *a1) >> 3)) < 0x1000 )
    {
      v28 = *a1;
    }
    else
    {
      v28 = (char *)*((_QWORD *)v27 - 1);
      if ( (unsigned __int64)(v27 - v28 - 8) > 0x1F )
LABEL_34:
        __fastfail(5u);
    }
    operator delete(v28);
  }
  *a1 = (char *)v12;
  a1[1] = (char *)&v12[v33];
  a1[2] = (char *)&v12[v11 / 8];
  std::vector<winrt::com_ptr<IStream>>::_Reallocation_guard::~_Reallocation_guard(v30, v17, v9);
  return (char *)&v12[v20];
}

```

## disassembly

```asm
0x18000e22c  push    rbx
0x18000e22e  push    rbp
0x18000e22f  push    rsi
0x18000e230  push    rdi
0x18000e231  push    r12
0x18000e233  push    r13
0x18000e235  push    r14
0x18000e237  push    r15
0x18000e239  sub     rsp, 58h
0x18000e23d  mov     r13, r8
0x18000e240  mov     rsi, rdx
0x18000e243  mov     rbx, rcx
0x18000e246  mov     r12, [rcx]
0x18000e249  mov     rdx, [rcx+8]
0x18000e24d  sub     rdx, r12
0x18000e250  sar     rdx, 3
0x18000e254  mov     r9, 1FFFFFFFFFFFFFFFh
0x18000e25e  cmp     rdx, r9
0x18000e261  jz      loc_18000E468
0x18000e267  mov     rcx, [rcx+10h]
0x18000e26b  sub     rcx, r12
0x18000e26e  sar     rcx, 3
0x18000e272  mov     r8, rcx
0x18000e275  shr     r8, 1
0x18000e278  mov     rax, r9
0x18000e27b  sub     rax, r8
0x18000e27e  cmp     rcx, rax
0x18000e281  ja      loc_18000E46E
0x18000e287  inc     rdx
0x18000e28a  mov     [rsp+98h+arg_0], rdx
0x18000e292  lea     rax, [rcx+r8]
0x18000e296  mov     rbp, rdx
0x18000e299  cmp     rax, rdx
0x18000e29c  cmovnb  rbp, rax
0x18000e2a0  cmp     rbp, r9
0x18000e2a3  ja      loc_18000E46E
0x18000e2a9  lea     r15, ds:0[rbp*8]
0x18000e2b1  test    r15, r15
0x18000e2b4  jnz     short loc_18000E2BA
0x18000e2b6  xor     edi, edi
0x18000e2b8  jmp     short loc_18000E2F7
0x18000e2ba  cmp     r15, 1000h
0x18000e2c1  jb      short loc_18000E2EC
0x18000e2c3  lea     rcx, [r15+27h]; Size
0x18000e2c7  cmp     rcx, r15
0x18000e2ca  jbe     loc_18000E46E
0x18000e2d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e2d5  test    rax, rax
0x18000e2d8  jz      loc_18000E41C
0x18000e2de  lea     rdi, [rax+27h]
0x18000e2e2  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000e2e6  mov     [rdi-8], rax
0x18000e2ea  jmp     short loc_18000E2F7
0x18000e2ec  mov     rcx, r15; Size
0x18000e2ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e2f4  mov     rdi, rax
0x18000e2f7  mov     r14, rsi
0x18000e2fa  sub     r14, r12
0x18000e2fd  sar     r14, 3
0x18000e301  lea     r12, [rdi+r14*8]
0x18000e305  mov     [rsp+98h+var_78], rbx
0x18000e30a  mov     [rsp+98h+var_68], rbp
0x18000e30f  lea     rcx, [r12+8]
0x18000e314  mov     [rsp+98h+var_58], rcx
0x18000e319  mov     rcx, [r13+0]
0x18000e31d  mov     [r12], rcx
0x18000e321  test    rcx, rcx
0x18000e324  jz      short loc_18000E333
0x18000e326  mov     rax, [rcx]
0x18000e329  mov     rax, [rax+8]
0x18000e32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e332  nop
0x18000e333  mov     [rsp+98h+var_60], r12
0x18000e338  mov     rdx, [rbx+8]
0x18000e33c  mov     rcx, [rbx]
0x18000e33f  cmp     rsi, rdx
0x18000e342  jnz     short loc_18000E369
0x18000e344  mov     r8, rdi
0x18000e347  jmp     short loc_18000E35E
0x18000e349  mov     rax, [rcx]
0x18000e34c  mov     qword ptr [rcx], 0
0x18000e353  mov     [r8], rax
0x18000e356  lea     r8, [r8+8]
0x18000e35a  add     rcx, 8
0x18000e35e  cmp     rcx, rdx
0x18000e361  jnz     short loc_18000E349
0x18000e363  shl     r14, 3
0x18000e367  jmp     short loc_18000E3B8
0x18000e369  mov     rdx, rdi
0x18000e36c  jmp     short loc_18000E383
0x18000e36e  mov     rax, [rcx]
0x18000e371  mov     qword ptr [rcx], 0
0x18000e378  mov     [rdx], rax
0x18000e37b  lea     rdx, [rdx+8]
0x18000e37f  add     rcx, 8
0x18000e383  cmp     rcx, rsi
0x18000e386  jnz     short loc_18000E36E
0x18000e388  mov     [rsp+98h+var_60], rdi
0x18000e38d  shl     r14, 3
0x18000e391  mov     rdx, [rbx+8]
0x18000e395  lea     rcx, [r14+8]
0x18000e399  add     rcx, rdi
0x18000e39c  jmp     short loc_18000E3B3
0x18000e39e  mov     rax, [rsi]
0x18000e3a1  mov     qword ptr [rsi], 0
0x18000e3a8  mov     [rcx], rax
0x18000e3ab  lea     rcx, [rcx+8]
0x18000e3af  add     rsi, 8
0x18000e3b3  cmp     rsi, rdx
0x18000e3b6  jnz     short loc_18000E39E
0x18000e3b8  mov     [rsp+98h+var_70], 0
0x18000e3c1  mov     rsi, [rbx]
0x18000e3c4  test    rsi, rsi
0x18000e3c7  jz      short loc_18000E42E
0x18000e3c9  mov     rbp, [rbx+8]
0x18000e3cd  jmp     short loc_18000E3E1
0x18000e3cf  cmp     qword ptr [rsi], 0
0x18000e3d3  jz      short loc_18000E3DD
0x18000e3d5  mov     rcx, rsi
0x18000e3d8  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x18000e3dd  add     rsi, 8
0x18000e3e1  cmp     rsi, rbp
0x18000e3e4  jnz     short loc_18000E3CF
0x18000e3e6  mov     rcx, [rbx]
0x18000e3e9  mov     rax, [rbx+10h]
0x18000e3ed  sub     rax, rcx
0x18000e3f0  sar     rax, 3
0x18000e3f4  lea     rdx, ds:0[rax*8]
0x18000e3fc  cmp     rdx, 1000h
0x18000e403  jb      short loc_18000E423
0x18000e405  mov     rax, [rcx-8]
0x18000e409  sub     rcx, rax
0x18000e40c  sub     rcx, 8
0x18000e410  cmp     rcx, 1Fh
0x18000e414  ja      short loc_18000E41C
0x18000e416  add     rdx, 27h ; '''
0x18000e41a  jmp     short loc_18000E426
0x18000e41c  mov     ecx, 5
0x18000e421  int     29h; Win8: RtlFailFast(ecx)
0x18000e423  mov     rax, rcx
0x18000e426  mov     rcx, rax; Block
0x18000e429  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e42e  mov     [rbx], rdi
0x18000e431  mov     rax, [rsp+98h+arg_0]
0x18000e439  lea     rax, [rdi+rax*8]
0x18000e43d  mov     [rbx+8], rax
0x18000e441  lea     rax, [r15+rdi]
0x18000e445  mov     [rbx+10h], rax
0x18000e449  lea     rcx, [rsp+98h+var_78]
0x18000e44e  call    ??1_Reallocation_guard@?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::com_ptr<IStream>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000e453  lea     rax, [r14+rdi]
0x18000e457  add     rsp, 58h
0x18000e45b  pop     r15
0x18000e45d  pop     r14
0x18000e45f  pop     r13
0x18000e461  pop     r12
0x18000e463  pop     rdi
0x18000e464  pop     rsi
0x18000e465  pop     rbp
0x18000e466  pop     rbx
0x18000e467  retn
0x18000e468  call    ?_Xlength@?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@CAXXZ; std::vector<winrt::com_ptr<IStream>>::_Xlength(void)
0x18000e46e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
