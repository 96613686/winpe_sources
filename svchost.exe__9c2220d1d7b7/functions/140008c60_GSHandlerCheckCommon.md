# __GSHandlerCheckCommon

- ea: `0x140008c60`
- end: `0x140008cc3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008c3c`

## callees

- `0x140004f90`
- `0x140008c60`

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
0x140008c60  mov     r10, rcx
0x140008c63  mov     r11, rdx
0x140008c66  mov     ecx, [r8]
0x140008c69  and     ecx, 0FFFFFFF8h
0x140008c6c  test    byte ptr [r8], 4
0x140008c70  jz      short loc_140008C87
0x140008c72  mov     eax, [r8+8]
0x140008c76  movsxd  r9, dword ptr [r8+4]
0x140008c7a  neg     eax
0x140008c7c  movsxd  rdx, eax
0x140008c7f  add     r9, r10
0x140008c82  and     r9, rdx
0x140008c85  jmp     short loc_140008C8A
0x140008c87  mov     r9, r10
0x140008c8a  movsxd  rax, ecx
0x140008c8d  mov     rdx, [rax+r9]
0x140008c91  mov     rax, [r11+10h]
0x140008c95  mov     ecx, [rax+8]
0x140008c98  mov     rax, [r11+8]
0x140008c9c  test    byte ptr [rcx+rax+3], 0Fh
0x140008ca1  jz      short loc_140008CB5
0x140008ca3  movzx   eax, byte ptr [rcx+rax+3]
0x140008ca8  mov     ecx, 0FFFFFFF0h
0x140008cad  and     rax, rcx
0x140008cb0  add     rax, r10
0x140008cb3  jmp     short loc_140008CB8
0x140008cb5  mov     rax, r10
0x140008cb8  xor     rdx, rax
0x140008cbb  mov     rcx, rdx; StackCookie
0x140008cbe  jmp     __security_check_cookie
```
