# __GSHandlerCheckCommon

- ea: `0x180001e7c`
- end: `0x180001edf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001e58`
- `0x1800273ec`
- `0x180027454`

## callees

- `0x180001e7c`
- `0x180027510`

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
0x180001e7c  mov     r10, rcx
0x180001e7f  mov     r11, rdx
0x180001e82  mov     ecx, [r8]
0x180001e85  and     ecx, 0FFFFFFF8h
0x180001e88  test    byte ptr [r8], 4
0x180001e8c  jz      short loc_180001EA3
0x180001e8e  mov     eax, [r8+8]
0x180001e92  movsxd  r9, dword ptr [r8+4]
0x180001e96  neg     eax
0x180001e98  movsxd  rdx, eax
0x180001e9b  add     r9, r10
0x180001e9e  and     r9, rdx
0x180001ea1  jmp     short loc_180001EA6
0x180001ea3  mov     r9, r10
0x180001ea6  movsxd  rax, ecx
0x180001ea9  mov     rdx, [rax+r9]
0x180001ead  mov     rax, [r11+10h]
0x180001eb1  mov     ecx, [rax+8]
0x180001eb4  mov     rax, [r11+8]
0x180001eb8  test    byte ptr [rcx+rax+3], 0Fh
0x180001ebd  jz      short loc_180001ED1
0x180001ebf  movzx   eax, byte ptr [rcx+rax+3]
0x180001ec4  mov     ecx, 0FFFFFFF0h
0x180001ec9  and     rax, rcx
0x180001ecc  add     rax, r10
0x180001ecf  jmp     short loc_180001ED4
0x180001ed1  mov     rax, r10
0x180001ed4  xor     rdx, rax
0x180001ed7  mov     rcx, rdx; StackCookie
0x180001eda  jmp     __security_check_cookie
```
