# __GSHandlerCheckCommon

- ea: `0x18001c658`
- end: `0x18001c6bb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c634`
- `0x18001c6c4`
- `0x18001c72c`

## callees

- `0x180008a90`
- `0x18001c658`

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
0x18001c658  mov     r10, rcx
0x18001c65b  mov     r11, rdx
0x18001c65e  mov     ecx, [r8]
0x18001c661  and     ecx, 0FFFFFFF8h
0x18001c664  test    byte ptr [r8], 4
0x18001c668  jz      short loc_18001C67F
0x18001c66a  mov     eax, [r8+8]
0x18001c66e  movsxd  r9, dword ptr [r8+4]
0x18001c672  neg     eax
0x18001c674  movsxd  rdx, eax
0x18001c677  add     r9, r10
0x18001c67a  and     r9, rdx
0x18001c67d  jmp     short loc_18001C682
0x18001c67f  mov     r9, r10
0x18001c682  movsxd  rax, ecx
0x18001c685  mov     rdx, [rax+r9]
0x18001c689  mov     rax, [r11+10h]
0x18001c68d  mov     ecx, [rax+8]
0x18001c690  mov     rax, [r11+8]
0x18001c694  test    byte ptr [rcx+rax+3], 0Fh
0x18001c699  jz      short loc_18001C6AD
0x18001c69b  movzx   eax, byte ptr [rcx+rax+3]
0x18001c6a0  mov     ecx, 0FFFFFFF0h
0x18001c6a5  and     rax, rcx
0x18001c6a8  add     rax, r10
0x18001c6ab  jmp     short loc_18001C6B0
0x18001c6ad  mov     rax, r10
0x18001c6b0  xor     rdx, rax
0x18001c6b3  mov     rcx, rdx; StackCookie
0x18001c6b6  jmp     __security_check_cookie
```
