# __GSHandlerCheckCommon

- ea: `0x1400183bc`
- end: `0x14001842c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018398`
- `0x140018434`

## callees

- `0x1400183bc`
- `0x1400184b0`

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
0x1400183bc  sub     rsp, 28h
0x1400183c0  mov     eax, [r8]
0x1400183c3  mov     r10, rcx
0x1400183c6  mov     ecx, eax
0x1400183c8  mov     r11, rdx
0x1400183cb  and     ecx, 0FFFFFFF8h
0x1400183ce  test    al, 4
0x1400183d0  jz      short loc_1400183E7
0x1400183d2  mov     eax, [r8+8]
0x1400183d6  movsxd  r9, dword ptr [r8+4]
0x1400183da  neg     eax
0x1400183dc  movsxd  rdx, eax
0x1400183df  add     r9, r10
0x1400183e2  and     r9, rdx
0x1400183e5  jmp     short loc_1400183EA
0x1400183e7  mov     r9, r10
0x1400183ea  movsxd  rax, ecx
0x1400183ed  mov     rdx, [rax+r9]
0x1400183f1  mov     rax, [r11+10h]
0x1400183f5  mov     ecx, [rax+8]
0x1400183f8  mov     rax, [r11+8]
0x1400183fc  movzx   r8d, byte ptr [rcx+rax+3]
0x140018402  test    r8b, 0Fh
0x140018406  jz      short loc_140018418
0x140018408  mov     eax, r8d
0x14001840b  mov     ecx, 0FFFFFFF0h
0x140018410  and     rax, rcx
0x140018413  add     rax, r10
0x140018416  jmp     short loc_14001841B
0x140018418  mov     rax, r10
0x14001841b  xor     rdx, rax
0x14001841e  mov     rcx, rdx; StackCookie
0x140018421  call    __security_check_cookie
0x140018426  add     rsp, 28h
0x14001842a  retn
```
