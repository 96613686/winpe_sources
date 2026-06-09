# wvr::MSFT_WvrReplicationGroup::IsCluster(void)

- ea: `0x180020c80`
- end: `0x180020cee`
- name: `?IsCluster@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@_N@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180008ad4`
- `0x1800137bc`
- `0x180015c58`
- `0x180015d2c`
- `0x180016684`
- `0x1800191e0`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::IsCluster(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"IsCluster");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180020c80  mov     [rsp+arg_0], rbx
0x180020c85  push    rdi
0x180020c86  sub     rsp, 60h
0x180020c8a  mov     rax, cs:__security_cookie
0x180020c91  xor     rax, rsp
0x180020c94  mov     [rsp+68h+var_18], rax
0x180020c99  mov     rdi, rdx
0x180020c9c  mov     rbx, rcx
0x180020c9f  mov     [rsp+68h+var_40], rdx
0x180020ca4  lea     rdx, aIscluster; "IsCluster"
0x180020cab  lea     rcx, [rsp+68h+var_38]
0x180020cb0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020cb5  nop
0x180020cb6  lea     rdx, [rbx+8]
0x180020cba  lea     r8, [rsp+68h+var_38]
0x180020cbf  mov     rcx, rdi
0x180020cc2  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020cc7  nop
0x180020cc8  lea     rcx, [rsp+68h+var_38]
0x180020ccd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020cd2  mov     rax, rdi
0x180020cd5  mov     rcx, [rsp+68h+var_18]
0x180020cda  xor     rcx, rsp; StackCookie
0x180020cdd  call    __security_check_cookie
0x180020ce2  mov     rbx, [rsp+68h+arg_0]
0x180020ce7  add     rsp, 60h
0x180020ceb  pop     rdi
0x180020cec  retn
```
