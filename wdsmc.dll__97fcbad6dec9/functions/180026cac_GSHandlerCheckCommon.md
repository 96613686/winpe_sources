# __GSHandlerCheckCommon

- ea: `0x180026cac`
- end: `0x180026d07`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026c88`

## callees

- `0x180026670`
- `0x180026cac`

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
0x180026cac  push    rbx
0x180026cae  mov     r11d, [r8]
0x180026cb1  mov     rbx, rdx
0x180026cb4  and     r11d, 0FFFFFFF8h
0x180026cb8  mov     r9, rcx
0x180026cbb  test    byte ptr [r8], 4
0x180026cbf  mov     r10, rcx
0x180026cc2  jz      short loc_180026CD7
0x180026cc4  mov     eax, [r8+8]
0x180026cc8  movsxd  r10, dword ptr [r8+4]
0x180026ccc  neg     eax
0x180026cce  add     r10, rcx
0x180026cd1  movsxd  rcx, eax
0x180026cd4  and     r10, rcx
0x180026cd7  movsxd  rax, r11d
0x180026cda  mov     rdx, [rax+r10]
0x180026cde  mov     rax, [rbx+10h]
0x180026ce2  mov     ecx, [rax+8]
0x180026ce5  mov     rax, [rbx+8]
0x180026ce9  test    byte ptr [rcx+rax+3], 0Fh
0x180026cee  jz      short loc_180026CFB
0x180026cf0  movzx   eax, byte ptr [rcx+rax+3]
0x180026cf5  and     eax, 0FFFFFFF0h
0x180026cf8  add     r9, rax
0x180026cfb  xor     r9, rdx
0x180026cfe  mov     rcx, r9; StackCookie
0x180026d01  pop     rbx
0x180026d02  jmp     __security_check_cookie
```
