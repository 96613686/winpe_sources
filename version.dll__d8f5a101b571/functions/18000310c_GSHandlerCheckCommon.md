# __GSHandlerCheckCommon

- ea: `0x18000310c`
- end: `0x18000316f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800030e8`

## callees

- `0x18000310c`
- `0x1800031b0`

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
0x18000310c  mov     r10, rcx
0x18000310f  mov     r11, rdx
0x180003112  mov     ecx, [r8]
0x180003115  and     ecx, 0FFFFFFF8h
0x180003118  test    byte ptr [r8], 4
0x18000311c  jz      short loc_180003133
0x18000311e  mov     eax, [r8+8]
0x180003122  movsxd  r9, dword ptr [r8+4]
0x180003126  neg     eax
0x180003128  movsxd  rdx, eax
0x18000312b  add     r9, r10
0x18000312e  and     r9, rdx
0x180003131  jmp     short loc_180003136
0x180003133  mov     r9, r10
0x180003136  movsxd  rax, ecx
0x180003139  mov     rdx, [rax+r9]
0x18000313d  mov     rax, [r11+10h]
0x180003141  mov     ecx, [rax+8]
0x180003144  mov     rax, [r11+8]
0x180003148  test    byte ptr [rcx+rax+3], 0Fh
0x18000314d  jz      short loc_180003161
0x18000314f  movzx   eax, byte ptr [rcx+rax+3]
0x180003154  mov     ecx, 0FFFFFFF0h
0x180003159  and     rax, rcx
0x18000315c  add     rax, r10
0x18000315f  jmp     short loc_180003164
0x180003161  mov     rax, r10
0x180003164  xor     rdx, rax
0x180003167  mov     rcx, rdx; StackCookie
0x18000316a  jmp     __security_check_cookie
```
