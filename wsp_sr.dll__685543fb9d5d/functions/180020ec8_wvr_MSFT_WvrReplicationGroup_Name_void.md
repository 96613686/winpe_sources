# wvr::MSFT_WvrReplicationGroup::Name(void)

- ea: `0x180020ec8`
- end: `0x180020f36`
- name: `?Name@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b5f8`
- `0x180013b60`
- `0x1800169ec`
- `0x180019904`
- `0x180021da4`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::Name(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"Name");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180020ec8  mov     [rsp+arg_0], rbx
0x180020ecd  push    rdi
0x180020ece  sub     rsp, 60h
0x180020ed2  mov     rax, cs:__security_cookie
0x180020ed9  xor     rax, rsp
0x180020edc  mov     [rsp+68h+var_18], rax
0x180020ee1  mov     rdi, rdx
0x180020ee4  mov     rbx, rcx
0x180020ee7  mov     [rsp+68h+var_40], rdx
0x180020eec  lea     rdx, aName; "Name"
0x180020ef3  lea     rcx, [rsp+68h+var_38]
0x180020ef8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020efd  nop
0x180020efe  lea     rdx, [rbx+8]
0x180020f02  lea     r8, [rsp+68h+var_38]
0x180020f07  mov     rcx, rdi
0x180020f0a  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020f0f  nop
0x180020f10  lea     rcx, [rsp+68h+var_38]
0x180020f15  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020f1a  mov     rax, rdi
0x180020f1d  mov     rcx, [rsp+68h+var_18]
0x180020f22  xor     rcx, rsp; StackCookie
0x180020f25  call    __security_check_cookie
0x180020f2a  mov     rbx, [rsp+68h+arg_0]
0x180020f2f  add     rsp, 60h
0x180020f33  pop     rdi
0x180020f34  retn
```
