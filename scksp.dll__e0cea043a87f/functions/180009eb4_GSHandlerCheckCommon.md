# __GSHandlerCheckCommon

- ea: `0x180009eb4`
- end: `0x180009f17`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009e90`
- `0x18003c188`

## callees

- `0x180009eb4`
- `0x18003c240`

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
0x180009eb4  mov     r10, rcx
0x180009eb7  mov     r11, rdx
0x180009eba  mov     ecx, [r8]
0x180009ebd  and     ecx, 0FFFFFFF8h
0x180009ec0  test    byte ptr [r8], 4
0x180009ec4  jz      short loc_180009EDB
0x180009ec6  mov     eax, [r8+8]
0x180009eca  movsxd  r9, dword ptr [r8+4]
0x180009ece  neg     eax
0x180009ed0  movsxd  rdx, eax
0x180009ed3  add     r9, r10
0x180009ed6  and     r9, rdx
0x180009ed9  jmp     short loc_180009EDE
0x180009edb  mov     r9, r10
0x180009ede  movsxd  rax, ecx
0x180009ee1  mov     rdx, [rax+r9]
0x180009ee5  mov     rax, [r11+10h]
0x180009ee9  mov     ecx, [rax+8]
0x180009eec  mov     rax, [r11+8]
0x180009ef0  test    byte ptr [rcx+rax+3], 0Fh
0x180009ef5  jz      short loc_180009F09
0x180009ef7  movzx   eax, byte ptr [rcx+rax+3]
0x180009efc  mov     ecx, 0FFFFFFF0h
0x180009f01  and     rax, rcx
0x180009f04  add     rax, r10
0x180009f07  jmp     short loc_180009F0C
0x180009f09  mov     rax, r10
0x180009f0c  xor     rdx, rax
0x180009f0f  mov     rcx, rdx; StackCookie
0x180009f12  jmp     __security_check_cookie
```
