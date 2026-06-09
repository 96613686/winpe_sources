# PrintErrorMessage(long)

- ea: `0x1400020c0`
- end: `0x140002110`
- name: `?PrintErrorMessage@@YAXJ@Z`
- size: `80`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001840`
- `0x1400022c4`

## callees

- `0x1400020c0`
- `0x140002118`

## pseudocode

```c
void __fastcall PrintErrorMessage(int a1)
{
  switch ( a1 )
  {
    case -2147024875:
      PrintResourceString(0x61AEu);
      break;
    case -2147024828:
      PrintResourceString(0x61ACu);
      break;
    case -2147024883:
      PrintResourceString(0x61ADu);
      break;
    case -2147024840:
      PrintResourceString(0x61AFu);
      break;
    default:
      PrintResourceString((a1 != -2147024809) + 25008);
      break;
  }
}

```

## disassembly

```asm
0x1400020c0  mov     eax, ecx
0x1400020c2  cmp     ecx, 80070015h
0x1400020c8  jnz     short loc_1400020D1
0x1400020ca  mov     ecx, 61AEh
0x1400020cf  jmp     short loc_14000210B
0x1400020d1  cmp     eax, 80070044h
0x1400020d6  jnz     short loc_1400020DF
0x1400020d8  mov     ecx, 61ACh
0x1400020dd  jmp     short loc_14000210B
0x1400020df  cmp     eax, 8007000Dh
0x1400020e4  jnz     short loc_1400020ED
0x1400020e6  mov     ecx, 61ADh
0x1400020eb  jmp     short loc_14000210B
0x1400020ed  cmp     eax, 80070038h
0x1400020f2  jnz     short loc_1400020FB
0x1400020f4  mov     ecx, 61AFh
0x1400020f9  jmp     short loc_14000210B
0x1400020fb  xor     ecx, ecx
0x1400020fd  cmp     eax, 80070057h
0x140002102  setnz   cl
0x140002105  add     ecx, 61B0h; uID
0x14000210b  jmp     ?PrintResourceString@@YAXK@Z; PrintResourceString(ulong)
```
