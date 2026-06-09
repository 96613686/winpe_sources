# wvr::MSFT_WvrReplicationGroup::Name(void)

- ea: `0x180020e54`
- end: `0x180020ec2`
- name: `?Name@MSFT_WvrReplicationGroup@wvr@@QEAA?AV?$write_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fc70`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020160`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrReplicationGroup::Name(__int64 a1, __int64 a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"Name");
  wvr::write_property<std::wstring>::write_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180020e54  mov     [rsp+arg_0], rbx
0x180020e59  push    rdi
0x180020e5a  sub     rsp, 60h
0x180020e5e  mov     rax, cs:__security_cookie
0x180020e65  xor     rax, rsp
0x180020e68  mov     [rsp+68h+var_18], rax
0x180020e6d  mov     rdi, rdx
0x180020e70  mov     rbx, rcx
0x180020e73  mov     [rsp+68h+var_40], rdx
0x180020e78  lea     rdx, aName; "Name"
0x180020e7f  lea     rcx, [rsp+68h+var_38]
0x180020e84  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020e89  nop
0x180020e8a  lea     rdx, [rbx+8]
0x180020e8e  lea     r8, [rsp+68h+var_38]
0x180020e93  mov     rcx, rdi
0x180020e96  call    ??0?$write_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wvr@@QEAA@AEAVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; wvr::write_property<std::wstring>::write_property<std::wstring>(mi::MiInstance &,std::wstring const &)
0x180020e9b  nop
0x180020e9c  lea     rcx, [rsp+68h+var_38]
0x180020ea1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020ea6  mov     rax, rdi
0x180020ea9  mov     rcx, [rsp+68h+var_18]
0x180020eae  xor     rcx, rsp; StackCookie
0x180020eb1  call    __security_check_cookie
0x180020eb6  mov     rbx, [rsp+68h+arg_0]
0x180020ebb  add     rsp, 60h
0x180020ebf  pop     rdi
0x180020ec0  retn
```
