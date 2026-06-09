# I_HashSearchCompareRoutineSHA256

- ea: `0x180017ea0`
- end: `0x180017eb5`
- name: `I_HashSearchCompareRoutineSHA256`
- size: `21`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003391a`

## pseudocode

```c
int __fastcall I_HashSearchCompareRoutineSHA256(const void *a1, const void *a2)
{
  return memcmp_0(a1, a2, 0x20u);
}

```

## disassembly

```asm
0x180017ea0  sub     rsp, 28h
0x180017ea4  mov     r8d, 20h ; ' '; Size
0x180017eaa  call    memcmp_0
0x180017eaf  add     rsp, 28h
0x180017eb3  retn
```
