# UdfUpdateChecksumAndCrc

- ea: `0x140009450`
- end: `0x1400094ac`
- name: `UdfUpdateChecksumAndCrc`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140004514`
- `0x1400050d8`
- `0x14000efc8`
- `0x140012308`
- `0x14001636c`
- `0x140016ac0`
- `0x140017c08`
- `0x140017fa8`
- `0x14001b938`
- `0x140030818`
- `0x140039938`
- `0x14003a274`
- `0x14003aa44`
- `0x14003b79c`

## callees

- `0x140009450`
- `0x14004ce00`

## pseudocode

```c
__int64 __fastcall UdfUpdateChecksumAndCrc(__int64 a1, int a2)
{
  unsigned int v2; // edx
  unsigned __int16 v3; // ax
  __int16 v4; // ax
  __int64 v5; // r11
  __int64 result; // rax
  char v7; // cl

  v2 = a2 - 16;
  v3 = -1;
  if ( v2 <= 0xFFFF )
    v3 = v2;
  *(_WORD *)(a1 + 10) = v3;
  v4 = UdfComputeCrc16(a1 + 16, v3);
  *(_WORD *)(v5 + 8) = v4;
  result = 5;
  v7 = *(_BYTE *)v5 + *(_BYTE *)(v5 + 1) + *(_BYTE *)(v5 + 2) + *(_BYTE *)(v5 + 3);
  *(_BYTE *)(v5 + 4) = v7;
  do
  {
    v7 += *(_BYTE *)(v5 + result++);
    *(_BYTE *)(v5 + 4) = v7;
  }
  while ( result != 16 );
  return result;
}

```

## disassembly

```asm
0x140009450  sub     rsp, 28h
0x140009454  add     edx, 0FFFFFFF0h
0x140009457  mov     eax, 0FFFFh
0x14000945c  mov     r11, rcx
0x14000945f  cmp     edx, eax
0x140009461  jbe     short loc_1400094A7
0x140009463  mov     [rcx+0Ah], ax
0x140009467  add     rcx, 10h
0x14000946b  movzx   edx, ax
0x14000946e  call    UdfComputeCrc16
0x140009473  mov     [r11+8], ax
0x140009478  mov     eax, 5
0x14000947d  mov     cl, [r11+3]
0x140009481  add     cl, [r11+2]
0x140009485  add     cl, [r11+1]
0x140009489  add     cl, [r11]
0x14000948c  mov     [r11+4], cl
0x140009490  add     cl, [r11+rax]
0x140009494  inc     rax
0x140009497  mov     [r11+4], cl
0x14000949b  cmp     rax, 10h
0x14000949f  jnz     short loc_140009490
0x1400094a1  add     rsp, 28h
0x1400094a5  retn
0x1400094a7  movzx   eax, dx
0x1400094aa  jmp     short loc_140009463
```
