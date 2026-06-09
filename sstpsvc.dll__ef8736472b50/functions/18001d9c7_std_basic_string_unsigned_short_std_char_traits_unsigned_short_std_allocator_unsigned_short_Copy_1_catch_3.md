# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$3

- ea: `0x18001d9c7`
- end: `0x18001da5b`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$3`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008f6c`
- `0x18000983e`
- `0x18001d9c7`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001da1c`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001da1c`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 136);
  *(_QWORD *)(a2 + 136) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
    {
      *(_QWORD *)(a2 + 136) = 0;
      exception::exception((exception *)(a2 + 56), (const char *const *)(a2 + 136));
      *(_QWORD *)(a2 + 56) = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)(a2 + 56);
    }
  }
  *(_QWORD *)(a2 + 152) = v4;
  return 0;
}

```

## disassembly

```asm
0x18001d9c7  mov     [rsp+arg_8], rdx
0x18001d9cc  push    rbp
0x18001d9cd  sub     rsp, 20h
0x18001d9d1  mov     rbp, rdx
0x18001d9d4  mov     rcx, [rbp+88h]
0x18001d9db  mov     [rbp+88h], rcx
0x18001d9e2  xor     eax, eax
0x18001d9e4  add     rcx, 1
0x18001d9e8  jz      short loc_18001DA43
0x18001d9ea  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001d9f4  cmp     rcx, rax
0x18001d9f7  ja      short loc_18001DA06
0x18001d9f9  add     rcx, rcx; Size
0x18001d9fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001da01  test    rax, rax
0x18001da04  jnz     short loc_18001DA43
0x18001da06  mov     qword ptr [rbp+88h], 0
0x18001da11  lea     rdx, [rbp+88h]
0x18001da18  lea     rcx, [rbp+38h]
0x18001da1c  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001da23  nop     dword ptr [rax+rax+00h]
0x18001da28  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001da2f  mov     [rbp+38h], rax
0x18001da33  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001da3a  lea     rcx, [rbp+38h]; pExceptionObject
0x18001da3e  call    _CxxThrowException_0
0x18001da43  mov     [rbp+98h], rax
0x18001da4a  mov     rax, 0
0x18001da54  add     rsp, 20h
0x18001da58  pop     rbp
0x18001da59  retn
```
