# __GSHandlerCheckCommon

- ea: `0x1400018e8`
- end: `0x14000194b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400018c4`

## callees

- `0x1400018e8`
- `0x140001990`

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
0x1400018e8  mov     r10, rcx
0x1400018eb  mov     r11, rdx
0x1400018ee  mov     ecx, [r8]
0x1400018f1  and     ecx, 0FFFFFFF8h
0x1400018f4  test    byte ptr [r8], 4
0x1400018f8  jz      short loc_14000190F
0x1400018fa  mov     eax, [r8+8]
0x1400018fe  movsxd  r9, dword ptr [r8+4]
0x140001902  neg     eax
0x140001904  movsxd  rdx, eax
0x140001907  add     r9, r10
0x14000190a  and     r9, rdx
0x14000190d  jmp     short loc_140001912
0x14000190f  mov     r9, r10
0x140001912  movsxd  rax, ecx
0x140001915  mov     rdx, [rax+r9]
0x140001919  mov     rax, [r11+10h]
0x14000191d  mov     ecx, [rax+8]
0x140001920  mov     rax, [r11+8]
0x140001924  test    byte ptr [rcx+rax+3], 0Fh
0x140001929  jz      short loc_14000193D
0x14000192b  movzx   eax, byte ptr [rcx+rax+3]
0x140001930  mov     ecx, 0FFFFFFF0h
0x140001935  and     rax, rcx
0x140001938  add     rax, r10
0x14000193b  jmp     short loc_140001940
0x14000193d  mov     rax, r10
0x140001940  xor     rdx, rax
0x140001943  mov     rcx, rdx; StackCookie
0x140001946  jmp     __security_check_cookie
```
