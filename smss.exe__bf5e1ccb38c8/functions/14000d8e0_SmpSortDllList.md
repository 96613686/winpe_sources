# SmpSortDllList

- ea: `0x14000d8e0`
- end: `0x14000d8e6`
- name: `SmpSortDllList`
- size: `6`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall SmpSortDllList(void *a1, _DWORD *a2, _DWORD *a3)
{
  return (unsigned int)(*a2 - *a3);
}

```

## disassembly

```asm
0x14000d8e0  mov     eax, [rdx]
0x14000d8e2  sub     eax, [r8]
0x14000d8e5  retn
```
