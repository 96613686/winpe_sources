# __GSHandlerCheckCommon

- ea: `0x180001f7c`
- end: `0x180001fdf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f58`
- `0x1800141b8`

## callees

- `0x180001f7c`
- `0x180014270`

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
0x180001f7c  mov     r10, rcx
0x180001f7f  mov     r11, rdx
0x180001f82  mov     ecx, [r8]
0x180001f85  and     ecx, 0FFFFFFF8h
0x180001f88  test    byte ptr [r8], 4
0x180001f8c  jz      short loc_180001FA3
0x180001f8e  mov     eax, [r8+8]
0x180001f92  movsxd  r9, dword ptr [r8+4]
0x180001f96  neg     eax
0x180001f98  movsxd  rdx, eax
0x180001f9b  add     r9, r10
0x180001f9e  and     r9, rdx
0x180001fa1  jmp     short loc_180001FA6
0x180001fa3  mov     r9, r10
0x180001fa6  movsxd  rax, ecx
0x180001fa9  mov     rdx, [rax+r9]
0x180001fad  mov     rax, [r11+10h]
0x180001fb1  mov     ecx, [rax+8]
0x180001fb4  mov     rax, [r11+8]
0x180001fb8  test    byte ptr [rcx+rax+3], 0Fh
0x180001fbd  jz      short loc_180001FD1
0x180001fbf  movzx   eax, byte ptr [rcx+rax+3]
0x180001fc4  mov     ecx, 0FFFFFFF0h
0x180001fc9  and     rax, rcx
0x180001fcc  add     rax, r10
0x180001fcf  jmp     short loc_180001FD4
0x180001fd1  mov     rax, r10
0x180001fd4  xor     rdx, rax
0x180001fd7  mov     rcx, rdx; StackCookie
0x180001fda  jmp     __security_check_cookie
```
