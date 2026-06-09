# __GSHandlerCheckCommon

- ea: `0x14001f1ec`
- end: `0x14001f25c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001f1c8`

## callees

- `0x14001f1ec`
- `0x14001f320`

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
0x14001f1ec  sub     rsp, 28h
0x14001f1f0  mov     eax, [r8]
0x14001f1f3  mov     r10, rcx
0x14001f1f6  mov     ecx, eax
0x14001f1f8  mov     r11, rdx
0x14001f1fb  and     ecx, 0FFFFFFF8h
0x14001f1fe  test    al, 4
0x14001f200  jz      short loc_14001F217
0x14001f202  mov     eax, [r8+8]
0x14001f206  movsxd  r9, dword ptr [r8+4]
0x14001f20a  neg     eax
0x14001f20c  movsxd  rdx, eax
0x14001f20f  add     r9, r10
0x14001f212  and     r9, rdx
0x14001f215  jmp     short loc_14001F21A
0x14001f217  mov     r9, r10
0x14001f21a  movsxd  rax, ecx
0x14001f21d  mov     rdx, [rax+r9]
0x14001f221  mov     rax, [r11+10h]
0x14001f225  mov     ecx, [rax+8]
0x14001f228  mov     rax, [r11+8]
0x14001f22c  movzx   r8d, byte ptr [rcx+rax+3]
0x14001f232  test    r8b, 0Fh
0x14001f236  jz      short loc_14001F248
0x14001f238  mov     eax, r8d
0x14001f23b  mov     ecx, 0FFFFFFF0h
0x14001f240  and     rax, rcx
0x14001f243  add     rax, r10
0x14001f246  jmp     short loc_14001F24B
0x14001f248  mov     rax, r10
0x14001f24b  xor     rdx, rax
0x14001f24e  mov     rcx, rdx; StackCookie
0x14001f251  call    __security_check_cookie
0x14001f256  add     rsp, 28h
0x14001f25a  retn
```
