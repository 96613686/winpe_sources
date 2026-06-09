# __GSHandlerCheckCommon

- ea: `0x14001cb5c`
- end: `0x14001cbcc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001cb38`

## callees

- `0x14001cb5c`
- `0x14001cdf0`

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
0x14001cb5c  sub     rsp, 28h
0x14001cb60  mov     eax, [r8]
0x14001cb63  mov     r10, rcx
0x14001cb66  mov     ecx, eax
0x14001cb68  mov     r11, rdx
0x14001cb6b  and     ecx, 0FFFFFFF8h
0x14001cb6e  test    al, 4
0x14001cb70  jz      short loc_14001CB87
0x14001cb72  mov     eax, [r8+8]
0x14001cb76  movsxd  r9, dword ptr [r8+4]
0x14001cb7a  neg     eax
0x14001cb7c  movsxd  rdx, eax
0x14001cb7f  add     r9, r10
0x14001cb82  and     r9, rdx
0x14001cb85  jmp     short loc_14001CB8A
0x14001cb87  mov     r9, r10
0x14001cb8a  movsxd  rax, ecx
0x14001cb8d  mov     rdx, [rax+r9]
0x14001cb91  mov     rax, [r11+10h]
0x14001cb95  mov     ecx, [rax+8]
0x14001cb98  mov     rax, [r11+8]
0x14001cb9c  movzx   r8d, byte ptr [rcx+rax+3]
0x14001cba2  test    r8b, 0Fh
0x14001cba6  jz      short loc_14001CBB8
0x14001cba8  mov     eax, r8d
0x14001cbab  mov     ecx, 0FFFFFFF0h
0x14001cbb0  and     rax, rcx
0x14001cbb3  add     rax, r10
0x14001cbb6  jmp     short loc_14001CBBB
0x14001cbb8  mov     rax, r10
0x14001cbbb  xor     rdx, rax
0x14001cbbe  mov     rcx, rdx; StackCookie
0x14001cbc1  call    __security_check_cookie
0x14001cbc6  add     rsp, 28h
0x14001cbca  retn
```
