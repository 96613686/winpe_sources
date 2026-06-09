# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001568`
- end: `0x18000165f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001778`
- `0x180001870`

## callees

- `0x180001390`
- `0x180001568`
- `0x1800016c8`
- `0x1800021b6`
- `0x180002686`

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
0x180001568  mov     rax, rsp
0x18000156b  mov     [rax+18h], r8
0x18000156f  mov     [rax+10h], rdx
0x180001573  mov     [rax+8], rcx
0x180001577  push    rbx
0x180001578  push    rsi
0x180001579  push    rdi
0x18000157a  push    r14
0x18000157c  sub     rsp, 38h
0x180001580  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001588  mov     r14, r8
0x18000158b  mov     rdi, rdx
0x18000158e  mov     rbx, rcx
0x180001591  or      rdx, 0Fh
0x180001595  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000159c  cmp     rdx, r9
0x18000159f  ja      short loc_1800015D5
0x1800015a1  mov     rdi, rdx
0x1800015a4  mov     r8, [rcx+18h]
0x1800015a8  mov     rcx, r8
0x1800015ab  shr     rcx, 1
0x1800015ae  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800015b8  mul     rdx
0x1800015bb  shr     rdx, 1
0x1800015be  cmp     rcx, rdx
0x1800015c1  jbe     short loc_1800015D5
0x1800015c3  mov     rax, r9
0x1800015c6  sub     rax, rcx
0x1800015c9  cmp     r8, rax
0x1800015cc  lea     rdi, [rcx+r8]
0x1800015d0  jbe     short loc_1800015D5
0x1800015d2  mov     rdi, r9
0x1800015d5  lea     rcx, [rdi+1]; Size
0x1800015d9  test    rcx, rcx
0x1800015dc  jz      short loc_1800015ED
0x1800015de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800015e3  mov     rsi, rax
0x1800015e6  test    rax, rax
0x1800015e9  jz      short loc_180001658
0x1800015eb  jmp     short loc_1800015EF
0x1800015ed  xor     esi, esi
0x1800015ef  jmp     short loc_180001605
0x1800015f1  mov     rbx, [rsp+58h+arg_0]
0x1800015f6  mov     r14, [rsp+58h+arg_10]
0x1800015fb  mov     rdi, [rsp+58h+arg_8]
0x180001600  mov     rsi, [rsp+58h+arg_18]
0x180001605  test    r14, r14
0x180001608  jz      short loc_180001624
0x18000160a  cmp     qword ptr [rbx+18h], 10h
0x18000160f  jb      short loc_180001616
0x180001611  mov     rdx, [rbx]
0x180001614  jmp     short loc_180001619
0x180001616  mov     rdx, rbx; Src
0x180001619  mov     r8, r14; Size
0x18000161c  mov     rcx, rsi; void *
0x18000161f  call    memcpy_0
0x180001624  cmp     qword ptr [rbx+18h], 10h
0x180001629  jb      short loc_180001633
0x18000162b  mov     rcx, [rbx]; void *
0x18000162e  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001633  lea     rax, [rbx+10h]
0x180001637  mov     [rbx], rsi
0x18000163a  mov     [rbx+18h], rdi
0x18000163e  cmp     rdi, 10h
0x180001642  cmovnb  rbx, rsi
0x180001646  mov     [rax], r14
0x180001649  mov     byte ptr [rbx+r14], 0
0x18000164e  add     rsp, 38h
0x180001652  pop     r14
0x180001654  pop     rdi
0x180001655  pop     rsi
0x180001656  pop     rbx
0x180001657  retn
0x180001658  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
