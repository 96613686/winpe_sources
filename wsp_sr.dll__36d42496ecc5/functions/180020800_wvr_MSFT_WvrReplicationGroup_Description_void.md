# wvr::MSFT_WvrReplicationGroup::Description(void)

- ea: `0x180020800`
- end: `0x18002086d`
- name: `?Description@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b48c`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::Description(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"Description");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020800  mov     [rsp+arg_0], rbx
0x180020805  push    rdi
0x180020806  sub     rsp, 60h
0x18002080a  mov     rax, cs:__security_cookie
0x180020811  xor     rax, rsp
0x180020814  mov     [rsp+68h+var_18], rax
0x180020819  mov     rdi, rdx
0x18002081c  mov     rbx, rcx
0x18002081f  mov     [rsp+68h+var_40], rdx
0x180020824  lea     rdx, aDescription; "Description"
0x18002082b  lea     rcx, [rsp+68h+var_38]
0x180020830  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020835  nop
0x180020836  lea     rdx, [rbx+8]
0x18002083a  lea     r8, [rsp+68h+var_38]
0x18002083f  mov     rcx, rdi
0x180020842  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020847  nop
0x180020848  lea     rcx, [rsp+68h+var_38]
0x18002084d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020852  mov     rax, rdi
0x180020855  mov     rcx, [rsp+68h+var_18]
0x18002085a  xor     rcx, rsp; StackCookie
0x18002085d  call    __security_check_cookie
0x180020862  mov     rbx, [rsp+68h+arg_0]
0x180020867  add     rsp, 60h
0x18002086b  pop     rdi
0x18002086c  retn
```
