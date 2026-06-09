# __GSHandlerCheckCommon

- ea: `0x180006994`
- end: `0x1800069f7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006970`
- `0x180006ad4`
- `0x18000be38`

## callees

- `0x180001590`
- `0x180006994`

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
0x180006994  mov     r10, rcx
0x180006997  mov     r11, rdx
0x18000699a  mov     ecx, [r8]
0x18000699d  and     ecx, 0FFFFFFF8h
0x1800069a0  test    byte ptr [r8], 4
0x1800069a4  jz      short loc_1800069BB
0x1800069a6  mov     eax, [r8+8]
0x1800069aa  movsxd  r9, dword ptr [r8+4]
0x1800069ae  neg     eax
0x1800069b0  movsxd  rdx, eax
0x1800069b3  add     r9, r10
0x1800069b6  and     r9, rdx
0x1800069b9  jmp     short loc_1800069BE
0x1800069bb  mov     r9, r10
0x1800069be  movsxd  rax, ecx
0x1800069c1  mov     rdx, [rax+r9]
0x1800069c5  mov     rax, [r11+10h]
0x1800069c9  mov     ecx, [rax+8]
0x1800069cc  mov     rax, [r11+8]
0x1800069d0  test    byte ptr [rcx+rax+3], 0Fh
0x1800069d5  jz      short loc_1800069E9
0x1800069d7  movzx   eax, byte ptr [rcx+rax+3]
0x1800069dc  mov     ecx, 0FFFFFFF0h
0x1800069e1  and     rax, rcx
0x1800069e4  add     rax, r10
0x1800069e7  jmp     short loc_1800069EC
0x1800069e9  mov     rax, r10
0x1800069ec  xor     rdx, rax
0x1800069ef  mov     rcx, rdx; StackCookie
0x1800069f2  jmp     __security_check_cookie
```
