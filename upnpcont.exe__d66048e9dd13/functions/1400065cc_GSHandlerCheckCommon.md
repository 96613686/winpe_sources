# __GSHandlerCheckCommon

- ea: `0x1400065cc`
- end: `0x14000662f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400065a8`

## callees

- `0x140001490`
- `0x1400065cc`

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
0x1400065cc  mov     r10, rcx
0x1400065cf  mov     r11, rdx
0x1400065d2  mov     ecx, [r8]
0x1400065d5  and     ecx, 0FFFFFFF8h
0x1400065d8  test    byte ptr [r8], 4
0x1400065dc  jz      short loc_1400065F3
0x1400065de  mov     eax, [r8+8]
0x1400065e2  movsxd  r9, dword ptr [r8+4]
0x1400065e6  neg     eax
0x1400065e8  movsxd  rdx, eax
0x1400065eb  add     r9, r10
0x1400065ee  and     r9, rdx
0x1400065f1  jmp     short loc_1400065F6
0x1400065f3  mov     r9, r10
0x1400065f6  movsxd  rax, ecx
0x1400065f9  mov     rdx, [rax+r9]
0x1400065fd  mov     rax, [r11+10h]
0x140006601  mov     ecx, [rax+8]
0x140006604  mov     rax, [r11+8]
0x140006608  test    byte ptr [rcx+rax+3], 0Fh
0x14000660d  jz      short loc_140006621
0x14000660f  movzx   eax, byte ptr [rcx+rax+3]
0x140006614  mov     ecx, 0FFFFFFF0h
0x140006619  and     rax, rcx
0x14000661c  add     rax, r10
0x14000661f  jmp     short loc_140006624
0x140006621  mov     rax, r10
0x140006624  xor     rdx, rax
0x140006627  mov     rcx, rdx; StackCookie
0x14000662a  jmp     __security_check_cookie
```
