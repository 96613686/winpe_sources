# SymCryptEcpointCopy

- ea: `0x180029328`
- end: `0x18002935d`
- name: `SymCryptEcpointCopy`
- size: `53`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180029704`
- `0x180029fa0`
- `0x18002a4b0`
- `0x18002f1c0`
- `0x18002f7ec`
- `0x180030d80`

## callees

- `0x180029328`
- `0x18003392c`

## pseudocode

```c
void *__fastcall SymCryptEcpointCopy(__int64 a1, _BYTE *a2, _BYTE *a3)
{
  void *result; // rax

  if ( a2 != a3 )
  {
    *a3 = *a2;
    return memcpy_0(a3 + 32, a2 + 32, (*(_DWORD *)(a1 + 16) * (*(_DWORD *)(a1 + 8) & 0xFu)) << 6);
  }
  return result;
}

```

## disassembly

```asm
0x180029328  sub     rsp, 28h
0x18002932c  mov     r9, r8
0x18002932f  cmp     rdx, r8
0x180029332  jz      short loc_180029357
0x180029334  mov     al, [rdx]
0x180029336  add     rdx, 20h ; ' '; Src
0x18002933a  mov     [r8], al
0x18002933d  mov     r8d, [rcx+8]
0x180029341  and     r8d, 0Fh
0x180029345  imul    r8d, [rcx+10h]
0x18002934a  lea     rcx, [r9+20h]; void *
0x18002934e  shl     r8d, 6; MaxCount
0x180029352  call    memcpy_0
0x180029357  add     rsp, 28h
0x18002935b  retn
```
