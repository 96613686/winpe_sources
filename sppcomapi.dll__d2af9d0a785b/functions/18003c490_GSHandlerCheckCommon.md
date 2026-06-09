# __GSHandlerCheckCommon

- ea: `0x18003c490`
- end: `0x18003c4f3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c46c`

## callees

- `0x18003c490`
- `0x18003c560`

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
0x18003c490  mov     r10, rcx
0x18003c493  mov     r11, rdx
0x18003c496  mov     ecx, [r8]
0x18003c499  and     ecx, 0FFFFFFF8h
0x18003c49c  test    byte ptr [r8], 4
0x18003c4a0  jz      short loc_18003C4B7
0x18003c4a2  mov     eax, [r8+8]
0x18003c4a6  movsxd  r9, dword ptr [r8+4]
0x18003c4aa  neg     eax
0x18003c4ac  movsxd  rdx, eax
0x18003c4af  add     r9, r10
0x18003c4b2  and     r9, rdx
0x18003c4b5  jmp     short loc_18003C4BA
0x18003c4b7  mov     r9, r10
0x18003c4ba  movsxd  rax, ecx
0x18003c4bd  mov     rdx, [rax+r9]
0x18003c4c1  mov     rax, [r11+10h]
0x18003c4c5  mov     ecx, [rax+8]
0x18003c4c8  mov     rax, [r11+8]
0x18003c4cc  test    byte ptr [rcx+rax+3], 0Fh
0x18003c4d1  jz      short loc_18003C4E5
0x18003c4d3  movzx   eax, byte ptr [rcx+rax+3]
0x18003c4d8  mov     ecx, 0FFFFFFF0h
0x18003c4dd  and     rax, rcx
0x18003c4e0  add     rax, r10
0x18003c4e3  jmp     short loc_18003C4E8
0x18003c4e5  mov     rax, r10
0x18003c4e8  xor     rdx, rax
0x18003c4eb  mov     rcx, rdx; StackCookie
0x18003c4ee  jmp     __security_check_cookie
```
