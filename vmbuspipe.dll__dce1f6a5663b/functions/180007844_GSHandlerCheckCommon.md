# __GSHandlerCheckCommon

- ea: `0x180007844`
- end: `0x1800078a7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007820`
- `0x1800078b0`

## callees

- `0x1800024e0`
- `0x180007844`

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
0x180007844  mov     r10, rcx
0x180007847  mov     r11, rdx
0x18000784a  mov     ecx, [r8]
0x18000784d  and     ecx, 0FFFFFFF8h
0x180007850  test    byte ptr [r8], 4
0x180007854  jz      short loc_18000786B
0x180007856  mov     eax, [r8+8]
0x18000785a  movsxd  r9, dword ptr [r8+4]
0x18000785e  neg     eax
0x180007860  movsxd  rdx, eax
0x180007863  add     r9, r10
0x180007866  and     r9, rdx
0x180007869  jmp     short loc_18000786E
0x18000786b  mov     r9, r10
0x18000786e  movsxd  rax, ecx
0x180007871  mov     rdx, [rax+r9]
0x180007875  mov     rax, [r11+10h]
0x180007879  mov     ecx, [rax+8]
0x18000787c  mov     rax, [r11+8]
0x180007880  test    byte ptr [rcx+rax+3], 0Fh
0x180007885  jz      short loc_180007899
0x180007887  movzx   eax, byte ptr [rcx+rax+3]
0x18000788c  mov     ecx, 0FFFFFFF0h
0x180007891  and     rax, rcx
0x180007894  add     rax, r10
0x180007897  jmp     short loc_18000789C
0x180007899  mov     rax, r10
0x18000789c  xor     rdx, rax
0x18000789f  mov     rcx, rdx; StackCookie
0x1800078a2  jmp     __security_check_cookie
```
