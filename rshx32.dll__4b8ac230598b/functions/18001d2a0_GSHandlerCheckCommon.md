# __GSHandlerCheckCommon

- ea: `0x18001d2a0`
- end: `0x18001d303`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d27c`

## callees

- `0x18001d2a0`
- `0x18001d370`

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
0x18001d2a0  mov     r10, rcx
0x18001d2a3  mov     r11, rdx
0x18001d2a6  mov     ecx, [r8]
0x18001d2a9  and     ecx, 0FFFFFFF8h
0x18001d2ac  test    byte ptr [r8], 4
0x18001d2b0  jz      short loc_18001D2C7
0x18001d2b2  mov     eax, [r8+8]
0x18001d2b6  movsxd  r9, dword ptr [r8+4]
0x18001d2ba  neg     eax
0x18001d2bc  movsxd  rdx, eax
0x18001d2bf  add     r9, r10
0x18001d2c2  and     r9, rdx
0x18001d2c5  jmp     short loc_18001D2CA
0x18001d2c7  mov     r9, r10
0x18001d2ca  movsxd  rax, ecx
0x18001d2cd  mov     rdx, [rax+r9]
0x18001d2d1  mov     rax, [r11+10h]
0x18001d2d5  mov     ecx, [rax+8]
0x18001d2d8  mov     rax, [r11+8]
0x18001d2dc  test    byte ptr [rcx+rax+3], 0Fh
0x18001d2e1  jz      short loc_18001D2F5
0x18001d2e3  movzx   eax, byte ptr [rcx+rax+3]
0x18001d2e8  mov     ecx, 0FFFFFFF0h
0x18001d2ed  and     rax, rcx
0x18001d2f0  add     rax, r10
0x18001d2f3  jmp     short loc_18001D2F8
0x18001d2f5  mov     rax, r10
0x18001d2f8  xor     rdx, rax
0x18001d2fb  mov     rcx, rdx; StackCookie
0x18001d2fe  jmp     __security_check_cookie
```
