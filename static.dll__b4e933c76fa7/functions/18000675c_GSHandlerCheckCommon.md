# __GSHandlerCheckCommon

- ea: `0x18000675c`
- end: `0x1800067bf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006738`

## callees

- `0x18000675c`
- `0x180006810`

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
0x18000675c  mov     r10, rcx
0x18000675f  mov     r11, rdx
0x180006762  mov     ecx, [r8]
0x180006765  and     ecx, 0FFFFFFF8h
0x180006768  test    byte ptr [r8], 4
0x18000676c  jz      short loc_180006783
0x18000676e  mov     eax, [r8+8]
0x180006772  movsxd  r9, dword ptr [r8+4]
0x180006776  neg     eax
0x180006778  movsxd  rdx, eax
0x18000677b  add     r9, r10
0x18000677e  and     r9, rdx
0x180006781  jmp     short loc_180006786
0x180006783  mov     r9, r10
0x180006786  movsxd  rax, ecx
0x180006789  mov     rdx, [rax+r9]
0x18000678d  mov     rax, [r11+10h]
0x180006791  mov     ecx, [rax+8]
0x180006794  mov     rax, [r11+8]
0x180006798  test    byte ptr [rcx+rax+3], 0Fh
0x18000679d  jz      short loc_1800067B1
0x18000679f  movzx   eax, byte ptr [rcx+rax+3]
0x1800067a4  mov     ecx, 0FFFFFFF0h
0x1800067a9  and     rax, rcx
0x1800067ac  add     rax, r10
0x1800067af  jmp     short loc_1800067B4
0x1800067b1  mov     rax, r10
0x1800067b4  xor     rdx, rax
0x1800067b7  mov     rcx, rdx; StackCookie
0x1800067ba  jmp     __security_check_cookie
```
