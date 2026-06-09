# __GSHandlerCheckCommon

- ea: `0x180015564`
- end: `0x1800155c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015540`
- `0x1800155d0`

## callees

- `0x180015564`
- `0x180015680`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180015564  mov     r10, rcx
0x180015567  mov     r11, rdx
0x18001556a  mov     ecx, [r8]
0x18001556d  and     ecx, 0FFFFFFF8h
0x180015570  test    byte ptr [r8], 4
0x180015574  jz      short loc_18001558B
0x180015576  mov     eax, [r8+8]
0x18001557a  movsxd  r9, dword ptr [r8+4]
0x18001557e  neg     eax
0x180015580  movsxd  rdx, eax
0x180015583  add     r9, r10
0x180015586  and     r9, rdx
0x180015589  jmp     short loc_18001558E
0x18001558b  mov     r9, r10
0x18001558e  movsxd  rax, ecx
0x180015591  mov     rdx, [rax+r9]
0x180015595  mov     rax, [r11+10h]
0x180015599  mov     ecx, [rax+8]
0x18001559c  mov     rax, [r11+8]
0x1800155a0  test    byte ptr [rcx+rax+3], 0Fh
0x1800155a5  jz      short loc_1800155B9
0x1800155a7  movzx   eax, byte ptr [rcx+rax+3]
0x1800155ac  mov     ecx, 0FFFFFFF0h
0x1800155b1  and     rax, rcx
0x1800155b4  add     rax, r10
0x1800155b7  jmp     short loc_1800155BC
0x1800155b9  mov     rax, r10
0x1800155bc  xor     rdx, rax
0x1800155bf  mov     rcx, rdx; StackCookie
0x1800155c2  jmp     __security_check_cookie
```
