# wvr::MSFT_WvrReplicationGroup::ReplicationMode(void)

- ea: `0x180020e4c`
- end: `0x180020eb9`
- name: `?ReplicationMode@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@I@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b98c`
- `0x1800126cc`
- `0x180013c50`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::ReplicationMode(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"ReplicationMode");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020e4c  mov     [rsp+arg_0], rbx
0x180020e51  push    rdi
0x180020e52  sub     rsp, 60h
0x180020e56  mov     rax, cs:__security_cookie
0x180020e5d  xor     rax, rsp
0x180020e60  mov     [rsp+68h+var_18], rax
0x180020e65  mov     rdi, rdx
0x180020e68  mov     rbx, rcx
0x180020e6b  mov     [rsp+68h+var_40], rdx
0x180020e70  lea     rdx, aReplicationmod; "ReplicationMode"
0x180020e77  lea     rcx, [rsp+68h+var_38]
0x180020e7c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020e81  nop
0x180020e82  lea     rdx, [rbx+8]
0x180020e86  lea     r8, [rsp+68h+var_38]
0x180020e8b  mov     rcx, rdi
0x180020e8e  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020e93  nop
0x180020e94  lea     rcx, [rsp+68h+var_38]
0x180020e99  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020e9e  mov     rax, rdi
0x180020ea1  mov     rcx, [rsp+68h+var_18]
0x180020ea6  xor     rcx, rsp; StackCookie
0x180020ea9  call    __security_check_cookie
0x180020eae  mov     rbx, [rsp+68h+arg_0]
0x180020eb3  add     rsp, 60h
0x180020eb7  pop     rdi
0x180020eb8  retn
```
