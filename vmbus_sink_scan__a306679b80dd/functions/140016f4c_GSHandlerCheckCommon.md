# __GSHandlerCheckCommon

- ea: `0x140016f4c`
- end: `0x140016fbc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140016f28`

## callees

- `0x140016f4c`
- `0x140017000`

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
0x140016f4c  sub     rsp, 28h
0x140016f50  mov     eax, [r8]
0x140016f53  mov     r10, rcx
0x140016f56  mov     ecx, eax
0x140016f58  mov     r11, rdx
0x140016f5b  and     ecx, 0FFFFFFF8h
0x140016f5e  test    al, 4
0x140016f60  jz      short loc_140016F77
0x140016f62  mov     eax, [r8+8]
0x140016f66  movsxd  r9, dword ptr [r8+4]
0x140016f6a  neg     eax
0x140016f6c  movsxd  rdx, eax
0x140016f6f  add     r9, r10
0x140016f72  and     r9, rdx
0x140016f75  jmp     short loc_140016F7A
0x140016f77  mov     r9, r10
0x140016f7a  movsxd  rax, ecx
0x140016f7d  mov     rdx, [rax+r9]
0x140016f81  mov     rax, [r11+10h]
0x140016f85  mov     ecx, [rax+8]
0x140016f88  mov     rax, [r11+8]
0x140016f8c  movzx   r8d, byte ptr [rcx+rax+3]
0x140016f92  test    r8b, 0Fh
0x140016f96  jz      short loc_140016FA8
0x140016f98  mov     eax, r8d
0x140016f9b  mov     ecx, 0FFFFFFF0h
0x140016fa0  and     rax, rcx
0x140016fa3  add     rax, r10
0x140016fa6  jmp     short loc_140016FAB
0x140016fa8  mov     rax, r10
0x140016fab  xor     rdx, rax
0x140016fae  mov     rcx, rdx; StackCookie
0x140016fb1  call    __security_check_cookie
0x140016fb6  add     rsp, 28h
0x140016fba  retn
```
