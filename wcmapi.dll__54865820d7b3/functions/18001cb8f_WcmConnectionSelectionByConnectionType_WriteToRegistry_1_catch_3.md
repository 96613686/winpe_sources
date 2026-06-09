# _WcmConnectionSelectionByConnectionType::WriteToRegistry_::_1_::catch$3

- ea: `0x18001cb8f`
- end: `0x18001cbb4`
- name: `_WcmConnectionSelectionByConnectionType::WriteToRegistry_::_1_::catch$3`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall WcmConnectionSelectionByConnectionType::WriteToRegistry_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x18001cb8f  mov     [rsp+arg_8], rdx
0x18001cb94  push    rbp
0x18001cb95  sub     rsp, 30h
0x18001cb99  mov     rbp, rdx
0x18001cb9c  mov     dword ptr [rbp+30h], 8007000Eh
0x18001cba3  mov     rax, 0
0x18001cbad  add     rsp, 30h
0x18001cbb1  pop     rbp
0x18001cbb2  retn
```
