# __GSHandlerCheckCommon

- ea: `0x180020664`
- end: `0x1800206c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020640`
- `0x1800206d0`

## callees

- `0x1800106c0`
- `0x180020664`

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
0x180020664  mov     r10, rcx
0x180020667  mov     r11, rdx
0x18002066a  mov     ecx, [r8]
0x18002066d  and     ecx, 0FFFFFFF8h
0x180020670  test    byte ptr [r8], 4
0x180020674  jz      short loc_18002068B
0x180020676  mov     eax, [r8+8]
0x18002067a  movsxd  r9, dword ptr [r8+4]
0x18002067e  neg     eax
0x180020680  movsxd  rdx, eax
0x180020683  add     r9, r10
0x180020686  and     r9, rdx
0x180020689  jmp     short loc_18002068E
0x18002068b  mov     r9, r10
0x18002068e  movsxd  rax, ecx
0x180020691  mov     rdx, [rax+r9]
0x180020695  mov     rax, [r11+10h]
0x180020699  mov     ecx, [rax+8]
0x18002069c  mov     rax, [r11+8]
0x1800206a0  test    byte ptr [rcx+rax+3], 0Fh
0x1800206a5  jz      short loc_1800206B9
0x1800206a7  movzx   eax, byte ptr [rcx+rax+3]
0x1800206ac  mov     ecx, 0FFFFFFF0h
0x1800206b1  and     rax, rcx
0x1800206b4  add     rax, r10
0x1800206b7  jmp     short loc_1800206BC
0x1800206b9  mov     rax, r10
0x1800206bc  xor     rdx, rax
0x1800206bf  mov     rcx, rdx; StackCookie
0x1800206c2  jmp     __security_check_cookie
```
