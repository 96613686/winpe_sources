# CipFileHashSearchCompareRoutineSHA256

- ea: `0x180044350`
- end: `0x180044365`
- name: `CipFileHashSearchCompareRoutineSHA256`
- size: `21`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003391a`

## pseudocode

```c
int __fastcall CipFileHashSearchCompareRoutineSHA256(const void *a1, const void *a2)
{
  return memcmp_0(a1, a2, 0x20u);
}

```

## disassembly

```asm
0x180044350  sub     rsp, 28h
0x180044354  mov     r8d, 20h ; ' '; Size
0x18004435a  call    memcmp_0
0x18004435f  add     rsp, 28h
0x180044363  retn
```
