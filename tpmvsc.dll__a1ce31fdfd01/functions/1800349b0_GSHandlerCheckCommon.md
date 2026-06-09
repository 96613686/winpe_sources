# __GSHandlerCheckCommon

- ea: `0x1800349b0`
- end: `0x180034a13`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003498c`
- `0x180034a1c`

## callees

- `0x180001ec0`
- `0x1800349b0`

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
0x1800349b0  mov     r10, rcx
0x1800349b3  mov     r11, rdx
0x1800349b6  mov     ecx, [r8]
0x1800349b9  and     ecx, 0FFFFFFF8h
0x1800349bc  test    byte ptr [r8], 4
0x1800349c0  jz      short loc_1800349D7
0x1800349c2  mov     eax, [r8+8]
0x1800349c6  movsxd  r9, dword ptr [r8+4]
0x1800349ca  neg     eax
0x1800349cc  movsxd  rdx, eax
0x1800349cf  add     r9, r10
0x1800349d2  and     r9, rdx
0x1800349d5  jmp     short loc_1800349DA
0x1800349d7  mov     r9, r10
0x1800349da  movsxd  rax, ecx
0x1800349dd  mov     rdx, [rax+r9]
0x1800349e1  mov     rax, [r11+10h]
0x1800349e5  mov     ecx, [rax+8]
0x1800349e8  mov     rax, [r11+8]
0x1800349ec  test    byte ptr [rcx+rax+3], 0Fh
0x1800349f1  jz      short loc_180034A05
0x1800349f3  movzx   eax, byte ptr [rcx+rax+3]
0x1800349f8  mov     ecx, 0FFFFFFF0h
0x1800349fd  and     rax, rcx
0x180034a00  add     rax, r10
0x180034a03  jmp     short loc_180034A08
0x180034a05  mov     rax, r10
0x180034a08  xor     rdx, rax
0x180034a0b  mov     rcx, rdx; StackCookie
0x180034a0e  jmp     __security_check_cookie
```
