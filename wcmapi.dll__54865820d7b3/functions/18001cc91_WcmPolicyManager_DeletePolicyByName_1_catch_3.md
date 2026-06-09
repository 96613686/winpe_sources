# _WcmPolicyManager::DeletePolicyByName_::_1_::catch$3

- ea: `0x18001cc91`
- end: `0x18001ccc6`
- name: `_WcmPolicyManager::DeletePolicyByName_::_1_::catch$3`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800085c8`

## pseudocode

```c
__int64 __fastcall WcmPolicyManager::DeletePolicyByName_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024322;
  ReportApplicationError(-2147024322, 0x12Au);
  return 0;
}

```

## disassembly

```asm
0x18001cc91  mov     [rsp+arg_8], rdx
0x18001cc96  push    rbp
0x18001cc97  sub     rsp, 30h
0x18001cc9b  mov     rbp, rdx
0x18001cc9e  mov     dword ptr [rbp+30h], 8007023Eh
0x18001cca5  mov     edx, 12Ah; unsigned int
0x18001ccaa  mov     ecx, 8007023Eh; int
0x18001ccaf  call    ?ReportApplicationError@@YAXJK@Z; ReportApplicationError(long,ulong)
0x18001ccb4  nop
0x18001ccb5  mov     rax, 0
0x18001ccbf  add     rsp, 30h
0x18001ccc3  pop     rbp
0x18001ccc4  retn
```
