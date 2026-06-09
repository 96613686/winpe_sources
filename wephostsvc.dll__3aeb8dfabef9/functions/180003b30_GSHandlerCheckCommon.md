# __GSHandlerCheckCommon

- ea: `0x180003b30`
- end: `0x180003b93`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b0c`

## callees

- `0x180003b30`
- `0x180003be0`

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
0x180003b30  mov     r10, rcx
0x180003b33  mov     r11, rdx
0x180003b36  mov     ecx, [r8]
0x180003b39  and     ecx, 0FFFFFFF8h
0x180003b3c  test    byte ptr [r8], 4
0x180003b40  jz      short loc_180003B57
0x180003b42  mov     eax, [r8+8]
0x180003b46  movsxd  r9, dword ptr [r8+4]
0x180003b4a  neg     eax
0x180003b4c  movsxd  rdx, eax
0x180003b4f  add     r9, r10
0x180003b52  and     r9, rdx
0x180003b55  jmp     short loc_180003B5A
0x180003b57  mov     r9, r10
0x180003b5a  movsxd  rax, ecx
0x180003b5d  mov     rdx, [rax+r9]
0x180003b61  mov     rax, [r11+10h]
0x180003b65  mov     ecx, [rax+8]
0x180003b68  mov     rax, [r11+8]
0x180003b6c  test    byte ptr [rcx+rax+3], 0Fh
0x180003b71  jz      short loc_180003B85
0x180003b73  movzx   eax, byte ptr [rcx+rax+3]
0x180003b78  mov     ecx, 0FFFFFFF0h
0x180003b7d  and     rax, rcx
0x180003b80  add     rax, r10
0x180003b83  jmp     short loc_180003B88
0x180003b85  mov     rax, r10
0x180003b88  xor     rdx, rax
0x180003b8b  mov     rcx, rdx; StackCookie
0x180003b8e  jmp     __security_check_cookie
```
