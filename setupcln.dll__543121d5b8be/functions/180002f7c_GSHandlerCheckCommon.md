# __GSHandlerCheckCommon

- ea: `0x180002f7c`
- end: `0x180002fdf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002f58`
- `0x180013120`

## callees

- `0x180002f7c`
- `0x1800131e0`

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
0x180002f7c  mov     r10, rcx
0x180002f7f  mov     r11, rdx
0x180002f82  mov     ecx, [r8]
0x180002f85  and     ecx, 0FFFFFFF8h
0x180002f88  test    byte ptr [r8], 4
0x180002f8c  jz      short loc_180002FA3
0x180002f8e  mov     eax, [r8+8]
0x180002f92  movsxd  r9, dword ptr [r8+4]
0x180002f96  neg     eax
0x180002f98  movsxd  rdx, eax
0x180002f9b  add     r9, r10
0x180002f9e  and     r9, rdx
0x180002fa1  jmp     short loc_180002FA6
0x180002fa3  mov     r9, r10
0x180002fa6  movsxd  rax, ecx
0x180002fa9  mov     rdx, [rax+r9]
0x180002fad  mov     rax, [r11+10h]
0x180002fb1  mov     ecx, [rax+8]
0x180002fb4  mov     rax, [r11+8]
0x180002fb8  test    byte ptr [rcx+rax+3], 0Fh
0x180002fbd  jz      short loc_180002FD1
0x180002fbf  movzx   eax, byte ptr [rcx+rax+3]
0x180002fc4  mov     ecx, 0FFFFFFF0h
0x180002fc9  and     rax, rcx
0x180002fcc  add     rax, r10
0x180002fcf  jmp     short loc_180002FD4
0x180002fd1  mov     rax, r10
0x180002fd4  xor     rdx, rax
0x180002fd7  mov     rcx, rdx; StackCookie
0x180002fda  jmp     __security_check_cookie
```
