# __GSHandlerCheckCommon

- ea: `0x18000cec0`
- end: `0x18000cf23`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ce9c`
- `0x18000cf2c`

## callees

- `0x18000cec0`
- `0x18000cff0`

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
0x18000cec0  mov     r10, rcx
0x18000cec3  mov     r11, rdx
0x18000cec6  mov     ecx, [r8]
0x18000cec9  and     ecx, 0FFFFFFF8h
0x18000cecc  test    byte ptr [r8], 4
0x18000ced0  jz      short loc_18000CEE7
0x18000ced2  mov     eax, [r8+8]
0x18000ced6  movsxd  r9, dword ptr [r8+4]
0x18000ceda  neg     eax
0x18000cedc  movsxd  rdx, eax
0x18000cedf  add     r9, r10
0x18000cee2  and     r9, rdx
0x18000cee5  jmp     short loc_18000CEEA
0x18000cee7  mov     r9, r10
0x18000ceea  movsxd  rax, ecx
0x18000ceed  mov     rdx, [rax+r9]
0x18000cef1  mov     rax, [r11+10h]
0x18000cef5  mov     ecx, [rax+8]
0x18000cef8  mov     rax, [r11+8]
0x18000cefc  test    byte ptr [rcx+rax+3], 0Fh
0x18000cf01  jz      short loc_18000CF15
0x18000cf03  movzx   eax, byte ptr [rcx+rax+3]
0x18000cf08  mov     ecx, 0FFFFFFF0h
0x18000cf0d  and     rax, rcx
0x18000cf10  add     rax, r10
0x18000cf13  jmp     short loc_18000CF18
0x18000cf15  mov     rax, r10
0x18000cf18  xor     rdx, rax
0x18000cf1b  mov     rcx, rdx; StackCookie
0x18000cf1e  jmp     __security_check_cookie
```
