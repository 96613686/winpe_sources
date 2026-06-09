# _WcmConnectionMappingPolicyData::WriteToRegistry_::_1_::catch$4

- ea: `0x18001cbde`
- end: `0x18001cc03`
- name: `_WcmConnectionMappingPolicyData::WriteToRegistry_::_1_::catch$4`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall WcmConnectionMappingPolicyData::WriteToRegistry_::_1_::catch_4(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x18001cbde  mov     [rsp+arg_8], rdx
0x18001cbe3  push    rbp
0x18001cbe4  sub     rsp, 40h
0x18001cbe8  mov     rbp, rdx
0x18001cbeb  mov     dword ptr [rbp+40h], 8007000Eh
0x18001cbf2  mov     rax, 0
0x18001cbfc  add     rsp, 40h
0x18001cc00  pop     rbp
0x18001cc01  retn
```
