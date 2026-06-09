# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001f2c`
- end: `0x18000201b`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `239`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800020b4`
- `0x1800021ac`

## callees

- `0x1800012d8`
- `0x180001ac6`
- `0x180001f2c`
- `0x18000262c`
- `0x1800026c0`

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
0x180001f2c  mov     [rsp+arg_10], r8
0x180001f31  mov     [rsp+arg_8], rdx
0x180001f36  mov     [rsp+arg_0], rcx
0x180001f3b  push    rbx
0x180001f3c  push    rsi
0x180001f3d  push    rdi
0x180001f3e  push    r14
0x180001f40  sub     rsp, 28h
0x180001f44  mov     r14, r8
0x180001f47  mov     rdi, rdx
0x180001f4a  mov     rbx, rcx
0x180001f4d  or      rdx, 0Fh
0x180001f51  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180001f58  cmp     rdx, r9
0x180001f5b  ja      short loc_180001F91
0x180001f5d  mov     rdi, rdx
0x180001f60  mov     r8, [rcx+18h]
0x180001f64  mov     rcx, r8
0x180001f67  shr     rcx, 1
0x180001f6a  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001f74  mul     rdx
0x180001f77  shr     rdx, 1
0x180001f7a  cmp     rcx, rdx
0x180001f7d  jbe     short loc_180001F91
0x180001f7f  mov     rax, r9
0x180001f82  sub     rax, rcx
0x180001f85  cmp     r8, rax
0x180001f88  lea     rdi, [rcx+r8]
0x180001f8c  jbe     short loc_180001F91
0x180001f8e  mov     rdi, r9
0x180001f91  lea     rcx, [rdi+1]; dwBytes
0x180001f95  test    rcx, rcx
0x180001f98  jz      short loc_180001FA9
0x180001f9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f9f  mov     rsi, rax
0x180001fa2  test    rax, rax
0x180001fa5  jz      short loc_180002014
0x180001fa7  jmp     short loc_180001FAB
0x180001fa9  xor     esi, esi
0x180001fab  jmp     short loc_180001FC1
0x180001fad  mov     rbx, [rsp+48h+arg_0]
0x180001fb2  mov     r14, [rsp+48h+arg_10]
0x180001fb7  mov     rdi, [rsp+48h+arg_8]
0x180001fbc  mov     rsi, [rsp+48h+arg_18]
0x180001fc1  test    r14, r14
0x180001fc4  jz      short loc_180001FE0
0x180001fc6  cmp     qword ptr [rbx+18h], 10h
0x180001fcb  jb      short loc_180001FD2
0x180001fcd  mov     rdx, [rbx]
0x180001fd0  jmp     short loc_180001FD5
0x180001fd2  mov     rdx, rbx; Src
0x180001fd5  mov     r8, r14; Size
0x180001fd8  mov     rcx, rsi; void *
0x180001fdb  call    memcpy_0
0x180001fe0  cmp     qword ptr [rbx+18h], 10h
0x180001fe5  jb      short loc_180001FEF
0x180001fe7  mov     rcx, [rbx]; void *
0x180001fea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001fef  lea     rax, [rbx+10h]
0x180001ff3  mov     [rbx], rsi
0x180001ff6  mov     [rbx+18h], rdi
0x180001ffa  cmp     rdi, 10h
0x180001ffe  cmovnb  rbx, rsi
0x180002002  mov     [rax], r14
0x180002005  mov     byte ptr [rbx+r14], 0
0x18000200a  add     rsp, 28h
0x18000200e  pop     r14
0x180002010  pop     rdi
0x180002011  pop     rsi
0x180002012  pop     rbx
0x180002013  retn
0x180002014  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
