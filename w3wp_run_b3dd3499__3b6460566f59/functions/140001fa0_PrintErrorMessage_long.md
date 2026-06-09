# PrintErrorMessage(long)

- ea: `0x140001fa0`
- end: `0x140001ff0`
- name: `?PrintErrorMessage@@YAXJ@Z`
- size: `80`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001840`
- `0x14000215c`

## callees

- `0x140001fa0`
- `0x140001ff8`

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
0x140001fa0  mov     eax, ecx
0x140001fa2  cmp     ecx, 80070015h
0x140001fa8  jnz     short loc_140001FB1
0x140001faa  mov     ecx, 61AEh
0x140001faf  jmp     short loc_140001FEB
0x140001fb1  cmp     eax, 80070044h
0x140001fb6  jnz     short loc_140001FBF
0x140001fb8  mov     ecx, 61ACh
0x140001fbd  jmp     short loc_140001FEB
0x140001fbf  cmp     eax, 8007000Dh
0x140001fc4  jnz     short loc_140001FCD
0x140001fc6  mov     ecx, 61ADh
0x140001fcb  jmp     short loc_140001FEB
0x140001fcd  cmp     eax, 80070038h
0x140001fd2  jnz     short loc_140001FDB
0x140001fd4  mov     ecx, 61AFh
0x140001fd9  jmp     short loc_140001FEB
0x140001fdb  xor     ecx, ecx
0x140001fdd  cmp     eax, 80070057h
0x140001fe2  setnz   cl
0x140001fe5  add     ecx, 61B0h; uID
0x140001feb  jmp     ?PrintResourceString@@YAXK@Z; PrintResourceString(ulong)
```
