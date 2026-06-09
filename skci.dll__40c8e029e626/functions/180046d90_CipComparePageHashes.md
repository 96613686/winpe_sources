# CipComparePageHashes

- ea: `0x180046d90`
- end: `0x180046d95`
- name: `CipComparePageHashes`
- size: `5`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CipComparePageHashes(const void *a1, _DWORD *a2)
{
  return (unsigned int)((_DWORD)a1 - *a2);
}

```

## disassembly

```asm
0x180046d90  sub     ecx, [rdx]
0x180046d92  mov     eax, ecx
0x180046d94  retn
```
