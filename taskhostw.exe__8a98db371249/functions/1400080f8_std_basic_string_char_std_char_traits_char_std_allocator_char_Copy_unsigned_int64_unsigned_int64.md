# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1400080f8`
- end: `0x1400081ef`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140008308`
- `0x140008400`

## callees

- `0x140007f24`
- `0x1400080f8`
- `0x140008258`
- `0x1400088d6`
- `0x140008966`

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
0x1400080f8  mov     rax, rsp
0x1400080fb  mov     [rax+18h], r8
0x1400080ff  mov     [rax+10h], rdx
0x140008103  mov     [rax+8], rcx
0x140008107  push    rbx
0x140008108  push    rsi
0x140008109  push    rdi
0x14000810a  push    r14
0x14000810c  sub     rsp, 38h
0x140008110  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x140008118  mov     r14, r8
0x14000811b  mov     rdi, rdx
0x14000811e  mov     rbx, rcx
0x140008121  or      rdx, 0Fh
0x140008125  mov     r9, 0FFFFFFFFFFFFFFFEh
0x14000812c  cmp     rdx, r9
0x14000812f  ja      short loc_140008165
0x140008131  mov     rdi, rdx
0x140008134  mov     r8, [rcx+18h]
0x140008138  mov     rcx, r8
0x14000813b  shr     rcx, 1
0x14000813e  mov     rax, 0AAAAAAAAAAAAAAABh
0x140008148  mul     rdx
0x14000814b  shr     rdx, 1
0x14000814e  cmp     rcx, rdx
0x140008151  jbe     short loc_140008165
0x140008153  mov     rax, r9
0x140008156  sub     rax, rcx
0x140008159  cmp     r8, rax
0x14000815c  lea     rdi, [rcx+r8]
0x140008160  jbe     short loc_140008165
0x140008162  mov     rdi, r9
0x140008165  lea     rcx, [rdi+1]; Size
0x140008169  test    rcx, rcx
0x14000816c  jz      short loc_14000817D
0x14000816e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008173  mov     rsi, rax
0x140008176  test    rax, rax
0x140008179  jz      short loc_1400081E8
0x14000817b  jmp     short loc_14000817F
0x14000817d  xor     esi, esi
0x14000817f  jmp     short loc_140008195
0x140008181  mov     rbx, [rsp+58h+arg_0]
0x140008186  mov     r14, [rsp+58h+arg_10]
0x14000818b  mov     rdi, [rsp+58h+arg_8]
0x140008190  mov     rsi, [rsp+58h+arg_18]
0x140008195  test    r14, r14
0x140008198  jz      short loc_1400081B4
0x14000819a  cmp     qword ptr [rbx+18h], 10h
0x14000819f  jb      short loc_1400081A6
0x1400081a1  mov     rdx, [rbx]
0x1400081a4  jmp     short loc_1400081A9
0x1400081a6  mov     rdx, rbx; Src
0x1400081a9  mov     r8, r14; Size
0x1400081ac  mov     rcx, rsi; void *
0x1400081af  call    memcpy_0
0x1400081b4  cmp     qword ptr [rbx+18h], 10h
0x1400081b9  jb      short loc_1400081C3
0x1400081bb  mov     rcx, [rbx]; void *
0x1400081be  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1400081c3  lea     rax, [rbx+10h]
0x1400081c7  mov     [rbx], rsi
0x1400081ca  mov     [rbx+18h], rdi
0x1400081ce  cmp     rdi, 10h
0x1400081d2  cmovnb  rbx, rsi
0x1400081d6  mov     [rax], r14
0x1400081d9  mov     byte ptr [rbx+r14], 0
0x1400081de  add     rsp, 38h
0x1400081e2  pop     r14
0x1400081e4  pop     rdi
0x1400081e5  pop     rsi
0x1400081e6  pop     rbx
0x1400081e7  retn
0x1400081e8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
