# WMCommListEntryAddRef

- ea: `0x140002a78`
- end: `0x140002a8b`
- name: `WMCommListEntryAddRef`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000b938`

## pseudocode

```c
bool __fastcall WMCommListEntryAddRef(__int64 a1)
{
  return _InterlockedIncrement((volatile signed __int32 *)(a1 + 16)) != -1;
}

```

## disassembly

```asm
0x140002a78  mov     eax, 1
0x140002a7d  lock xadd [rcx+10h], eax
0x140002a82  inc     eax
0x140002a84  cmp     eax, 0FFFFFFFFh
0x140002a87  setb    al
0x140002a8a  retn
```
