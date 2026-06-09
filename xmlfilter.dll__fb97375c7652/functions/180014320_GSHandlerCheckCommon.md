# __GSHandlerCheckCommon

- ea: `0x180014320`
- end: `0x180014383`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800142fc`
- `0x18001438c`

## callees

- `0x1800020e0`
- `0x180014320`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180014320  mov     r10, rcx
0x180014323  mov     r11, rdx
0x180014326  mov     ecx, [r8]
0x180014329  and     ecx, 0FFFFFFF8h
0x18001432c  test    byte ptr [r8], 4
0x180014330  jz      short loc_180014347
0x180014332  mov     eax, [r8+8]
0x180014336  movsxd  r9, dword ptr [r8+4]
0x18001433a  neg     eax
0x18001433c  movsxd  rdx, eax
0x18001433f  add     r9, r10
0x180014342  and     r9, rdx
0x180014345  jmp     short loc_18001434A
0x180014347  mov     r9, r10
0x18001434a  movsxd  rax, ecx
0x18001434d  mov     rdx, [rax+r9]
0x180014351  mov     rax, [r11+10h]
0x180014355  mov     ecx, [rax+8]
0x180014358  mov     rax, [r11+8]
0x18001435c  test    byte ptr [rcx+rax+3], 0Fh
0x180014361  jz      short loc_180014375
0x180014363  movzx   eax, byte ptr [rcx+rax+3]
0x180014368  mov     ecx, 0FFFFFFF0h
0x18001436d  and     rax, rcx
0x180014370  add     rax, r10
0x180014373  jmp     short loc_180014378
0x180014375  mov     rax, r10
0x180014378  xor     rdx, rax
0x18001437b  mov     rcx, rdx; StackCookie
0x18001437e  jmp     __security_check_cookie
```
