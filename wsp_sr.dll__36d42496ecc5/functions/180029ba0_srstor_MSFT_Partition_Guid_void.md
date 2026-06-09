# srstor::MSFT_Partition::Guid(void)

- ea: `0x180029ba0`
- end: `0x180029c0d`
- name: `?Guid@MSFT_Partition@srstor@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002216c`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall srstor::MSFT_Partition::Guid(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"Guid");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180029ba0  mov     [rsp+arg_0], rbx
0x180029ba5  push    rdi
0x180029ba6  sub     rsp, 60h
0x180029baa  mov     rax, cs:__security_cookie
0x180029bb1  xor     rax, rsp
0x180029bb4  mov     [rsp+68h+var_18], rax
0x180029bb9  mov     rdi, rdx
0x180029bbc  mov     rbx, rcx
0x180029bbf  mov     [rsp+68h+var_40], rdx
0x180029bc4  lea     rdx, aGuid; "Guid"
0x180029bcb  lea     rcx, [rsp+68h+var_38]
0x180029bd0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180029bd5  nop
0x180029bd6  lea     rdx, [rbx+8]
0x180029bda  lea     r8, [rsp+68h+var_38]
0x180029bdf  mov     rcx, rdi
0x180029be2  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180029be7  nop
0x180029be8  lea     rcx, [rsp+68h+var_38]
0x180029bed  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029bf2  mov     rax, rdi
0x180029bf5  mov     rcx, [rsp+68h+var_18]
0x180029bfa  xor     rcx, rsp; StackCookie
0x180029bfd  call    __security_check_cookie
0x180029c02  mov     rbx, [rsp+68h+arg_0]
0x180029c07  add     rsp, 60h
0x180029c0b  pop     rdi
0x180029c0c  retn
```
