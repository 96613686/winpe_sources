# __GSHandlerCheckCommon

- ea: `0x180002840`
- end: `0x1800028a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000281c`
- `0x180029d4c`

## callees

- `0x1800014e0`
- `0x180002840`

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
0x180002840  mov     r10, rcx
0x180002843  mov     r11, rdx
0x180002846  mov     ecx, [r8]
0x180002849  and     ecx, 0FFFFFFF8h
0x18000284c  test    byte ptr [r8], 4
0x180002850  jz      short loc_180002867
0x180002852  mov     eax, [r8+8]
0x180002856  movsxd  r9, dword ptr [r8+4]
0x18000285a  neg     eax
0x18000285c  movsxd  rdx, eax
0x18000285f  add     r9, r10
0x180002862  and     r9, rdx
0x180002865  jmp     short loc_18000286A
0x180002867  mov     r9, r10
0x18000286a  movsxd  rax, ecx
0x18000286d  mov     rdx, [rax+r9]
0x180002871  mov     rax, [r11+10h]
0x180002875  mov     ecx, [rax+8]
0x180002878  mov     rax, [r11+8]
0x18000287c  test    byte ptr [rcx+rax+3], 0Fh
0x180002881  jz      short loc_180002895
0x180002883  movzx   eax, byte ptr [rcx+rax+3]
0x180002888  mov     ecx, 0FFFFFFF0h
0x18000288d  and     rax, rcx
0x180002890  add     rax, r10
0x180002893  jmp     short loc_180002898
0x180002895  mov     rax, r10
0x180002898  xor     rdx, rax
0x18000289b  mov     rcx, rdx; StackCookie
0x18000289e  jmp     __security_check_cookie
```
