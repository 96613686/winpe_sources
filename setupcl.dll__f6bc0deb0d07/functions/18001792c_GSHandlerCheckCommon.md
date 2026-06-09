# __GSHandlerCheckCommon

- ea: `0x18001792c`
- end: `0x18001798f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017908`

## callees

- `0x18001792c`
- `0x1800179e0`

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
0x18001792c  mov     r10, rcx
0x18001792f  mov     r11, rdx
0x180017932  mov     ecx, [r8]
0x180017935  and     ecx, 0FFFFFFF8h
0x180017938  test    byte ptr [r8], 4
0x18001793c  jz      short loc_180017953
0x18001793e  mov     eax, [r8+8]
0x180017942  movsxd  r9, dword ptr [r8+4]
0x180017946  neg     eax
0x180017948  movsxd  rdx, eax
0x18001794b  add     r9, r10
0x18001794e  and     r9, rdx
0x180017951  jmp     short loc_180017956
0x180017953  mov     r9, r10
0x180017956  movsxd  rax, ecx
0x180017959  mov     rdx, [rax+r9]
0x18001795d  mov     rax, [r11+10h]
0x180017961  mov     ecx, [rax+8]
0x180017964  mov     rax, [r11+8]
0x180017968  test    byte ptr [rcx+rax+3], 0Fh
0x18001796d  jz      short loc_180017981
0x18001796f  movzx   eax, byte ptr [rcx+rax+3]
0x180017974  mov     ecx, 0FFFFFFF0h
0x180017979  and     rax, rcx
0x18001797c  add     rax, r10
0x18001797f  jmp     short loc_180017984
0x180017981  mov     rax, r10
0x180017984  xor     rdx, rax
0x180017987  mov     rcx, rdx; StackCookie
0x18001798a  jmp     __security_check_cookie
```
