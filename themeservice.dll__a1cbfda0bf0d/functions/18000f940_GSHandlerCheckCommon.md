# __GSHandlerCheckCommon

- ea: `0x18000f940`
- end: `0x18000f9a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f91c`

## callees

- `0x18000f940`
- `0x18000fa00`

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
0x18000f940  mov     r10, rcx
0x18000f943  mov     r11, rdx
0x18000f946  mov     ecx, [r8]
0x18000f949  and     ecx, 0FFFFFFF8h
0x18000f94c  test    byte ptr [r8], 4
0x18000f950  jz      short loc_18000F967
0x18000f952  mov     eax, [r8+8]
0x18000f956  movsxd  r9, dword ptr [r8+4]
0x18000f95a  neg     eax
0x18000f95c  movsxd  rdx, eax
0x18000f95f  add     r9, r10
0x18000f962  and     r9, rdx
0x18000f965  jmp     short loc_18000F96A
0x18000f967  mov     r9, r10
0x18000f96a  movsxd  rax, ecx
0x18000f96d  mov     rdx, [rax+r9]
0x18000f971  mov     rax, [r11+10h]
0x18000f975  mov     ecx, [rax+8]
0x18000f978  mov     rax, [r11+8]
0x18000f97c  test    byte ptr [rcx+rax+3], 0Fh
0x18000f981  jz      short loc_18000F995
0x18000f983  movzx   eax, byte ptr [rcx+rax+3]
0x18000f988  mov     ecx, 0FFFFFFF0h
0x18000f98d  and     rax, rcx
0x18000f990  add     rax, r10
0x18000f993  jmp     short loc_18000F998
0x18000f995  mov     rax, r10
0x18000f998  xor     rdx, rax
0x18000f99b  mov     rcx, rdx; StackCookie
0x18000f99e  jmp     __security_check_cookie
```
