# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140006d2c`
- end: `0x140006e24`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `248`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140006ef0`
- `0x140006fe8`

## callees

- `0x140001174`
- `0x140001318`
- `0x140001936`
- `0x140006d2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140006df2`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006df2`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  _QWORD *v13; // rdx
  _QWORD v14[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v18; // [rsp+78h] [rbp+20h]

  v14[4] = -2;
  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x140006d2c  mov     rax, rsp
0x140006d2f  mov     [rax+18h], r8
0x140006d33  mov     [rax+10h], rdx
0x140006d37  mov     [rax+8], rcx
0x140006d3b  push    rbx
0x140006d3c  push    rsi
0x140006d3d  push    rdi
0x140006d3e  push    r14
0x140006d40  sub     rsp, 38h
0x140006d44  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x140006d4c  mov     r14, r8
0x140006d4f  mov     rdi, rdx
0x140006d52  mov     rbx, rcx
0x140006d55  or      rdx, 0Fh
0x140006d59  mov     r9, 0FFFFFFFFFFFFFFFEh
0x140006d60  cmp     rdx, r9
0x140006d63  ja      short loc_140006D99
0x140006d65  mov     rdi, rdx
0x140006d68  mov     r8, [rcx+18h]
0x140006d6c  mov     rcx, r8
0x140006d6f  shr     rcx, 1
0x140006d72  mov     rax, 0AAAAAAAAAAAAAAABh
0x140006d7c  mul     rdx
0x140006d7f  shr     rdx, 1
0x140006d82  cmp     rcx, rdx
0x140006d85  jbe     short loc_140006D99
0x140006d87  mov     rax, r9
0x140006d8a  sub     rax, rcx
0x140006d8d  cmp     r8, rax
0x140006d90  lea     rdi, [rcx+r8]
0x140006d94  jbe     short loc_140006D99
0x140006d96  mov     rdi, r9
0x140006d99  lea     rcx, [rdi+1]; Size
0x140006d9d  test    rcx, rcx
0x140006da0  jz      short loc_140006DB1
0x140006da2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006da7  mov     rsi, rax
0x140006daa  test    rax, rax
0x140006dad  jz      short loc_140006E1D
0x140006daf  jmp     short loc_140006DB3
0x140006db1  xor     esi, esi
0x140006db3  jmp     short loc_140006DC9
0x140006db5  mov     rbx, [rsp+58h+arg_0]
0x140006dba  mov     r14, [rsp+58h+arg_10]
0x140006dbf  mov     rdi, [rsp+58h+arg_8]
0x140006dc4  mov     rsi, [rsp+58h+arg_18]
0x140006dc9  test    r14, r14
0x140006dcc  jz      short loc_140006DE8
0x140006dce  cmp     qword ptr [rbx+18h], 10h
0x140006dd3  jb      short loc_140006DDA
0x140006dd5  mov     rdx, [rbx]
0x140006dd8  jmp     short loc_140006DDD
0x140006dda  mov     rdx, rbx; Src
0x140006ddd  mov     r8, r14; Size
0x140006de0  mov     rcx, rsi; void *
0x140006de3  call    memcpy_0
0x140006de8  cmp     qword ptr [rbx+18h], 10h
0x140006ded  jb      short loc_140006DF8
0x140006def  mov     rcx, [rbx]
0x140006df2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140006df8  lea     rax, [rbx+10h]
0x140006dfc  mov     [rbx], rsi
0x140006dff  mov     [rbx+18h], rdi
0x140006e03  cmp     rdi, 10h
0x140006e07  cmovnb  rbx, rsi
0x140006e0b  mov     [rax], r14
0x140006e0e  mov     byte ptr [rbx+r14], 0
0x140006e13  add     rsp, 38h
0x140006e17  pop     r14
0x140006e19  pop     rdi
0x140006e1a  pop     rsi
0x140006e1b  pop     rbx
0x140006e1c  retn
0x140006e1d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
