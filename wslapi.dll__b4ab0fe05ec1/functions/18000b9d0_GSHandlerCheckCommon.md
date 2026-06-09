# __GSHandlerCheckCommon

- ea: `0x18000b9d0`
- end: `0x18000ba33`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b9ac`
- `0x18000ba3c`

## callees

- `0x180001dc0`
- `0x18000b9d0`

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
0x18000b9d0  mov     r10, rcx
0x18000b9d3  mov     r11, rdx
0x18000b9d6  mov     ecx, [r8]
0x18000b9d9  and     ecx, 0FFFFFFF8h
0x18000b9dc  test    byte ptr [r8], 4
0x18000b9e0  jz      short loc_18000B9F7
0x18000b9e2  mov     eax, [r8+8]
0x18000b9e6  movsxd  r9, dword ptr [r8+4]
0x18000b9ea  neg     eax
0x18000b9ec  movsxd  rdx, eax
0x18000b9ef  add     r9, r10
0x18000b9f2  and     r9, rdx
0x18000b9f5  jmp     short loc_18000B9FA
0x18000b9f7  mov     r9, r10
0x18000b9fa  movsxd  rax, ecx
0x18000b9fd  mov     rdx, [rax+r9]
0x18000ba01  mov     rax, [r11+10h]
0x18000ba05  mov     ecx, [rax+8]
0x18000ba08  mov     rax, [r11+8]
0x18000ba0c  test    byte ptr [rcx+rax+3], 0Fh
0x18000ba11  jz      short loc_18000BA25
0x18000ba13  movzx   eax, byte ptr [rcx+rax+3]
0x18000ba18  mov     ecx, 0FFFFFFF0h
0x18000ba1d  and     rax, rcx
0x18000ba20  add     rax, r10
0x18000ba23  jmp     short loc_18000BA28
0x18000ba25  mov     rax, r10
0x18000ba28  xor     rdx, rax
0x18000ba2b  mov     rcx, rdx; StackCookie
0x18000ba2e  jmp     __security_check_cookie
```
