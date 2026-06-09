# __GSHandlerCheckCommon

- ea: `0x18000d65c`
- end: `0x18000d6bf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d638`
- `0x18000d6c8`

## callees

- `0x180001770`
- `0x18000d65c`

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
0x18000d65c  mov     r10, rcx
0x18000d65f  mov     r11, rdx
0x18000d662  mov     ecx, [r8]
0x18000d665  and     ecx, 0FFFFFFF8h
0x18000d668  test    byte ptr [r8], 4
0x18000d66c  jz      short loc_18000D683
0x18000d66e  mov     eax, [r8+8]
0x18000d672  movsxd  r9, dword ptr [r8+4]
0x18000d676  neg     eax
0x18000d678  movsxd  rdx, eax
0x18000d67b  add     r9, r10
0x18000d67e  and     r9, rdx
0x18000d681  jmp     short loc_18000D686
0x18000d683  mov     r9, r10
0x18000d686  movsxd  rax, ecx
0x18000d689  mov     rdx, [rax+r9]
0x18000d68d  mov     rax, [r11+10h]
0x18000d691  mov     ecx, [rax+8]
0x18000d694  mov     rax, [r11+8]
0x18000d698  test    byte ptr [rcx+rax+3], 0Fh
0x18000d69d  jz      short loc_18000D6B1
0x18000d69f  movzx   eax, byte ptr [rcx+rax+3]
0x18000d6a4  mov     ecx, 0FFFFFFF0h
0x18000d6a9  and     rax, rcx
0x18000d6ac  add     rax, r10
0x18000d6af  jmp     short loc_18000D6B4
0x18000d6b1  mov     rax, r10
0x18000d6b4  xor     rdx, rax
0x18000d6b7  mov     rcx, rdx; StackCookie
0x18000d6ba  jmp     __security_check_cookie
```
