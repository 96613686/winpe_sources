# __GSHandlerCheckCommon

- ea: `0x180002d30`
- end: `0x180002d93`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002d0c`

## callees

- `0x180002d30`
- `0x180002dc0`

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
0x180002d30  mov     r10, rcx
0x180002d33  mov     r11, rdx
0x180002d36  mov     ecx, [r8]
0x180002d39  and     ecx, 0FFFFFFF8h
0x180002d3c  test    byte ptr [r8], 4
0x180002d40  jz      short loc_180002D57
0x180002d42  mov     eax, [r8+8]
0x180002d46  movsxd  r9, dword ptr [r8+4]
0x180002d4a  neg     eax
0x180002d4c  movsxd  rdx, eax
0x180002d4f  add     r9, r10
0x180002d52  and     r9, rdx
0x180002d55  jmp     short loc_180002D5A
0x180002d57  mov     r9, r10
0x180002d5a  movsxd  rax, ecx
0x180002d5d  mov     rdx, [rax+r9]
0x180002d61  mov     rax, [r11+10h]
0x180002d65  mov     ecx, [rax+8]
0x180002d68  mov     rax, [r11+8]
0x180002d6c  test    byte ptr [rcx+rax+3], 0Fh
0x180002d71  jz      short loc_180002D85
0x180002d73  movzx   eax, byte ptr [rcx+rax+3]
0x180002d78  mov     ecx, 0FFFFFFF0h
0x180002d7d  and     rax, rcx
0x180002d80  add     rax, r10
0x180002d83  jmp     short loc_180002D88
0x180002d85  mov     rax, r10
0x180002d88  xor     rdx, rax
0x180002d8b  mov     rcx, rdx; StackCookie
0x180002d8e  jmp     __security_check_cookie
```
