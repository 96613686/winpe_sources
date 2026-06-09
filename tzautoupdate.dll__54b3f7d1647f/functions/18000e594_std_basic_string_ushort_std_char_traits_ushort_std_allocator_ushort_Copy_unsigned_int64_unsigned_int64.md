# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000e594`
- end: `0x18000e69b`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `263`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000e73c`

## callees

- `0x180002050`
- `0x1800021f8`
- `0x18000e594`
- `0x18000e968`
- `0x18000eb88`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(_QWORD *a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  _QWORD *v10; // r14
  _QWORD *v11; // rdx
  _QWORD *result; // rax
  _QWORD *v13; // rax
  unsigned __int64 v14; // rcx
  _BYTE *v15; // rdx
  _BYTE v16[72]; // [rsp+0h] [rbp-48h] BYREF
  _QWORD *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = a1[3];
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
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
    v6 = (unsigned __int64)v16;
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
      std::wstring::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( v5[3] < 8u )
      v11 = v5;
    else
      v11 = (_QWORD *)*v5;
    std::char_traits<unsigned short>::copy(v10, v11, v3);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = v4;
  result = v5;
  if ( v4 >= 8 )
    result = v10;
  v5[2] = v3;
  *((_WORD *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000e594  mov     [rsp+arg_10], r8
0x18000e599  mov     [rsp+arg_8], rdx
0x18000e59e  mov     [rsp+arg_0], rcx
0x18000e5a3  push    rbx
0x18000e5a4  push    rsi
0x18000e5a5  push    rdi
0x18000e5a6  push    r14
0x18000e5a8  push    r15
0x18000e5aa  sub     rsp, 20h
0x18000e5ae  mov     r15, r8
0x18000e5b1  mov     rbx, rdx
0x18000e5b4  mov     rdi, rcx
0x18000e5b7  or      rdx, 7
0x18000e5bb  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000e5c5  cmp     rdx, r9
0x18000e5c8  ja      short loc_18000E5FE
0x18000e5ca  mov     rbx, rdx
0x18000e5cd  mov     r8, [rcx+18h]
0x18000e5d1  mov     rcx, r8
0x18000e5d4  shr     rcx, 1
0x18000e5d7  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000e5e1  mul     rdx
0x18000e5e4  shr     rdx, 1
0x18000e5e7  cmp     rcx, rdx
0x18000e5ea  jbe     short loc_18000E5FE
0x18000e5ec  mov     rax, r9
0x18000e5ef  sub     rax, rcx
0x18000e5f2  cmp     r8, rax
0x18000e5f5  lea     rbx, [rcx+r8]
0x18000e5f9  jbe     short loc_18000E5FE
0x18000e5fb  mov     rbx, r9
0x18000e5fe  lea     rcx, [rbx+1]
0x18000e602  xor     esi, esi
0x18000e604  test    rcx, rcx
0x18000e607  jz      short loc_18000E62D
0x18000e609  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000e613  cmp     rcx, rax
0x18000e616  ja      short loc_18000E628
0x18000e618  add     rcx, rcx; Size
0x18000e61b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e620  mov     r14, rax
0x18000e623  test    rax, rax
0x18000e626  jnz     short loc_18000E630
0x18000e628  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000e62d  mov     r14, rsi
0x18000e630  jmp     short loc_18000E648
0x18000e632  xor     esi, esi
0x18000e634  mov     rdi, [rsp+48h+arg_0]
0x18000e639  mov     r15, [rsp+48h+arg_10]
0x18000e63e  mov     rbx, [rsp+48h+arg_8]
0x18000e643  mov     r14, [rsp+48h+arg_18]
0x18000e648  test    r15, r15
0x18000e64b  jz      short loc_18000E667
0x18000e64d  cmp     qword ptr [rdi+18h], 8
0x18000e652  jb      short loc_18000E659
0x18000e654  mov     rdx, [rdi]
0x18000e657  jmp     short loc_18000E65C
0x18000e659  mov     rdx, rdi
0x18000e65c  mov     r8, r15
0x18000e65f  mov     rcx, r14
0x18000e662  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x18000e667  xor     r8d, r8d
0x18000e66a  mov     dl, 1
0x18000e66c  mov     rcx, rdi
0x18000e66f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000e674  mov     [rdi], r14
0x18000e677  mov     [rdi+18h], rbx
0x18000e67b  mov     rax, rdi
0x18000e67e  cmp     rbx, 8
0x18000e682  cmovnb  rax, r14
0x18000e686  mov     [rdi+10h], r15
0x18000e68a  mov     [rax+r15*2], si
0x18000e68f  add     rsp, 20h
0x18000e693  pop     r15
0x18000e695  pop     r14
0x18000e697  pop     rdi
0x18000e698  pop     rsi
0x18000e699  pop     rbx
0x18000e69a  retn
```
