# __GSHandlerCheckCommon

- ea: `0x14001ecac`
- end: `0x14001ed1c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001ec88`

## callees

- `0x14001ecac`
- `0x14001ede0`

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
0x14001ecac  sub     rsp, 28h
0x14001ecb0  mov     eax, [r8]
0x14001ecb3  mov     r10, rcx
0x14001ecb6  mov     ecx, eax
0x14001ecb8  mov     r11, rdx
0x14001ecbb  and     ecx, 0FFFFFFF8h
0x14001ecbe  test    al, 4
0x14001ecc0  jz      short loc_14001ECD7
0x14001ecc2  mov     eax, [r8+8]
0x14001ecc6  movsxd  r9, dword ptr [r8+4]
0x14001ecca  neg     eax
0x14001eccc  movsxd  rdx, eax
0x14001eccf  add     r9, r10
0x14001ecd2  and     r9, rdx
0x14001ecd5  jmp     short loc_14001ECDA
0x14001ecd7  mov     r9, r10
0x14001ecda  movsxd  rax, ecx
0x14001ecdd  mov     rdx, [rax+r9]
0x14001ece1  mov     rax, [r11+10h]
0x14001ece5  mov     ecx, [rax+8]
0x14001ece8  mov     rax, [r11+8]
0x14001ecec  movzx   r8d, byte ptr [rcx+rax+3]
0x14001ecf2  test    r8b, 0Fh
0x14001ecf6  jz      short loc_14001ED08
0x14001ecf8  mov     eax, r8d
0x14001ecfb  mov     ecx, 0FFFFFFF0h
0x14001ed00  and     rax, rcx
0x14001ed03  add     rax, r10
0x14001ed06  jmp     short loc_14001ED0B
0x14001ed08  mov     rax, r10
0x14001ed0b  xor     rdx, rax
0x14001ed0e  mov     rcx, rdx; StackCookie
0x14001ed11  call    __security_check_cookie
0x14001ed16  add     rsp, 28h
0x14001ed1a  retn
```
