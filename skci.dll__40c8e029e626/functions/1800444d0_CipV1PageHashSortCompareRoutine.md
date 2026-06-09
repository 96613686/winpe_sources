# CipV1PageHashSortCompareRoutine

- ea: `0x1800444d0`
- end: `0x1800444f8`
- name: `CipV1PageHashSortCompareRoutine`
- size: `40`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003391a`

## pseudocode

```c
int __fastcall CipV1PageHashSortCompareRoutine(char *a1, unsigned int *a2, unsigned int *a3)
{
  return memcmp_0(&a1[*a2 + 4], &a1[*a3 + 4], 0x14u);
}

```

## disassembly

```asm
0x1800444d0  sub     rsp, 28h
0x1800444d4  mov     eax, [rdx]
0x1800444d6  mov     edx, [r8]
0x1800444d9  mov     r8d, 14h; Size
0x1800444df  add     rdx, 4
0x1800444e3  add     rdx, rcx; Buf2
0x1800444e6  add     rcx, 4
0x1800444ea  add     rcx, rax; Buf1
0x1800444ed  call    memcmp_0
0x1800444f2  add     rsp, 28h
0x1800444f6  retn
```
