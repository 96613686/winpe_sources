# __GSHandlerCheckCommon

- ea: `0x180002a04`
- end: `0x180002a5f`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800029e0`
- `0x18001e930`

## callees

- `0x180002a04`
- `0x18001e9f0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x180002a04  push    rbx
0x180002a06  mov     r11d, [r8]
0x180002a09  mov     rbx, rdx
0x180002a0c  and     r11d, 0FFFFFFF8h
0x180002a10  mov     r9, rcx
0x180002a13  test    byte ptr [r8], 4
0x180002a17  mov     r10, rcx
0x180002a1a  jz      short loc_180002A2F
0x180002a1c  mov     eax, [r8+8]
0x180002a20  movsxd  r10, dword ptr [r8+4]
0x180002a24  neg     eax
0x180002a26  add     r10, rcx
0x180002a29  movsxd  rcx, eax
0x180002a2c  and     r10, rcx
0x180002a2f  movsxd  rax, r11d
0x180002a32  mov     rdx, [rax+r10]
0x180002a36  mov     rax, [rbx+10h]
0x180002a3a  mov     ecx, [rax+8]
0x180002a3d  mov     rax, [rbx+8]
0x180002a41  test    byte ptr [rcx+rax+3], 0Fh
0x180002a46  jz      short loc_180002A53
0x180002a48  movzx   eax, byte ptr [rcx+rax+3]
0x180002a4d  and     eax, 0FFFFFFF0h
0x180002a50  add     r9, rax
0x180002a53  xor     r9, rdx
0x180002a56  mov     rcx, r9; StackCookie
0x180002a59  pop     rbx
0x180002a5a  jmp     __security_check_cookie
```
