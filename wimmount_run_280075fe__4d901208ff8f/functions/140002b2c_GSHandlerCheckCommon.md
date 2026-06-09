# __GSHandlerCheckCommon

- ea: `0x140002b2c`
- end: `0x140002b9c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002b08`

## callees

- `0x140002b2c`
- `0x140002bb0`

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
0x140002b2c  sub     rsp, 28h
0x140002b30  mov     eax, [r8]
0x140002b33  mov     r10, rcx
0x140002b36  mov     ecx, eax
0x140002b38  mov     r11, rdx
0x140002b3b  and     ecx, 0FFFFFFF8h
0x140002b3e  test    al, 4
0x140002b40  jz      short loc_140002B57
0x140002b42  mov     eax, [r8+8]
0x140002b46  movsxd  r9, dword ptr [r8+4]
0x140002b4a  neg     eax
0x140002b4c  movsxd  rdx, eax
0x140002b4f  add     r9, r10
0x140002b52  and     r9, rdx
0x140002b55  jmp     short loc_140002B5A
0x140002b57  mov     r9, r10
0x140002b5a  movsxd  rax, ecx
0x140002b5d  mov     rdx, [rax+r9]
0x140002b61  mov     rax, [r11+10h]
0x140002b65  mov     ecx, [rax+8]
0x140002b68  mov     rax, [r11+8]
0x140002b6c  movzx   r8d, byte ptr [rcx+rax+3]
0x140002b72  test    r8b, 0Fh
0x140002b76  jz      short loc_140002B88
0x140002b78  mov     eax, r8d
0x140002b7b  mov     ecx, 0FFFFFFF0h
0x140002b80  and     rax, rcx
0x140002b83  add     rax, r10
0x140002b86  jmp     short loc_140002B8B
0x140002b88  mov     rax, r10
0x140002b8b  xor     rdx, rax
0x140002b8e  mov     rcx, rdx; StackCookie
0x140002b91  call    __security_check_cookie
0x140002b96  add     rsp, 28h
0x140002b9a  retn
```
