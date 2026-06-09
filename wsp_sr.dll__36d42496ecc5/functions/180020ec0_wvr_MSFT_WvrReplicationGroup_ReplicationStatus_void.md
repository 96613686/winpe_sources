# wvr::MSFT_WvrReplicationGroup::ReplicationStatus(void)

- ea: `0x180020ec0`
- end: `0x180020f2d`
- name: `?ReplicationStatus@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@I@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b48c`
- `0x18000cfa4`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::ReplicationStatus(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"ReplicationStatus");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020ec0  mov     [rsp+arg_0], rbx
0x180020ec5  push    rdi
0x180020ec6  sub     rsp, 60h
0x180020eca  mov     rax, cs:__security_cookie
0x180020ed1  xor     rax, rsp
0x180020ed4  mov     [rsp+68h+var_18], rax
0x180020ed9  mov     rdi, rdx
0x180020edc  mov     rbx, rcx
0x180020edf  mov     [rsp+68h+var_40], rdx
0x180020ee4  lea     rdx, aReplicationsta; "ReplicationStatus"
0x180020eeb  lea     rcx, [rsp+68h+var_38]
0x180020ef0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020ef5  nop
0x180020ef6  lea     rdx, [rbx+8]
0x180020efa  lea     r8, [rsp+68h+var_38]
0x180020eff  mov     rcx, rdi
0x180020f02  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020f07  nop
0x180020f08  lea     rcx, [rsp+68h+var_38]
0x180020f0d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020f12  mov     rax, rdi
0x180020f15  mov     rcx, [rsp+68h+var_18]
0x180020f1a  xor     rcx, rsp; StackCookie
0x180020f1d  call    __security_check_cookie
0x180020f22  mov     rbx, [rsp+68h+arg_0]
0x180020f27  add     rsp, 60h
0x180020f2b  pop     rdi
0x180020f2c  retn
```
