# CompareHeapTags

- ea: `0x140002af0`
- end: `0x140002af6`
- name: `CompareHeapTags`
- size: `6`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CompareHeapTags(void *a1, _DWORD *a2, _DWORD *a3)
{
  return (unsigned int)(*a2 - *a3);
}

```

## disassembly

```asm
0x140002af0  mov     eax, [rdx]
0x140002af2  sub     eax, [r8]
0x140002af5  retn
```
