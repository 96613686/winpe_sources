# __GSHandlerCheckCommon

- ea: `0x180015c0c`
- end: `0x180015c67`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015be8`

## callees

- `0x180015660`
- `0x180015c0c`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x180015c0c  push    rbx
0x180015c0e  mov     r11d, [r8]
0x180015c11  mov     rbx, rdx
0x180015c14  and     r11d, 0FFFFFFF8h
0x180015c18  mov     r9, rcx
0x180015c1b  test    byte ptr [r8], 4
0x180015c1f  mov     r10, rcx
0x180015c22  jz      short loc_180015C37
0x180015c24  mov     eax, [r8+8]
0x180015c28  movsxd  r10, dword ptr [r8+4]
0x180015c2c  neg     eax
0x180015c2e  add     r10, rcx
0x180015c31  movsxd  rcx, eax
0x180015c34  and     r10, rcx
0x180015c37  movsxd  rax, r11d
0x180015c3a  mov     rdx, [rax+r10]
0x180015c3e  mov     rax, [rbx+10h]
0x180015c42  mov     ecx, [rax+8]
0x180015c45  mov     rax, [rbx+8]
0x180015c49  test    byte ptr [rcx+rax+3], 0Fh
0x180015c4e  jz      short loc_180015C5B
0x180015c50  movzx   eax, byte ptr [rcx+rax+3]
0x180015c55  and     eax, 0FFFFFFF0h
0x180015c58  add     r9, rax
0x180015c5b  xor     r9, rdx
0x180015c5e  mov     rcx, r9; StackCookie
0x180015c61  pop     rbx
0x180015c62  jmp     __security_check_cookie
```
