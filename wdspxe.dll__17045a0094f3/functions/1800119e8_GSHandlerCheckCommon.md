# __GSHandlerCheckCommon

- ea: `0x1800119e8`
- end: `0x180011a43`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800119c4`

## callees

- `0x1800119e8`
- `0x180011a90`

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
0x1800119e8  push    rbx
0x1800119ea  mov     r11d, [r8]
0x1800119ed  mov     rbx, rdx
0x1800119f0  and     r11d, 0FFFFFFF8h
0x1800119f4  mov     r9, rcx
0x1800119f7  test    byte ptr [r8], 4
0x1800119fb  mov     r10, rcx
0x1800119fe  jz      short loc_180011A13
0x180011a00  mov     eax, [r8+8]
0x180011a04  movsxd  r10, dword ptr [r8+4]
0x180011a08  neg     eax
0x180011a0a  add     r10, rcx
0x180011a0d  movsxd  rcx, eax
0x180011a10  and     r10, rcx
0x180011a13  movsxd  rax, r11d
0x180011a16  mov     rdx, [rax+r10]
0x180011a1a  mov     rax, [rbx+10h]
0x180011a1e  mov     ecx, [rax+8]
0x180011a21  mov     rax, [rbx+8]
0x180011a25  test    byte ptr [rcx+rax+3], 0Fh
0x180011a2a  jz      short loc_180011A37
0x180011a2c  movzx   eax, byte ptr [rcx+rax+3]
0x180011a31  and     eax, 0FFFFFFF0h
0x180011a34  add     r9, rax
0x180011a37  xor     r9, rdx
0x180011a3a  mov     rcx, r9; StackCookie
0x180011a3d  pop     rbx
0x180011a3e  jmp     __security_check_cookie
```
