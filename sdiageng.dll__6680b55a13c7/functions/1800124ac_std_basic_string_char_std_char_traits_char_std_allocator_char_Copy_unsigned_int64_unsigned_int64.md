# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800124ac`
- end: `0x18001259b`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `239`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800126b4`
- `0x1800127ac`

## callees

- `0x180001264`
- `0x1800012a4`
- `0x180001488`
- `0x180001ca6`
- `0x1800124ac`

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
0x1800124ac  mov     [rsp+arg_10], r8
0x1800124b1  mov     [rsp+arg_8], rdx
0x1800124b6  mov     [rsp+arg_0], rcx
0x1800124bb  push    rbx
0x1800124bc  push    rsi
0x1800124bd  push    rdi
0x1800124be  push    r14
0x1800124c0  sub     rsp, 28h
0x1800124c4  mov     r14, r8
0x1800124c7  mov     rdi, rdx
0x1800124ca  mov     rbx, rcx
0x1800124cd  or      rdx, 0Fh
0x1800124d1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800124d8  cmp     rdx, r9
0x1800124db  ja      short loc_180012511
0x1800124dd  mov     rdi, rdx
0x1800124e0  mov     r8, [rcx+18h]
0x1800124e4  mov     rcx, r8
0x1800124e7  shr     rcx, 1
0x1800124ea  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800124f4  mul     rdx
0x1800124f7  shr     rdx, 1
0x1800124fa  cmp     rcx, rdx
0x1800124fd  jbe     short loc_180012511
0x1800124ff  mov     rax, r9
0x180012502  sub     rax, rcx
0x180012505  cmp     r8, rax
0x180012508  lea     rdi, [rcx+r8]
0x18001250c  jbe     short loc_180012511
0x18001250e  mov     rdi, r9
0x180012511  lea     rcx, [rdi+1]; Size
0x180012515  test    rcx, rcx
0x180012518  jz      short loc_180012529
0x18001251a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001251f  mov     rsi, rax
0x180012522  test    rax, rax
0x180012525  jz      short loc_180012594
0x180012527  jmp     short loc_18001252B
0x180012529  xor     esi, esi
0x18001252b  jmp     short loc_180012541
0x18001252d  mov     rbx, [rsp+48h+arg_0]
0x180012532  mov     r14, [rsp+48h+arg_10]
0x180012537  mov     rdi, [rsp+48h+arg_8]
0x18001253c  mov     rsi, [rsp+48h+arg_18]
0x180012541  test    r14, r14
0x180012544  jz      short loc_180012560
0x180012546  cmp     qword ptr [rbx+18h], 10h
0x18001254b  jb      short loc_180012552
0x18001254d  mov     rdx, [rbx]
0x180012550  jmp     short loc_180012555
0x180012552  mov     rdx, rbx; Src
0x180012555  mov     r8, r14; Size
0x180012558  mov     rcx, rsi; void *
0x18001255b  call    memcpy_0
0x180012560  cmp     qword ptr [rbx+18h], 10h
0x180012565  jb      short loc_18001256F
0x180012567  mov     rcx, [rbx]; Block
0x18001256a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001256f  lea     rax, [rbx+10h]
0x180012573  mov     [rbx], rsi
0x180012576  mov     [rbx+18h], rdi
0x18001257a  cmp     rdi, 10h
0x18001257e  cmovnb  rbx, rsi
0x180012582  mov     [rax], r14
0x180012585  mov     byte ptr [rbx+r14], 0
0x18001258a  add     rsp, 28h
0x18001258e  pop     r14
0x180012590  pop     rdi
0x180012591  pop     rsi
0x180012592  pop     rbx
0x180012593  retn
0x180012594  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
