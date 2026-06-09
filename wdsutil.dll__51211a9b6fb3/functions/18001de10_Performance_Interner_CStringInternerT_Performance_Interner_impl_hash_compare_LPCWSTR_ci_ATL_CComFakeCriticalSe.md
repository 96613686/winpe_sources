# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(void)

- ea: `0x18001de10`
- end: `0x18001de4c`
- name: `??1?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032ed3`

## callees

- `0x18001de10`
- `0x18001de54`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001de2c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001de2c`

## pseudocode

```c
void __fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(
        __int64 **a1)
{
  __int64 *i; // rbx

  for ( i = *a1; ; operator delete[]((void *)i[2]) )
  {
    i = (__int64 *)*i;
    if ( i == *a1 )
      break;
  }
  std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::~_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>((__int64)a1);
}

```

## disassembly

```asm
0x18001de10  mov     [rsp+arg_0], rbx
0x18001de15  push    rdi
0x18001de16  sub     rsp, 20h
0x18001de1a  mov     rbx, [rcx]
0x18001de1d  mov     rdi, rcx
0x18001de20  mov     rbx, [rbx]
0x18001de23  cmp     rbx, [rdi]
0x18001de26  jz      short loc_18001DE3A
0x18001de28  mov     rcx, [rbx+10h]
0x18001de2c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001de33  nop     dword ptr [rax+rax+00h]
0x18001de38  jmp     short loc_18001DE20
0x18001de3a  mov     rcx, rdi
0x18001de3d  mov     rbx, [rsp+28h+arg_0]
0x18001de42  add     rsp, 20h
0x18001de46  pop     rdi
0x18001de47  jmp     ??1?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::~_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>(void)
```
