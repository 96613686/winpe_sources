# NetprPathCompare

- ea: `0x180021040`
- end: `0x18002105b`
- name: `NetprPathCompare`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `netutils!NetpwPathCompare` at `0x180021054`

## pseudocode

```c
__int64 __fastcall NetprPathCompare(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned int a5)
{
  return NetpwPathCompare(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180021040  mov     eax, r9d
0x180021043  mov     r10, r8
0x180021046  mov     r9d, [rsp+arg_20]
0x18002104b  mov     rcx, rdx
0x18002104e  mov     r8d, eax
0x180021051  mov     rdx, r10
0x180021054  jmp     cs:__imp_NetpwPathCompare
```
