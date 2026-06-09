# __GSHandlerCheckCommon

- ea: `0x14000572c`
- end: `0x14000578c`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005708`
- `0x1400058b0`
- `0x14000593c`

## callees

- `0x140001500`
- `0x14000572c`

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
0x14000572c  push    rbx
0x14000572e  mov     r11d, [r8]
0x140005731  mov     rbx, rdx
0x140005734  and     r11d, 0FFFFFFF8h
0x140005738  mov     r9, rcx
0x14000573b  test    byte ptr [r8], 4
0x14000573f  mov     r10, rcx
0x140005742  jz      short loc_140005757
0x140005744  mov     eax, [r8+8]
0x140005748  movsxd  r10, dword ptr [r8+4]
0x14000574c  neg     eax
0x14000574e  add     r10, rcx
0x140005751  movsxd  rcx, eax
0x140005754  and     r10, rcx
0x140005757  movsxd  rax, r11d
0x14000575a  mov     rdx, [rax+r10]
0x14000575e  mov     rax, [rbx+10h]
0x140005762  mov     ecx, [rax+8]
0x140005765  mov     rax, [rbx+8]
0x140005769  test    byte ptr [rcx+rax+3], 0Fh
0x14000576e  jz      short loc_140005780
0x140005770  movzx   eax, byte ptr [rcx+rax+3]
0x140005775  mov     ecx, 0FFFFFFF0h
0x14000577a  and     rax, rcx
0x14000577d  add     r9, rax
0x140005780  xor     r9, rdx
0x140005783  mov     rcx, r9; StackCookie
0x140005786  pop     rbx
0x140005787  jmp     __security_check_cookie
```
