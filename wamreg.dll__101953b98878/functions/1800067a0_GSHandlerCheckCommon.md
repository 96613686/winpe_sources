# __GSHandlerCheckCommon

- ea: `0x1800067a0`
- end: `0x180006803`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000677c`

## callees

- `0x1800067a0`
- `0x180006850`

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
0x1800067a0  mov     r10, rcx
0x1800067a3  mov     r11, rdx
0x1800067a6  mov     ecx, [r8]
0x1800067a9  and     ecx, 0FFFFFFF8h
0x1800067ac  test    byte ptr [r8], 4
0x1800067b0  jz      short loc_1800067C7
0x1800067b2  mov     eax, [r8+8]
0x1800067b6  movsxd  r9, dword ptr [r8+4]
0x1800067ba  neg     eax
0x1800067bc  movsxd  rdx, eax
0x1800067bf  add     r9, r10
0x1800067c2  and     r9, rdx
0x1800067c5  jmp     short loc_1800067CA
0x1800067c7  mov     r9, r10
0x1800067ca  movsxd  rax, ecx
0x1800067cd  mov     rdx, [rax+r9]
0x1800067d1  mov     rax, [r11+10h]
0x1800067d5  mov     ecx, [rax+8]
0x1800067d8  mov     rax, [r11+8]
0x1800067dc  test    byte ptr [rcx+rax+3], 0Fh
0x1800067e1  jz      short loc_1800067F5
0x1800067e3  movzx   eax, byte ptr [rcx+rax+3]
0x1800067e8  mov     ecx, 0FFFFFFF0h
0x1800067ed  and     rax, rcx
0x1800067f0  add     rax, r10
0x1800067f3  jmp     short loc_1800067F8
0x1800067f5  mov     rax, r10
0x1800067f8  xor     rdx, rax
0x1800067fb  mov     rcx, rdx; StackCookie
0x1800067fe  jmp     __security_check_cookie
```
