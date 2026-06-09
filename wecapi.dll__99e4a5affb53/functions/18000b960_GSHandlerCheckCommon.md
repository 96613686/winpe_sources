# __GSHandlerCheckCommon

- ea: `0x18000b960`
- end: `0x18000b9c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b93c`
- `0x18000b9cc`

## callees

- `0x18000b960`
- `0x18000ba60`

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
0x18000b960  mov     r10, rcx
0x18000b963  mov     r11, rdx
0x18000b966  mov     ecx, [r8]
0x18000b969  and     ecx, 0FFFFFFF8h
0x18000b96c  test    byte ptr [r8], 4
0x18000b970  jz      short loc_18000B987
0x18000b972  mov     eax, [r8+8]
0x18000b976  movsxd  r9, dword ptr [r8+4]
0x18000b97a  neg     eax
0x18000b97c  movsxd  rdx, eax
0x18000b97f  add     r9, r10
0x18000b982  and     r9, rdx
0x18000b985  jmp     short loc_18000B98A
0x18000b987  mov     r9, r10
0x18000b98a  movsxd  rax, ecx
0x18000b98d  mov     rdx, [rax+r9]
0x18000b991  mov     rax, [r11+10h]
0x18000b995  mov     ecx, [rax+8]
0x18000b998  mov     rax, [r11+8]
0x18000b99c  test    byte ptr [rcx+rax+3], 0Fh
0x18000b9a1  jz      short loc_18000B9B5
0x18000b9a3  movzx   eax, byte ptr [rcx+rax+3]
0x18000b9a8  mov     ecx, 0FFFFFFF0h
0x18000b9ad  and     rax, rcx
0x18000b9b0  add     rax, r10
0x18000b9b3  jmp     short loc_18000B9B8
0x18000b9b5  mov     rax, r10
0x18000b9b8  xor     rdx, rax
0x18000b9bb  mov     rcx, rdx; StackCookie
0x18000b9be  jmp     __security_check_cookie
```
