# __GSHandlerCheckCommon

- ea: `0x1800028b0`
- end: `0x180002913`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000288c`

## callees

- `0x1800028b0`
- `0x180002950`

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
0x1800028b0  mov     r10, rcx
0x1800028b3  mov     r11, rdx
0x1800028b6  mov     ecx, [r8]
0x1800028b9  and     ecx, 0FFFFFFF8h
0x1800028bc  test    byte ptr [r8], 4
0x1800028c0  jz      short loc_1800028D7
0x1800028c2  mov     eax, [r8+8]
0x1800028c6  movsxd  r9, dword ptr [r8+4]
0x1800028ca  neg     eax
0x1800028cc  movsxd  rdx, eax
0x1800028cf  add     r9, r10
0x1800028d2  and     r9, rdx
0x1800028d5  jmp     short loc_1800028DA
0x1800028d7  mov     r9, r10
0x1800028da  movsxd  rax, ecx
0x1800028dd  mov     rdx, [rax+r9]
0x1800028e1  mov     rax, [r11+10h]
0x1800028e5  mov     ecx, [rax+8]
0x1800028e8  mov     rax, [r11+8]
0x1800028ec  test    byte ptr [rcx+rax+3], 0Fh
0x1800028f1  jz      short loc_180002905
0x1800028f3  movzx   eax, byte ptr [rcx+rax+3]
0x1800028f8  mov     ecx, 0FFFFFFF0h
0x1800028fd  and     rax, rcx
0x180002900  add     rax, r10
0x180002903  jmp     short loc_180002908
0x180002905  mov     rax, r10
0x180002908  xor     rdx, rax
0x18000290b  mov     rcx, rdx; StackCookie
0x18000290e  jmp     __security_check_cookie
```
