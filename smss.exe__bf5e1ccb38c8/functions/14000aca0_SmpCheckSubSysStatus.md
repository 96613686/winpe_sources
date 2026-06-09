# SmpCheckSubSysStatus

- ea: `0x14000aca0`
- end: `0x14000acc5`
- name: `SmpCheckSubSysStatus`
- size: `37`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001580`
- `0x140001630`
- `0x140001f60`
- `0x140002bb0`
- `0x140008210`
- `0x140018154`

## callees

- `0x14000aca0`

## pseudocode

```c
__int64 __fastcall SmpCheckSubSysStatus(__int64 a1)
{
  int v1; // eax

  v1 = *(_DWORD *)(a1 + 8);
  if ( (v1 & 4) != 0 )
    return 1;
  if ( (v1 & 1) == 0 )
    return *(_DWORD *)(a1 + 24) != -1;
  return *(_QWORD *)(a1 + 48) != 0;
}

```

## disassembly

```asm
0x14000aca0  mov     eax, [rcx+8]
0x14000aca3  test    al, 4
0x14000aca5  jz      short loc_14000ACAD
0x14000aca7  mov     eax, 1
0x14000acac  retn
0x14000acad  test    al, 1
0x14000acaf  jz      short loc_14000ACBB
0x14000acb1  cmp     qword ptr [rcx+30h], 0
0x14000acb6  jnz     short loc_14000ACA7
0x14000acb8  xor     eax, eax
0x14000acba  retn
0x14000acbb  xor     eax, eax
0x14000acbd  cmp     dword ptr [rcx+18h], 0FFFFFFFFh
0x14000acc1  setnz   al
0x14000acc4  retn
```
