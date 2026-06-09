# IPxlatFindInstance

- ea: `0x140034b28`
- end: `0x140034b49`
- name: `IPxlatFindInstance`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400164a8`
- `0x140016760`
- `0x1400169e4`
- `0x140016af0`
- `0x140034990`
- `0x140034a60`

## callees

- `0x140034b28`

## pseudocode

```c
PVOID *__fastcall IPxlatFindInstance(PVOID a1)
{
  PVOID *result; // rax

  for ( result = (PVOID *)qword_1400278E0; &qword_1400278E0 != result; result = (PVOID *)*result )
  {
    if ( result[2] == a1 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x140034b28  mov     rax, cs:qword_1400278E0
0x140034b2f  lea     rdx, qword_1400278E0
0x140034b36  cmp     rdx, rax
0x140034b39  jz      short loc_140034B46
0x140034b3b  cmp     [rax+10h], rcx
0x140034b3f  jz      short locret_140034B48
0x140034b41  mov     rax, [rax]
0x140034b44  jmp     short loc_140034B2F
0x140034b46  xor     eax, eax
0x140034b48  retn
```
