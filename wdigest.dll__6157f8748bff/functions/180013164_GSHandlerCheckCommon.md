# __GSHandlerCheckCommon

- ea: `0x180013164`
- end: `0x1800131c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013140`
- `0x1800376dc`

## callees

- `0x180012880`
- `0x180013164`

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
0x180013164  mov     r10, rcx
0x180013167  mov     r11, rdx
0x18001316a  mov     ecx, [r8]
0x18001316d  and     ecx, 0FFFFFFF8h
0x180013170  test    byte ptr [r8], 4
0x180013174  jz      short loc_18001318B
0x180013176  mov     eax, [r8+8]
0x18001317a  movsxd  r9, dword ptr [r8+4]
0x18001317e  neg     eax
0x180013180  movsxd  rdx, eax
0x180013183  add     r9, r10
0x180013186  and     r9, rdx
0x180013189  jmp     short loc_18001318E
0x18001318b  mov     r9, r10
0x18001318e  movsxd  rax, ecx
0x180013191  mov     rdx, [rax+r9]
0x180013195  mov     rax, [r11+10h]
0x180013199  mov     ecx, [rax+8]
0x18001319c  mov     rax, [r11+8]
0x1800131a0  test    byte ptr [rcx+rax+3], 0Fh
0x1800131a5  jz      short loc_1800131B9
0x1800131a7  movzx   eax, byte ptr [rcx+rax+3]
0x1800131ac  mov     ecx, 0FFFFFFF0h
0x1800131b1  and     rax, rcx
0x1800131b4  add     rax, r10
0x1800131b7  jmp     short loc_1800131BC
0x1800131b9  mov     rax, r10
0x1800131bc  xor     rdx, rax
0x1800131bf  mov     rcx, rdx; StackCookie
0x1800131c2  jmp     __security_check_cookie
```
