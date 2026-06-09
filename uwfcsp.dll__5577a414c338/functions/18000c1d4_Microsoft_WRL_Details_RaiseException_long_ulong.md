# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x18000c1d4`
- end: `0x18000c1e5`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `17`
- prototype: `void __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007d4c`
- `0x180008c94`
- `0x180008cbc`
- `0x180009c8c`
- `0x18000d0d8`
- `0x18000d7f0`
- `0x18000eed0`
- `0x180019144`
- `0x180019238`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c1de`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000c1d4  xor     r9d, r9d
0x18000c1d7  xor     r8d, r8d
0x18000c1da  lea     edx, [r9+1]
0x18000c1de  jmp     cs:__imp_RaiseException
```
