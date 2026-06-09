# __GSHandlerCheckCommon

- ea: `0x180004d60`
- end: `0x180004dc3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004d3c`
- `0x180004dcc`

## callees

- `0x180001510`
- `0x180004d60`

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
0x180004d60  mov     r10, rcx
0x180004d63  mov     r11, rdx
0x180004d66  mov     ecx, [r8]
0x180004d69  and     ecx, 0FFFFFFF8h
0x180004d6c  test    byte ptr [r8], 4
0x180004d70  jz      short loc_180004D87
0x180004d72  mov     eax, [r8+8]
0x180004d76  movsxd  r9, dword ptr [r8+4]
0x180004d7a  neg     eax
0x180004d7c  movsxd  rdx, eax
0x180004d7f  add     r9, r10
0x180004d82  and     r9, rdx
0x180004d85  jmp     short loc_180004D8A
0x180004d87  mov     r9, r10
0x180004d8a  movsxd  rax, ecx
0x180004d8d  mov     rdx, [rax+r9]
0x180004d91  mov     rax, [r11+10h]
0x180004d95  mov     ecx, [rax+8]
0x180004d98  mov     rax, [r11+8]
0x180004d9c  test    byte ptr [rcx+rax+3], 0Fh
0x180004da1  jz      short loc_180004DB5
0x180004da3  movzx   eax, byte ptr [rcx+rax+3]
0x180004da8  mov     ecx, 0FFFFFFF0h
0x180004dad  and     rax, rcx
0x180004db0  add     rax, r10
0x180004db3  jmp     short loc_180004DB8
0x180004db5  mov     rax, r10
0x180004db8  xor     rdx, rax
0x180004dbb  mov     rcx, rdx; StackCookie
0x180004dbe  jmp     __security_check_cookie
```
