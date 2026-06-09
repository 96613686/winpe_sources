# __GSHandlerCheckCommon

- ea: `0x1800030bc`
- end: `0x18000311f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003098`

## callees

- `0x1800030bc`
- `0x180003160`

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
0x1800030bc  mov     r10, rcx
0x1800030bf  mov     r11, rdx
0x1800030c2  mov     ecx, [r8]
0x1800030c5  and     ecx, 0FFFFFFF8h
0x1800030c8  test    byte ptr [r8], 4
0x1800030cc  jz      short loc_1800030E3
0x1800030ce  mov     eax, [r8+8]
0x1800030d2  movsxd  r9, dword ptr [r8+4]
0x1800030d6  neg     eax
0x1800030d8  movsxd  rdx, eax
0x1800030db  add     r9, r10
0x1800030de  and     r9, rdx
0x1800030e1  jmp     short loc_1800030E6
0x1800030e3  mov     r9, r10
0x1800030e6  movsxd  rax, ecx
0x1800030e9  mov     rdx, [rax+r9]
0x1800030ed  mov     rax, [r11+10h]
0x1800030f1  mov     ecx, [rax+8]
0x1800030f4  mov     rax, [r11+8]
0x1800030f8  test    byte ptr [rcx+rax+3], 0Fh
0x1800030fd  jz      short loc_180003111
0x1800030ff  movzx   eax, byte ptr [rcx+rax+3]
0x180003104  mov     ecx, 0FFFFFFF0h
0x180003109  and     rax, rcx
0x18000310c  add     rax, r10
0x18000310f  jmp     short loc_180003114
0x180003111  mov     rax, r10
0x180003114  xor     rdx, rax
0x180003117  mov     rcx, rdx; StackCookie
0x18000311a  jmp     __security_check_cookie
```
