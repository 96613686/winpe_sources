# __GSHandlerCheckCommon

- ea: `0x180002a8c`
- end: `0x180002aef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a68`
- `0x18000a538`
- `0x18000a5a0`

## callees

- `0x180002a8c`
- `0x18000a640`

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
0x180002a8c  mov     r10, rcx
0x180002a8f  mov     r11, rdx
0x180002a92  mov     ecx, [r8]
0x180002a95  and     ecx, 0FFFFFFF8h
0x180002a98  test    byte ptr [r8], 4
0x180002a9c  jz      short loc_180002AB3
0x180002a9e  mov     eax, [r8+8]
0x180002aa2  movsxd  r9, dword ptr [r8+4]
0x180002aa6  neg     eax
0x180002aa8  movsxd  rdx, eax
0x180002aab  add     r9, r10
0x180002aae  and     r9, rdx
0x180002ab1  jmp     short loc_180002AB6
0x180002ab3  mov     r9, r10
0x180002ab6  movsxd  rax, ecx
0x180002ab9  mov     rdx, [rax+r9]
0x180002abd  mov     rax, [r11+10h]
0x180002ac1  mov     ecx, [rax+8]
0x180002ac4  mov     rax, [r11+8]
0x180002ac8  test    byte ptr [rcx+rax+3], 0Fh
0x180002acd  jz      short loc_180002AE1
0x180002acf  movzx   eax, byte ptr [rcx+rax+3]
0x180002ad4  mov     ecx, 0FFFFFFF0h
0x180002ad9  and     rax, rcx
0x180002adc  add     rax, r10
0x180002adf  jmp     short loc_180002AE4
0x180002ae1  mov     rax, r10
0x180002ae4  xor     rdx, rax
0x180002ae7  mov     rcx, rdx; StackCookie
0x180002aea  jmp     __security_check_cookie
```
