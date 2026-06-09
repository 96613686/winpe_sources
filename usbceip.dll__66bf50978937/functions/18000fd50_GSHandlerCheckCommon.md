# __GSHandlerCheckCommon

- ea: `0x18000fd50`
- end: `0x18000fdb3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fd2c`
- `0x18000fdbc`

## callees

- `0x180002410`
- `0x18000fd50`

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
0x18000fd50  mov     r10, rcx
0x18000fd53  mov     r11, rdx
0x18000fd56  mov     ecx, [r8]
0x18000fd59  and     ecx, 0FFFFFFF8h
0x18000fd5c  test    byte ptr [r8], 4
0x18000fd60  jz      short loc_18000FD77
0x18000fd62  mov     eax, [r8+8]
0x18000fd66  movsxd  r9, dword ptr [r8+4]
0x18000fd6a  neg     eax
0x18000fd6c  movsxd  rdx, eax
0x18000fd6f  add     r9, r10
0x18000fd72  and     r9, rdx
0x18000fd75  jmp     short loc_18000FD7A
0x18000fd77  mov     r9, r10
0x18000fd7a  movsxd  rax, ecx
0x18000fd7d  mov     rdx, [rax+r9]
0x18000fd81  mov     rax, [r11+10h]
0x18000fd85  mov     ecx, [rax+8]
0x18000fd88  mov     rax, [r11+8]
0x18000fd8c  test    byte ptr [rcx+rax+3], 0Fh
0x18000fd91  jz      short loc_18000FDA5
0x18000fd93  movzx   eax, byte ptr [rcx+rax+3]
0x18000fd98  mov     ecx, 0FFFFFFF0h
0x18000fd9d  and     rax, rcx
0x18000fda0  add     rax, r10
0x18000fda3  jmp     short loc_18000FDA8
0x18000fda5  mov     rax, r10
0x18000fda8  xor     rdx, rax
0x18000fdab  mov     rcx, rdx; StackCookie
0x18000fdae  jmp     __security_check_cookie
```
