# __GSHandlerCheckCommon

- ea: `0x14000f80c`
- end: `0x14000f87c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f7e8`
- `0x14000f884`

## callees

- `0x14000f80c`
- `0x14000f900`

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
0x14000f80c  sub     rsp, 28h
0x14000f810  mov     eax, [r8]
0x14000f813  mov     r10, rcx
0x14000f816  mov     ecx, eax
0x14000f818  mov     r11, rdx
0x14000f81b  and     ecx, 0FFFFFFF8h
0x14000f81e  test    al, 4
0x14000f820  jz      short loc_14000F837
0x14000f822  mov     eax, [r8+8]
0x14000f826  movsxd  r9, dword ptr [r8+4]
0x14000f82a  neg     eax
0x14000f82c  movsxd  rdx, eax
0x14000f82f  add     r9, r10
0x14000f832  and     r9, rdx
0x14000f835  jmp     short loc_14000F83A
0x14000f837  mov     r9, r10
0x14000f83a  movsxd  rax, ecx
0x14000f83d  mov     rdx, [rax+r9]
0x14000f841  mov     rax, [r11+10h]
0x14000f845  mov     ecx, [rax+8]
0x14000f848  mov     rax, [r11+8]
0x14000f84c  movzx   r8d, byte ptr [rcx+rax+3]
0x14000f852  test    r8b, 0Fh
0x14000f856  jz      short loc_14000F868
0x14000f858  mov     eax, r8d
0x14000f85b  mov     ecx, 0FFFFFFF0h
0x14000f860  and     rax, rcx
0x14000f863  add     rax, r10
0x14000f866  jmp     short loc_14000F86B
0x14000f868  mov     rax, r10
0x14000f86b  xor     rdx, rax
0x14000f86e  mov     rcx, rdx; StackCookie
0x14000f871  call    __security_check_cookie
0x14000f876  add     rsp, 28h
0x14000f87a  retn
```
