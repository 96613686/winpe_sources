# DPA_GetPtr

- ea: `0x180007b90`
- end: `0x180007bae`
- name: `DPA_GetPtr`
- size: `30`
- prototype: `PVOID __stdcall(HDPA hdpa, INT_PTR i)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006180`
- `0x1800064d4`
- `0x180006c70`
- `0x18000765c`

## callees

- `0x180007b90`

## pseudocode

```c
PVOID __stdcall DPA_GetPtr(HDPA hdpa, INT_PTR i)
{
  if ( hdpa && i >= 0 && i < *(int *)hdpa )
    return *(PVOID *)(*((_QWORD *)hdpa + 1) + 8 * i);
  else
    return 0;
}

```

## disassembly

```asm
0x180007b90  test    rcx, rcx
0x180007b93  jz      short loc_180007BAB
0x180007b95  test    rdx, rdx
0x180007b98  js      short loc_180007BAB
0x180007b9a  movsxd  rax, dword ptr [rcx]
0x180007b9d  cmp     rdx, rax
0x180007ba0  jge     short loc_180007BAB
0x180007ba2  mov     rax, [rcx+8]
0x180007ba6  mov     rax, [rax+rdx*8]
0x180007baa  retn
0x180007bab  xor     eax, eax
0x180007bad  retn
```
