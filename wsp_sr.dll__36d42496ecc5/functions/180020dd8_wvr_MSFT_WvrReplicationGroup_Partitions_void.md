# wvr::MSFT_WvrReplicationGroup::Partitions(void)

- ea: `0x180020dd8`
- end: `0x180020e45`
- name: `?Partitions@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180013c50`
- `0x1800198cc`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::Partitions(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"Partitions");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020dd8  mov     [rsp+arg_0], rbx
0x180020ddd  push    rdi
0x180020dde  sub     rsp, 60h
0x180020de2  mov     rax, cs:__security_cookie
0x180020de9  xor     rax, rsp
0x180020dec  mov     [rsp+68h+var_18], rax
0x180020df1  mov     rdi, rdx
0x180020df4  mov     rbx, rcx
0x180020df7  mov     [rsp+68h+var_40], rdx
0x180020dfc  lea     rdx, aPartitions; "Partitions"
0x180020e03  lea     rcx, [rsp+68h+var_38]
0x180020e08  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020e0d  nop
0x180020e0e  lea     rdx, [rbx+8]
0x180020e12  lea     r8, [rsp+68h+var_38]
0x180020e17  mov     rcx, rdi
0x180020e1a  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020e1f  nop
0x180020e20  lea     rcx, [rsp+68h+var_38]
0x180020e25  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020e2a  mov     rax, rdi
0x180020e2d  mov     rcx, [rsp+68h+var_18]
0x180020e32  xor     rcx, rsp; StackCookie
0x180020e35  call    __security_check_cookie
0x180020e3a  mov     rbx, [rsp+68h+arg_0]
0x180020e3f  add     rsp, 60h
0x180020e43  pop     rdi
0x180020e44  retn
```
