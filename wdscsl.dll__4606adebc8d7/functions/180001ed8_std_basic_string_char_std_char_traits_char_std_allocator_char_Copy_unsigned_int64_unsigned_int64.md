# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001ed8`
- end: `0x180001fcf`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800020e8`
- `0x1800021f4`

## callees

- `0x1800018b5`
- `0x180001cf8`
- `0x180001ed8`
- `0x180002038`
- `0x1800026b8`

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
0x180001ed8  mov     rax, rsp
0x180001edb  mov     [rax+18h], r8
0x180001edf  mov     [rax+10h], rdx
0x180001ee3  mov     [rax+8], rcx
0x180001ee7  push    rbx
0x180001ee8  push    rsi
0x180001ee9  push    rdi
0x180001eea  push    r14
0x180001eec  sub     rsp, 38h
0x180001ef0  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001ef8  mov     r14, r8
0x180001efb  mov     rbx, rcx
0x180001efe  mov     rdi, rdx
0x180001f01  or      rdi, 0Fh
0x180001f05  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180001f0c  cmp     rdi, r9
0x180001f0f  jbe     short loc_180001F16
0x180001f11  mov     rdi, rdx
0x180001f14  jmp     short loc_180001F47
0x180001f16  mov     r8, [rcx+18h]
0x180001f1a  mov     rcx, r8
0x180001f1d  shr     rcx, 1
0x180001f20  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001f2a  mul     rdi
0x180001f2d  shr     rdx, 1
0x180001f30  cmp     rcx, rdx
0x180001f33  jbe     short loc_180001F47
0x180001f35  mov     rax, r9
0x180001f38  sub     rax, rcx
0x180001f3b  cmp     r8, rax
0x180001f3e  lea     rdi, [rcx+r8]
0x180001f42  jbe     short loc_180001F47
0x180001f44  mov     rdi, r9
0x180001f47  lea     rcx, [rdi+1]; Size
0x180001f4b  xor     esi, esi
0x180001f4d  test    rcx, rcx
0x180001f50  jz      short loc_180001F5F
0x180001f52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f57  mov     rsi, rax
0x180001f5a  test    rax, rax
0x180001f5d  jz      short loc_180001FC8
0x180001f5f  jmp     short loc_180001F75
0x180001f61  mov     rbx, [rsp+58h+arg_0]
0x180001f66  mov     r14, [rsp+58h+arg_10]
0x180001f6b  mov     rdi, [rsp+58h+arg_8]
0x180001f70  mov     rsi, [rsp+58h+arg_18]
0x180001f75  test    r14, r14
0x180001f78  jz      short loc_180001F94
0x180001f7a  cmp     qword ptr [rbx+18h], 10h
0x180001f7f  jb      short loc_180001F86
0x180001f81  mov     rdx, [rbx]
0x180001f84  jmp     short loc_180001F89
0x180001f86  mov     rdx, rbx; Src
0x180001f89  mov     r8, r14; Size
0x180001f8c  mov     rcx, rsi; void *
0x180001f8f  call    memcpy_0
0x180001f94  cmp     qword ptr [rbx+18h], 10h
0x180001f99  jb      short loc_180001FA3
0x180001f9b  mov     rcx, [rbx]; void *
0x180001f9e  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001fa3  lea     rax, [rbx+10h]
0x180001fa7  mov     [rbx], rsi
0x180001faa  mov     [rbx+18h], rdi
0x180001fae  cmp     rdi, 10h
0x180001fb2  cmovnb  rbx, rsi
0x180001fb6  mov     [rax], r14
0x180001fb9  mov     byte ptr [rbx+r14], 0
0x180001fbe  add     rsp, 38h
0x180001fc2  pop     r14
0x180001fc4  pop     rdi
0x180001fc5  pop     rsi
0x180001fc6  pop     rbx
0x180001fc7  retn
0x180001fc8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
