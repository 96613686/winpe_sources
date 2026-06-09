# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140007c5c`
- end: `0x140007d4c`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140007e10`
- `0x140007f08`

## callees

- `0x1400016dc`
- `0x140001888`
- `0x140002206`
- `0x140007c5c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140007d1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007d1a`

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
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
  void *v18; // [rsp+68h] [rbp+20h]

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
      v13 = &v14;
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
0x140007c5c  mov     [rsp+arg_10], r8
0x140007c61  mov     [rsp+arg_8], rdx
0x140007c66  mov     [rsp+arg_0], rcx
0x140007c6b  push    rbx
0x140007c6c  push    rsi
0x140007c6d  push    rdi
0x140007c6e  push    r14
0x140007c70  sub     rsp, 28h
0x140007c74  mov     r14, r8
0x140007c77  mov     rdi, rdx
0x140007c7a  mov     rbx, rcx
0x140007c7d  or      rdx, 0Fh
0x140007c81  mov     r9, 0FFFFFFFFFFFFFFFEh
0x140007c88  cmp     rdx, r9
0x140007c8b  ja      short loc_140007CC1
0x140007c8d  mov     rdi, rdx
0x140007c90  mov     r8, [rcx+18h]
0x140007c94  mov     rcx, r8
0x140007c97  shr     rcx, 1
0x140007c9a  mov     rax, 0AAAAAAAAAAAAAAABh
0x140007ca4  mul     rdx
0x140007ca7  shr     rdx, 1
0x140007caa  cmp     rcx, rdx
0x140007cad  jbe     short loc_140007CC1
0x140007caf  mov     rax, r9
0x140007cb2  sub     rax, rcx
0x140007cb5  cmp     r8, rax
0x140007cb8  lea     rdi, [rcx+r8]
0x140007cbc  jbe     short loc_140007CC1
0x140007cbe  mov     rdi, r9
0x140007cc1  lea     rcx, [rdi+1]; Size
0x140007cc5  test    rcx, rcx
0x140007cc8  jz      short loc_140007CD9
0x140007cca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007ccf  mov     rsi, rax
0x140007cd2  test    rax, rax
0x140007cd5  jz      short loc_140007D45
0x140007cd7  jmp     short loc_140007CDB
0x140007cd9  xor     esi, esi
0x140007cdb  jmp     short loc_140007CF1
0x140007cdd  mov     rbx, [rsp+48h+arg_0]
0x140007ce2  mov     r14, [rsp+48h+arg_10]
0x140007ce7  mov     rdi, [rsp+48h+arg_8]
0x140007cec  mov     rsi, [rsp+48h+arg_18]
0x140007cf1  test    r14, r14
0x140007cf4  jz      short loc_140007D10
0x140007cf6  cmp     qword ptr [rbx+18h], 10h
0x140007cfb  jb      short loc_140007D02
0x140007cfd  mov     rdx, [rbx]
0x140007d00  jmp     short loc_140007D05
0x140007d02  mov     rdx, rbx; Src
0x140007d05  mov     r8, r14; Size
0x140007d08  mov     rcx, rsi; void *
0x140007d0b  call    memcpy_0
0x140007d10  cmp     qword ptr [rbx+18h], 10h
0x140007d15  jb      short loc_140007D20
0x140007d17  mov     rcx, [rbx]
0x140007d1a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140007d20  lea     rax, [rbx+10h]
0x140007d24  mov     [rbx], rsi
0x140007d27  mov     [rbx+18h], rdi
0x140007d2b  cmp     rdi, 10h
0x140007d2f  cmovnb  rbx, rsi
0x140007d33  mov     [rax], r14
0x140007d36  mov     byte ptr [rbx+r14], 0
0x140007d3b  add     rsp, 28h
0x140007d3f  pop     r14
0x140007d41  pop     rdi
0x140007d42  pop     rsi
0x140007d43  pop     rbx
0x140007d44  retn
0x140007d45  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
