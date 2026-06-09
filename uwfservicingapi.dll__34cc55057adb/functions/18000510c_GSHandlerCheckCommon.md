# __GSHandlerCheckCommon

- ea: `0x18000510c`
- end: `0x18000516f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800050e8`

## callees

- `0x18000510c`
- `0x1800051a0`

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
0x18000510c  mov     r10, rcx
0x18000510f  mov     r11, rdx
0x180005112  mov     ecx, [r8]
0x180005115  and     ecx, 0FFFFFFF8h
0x180005118  test    byte ptr [r8], 4
0x18000511c  jz      short loc_180005133
0x18000511e  mov     eax, [r8+8]
0x180005122  movsxd  r9, dword ptr [r8+4]
0x180005126  neg     eax
0x180005128  movsxd  rdx, eax
0x18000512b  add     r9, r10
0x18000512e  and     r9, rdx
0x180005131  jmp     short loc_180005136
0x180005133  mov     r9, r10
0x180005136  movsxd  rax, ecx
0x180005139  mov     rdx, [rax+r9]
0x18000513d  mov     rax, [r11+10h]
0x180005141  mov     ecx, [rax+8]
0x180005144  mov     rax, [r11+8]
0x180005148  test    byte ptr [rcx+rax+3], 0Fh
0x18000514d  jz      short loc_180005161
0x18000514f  movzx   eax, byte ptr [rcx+rax+3]
0x180005154  mov     ecx, 0FFFFFFF0h
0x180005159  and     rax, rcx
0x18000515c  add     rax, r10
0x18000515f  jmp     short loc_180005164
0x180005161  mov     rax, r10
0x180005164  xor     rdx, rax
0x180005167  mov     rcx, rdx; StackCookie
0x18000516a  jmp     __security_check_cookie
```
