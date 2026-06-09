# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001da8`
- end: `0x180001e9f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001fb8`
- `0x1800020c4`

## callees

- `0x1800015c7`
- `0x180001bc8`
- `0x180001da8`
- `0x180001f08`
- `0x1800025d8`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  const void **v4; // rbx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rcx
  void *v8; // rsi
  const void *v9; // rdx
  size_t *result; // rax
  void *v11; // rax
  _QWORD *v12; // rdx
  _QWORD v13[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v17; // [rsp+78h] [rbp+20h]

  v13[4] = -2;
  v3 = a3;
  v4 = Src;
  v5 = a2 | 0xF;
  if ( (a2 | 0xF) == 0xFFFFFFFFFFFFFFFFuLL )
  {
    v5 = a2;
  }
  else
  {
    v6 = (unsigned __int64)Src[3];
    v7 = v6 >> 1;
    if ( v6 >> 1 > v5 / 3 )
    {
      v5 = v7 + v6;
      if ( v6 > -2LL - v7 )
        v5 = -2;
    }
  }
  try
  {
    v8 = 0;
    if ( v5 != -1 )
    {
      v8 = operator new(v5 + 1);
      if ( !v8 )
        std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v11 = 0;
      if ( a2 != -1 )
      {
        v11 = operator new(a2 + 1);
        if ( !v11 )
          std::_Xbad_alloc();
      }
      v17 = v11;
    }
    catch ( ... )
    {
      v12 = v13;
      LOBYTE(v12) = 1;
      std::string::_Tidy(Src, v12, 0);
      throw;
    }
    v4 = Src;
    v3 = a3;
    v5 = a2;
    v8 = v17;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v4[3] < 0x10 )
      v9 = v4;
    else
      v9 = *v4;
    memcpy_0(v8, v9, v3);
  }
  if ( (unsigned __int64)v4[3] >= 0x10 )
    operator delete((void *)*v4);
  result = (size_t *)(v4 + 2);
  *v4 = v8;
  v4[3] = (const void *)v5;
  if ( v5 >= 0x10 )
    v4 = (const void **)v8;
  *result = v3;
  *((_BYTE *)v4 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180001da8  mov     rax, rsp
0x180001dab  mov     [rax+18h], r8
0x180001daf  mov     [rax+10h], rdx
0x180001db3  mov     [rax+8], rcx
0x180001db7  push    rbx
0x180001db8  push    rsi
0x180001db9  push    rdi
0x180001dba  push    r14
0x180001dbc  sub     rsp, 38h
0x180001dc0  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001dc8  mov     r14, r8
0x180001dcb  mov     rbx, rcx
0x180001dce  mov     rdi, rdx
0x180001dd1  or      rdi, 0Fh
0x180001dd5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180001ddc  cmp     rdi, r9
0x180001ddf  jbe     short loc_180001DE6
0x180001de1  mov     rdi, rdx
0x180001de4  jmp     short loc_180001E17
0x180001de6  mov     r8, [rcx+18h]
0x180001dea  mov     rcx, r8
0x180001ded  shr     rcx, 1
0x180001df0  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001dfa  mul     rdi
0x180001dfd  shr     rdx, 1
0x180001e00  cmp     rcx, rdx
0x180001e03  jbe     short loc_180001E17
0x180001e05  mov     rax, r9
0x180001e08  sub     rax, rcx
0x180001e0b  cmp     r8, rax
0x180001e0e  lea     rdi, [rcx+r8]
0x180001e12  jbe     short loc_180001E17
0x180001e14  mov     rdi, r9
0x180001e17  lea     rcx, [rdi+1]; Size
0x180001e1b  xor     esi, esi
0x180001e1d  test    rcx, rcx
0x180001e20  jz      short loc_180001E2F
0x180001e22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e27  mov     rsi, rax
0x180001e2a  test    rax, rax
0x180001e2d  jz      short loc_180001E98
0x180001e2f  jmp     short loc_180001E45
0x180001e31  mov     rbx, [rsp+58h+arg_0]
0x180001e36  mov     r14, [rsp+58h+arg_10]
0x180001e3b  mov     rdi, [rsp+58h+arg_8]
0x180001e40  mov     rsi, [rsp+58h+arg_18]
0x180001e45  test    r14, r14
0x180001e48  jz      short loc_180001E64
0x180001e4a  cmp     qword ptr [rbx+18h], 10h
0x180001e4f  jb      short loc_180001E56
0x180001e51  mov     rdx, [rbx]
0x180001e54  jmp     short loc_180001E59
0x180001e56  mov     rdx, rbx; Src
0x180001e59  mov     r8, r14; Size
0x180001e5c  mov     rcx, rsi; void *
0x180001e5f  call    memcpy_0
0x180001e64  cmp     qword ptr [rbx+18h], 10h
0x180001e69  jb      short loc_180001E73
0x180001e6b  mov     rcx, [rbx]; void *
0x180001e6e  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001e73  lea     rax, [rbx+10h]
0x180001e77  mov     [rbx], rsi
0x180001e7a  mov     [rbx+18h], rdi
0x180001e7e  cmp     rdi, 10h
0x180001e82  cmovnb  rbx, rsi
0x180001e86  mov     [rax], r14
0x180001e89  mov     byte ptr [rbx+r14], 0
0x180001e8e  add     rsp, 38h
0x180001e92  pop     r14
0x180001e94  pop     rdi
0x180001e95  pop     rsi
0x180001e96  pop     rbx
0x180001e97  retn
0x180001e98  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
