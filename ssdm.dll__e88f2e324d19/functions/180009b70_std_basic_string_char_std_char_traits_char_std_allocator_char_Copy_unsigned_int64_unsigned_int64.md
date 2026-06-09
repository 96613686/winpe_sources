# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180009b70`
- end: `0x180009c60`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180009ce0`
- `0x180009dd8`

## callees

- `0x180002a88`
- `0x180002bc8`
- `0x180002ed6`
- `0x180009b70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009c2e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009c2e`

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
0x180009b70  mov     [rsp+arg_10], r8
0x180009b75  mov     [rsp+arg_8], rdx
0x180009b7a  mov     [rsp+arg_0], rcx
0x180009b7f  push    rbx
0x180009b80  push    rsi
0x180009b81  push    rdi
0x180009b82  push    r14
0x180009b84  sub     rsp, 28h
0x180009b88  mov     r14, r8
0x180009b8b  mov     rdi, rdx
0x180009b8e  mov     rbx, rcx
0x180009b91  or      rdx, 0Fh
0x180009b95  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180009b9c  cmp     rdx, r9
0x180009b9f  ja      short loc_180009BD5
0x180009ba1  mov     rdi, rdx
0x180009ba4  mov     r8, [rcx+18h]
0x180009ba8  mov     rcx, r8
0x180009bab  shr     rcx, 1
0x180009bae  mov     rax, 0AAAAAAAAAAAAAAABh
0x180009bb8  mul     rdx
0x180009bbb  shr     rdx, 1
0x180009bbe  cmp     rcx, rdx
0x180009bc1  jbe     short loc_180009BD5
0x180009bc3  mov     rax, r9
0x180009bc6  sub     rax, rcx
0x180009bc9  cmp     r8, rax
0x180009bcc  lea     rdi, [rcx+r8]
0x180009bd0  jbe     short loc_180009BD5
0x180009bd2  mov     rdi, r9
0x180009bd5  lea     rcx, [rdi+1]; Size
0x180009bd9  test    rcx, rcx
0x180009bdc  jz      short loc_180009BED
0x180009bde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009be3  mov     rsi, rax
0x180009be6  test    rax, rax
0x180009be9  jz      short loc_180009C59
0x180009beb  jmp     short loc_180009BEF
0x180009bed  xor     esi, esi
0x180009bef  jmp     short loc_180009C05
0x180009bf1  mov     rbx, [rsp+48h+arg_0]
0x180009bf6  mov     r14, [rsp+48h+arg_10]
0x180009bfb  mov     rdi, [rsp+48h+arg_8]
0x180009c00  mov     rsi, [rsp+48h+arg_18]
0x180009c05  test    r14, r14
0x180009c08  jz      short loc_180009C24
0x180009c0a  cmp     qword ptr [rbx+18h], 10h
0x180009c0f  jb      short loc_180009C16
0x180009c11  mov     rdx, [rbx]
0x180009c14  jmp     short loc_180009C19
0x180009c16  mov     rdx, rbx; Src
0x180009c19  mov     r8, r14; Size
0x180009c1c  mov     rcx, rsi; void *
0x180009c1f  call    memcpy_0
0x180009c24  cmp     qword ptr [rbx+18h], 10h
0x180009c29  jb      short loc_180009C34
0x180009c2b  mov     rcx, [rbx]
0x180009c2e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009c34  lea     rax, [rbx+10h]
0x180009c38  mov     [rbx], rsi
0x180009c3b  mov     [rbx+18h], rdi
0x180009c3f  cmp     rdi, 10h
0x180009c43  cmovnb  rbx, rsi
0x180009c47  mov     [rax], r14
0x180009c4a  mov     byte ptr [rbx+r14], 0
0x180009c4f  add     rsp, 28h
0x180009c53  pop     r14
0x180009c55  pop     rdi
0x180009c56  pop     rsi
0x180009c57  pop     rbx
0x180009c58  retn
0x180009c59  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
