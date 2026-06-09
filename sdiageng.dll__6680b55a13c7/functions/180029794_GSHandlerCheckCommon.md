# __GSHandlerCheckCommon

- ea: `0x180029794`
- end: `0x1800297f7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029770`
- `0x180029800`

## callees

- `0x180029794`
- `0x1800298c0`

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
0x180029794  mov     r10, rcx
0x180029797  mov     r11, rdx
0x18002979a  mov     ecx, [r8]
0x18002979d  and     ecx, 0FFFFFFF8h
0x1800297a0  test    byte ptr [r8], 4
0x1800297a4  jz      short loc_1800297BB
0x1800297a6  mov     eax, [r8+8]
0x1800297aa  movsxd  r9, dword ptr [r8+4]
0x1800297ae  neg     eax
0x1800297b0  movsxd  rdx, eax
0x1800297b3  add     r9, r10
0x1800297b6  and     r9, rdx
0x1800297b9  jmp     short loc_1800297BE
0x1800297bb  mov     r9, r10
0x1800297be  movsxd  rax, ecx
0x1800297c1  mov     rdx, [rax+r9]
0x1800297c5  mov     rax, [r11+10h]
0x1800297c9  mov     ecx, [rax+8]
0x1800297cc  mov     rax, [r11+8]
0x1800297d0  test    byte ptr [rcx+rax+3], 0Fh
0x1800297d5  jz      short loc_1800297E9
0x1800297d7  movzx   eax, byte ptr [rcx+rax+3]
0x1800297dc  mov     ecx, 0FFFFFFF0h
0x1800297e1  and     rax, rcx
0x1800297e4  add     rax, r10
0x1800297e7  jmp     short loc_1800297EC
0x1800297e9  mov     rax, r10
0x1800297ec  xor     rdx, rax
0x1800297ef  mov     rcx, rdx; StackCookie
0x1800297f2  jmp     __security_check_cookie
```
