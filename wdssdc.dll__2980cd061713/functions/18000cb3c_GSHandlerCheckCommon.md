# __GSHandlerCheckCommon

- ea: `0x18000cb3c`
- end: `0x18000cb9c`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cb18`

## callees

- `0x1800015b0`
- `0x18000cb3c`

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
0x18000cb3c  push    rbx
0x18000cb3e  mov     r11d, [r8]
0x18000cb41  mov     rbx, rdx
0x18000cb44  and     r11d, 0FFFFFFF8h
0x18000cb48  mov     r9, rcx
0x18000cb4b  test    byte ptr [r8], 4
0x18000cb4f  mov     r10, rcx
0x18000cb52  jz      short loc_18000CB67
0x18000cb54  mov     eax, [r8+8]
0x18000cb58  movsxd  r10, dword ptr [r8+4]
0x18000cb5c  neg     eax
0x18000cb5e  add     r10, rcx
0x18000cb61  movsxd  rcx, eax
0x18000cb64  and     r10, rcx
0x18000cb67  movsxd  rax, r11d
0x18000cb6a  mov     rdx, [rax+r10]
0x18000cb6e  mov     rax, [rbx+10h]
0x18000cb72  mov     ecx, [rax+8]
0x18000cb75  mov     rax, [rbx+8]
0x18000cb79  test    byte ptr [rcx+rax+3], 0Fh
0x18000cb7e  jz      short loc_18000CB90
0x18000cb80  movzx   eax, byte ptr [rcx+rax+3]
0x18000cb85  mov     ecx, 0FFFFFFF0h
0x18000cb8a  and     rax, rcx
0x18000cb8d  add     r9, rax
0x18000cb90  xor     r9, rdx
0x18000cb93  mov     rcx, r9; StackCookie
0x18000cb96  pop     rbx
0x18000cb97  jmp     __security_check_cookie
```
