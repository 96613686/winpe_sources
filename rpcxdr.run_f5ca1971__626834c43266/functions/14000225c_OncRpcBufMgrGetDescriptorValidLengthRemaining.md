# OncRpcBufMgrGetDescriptorValidLengthRemaining

- ea: `0x14000225c`
- end: `0x14000227e`
- name: `OncRpcBufMgrGetDescriptorValidLengthRemaining`
- size: `34`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000220c`
- `0x1400059f8`
- `0x14001530c`

## callees

- `0x14000225c`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrGetDescriptorValidLengthRemaining(_DWORD *a1)
{
  unsigned int v1; // edx
  unsigned int v2; // r8d
  unsigned int v3; // ecx
  __int64 result; // rax

  v1 = a1[16] - a1[14];
  v2 = a1[19];
  if ( v2 < v1 )
    v3 = -1;
  else
    v3 = v2 - v1;
  result = 0;
  if ( v2 >= v1 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x14000225c  mov     edx, [rcx+40h]
0x14000225f  sub     edx, [rcx+38h]
0x140002262  mov     r8d, [rcx+4Ch]
0x140002266  cmp     r8d, edx
0x140002269  jb      short loc_140002272
0x14000226b  mov     ecx, r8d
0x14000226e  sub     ecx, edx
0x140002270  jmp     short loc_140002275
0x140002272  or      ecx, 0FFFFFFFFh
0x140002275  xor     eax, eax
0x140002277  cmp     r8d, edx
0x14000227a  cmovnb  eax, ecx
0x14000227d  retn
```
