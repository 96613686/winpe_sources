# __GSHandlerCheckCommon

- ea: `0x1800434f0`
- end: `0x180043553`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800434cc`
- `0x18004355c`

## callees

- `0x180035e50`
- `0x1800434f0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x1800434f0  mov     r10, rcx
0x1800434f3  mov     r11, rdx
0x1800434f6  mov     ecx, [r8]
0x1800434f9  and     ecx, 0FFFFFFF8h
0x1800434fc  test    byte ptr [r8], 4
0x180043500  jz      short loc_180043517
0x180043502  mov     eax, [r8+8]
0x180043506  movsxd  r9, dword ptr [r8+4]
0x18004350a  neg     eax
0x18004350c  movsxd  rdx, eax
0x18004350f  add     r9, r10
0x180043512  and     r9, rdx
0x180043515  jmp     short loc_18004351A
0x180043517  mov     r9, r10
0x18004351a  movsxd  rax, ecx
0x18004351d  mov     rdx, [rax+r9]
0x180043521  mov     rax, [r11+10h]
0x180043525  mov     ecx, [rax+8]
0x180043528  mov     rax, [r11+8]
0x18004352c  test    byte ptr [rcx+rax+3], 0Fh
0x180043531  jz      short loc_180043545
0x180043533  movzx   eax, byte ptr [rcx+rax+3]
0x180043538  mov     ecx, 0FFFFFFF0h
0x18004353d  and     rax, rcx
0x180043540  add     rax, r10
0x180043543  jmp     short loc_180043548
0x180043545  mov     rax, r10
0x180043548  xor     rdx, rax
0x18004354b  mov     rcx, rdx; StackCookie
0x18004354e  jmp     __security_check_cookie
```
