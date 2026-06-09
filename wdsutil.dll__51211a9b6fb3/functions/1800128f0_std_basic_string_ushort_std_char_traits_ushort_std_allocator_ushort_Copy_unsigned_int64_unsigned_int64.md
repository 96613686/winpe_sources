# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800128f0`
- end: `0x180012a12`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `290`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180012a18`
- `0x180012b44`
- `0x180012cbc`
- `0x180015c88`
- `0x18001d338`
- `0x18001d438`

## callees

- `0x180001374`
- `0x180001518`
- `0x180001d66`
- `0x1800128f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800129d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800129d7`

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
  _QWORD *v15; // rdx
  _QWORD v16[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v20; // [rsp+78h] [rbp+20h]

  v16[4] = -2;
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
      v15 = v16;
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
0x1800128f0  mov     rax, rsp
0x1800128f3  mov     [rax+18h], r8
0x1800128f7  mov     [rax+10h], rdx
0x1800128fb  mov     [rax+8], rcx
0x1800128ff  push    rbx
0x180012900  push    rsi
0x180012901  push    rdi
0x180012902  push    r14
0x180012904  push    r15
0x180012906  sub     rsp, 30h
0x18001290a  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180012912  mov     r15, r8
0x180012915  mov     rdi, rdx
0x180012918  mov     rbx, rcx
0x18001291b  or      rdx, 7
0x18001291f  mov     r9, 7FFFFFFFFFFFFFFEh
0x180012929  cmp     rdx, r9
0x18001292c  ja      short loc_180012962
0x18001292e  mov     rdi, rdx
0x180012931  mov     r8, [rcx+18h]
0x180012935  mov     rcx, r8
0x180012938  shr     rcx, 1
0x18001293b  mov     rax, 0AAAAAAAAAAAAAAABh
0x180012945  mul     rdx
0x180012948  shr     rdx, 1
0x18001294b  cmp     rcx, rdx
0x18001294e  jbe     short loc_180012962
0x180012950  mov     rax, r9
0x180012953  sub     rax, rcx
0x180012956  cmp     r8, rax
0x180012959  lea     rdi, [rcx+r8]
0x18001295d  jbe     short loc_180012962
0x18001295f  mov     rdi, r9
0x180012962  lea     rcx, [rdi+1]
0x180012966  xor     esi, esi
0x180012968  test    rcx, rcx
0x18001296b  jz      short loc_180012992
0x18001296d  mov     rax, 7FFFFFFFFFFFFFFFh
0x180012977  cmp     rcx, rax
0x18001297a  ja      loc_180012A0B
0x180012980  add     rcx, rcx; Size
0x180012983  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012988  mov     r14, rax
0x18001298b  test    rax, rax
0x18001298e  jz      short loc_180012A0B
0x180012990  jmp     short loc_180012995
0x180012992  mov     r14, rsi
0x180012995  jmp     short loc_1800129AD
0x180012997  xor     esi, esi
0x180012999  mov     rbx, [rsp+58h+arg_0]
0x18001299e  mov     r15, [rsp+58h+arg_10]
0x1800129a3  mov     rdi, [rsp+58h+arg_8]
0x1800129a8  mov     r14, [rsp+58h+arg_18]
0x1800129ad  test    r15, r15
0x1800129b0  jz      short loc_1800129CD
0x1800129b2  cmp     qword ptr [rbx+18h], 8
0x1800129b7  jb      short loc_1800129BE
0x1800129b9  mov     rdx, [rbx]
0x1800129bc  jmp     short loc_1800129C1
0x1800129be  mov     rdx, rbx; Src
0x1800129c1  lea     r8, [r15+r15]; Size
0x1800129c5  mov     rcx, r14; void *
0x1800129c8  call    memcpy_0
0x1800129cd  cmp     qword ptr [rbx+18h], 8
0x1800129d2  jb      short loc_1800129E3
0x1800129d4  mov     rcx, [rbx]
0x1800129d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800129de  nop     dword ptr [rax+rax+00h]
0x1800129e3  lea     rax, [rbx+10h]
0x1800129e7  mov     [rbx], r14
0x1800129ea  mov     [rbx+18h], rdi
0x1800129ee  cmp     rdi, 8
0x1800129f2  cmovnb  rbx, r14
0x1800129f6  mov     [rax], r15
0x1800129f9  mov     [rbx+r15*2], si
0x1800129fe  add     rsp, 30h
0x180012a02  pop     r15
0x180012a04  pop     r14
0x180012a06  pop     rdi
0x180012a07  pop     rsi
0x180012a08  pop     rbx
0x180012a09  retn
0x180012a0b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
