# wvr::MSFT_WvrReplicationGroup::ComputerName(void)

- ea: `0x18002078c`
- end: `0x1800207f9`
- name: `?ComputerName@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b48c`
- `0x18000fc98`
- `0x180016b28`
- `0x1800198cc`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## string_xrefs

- `0x1800207b0`: `ComputerName`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::ComputerName(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"ComputerName");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x18002078c  mov     [rsp+arg_0], rbx
0x180020791  push    rdi
0x180020792  sub     rsp, 60h
0x180020796  mov     rax, cs:__security_cookie
0x18002079d  xor     rax, rsp
0x1800207a0  mov     [rsp+68h+var_18], rax
0x1800207a5  mov     rdi, rdx
0x1800207a8  mov     rbx, rcx
0x1800207ab  mov     [rsp+68h+var_40], rdx
0x1800207b0  lea     rdx, aComputername; "ComputerName"
0x1800207b7  lea     rcx, [rsp+68h+var_38]
0x1800207bc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800207c1  nop
0x1800207c2  lea     rdx, [rbx+8]
0x1800207c6  lea     r8, [rsp+68h+var_38]
0x1800207cb  mov     rcx, rdi
0x1800207ce  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x1800207d3  nop
0x1800207d4  lea     rcx, [rsp+68h+var_38]
0x1800207d9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800207de  mov     rax, rdi
0x1800207e1  mov     rcx, [rsp+68h+var_18]
0x1800207e6  xor     rcx, rsp; StackCookie
0x1800207e9  call    __security_check_cookie
0x1800207ee  mov     rbx, [rsp+68h+arg_0]
0x1800207f3  add     rsp, 60h
0x1800207f7  pop     rdi
0x1800207f8  retn
```
