# __GSHandlerCheckCommon

- ea: `0x140002454`
- end: `0x1400024b7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002430`
- `0x14000ab80`

## callees

- `0x140002120`
- `0x140002454`

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
0x140002454  mov     r10, rcx
0x140002457  mov     r11, rdx
0x14000245a  mov     ecx, [r8]
0x14000245d  and     ecx, 0FFFFFFF8h
0x140002460  test    byte ptr [r8], 4
0x140002464  jz      short loc_14000247B
0x140002466  mov     eax, [r8+8]
0x14000246a  movsxd  r9, dword ptr [r8+4]
0x14000246e  neg     eax
0x140002470  movsxd  rdx, eax
0x140002473  add     r9, r10
0x140002476  and     r9, rdx
0x140002479  jmp     short loc_14000247E
0x14000247b  mov     r9, r10
0x14000247e  movsxd  rax, ecx
0x140002481  mov     rdx, [rax+r9]
0x140002485  mov     rax, [r11+10h]
0x140002489  mov     ecx, [rax+8]
0x14000248c  mov     rax, [r11+8]
0x140002490  test    byte ptr [rcx+rax+3], 0Fh
0x140002495  jz      short loc_1400024A9
0x140002497  movzx   eax, byte ptr [rcx+rax+3]
0x14000249c  mov     ecx, 0FFFFFFF0h
0x1400024a1  and     rax, rcx
0x1400024a4  add     rax, r10
0x1400024a7  jmp     short loc_1400024AC
0x1400024a9  mov     rax, r10
0x1400024ac  xor     rdx, rax
0x1400024af  mov     rcx, rdx; StackCookie
0x1400024b2  jmp     __security_check_cookie
```
