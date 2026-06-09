# TSContextCompareCallback

- ea: `0x180004440`
- end: `0x18000444f`
- name: `TSContextCompareCallback`
- size: `15`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001160`
- `0x180003ea0`
- `0x180004170`
- `0x18000a5d4`
- `0x18001b77c`

## callees

- `0x180004440`

## pseudocode

```c
__int64 __fastcall TSContextCompareCallback(unsigned __int64 a1, __int64 a2)
{
  if ( *(_QWORD *)(a2 + 56) > a1 )
    return 1;
  else
    return (unsigned int)-(*(_QWORD *)(a2 + 56) < a1);
}

```

## disassembly

```asm
0x180004440  cmp     [rdx+38h], rcx
0x180004444  ja      short loc_180004449
0x180004446  sbb     eax, eax
0x180004448  retn
0x180004449  mov     eax, 1
0x18000444e  retn
```
