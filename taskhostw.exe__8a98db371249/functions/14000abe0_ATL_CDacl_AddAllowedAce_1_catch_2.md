# _ATL::CDacl::AddAllowedAce_::_1_::catch$2

- ea: `0x14000abe0`
- end: `0x14000abfe`
- name: `_ATL::CDacl::AddAllowedAce_::_1_::catch$2`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
__int64 ATL::CDacl::AddAllowedAce_::_1_::catch_2()
{
  return 0;
}

```

## disassembly

```asm
0x14000abe0  mov     [rsp+arg_8], rdx
0x14000abe5  push    rbp
0x14000abe6  sub     rsp, 30h
0x14000abea  mov     rbp, rdx
0x14000abed  mov     rax, 0
0x14000abf7  add     rsp, 30h
0x14000abfb  pop     rbp
0x14000abfc  retn
```
