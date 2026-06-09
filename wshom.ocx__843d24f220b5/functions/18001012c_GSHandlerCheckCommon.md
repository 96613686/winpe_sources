# __GSHandlerCheckCommon

- ea: `0x18001012c`
- end: `0x18001018f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010108`
- `0x180010198`

## callees

- `0x18001012c`
- `0x180010250`

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
0x18001012c  mov     r10, rcx
0x18001012f  mov     r11, rdx
0x180010132  mov     ecx, [r8]
0x180010135  and     ecx, 0FFFFFFF8h
0x180010138  test    byte ptr [r8], 4
0x18001013c  jz      short loc_180010153
0x18001013e  mov     eax, [r8+8]
0x180010142  movsxd  r9, dword ptr [r8+4]
0x180010146  neg     eax
0x180010148  movsxd  rdx, eax
0x18001014b  add     r9, r10
0x18001014e  and     r9, rdx
0x180010151  jmp     short loc_180010156
0x180010153  mov     r9, r10
0x180010156  movsxd  rax, ecx
0x180010159  mov     rdx, [rax+r9]
0x18001015d  mov     rax, [r11+10h]
0x180010161  mov     ecx, [rax+8]
0x180010164  mov     rax, [r11+8]
0x180010168  test    byte ptr [rcx+rax+3], 0Fh
0x18001016d  jz      short loc_180010181
0x18001016f  movzx   eax, byte ptr [rcx+rax+3]
0x180010174  mov     ecx, 0FFFFFFF0h
0x180010179  and     rax, rcx
0x18001017c  add     rax, r10
0x18001017f  jmp     short loc_180010184
0x180010181  mov     rax, r10
0x180010184  xor     rdx, rax
0x180010187  mov     rcx, rdx; StackCookie
0x18001018a  jmp     __security_check_cookie
```
