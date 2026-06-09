# __GSHandlerCheckCommon

- ea: `0x180002870`
- end: `0x1800028d3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000284c`
- `0x18002a1fc`

## callees

- `0x1800014e0`
- `0x180002870`

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
0x180002870  mov     r10, rcx
0x180002873  mov     r11, rdx
0x180002876  mov     ecx, [r8]
0x180002879  and     ecx, 0FFFFFFF8h
0x18000287c  test    byte ptr [r8], 4
0x180002880  jz      short loc_180002897
0x180002882  mov     eax, [r8+8]
0x180002886  movsxd  r9, dword ptr [r8+4]
0x18000288a  neg     eax
0x18000288c  movsxd  rdx, eax
0x18000288f  add     r9, r10
0x180002892  and     r9, rdx
0x180002895  jmp     short loc_18000289A
0x180002897  mov     r9, r10
0x18000289a  movsxd  rax, ecx
0x18000289d  mov     rdx, [rax+r9]
0x1800028a1  mov     rax, [r11+10h]
0x1800028a5  mov     ecx, [rax+8]
0x1800028a8  mov     rax, [r11+8]
0x1800028ac  test    byte ptr [rcx+rax+3], 0Fh
0x1800028b1  jz      short loc_1800028C5
0x1800028b3  movzx   eax, byte ptr [rcx+rax+3]
0x1800028b8  mov     ecx, 0FFFFFFF0h
0x1800028bd  and     rax, rcx
0x1800028c0  add     rax, r10
0x1800028c3  jmp     short loc_1800028C8
0x1800028c5  mov     rax, r10
0x1800028c8  xor     rdx, rax
0x1800028cb  mov     rcx, rdx; StackCookie
0x1800028ce  jmp     __security_check_cookie
```
