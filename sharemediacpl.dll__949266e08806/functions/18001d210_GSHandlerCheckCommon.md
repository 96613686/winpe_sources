# __GSHandlerCheckCommon

- ea: `0x18001d210`
- end: `0x18001d273`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d1ec`

## callees

- `0x180001d60`
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
0x18001d210  mov     r10, rcx
0x18001d213  mov     r11, rdx
0x18001d216  mov     ecx, [r8]
0x18001d219  and     ecx, 0FFFFFFF8h
0x18001d21c  test    byte ptr [r8], 4
0x18001d220  jz      short loc_18001D237
0x18001d222  mov     eax, [r8+8]
0x18001d226  movsxd  r9, dword ptr [r8+4]
0x18001d22a  neg     eax
0x18001d22c  movsxd  rdx, eax
0x18001d22f  add     r9, r10
0x18001d232  and     r9, rdx
0x18001d235  jmp     short loc_18001D23A
0x18001d237  mov     r9, r10
0x18001d23a  movsxd  rax, ecx
0x18001d23d  mov     rdx, [rax+r9]
0x18001d241  mov     rax, [r11+10h]
0x18001d245  mov     ecx, [rax+8]
0x18001d248  mov     rax, [r11+8]
0x18001d24c  test    byte ptr [rcx+rax+3], 0Fh
0x18001d251  jz      short loc_18001D265
0x18001d253  movzx   eax, byte ptr [rcx+rax+3]
0x18001d258  mov     ecx, 0FFFFFFF0h
0x18001d25d  and     rax, rcx
0x18001d260  add     rax, r10
0x18001d263  jmp     short loc_18001D268
0x18001d265  mov     rax, r10
0x18001d268  xor     rdx, rax
0x18001d26b  mov     rcx, rdx; StackCookie
0x18001d26e  jmp     __security_check_cookie
```
