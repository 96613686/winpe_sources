# wvr::MSFT_WvrReplicationGroup::Name(void)

- ea: `0x180020d64`
- end: `0x180020dd1`
- name: `?Name@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b48c`
- `0x180013c50`
- `0x180016b28`
- `0x1800198cc`
- `0x180021bfc`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::Name(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"Name");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020d64  mov     [rsp+arg_0], rbx
0x180020d69  push    rdi
0x180020d6a  sub     rsp, 60h
0x180020d6e  mov     rax, cs:__security_cookie
0x180020d75  xor     rax, rsp
0x180020d78  mov     [rsp+68h+var_18], rax
0x180020d7d  mov     rdi, rdx
0x180020d80  mov     rbx, rcx
0x180020d83  mov     [rsp+68h+var_40], rdx
0x180020d88  lea     rdx, aName; "Name"
0x180020d8f  lea     rcx, [rsp+68h+var_38]
0x180020d94  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020d99  nop
0x180020d9a  lea     rdx, [rbx+8]
0x180020d9e  lea     r8, [rsp+68h+var_38]
0x180020da3  mov     rcx, rdi
0x180020da6  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020dab  nop
0x180020dac  lea     rcx, [rsp+68h+var_38]
0x180020db1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020db6  mov     rax, rdi
0x180020db9  mov     rcx, [rsp+68h+var_18]
0x180020dbe  xor     rcx, rsp; StackCookie
0x180020dc1  call    __security_check_cookie
0x180020dc6  mov     rbx, [rsp+68h+arg_0]
0x180020dcb  add     rsp, 60h
0x180020dcf  pop     rdi
0x180020dd0  retn
```
