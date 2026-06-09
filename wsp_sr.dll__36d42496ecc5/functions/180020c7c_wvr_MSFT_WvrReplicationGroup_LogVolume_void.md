# wvr::MSFT_WvrReplicationGroup::LogVolume(void)

- ea: `0x180020c7c`
- end: `0x180020ce9`
- name: `?LogVolume@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b98c`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::LogVolume(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"LogVolume");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020c7c  mov     [rsp+arg_0], rbx
0x180020c81  push    rdi
0x180020c82  sub     rsp, 60h
0x180020c86  mov     rax, cs:__security_cookie
0x180020c8d  xor     rax, rsp
0x180020c90  mov     [rsp+68h+var_18], rax
0x180020c95  mov     rdi, rdx
0x180020c98  mov     rbx, rcx
0x180020c9b  mov     [rsp+68h+var_40], rdx
0x180020ca0  lea     rdx, aLogvolume; "LogVolume"
0x180020ca7  lea     rcx, [rsp+68h+var_38]
0x180020cac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020cb1  nop
0x180020cb2  lea     rdx, [rbx+8]
0x180020cb6  lea     r8, [rsp+68h+var_38]
0x180020cbb  mov     rcx, rdi
0x180020cbe  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020cc3  nop
0x180020cc4  lea     rcx, [rsp+68h+var_38]
0x180020cc9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020cce  mov     rax, rdi
0x180020cd1  mov     rcx, [rsp+68h+var_18]
0x180020cd6  xor     rcx, rsp; StackCookie
0x180020cd9  call    __security_check_cookie
0x180020cde  mov     rbx, [rsp+68h+arg_0]
0x180020ce3  add     rsp, 60h
0x180020ce7  pop     rdi
0x180020ce8  retn
```
