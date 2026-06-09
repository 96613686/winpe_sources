# __GSHandlerCheckCommon

- ea: `0x140017450`
- end: `0x1400174b3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001742c`
- `0x1400174bc`

## callees

- `0x140017450`
- `0x1400175a0`

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
0x140017450  mov     r10, rcx
0x140017453  mov     r11, rdx
0x140017456  mov     ecx, [r8]
0x140017459  and     ecx, 0FFFFFFF8h
0x14001745c  test    byte ptr [r8], 4
0x140017460  jz      short loc_140017477
0x140017462  mov     eax, [r8+8]
0x140017466  movsxd  r9, dword ptr [r8+4]
0x14001746a  neg     eax
0x14001746c  movsxd  rdx, eax
0x14001746f  add     r9, r10
0x140017472  and     r9, rdx
0x140017475  jmp     short loc_14001747A
0x140017477  mov     r9, r10
0x14001747a  movsxd  rax, ecx
0x14001747d  mov     rdx, [rax+r9]
0x140017481  mov     rax, [r11+10h]
0x140017485  mov     ecx, [rax+8]
0x140017488  mov     rax, [r11+8]
0x14001748c  test    byte ptr [rcx+rax+3], 0Fh
0x140017491  jz      short loc_1400174A5
0x140017493  movzx   eax, byte ptr [rcx+rax+3]
0x140017498  mov     ecx, 0FFFFFFF0h
0x14001749d  and     rax, rcx
0x1400174a0  add     rax, r10
0x1400174a3  jmp     short loc_1400174A8
0x1400174a5  mov     rax, r10
0x1400174a8  xor     rdx, rax
0x1400174ab  mov     rcx, rdx; StackCookie
0x1400174ae  jmp     __security_check_cookie
```
