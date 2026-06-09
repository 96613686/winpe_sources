# __GSHandlerCheckCommon

- ea: `0x14001cb2c`
- end: `0x14001cb8f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001cb08`
- `0x14001cb98`

## callees

- `0x14001cb2c`
- `0x14001cc40`

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
0x14001cb2c  mov     r10, rcx
0x14001cb2f  mov     r11, rdx
0x14001cb32  mov     ecx, [r8]
0x14001cb35  and     ecx, 0FFFFFFF8h
0x14001cb38  test    byte ptr [r8], 4
0x14001cb3c  jz      short loc_14001CB53
0x14001cb3e  mov     eax, [r8+8]
0x14001cb42  movsxd  r9, dword ptr [r8+4]
0x14001cb46  neg     eax
0x14001cb48  movsxd  rdx, eax
0x14001cb4b  add     r9, r10
0x14001cb4e  and     r9, rdx
0x14001cb51  jmp     short loc_14001CB56
0x14001cb53  mov     r9, r10
0x14001cb56  movsxd  rax, ecx
0x14001cb59  mov     rdx, [rax+r9]
0x14001cb5d  mov     rax, [r11+10h]
0x14001cb61  mov     ecx, [rax+8]
0x14001cb64  mov     rax, [r11+8]
0x14001cb68  test    byte ptr [rcx+rax+3], 0Fh
0x14001cb6d  jz      short loc_14001CB81
0x14001cb6f  movzx   eax, byte ptr [rcx+rax+3]
0x14001cb74  mov     ecx, 0FFFFFFF0h
0x14001cb79  and     rax, rcx
0x14001cb7c  add     rax, r10
0x14001cb7f  jmp     short loc_14001CB84
0x14001cb81  mov     rax, r10
0x14001cb84  xor     rdx, rax
0x14001cb87  mov     rcx, rdx; StackCookie
0x14001cb8a  jmp     __security_check_cookie
```
