# _WcmConnectionSelectionByName::ReadFromRegistry_::_1_::catch$0

- ea: `0x18001d5a2`
- end: `0x18001d5c7`
- name: `_WcmConnectionSelectionByName::ReadFromRegistry_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall WcmConnectionSelectionByName::ReadFromRegistry_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x18001d5a2  mov     [rsp+arg_8], rdx
0x18001d5a7  push    rbp
0x18001d5a8  sub     rsp, 30h
0x18001d5ac  mov     rbp, rdx
0x18001d5af  mov     dword ptr [rbp+60h], 8007000Eh
0x18001d5b6  mov     rax, 0
0x18001d5c0  add     rsp, 30h
0x18001d5c4  pop     rbp
0x18001d5c5  retn
```
