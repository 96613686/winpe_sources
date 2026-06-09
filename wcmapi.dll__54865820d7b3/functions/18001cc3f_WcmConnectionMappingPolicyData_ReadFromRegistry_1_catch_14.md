# _WcmConnectionMappingPolicyData::ReadFromRegistry_::_1_::catch$14

- ea: `0x18001cc3f`
- end: `0x18001cc67`
- name: `_WcmConnectionMappingPolicyData::ReadFromRegistry_::_1_::catch$14`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall WcmConnectionMappingPolicyData::ReadFromRegistry_::_1_::catch_14(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 152) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x18001cc3f  mov     [rsp+arg_8], rdx
0x18001cc44  push    rbp
0x18001cc45  sub     rsp, 30h
0x18001cc49  mov     rbp, rdx
0x18001cc4c  mov     dword ptr [rbp+98h], 8007000Eh
0x18001cc56  mov     rax, 0
0x18001cc60  add     rsp, 30h
0x18001cc64  pop     rbp
0x18001cc65  retn
```
