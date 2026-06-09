# __GSHandlerCheckCommon

- ea: `0x1800076d0`
- end: `0x180007733`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800076ac`
- `0x18000773c`

## callees

- `0x180004c80`
- `0x1800076d0`

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
0x1800076d0  mov     r10, rcx
0x1800076d3  mov     r11, rdx
0x1800076d6  mov     ecx, [r8]
0x1800076d9  and     ecx, 0FFFFFFF8h
0x1800076dc  test    byte ptr [r8], 4
0x1800076e0  jz      short loc_1800076F7
0x1800076e2  mov     eax, [r8+8]
0x1800076e6  movsxd  r9, dword ptr [r8+4]
0x1800076ea  neg     eax
0x1800076ec  movsxd  rdx, eax
0x1800076ef  add     r9, r10
0x1800076f2  and     r9, rdx
0x1800076f5  jmp     short loc_1800076FA
0x1800076f7  mov     r9, r10
0x1800076fa  movsxd  rax, ecx
0x1800076fd  mov     rdx, [rax+r9]
0x180007701  mov     rax, [r11+10h]
0x180007705  mov     ecx, [rax+8]
0x180007708  mov     rax, [r11+8]
0x18000770c  test    byte ptr [rcx+rax+3], 0Fh
0x180007711  jz      short loc_180007725
0x180007713  movzx   eax, byte ptr [rcx+rax+3]
0x180007718  mov     ecx, 0FFFFFFF0h
0x18000771d  and     rax, rcx
0x180007720  add     rax, r10
0x180007723  jmp     short loc_180007728
0x180007725  mov     rax, r10
0x180007728  xor     rdx, rax
0x18000772b  mov     rcx, rdx; StackCookie
0x18000772e  jmp     __security_check_cookie
```
