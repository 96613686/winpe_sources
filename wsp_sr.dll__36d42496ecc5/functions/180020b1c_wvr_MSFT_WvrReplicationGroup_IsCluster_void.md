# wvr::MSFT_WvrReplicationGroup::IsCluster(void)

- ea: `0x180020b1c`
- end: `0x180020b89`
- name: `?IsCluster@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@_N@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180008948`
- `0x1800138b4`
- `0x180015da4`
- `0x180015e78`
- `0x1800167c8`
- `0x1800191b4`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::IsCluster(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"IsCluster");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x180020b1c  mov     [rsp+arg_0], rbx
0x180020b21  push    rdi
0x180020b22  sub     rsp, 60h
0x180020b26  mov     rax, cs:__security_cookie
0x180020b2d  xor     rax, rsp
0x180020b30  mov     [rsp+68h+var_18], rax
0x180020b35  mov     rdi, rdx
0x180020b38  mov     rbx, rcx
0x180020b3b  mov     [rsp+68h+var_40], rdx
0x180020b40  lea     rdx, aIscluster; "IsCluster"
0x180020b47  lea     rcx, [rsp+68h+var_38]
0x180020b4c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020b51  nop
0x180020b52  lea     rdx, [rbx+8]
0x180020b56  lea     r8, [rsp+68h+var_38]
0x180020b5b  mov     rcx, rdi
0x180020b5e  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020b63  nop
0x180020b64  lea     rcx, [rsp+68h+var_38]
0x180020b69  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020b6e  mov     rax, rdi
0x180020b71  mov     rcx, [rsp+68h+var_18]
0x180020b76  xor     rcx, rsp; StackCookie
0x180020b79  call    __security_check_cookie
0x180020b7e  mov     rbx, [rsp+68h+arg_0]
0x180020b83  add     rsp, 60h
0x180020b87  pop     rdi
0x180020b88  retn
```
