# __GSHandlerCheckCommon

- ea: `0x180015f98`
- end: `0x180015ff3`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015f74`

## callees

- `0x180015f98`
- `0x180016020`

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
0x180015f98  push    rbx
0x180015f9a  mov     r11d, [r8]
0x180015f9d  mov     rbx, rdx
0x180015fa0  and     r11d, 0FFFFFFF8h
0x180015fa4  mov     r9, rcx
0x180015fa7  test    byte ptr [r8], 4
0x180015fab  mov     r10, rcx
0x180015fae  jz      short loc_180015FC3
0x180015fb0  mov     eax, [r8+8]
0x180015fb4  movsxd  r10, dword ptr [r8+4]
0x180015fb8  neg     eax
0x180015fba  add     r10, rcx
0x180015fbd  movsxd  rcx, eax
0x180015fc0  and     r10, rcx
0x180015fc3  movsxd  rax, r11d
0x180015fc6  mov     rdx, [rax+r10]
0x180015fca  mov     rax, [rbx+10h]
0x180015fce  mov     ecx, [rax+8]
0x180015fd1  mov     rax, [rbx+8]
0x180015fd5  test    byte ptr [rcx+rax+3], 0Fh
0x180015fda  jz      short loc_180015FE7
0x180015fdc  movzx   eax, byte ptr [rcx+rax+3]
0x180015fe1  and     eax, 0FFFFFFF0h
0x180015fe4  add     r9, rax
0x180015fe7  xor     r9, rdx
0x180015fea  mov     rcx, r9; StackCookie
0x180015fed  pop     rbx
0x180015fee  jmp     __security_check_cookie
```
