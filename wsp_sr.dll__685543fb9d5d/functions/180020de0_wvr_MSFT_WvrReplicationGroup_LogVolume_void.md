# wvr::MSFT_WvrReplicationGroup::LogVolume(void)

- ea: `0x180020de0`
- end: `0x180020e4e`
- name: `?LogVolume@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bab8`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::LogVolume(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"LogVolume");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180020de0  mov     [rsp+arg_0], rbx
0x180020de5  push    rdi
0x180020de6  sub     rsp, 60h
0x180020dea  mov     rax, cs:__security_cookie
0x180020df1  xor     rax, rsp
0x180020df4  mov     [rsp+68h+var_18], rax
0x180020df9  mov     rdi, rdx
0x180020dfc  mov     rbx, rcx
0x180020dff  mov     [rsp+68h+var_40], rdx
0x180020e04  lea     rdx, aLogvolume; "LogVolume"
0x180020e0b  lea     rcx, [rsp+68h+var_38]
0x180020e10  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020e15  nop
0x180020e16  lea     rdx, [rbx+8]
0x180020e1a  lea     r8, [rsp+68h+var_38]
0x180020e1f  mov     rcx, rdi
0x180020e22  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020e27  nop
0x180020e28  lea     rcx, [rsp+68h+var_38]
0x180020e2d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020e32  mov     rax, rdi
0x180020e35  mov     rcx, [rsp+68h+var_18]
0x180020e3a  xor     rcx, rsp; StackCookie
0x180020e3d  call    __security_check_cookie
0x180020e42  mov     rbx, [rsp+68h+arg_0]
0x180020e47  add     rsp, 60h
0x180020e4b  pop     rdi
0x180020e4c  retn
```
