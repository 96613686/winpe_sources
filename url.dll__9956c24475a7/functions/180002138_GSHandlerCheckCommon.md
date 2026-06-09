# __GSHandlerCheckCommon

- ea: `0x180002138`
- end: `0x18000219b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002114`

## callees

- `0x180002138`
- `0x1800021e0`

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
0x180002138  mov     r10, rcx
0x18000213b  mov     r11, rdx
0x18000213e  mov     ecx, [r8]
0x180002141  and     ecx, 0FFFFFFF8h
0x180002144  test    byte ptr [r8], 4
0x180002148  jz      short loc_18000215F
0x18000214a  mov     eax, [r8+8]
0x18000214e  movsxd  r9, dword ptr [r8+4]
0x180002152  neg     eax
0x180002154  movsxd  rdx, eax
0x180002157  add     r9, r10
0x18000215a  and     r9, rdx
0x18000215d  jmp     short loc_180002162
0x18000215f  mov     r9, r10
0x180002162  movsxd  rax, ecx
0x180002165  mov     rdx, [rax+r9]
0x180002169  mov     rax, [r11+10h]
0x18000216d  mov     ecx, [rax+8]
0x180002170  mov     rax, [r11+8]
0x180002174  test    byte ptr [rcx+rax+3], 0Fh
0x180002179  jz      short loc_18000218D
0x18000217b  movzx   eax, byte ptr [rcx+rax+3]
0x180002180  mov     ecx, 0FFFFFFF0h
0x180002185  and     rax, rcx
0x180002188  add     rax, r10
0x18000218b  jmp     short loc_180002190
0x18000218d  mov     rax, r10
0x180002190  xor     rdx, rax
0x180002193  mov     rcx, rdx; StackCookie
0x180002196  jmp     __security_check_cookie
```
