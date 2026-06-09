# IsDialInAdapter

- ea: `0x140002030`
- end: `0x14000205c`
- name: `IsDialInAdapter`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140015cf0`
- `0x140015d30`
- `0x140015d70`

## callees

- `0x140002030`

## pseudocode

```c
__int64 __fastcall IsDialInAdapter(__int64 *a1)
{
  __int64 *i; // rax

  for ( i = (__int64 *)g_leDialInAdapterList; i != &g_leDialInAdapterList; i = (__int64 *)*i )
  {
    if ( i - 4 == a1 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140002030  mov     rax, cs:g_leDialInAdapterList
0x140002037  lea     r8, g_leDialInAdapterList
0x14000203e  cmp     rax, r8
0x140002041  jz      short loc_140002053
0x140002043  lea     rdx, [rax-20h]
0x140002047  cmp     rdx, rcx
0x14000204a  jnz     short loc_140002057
0x14000204c  mov     eax, 1
0x140002051  retn
0x140002053  xor     eax, eax
0x140002055  retn
0x140002057  mov     rax, [rax]
0x14000205a  jmp     short loc_14000203E
```
