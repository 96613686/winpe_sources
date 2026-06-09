# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001c18`
- end: `0x180001d0f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001e28`
- `0x180001f20`

## callees

- `0x180001536`
- `0x180001a38`
- `0x180001c18`
- `0x180001d78`
- `0x1800024f6`

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
0x180001c18  mov     rax, rsp
0x180001c1b  mov     [rax+18h], r8
0x180001c1f  mov     [rax+10h], rdx
0x180001c23  mov     [rax+8], rcx
0x180001c27  push    rbx
0x180001c28  push    rsi
0x180001c29  push    rdi
0x180001c2a  push    r14
0x180001c2c  sub     rsp, 38h
0x180001c30  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001c38  mov     r14, r8
0x180001c3b  mov     rdi, rdx
0x180001c3e  mov     rbx, rcx
0x180001c41  or      rdx, 0Fh
0x180001c45  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180001c4c  cmp     rdx, r9
0x180001c4f  ja      short loc_180001C85
0x180001c51  mov     rdi, rdx
0x180001c54  mov     r8, [rcx+18h]
0x180001c58  mov     rcx, r8
0x180001c5b  shr     rcx, 1
0x180001c5e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001c68  mul     rdx
0x180001c6b  shr     rdx, 1
0x180001c6e  cmp     rcx, rdx
0x180001c71  jbe     short loc_180001C85
0x180001c73  mov     rax, r9
0x180001c76  sub     rax, rcx
0x180001c79  cmp     r8, rax
0x180001c7c  lea     rdi, [rcx+r8]
0x180001c80  jbe     short loc_180001C85
0x180001c82  mov     rdi, r9
0x180001c85  lea     rcx, [rdi+1]; Size
0x180001c89  test    rcx, rcx
0x180001c8c  jz      short loc_180001C9D
0x180001c8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c93  mov     rsi, rax
0x180001c96  test    rax, rax
0x180001c99  jz      short loc_180001D08
0x180001c9b  jmp     short loc_180001C9F
0x180001c9d  xor     esi, esi
0x180001c9f  jmp     short loc_180001CB5
0x180001ca1  mov     rbx, [rsp+58h+arg_0]
0x180001ca6  mov     r14, [rsp+58h+arg_10]
0x180001cab  mov     rdi, [rsp+58h+arg_8]
0x180001cb0  mov     rsi, [rsp+58h+arg_18]
0x180001cb5  test    r14, r14
0x180001cb8  jz      short loc_180001CD4
0x180001cba  cmp     qword ptr [rbx+18h], 10h
0x180001cbf  jb      short loc_180001CC6
0x180001cc1  mov     rdx, [rbx]
0x180001cc4  jmp     short loc_180001CC9
0x180001cc6  mov     rdx, rbx; Src
0x180001cc9  mov     r8, r14; Size
0x180001ccc  mov     rcx, rsi; void *
0x180001ccf  call    memcpy_0
0x180001cd4  cmp     qword ptr [rbx+18h], 10h
0x180001cd9  jb      short loc_180001CE3
0x180001cdb  mov     rcx, [rbx]; void *
0x180001cde  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001ce3  lea     rax, [rbx+10h]
0x180001ce7  mov     [rbx], rsi
0x180001cea  mov     [rbx+18h], rdi
0x180001cee  cmp     rdi, 10h
0x180001cf2  cmovnb  rbx, rsi
0x180001cf6  mov     [rax], r14
0x180001cf9  mov     byte ptr [rbx+r14], 0
0x180001cfe  add     rsp, 38h
0x180001d02  pop     r14
0x180001d04  pop     rdi
0x180001d05  pop     rsi
0x180001d06  pop     rbx
0x180001d07  retn
0x180001d08  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
