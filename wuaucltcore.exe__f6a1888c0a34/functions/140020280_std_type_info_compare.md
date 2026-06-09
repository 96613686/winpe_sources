# __std_type_info_compare

- ea: `0x140020280`
- end: `0x140020295`
- name: `__std_type_info_compare`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001fd7c`

## callees

- `0x140020280`
- `0x1400202f8`

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
0x140020280  cmp     rcx, rdx
0x140020283  jnz     short loc_140020288
0x140020285  xor     eax, eax
0x140020287  retn
0x140020288  add     rdx, 9; Str2
0x14002028c  add     rcx, 9; Str1
0x140020290  jmp     strcmp_0
```
