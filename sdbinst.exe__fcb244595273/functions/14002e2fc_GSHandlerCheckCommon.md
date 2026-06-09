# __GSHandlerCheckCommon

- ea: `0x14002e2fc`
- end: `0x14002e35f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002e2d8`
- `0x14002e368`

## callees

- `0x14002e2fc`
- `0x14002e420`

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
0x14002e2fc  mov     r10, rcx
0x14002e2ff  mov     r11, rdx
0x14002e302  mov     ecx, [r8]
0x14002e305  and     ecx, 0FFFFFFF8h
0x14002e308  test    byte ptr [r8], 4
0x14002e30c  jz      short loc_14002E323
0x14002e30e  mov     eax, [r8+8]
0x14002e312  movsxd  r9, dword ptr [r8+4]
0x14002e316  neg     eax
0x14002e318  movsxd  rdx, eax
0x14002e31b  add     r9, r10
0x14002e31e  and     r9, rdx
0x14002e321  jmp     short loc_14002E326
0x14002e323  mov     r9, r10
0x14002e326  movsxd  rax, ecx
0x14002e329  mov     rdx, [rax+r9]
0x14002e32d  mov     rax, [r11+10h]
0x14002e331  mov     ecx, [rax+8]
0x14002e334  mov     rax, [r11+8]
0x14002e338  test    byte ptr [rcx+rax+3], 0Fh
0x14002e33d  jz      short loc_14002E351
0x14002e33f  movzx   eax, byte ptr [rcx+rax+3]
0x14002e344  mov     ecx, 0FFFFFFF0h
0x14002e349  and     rax, rcx
0x14002e34c  add     rax, r10
0x14002e34f  jmp     short loc_14002E354
0x14002e351  mov     rax, r10
0x14002e354  xor     rdx, rax
0x14002e357  mov     rcx, rdx; StackCookie
0x14002e35a  jmp     __security_check_cookie
```
