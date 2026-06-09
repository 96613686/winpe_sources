# OncRpcBufMgrGetDescriptorAllocationLengthRemaining

- ea: `0x140002230`
- end: `0x140002252`
- name: `OncRpcBufMgrGetDescriptorAllocationLengthRemaining`
- size: `34`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400021e8`
- `0x1400085c0`
- `0x14000aac4`
- `0x14000d7a4`

## callees

- `0x140002230`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrGetDescriptorAllocationLengthRemaining(_DWORD *a1)
{
  unsigned int v1; // edx
  unsigned int v2; // r8d
  unsigned int v3; // ecx
  __int64 result; // rax

  v1 = a1[16] - a1[14];
  v2 = a1[18];
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
0x140002230  mov     edx, [rcx+40h]
0x140002233  sub     edx, [rcx+38h]
0x140002236  mov     r8d, [rcx+48h]
0x14000223a  cmp     r8d, edx
0x14000223d  jb      short loc_140002246
0x14000223f  mov     ecx, r8d
0x140002242  sub     ecx, edx
0x140002244  jmp     short loc_140002249
0x140002246  or      ecx, 0FFFFFFFFh
0x140002249  xor     eax, eax
0x14000224b  cmp     r8d, edx
0x14000224e  cmovnb  eax, ecx
0x140002251  retn
```
