# __AdjustPointer

- ea: `0x180011b00`
- end: `0x180011b23`
- name: `__AdjustPointer`
- size: `35`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180012350`
- `0x180012548`
- `0x180012744`
- `0x18001280c`

## callees

- `0x180011b00`

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
0x180011b00  movsxd  rax, dword ptr [rdx]
0x180011b03  add     rax, rcx
0x180011b06  cmp     dword ptr [rdx+4], 0
0x180011b0a  jl      short locret_180011B22
0x180011b0c  movsxd  r9, dword ptr [rdx+4]
0x180011b10  movsxd  rdx, dword ptr [rdx+8]
0x180011b14  mov     rcx, [r9+rcx]
0x180011b18  movsxd  r8, dword ptr [rdx+rcx]
0x180011b1c  add     r8, r9
0x180011b1f  add     rax, r8
0x180011b22  retn
```
