# OncRpcSeSecStatusToGssMajor

- ea: `0x14000a1ec`
- end: `0x14000a244`
- name: `OncRpcSeSecStatusToGssMajor`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140009540`
- `0x14000a814`
- `0x14000aac4`
- `0x14000b498`
- `0x14000bf88`
- `0x14000c470`
- `0x14000c56c`
- `0x14000c740`
- `0x14000c7f4`
- `0x14000cb78`

## callees

- `0x14000a1ec`

## pseudocode

```c
__int64 __fastcall OncRpcSeSecStatusToGssMajor(int a1)
{
  __int64 result; // rax

  switch ( a1 )
  {
    case -2146893055:
      return 655360;
    case -2146893048:
      return 589824;
    case -2146893046:
      return 917504;
    case 0:
      return 0;
    case 590610:
      return 1;
  }
  result = 720896;
  if ( a1 != 590625 )
    return 851968;
  return result;
}

```

## disassembly

```asm
0x14000a1ec  cmp     ecx, 80090301h
0x14000a1f2  jz      short loc_14000A23E
0x14000a1f4  cmp     ecx, 80090308h
0x14000a1fa  jz      short loc_14000A237
0x14000a1fc  cmp     ecx, 8009030Ah
0x14000a202  jz      short loc_14000A230
0x14000a204  test    ecx, ecx
0x14000a206  jz      short loc_14000A22C
0x14000a208  cmp     ecx, 90312h
0x14000a20e  jz      short loc_14000A225
0x14000a210  cmp     ecx, 90321h
0x14000a216  mov     eax, 0B0000h
0x14000a21b  mov     edx, 0D0000h
0x14000a220  cmovnz  eax, edx
0x14000a223  retn
0x14000a225  mov     eax, 1
0x14000a22a  retn
0x14000a22c  xor     eax, eax
0x14000a22e  retn
0x14000a230  mov     eax, 0E0000h
0x14000a235  retn
0x14000a237  mov     eax, 90000h
0x14000a23c  retn
0x14000a23e  mov     eax, 0A0000h
0x14000a243  retn
```
