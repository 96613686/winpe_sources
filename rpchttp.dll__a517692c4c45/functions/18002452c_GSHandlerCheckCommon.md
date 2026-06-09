# __GSHandlerCheckCommon

- ea: `0x18002452c`
- end: `0x18002458f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024508`
- `0x180024598`

## callees

- `0x18002452c`
- `0x180024640`

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
0x18002452c  mov     r10, rcx
0x18002452f  mov     r11, rdx
0x180024532  mov     ecx, [r8]
0x180024535  and     ecx, 0FFFFFFF8h
0x180024538  test    byte ptr [r8], 4
0x18002453c  jz      short loc_180024553
0x18002453e  mov     eax, [r8+8]
0x180024542  movsxd  r9, dword ptr [r8+4]
0x180024546  neg     eax
0x180024548  movsxd  rdx, eax
0x18002454b  add     r9, r10
0x18002454e  and     r9, rdx
0x180024551  jmp     short loc_180024556
0x180024553  mov     r9, r10
0x180024556  movsxd  rax, ecx
0x180024559  mov     rdx, [rax+r9]
0x18002455d  mov     rax, [r11+10h]
0x180024561  mov     ecx, [rax+8]
0x180024564  mov     rax, [r11+8]
0x180024568  test    byte ptr [rcx+rax+3], 0Fh
0x18002456d  jz      short loc_180024581
0x18002456f  movzx   eax, byte ptr [rcx+rax+3]
0x180024574  mov     ecx, 0FFFFFFF0h
0x180024579  and     rax, rcx
0x18002457c  add     rax, r10
0x18002457f  jmp     short loc_180024584
0x180024581  mov     rax, r10
0x180024584  xor     rdx, rax
0x180024587  mov     rcx, rdx; StackCookie
0x18002458a  jmp     __security_check_cookie
```
