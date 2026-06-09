# __GSHandlerCheckCommon

- ea: `0x18001a790`
- end: `0x18001a7f3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a76c`
- `0x18001a82c`

## callees

- `0x18000c990`
- `0x18001a790`

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
0x18001a790  mov     r10, rcx
0x18001a793  mov     r11, rdx
0x18001a796  mov     ecx, [r8]
0x18001a799  and     ecx, 0FFFFFFF8h
0x18001a79c  test    byte ptr [r8], 4
0x18001a7a0  jz      short loc_18001A7B7
0x18001a7a2  mov     eax, [r8+8]
0x18001a7a6  movsxd  r9, dword ptr [r8+4]
0x18001a7aa  neg     eax
0x18001a7ac  movsxd  rdx, eax
0x18001a7af  add     r9, r10
0x18001a7b2  and     r9, rdx
0x18001a7b5  jmp     short loc_18001A7BA
0x18001a7b7  mov     r9, r10
0x18001a7ba  movsxd  rax, ecx
0x18001a7bd  mov     rdx, [rax+r9]
0x18001a7c1  mov     rax, [r11+10h]
0x18001a7c5  mov     ecx, [rax+8]
0x18001a7c8  mov     rax, [r11+8]
0x18001a7cc  test    byte ptr [rcx+rax+3], 0Fh
0x18001a7d1  jz      short loc_18001A7E5
0x18001a7d3  movzx   eax, byte ptr [rcx+rax+3]
0x18001a7d8  mov     ecx, 0FFFFFFF0h
0x18001a7dd  and     rax, rcx
0x18001a7e0  add     rax, r10
0x18001a7e3  jmp     short loc_18001A7E8
0x18001a7e5  mov     rax, r10
0x18001a7e8  xor     rdx, rax
0x18001a7eb  mov     rcx, rdx; StackCookie
0x18001a7ee  jmp     __security_check_cookie
```
