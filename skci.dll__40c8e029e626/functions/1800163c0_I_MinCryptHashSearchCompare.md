# I_MinCryptHashSearchCompare

- ea: `0x1800163c0`
- end: `0x1800163de`
- name: `I_MinCryptHashSearchCompare`
- size: `30`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003391a`

## pseudocode

```c
int __fastcall I_MinCryptHashSearchCompare(size_t a1, const void *a2, const void *a3)
{
  return memcmp_0(a2, a3, a1);
}

```

## disassembly

```asm
0x1800163c0  sub     rsp, 28h
0x1800163c4  mov     rax, r8
0x1800163c7  mov     r9, rdx
0x1800163ca  mov     r8, rcx; Size
0x1800163cd  mov     rdx, rax; Buf2
0x1800163d0  mov     rcx, r9; Buf1
0x1800163d3  call    memcmp_0
0x1800163d8  add     rsp, 28h
0x1800163dc  retn
```
