# __GSHandlerCheckCommon

- ea: `0x100423a28`
- end: `0x100423a83`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100423a04`
- `0x100423a98`
- `0x100423b84`

## callees

- `0x100416590`
- `0x100423a28`

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
0x100423a28  push    rbx
0x100423a2a  mov     r11d, [r8]
0x100423a2d  mov     rbx, rdx
0x100423a30  and     r11d, 0FFFFFFF8h
0x100423a34  mov     r9, rcx
0x100423a37  test    byte ptr [r8], 4
0x100423a3b  mov     r10, rcx
0x100423a3e  jz      short loc_100423A53
0x100423a40  mov     eax, [r8+8]
0x100423a44  movsxd  r10, dword ptr [r8+4]
0x100423a48  neg     eax
0x100423a4a  add     r10, rcx
0x100423a4d  movsxd  rcx, eax
0x100423a50  and     r10, rcx
0x100423a53  movsxd  rax, r11d
0x100423a56  mov     rdx, [rax+r10]
0x100423a5a  mov     rax, [rbx+10h]
0x100423a5e  mov     ecx, [rax+8]
0x100423a61  mov     rax, [rbx+8]
0x100423a65  test    byte ptr [rcx+rax+3], 0Fh
0x100423a6a  jz      short loc_100423A77
0x100423a6c  movzx   eax, byte ptr [rcx+rax+3]
0x100423a71  and     eax, 0FFFFFFF0h
0x100423a74  add     r9, rax
0x100423a77  xor     r9, rdx
0x100423a7a  mov     rcx, r9; StackCookie
0x100423a7d  pop     rbx
0x100423a7e  jmp     __security_check_cookie
```
