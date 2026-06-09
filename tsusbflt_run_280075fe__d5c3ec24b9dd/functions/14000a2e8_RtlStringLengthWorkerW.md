# RtlStringLengthWorkerW

- ea: `0x14000a2e8`
- end: `0x14000a328`
- name: `RtlStringLengthWorkerW`
- size: `64`
- prototype: `NTSTATUS __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e80`
- `0x140002bc4`
- `0x140003f90`
- `0x140004480`
- `0x140005754`
- `0x140005d24`
- `0x1400065e8`
- `0x14000711c`
- `0x140009c90`

## callees

- `0x14000a2e8`

## pseudocode

```c
NTSTATUS __stdcall RtlStringLengthWorkerW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  size_t i; // r9
  NTSTATUS result; // eax

  for ( i = cchMax; cchMax; --cchMax )
  {
    if ( !*psz )
      break;
    ++psz;
  }
  result = cchMax == 0 ? 0xC000000D : 0;
  if ( pcchLength )
  {
    if ( cchMax )
      *pcchLength = i - cchMax;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000a2e8  xor     r10d, r10d
0x14000a2eb  mov     r9, rdx
0x14000a2ee  test    rdx, rdx
0x14000a2f1  jz      short loc_14000A303
0x14000a2f3  cmp     [rcx], r10w
0x14000a2f7  jz      short loc_14000A303
0x14000a2f9  add     rcx, 2
0x14000a2fd  sub     rdx, 1
0x14000a301  jnz     short loc_14000A2F3
0x14000a303  mov     rax, rdx
0x14000a306  neg     rax
0x14000a309  sbb     eax, eax
0x14000a30b  not     eax
0x14000a30d  and     eax, 0C000000Dh
0x14000a312  test    r8, r8
0x14000a315  jz      short locret_14000A327
0x14000a317  test    rdx, rdx
0x14000a31a  jz      short loc_14000A324
0x14000a31c  sub     r9, rdx
0x14000a31f  mov     [r8], r9
0x14000a322  retn
0x14000a324  mov     [r8], r10
0x14000a327  retn
```
