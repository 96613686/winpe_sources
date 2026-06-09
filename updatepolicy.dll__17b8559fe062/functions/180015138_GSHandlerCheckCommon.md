# __GSHandlerCheckCommon

- ea: `0x180015138`
- end: `0x180015198`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015114`
- `0x180015274`
- `0x18001532c`

## callees

- `0x18000ed40`
- `0x180015138`

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
0x180015138  push    rbx
0x18001513a  mov     r11d, [r8]
0x18001513d  mov     rbx, rdx
0x180015140  and     r11d, 0FFFFFFF8h
0x180015144  mov     r9, rcx
0x180015147  test    byte ptr [r8], 4
0x18001514b  mov     r10, rcx
0x18001514e  jz      short loc_180015163
0x180015150  mov     eax, [r8+8]
0x180015154  movsxd  r10, dword ptr [r8+4]
0x180015158  neg     eax
0x18001515a  add     r10, rcx
0x18001515d  movsxd  rcx, eax
0x180015160  and     r10, rcx
0x180015163  movsxd  rax, r11d
0x180015166  mov     rdx, [rax+r10]
0x18001516a  mov     rax, [rbx+10h]
0x18001516e  mov     ecx, [rax+8]
0x180015171  mov     rax, [rbx+8]
0x180015175  test    byte ptr [rcx+rax+3], 0Fh
0x18001517a  jz      short loc_18001518C
0x18001517c  movzx   eax, byte ptr [rcx+rax+3]
0x180015181  mov     ecx, 0FFFFFFF0h
0x180015186  and     rax, rcx
0x180015189  add     r9, rax
0x18001518c  xor     r9, rdx
0x18001518f  mov     rcx, r9; StackCookie
0x180015192  pop     rbx
0x180015193  jmp     __security_check_cookie
```
