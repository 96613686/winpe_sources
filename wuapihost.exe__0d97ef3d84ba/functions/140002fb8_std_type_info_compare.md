# __std_type_info_compare

- ea: `0x140002fb8`
- end: `0x140002fcd`
- name: `__std_type_info_compare`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004f24`

## callees

- `0x140002fb8`
- `0x1400055e6`

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
0x140002fb8  cmp     rcx, rdx
0x140002fbb  jnz     short loc_140002FC0
0x140002fbd  xor     eax, eax
0x140002fbf  retn
0x140002fc0  add     rdx, 9; Str2
0x140002fc4  add     rcx, 9; Str1
0x140002fc8  jmp     strcmp_0
```
