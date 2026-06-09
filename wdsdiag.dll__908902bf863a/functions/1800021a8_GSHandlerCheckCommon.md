# __GSHandlerCheckCommon

- ea: `0x1800021a8`
- end: `0x180002201`
- name: `__GSHandlerCheckCommon`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002188`

## callees

- `0x180001b30`
- `0x1800021a8`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = *(_QWORD *)(a2 + 16);
  v3 = *(_QWORD *)(a2 + 8) + *(unsigned int *)(result + 8);
  if ( (*(_BYTE *)(v3 + 3) & 0xF) != 0 )
    return *(_BYTE *)(v3 + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x1800021a8  push    rbx
0x1800021aa  mov     r11d, [r8]
0x1800021ad  mov     rbx, rdx
0x1800021b0  and     r11d, 0FFFFFFF8h
0x1800021b4  mov     r9, rcx
0x1800021b7  test    byte ptr [r8], 4
0x1800021bb  mov     r10, rcx
0x1800021be  jz      short loc_1800021D3
0x1800021c0  mov     eax, [r8+8]
0x1800021c4  movsxd  r10, dword ptr [r8+4]
0x1800021c8  neg     eax
0x1800021ca  add     r10, rcx
0x1800021cd  movsxd  rcx, eax
0x1800021d0  and     r10, rcx
0x1800021d3  movsxd  rax, r11d
0x1800021d6  mov     rdx, [rax+r10]
0x1800021da  mov     rax, [rbx+10h]
0x1800021de  mov     ecx, [rax+8]
0x1800021e1  add     rcx, [rbx+8]
0x1800021e5  test    byte ptr [rcx+3], 0Fh
0x1800021e9  jz      short loc_1800021F5
0x1800021eb  movzx   eax, byte ptr [rcx+3]
0x1800021ef  and     eax, 0FFFFFFF0h
0x1800021f2  add     r9, rax
0x1800021f5  xor     r9, rdx
0x1800021f8  mov     rcx, r9
0x1800021fb  pop     rbx
0x1800021fc  jmp     __security_check_cookie
```
