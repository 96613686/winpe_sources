# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180006fe4`
- end: `0x1800070f7`
- name: `?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000424c`

## callees

- `0x180002a88`
- `0x180002bc8`
- `0x180002ed6`
- `0x180006fe4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800070c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800070c3`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  void *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, 2 * v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *((_WORD *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180006fe4  mov     [rsp+arg_10], r8
0x180006fe9  mov     [rsp+arg_8], rdx
0x180006fee  mov     [rsp+arg_0], rcx
0x180006ff3  push    rbx
0x180006ff4  push    rsi
0x180006ff5  push    rdi
0x180006ff6  push    r14
0x180006ff8  push    r15
0x180006ffa  sub     rsp, 20h
0x180006ffe  mov     r15, r8
0x180007001  mov     rdi, rdx
0x180007004  mov     rbx, rcx
0x180007007  or      rdx, 7
0x18000700b  mov     r9, 7FFFFFFFFFFFFFFEh
0x180007015  cmp     rdx, r9
0x180007018  ja      short loc_18000704E
0x18000701a  mov     rdi, rdx
0x18000701d  mov     r8, [rcx+18h]
0x180007021  mov     rcx, r8
0x180007024  shr     rcx, 1
0x180007027  mov     rax, 0AAAAAAAAAAAAAAABh
0x180007031  mul     rdx
0x180007034  shr     rdx, 1
0x180007037  cmp     rcx, rdx
0x18000703a  jbe     short loc_18000704E
0x18000703c  mov     rax, r9
0x18000703f  sub     rax, rcx
0x180007042  cmp     r8, rax
0x180007045  lea     rdi, [rcx+r8]
0x180007049  jbe     short loc_18000704E
0x18000704b  mov     rdi, r9
0x18000704e  lea     rcx, [rdi+1]
0x180007052  xor     esi, esi
0x180007054  test    rcx, rcx
0x180007057  jz      short loc_18000707E
0x180007059  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007063  cmp     rcx, rax
0x180007066  ja      loc_1800070F0
0x18000706c  add     rcx, rcx; Size
0x18000706f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007074  mov     r14, rax
0x180007077  test    rax, rax
0x18000707a  jz      short loc_1800070F0
0x18000707c  jmp     short loc_180007081
0x18000707e  mov     r14, rsi
0x180007081  jmp     short loc_180007099
0x180007083  xor     esi, esi
0x180007085  mov     rbx, [rsp+48h+arg_0]
0x18000708a  mov     r15, [rsp+48h+arg_10]
0x18000708f  mov     rdi, [rsp+48h+arg_8]
0x180007094  mov     r14, [rsp+48h+arg_18]
0x180007099  test    r15, r15
0x18000709c  jz      short loc_1800070B9
0x18000709e  cmp     qword ptr [rbx+18h], 8
0x1800070a3  jb      short loc_1800070AA
0x1800070a5  mov     rdx, [rbx]
0x1800070a8  jmp     short loc_1800070AD
0x1800070aa  mov     rdx, rbx; Src
0x1800070ad  lea     r8, [r15+r15]; Size
0x1800070b1  mov     rcx, r14; void *
0x1800070b4  call    memcpy_0
0x1800070b9  cmp     qword ptr [rbx+18h], 8
0x1800070be  jb      short loc_1800070C9
0x1800070c0  mov     rcx, [rbx]
0x1800070c3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800070c9  lea     rax, [rbx+10h]
0x1800070cd  mov     [rbx], r14
0x1800070d0  mov     [rbx+18h], rdi
0x1800070d4  cmp     rdi, 8
0x1800070d8  cmovnb  rbx, r14
0x1800070dc  mov     [rax], r15
0x1800070df  mov     [rbx+r15*2], si
0x1800070e4  add     rsp, 20h
0x1800070e8  pop     r15
0x1800070ea  pop     r14
0x1800070ec  pop     rdi
0x1800070ed  pop     rsi
0x1800070ee  pop     rbx
0x1800070ef  retn
0x1800070f0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
