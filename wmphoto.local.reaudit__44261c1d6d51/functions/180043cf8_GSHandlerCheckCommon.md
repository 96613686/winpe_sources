# __GSHandlerCheckCommon

- ea: `0x180043cf8`
- end: `0x180043d5b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043cd4`
- `0x180043d64`

## callees

- `0x180036420`
- `0x180043cf8`

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
0x180043cf8  mov     r10, rcx
0x180043cfb  mov     r11, rdx
0x180043cfe  mov     ecx, [r8]
0x180043d01  and     ecx, 0FFFFFFF8h
0x180043d04  test    byte ptr [r8], 4
0x180043d08  jz      short loc_180043D1F
0x180043d0a  mov     eax, [r8+8]
0x180043d0e  movsxd  r9, dword ptr [r8+4]
0x180043d12  neg     eax
0x180043d14  movsxd  rdx, eax
0x180043d17  add     r9, r10
0x180043d1a  and     r9, rdx
0x180043d1d  jmp     short loc_180043D22
0x180043d1f  mov     r9, r10
0x180043d22  movsxd  rax, ecx
0x180043d25  mov     rdx, [rax+r9]
0x180043d29  mov     rax, [r11+10h]
0x180043d2d  mov     ecx, [rax+8]
0x180043d30  mov     rax, [r11+8]
0x180043d34  test    byte ptr [rcx+rax+3], 0Fh
0x180043d39  jz      short loc_180043D4D
0x180043d3b  movzx   eax, byte ptr [rcx+rax+3]
0x180043d40  mov     ecx, 0FFFFFFF0h
0x180043d45  and     rax, rcx
0x180043d48  add     rax, r10
0x180043d4b  jmp     short loc_180043D50
0x180043d4d  mov     rax, r10
0x180043d50  xor     rdx, rax
0x180043d53  mov     rcx, rdx; StackCookie
0x180043d56  jmp     __security_check_cookie
```
