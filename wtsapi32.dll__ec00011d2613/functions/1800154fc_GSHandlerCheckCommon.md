# __GSHandlerCheckCommon

- ea: `0x1800154fc`
- end: `0x18001555f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800154d8`

## callees

- `0x1800154fc`
- `0x1800155c0`

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
0x1800154fc  mov     r10, rcx
0x1800154ff  mov     r11, rdx
0x180015502  mov     ecx, [r8]
0x180015505  and     ecx, 0FFFFFFF8h
0x180015508  test    byte ptr [r8], 4
0x18001550c  jz      short loc_180015523
0x18001550e  mov     eax, [r8+8]
0x180015512  movsxd  r9, dword ptr [r8+4]
0x180015516  neg     eax
0x180015518  movsxd  rdx, eax
0x18001551b  add     r9, r10
0x18001551e  and     r9, rdx
0x180015521  jmp     short loc_180015526
0x180015523  mov     r9, r10
0x180015526  movsxd  rax, ecx
0x180015529  mov     rdx, [rax+r9]
0x18001552d  mov     rax, [r11+10h]
0x180015531  mov     ecx, [rax+8]
0x180015534  mov     rax, [r11+8]
0x180015538  test    byte ptr [rcx+rax+3], 0Fh
0x18001553d  jz      short loc_180015551
0x18001553f  movzx   eax, byte ptr [rcx+rax+3]
0x180015544  mov     ecx, 0FFFFFFF0h
0x180015549  and     rax, rcx
0x18001554c  add     rax, r10
0x18001554f  jmp     short loc_180015554
0x180015551  mov     rax, r10
0x180015554  xor     rdx, rax
0x180015557  mov     rcx, rdx; StackCookie
0x18001555a  jmp     __security_check_cookie
```
