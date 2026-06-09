# wvr::MSFT_WvrReplicationGroup::LogSizeInBytes(void)

- ea: `0x180020d68`
- end: `0x180020dda`
- name: `?LogSizeInBytes@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@_K@2@XZ`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bab8`

## callees

- `0x1800014e0`
- `0x180005884`
- `0x1800058c8`
- `0x180006724`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::LogSizeInBytes(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"LogSizeInBytes");
  *a2 = a1 + 8;
  std::wstring::wstring(a2 + 1, v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180020d68  mov     [rsp+arg_0], rbx
0x180020d6d  push    rdi
0x180020d6e  sub     rsp, 60h
0x180020d72  mov     rax, cs:__security_cookie
0x180020d79  xor     rax, rsp
0x180020d7c  mov     [rsp+68h+var_18], rax
0x180020d81  mov     rdi, rdx
0x180020d84  mov     rbx, rcx
0x180020d87  mov     [rsp+68h+var_40], rdx
0x180020d8c  lea     rdx, aLogsizeinbytes; "LogSizeInBytes"
0x180020d93  lea     rcx, [rsp+68h+var_38]
0x180020d98  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020d9d  nop
0x180020d9e  lea     rcx, [rbx+8]
0x180020da2  mov     [rdi], rcx
0x180020da5  lea     rcx, [rdi+8]
0x180020da9  lea     rdx, [rsp+68h+var_38]
0x180020dae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180020db3  nop
0x180020db4  lea     rcx, [rsp+68h+var_38]
0x180020db9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020dbe  mov     rax, rdi
0x180020dc1  mov     rcx, [rsp+68h+var_18]
0x180020dc6  xor     rcx, rsp; StackCookie
0x180020dc9  call    __security_check_cookie
0x180020dce  mov     rbx, [rsp+68h+arg_0]
0x180020dd3  add     rsp, 60h
0x180020dd7  pop     rdi
0x180020dd8  retn
```
