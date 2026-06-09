# __GSHandlerCheckCommon

- ea: `0x1800028ac`
- end: `0x18000290f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002888`
- `0x180012760`

## callees

- `0x1800028ac`
- `0x180012800`

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
0x1800028ac  mov     r10, rcx
0x1800028af  mov     r11, rdx
0x1800028b2  mov     ecx, [r8]
0x1800028b5  and     ecx, 0FFFFFFF8h
0x1800028b8  test    byte ptr [r8], 4
0x1800028bc  jz      short loc_1800028D3
0x1800028be  mov     eax, [r8+8]
0x1800028c2  movsxd  r9, dword ptr [r8+4]
0x1800028c6  neg     eax
0x1800028c8  movsxd  rdx, eax
0x1800028cb  add     r9, r10
0x1800028ce  and     r9, rdx
0x1800028d1  jmp     short loc_1800028D6
0x1800028d3  mov     r9, r10
0x1800028d6  movsxd  rax, ecx
0x1800028d9  mov     rdx, [rax+r9]
0x1800028dd  mov     rax, [r11+10h]
0x1800028e1  mov     ecx, [rax+8]
0x1800028e4  mov     rax, [r11+8]
0x1800028e8  test    byte ptr [rcx+rax+3], 0Fh
0x1800028ed  jz      short loc_180002901
0x1800028ef  movzx   eax, byte ptr [rcx+rax+3]
0x1800028f4  mov     ecx, 0FFFFFFF0h
0x1800028f9  and     rax, rcx
0x1800028fc  add     rax, r10
0x1800028ff  jmp     short loc_180002904
0x180002901  mov     rax, r10
0x180002904  xor     rdx, rax
0x180002907  mov     rcx, rdx; StackCookie
0x18000290a  jmp     __security_check_cookie
```
