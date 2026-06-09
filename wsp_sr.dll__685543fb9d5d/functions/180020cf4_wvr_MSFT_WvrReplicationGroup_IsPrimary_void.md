# wvr::MSFT_WvrReplicationGroup::IsPrimary(void)

- ea: `0x180020cf4`
- end: `0x180020d62`
- name: `?IsPrimary@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@_N@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013b60`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::IsPrimary(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"IsPrimary");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180020cf4  mov     [rsp+arg_0], rbx
0x180020cf9  push    rdi
0x180020cfa  sub     rsp, 60h
0x180020cfe  mov     rax, cs:__security_cookie
0x180020d05  xor     rax, rsp
0x180020d08  mov     [rsp+68h+var_18], rax
0x180020d0d  mov     rdi, rdx
0x180020d10  mov     rbx, rcx
0x180020d13  mov     [rsp+68h+var_40], rdx
0x180020d18  lea     rdx, aIsprimary; "IsPrimary"
0x180020d1f  lea     rcx, [rsp+68h+var_38]
0x180020d24  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020d29  nop
0x180020d2a  lea     rdx, [rbx+8]
0x180020d2e  lea     r8, [rsp+68h+var_38]
0x180020d33  mov     rcx, rdi
0x180020d36  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020d3b  nop
0x180020d3c  lea     rcx, [rsp+68h+var_38]
0x180020d41  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020d46  mov     rax, rdi
0x180020d49  mov     rcx, [rsp+68h+var_18]
0x180020d4e  xor     rcx, rsp; StackCookie
0x180020d51  call    __security_check_cookie
0x180020d56  mov     rbx, [rsp+68h+arg_0]
0x180020d5b  add     rsp, 60h
0x180020d5f  pop     rdi
0x180020d60  retn
```
