# wvr::MSFT_WvrReplicationGroup::LogSizeInBytes(void)

- ea: `0x180020c04`
- end: `0x180020c75`
- name: `?LogSizeInBytes@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@_K@2@XZ`
- size: `113`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b98c`

## callees

- `0x1800014e0`
- `0x18000584c`
- `0x180005890`
- `0x1800066d8`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::LogSizeInBytes(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"LogSizeInBytes");
  *a2 = a1 + 8;
  std::wstring::wstring((__int64)(a2 + 1), v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020c04  mov     [rsp+arg_0], rbx
0x180020c09  push    rdi
0x180020c0a  sub     rsp, 60h
0x180020c0e  mov     rax, cs:__security_cookie
0x180020c15  xor     rax, rsp
0x180020c18  mov     [rsp+68h+var_18], rax
0x180020c1d  mov     rdi, rdx
0x180020c20  mov     rbx, rcx
0x180020c23  mov     [rsp+68h+var_40], rdx
0x180020c28  lea     rdx, aLogsizeinbytes; "LogSizeInBytes"
0x180020c2f  lea     rcx, [rsp+68h+var_38]
0x180020c34  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020c39  nop
0x180020c3a  lea     rcx, [rbx+8]
0x180020c3e  mov     [rdi], rcx
0x180020c41  lea     rcx, [rdi+8]
0x180020c45  lea     rdx, [rsp+68h+var_38]
0x180020c4a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180020c4f  nop
0x180020c50  lea     rcx, [rsp+68h+var_38]
0x180020c55  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020c5a  mov     rax, rdi
0x180020c5d  mov     rcx, [rsp+68h+var_18]
0x180020c62  xor     rcx, rsp; StackCookie
0x180020c65  call    __security_check_cookie
0x180020c6a  mov     rbx, [rsp+68h+arg_0]
0x180020c6f  add     rsp, 60h
0x180020c73  pop     rdi
0x180020c74  retn
```
