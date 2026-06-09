# __GSHandlerCheckCommon

- ea: `0x180016b2c`
- end: `0x180016b8f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016b08`
- `0x180016b98`

## callees

- `0x180016b2c`
- `0x180016c50`

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
0x180016b2c  mov     r10, rcx
0x180016b2f  mov     r11, rdx
0x180016b32  mov     ecx, [r8]
0x180016b35  and     ecx, 0FFFFFFF8h
0x180016b38  test    byte ptr [r8], 4
0x180016b3c  jz      short loc_180016B53
0x180016b3e  mov     eax, [r8+8]
0x180016b42  movsxd  r9, dword ptr [r8+4]
0x180016b46  neg     eax
0x180016b48  movsxd  rdx, eax
0x180016b4b  add     r9, r10
0x180016b4e  and     r9, rdx
0x180016b51  jmp     short loc_180016B56
0x180016b53  mov     r9, r10
0x180016b56  movsxd  rax, ecx
0x180016b59  mov     rdx, [rax+r9]
0x180016b5d  mov     rax, [r11+10h]
0x180016b61  mov     ecx, [rax+8]
0x180016b64  mov     rax, [r11+8]
0x180016b68  test    byte ptr [rcx+rax+3], 0Fh
0x180016b6d  jz      short loc_180016B81
0x180016b6f  movzx   eax, byte ptr [rcx+rax+3]
0x180016b74  mov     ecx, 0FFFFFFF0h
0x180016b79  and     rax, rcx
0x180016b7c  add     rax, r10
0x180016b7f  jmp     short loc_180016B84
0x180016b81  mov     rax, r10
0x180016b84  xor     rdx, rax
0x180016b87  mov     rcx, rdx; StackCookie
0x180016b8a  jmp     __security_check_cookie
```
