# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001518`
- end: `0x18000160f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001728`
- `0x180001820`

## callees

- `0x180001344`
- `0x180001518`
- `0x180001678`
- `0x180002191`
- `0x1800022e6`

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
0x180001518  mov     rax, rsp
0x18000151b  mov     [rax+18h], r8
0x18000151f  mov     [rax+10h], rdx
0x180001523  mov     [rax+8], rcx
0x180001527  push    rbx
0x180001528  push    rsi
0x180001529  push    rdi
0x18000152a  push    r14
0x18000152c  sub     rsp, 38h
0x180001530  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001538  mov     r14, r8
0x18000153b  mov     rdi, rdx
0x18000153e  mov     rbx, rcx
0x180001541  or      rdx, 0Fh
0x180001545  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000154c  cmp     rdx, r9
0x18000154f  ja      short loc_180001585
0x180001551  mov     rdi, rdx
0x180001554  mov     r8, [rcx+18h]
0x180001558  mov     rcx, r8
0x18000155b  shr     rcx, 1
0x18000155e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001568  mul     rdx
0x18000156b  shr     rdx, 1
0x18000156e  cmp     rcx, rdx
0x180001571  jbe     short loc_180001585
0x180001573  mov     rax, r9
0x180001576  sub     rax, rcx
0x180001579  cmp     r8, rax
0x18000157c  lea     rdi, [rcx+r8]
0x180001580  jbe     short loc_180001585
0x180001582  mov     rdi, r9
0x180001585  lea     rcx, [rdi+1]; Size
0x180001589  test    rcx, rcx
0x18000158c  jz      short loc_18000159D
0x18000158e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001593  mov     rsi, rax
0x180001596  test    rax, rax
0x180001599  jz      short loc_180001608
0x18000159b  jmp     short loc_18000159F
0x18000159d  xor     esi, esi
0x18000159f  jmp     short loc_1800015B5
0x1800015a1  mov     rbx, [rsp+58h+arg_0]
0x1800015a6  mov     r14, [rsp+58h+arg_10]
0x1800015ab  mov     rdi, [rsp+58h+arg_8]
0x1800015b0  mov     rsi, [rsp+58h+arg_18]
0x1800015b5  test    r14, r14
0x1800015b8  jz      short loc_1800015D4
0x1800015ba  cmp     qword ptr [rbx+18h], 10h
0x1800015bf  jb      short loc_1800015C6
0x1800015c1  mov     rdx, [rbx]
0x1800015c4  jmp     short loc_1800015C9
0x1800015c6  mov     rdx, rbx; Src
0x1800015c9  mov     r8, r14; Size
0x1800015cc  mov     rcx, rsi; void *
0x1800015cf  call    memcpy_0
0x1800015d4  cmp     qword ptr [rbx+18h], 10h
0x1800015d9  jb      short loc_1800015E3
0x1800015db  mov     rcx, [rbx]; void *
0x1800015de  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800015e3  lea     rax, [rbx+10h]
0x1800015e7  mov     [rbx], rsi
0x1800015ea  mov     [rbx+18h], rdi
0x1800015ee  cmp     rdi, 10h
0x1800015f2  cmovnb  rbx, rsi
0x1800015f6  mov     [rax], r14
0x1800015f9  mov     byte ptr [rbx+r14], 0
0x1800015fe  add     rsp, 38h
0x180001602  pop     r14
0x180001604  pop     rdi
0x180001605  pop     rsi
0x180001606  pop     rbx
0x180001607  retn
0x180001608  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
