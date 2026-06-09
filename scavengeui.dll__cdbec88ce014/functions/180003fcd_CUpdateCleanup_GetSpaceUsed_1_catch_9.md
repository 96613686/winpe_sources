# _CUpdateCleanup::GetSpaceUsed_::_1_::catch$9

- ea: `0x180003fcd`
- end: `0x180003feb`
- name: `_CUpdateCleanup::GetSpaceUsed_::_1_::catch$9`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 CUpdateCleanup::GetSpaceUsed_::_1_::catch_9()
{
  return 0;
}

```

## disassembly

```asm
0x180003fcd  mov     [rsp+arg_8], rdx
0x180003fd2  push    rbp
0x180003fd3  sub     rsp, 30h
0x180003fd7  mov     rbp, rdx
0x180003fda  mov     rax, 0
0x180003fe4  add     rsp, 30h
0x180003fe8  pop     rbp
0x180003fe9  retn
```
