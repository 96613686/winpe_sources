# wvr::MSFT_WvrReplicationGroup::Name(void)

- ea: `0x180020cf0`
- end: `0x180020d5d`
- name: `?Name@MSFT_WvrReplicationGroup@wvr@@QEAA?AV?$write_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fc98`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18002001c`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::Name(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"Name");
  wvr::write_property<std::wstring>::write_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020cf0  mov     [rsp+arg_0], rbx
0x180020cf5  push    rdi
0x180020cf6  sub     rsp, 60h
0x180020cfa  mov     rax, cs:__security_cookie
0x180020d01  xor     rax, rsp
0x180020d04  mov     [rsp+68h+var_18], rax
0x180020d09  mov     rdi, rdx
0x180020d0c  mov     rbx, rcx
0x180020d0f  mov     [rsp+68h+var_40], rdx
0x180020d14  lea     rdx, aName; "Name"
0x180020d1b  lea     rcx, [rsp+68h+var_38]
0x180020d20  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020d25  nop
0x180020d26  lea     rdx, [rbx+8]
0x180020d2a  lea     r8, [rsp+68h+var_38]
0x180020d2f  mov     rcx, rdi
0x180020d32  call    ??0?$write_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wvr@@QEAA@AEAVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; wvr::write_property<std::wstring>::write_property<std::wstring>(mi::MiInstance &,std::wstring const &)
0x180020d37  nop
0x180020d38  lea     rcx, [rsp+68h+var_38]
0x180020d3d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020d42  mov     rax, rdi
0x180020d45  mov     rcx, [rsp+68h+var_18]
0x180020d4a  xor     rcx, rsp; StackCookie
0x180020d4d  call    __security_check_cookie
0x180020d52  mov     rbx, [rsp+68h+arg_0]
0x180020d57  add     rsp, 60h
0x180020d5b  pop     rdi
0x180020d5c  retn
```
