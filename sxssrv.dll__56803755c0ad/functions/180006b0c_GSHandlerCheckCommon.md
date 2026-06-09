# __GSHandlerCheckCommon

- ea: `0x180006b0c`
- end: `0x180006b67`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006ae8`
- `0x180006b70`

## callees

- `0x180006b0c`
- `0x180006c30`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x180006b0c  push    rbx
0x180006b0e  mov     r11d, [r8]
0x180006b11  mov     rbx, rdx
0x180006b14  and     r11d, 0FFFFFFF8h
0x180006b18  mov     r9, rcx
0x180006b1b  test    byte ptr [r8], 4
0x180006b1f  mov     r10, rcx
0x180006b22  jz      short loc_180006B37
0x180006b24  mov     eax, [r8+8]
0x180006b28  movsxd  r10, dword ptr [r8+4]
0x180006b2c  neg     eax
0x180006b2e  add     r10, rcx
0x180006b31  movsxd  rcx, eax
0x180006b34  and     r10, rcx
0x180006b37  movsxd  rax, r11d
0x180006b3a  mov     rdx, [rax+r10]
0x180006b3e  mov     rax, [rbx+10h]
0x180006b42  mov     ecx, [rax+8]
0x180006b45  mov     rax, [rbx+8]
0x180006b49  test    byte ptr [rcx+rax+3], 0Fh
0x180006b4e  jz      short loc_180006B5B
0x180006b50  movzx   eax, byte ptr [rcx+rax+3]
0x180006b55  and     eax, 0FFFFFFF0h
0x180006b58  add     r9, rax
0x180006b5b  xor     r9, rdx
0x180006b5e  mov     rcx, r9; StackCookie
0x180006b61  pop     rbx
0x180006b62  jmp     __security_check_cookie
```
