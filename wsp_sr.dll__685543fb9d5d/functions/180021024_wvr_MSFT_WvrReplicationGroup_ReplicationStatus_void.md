# wvr::MSFT_WvrReplicationGroup::ReplicationStatus(void)

- ea: `0x180021024`
- end: `0x180021092`
- name: `?ReplicationStatus@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@I@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b5f8`
- `0x18000cec8`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::ReplicationStatus(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"ReplicationStatus");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180021024  mov     [rsp+arg_0], rbx
0x180021029  push    rdi
0x18002102a  sub     rsp, 60h
0x18002102e  mov     rax, cs:__security_cookie
0x180021035  xor     rax, rsp
0x180021038  mov     [rsp+68h+var_18], rax
0x18002103d  mov     rdi, rdx
0x180021040  mov     rbx, rcx
0x180021043  mov     [rsp+68h+var_40], rdx
0x180021048  lea     rdx, aReplicationsta; "ReplicationStatus"
0x18002104f  lea     rcx, [rsp+68h+var_38]
0x180021054  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180021059  nop
0x18002105a  lea     rdx, [rbx+8]
0x18002105e  lea     r8, [rsp+68h+var_38]
0x180021063  mov     rcx, rdi
0x180021066  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x18002106b  nop
0x18002106c  lea     rcx, [rsp+68h+var_38]
0x180021071  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021076  mov     rax, rdi
0x180021079  mov     rcx, [rsp+68h+var_18]
0x18002107e  xor     rcx, rsp; StackCookie
0x180021081  call    __security_check_cookie
0x180021086  mov     rbx, [rsp+68h+arg_0]
0x18002108b  add     rsp, 60h
0x18002108f  pop     rdi
0x180021090  retn
```
