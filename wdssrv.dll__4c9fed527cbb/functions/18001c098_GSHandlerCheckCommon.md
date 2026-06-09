# __GSHandlerCheckCommon

- ea: `0x18001c098`
- end: `0x18001c0f3`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c074`

## callees

- `0x18001c098`
- `0x18001c150`

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
0x18001c098  push    rbx
0x18001c09a  mov     r11d, [r8]
0x18001c09d  mov     rbx, rdx
0x18001c0a0  and     r11d, 0FFFFFFF8h
0x18001c0a4  mov     r9, rcx
0x18001c0a7  test    byte ptr [r8], 4
0x18001c0ab  mov     r10, rcx
0x18001c0ae  jz      short loc_18001C0C3
0x18001c0b0  mov     eax, [r8+8]
0x18001c0b4  movsxd  r10, dword ptr [r8+4]
0x18001c0b8  neg     eax
0x18001c0ba  add     r10, rcx
0x18001c0bd  movsxd  rcx, eax
0x18001c0c0  and     r10, rcx
0x18001c0c3  movsxd  rax, r11d
0x18001c0c6  mov     rdx, [rax+r10]
0x18001c0ca  mov     rax, [rbx+10h]
0x18001c0ce  mov     ecx, [rax+8]
0x18001c0d1  mov     rax, [rbx+8]
0x18001c0d5  test    byte ptr [rcx+rax+3], 0Fh
0x18001c0da  jz      short loc_18001C0E7
0x18001c0dc  movzx   eax, byte ptr [rcx+rax+3]
0x18001c0e1  and     eax, 0FFFFFFF0h
0x18001c0e4  add     r9, rax
0x18001c0e7  xor     r9, rdx
0x18001c0ea  mov     rcx, r9; StackCookie
0x18001c0ed  pop     rbx
0x18001c0ee  jmp     __security_check_cookie
```
