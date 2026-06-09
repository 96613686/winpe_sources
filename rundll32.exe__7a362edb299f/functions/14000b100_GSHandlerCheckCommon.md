# __GSHandlerCheckCommon

- ea: `0x14000b100`
- end: `0x14000b163`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b0dc`

## callees

- `0x1400015a0`
- `0x14000b100`

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
0x14000b100  mov     r10, rcx
0x14000b103  mov     r11, rdx
0x14000b106  mov     ecx, [r8]
0x14000b109  and     ecx, 0FFFFFFF8h
0x14000b10c  test    byte ptr [r8], 4
0x14000b110  jz      short loc_14000B127
0x14000b112  mov     eax, [r8+8]
0x14000b116  movsxd  r9, dword ptr [r8+4]
0x14000b11a  neg     eax
0x14000b11c  movsxd  rdx, eax
0x14000b11f  add     r9, r10
0x14000b122  and     r9, rdx
0x14000b125  jmp     short loc_14000B12A
0x14000b127  mov     r9, r10
0x14000b12a  movsxd  rax, ecx
0x14000b12d  mov     rdx, [rax+r9]
0x14000b131  mov     rax, [r11+10h]
0x14000b135  mov     ecx, [rax+8]
0x14000b138  mov     rax, [r11+8]
0x14000b13c  test    byte ptr [rcx+rax+3], 0Fh
0x14000b141  jz      short loc_14000B155
0x14000b143  movzx   eax, byte ptr [rcx+rax+3]
0x14000b148  mov     ecx, 0FFFFFFF0h
0x14000b14d  and     rax, rcx
0x14000b150  add     rax, r10
0x14000b153  jmp     short loc_14000B158
0x14000b155  mov     rax, r10
0x14000b158  xor     rdx, rax
0x14000b15b  mov     rcx, rdx; StackCookie
0x14000b15e  jmp     __security_check_cookie
```
