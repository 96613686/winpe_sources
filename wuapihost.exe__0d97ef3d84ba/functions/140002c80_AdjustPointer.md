# __AdjustPointer

- ea: `0x140002c80`
- end: `0x140002ca3`
- name: `__AdjustPointer`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000327c`
- `0x140003478`

## callees

- `0x140002c80`

## pseudocode

```c
__int64 __fastcall _AdjustPointer(__int64 a1, int *a2)
{
  __int64 result; // rax

  result = a1 + *a2;
  if ( a2[1] >= 0 )
    result += a2[1] + (__int64)*(int *)(a2[2] + *(_QWORD *)(a2[1] + a1));
  return result;
}

```

## disassembly

```asm
0x140002c80  movsxd  rax, dword ptr [rdx]
0x140002c83  add     rax, rcx
0x140002c86  cmp     dword ptr [rdx+4], 0
0x140002c8a  jl      short locret_140002CA2
0x140002c8c  movsxd  r9, dword ptr [rdx+4]
0x140002c90  movsxd  rdx, dword ptr [rdx+8]
0x140002c94  mov     rcx, [r9+rcx]
0x140002c98  movsxd  r8, dword ptr [rdx+rcx]
0x140002c9c  add     r8, r9
0x140002c9f  add     rax, r8
0x140002ca2  retn
```
