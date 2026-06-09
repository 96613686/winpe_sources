# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800021a8`
- end: `0x18000229f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800023b8`
- `0x1800024c4`

## callees

- `0x180001abd`
- `0x180001fd4`
- `0x1800021a8`
- `0x180002308`
- `0x180002988`

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
0x1800021a8  mov     rax, rsp
0x1800021ab  mov     [rax+18h], r8
0x1800021af  mov     [rax+10h], rdx
0x1800021b3  mov     [rax+8], rcx
0x1800021b7  push    rbx
0x1800021b8  push    rsi
0x1800021b9  push    rdi
0x1800021ba  push    r14
0x1800021bc  sub     rsp, 38h
0x1800021c0  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1800021c8  mov     r14, r8
0x1800021cb  mov     rbx, rcx
0x1800021ce  mov     rdi, rdx
0x1800021d1  or      rdi, 0Fh
0x1800021d5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800021dc  cmp     rdi, r9
0x1800021df  jbe     short loc_1800021E6
0x1800021e1  mov     rdi, rdx
0x1800021e4  jmp     short loc_180002217
0x1800021e6  mov     r8, [rcx+18h]
0x1800021ea  mov     rcx, r8
0x1800021ed  shr     rcx, 1
0x1800021f0  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800021fa  mul     rdi
0x1800021fd  shr     rdx, 1
0x180002200  cmp     rcx, rdx
0x180002203  jbe     short loc_180002217
0x180002205  mov     rax, r9
0x180002208  sub     rax, rcx
0x18000220b  cmp     r8, rax
0x18000220e  lea     rdi, [rcx+r8]
0x180002212  jbe     short loc_180002217
0x180002214  mov     rdi, r9
0x180002217  lea     rcx, [rdi+1]; Size
0x18000221b  xor     esi, esi
0x18000221d  test    rcx, rcx
0x180002220  jz      short loc_18000222F
0x180002222  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002227  mov     rsi, rax
0x18000222a  test    rax, rax
0x18000222d  jz      short loc_180002298
0x18000222f  jmp     short loc_180002245
0x180002231  mov     rbx, [rsp+58h+arg_0]
0x180002236  mov     r14, [rsp+58h+arg_10]
0x18000223b  mov     rdi, [rsp+58h+arg_8]
0x180002240  mov     rsi, [rsp+58h+arg_18]
0x180002245  test    r14, r14
0x180002248  jz      short loc_180002264
0x18000224a  cmp     qword ptr [rbx+18h], 10h
0x18000224f  jb      short loc_180002256
0x180002251  mov     rdx, [rbx]
0x180002254  jmp     short loc_180002259
0x180002256  mov     rdx, rbx; Src
0x180002259  mov     r8, r14; Size
0x18000225c  mov     rcx, rsi; void *
0x18000225f  call    memcpy_0
0x180002264  cmp     qword ptr [rbx+18h], 10h
0x180002269  jb      short loc_180002273
0x18000226b  mov     rcx, [rbx]; void *
0x18000226e  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180002273  lea     rax, [rbx+10h]
0x180002277  mov     [rbx], rsi
0x18000227a  mov     [rbx+18h], rdi
0x18000227e  cmp     rdi, 10h
0x180002282  cmovnb  rbx, rsi
0x180002286  mov     [rax], r14
0x180002289  mov     byte ptr [rbx+r14], 0
0x18000228e  add     rsp, 38h
0x180002292  pop     r14
0x180002294  pop     rdi
0x180002295  pop     rsi
0x180002296  pop     rbx
0x180002297  retn
0x180002298  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
