# srstor::MSFT_Partition::Guid(void)

- ea: `0x18002a050`
- end: `0x18002a0be`
- name: `?Guid@MSFT_Partition@srstor@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002231c`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall srstor::MSFT_Partition::Guid(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"Guid");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x18002a050  mov     [rsp+arg_0], rbx
0x18002a055  push    rdi
0x18002a056  sub     rsp, 60h
0x18002a05a  mov     rax, cs:__security_cookie
0x18002a061  xor     rax, rsp
0x18002a064  mov     [rsp+68h+var_18], rax
0x18002a069  mov     rdi, rdx
0x18002a06c  mov     rbx, rcx
0x18002a06f  mov     [rsp+68h+var_40], rdx
0x18002a074  lea     rdx, aGuid; "Guid"
0x18002a07b  lea     rcx, [rsp+68h+var_38]
0x18002a080  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002a085  nop
0x18002a086  lea     rdx, [rbx+8]
0x18002a08a  lea     r8, [rsp+68h+var_38]
0x18002a08f  mov     rcx, rdi
0x18002a092  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x18002a097  nop
0x18002a098  lea     rcx, [rsp+68h+var_38]
0x18002a09d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a0a2  mov     rax, rdi
0x18002a0a5  mov     rcx, [rsp+68h+var_18]
0x18002a0aa  xor     rcx, rsp; StackCookie
0x18002a0ad  call    __security_check_cookie
0x18002a0b2  mov     rbx, [rsp+68h+arg_0]
0x18002a0b7  add     rsp, 60h
0x18002a0bb  pop     rdi
0x18002a0bc  retn
```
