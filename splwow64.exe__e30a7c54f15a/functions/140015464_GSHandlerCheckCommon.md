# __GSHandlerCheckCommon

- ea: `0x140015464`
- end: `0x1400154c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015440`

## callees

- `0x140001ee0`
- `0x140015464`

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
0x140015464  mov     r10, rcx
0x140015467  mov     r11, rdx
0x14001546a  mov     ecx, [r8]
0x14001546d  and     ecx, 0FFFFFFF8h
0x140015470  test    byte ptr [r8], 4
0x140015474  jz      short loc_14001548B
0x140015476  mov     eax, [r8+8]
0x14001547a  movsxd  r9, dword ptr [r8+4]
0x14001547e  neg     eax
0x140015480  movsxd  rdx, eax
0x140015483  add     r9, r10
0x140015486  and     r9, rdx
0x140015489  jmp     short loc_14001548E
0x14001548b  mov     r9, r10
0x14001548e  movsxd  rax, ecx
0x140015491  mov     rdx, [rax+r9]
0x140015495  mov     rax, [r11+10h]
0x140015499  mov     ecx, [rax+8]
0x14001549c  mov     rax, [r11+8]
0x1400154a0  test    byte ptr [rcx+rax+3], 0Fh
0x1400154a5  jz      short loc_1400154B9
0x1400154a7  movzx   eax, byte ptr [rcx+rax+3]
0x1400154ac  mov     ecx, 0FFFFFFF0h
0x1400154b1  and     rax, rcx
0x1400154b4  add     rax, r10
0x1400154b7  jmp     short loc_1400154BC
0x1400154b9  mov     rax, r10
0x1400154bc  xor     rdx, rax
0x1400154bf  mov     rcx, rdx; StackCookie
0x1400154c2  jmp     __security_check_cookie
```
