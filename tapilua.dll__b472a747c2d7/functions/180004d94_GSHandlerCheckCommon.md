# __GSHandlerCheckCommon

- ea: `0x180004d94`
- end: `0x180004df7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004d70`
- `0x180004e00`
- `0x180004e68`

## callees

- `0x180001470`
- `0x180004d94`

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
0x180004d94  mov     r10, rcx
0x180004d97  mov     r11, rdx
0x180004d9a  mov     ecx, [r8]
0x180004d9d  and     ecx, 0FFFFFFF8h
0x180004da0  test    byte ptr [r8], 4
0x180004da4  jz      short loc_180004DBB
0x180004da6  mov     eax, [r8+8]
0x180004daa  movsxd  r9, dword ptr [r8+4]
0x180004dae  neg     eax
0x180004db0  movsxd  rdx, eax
0x180004db3  add     r9, r10
0x180004db6  and     r9, rdx
0x180004db9  jmp     short loc_180004DBE
0x180004dbb  mov     r9, r10
0x180004dbe  movsxd  rax, ecx
0x180004dc1  mov     rdx, [rax+r9]
0x180004dc5  mov     rax, [r11+10h]
0x180004dc9  mov     ecx, [rax+8]
0x180004dcc  mov     rax, [r11+8]
0x180004dd0  test    byte ptr [rcx+rax+3], 0Fh
0x180004dd5  jz      short loc_180004DE9
0x180004dd7  movzx   eax, byte ptr [rcx+rax+3]
0x180004ddc  mov     ecx, 0FFFFFFF0h
0x180004de1  and     rax, rcx
0x180004de4  add     rax, r10
0x180004de7  jmp     short loc_180004DEC
0x180004de9  mov     rax, r10
0x180004dec  xor     rdx, rax
0x180004def  mov     rcx, rdx; StackCookie
0x180004df2  jmp     __security_check_cookie
```
