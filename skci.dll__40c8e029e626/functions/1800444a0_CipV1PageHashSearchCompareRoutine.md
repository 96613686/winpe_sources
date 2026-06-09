# CipV1PageHashSearchCompareRoutine

- ea: `0x1800444a0`
- end: `0x1800444c5`
- name: `CipV1PageHashSearchCompareRoutine`
- size: `37`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003391a`

## pseudocode

```c
int __fastcall CipV1PageHashSearchCompareRoutine(char *a1, const void *a2, unsigned int *a3)
{
  return memcmp_0(a2, &a1[*a3 + 4], 0x14u);
}

```

## disassembly

```asm
0x1800444a0  sub     rsp, 28h
0x1800444a4  mov     r9, rdx
0x1800444a7  add     rcx, 4
0x1800444ab  mov     edx, [r8]
0x1800444ae  mov     r8d, 14h; Size
0x1800444b4  add     rdx, rcx; Buf2
0x1800444b7  mov     rcx, r9; Buf1
0x1800444ba  call    memcmp_0
0x1800444bf  add     rsp, 28h
0x1800444c3  retn
```
