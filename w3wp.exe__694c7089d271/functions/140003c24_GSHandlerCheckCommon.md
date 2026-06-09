# __GSHandlerCheckCommon

- ea: `0x140003c24`
- end: `0x140003c87`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003c00`

## callees

- `0x140003c24`
- `0x140003cc0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x140003c24  mov     r10, rcx
0x140003c27  mov     r11, rdx
0x140003c2a  mov     ecx, [r8]
0x140003c2d  and     ecx, 0FFFFFFF8h
0x140003c30  test    byte ptr [r8], 4
0x140003c34  jz      short loc_140003C4B
0x140003c36  mov     eax, [r8+8]
0x140003c3a  movsxd  r9, dword ptr [r8+4]
0x140003c3e  neg     eax
0x140003c40  movsxd  rdx, eax
0x140003c43  add     r9, r10
0x140003c46  and     r9, rdx
0x140003c49  jmp     short loc_140003C4E
0x140003c4b  mov     r9, r10
0x140003c4e  movsxd  rax, ecx
0x140003c51  mov     rdx, [rax+r9]
0x140003c55  mov     rax, [r11+10h]
0x140003c59  mov     ecx, [rax+8]
0x140003c5c  mov     rax, [r11+8]
0x140003c60  test    byte ptr [rcx+rax+3], 0Fh
0x140003c65  jz      short loc_140003C79
0x140003c67  movzx   eax, byte ptr [rcx+rax+3]
0x140003c6c  mov     ecx, 0FFFFFFF0h
0x140003c71  and     rax, rcx
0x140003c74  add     rax, r10
0x140003c77  jmp     short loc_140003C7C
0x140003c79  mov     rax, r10
0x140003c7c  xor     rdx, rax
0x140003c7f  mov     rcx, rdx; StackCookie
0x140003c82  jmp     __security_check_cookie
```
