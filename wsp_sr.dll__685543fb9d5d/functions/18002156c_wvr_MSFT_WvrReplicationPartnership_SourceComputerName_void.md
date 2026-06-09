# wvr::MSFT_WvrReplicationPartnership::SourceComputerName(void)

- ea: `0x18002156c`
- end: `0x1800215da`
- name: `?SourceComputerName@MSFT_WvrReplicationPartnership@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
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

- `0x180021590`: `SourceComputerName`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrReplicationPartnership::SourceComputerName(__int64 a1, __int64 a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"SourceComputerName");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x18002156c  mov     [rsp+arg_0], rbx
0x180021571  push    rdi
0x180021572  sub     rsp, 60h
0x180021576  mov     rax, cs:__security_cookie
0x18002157d  xor     rax, rsp
0x180021580  mov     [rsp+68h+var_18], rax
0x180021585  mov     rdi, rdx
0x180021588  mov     rbx, rcx
0x18002158b  mov     [rsp+68h+var_40], rdx
0x180021590  lea     rdx, aSourcecomputer; "SourceComputerName"
0x180021597  lea     rcx, [rsp+68h+var_38]
0x18002159c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800215a1  nop
0x1800215a2  lea     rdx, [rbx+8]
0x1800215a6  lea     r8, [rsp+68h+var_38]
0x1800215ab  mov     rcx, rdi
0x1800215ae  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x1800215b3  nop
0x1800215b4  lea     rcx, [rsp+68h+var_38]
0x1800215b9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800215be  mov     rax, rdi
0x1800215c1  mov     rcx, [rsp+68h+var_18]
0x1800215c6  xor     rcx, rsp; StackCookie
0x1800215c9  call    __security_check_cookie
0x1800215ce  mov     rbx, [rsp+68h+arg_0]
0x1800215d3  add     rsp, 60h
0x1800215d7  pop     rdi
0x1800215d8  retn
```
