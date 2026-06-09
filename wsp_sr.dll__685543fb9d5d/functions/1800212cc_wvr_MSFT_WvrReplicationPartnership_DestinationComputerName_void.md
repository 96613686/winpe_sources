# wvr::MSFT_WvrReplicationPartnership::DestinationComputerName(void)

- ea: `0x1800212cc`
- end: `0x18002133a`
- name: `?DestinationComputerName@MSFT_WvrReplicationPartnership@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008b90`
- `0x180011d40`
- `0x18001478c`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## string_xrefs

- `0x1800212f0`: `DestinationComputerName`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrReplicationPartnership::DestinationComputerName(__int64 a1, __int64 a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"DestinationComputerName");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x1800212cc  mov     [rsp+arg_0], rbx
0x1800212d1  push    rdi
0x1800212d2  sub     rsp, 60h
0x1800212d6  mov     rax, cs:__security_cookie
0x1800212dd  xor     rax, rsp
0x1800212e0  mov     [rsp+68h+var_18], rax
0x1800212e5  mov     rdi, rdx
0x1800212e8  mov     rbx, rcx
0x1800212eb  mov     [rsp+68h+var_40], rdx
0x1800212f0  lea     rdx, aDestinationcom; "DestinationComputerName"
0x1800212f7  lea     rcx, [rsp+68h+var_38]
0x1800212fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180021301  nop
0x180021302  lea     rdx, [rbx+8]
0x180021306  lea     r8, [rsp+68h+var_38]
0x18002130b  mov     rcx, rdi
0x18002130e  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180021313  nop
0x180021314  lea     rcx, [rsp+68h+var_38]
0x180021319  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002131e  mov     rax, rdi
0x180021321  mov     rcx, [rsp+68h+var_18]
0x180021326  xor     rcx, rsp; StackCookie
0x180021329  call    __security_check_cookie
0x18002132e  mov     rbx, [rsp+68h+arg_0]
0x180021333  add     rsp, 60h
0x180021337  pop     rdi
0x180021338  retn
```
