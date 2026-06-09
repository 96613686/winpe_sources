# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180002e38`
- end: `0x180002f2f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003048`
- `0x180003140`

## callees

- `0x180002c54`
- `0x180002e38`
- `0x180002f98`
- `0x180003a86`
- `0x180003f66`

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
0x180002e38  mov     rax, rsp
0x180002e3b  mov     [rax+18h], r8
0x180002e3f  mov     [rax+10h], rdx
0x180002e43  mov     [rax+8], rcx
0x180002e47  push    rbx
0x180002e48  push    rsi
0x180002e49  push    rdi
0x180002e4a  push    r14
0x180002e4c  sub     rsp, 38h
0x180002e50  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180002e58  mov     r14, r8
0x180002e5b  mov     rdi, rdx
0x180002e5e  mov     rbx, rcx
0x180002e61  or      rdx, 0Fh
0x180002e65  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180002e6c  cmp     rdx, r9
0x180002e6f  ja      short loc_180002EA5
0x180002e71  mov     rdi, rdx
0x180002e74  mov     r8, [rcx+18h]
0x180002e78  mov     rcx, r8
0x180002e7b  shr     rcx, 1
0x180002e7e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180002e88  mul     rdx
0x180002e8b  shr     rdx, 1
0x180002e8e  cmp     rcx, rdx
0x180002e91  jbe     short loc_180002EA5
0x180002e93  mov     rax, r9
0x180002e96  sub     rax, rcx
0x180002e99  cmp     r8, rax
0x180002e9c  lea     rdi, [rcx+r8]
0x180002ea0  jbe     short loc_180002EA5
0x180002ea2  mov     rdi, r9
0x180002ea5  lea     rcx, [rdi+1]; Size
0x180002ea9  test    rcx, rcx
0x180002eac  jz      short loc_180002EBD
0x180002eae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002eb3  mov     rsi, rax
0x180002eb6  test    rax, rax
0x180002eb9  jz      short loc_180002F28
0x180002ebb  jmp     short loc_180002EBF
0x180002ebd  xor     esi, esi
0x180002ebf  jmp     short loc_180002ED5
0x180002ec1  mov     rbx, [rsp+58h+arg_0]
0x180002ec6  mov     r14, [rsp+58h+arg_10]
0x180002ecb  mov     rdi, [rsp+58h+arg_8]
0x180002ed0  mov     rsi, [rsp+58h+arg_18]
0x180002ed5  test    r14, r14
0x180002ed8  jz      short loc_180002EF4
0x180002eda  cmp     qword ptr [rbx+18h], 10h
0x180002edf  jb      short loc_180002EE6
0x180002ee1  mov     rdx, [rbx]
0x180002ee4  jmp     short loc_180002EE9
0x180002ee6  mov     rdx, rbx; Src
0x180002ee9  mov     r8, r14; Size
0x180002eec  mov     rcx, rsi; void *
0x180002eef  call    memcpy_0
0x180002ef4  cmp     qword ptr [rbx+18h], 10h
0x180002ef9  jb      short loc_180002F03
0x180002efb  mov     rcx, [rbx]; void *
0x180002efe  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180002f03  lea     rax, [rbx+10h]
0x180002f07  mov     [rbx], rsi
0x180002f0a  mov     [rbx+18h], rdi
0x180002f0e  cmp     rdi, 10h
0x180002f12  cmovnb  rbx, rsi
0x180002f16  mov     [rax], r14
0x180002f19  mov     byte ptr [rbx+r14], 0
0x180002f1e  add     rsp, 38h
0x180002f22  pop     r14
0x180002f24  pop     rdi
0x180002f25  pop     rsi
0x180002f26  pop     rbx
0x180002f27  retn
0x180002f28  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
