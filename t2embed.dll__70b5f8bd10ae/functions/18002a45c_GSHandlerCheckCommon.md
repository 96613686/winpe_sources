# __GSHandlerCheckCommon

- ea: `0x18002a45c`
- end: `0x18002a4bf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a438`
- `0x18002a4c8`

## callees

- `0x18002a45c`
- `0x18002a590`

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
0x18002a45c  mov     r10, rcx
0x18002a45f  mov     r11, rdx
0x18002a462  mov     ecx, [r8]
0x18002a465  and     ecx, 0FFFFFFF8h
0x18002a468  test    byte ptr [r8], 4
0x18002a46c  jz      short loc_18002A483
0x18002a46e  mov     eax, [r8+8]
0x18002a472  movsxd  r9, dword ptr [r8+4]
0x18002a476  neg     eax
0x18002a478  movsxd  rdx, eax
0x18002a47b  add     r9, r10
0x18002a47e  and     r9, rdx
0x18002a481  jmp     short loc_18002A486
0x18002a483  mov     r9, r10
0x18002a486  movsxd  rax, ecx
0x18002a489  mov     rdx, [rax+r9]
0x18002a48d  mov     rax, [r11+10h]
0x18002a491  mov     ecx, [rax+8]
0x18002a494  mov     rax, [r11+8]
0x18002a498  test    byte ptr [rcx+rax+3], 0Fh
0x18002a49d  jz      short loc_18002A4B1
0x18002a49f  movzx   eax, byte ptr [rcx+rax+3]
0x18002a4a4  mov     ecx, 0FFFFFFF0h
0x18002a4a9  and     rax, rcx
0x18002a4ac  add     rax, r10
0x18002a4af  jmp     short loc_18002A4B4
0x18002a4b1  mov     rax, r10
0x18002a4b4  xor     rdx, rax
0x18002a4b7  mov     rcx, rdx; StackCookie
0x18002a4ba  jmp     __security_check_cookie
```
