# __GSHandlerCheckCommon

- ea: `0x140004f1c`
- end: `0x140004f8c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004ef8`

## callees

- `0x140004f1c`
- `0x140005050`

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
0x140004f1c  sub     rsp, 28h
0x140004f20  mov     eax, [r8]
0x140004f23  mov     r10, rcx
0x140004f26  mov     ecx, eax
0x140004f28  mov     r11, rdx
0x140004f2b  and     ecx, 0FFFFFFF8h
0x140004f2e  test    al, 4
0x140004f30  jz      short loc_140004F47
0x140004f32  mov     eax, [r8+8]
0x140004f36  movsxd  r9, dword ptr [r8+4]
0x140004f3a  neg     eax
0x140004f3c  movsxd  rdx, eax
0x140004f3f  add     r9, r10
0x140004f42  and     r9, rdx
0x140004f45  jmp     short loc_140004F4A
0x140004f47  mov     r9, r10
0x140004f4a  movsxd  rax, ecx
0x140004f4d  mov     rdx, [rax+r9]
0x140004f51  mov     rax, [r11+10h]
0x140004f55  mov     ecx, [rax+8]
0x140004f58  mov     rax, [r11+8]
0x140004f5c  movzx   r8d, byte ptr [rcx+rax+3]
0x140004f62  test    r8b, 0Fh
0x140004f66  jz      short loc_140004F78
0x140004f68  mov     eax, r8d
0x140004f6b  mov     ecx, 0FFFFFFF0h
0x140004f70  and     rax, rcx
0x140004f73  add     rax, r10
0x140004f76  jmp     short loc_140004F7B
0x140004f78  mov     rax, r10
0x140004f7b  xor     rdx, rax
0x140004f7e  mov     rcx, rdx; StackCookie
0x140004f81  call    __security_check_cookie
0x140004f86  add     rsp, 28h
0x140004f8a  retn
```
