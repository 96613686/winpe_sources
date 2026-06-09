# __GSHandlerCheckCommon

- ea: `0x14001145c`
- end: `0x1400114cc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011438`
- `0x1400114d4`

## callees

- `0x14001145c`
- `0x140011560`

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
0x14001145c  sub     rsp, 28h
0x140011460  mov     eax, [r8]
0x140011463  mov     r10, rcx
0x140011466  mov     ecx, eax
0x140011468  mov     r11, rdx
0x14001146b  and     ecx, 0FFFFFFF8h
0x14001146e  test    al, 4
0x140011470  jz      short loc_140011487
0x140011472  mov     eax, [r8+8]
0x140011476  movsxd  r9, dword ptr [r8+4]
0x14001147a  neg     eax
0x14001147c  movsxd  rdx, eax
0x14001147f  add     r9, r10
0x140011482  and     r9, rdx
0x140011485  jmp     short loc_14001148A
0x140011487  mov     r9, r10
0x14001148a  movsxd  rax, ecx
0x14001148d  mov     rdx, [rax+r9]
0x140011491  mov     rax, [r11+10h]
0x140011495  mov     ecx, [rax+8]
0x140011498  mov     rax, [r11+8]
0x14001149c  movzx   r8d, byte ptr [rcx+rax+3]
0x1400114a2  test    r8b, 0Fh
0x1400114a6  jz      short loc_1400114B8
0x1400114a8  mov     eax, r8d
0x1400114ab  mov     ecx, 0FFFFFFF0h
0x1400114b0  and     rax, rcx
0x1400114b3  add     rax, r10
0x1400114b6  jmp     short loc_1400114BB
0x1400114b8  mov     rax, r10
0x1400114bb  xor     rdx, rax
0x1400114be  mov     rcx, rdx; StackCookie
0x1400114c1  call    __security_check_cookie
0x1400114c6  add     rsp, 28h
0x1400114ca  retn
```
