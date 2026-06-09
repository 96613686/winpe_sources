# __GSHandlerCheckCommon

- ea: `0x14001bb2c`
- end: `0x14001bb9c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001bb08`
- `0x14001bba4`

## callees

- `0x14001bb2c`
- `0x14001bc30`

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
0x14001bb2c  sub     rsp, 28h
0x14001bb30  mov     eax, [r8]
0x14001bb33  mov     r10, rcx
0x14001bb36  mov     ecx, eax
0x14001bb38  mov     r11, rdx
0x14001bb3b  and     ecx, 0FFFFFFF8h
0x14001bb3e  test    al, 4
0x14001bb40  jz      short loc_14001BB57
0x14001bb42  mov     eax, [r8+8]
0x14001bb46  movsxd  r9, dword ptr [r8+4]
0x14001bb4a  neg     eax
0x14001bb4c  movsxd  rdx, eax
0x14001bb4f  add     r9, r10
0x14001bb52  and     r9, rdx
0x14001bb55  jmp     short loc_14001BB5A
0x14001bb57  mov     r9, r10
0x14001bb5a  movsxd  rax, ecx
0x14001bb5d  mov     rdx, [rax+r9]
0x14001bb61  mov     rax, [r11+10h]
0x14001bb65  mov     ecx, [rax+8]
0x14001bb68  mov     rax, [r11+8]
0x14001bb6c  movzx   r8d, byte ptr [rcx+rax+3]
0x14001bb72  test    r8b, 0Fh
0x14001bb76  jz      short loc_14001BB88
0x14001bb78  mov     eax, r8d
0x14001bb7b  mov     ecx, 0FFFFFFF0h
0x14001bb80  and     rax, rcx
0x14001bb83  add     rax, r10
0x14001bb86  jmp     short loc_14001BB8B
0x14001bb88  mov     rax, r10
0x14001bb8b  xor     rdx, rax
0x14001bb8e  mov     rcx, rdx; StackCookie
0x14001bb91  call    __security_check_cookie
0x14001bb96  add     rsp, 28h
0x14001bb9a  retn
```
