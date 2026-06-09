# SdbBeginWriteListTag

- ea: `0x140014500`
- end: `0x14001456d`
- name: `SdbBeginWriteListTag`
- size: `109`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140014574`
- `0x1400147d0`
- `0x1400153a4`
- `0x140019410`
- `0x14001c730`
- `0x14001d808`
- `0x14001fc0c`
- `0x1400207cc`

## callees

- `0x14001008c`
- `0x140014500`
- `0x140015838`

## string_xrefs

- `0x14001452c`: `SdbBeginWriteListTag`
- `0x140014556`: `Failed to write the data`

## pseudocode

```c
__int64 __fastcall SdbBeginWriteListTag(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx

  if ( (a2 & 0xF000) != 0x7000 )
  {
    AslLogCallPrintf(1, "SdbBeginWriteListTag", 374, "This is not a list tag");
    return 0;
  }
  v3 = *(_DWORD *)(a1 + 20);
  if ( !(unsigned int)SdbpWriteTagData(a1, a2, 0, 0x20000000) )
  {
    AslLogCallPrintf(1, "SdbBeginWriteListTag", 379, "Failed to write the data");
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x140014500  push    rbx
0x140014502  sub     rsp, 20h
0x140014506  mov     r8d, 0F000h
0x14001450c  movzx   eax, dx
0x14001450f  and     ax, r8w
0x140014513  mov     r8d, 7000h
0x140014519  cmp     ax, r8w
0x14001451d  jz      short loc_140014541
0x14001451f  lea     r9, aThisIsNotAList; "This is not a list tag"
0x140014526  mov     r8d, 176h
0x14001452c  lea     rdx, aSdbbeginwritel_0; "SdbBeginWriteListTag"
0x140014533  mov     ecx, 1
0x140014538  call    AslLogCallPrintf
0x14001453d  xor     eax, eax
0x14001453f  jmp     short loc_140014567
0x140014541  mov     ebx, [rcx+14h]
0x140014544  mov     r9d, 20000000h
0x14001454a  xor     r8d, r8d
0x14001454d  call    SdbpWriteTagData
0x140014552  test    eax, eax
0x140014554  jnz     short loc_140014565
0x140014556  lea     r9, aFailedToWriteT_0; "Failed to write the data"
0x14001455d  mov     r8d, 17Bh
0x140014563  jmp     short loc_14001452C
0x140014565  mov     eax, ebx
0x140014567  add     rsp, 20h
0x14001456b  pop     rbx
0x14001456c  retn
```
