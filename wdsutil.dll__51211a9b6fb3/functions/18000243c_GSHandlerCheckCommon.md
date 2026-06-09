# __GSHandlerCheckCommon

- ea: `0x18000243c`
- end: `0x18000249f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002418`
- `0x180031920`

## callees

- `0x18000243c`
- `0x1800319f0`

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
0x18000243c  mov     r10, rcx
0x18000243f  mov     r11, rdx
0x180002442  mov     ecx, [r8]
0x180002445  and     ecx, 0FFFFFFF8h
0x180002448  test    byte ptr [r8], 4
0x18000244c  jz      short loc_180002463
0x18000244e  mov     eax, [r8+8]
0x180002452  movsxd  r9, dword ptr [r8+4]
0x180002456  neg     eax
0x180002458  movsxd  rdx, eax
0x18000245b  add     r9, r10
0x18000245e  and     r9, rdx
0x180002461  jmp     short loc_180002466
0x180002463  mov     r9, r10
0x180002466  movsxd  rax, ecx
0x180002469  mov     rdx, [rax+r9]
0x18000246d  mov     rax, [r11+10h]
0x180002471  mov     ecx, [rax+8]
0x180002474  mov     rax, [r11+8]
0x180002478  test    byte ptr [rcx+rax+3], 0Fh
0x18000247d  jz      short loc_180002491
0x18000247f  movzx   eax, byte ptr [rcx+rax+3]
0x180002484  mov     ecx, 0FFFFFFF0h
0x180002489  and     rax, rcx
0x18000248c  add     rax, r10
0x18000248f  jmp     short loc_180002494
0x180002491  mov     rax, r10
0x180002494  xor     rdx, rax
0x180002497  mov     rcx, rdx; StackCookie
0x18000249a  jmp     __security_check_cookie
```
