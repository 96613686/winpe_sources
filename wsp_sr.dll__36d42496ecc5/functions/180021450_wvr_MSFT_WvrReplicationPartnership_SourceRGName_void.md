# wvr::MSFT_WvrReplicationPartnership::SourceRGName(void)

- ea: `0x180021450`
- end: `0x1800214bd`
- name: `?SourceRGName@MSFT_WvrReplicationPartnership@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008a04`
- `0x180011e78`
- `0x1800148d8`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationPartnership::SourceRGName(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"SourceRGName");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180021450  mov     [rsp+arg_0], rbx
0x180021455  push    rdi
0x180021456  sub     rsp, 60h
0x18002145a  mov     rax, cs:__security_cookie
0x180021461  xor     rax, rsp
0x180021464  mov     [rsp+68h+var_18], rax
0x180021469  mov     rdi, rdx
0x18002146c  mov     rbx, rcx
0x18002146f  mov     [rsp+68h+var_40], rdx
0x180021474  lea     rdx, aSourcergname; "SourceRGName"
0x18002147b  lea     rcx, [rsp+68h+var_38]
0x180021480  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180021485  nop
0x180021486  lea     rdx, [rbx+8]
0x18002148a  lea     r8, [rsp+68h+var_38]
0x18002148f  mov     rcx, rdi
0x180021492  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180021497  nop
0x180021498  lea     rcx, [rsp+68h+var_38]
0x18002149d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800214a2  mov     rax, rdi
0x1800214a5  mov     rcx, [rsp+68h+var_18]
0x1800214aa  xor     rcx, rsp; StackCookie
0x1800214ad  call    __security_check_cookie
0x1800214b2  mov     rbx, [rsp+68h+arg_0]
0x1800214b7  add     rsp, 60h
0x1800214bb  pop     rdi
0x1800214bc  retn
```
