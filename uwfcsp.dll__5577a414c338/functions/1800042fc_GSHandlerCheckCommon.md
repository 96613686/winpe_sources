# __GSHandlerCheckCommon

- ea: `0x1800042fc`
- end: `0x18000435f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800042d8`

## callees

- `0x1800042fc`
- `0x18001a210`

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
0x1800042fc  mov     r10, rcx
0x1800042ff  mov     r11, rdx
0x180004302  mov     ecx, [r8]
0x180004305  and     ecx, 0FFFFFFF8h
0x180004308  test    byte ptr [r8], 4
0x18000430c  jz      short loc_180004323
0x18000430e  mov     eax, [r8+8]
0x180004312  movsxd  r9, dword ptr [r8+4]
0x180004316  neg     eax
0x180004318  movsxd  rdx, eax
0x18000431b  add     r9, r10
0x18000431e  and     r9, rdx
0x180004321  jmp     short loc_180004326
0x180004323  mov     r9, r10
0x180004326  movsxd  rax, ecx
0x180004329  mov     rdx, [rax+r9]
0x18000432d  mov     rax, [r11+10h]
0x180004331  mov     ecx, [rax+8]
0x180004334  mov     rax, [r11+8]
0x180004338  test    byte ptr [rcx+rax+3], 0Fh
0x18000433d  jz      short loc_180004351
0x18000433f  movzx   eax, byte ptr [rcx+rax+3]
0x180004344  mov     ecx, 0FFFFFFF0h
0x180004349  and     rax, rcx
0x18000434c  add     rax, r10
0x18000434f  jmp     short loc_180004354
0x180004351  mov     rax, r10
0x180004354  xor     rdx, rax
0x180004357  mov     rcx, rdx; StackCookie
0x18000435a  jmp     __security_check_cookie
```
