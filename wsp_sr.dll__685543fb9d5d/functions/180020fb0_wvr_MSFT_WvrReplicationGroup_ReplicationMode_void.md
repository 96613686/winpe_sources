# wvr::MSFT_WvrReplicationGroup::ReplicationMode(void)

- ea: `0x180020fb0`
- end: `0x18002101e`
- name: `?ReplicationMode@MSFT_WvrReplicationGroup@wvr@@QEBA?BV?$read_property@I@2@XZ`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bab8`
- `0x180012594`
- `0x180013b60`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180020138`

## pseudocode

```c
_QWORD *__fastcall wvr::MSFT_WvrReplicationGroup::ReplicationMode(__int64 a1, _QWORD *a2)
{
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(v5, L"ReplicationMode");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, (__int64)v5);
  std::wstring::_Tidy_deallocate(v5);
  return a2;
}

```

## disassembly

```asm
0x180020fb0  mov     [rsp+arg_0], rbx
0x180020fb5  push    rdi
0x180020fb6  sub     rsp, 60h
0x180020fba  mov     rax, cs:__security_cookie
0x180020fc1  xor     rax, rsp
0x180020fc4  mov     [rsp+68h+var_18], rax
0x180020fc9  mov     rdi, rdx
0x180020fcc  mov     rbx, rcx
0x180020fcf  mov     [rsp+68h+var_40], rdx
0x180020fd4  lea     rdx, aReplicationmod; "ReplicationMode"
0x180020fdb  lea     rcx, [rsp+68h+var_38]
0x180020fe0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020fe5  nop
0x180020fe6  lea     rdx, [rbx+8]
0x180020fea  lea     r8, [rsp+68h+var_38]
0x180020fef  mov     rcx, rdi
0x180020ff2  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180020ff7  nop
0x180020ff8  lea     rcx, [rsp+68h+var_38]
0x180020ffd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021002  mov     rax, rdi
0x180021005  mov     rcx, [rsp+68h+var_18]
0x18002100a  xor     rcx, rsp; StackCookie
0x18002100d  call    __security_check_cookie
0x180021012  mov     rbx, [rsp+68h+arg_0]
0x180021017  add     rsp, 60h
0x18002101b  pop     rdi
0x18002101c  retn
```
