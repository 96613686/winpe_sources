# __std_type_info_compare

- ea: `0x1800143c0`
- end: `0x1800143d5`
- name: `__std_type_info_compare`
- size: `21`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013eb4`

## callees

- `0x1800143c0`
- `0x1800144de`

## pseudocode

```c
int __fastcall _std_type_info_compare(__int64 a1, __int64 a2)
{
  if ( a1 == a2 )
    return 0;
  else
    return strcmp_0((const char *)(a1 + 9), (const char *)(a2 + 9));
}

```

## disassembly

```asm
0x1800143c0  cmp     rcx, rdx
0x1800143c3  jnz     short loc_1800143C8
0x1800143c5  xor     eax, eax
0x1800143c7  retn
0x1800143c8  add     rdx, 9; Str2
0x1800143cc  add     rcx, 9; Str1
0x1800143d0  jmp     strcmp_0
```
