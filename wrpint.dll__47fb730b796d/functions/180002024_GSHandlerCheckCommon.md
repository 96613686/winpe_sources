# __GSHandlerCheckCommon

- ea: `0x180002024`
- end: `0x180002087`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002000`

## callees

- `0x180002024`
- `0x18001b7b0`

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
0x180002024  mov     r10, rcx
0x180002027  mov     r11, rdx
0x18000202a  mov     ecx, [r8]
0x18000202d  and     ecx, 0FFFFFFF8h
0x180002030  test    byte ptr [r8], 4
0x180002034  jz      short loc_18000204B
0x180002036  mov     eax, [r8+8]
0x18000203a  movsxd  r9, dword ptr [r8+4]
0x18000203e  neg     eax
0x180002040  movsxd  rdx, eax
0x180002043  add     r9, r10
0x180002046  and     r9, rdx
0x180002049  jmp     short loc_18000204E
0x18000204b  mov     r9, r10
0x18000204e  movsxd  rax, ecx
0x180002051  mov     rdx, [rax+r9]
0x180002055  mov     rax, [r11+10h]
0x180002059  mov     ecx, [rax+8]
0x18000205c  mov     rax, [r11+8]
0x180002060  test    byte ptr [rcx+rax+3], 0Fh
0x180002065  jz      short loc_180002079
0x180002067  movzx   eax, byte ptr [rcx+rax+3]
0x18000206c  mov     ecx, 0FFFFFFF0h
0x180002071  and     rax, rcx
0x180002074  add     rax, r10
0x180002077  jmp     short loc_18000207C
0x180002079  mov     rax, r10
0x18000207c  xor     rdx, rax
0x18000207f  mov     rcx, rdx; StackCookie
0x180002082  jmp     __security_check_cookie
```
