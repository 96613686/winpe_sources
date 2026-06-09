# wvr::MSFT_WvrReplicationGroup::ComputerName(void)

- ea: `0x1800208ec`
- end: `0x18002095a`
- name: `?ComputerName@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b5f8`
- `0x18000fc70`
- `0x1800169ec`
- `0x180019904`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## string_xrefs

- `0x180020910`: `ComputerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wvr::MSFT_WvrReplicationGroup::ComputerName(__int64 a1, __int64 a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"ComputerName");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x1800208ec  mov     [rsp+arg_0], rbx
0x1800208f1  push    rdi
0x1800208f2  sub     rsp, 60h
0x1800208f6  mov     rax, cs:__security_cookie
0x1800208fd  xor     rax, rsp
0x180020900  mov     [rsp+68h+var_18], rax
0x180020905  mov     rdi, rdx
0x180020908  mov     rbx, rcx
0x18002090b  mov     [rsp+68h+var_40], rdx
0x180020910  lea     rdx, aComputername; "ComputerName"
0x180020917  lea     rcx, [rsp+68h+var_38]
0x18002091c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020921  nop
0x180020922  lea     rdx, [rbx+8]
0x180020926  lea     r8, [rsp+68h+var_38]
0x18002092b  mov     rcx, rdi
0x18002092e  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020933  nop
0x180020934  lea     rcx, [rsp+68h+var_38]
0x180020939  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002093e  mov     rax, rdi
0x180020941  mov     rcx, [rsp+68h+var_18]
0x180020946  xor     rcx, rsp; StackCookie
0x180020949  call    __security_check_cookie
0x18002094e  mov     rbx, [rsp+68h+arg_0]
0x180020953  add     rsp, 60h
0x180020957  pop     rdi
0x180020958  retn
```
