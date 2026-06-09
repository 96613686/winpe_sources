# __GSHandlerCheckCommon

- ea: `0x18000a6f4`
- end: `0x18000a757`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a6d0`

## callees

- `0x18000a6f4`
- `0x18000a7a0`

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
0x18000a6f4  mov     r10, rcx
0x18000a6f7  mov     r11, rdx
0x18000a6fa  mov     ecx, [r8]
0x18000a6fd  and     ecx, 0FFFFFFF8h
0x18000a700  test    byte ptr [r8], 4
0x18000a704  jz      short loc_18000A71B
0x18000a706  mov     eax, [r8+8]
0x18000a70a  movsxd  r9, dword ptr [r8+4]
0x18000a70e  neg     eax
0x18000a710  movsxd  rdx, eax
0x18000a713  add     r9, r10
0x18000a716  and     r9, rdx
0x18000a719  jmp     short loc_18000A71E
0x18000a71b  mov     r9, r10
0x18000a71e  movsxd  rax, ecx
0x18000a721  mov     rdx, [rax+r9]
0x18000a725  mov     rax, [r11+10h]
0x18000a729  mov     ecx, [rax+8]
0x18000a72c  mov     rax, [r11+8]
0x18000a730  test    byte ptr [rcx+rax+3], 0Fh
0x18000a735  jz      short loc_18000A749
0x18000a737  movzx   eax, byte ptr [rcx+rax+3]
0x18000a73c  mov     ecx, 0FFFFFFF0h
0x18000a741  and     rax, rcx
0x18000a744  add     rax, r10
0x18000a747  jmp     short loc_18000A74C
0x18000a749  mov     rax, r10
0x18000a74c  xor     rdx, rax
0x18000a74f  mov     rcx, rdx; StackCookie
0x18000a752  jmp     __security_check_cookie
```
