# TmpRemoveTransactionEnlistmentCounts

- ea: `0x14000cec8`
- end: `0x14000cf1f`
- name: `TmpRemoveTransactionEnlistmentCounts`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c9ac`
- `0x14000cccc`

## callees

- `0x14000cec8`

## pseudocode

```c
__int64 __fastcall TmpRemoveTransactionEnlistmentCounts(__int64 a1)
{
  _DWORD *v1; // rdx
  __int64 result; // rax

  v1 = *(_DWORD **)(a1 + 160);
  if ( (*(_DWORD *)(a1 + 172) & 2) != 0 )
    --v1[55];
  if ( (*(_DWORD *)(a1 + 176) & 2) != 0 )
    --v1[57];
  if ( (*(_DWORD *)(a1 + 176) & 1) != 0 )
    --v1[56];
  result = *(unsigned int *)(a1 + 172);
  if ( (result & 0x10) != 0 )
    --v1[58];
  --v1[54];
  return result;
}

```

## disassembly

```asm
0x14000cec8  mov     eax, [rcx+0ACh]
0x14000cece  or      r8d, 0FFFFFFFFh
0x14000ced2  mov     rdx, [rcx+0A0h]
0x14000ced9  test    al, 2
0x14000cedb  jz      short loc_14000CEE4
0x14000cedd  add     [rdx+0DCh], r8d
0x14000cee4  mov     eax, [rcx+0B0h]
0x14000ceea  test    al, 2
0x14000ceec  jz      short loc_14000CEF5
0x14000ceee  add     [rdx+0E4h], r8d
0x14000cef5  mov     eax, [rcx+0B0h]
0x14000cefb  test    al, 1
0x14000cefd  jz      short loc_14000CF06
0x14000ceff  add     [rdx+0E0h], r8d
0x14000cf06  mov     eax, [rcx+0ACh]
0x14000cf0c  test    al, 10h
0x14000cf0e  jz      short loc_14000CF17
0x14000cf10  add     [rdx+0E8h], r8d
0x14000cf17  add     [rdx+0D8h], r8d
0x14000cf1e  retn
```
