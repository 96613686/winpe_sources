# __AdjustPointer

- ea: `0x180011b50`
- end: `0x180011b73`
- name: `__AdjustPointer`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800123a0`
- `0x180012598`
- `0x180012794`
- `0x18001285c`

## callees

- `0x180011b50`

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
0x180011b50  movsxd  rax, dword ptr [rdx]
0x180011b53  add     rax, rcx
0x180011b56  cmp     dword ptr [rdx+4], 0
0x180011b5a  jl      short locret_180011B72
0x180011b5c  movsxd  r9, dword ptr [rdx+4]
0x180011b60  movsxd  rdx, dword ptr [rdx+8]
0x180011b64  mov     rcx, [r9+rcx]
0x180011b68  movsxd  r8, dword ptr [rdx+rcx]
0x180011b6c  add     r8, r9
0x180011b6f  add     rax, r8
0x180011b72  retn
```
