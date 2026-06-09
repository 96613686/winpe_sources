# CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::RemoveTail(void)

- ea: `0x18000e158`
- end: `0x18000e192`
- name: `?RemoveTail@?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@QEAAPEAVCTnMultiResCursor@@XZ`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dc24`

## callees

- `0x18000e158`

## pseudocode

```c
__int64 __fastcall CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::RemoveTail(__int64 a1)
{
  _QWORD *v1; // rdx
  _QWORD *v3; // rcx
  __int64 v4; // r8

  v1 = *(_QWORD **)(a1 + 8);
  v3 = (_QWORD *)v1[1];
  v4 = v1[2];
  *(_QWORD *)(a1 + 8) = v3;
  if ( v3 )
    *v3 = 0;
  else
    *(_QWORD *)a1 = 0;
  *v1 = *(_QWORD *)(a1 + 24);
  --*(_DWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 24) = v1;
  return v4;
}

```

## disassembly

```asm
0x18000e158  mov     rdx, [rcx+8]
0x18000e15c  mov     rax, rcx
0x18000e15f  mov     rcx, [rdx+8]
0x18000e163  mov     r8, [rdx+10h]
0x18000e167  mov     [rax+8], rcx
0x18000e16b  test    rcx, rcx
0x18000e16e  jz      short loc_18000E179
0x18000e170  mov     qword ptr [rcx], 0
0x18000e177  jmp     short loc_18000E180
0x18000e179  mov     qword ptr [rax], 0
0x18000e180  mov     rcx, [rax+18h]
0x18000e184  mov     [rdx], rcx
0x18000e187  dec     dword ptr [rax+10h]
0x18000e18a  mov     [rax+18h], rdx
0x18000e18e  mov     rax, r8
0x18000e191  retn
```
