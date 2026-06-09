# __AdjustPointer

- ea: `0x180002ec8`
- end: `0x180002eef`
- name: `__AdjustPointer`
- size: `39`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003760`
- `0x180003930`
- `0x180003b00`
- `0x180003bc0`

## callees

- `0x180002ec8`

## pseudocode

```c
__int64 __fastcall _AdjustPointer(__int64 a1, int *a2)
{
  if ( a2[1] < 0 )
    return a1 + *a2;
  else
    return a1 + *a2 + a2[1] + (__int64)*(int *)(a2[2] + *(_QWORD *)(a2[1] + a1));
}

```

## disassembly

```asm
0x180002ec8  movsxd  r9, dword ptr [rdx]
0x180002ecb  add     r9, rcx
0x180002ece  cmp     dword ptr [rdx+4], 0
0x180002ed2  jl      short loc_180002EEB
0x180002ed4  movsxd  r8, dword ptr [rdx+4]
0x180002ed8  movsxd  rdx, dword ptr [rdx+8]
0x180002edc  mov     rax, [r8+rcx]
0x180002ee0  movsxd  rax, dword ptr [rdx+rax]
0x180002ee4  add     rax, r8
0x180002ee7  add     rax, r9
0x180002eea  retn
0x180002eeb  mov     rax, r9
0x180002eee  retn
```
