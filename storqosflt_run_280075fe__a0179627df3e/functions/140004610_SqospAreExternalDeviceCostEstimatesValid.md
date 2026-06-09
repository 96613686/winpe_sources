# SqospAreExternalDeviceCostEstimatesValid

- ea: `0x140004610`
- end: `0x140004636`
- name: `SqospAreExternalDeviceCostEstimatesValid`
- size: `38`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001380`
- `0x140002bf0`
- `0x1400056e0`

## callees

- `0x140004610`

## pseudocode

```c
bool __fastcall SqospAreExternalDeviceCostEstimatesValid(__int64 a1)
{
  return *(_DWORD *)(a1 + 1100) == 1 && MEMORY[0xFFFFF78000000008] < *(_QWORD *)(a1 + 1104);
}

```

## disassembly

```asm
0x140004610  cmp     dword ptr [rcx+44Ch], 1
0x140004617  jnz     short loc_140004633
0x140004619  mov     rdx, [rcx+450h]
0x140004620  mov     rax, ds:0FFFFF78000000008h
0x14000462a  cmp     rax, rdx
0x14000462d  jnb     short loc_140004633
0x14000462f  mov     al, 1
0x140004631  retn
0x140004633  xor     al, al
0x140004635  retn
```
