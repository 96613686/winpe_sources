# __GSHandlerCheckCommon

- ea: `0x180001fcc`
- end: `0x18000202f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001fa8`

## callees

- `0x180001fcc`
- `0x180012db0`

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
0x180001fcc  mov     r10, rcx
0x180001fcf  mov     r11, rdx
0x180001fd2  mov     ecx, [r8]
0x180001fd5  and     ecx, 0FFFFFFF8h
0x180001fd8  test    byte ptr [r8], 4
0x180001fdc  jz      short loc_180001FF3
0x180001fde  mov     eax, [r8+8]
0x180001fe2  movsxd  r9, dword ptr [r8+4]
0x180001fe6  neg     eax
0x180001fe8  movsxd  rdx, eax
0x180001feb  add     r9, r10
0x180001fee  and     r9, rdx
0x180001ff1  jmp     short loc_180001FF6
0x180001ff3  mov     r9, r10
0x180001ff6  movsxd  rax, ecx
0x180001ff9  mov     rdx, [rax+r9]
0x180001ffd  mov     rax, [r11+10h]
0x180002001  mov     ecx, [rax+8]
0x180002004  mov     rax, [r11+8]
0x180002008  test    byte ptr [rcx+rax+3], 0Fh
0x18000200d  jz      short loc_180002021
0x18000200f  movzx   eax, byte ptr [rcx+rax+3]
0x180002014  mov     ecx, 0FFFFFFF0h
0x180002019  and     rax, rcx
0x18000201c  add     rax, r10
0x18000201f  jmp     short loc_180002024
0x180002021  mov     rax, r10
0x180002024  xor     rdx, rax
0x180002027  mov     rcx, rdx; StackCookie
0x18000202a  jmp     __security_check_cookie
```
