# __GSHandlerCheckCommon

- ea: `0x18000ae10`
- end: `0x18000ae73`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000adec`

## callees

- `0x18000ae10`
- `0x18000aea0`

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
0x18000ae10  mov     r10, rcx
0x18000ae13  mov     r11, rdx
0x18000ae16  mov     ecx, [r8]
0x18000ae19  and     ecx, 0FFFFFFF8h
0x18000ae1c  test    byte ptr [r8], 4
0x18000ae20  jz      short loc_18000AE37
0x18000ae22  mov     eax, [r8+8]
0x18000ae26  movsxd  r9, dword ptr [r8+4]
0x18000ae2a  neg     eax
0x18000ae2c  movsxd  rdx, eax
0x18000ae2f  add     r9, r10
0x18000ae32  and     r9, rdx
0x18000ae35  jmp     short loc_18000AE3A
0x18000ae37  mov     r9, r10
0x18000ae3a  movsxd  rax, ecx
0x18000ae3d  mov     rdx, [rax+r9]
0x18000ae41  mov     rax, [r11+10h]
0x18000ae45  mov     ecx, [rax+8]
0x18000ae48  mov     rax, [r11+8]
0x18000ae4c  test    byte ptr [rcx+rax+3], 0Fh
0x18000ae51  jz      short loc_18000AE65
0x18000ae53  movzx   eax, byte ptr [rcx+rax+3]
0x18000ae58  mov     ecx, 0FFFFFFF0h
0x18000ae5d  and     rax, rcx
0x18000ae60  add     rax, r10
0x18000ae63  jmp     short loc_18000AE68
0x18000ae65  mov     rax, r10
0x18000ae68  xor     rdx, rax
0x18000ae6b  mov     rcx, rdx; StackCookie
0x18000ae6e  jmp     __security_check_cookie
```
