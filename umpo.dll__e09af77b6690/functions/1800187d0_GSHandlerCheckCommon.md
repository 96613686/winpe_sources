# __GSHandlerCheckCommon

- ea: `0x1800187d0`
- end: `0x180018833`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800187ac`

## callees

- `0x180010070`
- `0x1800187d0`

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
0x1800187d0  mov     r10, rcx
0x1800187d3  mov     r11, rdx
0x1800187d6  mov     ecx, [r8]
0x1800187d9  and     ecx, 0FFFFFFF8h
0x1800187dc  test    byte ptr [r8], 4
0x1800187e0  jz      short loc_1800187F7
0x1800187e2  mov     eax, [r8+8]
0x1800187e6  movsxd  r9, dword ptr [r8+4]
0x1800187ea  neg     eax
0x1800187ec  movsxd  rdx, eax
0x1800187ef  add     r9, r10
0x1800187f2  and     r9, rdx
0x1800187f5  jmp     short loc_1800187FA
0x1800187f7  mov     r9, r10
0x1800187fa  movsxd  rax, ecx
0x1800187fd  mov     rdx, [rax+r9]
0x180018801  mov     rax, [r11+10h]
0x180018805  mov     ecx, [rax+8]
0x180018808  mov     rax, [r11+8]
0x18001880c  test    byte ptr [rcx+rax+3], 0Fh
0x180018811  jz      short loc_180018825
0x180018813  movzx   eax, byte ptr [rcx+rax+3]
0x180018818  mov     ecx, 0FFFFFFF0h
0x18001881d  and     rax, rcx
0x180018820  add     rax, r10
0x180018823  jmp     short loc_180018828
0x180018825  mov     rax, r10
0x180018828  xor     rdx, rax
0x18001882b  mov     rcx, rdx; StackCookie
0x18001882e  jmp     __security_check_cookie
```
