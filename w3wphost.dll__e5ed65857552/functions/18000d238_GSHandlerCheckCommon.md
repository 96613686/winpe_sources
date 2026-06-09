# __GSHandlerCheckCommon

- ea: `0x18000d238`
- end: `0x18000d29b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d214`

## callees

- `0x18000d238`
- `0x18000d2f0`

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
0x18000d238  mov     r10, rcx
0x18000d23b  mov     r11, rdx
0x18000d23e  mov     ecx, [r8]
0x18000d241  and     ecx, 0FFFFFFF8h
0x18000d244  test    byte ptr [r8], 4
0x18000d248  jz      short loc_18000D25F
0x18000d24a  mov     eax, [r8+8]
0x18000d24e  movsxd  r9, dword ptr [r8+4]
0x18000d252  neg     eax
0x18000d254  movsxd  rdx, eax
0x18000d257  add     r9, r10
0x18000d25a  and     r9, rdx
0x18000d25d  jmp     short loc_18000D262
0x18000d25f  mov     r9, r10
0x18000d262  movsxd  rax, ecx
0x18000d265  mov     rdx, [rax+r9]
0x18000d269  mov     rax, [r11+10h]
0x18000d26d  mov     ecx, [rax+8]
0x18000d270  mov     rax, [r11+8]
0x18000d274  test    byte ptr [rcx+rax+3], 0Fh
0x18000d279  jz      short loc_18000D28D
0x18000d27b  movzx   eax, byte ptr [rcx+rax+3]
0x18000d280  mov     ecx, 0FFFFFFF0h
0x18000d285  and     rax, rcx
0x18000d288  add     rax, r10
0x18000d28b  jmp     short loc_18000D290
0x18000d28d  mov     rax, r10
0x18000d290  xor     rdx, rax
0x18000d293  mov     rcx, rdx; StackCookie
0x18000d296  jmp     __security_check_cookie
```
