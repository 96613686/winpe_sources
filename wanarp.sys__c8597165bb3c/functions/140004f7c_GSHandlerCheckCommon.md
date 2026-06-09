# __GSHandlerCheckCommon

- ea: `0x140004f7c`
- end: `0x140004fec`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004f58`

## callees

- `0x140004f7c`
- `0x1400050b0`

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
0x140004f7c  sub     rsp, 28h
0x140004f80  mov     eax, [r8]
0x140004f83  mov     r10, rcx
0x140004f86  mov     ecx, eax
0x140004f88  mov     r11, rdx
0x140004f8b  and     ecx, 0FFFFFFF8h
0x140004f8e  test    al, 4
0x140004f90  jz      short loc_140004FA7
0x140004f92  mov     eax, [r8+8]
0x140004f96  movsxd  r9, dword ptr [r8+4]
0x140004f9a  neg     eax
0x140004f9c  movsxd  rdx, eax
0x140004f9f  add     r9, r10
0x140004fa2  and     r9, rdx
0x140004fa5  jmp     short loc_140004FAA
0x140004fa7  mov     r9, r10
0x140004faa  movsxd  rax, ecx
0x140004fad  mov     rdx, [rax+r9]
0x140004fb1  mov     rax, [r11+10h]
0x140004fb5  mov     ecx, [rax+8]
0x140004fb8  mov     rax, [r11+8]
0x140004fbc  movzx   r8d, byte ptr [rcx+rax+3]
0x140004fc2  test    r8b, 0Fh
0x140004fc6  jz      short loc_140004FD8
0x140004fc8  mov     eax, r8d
0x140004fcb  mov     ecx, 0FFFFFFF0h
0x140004fd0  and     rax, rcx
0x140004fd3  add     rax, r10
0x140004fd6  jmp     short loc_140004FDB
0x140004fd8  mov     rax, r10
0x140004fdb  xor     rdx, rax
0x140004fde  mov     rcx, rdx; StackCookie
0x140004fe1  call    __security_check_cookie
0x140004fe6  add     rsp, 28h
0x140004fea  retn
```
