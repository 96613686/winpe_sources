# wvr::MSFT_WvrReplicationGroup::Description(void)

- ea: `0x180020960`
- end: `0x1800209ce`
- name: `?Description@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b5f8`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::Description(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"Description");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180020960  mov     [rsp+arg_0], rbx
0x180020965  push    rdi
0x180020966  sub     rsp, 60h
0x18002096a  mov     rax, cs:__security_cookie
0x180020971  xor     rax, rsp
0x180020974  mov     [rsp+68h+var_18], rax
0x180020979  mov     rdi, rdx
0x18002097c  mov     rbx, rcx
0x18002097f  mov     [rsp+68h+var_40], rdx
0x180020984  lea     rdx, aDescription; "Description"
0x18002098b  lea     rcx, [rsp+68h+var_38]
0x180020990  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020995  nop
0x180020996  lea     rdx, [rbx+8]
0x18002099a  lea     r8, [rsp+68h+var_38]
0x18002099f  mov     rcx, rdi
0x1800209a2  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x1800209a7  nop
0x1800209a8  lea     rcx, [rsp+68h+var_38]
0x1800209ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800209b2  mov     rax, rdi
0x1800209b5  mov     rcx, [rsp+68h+var_18]
0x1800209ba  xor     rcx, rsp; StackCookie
0x1800209bd  call    __security_check_cookie
0x1800209c2  mov     rbx, [rsp+68h+arg_0]
0x1800209c7  add     rsp, 60h
0x1800209cb  pop     rdi
0x1800209cc  retn
```
