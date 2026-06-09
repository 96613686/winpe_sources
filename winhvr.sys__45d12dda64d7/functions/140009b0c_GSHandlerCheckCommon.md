# __GSHandlerCheckCommon

- ea: `0x140009b0c`
- end: `0x140009b7c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009ae8`

## callees

- `0x140009b0c`
- `0x140009c50`

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
0x140009b0c  sub     rsp, 28h
0x140009b10  mov     eax, [r8]
0x140009b13  mov     r10, rcx
0x140009b16  mov     ecx, eax
0x140009b18  mov     r11, rdx
0x140009b1b  and     ecx, 0FFFFFFF8h
0x140009b1e  test    al, 4
0x140009b20  jz      short loc_140009B37
0x140009b22  mov     eax, [r8+8]
0x140009b26  movsxd  r9, dword ptr [r8+4]
0x140009b2a  neg     eax
0x140009b2c  movsxd  rdx, eax
0x140009b2f  add     r9, r10
0x140009b32  and     r9, rdx
0x140009b35  jmp     short loc_140009B3A
0x140009b37  mov     r9, r10
0x140009b3a  movsxd  rax, ecx
0x140009b3d  mov     rdx, [rax+r9]
0x140009b41  mov     rax, [r11+10h]
0x140009b45  mov     ecx, [rax+8]
0x140009b48  mov     rax, [r11+8]
0x140009b4c  movzx   r8d, byte ptr [rcx+rax+3]
0x140009b52  test    r8b, 0Fh
0x140009b56  jz      short loc_140009B68
0x140009b58  mov     eax, r8d
0x140009b5b  mov     ecx, 0FFFFFFF0h
0x140009b60  and     rax, rcx
0x140009b63  add     rax, r10
0x140009b66  jmp     short loc_140009B6B
0x140009b68  mov     rax, r10
0x140009b6b  xor     rdx, rax
0x140009b6e  mov     rcx, rdx; StackCookie
0x140009b71  call    __security_check_cookie
0x140009b76  add     rsp, 28h
0x140009b7a  retn
```
