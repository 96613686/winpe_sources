# __GSHandlerCheckCommon

- ea: `0x18000db2c`
- end: `0x18000db8f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000db08`

## callees

- `0x180001670`
- `0x18000db2c`

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
0x18000db2c  mov     r10, rcx
0x18000db2f  mov     r11, rdx
0x18000db32  mov     ecx, [r8]
0x18000db35  and     ecx, 0FFFFFFF8h
0x18000db38  test    byte ptr [r8], 4
0x18000db3c  jz      short loc_18000DB53
0x18000db3e  mov     eax, [r8+8]
0x18000db42  movsxd  r9, dword ptr [r8+4]
0x18000db46  neg     eax
0x18000db48  movsxd  rdx, eax
0x18000db4b  add     r9, r10
0x18000db4e  and     r9, rdx
0x18000db51  jmp     short loc_18000DB56
0x18000db53  mov     r9, r10
0x18000db56  movsxd  rax, ecx
0x18000db59  mov     rdx, [rax+r9]
0x18000db5d  mov     rax, [r11+10h]
0x18000db61  mov     ecx, [rax+8]
0x18000db64  mov     rax, [r11+8]
0x18000db68  test    byte ptr [rcx+rax+3], 0Fh
0x18000db6d  jz      short loc_18000DB81
0x18000db6f  movzx   eax, byte ptr [rcx+rax+3]
0x18000db74  mov     ecx, 0FFFFFFF0h
0x18000db79  and     rax, rcx
0x18000db7c  add     rax, r10
0x18000db7f  jmp     short loc_18000DB84
0x18000db81  mov     rax, r10
0x18000db84  xor     rdx, rax
0x18000db87  mov     rcx, rdx; StackCookie
0x18000db8a  jmp     __security_check_cookie
```
