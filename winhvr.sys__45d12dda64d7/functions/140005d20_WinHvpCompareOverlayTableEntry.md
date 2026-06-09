# WinHvpCompareOverlayTableEntry

- ea: `0x140005d20`
- end: `0x140005d35`
- name: `WinHvpCompareOverlayTableEntry`
- size: `21`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005d20`

## pseudocode

```c
__int64 __fastcall WinHvpCompareOverlayTableEntry(
        struct _RTL_GENERIC_TABLE *Table,
        _QWORD *FirstStruct,
        _QWORD *SecondStruct)
{
  if ( *SecondStruct <= *FirstStruct )
    return 2 - (unsigned int)(*SecondStruct < *FirstStruct);
  else
    return 0;
}

```

## disassembly

```asm
0x140005d20  mov     rax, [r8]
0x140005d23  mov     rcx, [rdx]
0x140005d26  cmp     rax, rcx
0x140005d29  jbe     short loc_140005D2F
0x140005d2b  xor     eax, eax
0x140005d2d  retn
0x140005d2f  sbb     eax, eax
0x140005d31  add     eax, 2
0x140005d34  retn
```
