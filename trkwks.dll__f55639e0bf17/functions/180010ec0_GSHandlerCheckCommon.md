# __GSHandlerCheckCommon

- ea: `0x180010ec0`
- end: `0x180010f23`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010e9c`
- `0x180010f2c`

## callees

- `0x180010ec0`
- `0x180011000`

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
0x180010ec0  mov     r10, rcx
0x180010ec3  mov     r11, rdx
0x180010ec6  mov     ecx, [r8]
0x180010ec9  and     ecx, 0FFFFFFF8h
0x180010ecc  test    byte ptr [r8], 4
0x180010ed0  jz      short loc_180010EE7
0x180010ed2  mov     eax, [r8+8]
0x180010ed6  movsxd  r9, dword ptr [r8+4]
0x180010eda  neg     eax
0x180010edc  movsxd  rdx, eax
0x180010edf  add     r9, r10
0x180010ee2  and     r9, rdx
0x180010ee5  jmp     short loc_180010EEA
0x180010ee7  mov     r9, r10
0x180010eea  movsxd  rax, ecx
0x180010eed  mov     rdx, [rax+r9]
0x180010ef1  mov     rax, [r11+10h]
0x180010ef5  mov     ecx, [rax+8]
0x180010ef8  mov     rax, [r11+8]
0x180010efc  test    byte ptr [rcx+rax+3], 0Fh
0x180010f01  jz      short loc_180010F15
0x180010f03  movzx   eax, byte ptr [rcx+rax+3]
0x180010f08  mov     ecx, 0FFFFFFF0h
0x180010f0d  and     rax, rcx
0x180010f10  add     rax, r10
0x180010f13  jmp     short loc_180010F18
0x180010f15  mov     rax, r10
0x180010f18  xor     rdx, rax
0x180010f1b  mov     rcx, rdx; StackCookie
0x180010f1e  jmp     __security_check_cookie
```
