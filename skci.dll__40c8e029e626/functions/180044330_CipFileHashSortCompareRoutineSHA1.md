# CipFileHashSortCompareRoutineSHA1

- ea: `0x180044330`
- end: `0x180044345`
- name: `CipFileHashSortCompareRoutineSHA1`
- size: `21`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003391a`

## pseudocode

```c
int __fastcall CipFileHashSortCompareRoutineSHA1(const void *a1, const void *a2)
{
  return memcmp_0(a1, a2, 0x14u);
}

```

## disassembly

```asm
0x180044330  sub     rsp, 28h
0x180044334  mov     r8d, 14h; Size
0x18004433a  call    memcmp_0
0x18004433f  add     rsp, 28h
0x180044343  retn
```
