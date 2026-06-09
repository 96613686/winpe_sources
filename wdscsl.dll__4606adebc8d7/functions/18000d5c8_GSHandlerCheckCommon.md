# __GSHandlerCheckCommon

- ea: `0x18000d5c8`
- end: `0x18000d623`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d5a4`
- `0x18000d62c`

## callees

- `0x18000d5c8`
- `0x18000d700`

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
0x18000d5c8  push    rbx
0x18000d5ca  mov     r11d, [r8]
0x18000d5cd  mov     rbx, rdx
0x18000d5d0  and     r11d, 0FFFFFFF8h
0x18000d5d4  mov     r9, rcx
0x18000d5d7  test    byte ptr [r8], 4
0x18000d5db  mov     r10, rcx
0x18000d5de  jz      short loc_18000D5F3
0x18000d5e0  mov     eax, [r8+8]
0x18000d5e4  movsxd  r10, dword ptr [r8+4]
0x18000d5e8  neg     eax
0x18000d5ea  add     r10, rcx
0x18000d5ed  movsxd  rcx, eax
0x18000d5f0  and     r10, rcx
0x18000d5f3  movsxd  rax, r11d
0x18000d5f6  mov     rdx, [rax+r10]
0x18000d5fa  mov     rax, [rbx+10h]
0x18000d5fe  mov     ecx, [rax+8]
0x18000d601  mov     rax, [rbx+8]
0x18000d605  test    byte ptr [rcx+rax+3], 0Fh
0x18000d60a  jz      short loc_18000D617
0x18000d60c  movzx   eax, byte ptr [rcx+rax+3]
0x18000d611  and     eax, 0FFFFFFF0h
0x18000d614  add     r9, rax
0x18000d617  xor     r9, rdx
0x18000d61a  mov     rcx, r9; StackCookie
0x18000d61d  pop     rbx
0x18000d61e  jmp     __security_check_cookie
```
