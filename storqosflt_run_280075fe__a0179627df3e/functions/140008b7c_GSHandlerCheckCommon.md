# __GSHandlerCheckCommon

- ea: `0x140008b7c`
- end: `0x140008bec`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008b58`
- `0x140008bf4`

## callees

- `0x140008b7c`
- `0x140008d20`

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
0x140008b7c  sub     rsp, 28h
0x140008b80  mov     eax, [r8]
0x140008b83  mov     r10, rcx
0x140008b86  mov     ecx, eax
0x140008b88  mov     r11, rdx
0x140008b8b  and     ecx, 0FFFFFFF8h
0x140008b8e  test    al, 4
0x140008b90  jz      short loc_140008BA7
0x140008b92  mov     eax, [r8+8]
0x140008b96  movsxd  r9, dword ptr [r8+4]
0x140008b9a  neg     eax
0x140008b9c  movsxd  rdx, eax
0x140008b9f  add     r9, r10
0x140008ba2  and     r9, rdx
0x140008ba5  jmp     short loc_140008BAA
0x140008ba7  mov     r9, r10
0x140008baa  movsxd  rax, ecx
0x140008bad  mov     rdx, [rax+r9]
0x140008bb1  mov     rax, [r11+10h]
0x140008bb5  mov     ecx, [rax+8]
0x140008bb8  mov     rax, [r11+8]
0x140008bbc  movzx   r8d, byte ptr [rcx+rax+3]
0x140008bc2  test    r8b, 0Fh
0x140008bc6  jz      short loc_140008BD8
0x140008bc8  mov     eax, r8d
0x140008bcb  mov     ecx, 0FFFFFFF0h
0x140008bd0  and     rax, rcx
0x140008bd3  add     rax, r10
0x140008bd6  jmp     short loc_140008BDB
0x140008bd8  mov     rax, r10
0x140008bdb  xor     rdx, rax
0x140008bde  mov     rcx, rdx; StackCookie
0x140008be1  call    __security_check_cookie
0x140008be6  add     rsp, 28h
0x140008bea  retn
```
