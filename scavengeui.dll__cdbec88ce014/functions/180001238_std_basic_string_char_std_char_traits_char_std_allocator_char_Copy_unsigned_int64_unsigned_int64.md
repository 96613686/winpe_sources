# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001238`
- end: `0x18000132f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001448`
- `0x180001540`

## callees

- `0x180001064`
- `0x180001238`
- `0x180001398`
- `0x180001e86`
- `0x180002026`

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
0x180001238  mov     rax, rsp
0x18000123b  mov     [rax+18h], r8
0x18000123f  mov     [rax+10h], rdx
0x180001243  mov     [rax+8], rcx
0x180001247  push    rbx
0x180001248  push    rsi
0x180001249  push    rdi
0x18000124a  push    r14
0x18000124c  sub     rsp, 38h
0x180001250  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001258  mov     r14, r8
0x18000125b  mov     rdi, rdx
0x18000125e  mov     rbx, rcx
0x180001261  or      rdx, 0Fh
0x180001265  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000126c  cmp     rdx, r9
0x18000126f  ja      short loc_1800012A5
0x180001271  mov     rdi, rdx
0x180001274  mov     r8, [rcx+18h]
0x180001278  mov     rcx, r8
0x18000127b  shr     rcx, 1
0x18000127e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001288  mul     rdx
0x18000128b  shr     rdx, 1
0x18000128e  cmp     rcx, rdx
0x180001291  jbe     short loc_1800012A5
0x180001293  mov     rax, r9
0x180001296  sub     rax, rcx
0x180001299  cmp     r8, rax
0x18000129c  lea     rdi, [rcx+r8]
0x1800012a0  jbe     short loc_1800012A5
0x1800012a2  mov     rdi, r9
0x1800012a5  lea     rcx, [rdi+1]; Size
0x1800012a9  test    rcx, rcx
0x1800012ac  jz      short loc_1800012BD
0x1800012ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800012b3  mov     rsi, rax
0x1800012b6  test    rax, rax
0x1800012b9  jz      short loc_180001328
0x1800012bb  jmp     short loc_1800012BF
0x1800012bd  xor     esi, esi
0x1800012bf  jmp     short loc_1800012D5
0x1800012c1  mov     rbx, [rsp+58h+arg_0]
0x1800012c6  mov     r14, [rsp+58h+arg_10]
0x1800012cb  mov     rdi, [rsp+58h+arg_8]
0x1800012d0  mov     rsi, [rsp+58h+arg_18]
0x1800012d5  test    r14, r14
0x1800012d8  jz      short loc_1800012F4
0x1800012da  cmp     qword ptr [rbx+18h], 10h
0x1800012df  jb      short loc_1800012E6
0x1800012e1  mov     rdx, [rbx]
0x1800012e4  jmp     short loc_1800012E9
0x1800012e6  mov     rdx, rbx; Src
0x1800012e9  mov     r8, r14; Size
0x1800012ec  mov     rcx, rsi; void *
0x1800012ef  call    memcpy_0
0x1800012f4  cmp     qword ptr [rbx+18h], 10h
0x1800012f9  jb      short loc_180001303
0x1800012fb  mov     rcx, [rbx]; void *
0x1800012fe  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001303  lea     rax, [rbx+10h]
0x180001307  mov     [rbx], rsi
0x18000130a  mov     [rbx+18h], rdi
0x18000130e  cmp     rdi, 10h
0x180001312  cmovnb  rbx, rsi
0x180001316  mov     [rax], r14
0x180001319  mov     byte ptr [rbx+r14], 0
0x18000131e  add     rsp, 38h
0x180001322  pop     r14
0x180001324  pop     rdi
0x180001325  pop     rsi
0x180001326  pop     rbx
0x180001327  retn
0x180001328  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
