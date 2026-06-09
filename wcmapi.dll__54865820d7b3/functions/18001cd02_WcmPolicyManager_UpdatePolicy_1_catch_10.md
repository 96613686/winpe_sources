# _WcmPolicyManager::UpdatePolicy_::_1_::catch$10

- ea: `0x18001cd02`
- end: `0x18001cd37`
- name: `_WcmPolicyManager::UpdatePolicy_::_1_::catch$10`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800085c8`

## pseudocode

```c
__int64 __fastcall WcmPolicyManager::UpdatePolicy_::_1_::catch_10(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024322;
  ReportApplicationError(-2147024322, 0xD7u);
  return 0;
}

```

## disassembly

```asm
0x18001cd02  mov     [rsp+arg_8], rdx
0x18001cd07  push    rbp
0x18001cd08  sub     rsp, 40h
0x18001cd0c  mov     rbp, rdx
0x18001cd0f  mov     dword ptr [rbp+40h], 8007023Eh
0x18001cd16  mov     edx, 0D7h; unsigned int
0x18001cd1b  mov     ecx, 8007023Eh; int
0x18001cd20  call    ?ReportApplicationError@@YAXJK@Z; ReportApplicationError(long,ulong)
0x18001cd25  nop
0x18001cd26  mov     rax, 0
0x18001cd30  add     rsp, 40h
0x18001cd34  pop     rbp
0x18001cd35  retn
```
