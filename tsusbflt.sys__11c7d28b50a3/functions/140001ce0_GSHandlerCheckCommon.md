# __GSHandlerCheckCommon

- ea: `0x140001ce0`
- end: `0x140001d50`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001cbc`

## callees

- `0x140001ce0`
- `0x14000a9f0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x140001ce0  sub     rsp, 28h
0x140001ce4  mov     eax, [r8]
0x140001ce7  mov     r10, rcx
0x140001cea  mov     ecx, eax
0x140001cec  mov     r11, rdx
0x140001cef  and     ecx, 0FFFFFFF8h
0x140001cf2  test    al, 4
0x140001cf4  jz      short loc_140001D0B
0x140001cf6  mov     eax, [r8+8]
0x140001cfa  movsxd  r9, dword ptr [r8+4]
0x140001cfe  neg     eax
0x140001d00  movsxd  rdx, eax
0x140001d03  add     r9, r10
0x140001d06  and     r9, rdx
0x140001d09  jmp     short loc_140001D0E
0x140001d0b  mov     r9, r10
0x140001d0e  movsxd  rax, ecx
0x140001d11  mov     rdx, [rax+r9]
0x140001d15  mov     rax, [r11+10h]
0x140001d19  mov     ecx, [rax+8]
0x140001d1c  mov     rax, [r11+8]
0x140001d20  movzx   r8d, byte ptr [rcx+rax+3]
0x140001d26  test    r8b, 0Fh
0x140001d2a  jz      short loc_140001D3C
0x140001d2c  mov     eax, r8d
0x140001d2f  mov     ecx, 0FFFFFFF0h
0x140001d34  and     rax, rcx
0x140001d37  add     rax, r10
0x140001d3a  jmp     short loc_140001D3F
0x140001d3c  mov     rax, r10
0x140001d3f  xor     rdx, rax
0x140001d42  mov     rcx, rdx; StackCookie
0x140001d45  call    __security_check_cookie
0x140001d4a  add     rsp, 28h
0x140001d4e  retn
```
