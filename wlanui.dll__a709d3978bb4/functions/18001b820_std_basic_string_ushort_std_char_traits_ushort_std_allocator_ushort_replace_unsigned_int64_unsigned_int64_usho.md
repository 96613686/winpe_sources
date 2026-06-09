# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18001b820`
- end: `0x18001ba15`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0PEBG0@Z`
- size: `501`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001a84c`

## callees

- `0x180001e26`
- `0x180001e32`
- `0x18001661c`
- `0x180016634`
- `0x18001af34`
- `0x18001b4b8`
- `0x18001b820`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *Src,
        unsigned __int64 a2,
        unsigned __int64 a3,
        char *a4,
        unsigned __int64 a5)
{
  unsigned __int64 v6; // rdi
  _QWORD *v8; // rbx
  char *v9; // rax
  char *v10; // rax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // r15
  _WORD *v14; // rcx
  _WORD *v15; // rdx
  unsigned __int64 v16; // rsi
  _WORD *v17; // rcx
  _WORD *v18; // rdx
  _WORD *v19; // rcx
  _WORD *v20; // rax
  _WORD *v21; // rcx

  v6 = a3;
  v8 = Src;
  if ( !a4 )
    goto LABEL_13;
  v9 = Src[3] < 8u ? (char *)Src : (char *)*Src;
  if ( a4 < v9 )
    goto LABEL_13;
  if ( Src[3] >= 8u )
    Src = (_QWORD *)*Src;
  if ( (char *)Src + 2 * v8[2] <= a4 )
  {
LABEL_13:
    v12 = v8[2];
    if ( v12 < a2 )
      std::wstring::_Xran();
    if ( v12 - a2 < a3 )
      v6 = v12 - a2;
    if ( ~a5 <= v12 - v6 )
      std::wstring::_Xlen();
    v13 = v12 - a2 - v6;
    if ( a5 < v6 )
    {
      if ( v8[3] < 8u )
      {
        v14 = v8;
        v15 = v8;
      }
      else
      {
        v14 = (_WORD *)*v8;
        v15 = (_WORD *)*v8;
      }
      if ( v13 )
        memmove_0(&v14[a2 + a5], &v15[a2 + v6], 2 * v13);
    }
    if ( !a5 && !v6 )
      return v8;
    v16 = a5 + v8[2] - v6;
    if ( v16 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( v8[3] >= v16 )
    {
      if ( v16 )
      {
LABEL_28:
        if ( v6 < a5 )
        {
          if ( v8[3] < 8u )
          {
            v17 = v8;
            v18 = v8;
          }
          else
          {
            v17 = (_WORD *)*v8;
            v18 = (_WORD *)*v8;
          }
          if ( v13 )
            memmove_0(&v17[a2 + a5], &v18[a2 + v6], 2 * v13);
        }
        if ( v8[3] < 8u )
          v20 = v8;
        else
          v20 = (_WORD *)*v8;
        if ( a5 )
          memcpy_0(&v20[a2], a4, 2 * a5);
        if ( v8[3] < 8u )
          v21 = v8;
        else
          v21 = (_WORD *)*v8;
        v8[2] = v16;
        v21[v16] = 0;
        return v8;
      }
      if ( v8[3] < 8u )
        v19 = v8;
      else
        v19 = (_WORD *)*v8;
      v8[2] = 0;
      *v19 = 0;
    }
    else
    {
      std::wstring::_Copy((const void **)v8, a5 + v8[2] - v6, v8[2]);
      if ( v16 )
        goto LABEL_28;
    }
    return v8;
  }
  if ( v8[3] < 8u )
    v10 = (char *)v8;
  else
    v10 = (char *)*v8;
  return std::wstring::replace(v8, a2, a3, v8, (a4 - v10) >> 1, a5);
}

```

## disassembly

```asm
0x18001b820  push    rbx
0x18001b822  push    rbp
0x18001b823  push    rsi
0x18001b824  push    rdi
0x18001b825  push    r12
0x18001b827  push    r14
0x18001b829  push    r15
0x18001b82b  sub     rsp, 30h
0x18001b82f  mov     rbp, r9
0x18001b832  mov     rdi, r8
0x18001b835  mov     r12, rdx
0x18001b838  mov     rbx, rcx
0x18001b83b  test    r9, r9
0x18001b83e  jz      short loc_18001B8A2
0x18001b840  cmp     qword ptr [rcx+18h], 8
0x18001b845  jb      short loc_18001B84C
0x18001b847  mov     rax, [rcx]
0x18001b84a  jmp     short loc_18001B84F
0x18001b84c  mov     rax, rbx
0x18001b84f  cmp     rbp, rax
0x18001b852  jb      short loc_18001B8A2
0x18001b854  cmp     qword ptr [rcx+18h], 8
0x18001b859  jb      short loc_18001B85E
0x18001b85b  mov     rcx, [rcx]
0x18001b85e  mov     rax, [rbx+10h]
0x18001b862  lea     rcx, [rcx+rax*2]
0x18001b866  cmp     rcx, rbp
0x18001b869  jbe     short loc_18001B8A2
0x18001b86b  cmp     qword ptr [rbx+18h], 8
0x18001b870  jb      short loc_18001B877
0x18001b872  mov     rax, [rbx]
0x18001b875  jmp     short loc_18001B87A
0x18001b877  mov     rax, rbx
0x18001b87a  sub     rbp, rax
0x18001b87d  mov     r9, rbx
0x18001b880  mov     rax, [rsp+68h+arg_20]
0x18001b888  mov     rcx, rbx; Src
0x18001b88b  sar     rbp, 1
0x18001b88e  mov     [rsp+68h+var_40], rax; __int64
0x18001b893  mov     [rsp+68h+var_48], rbp; __int64
0x18001b898  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x18001b89d  jmp     loc_18001B9F4
0x18001b8a2  mov     rcx, [rbx+10h]
0x18001b8a6  cmp     rcx, r12
0x18001b8a9  jb      loc_18001BA03
0x18001b8af  mov     r14, [rsp+68h+arg_20]
0x18001b8b7  mov     r15, rcx
0x18001b8ba  sub     r15, r12
0x18001b8bd  mov     rax, r14
0x18001b8c0  cmp     r15, rdi
0x18001b8c3  not     rax
0x18001b8c6  cmovb   rdi, r15
0x18001b8ca  sub     rcx, rdi
0x18001b8cd  cmp     rax, rcx
0x18001b8d0  jbe     loc_18001BA09
0x18001b8d6  sub     r15, rdi
0x18001b8d9  cmp     r14, rdi
0x18001b8dc  jnb     short loc_18001B911
0x18001b8de  cmp     qword ptr [rbx+18h], 8
0x18001b8e3  jb      short loc_18001B8ED
0x18001b8e5  mov     rcx, [rbx]
0x18001b8e8  mov     rdx, rcx
0x18001b8eb  jmp     short loc_18001B8F3
0x18001b8ed  mov     rcx, rbx
0x18001b8f0  mov     rdx, rbx
0x18001b8f3  test    r15, r15
0x18001b8f6  jz      short loc_18001B911
0x18001b8f8  lea     rax, [r12+rdi]
0x18001b8fc  lea     rdx, [rdx+rax*2]; Src
0x18001b900  lea     rax, [r12+r14]
0x18001b904  lea     rcx, [rcx+rax*2]; void *
0x18001b908  lea     r8, [r15+r15]; Size
0x18001b90c  call    memmove_0
0x18001b911  test    r14, r14
0x18001b914  jnz     short loc_18001B91F
0x18001b916  test    rdi, rdi
0x18001b919  jz      loc_18001B9F1
0x18001b91f  mov     r8, [rbx+10h]
0x18001b923  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001b92d  mov     rsi, r8
0x18001b930  sub     rsi, rdi
0x18001b933  add     rsi, r14
0x18001b936  cmp     rsi, rax
0x18001b939  ja      loc_18001BA0F
0x18001b93f  cmp     [rbx+18h], rsi
0x18001b943  jnb     short loc_18001B96D
0x18001b945  mov     rdx, rsi
0x18001b948  mov     rcx, rbx; Src
0x18001b94b  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001b950  test    rsi, rsi
0x18001b953  jz      loc_18001B9F1
0x18001b959  cmp     rdi, r14
0x18001b95c  jnb     short loc_18001B9B4
0x18001b95e  cmp     qword ptr [rbx+18h], 8
0x18001b963  jb      short loc_18001B990
0x18001b965  mov     rcx, [rbx]
0x18001b968  mov     rdx, rcx
0x18001b96b  jmp     short loc_18001B996
0x18001b96d  test    rsi, rsi
0x18001b970  jnz     short loc_18001B959
0x18001b972  cmp     qword ptr [rbx+18h], 8
0x18001b977  jb      short loc_18001B97E
0x18001b979  mov     rcx, [rbx]
0x18001b97c  jmp     short loc_18001B981
0x18001b97e  mov     rcx, rbx
0x18001b981  xor     eax, eax
0x18001b983  mov     qword ptr [rbx+10h], 0
0x18001b98b  mov     [rcx], ax
0x18001b98e  jmp     short loc_18001B9F1
0x18001b990  mov     rcx, rbx
0x18001b993  mov     rdx, rbx
0x18001b996  test    r15, r15
0x18001b999  jz      short loc_18001B9B4
0x18001b99b  lea     rax, [r12+rdi]
0x18001b99f  lea     rdx, [rdx+rax*2]; Src
0x18001b9a3  lea     rax, [r12+r14]
0x18001b9a7  lea     rcx, [rcx+rax*2]; void *
0x18001b9ab  lea     r8, [r15+r15]; Size
0x18001b9af  call    memmove_0
0x18001b9b4  cmp     qword ptr [rbx+18h], 8
0x18001b9b9  jb      short loc_18001B9C0
0x18001b9bb  mov     rax, [rbx]
0x18001b9be  jmp     short loc_18001B9C3
0x18001b9c0  mov     rax, rbx
0x18001b9c3  test    r14, r14
0x18001b9c6  jz      short loc_18001B9D8
0x18001b9c8  lea     r8, [r14+r14]; Size
0x18001b9cc  mov     rdx, rbp; Src
0x18001b9cf  lea     rcx, [rax+r12*2]; void *
0x18001b9d3  call    memcpy_0
0x18001b9d8  cmp     qword ptr [rbx+18h], 8
0x18001b9dd  jb      short loc_18001B9E4
0x18001b9df  mov     rcx, [rbx]
0x18001b9e2  jmp     short loc_18001B9E7
0x18001b9e4  mov     rcx, rbx
0x18001b9e7  xor     eax, eax
0x18001b9e9  mov     [rbx+10h], rsi
0x18001b9ed  mov     [rcx+rsi*2], ax
0x18001b9f1  mov     rax, rbx
0x18001b9f4  add     rsp, 30h
0x18001b9f8  pop     r15
0x18001b9fa  pop     r14
0x18001b9fc  pop     r12
0x18001b9fe  pop     rdi
0x18001b9ff  pop     rsi
0x18001ba00  pop     rbp
0x18001ba01  pop     rbx
0x18001ba02  retn
0x18001ba03  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18001ba09  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x18001ba0f  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
