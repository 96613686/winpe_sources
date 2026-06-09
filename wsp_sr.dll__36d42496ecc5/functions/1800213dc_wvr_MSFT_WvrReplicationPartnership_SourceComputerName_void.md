# wvr::MSFT_WvrReplicationPartnership::SourceComputerName(void)

- ea: `0x1800213dc`
- end: `0x180021449`
- name: `?SourceComputerName@MSFT_WvrReplicationPartnership@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
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

- `0x180021400`: `SourceComputerName`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationPartnership::SourceComputerName(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"SourceComputerName");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x1800213dc  mov     [rsp+arg_0], rbx
0x1800213e1  push    rdi
0x1800213e2  sub     rsp, 60h
0x1800213e6  mov     rax, cs:__security_cookie
0x1800213ed  xor     rax, rsp
0x1800213f0  mov     [rsp+68h+var_18], rax
0x1800213f5  mov     rdi, rdx
0x1800213f8  mov     rbx, rcx
0x1800213fb  mov     [rsp+68h+var_40], rdx
0x180021400  lea     rdx, aSourcecomputer; "SourceComputerName"
0x180021407  lea     rcx, [rsp+68h+var_38]
0x18002140c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180021411  nop
0x180021412  lea     rdx, [rbx+8]
0x180021416  lea     r8, [rsp+68h+var_38]
0x18002141b  mov     rcx, rdi
0x18002141e  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180021423  nop
0x180021424  lea     rcx, [rsp+68h+var_38]
0x180021429  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002142e  mov     rax, rdi
0x180021431  mov     rcx, [rsp+68h+var_18]
0x180021436  xor     rcx, rsp; StackCookie
0x180021439  call    __security_check_cookie
0x18002143e  mov     rbx, [rsp+68h+arg_0]
0x180021443  add     rsp, 60h
0x180021447  pop     rdi
0x180021448  retn
```
