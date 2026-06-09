# __GSHandlerCheckCommon

- ea: `0x18001f860`
- end: `0x18001f8c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f83c`
- `0x18001f8cc`

## callees

- `0x18001f860`
- `0x18001f980`

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
0x18001f860  mov     r10, rcx
0x18001f863  mov     r11, rdx
0x18001f866  mov     ecx, [r8]
0x18001f869  and     ecx, 0FFFFFFF8h
0x18001f86c  test    byte ptr [r8], 4
0x18001f870  jz      short loc_18001F887
0x18001f872  mov     eax, [r8+8]
0x18001f876  movsxd  r9, dword ptr [r8+4]
0x18001f87a  neg     eax
0x18001f87c  movsxd  rdx, eax
0x18001f87f  add     r9, r10
0x18001f882  and     r9, rdx
0x18001f885  jmp     short loc_18001F88A
0x18001f887  mov     r9, r10
0x18001f88a  movsxd  rax, ecx
0x18001f88d  mov     rdx, [rax+r9]
0x18001f891  mov     rax, [r11+10h]
0x18001f895  mov     ecx, [rax+8]
0x18001f898  mov     rax, [r11+8]
0x18001f89c  test    byte ptr [rcx+rax+3], 0Fh
0x18001f8a1  jz      short loc_18001F8B5
0x18001f8a3  movzx   eax, byte ptr [rcx+rax+3]
0x18001f8a8  mov     ecx, 0FFFFFFF0h
0x18001f8ad  and     rax, rcx
0x18001f8b0  add     rax, r10
0x18001f8b3  jmp     short loc_18001F8B8
0x18001f8b5  mov     rax, r10
0x18001f8b8  xor     rdx, rax
0x18001f8bb  mov     rcx, rdx; StackCookie
0x18001f8be  jmp     __security_check_cookie
```
