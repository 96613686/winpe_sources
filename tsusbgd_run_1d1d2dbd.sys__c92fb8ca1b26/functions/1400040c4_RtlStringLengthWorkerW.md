# RtlStringLengthWorkerW

- ea: `0x1400040c4`
- end: `0x140004105`
- name: `RtlStringLengthWorkerW`
- size: `65`
- prototype: `NTSTATUS __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001b50`

## callees

- `0x1400040c4`

## pseudocode

```c
NTSTATUS __stdcall RtlStringLengthWorkerW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  __int64 v3; // rdx
  NTSTATUS result; // eax

  v3 = 0x7FFF;
  do
  {
    if ( !*psz )
      break;
    ++psz;
    --v3;
  }
  while ( v3 );
  result = v3 == 0 ? 0xC000000D : 0;
  if ( pcchLength )
  {
    if ( v3 )
      *pcchLength = 0x7FFF - v3;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400040c4  mov     r9d, 7FFFh
0x1400040ca  xor     r10d, r10d
0x1400040cd  mov     edx, r9d
0x1400040d0  cmp     [rcx], r10w
0x1400040d4  jz      short loc_1400040E0
0x1400040d6  add     rcx, 2
0x1400040da  sub     rdx, 1
0x1400040de  jnz     short loc_1400040D0
0x1400040e0  mov     rax, rdx
0x1400040e3  neg     rax
0x1400040e6  sbb     eax, eax
0x1400040e8  not     eax
0x1400040ea  and     eax, 0C000000Dh
0x1400040ef  test    r8, r8
0x1400040f2  jz      short locret_140004104
0x1400040f4  test    rdx, rdx
0x1400040f7  jz      short loc_140004101
0x1400040f9  sub     r9, rdx
0x1400040fc  mov     [r8], r9
0x1400040ff  retn
0x140004101  mov     [r8], r10
0x140004104  retn
```
