# __GSHandlerCheckCommon

- ea: `0x180015890`
- end: `0x1800158f3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001586c`

## callees

- `0x180001dc0`
- `0x180015890`

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
0x180015890  mov     r10, rcx
0x180015893  mov     r11, rdx
0x180015896  mov     ecx, [r8]
0x180015899  and     ecx, 0FFFFFFF8h
0x18001589c  test    byte ptr [r8], 4
0x1800158a0  jz      short loc_1800158B7
0x1800158a2  mov     eax, [r8+8]
0x1800158a6  movsxd  r9, dword ptr [r8+4]
0x1800158aa  neg     eax
0x1800158ac  movsxd  rdx, eax
0x1800158af  add     r9, r10
0x1800158b2  and     r9, rdx
0x1800158b5  jmp     short loc_1800158BA
0x1800158b7  mov     r9, r10
0x1800158ba  movsxd  rax, ecx
0x1800158bd  mov     rdx, [rax+r9]
0x1800158c1  mov     rax, [r11+10h]
0x1800158c5  mov     ecx, [rax+8]
0x1800158c8  mov     rax, [r11+8]
0x1800158cc  test    byte ptr [rcx+rax+3], 0Fh
0x1800158d1  jz      short loc_1800158E5
0x1800158d3  movzx   eax, byte ptr [rcx+rax+3]
0x1800158d8  mov     ecx, 0FFFFFFF0h
0x1800158dd  and     rax, rcx
0x1800158e0  add     rax, r10
0x1800158e3  jmp     short loc_1800158E8
0x1800158e5  mov     rax, r10
0x1800158e8  xor     rdx, rax
0x1800158eb  mov     rcx, rdx; StackCookie
0x1800158ee  jmp     __security_check_cookie
```
