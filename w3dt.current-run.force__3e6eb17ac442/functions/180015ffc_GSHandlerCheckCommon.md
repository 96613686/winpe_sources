# __GSHandlerCheckCommon

- ea: `0x180015ffc`
- end: `0x18001605f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015fd8`

## callees

- `0x180015ffc`
- `0x1800160a0`

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
0x180015ffc  mov     r10, rcx
0x180015fff  mov     r11, rdx
0x180016002  mov     ecx, [r8]
0x180016005  and     ecx, 0FFFFFFF8h
0x180016008  test    byte ptr [r8], 4
0x18001600c  jz      short loc_180016023
0x18001600e  mov     eax, [r8+8]
0x180016012  movsxd  r9, dword ptr [r8+4]
0x180016016  neg     eax
0x180016018  movsxd  rdx, eax
0x18001601b  add     r9, r10
0x18001601e  and     r9, rdx
0x180016021  jmp     short loc_180016026
0x180016023  mov     r9, r10
0x180016026  movsxd  rax, ecx
0x180016029  mov     rdx, [rax+r9]
0x18001602d  mov     rax, [r11+10h]
0x180016031  mov     ecx, [rax+8]
0x180016034  mov     rax, [r11+8]
0x180016038  test    byte ptr [rcx+rax+3], 0Fh
0x18001603d  jz      short loc_180016051
0x18001603f  movzx   eax, byte ptr [rcx+rax+3]
0x180016044  mov     ecx, 0FFFFFFF0h
0x180016049  and     rax, rcx
0x18001604c  add     rax, r10
0x18001604f  jmp     short loc_180016054
0x180016051  mov     rax, r10
0x180016054  xor     rdx, rax
0x180016057  mov     rcx, rdx; StackCookie
0x18001605a  jmp     __security_check_cookie
```
