# wvr::MSFT_WvrReplicationPartnership::DestinationRGName(void)

- ea: `0x1800211ac`
- end: `0x180021219`
- name: `?DestinationRGName@MSFT_WvrReplicationPartnership@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
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
_QWORD *__fastcall wvr::MSFT_WvrReplicationPartnership::DestinationRGName(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"DestinationRGName");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x1800211ac  mov     [rsp+arg_0], rbx
0x1800211b1  push    rdi
0x1800211b2  sub     rsp, 60h
0x1800211b6  mov     rax, cs:__security_cookie
0x1800211bd  xor     rax, rsp
0x1800211c0  mov     [rsp+68h+var_18], rax
0x1800211c5  mov     rdi, rdx
0x1800211c8  mov     rbx, rcx
0x1800211cb  mov     [rsp+68h+var_40], rdx
0x1800211d0  lea     rdx, aDestinationrgn; "DestinationRGName"
0x1800211d7  lea     rcx, [rsp+68h+var_38]
0x1800211dc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800211e1  nop
0x1800211e2  lea     rdx, [rbx+8]
0x1800211e6  lea     r8, [rsp+68h+var_38]
0x1800211eb  mov     rcx, rdi
0x1800211ee  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x1800211f3  nop
0x1800211f4  lea     rcx, [rsp+68h+var_38]
0x1800211f9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800211fe  mov     rax, rdi
0x180021201  mov     rcx, [rsp+68h+var_18]
0x180021206  xor     rcx, rsp; StackCookie
0x180021209  call    __security_check_cookie
0x18002120e  mov     rbx, [rsp+68h+arg_0]
0x180021213  add     rsp, 60h
0x180021217  pop     rdi
0x180021218  retn
```
