# __GSHandlerCheckCommon

- ea: `0x1800156c0`
- end: `0x180015720`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001569c`
- `0x180015804`
- `0x1800158a8`

## callees

- `0x18000fc90`
- `0x1800156c0`

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
0x1800156c0  push    rbx
0x1800156c2  mov     r11d, [r8]
0x1800156c5  mov     rbx, rdx
0x1800156c8  and     r11d, 0FFFFFFF8h
0x1800156cc  mov     r9, rcx
0x1800156cf  test    byte ptr [r8], 4
0x1800156d3  mov     r10, rcx
0x1800156d6  jz      short loc_1800156EB
0x1800156d8  mov     eax, [r8+8]
0x1800156dc  movsxd  r10, dword ptr [r8+4]
0x1800156e0  neg     eax
0x1800156e2  add     r10, rcx
0x1800156e5  movsxd  rcx, eax
0x1800156e8  and     r10, rcx
0x1800156eb  movsxd  rax, r11d
0x1800156ee  mov     rdx, [rax+r10]
0x1800156f2  mov     rax, [rbx+10h]
0x1800156f6  mov     ecx, [rax+8]
0x1800156f9  mov     rax, [rbx+8]
0x1800156fd  test    byte ptr [rcx+rax+3], 0Fh
0x180015702  jz      short loc_180015714
0x180015704  movzx   eax, byte ptr [rcx+rax+3]
0x180015709  mov     ecx, 0FFFFFFF0h
0x18001570e  and     rax, rcx
0x180015711  add     r9, rax
0x180015714  xor     r9, rdx
0x180015717  mov     rcx, r9; StackCookie
0x18001571a  pop     rbx
0x18001571b  jmp     __security_check_cookie
```
