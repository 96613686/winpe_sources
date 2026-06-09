# NetprNameCompare

- ea: `0x180020fb0`
- end: `0x180020fcb`
- name: `NetprNameCompare`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `netutils!NetpwNameCompare` at `0x180020fc4`

## pseudocode

```c
__int64 __fastcall NetprNameCompare(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned int a5)
{
  return NetpwNameCompare(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180020fb0  mov     eax, r9d
0x180020fb3  mov     r10, r8
0x180020fb6  mov     r9d, [rsp+arg_20]
0x180020fbb  mov     rcx, rdx
0x180020fbe  mov     r8d, eax
0x180020fc1  mov     rdx, r10
0x180020fc4  jmp     cs:__imp_NetpwNameCompare
```
