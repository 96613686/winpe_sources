# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001cc8`
- end: `0x180001dbf`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001ed8`
- `0x180001fe4`

## callees

- `0x1800015ad`
- `0x180001ae8`
- `0x180001cc8`
- `0x180001e28`
- `0x1800024a8`

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
0x180001cc8  mov     rax, rsp
0x180001ccb  mov     [rax+18h], r8
0x180001ccf  mov     [rax+10h], rdx
0x180001cd3  mov     [rax+8], rcx
0x180001cd7  push    rbx
0x180001cd8  push    rsi
0x180001cd9  push    rdi
0x180001cda  push    r14
0x180001cdc  sub     rsp, 38h
0x180001ce0  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001ce8  mov     r14, r8
0x180001ceb  mov     rbx, rcx
0x180001cee  mov     rdi, rdx
0x180001cf1  or      rdi, 0Fh
0x180001cf5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180001cfc  cmp     rdi, r9
0x180001cff  jbe     short loc_180001D06
0x180001d01  mov     rdi, rdx
0x180001d04  jmp     short loc_180001D37
0x180001d06  mov     r8, [rcx+18h]
0x180001d0a  mov     rcx, r8
0x180001d0d  shr     rcx, 1
0x180001d10  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001d1a  mul     rdi
0x180001d1d  shr     rdx, 1
0x180001d20  cmp     rcx, rdx
0x180001d23  jbe     short loc_180001D37
0x180001d25  mov     rax, r9
0x180001d28  sub     rax, rcx
0x180001d2b  cmp     r8, rax
0x180001d2e  lea     rdi, [rcx+r8]
0x180001d32  jbe     short loc_180001D37
0x180001d34  mov     rdi, r9
0x180001d37  lea     rcx, [rdi+1]; Size
0x180001d3b  xor     esi, esi
0x180001d3d  test    rcx, rcx
0x180001d40  jz      short loc_180001D4F
0x180001d42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001d47  mov     rsi, rax
0x180001d4a  test    rax, rax
0x180001d4d  jz      short loc_180001DB8
0x180001d4f  jmp     short loc_180001D65
0x180001d51  mov     rbx, [rsp+58h+arg_0]
0x180001d56  mov     r14, [rsp+58h+arg_10]
0x180001d5b  mov     rdi, [rsp+58h+arg_8]
0x180001d60  mov     rsi, [rsp+58h+arg_18]
0x180001d65  test    r14, r14
0x180001d68  jz      short loc_180001D84
0x180001d6a  cmp     qword ptr [rbx+18h], 10h
0x180001d6f  jb      short loc_180001D76
0x180001d71  mov     rdx, [rbx]
0x180001d74  jmp     short loc_180001D79
0x180001d76  mov     rdx, rbx; Src
0x180001d79  mov     r8, r14; Size
0x180001d7c  mov     rcx, rsi; void *
0x180001d7f  call    memcpy_0
0x180001d84  cmp     qword ptr [rbx+18h], 10h
0x180001d89  jb      short loc_180001D93
0x180001d8b  mov     rcx, [rbx]; void *
0x180001d8e  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001d93  lea     rax, [rbx+10h]
0x180001d97  mov     [rbx], rsi
0x180001d9a  mov     [rbx+18h], rdi
0x180001d9e  cmp     rdi, 10h
0x180001da2  cmovnb  rbx, rsi
0x180001da6  mov     [rax], r14
0x180001da9  mov     byte ptr [rbx+r14], 0
0x180001dae  add     rsp, 38h
0x180001db2  pop     r14
0x180001db4  pop     rdi
0x180001db5  pop     rsi
0x180001db6  pop     rbx
0x180001db7  retn
0x180001db8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
