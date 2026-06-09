# __GSHandlerCheckCommon

- ea: `0x18000c740`
- end: `0x18000c79b`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c71c`
- `0x18000c7a4`

## callees

- `0x18000c740`
- `0x18000c860`

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
0x18000c740  push    rbx
0x18000c742  mov     r11d, [r8]
0x18000c745  mov     rbx, rdx
0x18000c748  and     r11d, 0FFFFFFF8h
0x18000c74c  mov     r9, rcx
0x18000c74f  test    byte ptr [r8], 4
0x18000c753  mov     r10, rcx
0x18000c756  jz      short loc_18000C76B
0x18000c758  mov     eax, [r8+8]
0x18000c75c  movsxd  r10, dword ptr [r8+4]
0x18000c760  neg     eax
0x18000c762  add     r10, rcx
0x18000c765  movsxd  rcx, eax
0x18000c768  and     r10, rcx
0x18000c76b  movsxd  rax, r11d
0x18000c76e  mov     rdx, [rax+r10]
0x18000c772  mov     rax, [rbx+10h]
0x18000c776  mov     ecx, [rax+8]
0x18000c779  mov     rax, [rbx+8]
0x18000c77d  test    byte ptr [rcx+rax+3], 0Fh
0x18000c782  jz      short loc_18000C78F
0x18000c784  movzx   eax, byte ptr [rcx+rax+3]
0x18000c789  and     eax, 0FFFFFFF0h
0x18000c78c  add     r9, rax
0x18000c78f  xor     r9, rdx
0x18000c792  mov     rcx, r9; StackCookie
0x18000c795  pop     rbx
0x18000c796  jmp     __security_check_cookie
```
