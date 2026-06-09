# __GSHandlerCheckCommon

- ea: `0x140002fbc`
- end: `0x14000302c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002f98`

## callees

- `0x140002fbc`
- `0x1400030f0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x140002fbc  sub     rsp, 28h
0x140002fc0  mov     eax, [r8]
0x140002fc3  mov     r10, rcx
0x140002fc6  mov     ecx, eax
0x140002fc8  mov     r11, rdx
0x140002fcb  and     ecx, 0FFFFFFF8h
0x140002fce  test    al, 4
0x140002fd0  jz      short loc_140002FE7
0x140002fd2  mov     eax, [r8+8]
0x140002fd6  movsxd  r9, dword ptr [r8+4]
0x140002fda  neg     eax
0x140002fdc  movsxd  rdx, eax
0x140002fdf  add     r9, r10
0x140002fe2  and     r9, rdx
0x140002fe5  jmp     short loc_140002FEA
0x140002fe7  mov     r9, r10
0x140002fea  movsxd  rax, ecx
0x140002fed  mov     rdx, [rax+r9]
0x140002ff1  mov     rax, [r11+10h]
0x140002ff5  mov     ecx, [rax+8]
0x140002ff8  mov     rax, [r11+8]
0x140002ffc  movzx   r8d, byte ptr [rcx+rax+3]
0x140003002  test    r8b, 0Fh
0x140003006  jz      short loc_140003018
0x140003008  mov     eax, r8d
0x14000300b  mov     ecx, 0FFFFFFF0h
0x140003010  and     rax, rcx
0x140003013  add     rax, r10
0x140003016  jmp     short loc_14000301B
0x140003018  mov     rax, r10
0x14000301b  xor     rdx, rax
0x14000301e  mov     rcx, rdx; StackCookie
0x140003021  call    __security_check_cookie
0x140003026  add     rsp, 28h
0x14000302a  retn
```
