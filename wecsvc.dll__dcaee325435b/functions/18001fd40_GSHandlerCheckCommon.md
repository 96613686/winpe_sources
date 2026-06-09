# __GSHandlerCheckCommon

- ea: `0x18001fd40`
- end: `0x18001fda3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fd1c`
- `0x18001fdac`

## callees

- `0x18001fd40`
- `0x18001fe50`

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
0x18001fd40  mov     r10, rcx
0x18001fd43  mov     r11, rdx
0x18001fd46  mov     ecx, [r8]
0x18001fd49  and     ecx, 0FFFFFFF8h
0x18001fd4c  test    byte ptr [r8], 4
0x18001fd50  jz      short loc_18001FD67
0x18001fd52  mov     eax, [r8+8]
0x18001fd56  movsxd  r9, dword ptr [r8+4]
0x18001fd5a  neg     eax
0x18001fd5c  movsxd  rdx, eax
0x18001fd5f  add     r9, r10
0x18001fd62  and     r9, rdx
0x18001fd65  jmp     short loc_18001FD6A
0x18001fd67  mov     r9, r10
0x18001fd6a  movsxd  rax, ecx
0x18001fd6d  mov     rdx, [rax+r9]
0x18001fd71  mov     rax, [r11+10h]
0x18001fd75  mov     ecx, [rax+8]
0x18001fd78  mov     rax, [r11+8]
0x18001fd7c  test    byte ptr [rcx+rax+3], 0Fh
0x18001fd81  jz      short loc_18001FD95
0x18001fd83  movzx   eax, byte ptr [rcx+rax+3]
0x18001fd88  mov     ecx, 0FFFFFFF0h
0x18001fd8d  and     rax, rcx
0x18001fd90  add     rax, r10
0x18001fd93  jmp     short loc_18001FD98
0x18001fd95  mov     rax, r10
0x18001fd98  xor     rdx, rax
0x18001fd9b  mov     rcx, rdx; StackCookie
0x18001fd9e  jmp     __security_check_cookie
```
