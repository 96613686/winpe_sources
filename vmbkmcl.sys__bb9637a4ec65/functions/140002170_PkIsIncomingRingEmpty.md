# PkIsIncomingRingEmpty

- ea: `0x140002170`
- end: `0x14000217d`
- name: `PkIsIncomingRingEmpty`
- size: `13`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001120`
- `0x140001170`
- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x1400049a0`
- `0x140007800`

## pseudocode

```c
bool __fastcall PkIsIncomingRingEmpty(__int64 a1)
{
  return *(_DWORD *)(a1 + 68) == **(_DWORD **)(a1 + 24);
}

```

## disassembly

```asm
0x140002170  mov     rax, [rcx+18h]
0x140002174  mov     edx, [rax]
0x140002176  cmp     [rcx+44h], edx
0x140002179  setz    al
0x14000217c  retn
```
