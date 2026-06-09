# wvr::MSFT_WvrReplicationPartnership::DestinationComputerName(void)

- ea: `0x180021138`
- end: `0x1800211a5`
- name: `?DestinationComputerName@MSFT_WvrReplicationPartnership@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008a04`
- `0x180011e78`
- `0x1800148d8`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## string_xrefs

- `0x18002115c`: `DestinationComputerName`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationPartnership::DestinationComputerName(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"DestinationComputerName");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180021138  mov     [rsp+arg_0], rbx
0x18002113d  push    rdi
0x18002113e  sub     rsp, 60h
0x180021142  mov     rax, cs:__security_cookie
0x180021149  xor     rax, rsp
0x18002114c  mov     [rsp+68h+var_18], rax
0x180021151  mov     rdi, rdx
0x180021154  mov     rbx, rcx
0x180021157  mov     [rsp+68h+var_40], rdx
0x18002115c  lea     rdx, aDestinationcom; "DestinationComputerName"
0x180021163  lea     rcx, [rsp+68h+var_38]
0x180021168  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002116d  nop
0x18002116e  lea     rdx, [rbx+8]
0x180021172  lea     r8, [rsp+68h+var_38]
0x180021177  mov     rcx, rdi
0x18002117a  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x18002117f  nop
0x180021180  lea     rcx, [rsp+68h+var_38]
0x180021185  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002118a  mov     rax, rdi
0x18002118d  mov     rcx, [rsp+68h+var_18]
0x180021192  xor     rcx, rsp; StackCookie
0x180021195  call    __security_check_cookie
0x18002119a  mov     rbx, [rsp+68h+arg_0]
0x18002119f  add     rsp, 60h
0x1800211a3  pop     rdi
0x1800211a4  retn
```
