# __std_type_info_compare

- ea: `0x180015620`
- end: `0x180015635`
- name: `__std_type_info_compare`
- size: `21`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001511c`

## callees

- `0x180015620`
- `0x18001568e`

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
0x180015620  cmp     rcx, rdx
0x180015623  jnz     short loc_180015628
0x180015625  xor     eax, eax
0x180015627  retn
0x180015628  add     rdx, 9; Str2
0x18001562c  add     rcx, 9; Str1
0x180015630  jmp     strcmp_0
```
