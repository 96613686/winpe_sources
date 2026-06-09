# __GSHandlerCheckCommon

- ea: `0x1800168f0`
- end: `0x180016953`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800168cc`
- `0x18001695c`

## callees

- `0x180005680`
- `0x1800168f0`

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
0x1800168f0  mov     r10, rcx
0x1800168f3  mov     r11, rdx
0x1800168f6  mov     ecx, [r8]
0x1800168f9  and     ecx, 0FFFFFFF8h
0x1800168fc  test    byte ptr [r8], 4
0x180016900  jz      short loc_180016917
0x180016902  mov     eax, [r8+8]
0x180016906  movsxd  r9, dword ptr [r8+4]
0x18001690a  neg     eax
0x18001690c  movsxd  rdx, eax
0x18001690f  add     r9, r10
0x180016912  and     r9, rdx
0x180016915  jmp     short loc_18001691A
0x180016917  mov     r9, r10
0x18001691a  movsxd  rax, ecx
0x18001691d  mov     rdx, [rax+r9]
0x180016921  mov     rax, [r11+10h]
0x180016925  mov     ecx, [rax+8]
0x180016928  mov     rax, [r11+8]
0x18001692c  test    byte ptr [rcx+rax+3], 0Fh
0x180016931  jz      short loc_180016945
0x180016933  movzx   eax, byte ptr [rcx+rax+3]
0x180016938  mov     ecx, 0FFFFFFF0h
0x18001693d  and     rax, rcx
0x180016940  add     rax, r10
0x180016943  jmp     short loc_180016948
0x180016945  mov     rax, r10
0x180016948  xor     rdx, rax
0x18001694b  mov     rcx, rdx; StackCookie
0x18001694e  jmp     __security_check_cookie
```
