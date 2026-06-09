# __GSHandlerCheckCommon

- ea: `0x140011d5c`
- end: `0x140011dcc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011d38`

## callees

- `0x140011d5c`
- `0x140011e90`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x140011d5c  sub     rsp, 28h
0x140011d60  mov     eax, [r8]
0x140011d63  mov     r10, rcx
0x140011d66  mov     ecx, eax
0x140011d68  mov     r11, rdx
0x140011d6b  and     ecx, 0FFFFFFF8h
0x140011d6e  test    al, 4
0x140011d70  jz      short loc_140011D87
0x140011d72  mov     eax, [r8+8]
0x140011d76  movsxd  r9, dword ptr [r8+4]
0x140011d7a  neg     eax
0x140011d7c  movsxd  rdx, eax
0x140011d7f  add     r9, r10
0x140011d82  and     r9, rdx
0x140011d85  jmp     short loc_140011D8A
0x140011d87  mov     r9, r10
0x140011d8a  movsxd  rax, ecx
0x140011d8d  mov     rdx, [rax+r9]
0x140011d91  mov     rax, [r11+10h]
0x140011d95  mov     ecx, [rax+8]
0x140011d98  mov     rax, [r11+8]
0x140011d9c  movzx   r8d, byte ptr [rcx+rax+3]
0x140011da2  test    r8b, 0Fh
0x140011da6  jz      short loc_140011DB8
0x140011da8  mov     eax, r8d
0x140011dab  mov     ecx, 0FFFFFFF0h
0x140011db0  and     rax, rcx
0x140011db3  add     rax, r10
0x140011db6  jmp     short loc_140011DBB
0x140011db8  mov     rax, r10
0x140011dbb  xor     rdx, rax
0x140011dbe  mov     rcx, rdx; StackCookie
0x140011dc1  call    __security_check_cookie
0x140011dc6  add     rsp, 28h
0x140011dca  retn
```
