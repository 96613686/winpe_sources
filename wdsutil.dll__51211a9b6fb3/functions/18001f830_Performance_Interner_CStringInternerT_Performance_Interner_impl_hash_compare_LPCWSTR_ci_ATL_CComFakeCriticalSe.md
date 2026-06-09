# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(ushort const *)

- ea: `0x18001f830`
- end: `0x18001f964`
- name: `?Intern@?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAAPEBGPEBG@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001fd04`

## callees

- `0x180001d66`
- `0x1800024a8`
- `0x18001d78c`
- `0x18001f830`
- `0x180020320`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001f8be`
- `msvcrt!_wcsicmp` at `0x18001f8da`
- `msvcrt!_wcsicmp` at `0x18001f8be`
- `msvcrt!_wcsicmp` at `0x18001f8da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
wchar_t *__fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(
        __int64 a1,
        const wchar_t *a2)
{
  wchar_t *result; // rax
  __int64 v5; // rax
  __int64 v6; // r14
  __int64 *i; // rbx
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  unsigned __int64 v11; // rbx
  _BYTE v12[24]; // [rsp+38h] [rbp-30h] BYREF
  wchar_t *v13; // [rsp+78h] [rbp+10h] BYREF

  v13 = (wchar_t *)a2;
  if ( !a2 )
    return 0;
  v5 = std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Hashval(
         a1,
         &v13);
  v6 = 2 * v5;
  for ( i = *(__int64 **)(*(_QWORD *)(a1 + 16) + 16 * v5); ; i = (__int64 *)*i )
  {
    v8 = *(__int64 **)a1;
    v9 = *(_QWORD *)(a1 + 16);
    if ( *(_QWORD *)(v9 + 8 * v6) != *(_QWORD *)a1 )
      v8 = **(__int64 ***)(v9 + 8 * v6 + 8);
    if ( i == v8 )
      break;
    if ( _wcsicmp((const wchar_t *)i[2], a2) >= 0 )
    {
      if ( _wcsicmp(a2, (const wchar_t *)i[2]) < 0 )
        i = *(__int64 **)a1;
      if ( i != *(__int64 **)a1 )
        return (wchar_t *)i[2];
      break;
    }
  }
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = v10 + 1;
  v13 = (wchar_t *)operator new[](saturated_mul(v11, 2u));
  memcpy_0(v13, a2, 2 * v11);
  try
  {
    std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Insert<unsigned short const * const &,std::_Nil>(
      (__int64 **)a1,
      (__int64)v12,
      (const wchar_t **)&v13);
    result = v13;
  }
  catch ( ... )
  {
    operator delete[](v13);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001f830  mov     rax, rsp
0x18001f833  mov     [rax+10h], rdx
0x18001f837  push    rdi
0x18001f838  push    r14
0x18001f83a  push    r15
0x18001f83c  sub     rsp, 50h
0x18001f840  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18001f848  mov     [rax+8], rbx
0x18001f84c  mov     [rax+18h], rsi
0x18001f850  mov     rsi, rdx
0x18001f853  mov     rdi, rcx
0x18001f856  xor     r15d, r15d
0x18001f859  test    rdx, rdx
0x18001f85c  jnz     short loc_18001F877
0x18001f85e  xor     eax, eax
0x18001f860  lea     r11, [rsp+68h+var_18]
0x18001f865  mov     rbx, [r11+20h]
0x18001f869  mov     rsi, [r11+30h]
0x18001f86d  mov     rsp, r11
0x18001f870  pop     r15
0x18001f872  pop     r14
0x18001f874  pop     rdi
0x18001f875  retn
0x18001f877  lea     rax, [rcx+40h]
0x18001f87b  mov     [rsp+68h+var_40], rax
0x18001f880  mov     [rsp+68h+var_38], 1
0x18001f885  lea     rdx, [rsp+68h+arg_8]
0x18001f88a  call    ?_Hashval@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA_KAEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Hashval(ushort const * const &)
0x18001f88f  mov     r14, rax
0x18001f892  add     r14, r14
0x18001f895  mov     rcx, [rdi+10h]
0x18001f899  mov     rbx, [rcx+r14*8]
0x18001f89d  mov     rcx, [rdi]
0x18001f8a0  mov     rax, [rdi+10h]
0x18001f8a4  cmp     [rax+r14*8], rcx
0x18001f8a8  jz      short loc_18001F8B2
0x18001f8aa  mov     rcx, [rax+r14*8+8]
0x18001f8af  mov     rcx, [rcx]
0x18001f8b2  cmp     rbx, rcx
0x18001f8b5  jz      short loc_18001F903
0x18001f8b7  mov     rdx, rsi; String2
0x18001f8ba  mov     rcx, [rbx+10h]; String1
0x18001f8be  call    cs:__imp__wcsicmp
0x18001f8c5  nop     dword ptr [rax+rax+00h]
0x18001f8ca  test    eax, eax
0x18001f8cc  jns     short loc_18001F8D3
0x18001f8ce  mov     rbx, [rbx]
0x18001f8d1  jmp     short loc_18001F89D
0x18001f8d3  mov     rdx, [rbx+10h]; String2
0x18001f8d7  mov     rcx, rsi; String1
0x18001f8da  call    cs:__imp__wcsicmp
0x18001f8e1  nop     dword ptr [rax+rax+00h]
0x18001f8e6  test    eax, eax
0x18001f8e8  jns     short loc_18001F8F2
0x18001f8ea  mov     rbx, [rdi]
0x18001f8ed  mov     rax, rbx
0x18001f8f0  jmp     short loc_18001F8F5
0x18001f8f2  mov     rax, [rdi]
0x18001f8f5  cmp     rbx, rax
0x18001f8f8  jz      short loc_18001F903
0x18001f8fa  mov     rax, [rbx+10h]
0x18001f8fe  jmp     loc_18001F860
0x18001f903  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f907  mov     rbx, rcx
0x18001f90a  inc     rbx
0x18001f90d  cmp     [rsi+rbx*2], r15w
0x18001f912  jnz     short loc_18001F90A
0x18001f914  inc     rbx
0x18001f917  mov     eax, 2
0x18001f91c  mul     rbx
0x18001f91f  cmovb   rax, rcx
0x18001f923  mov     rcx, rax; unsigned __int64
0x18001f926  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f92b  mov     [rsp+68h+arg_8], rax
0x18001f930  lea     r8, [rbx+rbx]; Size
0x18001f934  mov     rdx, rsi; Src
0x18001f937  mov     rcx, rax; void *
0x18001f93a  call    memcpy_0
0x18001f93f  nop
0x18001f940  mov     r9b, cs:byte_18004D349
0x18001f947  lea     r8, [rsp+68h+arg_8]
0x18001f94c  lea     rdx, [rsp+68h+var_30]
0x18001f951  mov     rcx, rdi
0x18001f954  call    ??$_Insert@AEBQEBGU_Nil@std@@@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@1@AEBQEBGU_Nil@1@@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Insert<ushort const * const &,std::_Nil>(ushort const * const &,std::_Nil)
0x18001f959  nop
0x18001f95a  mov     rax, [rsp+68h+arg_8]
0x18001f95f  jmp     loc_18001F860
```
