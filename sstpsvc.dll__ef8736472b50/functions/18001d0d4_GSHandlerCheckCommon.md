# __GSHandlerCheckCommon

- ea: `0x18001d0d4`
- end: `0x18001d137`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d0b0`
- `0x18001d140`

## callees

- `0x18001d0d4`
- `0x18001d210`

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
0x18001d0d4  mov     r10, rcx
0x18001d0d7  mov     r11, rdx
0x18001d0da  mov     ecx, [r8]
0x18001d0dd  and     ecx, 0FFFFFFF8h
0x18001d0e0  test    byte ptr [r8], 4
0x18001d0e4  jz      short loc_18001D0FB
0x18001d0e6  mov     eax, [r8+8]
0x18001d0ea  movsxd  r9, dword ptr [r8+4]
0x18001d0ee  neg     eax
0x18001d0f0  movsxd  rdx, eax
0x18001d0f3  add     r9, r10
0x18001d0f6  and     r9, rdx
0x18001d0f9  jmp     short loc_18001D0FE
0x18001d0fb  mov     r9, r10
0x18001d0fe  movsxd  rax, ecx
0x18001d101  mov     rdx, [rax+r9]
0x18001d105  mov     rax, [r11+10h]
0x18001d109  mov     ecx, [rax+8]
0x18001d10c  mov     rax, [r11+8]
0x18001d110  test    byte ptr [rcx+rax+3], 0Fh
0x18001d115  jz      short loc_18001D129
0x18001d117  movzx   eax, byte ptr [rcx+rax+3]
0x18001d11c  mov     ecx, 0FFFFFFF0h
0x18001d121  and     rax, rcx
0x18001d124  add     rax, r10
0x18001d127  jmp     short loc_18001D12C
0x18001d129  mov     rax, r10
0x18001d12c  xor     rdx, rax
0x18001d12f  mov     rcx, rdx; StackCookie
0x18001d132  jmp     __security_check_cookie
```
