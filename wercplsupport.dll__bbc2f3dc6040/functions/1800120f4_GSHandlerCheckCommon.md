# __GSHandlerCheckCommon

- ea: `0x1800120f4`
- end: `0x180012157`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800120d0`

## callees

- `0x1800120f4`
- `0x1800121b0`

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
0x1800120f4  mov     r10, rcx
0x1800120f7  mov     r11, rdx
0x1800120fa  mov     ecx, [r8]
0x1800120fd  and     ecx, 0FFFFFFF8h
0x180012100  test    byte ptr [r8], 4
0x180012104  jz      short loc_18001211B
0x180012106  mov     eax, [r8+8]
0x18001210a  movsxd  r9, dword ptr [r8+4]
0x18001210e  neg     eax
0x180012110  movsxd  rdx, eax
0x180012113  add     r9, r10
0x180012116  and     r9, rdx
0x180012119  jmp     short loc_18001211E
0x18001211b  mov     r9, r10
0x18001211e  movsxd  rax, ecx
0x180012121  mov     rdx, [rax+r9]
0x180012125  mov     rax, [r11+10h]
0x180012129  mov     ecx, [rax+8]
0x18001212c  mov     rax, [r11+8]
0x180012130  test    byte ptr [rcx+rax+3], 0Fh
0x180012135  jz      short loc_180012149
0x180012137  movzx   eax, byte ptr [rcx+rax+3]
0x18001213c  mov     ecx, 0FFFFFFF0h
0x180012141  and     rax, rcx
0x180012144  add     rax, r10
0x180012147  jmp     short loc_18001214C
0x180012149  mov     rax, r10
0x18001214c  xor     rdx, rax
0x18001214f  mov     rcx, rdx; StackCookie
0x180012152  jmp     __security_check_cookie
```
