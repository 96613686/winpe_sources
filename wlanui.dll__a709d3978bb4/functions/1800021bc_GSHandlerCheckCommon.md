# __GSHandlerCheckCommon

- ea: `0x1800021bc`
- end: `0x18000221f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002198`
- `0x18001be7c`

## callees

- `0x1800021bc`
- `0x18001bf40`

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
0x1800021bc  mov     r10, rcx
0x1800021bf  mov     r11, rdx
0x1800021c2  mov     ecx, [r8]
0x1800021c5  and     ecx, 0FFFFFFF8h
0x1800021c8  test    byte ptr [r8], 4
0x1800021cc  jz      short loc_1800021E3
0x1800021ce  mov     eax, [r8+8]
0x1800021d2  movsxd  r9, dword ptr [r8+4]
0x1800021d6  neg     eax
0x1800021d8  movsxd  rdx, eax
0x1800021db  add     r9, r10
0x1800021de  and     r9, rdx
0x1800021e1  jmp     short loc_1800021E6
0x1800021e3  mov     r9, r10
0x1800021e6  movsxd  rax, ecx
0x1800021e9  mov     rdx, [rax+r9]
0x1800021ed  mov     rax, [r11+10h]
0x1800021f1  mov     ecx, [rax+8]
0x1800021f4  mov     rax, [r11+8]
0x1800021f8  test    byte ptr [rcx+rax+3], 0Fh
0x1800021fd  jz      short loc_180002211
0x1800021ff  movzx   eax, byte ptr [rcx+rax+3]
0x180002204  mov     ecx, 0FFFFFFF0h
0x180002209  and     rax, rcx
0x18000220c  add     rax, r10
0x18000220f  jmp     short loc_180002214
0x180002211  mov     rax, r10
0x180002214  xor     rdx, rax
0x180002217  mov     rcx, rdx; StackCookie
0x18000221a  jmp     __security_check_cookie
```
