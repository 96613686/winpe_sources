# wvr::MSFT_WvrReplicationPartnership::DestinationRGName(void)

- ea: `0x180021340`
- end: `0x1800213ae`
- name: `?DestinationRGName@MSFT_WvrReplicationPartnership@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008b90`
- `0x180011d40`
- `0x18001478c`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationPartnership::DestinationRGName(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"DestinationRGName");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180021340  mov     [rsp+arg_0], rbx
0x180021345  push    rdi
0x180021346  sub     rsp, 60h
0x18002134a  mov     rax, cs:__security_cookie
0x180021351  xor     rax, rsp
0x180021354  mov     [rsp+68h+var_18], rax
0x180021359  mov     rdi, rdx
0x18002135c  mov     rbx, rcx
0x18002135f  mov     [rsp+68h+var_40], rdx
0x180021364  lea     rdx, aDestinationrgn; "DestinationRGName"
0x18002136b  lea     rcx, [rsp+68h+var_38]
0x180021370  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180021375  nop
0x180021376  lea     rdx, [rbx+8]
0x18002137a  lea     r8, [rsp+68h+var_38]
0x18002137f  mov     rcx, rdi
0x180021382  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180021387  nop
0x180021388  lea     rcx, [rsp+68h+var_38]
0x18002138d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021392  mov     rax, rdi
0x180021395  mov     rcx, [rsp+68h+var_18]
0x18002139a  xor     rcx, rsp; StackCookie
0x18002139d  call    __security_check_cookie
0x1800213a2  mov     rbx, [rsp+68h+arg_0]
0x1800213a7  add     rsp, 60h
0x1800213ab  pop     rdi
0x1800213ac  retn
```
