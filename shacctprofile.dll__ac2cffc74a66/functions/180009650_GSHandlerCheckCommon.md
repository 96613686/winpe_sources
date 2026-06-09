# __GSHandlerCheckCommon

- ea: `0x180009650`
- end: `0x1800096b3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000962c`

## callees

- `0x180002230`
- `0x180009650`

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
0x180009650  mov     r10, rcx
0x180009653  mov     r11, rdx
0x180009656  mov     ecx, [r8]
0x180009659  and     ecx, 0FFFFFFF8h
0x18000965c  test    byte ptr [r8], 4
0x180009660  jz      short loc_180009677
0x180009662  mov     eax, [r8+8]
0x180009666  movsxd  r9, dword ptr [r8+4]
0x18000966a  neg     eax
0x18000966c  movsxd  rdx, eax
0x18000966f  add     r9, r10
0x180009672  and     r9, rdx
0x180009675  jmp     short loc_18000967A
0x180009677  mov     r9, r10
0x18000967a  movsxd  rax, ecx
0x18000967d  mov     rdx, [rax+r9]
0x180009681  mov     rax, [r11+10h]
0x180009685  mov     ecx, [rax+8]
0x180009688  mov     rax, [r11+8]
0x18000968c  test    byte ptr [rcx+rax+3], 0Fh
0x180009691  jz      short loc_1800096A5
0x180009693  movzx   eax, byte ptr [rcx+rax+3]
0x180009698  mov     ecx, 0FFFFFFF0h
0x18000969d  and     rax, rcx
0x1800096a0  add     rax, r10
0x1800096a3  jmp     short loc_1800096A8
0x1800096a5  mov     rax, r10
0x1800096a8  xor     rdx, rax
0x1800096ab  mov     rcx, rdx; StackCookie
0x1800096ae  jmp     __security_check_cookie
```
