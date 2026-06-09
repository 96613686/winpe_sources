# srstor::MSFT_Partition::AccessPaths(void)

- ea: `0x180029ef0`
- end: `0x180029f5e`
- name: `?AccessPaths@MSFT_Partition@srstor@@QEBA?BV?$read_property@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180021f64`
- `0x180022490`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## string_xrefs

- `0x180029f14`: `AccessPaths`

## pseudocode

```c
__int64 __fastcall srstor::MSFT_Partition::AccessPaths(__int64 a1, __int64 a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"AccessPaths");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180029ef0  mov     [rsp+arg_0], rbx
0x180029ef5  push    rdi
0x180029ef6  sub     rsp, 60h
0x180029efa  mov     rax, cs:__security_cookie
0x180029f01  xor     rax, rsp
0x180029f04  mov     [rsp+68h+var_18], rax
0x180029f09  mov     rdi, rdx
0x180029f0c  mov     rbx, rcx
0x180029f0f  mov     [rsp+68h+var_40], rdx
0x180029f14  lea     rdx, aAccesspaths; "AccessPaths"
0x180029f1b  lea     rcx, [rsp+68h+var_38]
0x180029f20  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180029f25  nop
0x180029f26  lea     rdx, [rbx+8]
0x180029f2a  lea     r8, [rsp+68h+var_38]
0x180029f2f  mov     rcx, rdi
0x180029f32  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180029f37  nop
0x180029f38  lea     rcx, [rsp+68h+var_38]
0x180029f3d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029f42  mov     rax, rdi
0x180029f45  mov     rcx, [rsp+68h+var_18]
0x180029f4a  xor     rcx, rsp; StackCookie
0x180029f4d  call    __security_check_cookie
0x180029f52  mov     rbx, [rsp+68h+arg_0]
0x180029f57  add     rsp, 60h
0x180029f5b  pop     rdi
0x180029f5c  retn
```
