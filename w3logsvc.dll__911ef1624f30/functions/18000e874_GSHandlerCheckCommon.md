# __GSHandlerCheckCommon

- ea: `0x18000e874`
- end: `0x18000e8d7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e850`
- `0x18000e8e0`

## callees

- `0x18000e874`
- `0x18000e9a0`

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
0x18000e874  mov     r10, rcx
0x18000e877  mov     r11, rdx
0x18000e87a  mov     ecx, [r8]
0x18000e87d  and     ecx, 0FFFFFFF8h
0x18000e880  test    byte ptr [r8], 4
0x18000e884  jz      short loc_18000E89B
0x18000e886  mov     eax, [r8+8]
0x18000e88a  movsxd  r9, dword ptr [r8+4]
0x18000e88e  neg     eax
0x18000e890  movsxd  rdx, eax
0x18000e893  add     r9, r10
0x18000e896  and     r9, rdx
0x18000e899  jmp     short loc_18000E89E
0x18000e89b  mov     r9, r10
0x18000e89e  movsxd  rax, ecx
0x18000e8a1  mov     rdx, [rax+r9]
0x18000e8a5  mov     rax, [r11+10h]
0x18000e8a9  mov     ecx, [rax+8]
0x18000e8ac  mov     rax, [r11+8]
0x18000e8b0  test    byte ptr [rcx+rax+3], 0Fh
0x18000e8b5  jz      short loc_18000E8C9
0x18000e8b7  movzx   eax, byte ptr [rcx+rax+3]
0x18000e8bc  mov     ecx, 0FFFFFFF0h
0x18000e8c1  and     rax, rcx
0x18000e8c4  add     rax, r10
0x18000e8c7  jmp     short loc_18000E8CC
0x18000e8c9  mov     rax, r10
0x18000e8cc  xor     rdx, rax
0x18000e8cf  mov     rcx, rdx; StackCookie
0x18000e8d2  jmp     __security_check_cookie
```
