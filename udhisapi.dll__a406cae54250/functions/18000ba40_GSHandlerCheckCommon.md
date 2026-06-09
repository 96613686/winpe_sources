# __GSHandlerCheckCommon

- ea: `0x18000ba40`
- end: `0x18000baa3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ba1c`

## callees

- `0x180001400`
- `0x18000ba40`

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
0x18000ba40  mov     r10, rcx
0x18000ba43  mov     r11, rdx
0x18000ba46  mov     ecx, [r8]
0x18000ba49  and     ecx, 0FFFFFFF8h
0x18000ba4c  test    byte ptr [r8], 4
0x18000ba50  jz      short loc_18000BA67
0x18000ba52  mov     eax, [r8+8]
0x18000ba56  movsxd  r9, dword ptr [r8+4]
0x18000ba5a  neg     eax
0x18000ba5c  movsxd  rdx, eax
0x18000ba5f  add     r9, r10
0x18000ba62  and     r9, rdx
0x18000ba65  jmp     short loc_18000BA6A
0x18000ba67  mov     r9, r10
0x18000ba6a  movsxd  rax, ecx
0x18000ba6d  mov     rdx, [rax+r9]
0x18000ba71  mov     rax, [r11+10h]
0x18000ba75  mov     ecx, [rax+8]
0x18000ba78  mov     rax, [r11+8]
0x18000ba7c  test    byte ptr [rcx+rax+3], 0Fh
0x18000ba81  jz      short loc_18000BA95
0x18000ba83  movzx   eax, byte ptr [rcx+rax+3]
0x18000ba88  mov     ecx, 0FFFFFFF0h
0x18000ba8d  and     rax, rcx
0x18000ba90  add     rax, r10
0x18000ba93  jmp     short loc_18000BA98
0x18000ba95  mov     rax, r10
0x18000ba98  xor     rdx, rax
0x18000ba9b  mov     rcx, rdx; StackCookie
0x18000ba9e  jmp     __security_check_cookie
```
