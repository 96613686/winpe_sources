# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000f978`
- end: `0x18000fa6f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000fb88`
- `0x18000fc80`

## callees

- `0x18000a044`
- `0x18000a61c`
- `0x18000f978`
- `0x18000fad8`
- `0x1800101e4`

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
0x18000f978  mov     rax, rsp
0x18000f97b  mov     [rax+18h], r8
0x18000f97f  mov     [rax+10h], rdx
0x18000f983  mov     [rax+8], rcx
0x18000f987  push    rbx
0x18000f988  push    rsi
0x18000f989  push    rdi
0x18000f98a  push    r14
0x18000f98c  sub     rsp, 38h
0x18000f990  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18000f998  mov     r14, r8
0x18000f99b  mov     rdi, rdx
0x18000f99e  mov     rbx, rcx
0x18000f9a1  or      rdx, 0Fh
0x18000f9a5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000f9ac  cmp     rdx, r9
0x18000f9af  ja      short loc_18000F9E5
0x18000f9b1  mov     rdi, rdx
0x18000f9b4  mov     r8, [rcx+18h]
0x18000f9b8  mov     rcx, r8
0x18000f9bb  shr     rcx, 1
0x18000f9be  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000f9c8  mul     rdx
0x18000f9cb  shr     rdx, 1
0x18000f9ce  cmp     rcx, rdx
0x18000f9d1  jbe     short loc_18000F9E5
0x18000f9d3  mov     rax, r9
0x18000f9d6  sub     rax, rcx
0x18000f9d9  cmp     r8, rax
0x18000f9dc  lea     rdi, [rcx+r8]
0x18000f9e0  jbe     short loc_18000F9E5
0x18000f9e2  mov     rdi, r9
0x18000f9e5  lea     rcx, [rdi+1]; unsigned __int64
0x18000f9e9  test    rcx, rcx
0x18000f9ec  jz      short loc_18000F9FD
0x18000f9ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f9f3  mov     rsi, rax
0x18000f9f6  test    rax, rax
0x18000f9f9  jz      short loc_18000FA68
0x18000f9fb  jmp     short loc_18000F9FF
0x18000f9fd  xor     esi, esi
0x18000f9ff  jmp     short loc_18000FA15
0x18000fa01  mov     rbx, [rsp+58h+arg_0]
0x18000fa06  mov     r14, [rsp+58h+arg_10]
0x18000fa0b  mov     rdi, [rsp+58h+arg_8]
0x18000fa10  mov     rsi, [rsp+58h+arg_18]
0x18000fa15  test    r14, r14
0x18000fa18  jz      short loc_18000FA34
0x18000fa1a  cmp     qword ptr [rbx+18h], 10h
0x18000fa1f  jb      short loc_18000FA26
0x18000fa21  mov     rdx, [rbx]
0x18000fa24  jmp     short loc_18000FA29
0x18000fa26  mov     rdx, rbx; Src
0x18000fa29  mov     r8, r14; Size
0x18000fa2c  mov     rcx, rsi; void *
0x18000fa2f  call    memcpy_0
0x18000fa34  cmp     qword ptr [rbx+18h], 10h
0x18000fa39  jb      short loc_18000FA43
0x18000fa3b  mov     rcx, [rbx]; void *
0x18000fa3e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fa43  lea     rax, [rbx+10h]
0x18000fa47  mov     [rbx], rsi
0x18000fa4a  mov     [rbx+18h], rdi
0x18000fa4e  cmp     rdi, 10h
0x18000fa52  cmovnb  rbx, rsi
0x18000fa56  mov     [rax], r14
0x18000fa59  mov     byte ptr [rbx+r14], 0
0x18000fa5e  add     rsp, 38h
0x18000fa62  pop     r14
0x18000fa64  pop     rdi
0x18000fa65  pop     rsi
0x18000fa66  pop     rbx
0x18000fa67  retn
0x18000fa68  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
