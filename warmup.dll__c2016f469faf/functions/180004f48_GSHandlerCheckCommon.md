# __GSHandlerCheckCommon

- ea: `0x180004f48`
- end: `0x180004fab`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004f24`

## callees

- `0x180004f48`
- `0x180004fe0`

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
0x180004f48  mov     r10, rcx
0x180004f4b  mov     r11, rdx
0x180004f4e  mov     ecx, [r8]
0x180004f51  and     ecx, 0FFFFFFF8h
0x180004f54  test    byte ptr [r8], 4
0x180004f58  jz      short loc_180004F6F
0x180004f5a  mov     eax, [r8+8]
0x180004f5e  movsxd  r9, dword ptr [r8+4]
0x180004f62  neg     eax
0x180004f64  movsxd  rdx, eax
0x180004f67  add     r9, r10
0x180004f6a  and     r9, rdx
0x180004f6d  jmp     short loc_180004F72
0x180004f6f  mov     r9, r10
0x180004f72  movsxd  rax, ecx
0x180004f75  mov     rdx, [rax+r9]
0x180004f79  mov     rax, [r11+10h]
0x180004f7d  mov     ecx, [rax+8]
0x180004f80  mov     rax, [r11+8]
0x180004f84  test    byte ptr [rcx+rax+3], 0Fh
0x180004f89  jz      short loc_180004F9D
0x180004f8b  movzx   eax, byte ptr [rcx+rax+3]
0x180004f90  mov     ecx, 0FFFFFFF0h
0x180004f95  and     rax, rcx
0x180004f98  add     rax, r10
0x180004f9b  jmp     short loc_180004FA0
0x180004f9d  mov     rax, r10
0x180004fa0  xor     rdx, rax
0x180004fa3  mov     rcx, rdx; StackCookie
0x180004fa6  jmp     __security_check_cookie
```
