# wvr::MSFT_WvrReplicationGroup::Partitions(void)

- ea: `0x180020f3c`
- end: `0x180020faa`
- name: `?Partitions@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180013b60`
- `0x180019904`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::Partitions(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"Partitions");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180020f3c  mov     [rsp+arg_0], rbx
0x180020f41  push    rdi
0x180020f42  sub     rsp, 60h
0x180020f46  mov     rax, cs:__security_cookie
0x180020f4d  xor     rax, rsp
0x180020f50  mov     [rsp+68h+var_18], rax
0x180020f55  mov     rdi, rdx
0x180020f58  mov     rbx, rcx
0x180020f5b  mov     [rsp+68h+var_40], rdx
0x180020f60  lea     rdx, aPartitions; "Partitions"
0x180020f67  lea     rcx, [rsp+68h+var_38]
0x180020f6c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020f71  nop
0x180020f72  lea     rdx, [rbx+8]
0x180020f76  lea     r8, [rsp+68h+var_38]
0x180020f7b  mov     rcx, rdi
0x180020f7e  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020f83  nop
0x180020f84  lea     rcx, [rsp+68h+var_38]
0x180020f89  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020f8e  mov     rax, rdi
0x180020f91  mov     rcx, [rsp+68h+var_18]
0x180020f96  xor     rcx, rsp; StackCookie
0x180020f99  call    __security_check_cookie
0x180020f9e  mov     rbx, [rsp+68h+arg_0]
0x180020fa3  add     rsp, 60h
0x180020fa7  pop     rdi
0x180020fa8  retn
```
