# __GSHandlerCheckCommon

- ea: `0x1800032f4`
- end: `0x180003357`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800032d0`
- `0x180003360`

## callees

- `0x1800032f4`
- `0x1800033f0`

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
0x1800032f4  mov     r10, rcx
0x1800032f7  mov     r11, rdx
0x1800032fa  mov     ecx, [r8]
0x1800032fd  and     ecx, 0FFFFFFF8h
0x180003300  test    byte ptr [r8], 4
0x180003304  jz      short loc_18000331B
0x180003306  mov     eax, [r8+8]
0x18000330a  movsxd  r9, dword ptr [r8+4]
0x18000330e  neg     eax
0x180003310  movsxd  rdx, eax
0x180003313  add     r9, r10
0x180003316  and     r9, rdx
0x180003319  jmp     short loc_18000331E
0x18000331b  mov     r9, r10
0x18000331e  movsxd  rax, ecx
0x180003321  mov     rdx, [rax+r9]
0x180003325  mov     rax, [r11+10h]
0x180003329  mov     ecx, [rax+8]
0x18000332c  mov     rax, [r11+8]
0x180003330  test    byte ptr [rcx+rax+3], 0Fh
0x180003335  jz      short loc_180003349
0x180003337  movzx   eax, byte ptr [rcx+rax+3]
0x18000333c  mov     ecx, 0FFFFFFF0h
0x180003341  and     rax, rcx
0x180003344  add     rax, r10
0x180003347  jmp     short loc_18000334C
0x180003349  mov     rax, r10
0x18000334c  xor     rdx, rax
0x18000334f  mov     rcx, rdx; StackCookie
0x180003352  jmp     __security_check_cookie
```
