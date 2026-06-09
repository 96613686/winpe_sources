# __GSHandlerCheckCommon

- ea: `0x14003ffc8`
- end: `0x14004002b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003ffa4`
- `0x140040034`

## callees

- `0x14003ffc8`
- `0x140040130`

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
0x14003ffc8  mov     r10, rcx
0x14003ffcb  mov     r11, rdx
0x14003ffce  mov     ecx, [r8]
0x14003ffd1  and     ecx, 0FFFFFFF8h
0x14003ffd4  test    byte ptr [r8], 4
0x14003ffd8  jz      short loc_14003FFEF
0x14003ffda  mov     eax, [r8+8]
0x14003ffde  movsxd  r9, dword ptr [r8+4]
0x14003ffe2  neg     eax
0x14003ffe4  movsxd  rdx, eax
0x14003ffe7  add     r9, r10
0x14003ffea  and     r9, rdx
0x14003ffed  jmp     short loc_14003FFF2
0x14003ffef  mov     r9, r10
0x14003fff2  movsxd  rax, ecx
0x14003fff5  mov     rdx, [rax+r9]
0x14003fff9  mov     rax, [r11+10h]
0x14003fffd  mov     ecx, [rax+8]
0x140040000  mov     rax, [r11+8]
0x140040004  test    byte ptr [rcx+rax+3], 0Fh
0x140040009  jz      short loc_14004001D
0x14004000b  movzx   eax, byte ptr [rcx+rax+3]
0x140040010  mov     ecx, 0FFFFFFF0h
0x140040015  and     rax, rcx
0x140040018  add     rax, r10
0x14004001b  jmp     short loc_140040020
0x14004001d  mov     rax, r10
0x140040020  xor     rdx, rax
0x140040023  mov     rcx, rdx; StackCookie
0x140040026  jmp     __security_check_cookie
```
