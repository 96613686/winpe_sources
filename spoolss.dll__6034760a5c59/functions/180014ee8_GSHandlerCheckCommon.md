# __GSHandlerCheckCommon

- ea: `0x180014ee8`
- end: `0x180014f4b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014ec4`
- `0x180014f54`

## callees

- `0x180005320`
- `0x180014ee8`

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
0x180014ee8  mov     r10, rcx
0x180014eeb  mov     r11, rdx
0x180014eee  mov     ecx, [r8]
0x180014ef1  and     ecx, 0FFFFFFF8h
0x180014ef4  test    byte ptr [r8], 4
0x180014ef8  jz      short loc_180014F0F
0x180014efa  mov     eax, [r8+8]
0x180014efe  movsxd  r9, dword ptr [r8+4]
0x180014f02  neg     eax
0x180014f04  movsxd  rdx, eax
0x180014f07  add     r9, r10
0x180014f0a  and     r9, rdx
0x180014f0d  jmp     short loc_180014F12
0x180014f0f  mov     r9, r10
0x180014f12  movsxd  rax, ecx
0x180014f15  mov     rdx, [rax+r9]
0x180014f19  mov     rax, [r11+10h]
0x180014f1d  mov     ecx, [rax+8]
0x180014f20  mov     rax, [r11+8]
0x180014f24  test    byte ptr [rcx+rax+3], 0Fh
0x180014f29  jz      short loc_180014F3D
0x180014f2b  movzx   eax, byte ptr [rcx+rax+3]
0x180014f30  mov     ecx, 0FFFFFFF0h
0x180014f35  and     rax, rcx
0x180014f38  add     rax, r10
0x180014f3b  jmp     short loc_180014F40
0x180014f3d  mov     rax, r10
0x180014f40  xor     rdx, rax
0x180014f43  mov     rcx, rdx; StackCookie
0x180014f46  jmp     __security_check_cookie
```
