# RtlIsLUnicodeStringValid

- ea: `0x180007c60`
- end: `0x180007c88`
- name: `RtlIsLUnicodeStringValid`
- size: `40`
- prototype: `char __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800078c8`
- `0x180007cc0`
- `0x180007d8c`
- `0x180016478`
- `0x18001b698`

## callees

- `0x180007c60`

## pseudocode

```c
char __fastcall RtlIsLUnicodeStringValid(__int64 a1)
{
  char result; // al
  unsigned __int64 v2; // rdx

  if ( !a1 )
    return 0;
  result = 1;
  if ( (*(_BYTE *)a1 & 1) != 0 )
    return 0;
  v2 = *(_QWORD *)(a1 + 8);
  if ( (v2 & 1) != 0 || *(_QWORD *)a1 > v2 || !*(_QWORD *)(a1 + 16) && *(_QWORD *)a1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180007c60  test    rcx, rcx
0x180007c63  jz      short loc_180007C85
0x180007c65  mov     al, 1
0x180007c67  test    [rcx], al
0x180007c69  jnz     short loc_180007C85
0x180007c6b  mov     rdx, [rcx+8]
0x180007c6f  test    al, dl
0x180007c71  jnz     short loc_180007C85
0x180007c73  cmp     [rcx], rdx
0x180007c76  ja      short loc_180007C85
0x180007c78  cmp     qword ptr [rcx+10h], 0
0x180007c7d  jnz     short locret_180007C87
0x180007c7f  cmp     qword ptr [rcx], 0
0x180007c83  jz      short locret_180007C87
0x180007c85  xor     al, al
0x180007c87  retn
```
