# __GSHandlerCheckCommon

- ea: `0x180016c74`
- end: `0x180016cd7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016c50`

## callees

- `0x18000c240`
- `0x180016c74`

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
0x180016c74  mov     r10, rcx
0x180016c77  mov     r11, rdx
0x180016c7a  mov     ecx, [r8]
0x180016c7d  and     ecx, 0FFFFFFF8h
0x180016c80  test    byte ptr [r8], 4
0x180016c84  jz      short loc_180016C9B
0x180016c86  mov     eax, [r8+8]
0x180016c8a  movsxd  r9, dword ptr [r8+4]
0x180016c8e  neg     eax
0x180016c90  movsxd  rdx, eax
0x180016c93  add     r9, r10
0x180016c96  and     r9, rdx
0x180016c99  jmp     short loc_180016C9E
0x180016c9b  mov     r9, r10
0x180016c9e  movsxd  rax, ecx
0x180016ca1  mov     rdx, [rax+r9]
0x180016ca5  mov     rax, [r11+10h]
0x180016ca9  mov     ecx, [rax+8]
0x180016cac  mov     rax, [r11+8]
0x180016cb0  test    byte ptr [rcx+rax+3], 0Fh
0x180016cb5  jz      short loc_180016CC9
0x180016cb7  movzx   eax, byte ptr [rcx+rax+3]
0x180016cbc  mov     ecx, 0FFFFFFF0h
0x180016cc1  and     rax, rcx
0x180016cc4  add     rax, r10
0x180016cc7  jmp     short loc_180016CCC
0x180016cc9  mov     rax, r10
0x180016ccc  xor     rdx, rax
0x180016ccf  mov     rcx, rdx; StackCookie
0x180016cd2  jmp     __security_check_cookie
```
