# __GSHandlerCheckCommon

- ea: `0x180015710`
- end: `0x180015770`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800156ec`
- `0x180015854`
- `0x1800158f8`

## callees

- `0x18000fce0`
- `0x180015710`

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
0x180015710  push    rbx
0x180015712  mov     r11d, [r8]
0x180015715  mov     rbx, rdx
0x180015718  and     r11d, 0FFFFFFF8h
0x18001571c  mov     r9, rcx
0x18001571f  test    byte ptr [r8], 4
0x180015723  mov     r10, rcx
0x180015726  jz      short loc_18001573B
0x180015728  mov     eax, [r8+8]
0x18001572c  movsxd  r10, dword ptr [r8+4]
0x180015730  neg     eax
0x180015732  add     r10, rcx
0x180015735  movsxd  rcx, eax
0x180015738  and     r10, rcx
0x18001573b  movsxd  rax, r11d
0x18001573e  mov     rdx, [rax+r10]
0x180015742  mov     rax, [rbx+10h]
0x180015746  mov     ecx, [rax+8]
0x180015749  mov     rax, [rbx+8]
0x18001574d  test    byte ptr [rcx+rax+3], 0Fh
0x180015752  jz      short loc_180015764
0x180015754  movzx   eax, byte ptr [rcx+rax+3]
0x180015759  mov     ecx, 0FFFFFFF0h
0x18001575e  and     rax, rcx
0x180015761  add     r9, rax
0x180015764  xor     r9, rdx
0x180015767  mov     rcx, r9; StackCookie
0x18001576a  pop     rbx
0x18001576b  jmp     __security_check_cookie
```
