# __GSHandlerCheckCommon

- ea: `0x18002209c`
- end: `0x1800220ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022078`
- `0x180022108`

## callees

- `0x18002209c`
- `0x180022190`

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
0x18002209c  mov     r10, rcx
0x18002209f  mov     r11, rdx
0x1800220a2  mov     ecx, [r8]
0x1800220a5  and     ecx, 0FFFFFFF8h
0x1800220a8  test    byte ptr [r8], 4
0x1800220ac  jz      short loc_1800220C3
0x1800220ae  mov     eax, [r8+8]
0x1800220b2  movsxd  r9, dword ptr [r8+4]
0x1800220b6  neg     eax
0x1800220b8  movsxd  rdx, eax
0x1800220bb  add     r9, r10
0x1800220be  and     r9, rdx
0x1800220c1  jmp     short loc_1800220C6
0x1800220c3  mov     r9, r10
0x1800220c6  movsxd  rax, ecx
0x1800220c9  mov     rdx, [rax+r9]
0x1800220cd  mov     rax, [r11+10h]
0x1800220d1  mov     ecx, [rax+8]
0x1800220d4  mov     rax, [r11+8]
0x1800220d8  test    byte ptr [rcx+rax+3], 0Fh
0x1800220dd  jz      short loc_1800220F1
0x1800220df  movzx   eax, byte ptr [rcx+rax+3]
0x1800220e4  mov     ecx, 0FFFFFFF0h
0x1800220e9  and     rax, rcx
0x1800220ec  add     rax, r10
0x1800220ef  jmp     short loc_1800220F4
0x1800220f1  mov     rax, r10
0x1800220f4  xor     rdx, rax
0x1800220f7  mov     rcx, rdx; StackCookie
0x1800220fa  jmp     __security_check_cookie
```
