# __GSHandlerCheckCommon

- ea: `0x1400023dc`
- end: `0x14000244c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400023b8`
- `0x140002454`

## callees

- `0x1400023dc`
- `0x1400024e0`

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
0x1400023dc  sub     rsp, 28h
0x1400023e0  mov     eax, [r8]
0x1400023e3  mov     r10, rcx
0x1400023e6  mov     ecx, eax
0x1400023e8  mov     r11, rdx
0x1400023eb  and     ecx, 0FFFFFFF8h
0x1400023ee  test    al, 4
0x1400023f0  jz      short loc_140002407
0x1400023f2  mov     eax, [r8+8]
0x1400023f6  movsxd  r9, dword ptr [r8+4]
0x1400023fa  neg     eax
0x1400023fc  movsxd  rdx, eax
0x1400023ff  add     r9, r10
0x140002402  and     r9, rdx
0x140002405  jmp     short loc_14000240A
0x140002407  mov     r9, r10
0x14000240a  movsxd  rax, ecx
0x14000240d  mov     rdx, [rax+r9]
0x140002411  mov     rax, [r11+10h]
0x140002415  mov     ecx, [rax+8]
0x140002418  mov     rax, [r11+8]
0x14000241c  movzx   r8d, byte ptr [rcx+rax+3]
0x140002422  test    r8b, 0Fh
0x140002426  jz      short loc_140002438
0x140002428  mov     eax, r8d
0x14000242b  mov     ecx, 0FFFFFFF0h
0x140002430  and     rax, rcx
0x140002433  add     rax, r10
0x140002436  jmp     short loc_14000243B
0x140002438  mov     rax, r10
0x14000243b  xor     rdx, rax
0x14000243e  mov     rcx, rdx; StackCookie
0x140002441  call    __security_check_cookie
0x140002446  add     rsp, 28h
0x14000244a  retn
```
