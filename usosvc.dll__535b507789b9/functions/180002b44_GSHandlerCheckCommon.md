# __GSHandlerCheckCommon

- ea: `0x180002b44`
- end: `0x180002ba7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b20`
- `0x18000e38c`

## callees

- `0x1800026d0`
- `0x180002b44`

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
0x180002b44  mov     r10, rcx
0x180002b47  mov     r11, rdx
0x180002b4a  mov     ecx, [r8]
0x180002b4d  and     ecx, 0FFFFFFF8h
0x180002b50  test    byte ptr [r8], 4
0x180002b54  jz      short loc_180002B6B
0x180002b56  mov     eax, [r8+8]
0x180002b5a  movsxd  r9, dword ptr [r8+4]
0x180002b5e  neg     eax
0x180002b60  movsxd  rdx, eax
0x180002b63  add     r9, r10
0x180002b66  and     r9, rdx
0x180002b69  jmp     short loc_180002B6E
0x180002b6b  mov     r9, r10
0x180002b6e  movsxd  rax, ecx
0x180002b71  mov     rdx, [rax+r9]
0x180002b75  mov     rax, [r11+10h]
0x180002b79  mov     ecx, [rax+8]
0x180002b7c  mov     rax, [r11+8]
0x180002b80  test    byte ptr [rcx+rax+3], 0Fh
0x180002b85  jz      short loc_180002B99
0x180002b87  movzx   eax, byte ptr [rcx+rax+3]
0x180002b8c  mov     ecx, 0FFFFFFF0h
0x180002b91  and     rax, rcx
0x180002b94  add     rax, r10
0x180002b97  jmp     short loc_180002B9C
0x180002b99  mov     rax, r10
0x180002b9c  xor     rdx, rax
0x180002b9f  mov     rcx, rdx; StackCookie
0x180002ba2  jmp     __security_check_cookie
```
