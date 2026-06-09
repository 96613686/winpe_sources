# CreateFileDowngrade_Win7

- ea: `0x14001a3f0`
- end: `0x14001a3f5`
- name: `CreateFileDowngrade_Win7`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## pseudocode

```c
void __fastcall CreateFileDowngrade_Win7(_DWORD *a1)
{
  *a1 |= 0x20000u;
}

```

## disassembly

```asm
0x14001a3f0  bts     dword ptr [rcx], 11h
0x14001a3f4  retn
```
