# WinHvResetTdComprehensiveScan

- ea: `0x1400252a0`
- end: `0x1400252b7`
- name: `WinHvResetTdComprehensiveScan`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001b010`

## pseudocode

```c
__int64 __fastcall WinHvResetTdComprehensiveScan(__int64 a1)
{
  return WinHvSetPartitionProperty(a1, 524549, a1);
}

```

## disassembly

```asm
0x1400252a0  sub     rsp, 28h
0x1400252a4  mov     r8, rcx
0x1400252a7  mov     edx, 80105h
0x1400252ac  call    WinHvSetPartitionProperty
0x1400252b1  add     rsp, 28h
0x1400252b5  retn
```
