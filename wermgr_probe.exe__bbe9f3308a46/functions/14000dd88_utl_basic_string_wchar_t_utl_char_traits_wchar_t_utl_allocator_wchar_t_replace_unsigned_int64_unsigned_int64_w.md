# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x14000dd88`
- end: `0x14000e018`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000b70c`

## callees

- `0x140003224`
- `0x14000d7d8`
- `0x14000d87c`
- `0x14000dd88`
- `0x14001c9a8`
- `0x14001c9b4`

## pseudocode

```c
char __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
        char **a1,
        __int64 a2,
        unsigned __int64 a3,
        __int16 *a4,
        unsigned __int64 a5)
{
  char *v5; // r13
  unsigned __int64 v8; // r8
  unsigned __int64 v10; // r12
  char v11; // r15
  char *v13; // r10
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  char *v16; // r11
  _WORD *v17; // rdi
  unsigned __int64 v18; // rdx
  _WORD *v19; // rcx
  char v20; // al
  __int16 v21; // ax
  __int64 v22; // r12
  char *v23; // rdi
  void *v24; // r14
  void *v25[2]; // [rsp+20h] [rbp-30h] BYREF
  _WORD *v26; // [rsp+30h] [rbp-20h] BYREF
  _WORD *v27; // [rsp+38h] [rbp-18h]
  _WORD v28[8]; // [rsp+40h] [rbp-10h] BYREF
  char *v29; // [rsp+90h] [rbp+40h]
  char *Src; // [rsp+98h] [rbp+48h]

  v5 = *a1;
  v8 = (unsigned __int64)a1[1];
  if ( (__int64)(v8 - (_QWORD)*a1) >> 1 < a3 )
    a3 = (a1[1] - *a1) >> 1;
  v10 = v8 + 2 * (a5 - a3);
  if ( v10 < (unsigned __int64)v5 )
    return 0;
  v11 = 1;
  v13 = &v5[2 * a3];
  Src = v13;
  if ( v5 == (char *)(a1 + 2) )
    v14 = (unsigned __int64)a1 + 30;
  else
    v14 = (unsigned __int64)a1[2];
  if ( v10 <= v14 )
  {
    v15 = 2 * a5;
    v16 = (char *)&a4[a5];
    v29 = v16;
    if ( v16 <= v5 || v8 < (unsigned __int64)a4 )
    {
      memmove_0(&v5[2 * a5], &v5[2 * a3], 2 * ((__int64)(v8 - (_QWORD)v13) >> 1) + 2);
      memcpy_0(v5, a4, 2 * a5);
      goto LABEL_29;
    }
    if ( a5 <= a3 )
    {
      memmove_0(v5, a4, 2 * a5);
      memmove_0(&v5[2 * a5], Src, 2 * ((a1[1] - Src) >> 1) + 2);
LABEL_29:
      a1[1] = (char *)v10;
      return v11;
    }
    v17 = v28;
    v26 = v28;
    v18 = v15 >> 1;
    v19 = v28;
    v27 = v28;
    v28[0] = 0;
    if ( (unsigned __int64)(v15 >> 1) >= 8 )
    {
      if ( v18 <= 0xF )
      {
        v18 = 15;
      }
      else if ( v18 > 0x3FFFFFFFFFFFFFF7LL )
      {
LABEL_20:
        v11 = 0;
LABEL_26:
        if ( v17 != v28 )
          operator delete(v17, (const struct std::nothrow_t *)&std::nothrow);
        return v11;
      }
      v20 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(&v26, v18);
      v17 = v26;
      if ( !v20 )
        goto LABEL_20;
      v19 = v27;
      v13 = Src;
      v16 = v29;
    }
    if ( a4 != (__int16 *)v16 )
    {
      do
      {
        v21 = *a4++;
        *v19 = v21;
        v19 = ++v27;
      }
      while ( a4 != (__int16 *)v16 );
      v17 = v26;
    }
    memmove_0(&v5[2 * a5], v13, 2 * ((a1[1] - v13) >> 1) + 2);
    memcpy_0(v5, v17, 2 * a5);
    a1[1] = (char *)v10;
    goto LABEL_26;
  }
  v22 = (__int64)(v10 - (_QWORD)v5) >> 1;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(a1, v25, v22);
  v23 = (char *)v25[0];
  if ( !v25[0] )
    return 0;
  memcpy_0(v25[0], a4, 2 * a5);
  memcpy_0(&v23[2 * a5], Src, 2 * ((a1[1] - Src) >> 1) + 2);
  v24 = v25[1];
  if ( *a1 != (char *)(a1 + 2) )
    operator delete(*a1, (const struct std::nothrow_t *)&std::nothrow);
  *a1 = v23;
  a1[1] = &v23[2 * v22];
  a1[2] = &v23[2 * ((__int64)v24 - 1)];
  return v11;
}

```

## disassembly

```asm
0x14000dd88  mov     [rsp-38h+arg_18], rbx
0x14000dd8d  mov     [rsp-38h+Src], rdx
0x14000dd92  push    rbp
0x14000dd93  push    rsi
0x14000dd94  push    rdi
0x14000dd95  push    r12
0x14000dd97  push    r13
0x14000dd99  push    r14
0x14000dd9b  push    r15
0x14000dd9d  mov     rbp, rsp
0x14000dda0  sub     rsp, 50h
0x14000dda4  mov     r13, [rcx]
0x14000dda7  mov     r14, r9
0x14000ddaa  mov     rbx, [rbp+arg_20]
0x14000ddae  mov     r9, r8
0x14000ddb1  mov     r8, [rcx+8]
0x14000ddb5  mov     rsi, rcx
0x14000ddb8  mov     rax, r8
0x14000ddbb  sub     rax, r13
0x14000ddbe  sar     rax, 1
0x14000ddc1  cmp     rax, r9
0x14000ddc4  cmovb   r9, rax
0x14000ddc8  mov     rax, rbx
0x14000ddcb  sub     rax, r9
0x14000ddce  lea     r12, [r8+rax*2]
0x14000ddd2  cmp     r12, r13
0x14000ddd5  jnb     short loc_14000DDF7
0x14000ddd7  xor     ebx, ebx
0x14000ddd9  mov     r15b, bl
0x14000dddc  mov     rbx, [rsp+50h+arg_18]
0x14000dde4  mov     al, r15b
0x14000dde7  add     rsp, 50h
0x14000ddeb  pop     r15
0x14000dded  pop     r14
0x14000ddef  pop     r13
0x14000ddf1  pop     r12
0x14000ddf3  pop     rdi
0x14000ddf4  pop     rsi
0x14000ddf5  pop     rbp
0x14000ddf6  retn
0x14000ddf7  lea     r10, ds:0[r9*2]
0x14000ddff  mov     r15b, 1
0x14000de02  add     r10, r13
0x14000de05  lea     rax, [rcx+10h]
0x14000de09  mov     [rbp+Src], r10
0x14000de0d  cmp     r13, rax
0x14000de10  jnz     short loc_14000DE18
0x14000de12  lea     rax, [rcx+1Eh]
0x14000de16  jmp     short loc_14000DE1B
0x14000de18  mov     rax, [rax]
0x14000de1b  cmp     r12, rax
0x14000de1e  ja      loc_14000DF8C
0x14000de24  lea     rax, [rbx+rbx]
0x14000de28  lea     r11, [rax+r14]
0x14000de2c  mov     [rbp+arg_0], r11
0x14000de30  lea     rdi, [rax+r13]
0x14000de34  mov     [rbp+arg_10], rdi
0x14000de38  cmp     r11, r13
0x14000de3b  jbe     loc_14000DF5B
0x14000de41  cmp     r8, r14
0x14000de44  jb      loc_14000DF5B
0x14000de4a  cmp     rbx, r9
0x14000de4d  ja      short loc_14000DE80
0x14000de4f  mov     r8, rax; Size
0x14000de52  mov     rdx, r14; Src
0x14000de55  mov     rcx, r13; void *
0x14000de58  call    memmove_0
0x14000de5d  mov     r8, [rsi+8]
0x14000de61  mov     rcx, rdi; void *
0x14000de64  mov     rdx, [rbp+Src]; Src
0x14000de68  sub     r8, rdx
0x14000de6b  sar     r8, 1
0x14000de6e  lea     r8, ds:2[r8*2]; Size
0x14000de76  call    memmove_0
0x14000de7b  jmp     loc_14000DF83
0x14000de80  xor     ebx, ebx
0x14000de82  lea     rdi, [rbp+var_10]
0x14000de86  mov     rdx, rax
0x14000de89  mov     [rbp+var_20], rdi
0x14000de8d  sar     rdx, 1
0x14000de90  lea     rcx, [rbp+var_10]
0x14000de94  mov     [rbp+var_18], rcx
0x14000de98  mov     [rbp+var_10], bx
0x14000de9c  cmp     rdx, 8
0x14000dea0  jb      short loc_14000DEE0
0x14000dea2  cmp     rdx, 0Fh
0x14000dea6  jbe     short loc_14000DEB9
0x14000dea8  mov     rax, 3FFFFFFFFFFFFFF7h
0x14000deb2  cmp     rdx, rax
0x14000deb5  ja      short loc_14000DECF
0x14000deb7  jmp     short loc_14000DEBE
0x14000deb9  mov     edx, 0Fh
0x14000debe  lea     rcx, [rbp+var_20]
0x14000dec2  call    ?_GrowTo@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(unsigned __int64)
0x14000dec7  mov     rdi, [rbp+var_20]
0x14000decb  test    al, al
0x14000decd  jnz     short loc_14000DED4
0x14000decf  mov     r15b, bl
0x14000ded2  jmp     short loc_14000DF3A
0x14000ded4  mov     rcx, [rbp+var_18]
0x14000ded8  mov     r10, [rbp+Src]
0x14000dedc  mov     r11, [rbp+arg_0]
0x14000dee0  cmp     r14, r11
0x14000dee3  jz      short loc_14000DF05
0x14000dee5  movzx   eax, word ptr [r14]
0x14000dee9  add     r14, 2
0x14000deed  mov     [rcx], ax
0x14000def0  mov     rcx, [rbp+var_18]
0x14000def4  add     rcx, 2
0x14000def8  mov     [rbp+var_18], rcx
0x14000defc  cmp     r14, r11
0x14000deff  jnz     short loc_14000DEE5
0x14000df01  mov     rdi, [rbp+var_20]
0x14000df05  mov     r8, [rsi+8]
0x14000df09  mov     rdx, r10; Src
0x14000df0c  mov     rcx, [rbp+arg_10]; void *
0x14000df10  sub     r8, r10
0x14000df13  sar     r8, 1
0x14000df16  lea     r8, ds:2[r8*2]; Size
0x14000df1e  call    memmove_0
0x14000df23  mov     rbx, [rbp+arg_20]
0x14000df27  mov     rdx, rdi; Src
0x14000df2a  mov     rcx, r13; void *
0x14000df2d  lea     r8, [rbx+rbx]; Size
0x14000df31  call    memcpy_0
0x14000df36  mov     [rsi+8], r12
0x14000df3a  lea     rax, [rbp+var_10]
0x14000df3e  cmp     rdi, rax
0x14000df41  jz      loc_14000DDDC
0x14000df47  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000df4e  mov     rcx, rdi; void *
0x14000df51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000df56  jmp     loc_14000DDDC
0x14000df5b  sub     r8, r10
0x14000df5e  mov     rdx, r10; Src
0x14000df61  sar     r8, 1
0x14000df64  mov     rcx, rdi; void *
0x14000df67  lea     r8, ds:2[r8*2]; Size
0x14000df6f  call    memmove_0
0x14000df74  lea     r8, [rbx+rbx]; Size
0x14000df78  mov     rdx, r14; Src
0x14000df7b  mov     rcx, r13; void *
0x14000df7e  call    memcpy_0
0x14000df83  mov     [rsi+8], r12
0x14000df87  jmp     loc_14000DDDC
0x14000df8c  sub     r12, r13
0x14000df8f  lea     rdx, [rbp+var_30]
0x14000df93  sar     r12, 1
0x14000df96  mov     r8, r12
0x14000df99  call    ?_GrowAlloc@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA?AU?$pair@PEA_W_K@2@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(unsigned __int64)
0x14000df9e  mov     rdi, [rbp+var_30]
0x14000dfa2  xor     ebx, ebx
0x14000dfa4  test    rdi, rdi
0x14000dfa7  jz      loc_14000DDD9
0x14000dfad  mov     rbx, [rbp+arg_20]
0x14000dfb1  mov     rdx, r14; Src
0x14000dfb4  add     rbx, rbx
0x14000dfb7  mov     rcx, rdi; void *
0x14000dfba  mov     r8, rbx; Size
0x14000dfbd  call    memcpy_0
0x14000dfc2  mov     r8, [rsi+8]
0x14000dfc6  lea     rcx, [rbx+rdi]; void *
0x14000dfca  mov     rdx, [rbp+Src]; Src
0x14000dfce  sub     r8, rdx
0x14000dfd1  sar     r8, 1
0x14000dfd4  lea     r8, ds:2[r8*2]; Size
0x14000dfdc  call    memcpy_0
0x14000dfe1  mov     r14, [rbp+var_28]
0x14000dfe5  lea     rbx, [rsi+10h]
0x14000dfe9  cmp     [rsi], rbx
0x14000dfec  jz      short loc_14000DFFD
0x14000dfee  mov     rcx, [rsi]; void *
0x14000dff1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dff8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dffd  lea     rax, [rdi+r12*2]
0x14000e001  mov     [rsi], rdi
0x14000e004  mov     [rsi+8], rax
0x14000e008  lea     rax, [r14-1]
0x14000e00c  lea     rax, [rdi+rax*2]
0x14000e010  mov     [rbx], rax
0x14000e013  jmp     loc_14000DDDC
```
