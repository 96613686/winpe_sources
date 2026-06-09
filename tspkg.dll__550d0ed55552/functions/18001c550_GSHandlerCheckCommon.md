# __GSHandlerCheckCommon

- ea: `0x18001c550`
- end: `0x18001c5b3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c52c`

## callees

- `0x18000b550`
- `0x18001c550`

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
0x18001c550  mov     r10, rcx
0x18001c553  mov     r11, rdx
0x18001c556  mov     ecx, [r8]
0x18001c559  and     ecx, 0FFFFFFF8h
0x18001c55c  test    byte ptr [r8], 4
0x18001c560  jz      short loc_18001C577
0x18001c562  mov     eax, [r8+8]
0x18001c566  movsxd  r9, dword ptr [r8+4]
0x18001c56a  neg     eax
0x18001c56c  movsxd  rdx, eax
0x18001c56f  add     r9, r10
0x18001c572  and     r9, rdx
0x18001c575  jmp     short loc_18001C57A
0x18001c577  mov     r9, r10
0x18001c57a  movsxd  rax, ecx
0x18001c57d  mov     rdx, [rax+r9]
0x18001c581  mov     rax, [r11+10h]
0x18001c585  mov     ecx, [rax+8]
0x18001c588  mov     rax, [r11+8]
0x18001c58c  test    byte ptr [rcx+rax+3], 0Fh
0x18001c591  jz      short loc_18001C5A5
0x18001c593  movzx   eax, byte ptr [rcx+rax+3]
0x18001c598  mov     ecx, 0FFFFFFF0h
0x18001c59d  and     rax, rcx
0x18001c5a0  add     rax, r10
0x18001c5a3  jmp     short loc_18001C5A8
0x18001c5a5  mov     rax, r10
0x18001c5a8  xor     rdx, rax
0x18001c5ab  mov     rcx, rdx; StackCookie
0x18001c5ae  jmp     __security_check_cookie
```
