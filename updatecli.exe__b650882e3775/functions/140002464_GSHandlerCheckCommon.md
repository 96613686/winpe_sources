# __GSHandlerCheckCommon

- ea: `0x140002464`
- end: `0x1400024c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002440`
- `0x14000aba0`

## callees

- `0x140002130`
- `0x140002464`

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
0x140002464  mov     r10, rcx
0x140002467  mov     r11, rdx
0x14000246a  mov     ecx, [r8]
0x14000246d  and     ecx, 0FFFFFFF8h
0x140002470  test    byte ptr [r8], 4
0x140002474  jz      short loc_14000248B
0x140002476  mov     eax, [r8+8]
0x14000247a  movsxd  r9, dword ptr [r8+4]
0x14000247e  neg     eax
0x140002480  movsxd  rdx, eax
0x140002483  add     r9, r10
0x140002486  and     r9, rdx
0x140002489  jmp     short loc_14000248E
0x14000248b  mov     r9, r10
0x14000248e  movsxd  rax, ecx
0x140002491  mov     rdx, [rax+r9]
0x140002495  mov     rax, [r11+10h]
0x140002499  mov     ecx, [rax+8]
0x14000249c  mov     rax, [r11+8]
0x1400024a0  test    byte ptr [rcx+rax+3], 0Fh
0x1400024a5  jz      short loc_1400024B9
0x1400024a7  movzx   eax, byte ptr [rcx+rax+3]
0x1400024ac  mov     ecx, 0FFFFFFF0h
0x1400024b1  and     rax, rcx
0x1400024b4  add     rax, r10
0x1400024b7  jmp     short loc_1400024BC
0x1400024b9  mov     rax, r10
0x1400024bc  xor     rdx, rax
0x1400024bf  mov     rcx, rdx; StackCookie
0x1400024c2  jmp     __security_check_cookie
```
