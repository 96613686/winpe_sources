# __GSHandlerCheckCommon

- ea: `0x14001c850`
- end: `0x14001c8b3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001c82c`
- `0x14001c8bc`

## callees

- `0x140003200`
- `0x14001c850`

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
0x14001c850  mov     r10, rcx
0x14001c853  mov     r11, rdx
0x14001c856  mov     ecx, [r8]
0x14001c859  and     ecx, 0FFFFFFF8h
0x14001c85c  test    byte ptr [r8], 4
0x14001c860  jz      short loc_14001C877
0x14001c862  mov     eax, [r8+8]
0x14001c866  movsxd  r9, dword ptr [r8+4]
0x14001c86a  neg     eax
0x14001c86c  movsxd  rdx, eax
0x14001c86f  add     r9, r10
0x14001c872  and     r9, rdx
0x14001c875  jmp     short loc_14001C87A
0x14001c877  mov     r9, r10
0x14001c87a  movsxd  rax, ecx
0x14001c87d  mov     rdx, [rax+r9]
0x14001c881  mov     rax, [r11+10h]
0x14001c885  mov     ecx, [rax+8]
0x14001c888  mov     rax, [r11+8]
0x14001c88c  test    byte ptr [rcx+rax+3], 0Fh
0x14001c891  jz      short loc_14001C8A5
0x14001c893  movzx   eax, byte ptr [rcx+rax+3]
0x14001c898  mov     ecx, 0FFFFFFF0h
0x14001c89d  and     rax, rcx
0x14001c8a0  add     rax, r10
0x14001c8a3  jmp     short loc_14001C8A8
0x14001c8a5  mov     rax, r10
0x14001c8a8  xor     rdx, rax
0x14001c8ab  mov     rcx, rdx; StackCookie
0x14001c8ae  jmp     __security_check_cookie
```
