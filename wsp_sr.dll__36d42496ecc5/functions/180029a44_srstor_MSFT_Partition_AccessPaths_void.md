# srstor::MSFT_Partition::AccessPaths(void)

- ea: `0x180029a44`
- end: `0x180029ab1`
- name: `?AccessPaths@MSFT_Partition@srstor@@QEBA?BV?$read_property@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180021dbc`
- `0x1800222d8`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## string_xrefs

- `0x180029a68`: `AccessPaths`

## pseudocode

```c
_QWORD *__fastcall srstor::MSFT_Partition::AccessPaths(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"AccessPaths");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180029a44  mov     [rsp+arg_0], rbx
0x180029a49  push    rdi
0x180029a4a  sub     rsp, 60h
0x180029a4e  mov     rax, cs:__security_cookie
0x180029a55  xor     rax, rsp
0x180029a58  mov     [rsp+68h+var_18], rax
0x180029a5d  mov     rdi, rdx
0x180029a60  mov     rbx, rcx
0x180029a63  mov     [rsp+68h+var_40], rdx
0x180029a68  lea     rdx, aAccesspaths; "AccessPaths"
0x180029a6f  lea     rcx, [rsp+68h+var_38]
0x180029a74  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180029a79  nop
0x180029a7a  lea     rdx, [rbx+8]
0x180029a7e  lea     r8, [rsp+68h+var_38]
0x180029a83  mov     rcx, rdi
0x180029a86  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180029a8b  nop
0x180029a8c  lea     rcx, [rsp+68h+var_38]
0x180029a91  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029a96  mov     rax, rdi
0x180029a99  mov     rcx, [rsp+68h+var_18]
0x180029a9e  xor     rcx, rsp; StackCookie
0x180029aa1  call    __security_check_cookie
0x180029aa6  mov     rbx, [rsp+68h+arg_0]
0x180029aab  add     rsp, 60h
0x180029aaf  pop     rdi
0x180029ab0  retn
```
