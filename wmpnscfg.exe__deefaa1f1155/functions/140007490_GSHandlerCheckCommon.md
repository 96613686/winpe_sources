# __GSHandlerCheckCommon

- ea: `0x140007490`
- end: `0x1400074f3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000746c`
- `0x1400074fc`

## callees

- `0x1400014f0`
- `0x140007490`

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
0x140007490  mov     r10, rcx
0x140007493  mov     r11, rdx
0x140007496  mov     ecx, [r8]
0x140007499  and     ecx, 0FFFFFFF8h
0x14000749c  test    byte ptr [r8], 4
0x1400074a0  jz      short loc_1400074B7
0x1400074a2  mov     eax, [r8+8]
0x1400074a6  movsxd  r9, dword ptr [r8+4]
0x1400074aa  neg     eax
0x1400074ac  movsxd  rdx, eax
0x1400074af  add     r9, r10
0x1400074b2  and     r9, rdx
0x1400074b5  jmp     short loc_1400074BA
0x1400074b7  mov     r9, r10
0x1400074ba  movsxd  rax, ecx
0x1400074bd  mov     rdx, [rax+r9]
0x1400074c1  mov     rax, [r11+10h]
0x1400074c5  mov     ecx, [rax+8]
0x1400074c8  mov     rax, [r11+8]
0x1400074cc  test    byte ptr [rcx+rax+3], 0Fh
0x1400074d1  jz      short loc_1400074E5
0x1400074d3  movzx   eax, byte ptr [rcx+rax+3]
0x1400074d8  mov     ecx, 0FFFFFFF0h
0x1400074dd  and     rax, rcx
0x1400074e0  add     rax, r10
0x1400074e3  jmp     short loc_1400074E8
0x1400074e5  mov     rax, r10
0x1400074e8  xor     rdx, rax
0x1400074eb  mov     rcx, rdx; StackCookie
0x1400074ee  jmp     __security_check_cookie
```
