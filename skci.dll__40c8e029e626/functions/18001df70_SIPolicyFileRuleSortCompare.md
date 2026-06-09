# SIPolicyFileRuleSortCompare

- ea: `0x18001df70`
- end: `0x18001df9f`
- name: `SIPolicyFileRuleSortCompare`
- size: `47`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800211b4`

## pseudocode

```c
int __fastcall SIPolicyFileRuleSortCompare(void *a1, unsigned int *a2, unsigned int *a3)
{
  return SIPolicyFileRuleCompare((__int64)a1 + 168 * *a2, (__int64)a1 + 168 * *a3);
}

```

## disassembly

```asm
0x18001df70  sub     rsp, 28h
0x18001df74  mov     eax, [r8]
0x18001df77  mov     r9, rdx
0x18001df7a  imul    rdx, rax, 0A8h
0x18001df81  mov     eax, [r9]
0x18001df84  mov     r10, rcx
0x18001df87  add     rdx, rcx
0x18001df8a  imul    rcx, rax, 0A8h
0x18001df91  add     rcx, r10
0x18001df94  call    SIPolicyFileRuleCompare
0x18001df99  add     rsp, 28h
0x18001df9d  retn
```
