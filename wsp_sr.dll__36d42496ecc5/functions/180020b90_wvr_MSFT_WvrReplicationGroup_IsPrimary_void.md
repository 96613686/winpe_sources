# wvr::MSFT_WvrReplicationGroup::IsPrimary(void)

- ea: `0x180020b90`
- end: `0x180020bfd`
- name: `?IsPrimary@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@_N@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013c50`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::IsPrimary(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"IsPrimary");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020b90  mov     [rsp+arg_0], rbx
0x180020b95  push    rdi
0x180020b96  sub     rsp, 60h
0x180020b9a  mov     rax, cs:__security_cookie
0x180020ba1  xor     rax, rsp
0x180020ba4  mov     [rsp+68h+var_18], rax
0x180020ba9  mov     rdi, rdx
0x180020bac  mov     rbx, rcx
0x180020baf  mov     [rsp+68h+var_40], rdx
0x180020bb4  lea     rdx, aIsprimary; "IsPrimary"
0x180020bbb  lea     rcx, [rsp+68h+var_38]
0x180020bc0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020bc5  nop
0x180020bc6  lea     rdx, [rbx+8]
0x180020bca  lea     r8, [rsp+68h+var_38]
0x180020bcf  mov     rcx, rdi
0x180020bd2  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020bd7  nop
0x180020bd8  lea     rcx, [rsp+68h+var_38]
0x180020bdd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020be2  mov     rax, rdi
0x180020be5  mov     rcx, [rsp+68h+var_18]
0x180020bea  xor     rcx, rsp; StackCookie
0x180020bed  call    __security_check_cookie
0x180020bf2  mov     rbx, [rsp+68h+arg_0]
0x180020bf7  add     rsp, 60h
0x180020bfb  pop     rdi
0x180020bfc  retn
```
