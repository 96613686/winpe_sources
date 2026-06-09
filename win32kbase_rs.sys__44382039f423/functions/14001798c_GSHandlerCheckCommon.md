# __GSHandlerCheckCommon

- ea: `0x14001798c`
- end: `0x1400179fc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017968`

## callees

- `0x14001798c`
- `0x140017a10`

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
0x14001798c  sub     rsp, 28h
0x140017990  mov     eax, [r8]
0x140017993  mov     r10, rcx
0x140017996  mov     ecx, eax
0x140017998  mov     r11, rdx
0x14001799b  and     ecx, 0FFFFFFF8h
0x14001799e  test    al, 4
0x1400179a0  jz      short loc_1400179B7
0x1400179a2  mov     eax, [r8+8]
0x1400179a6  movsxd  r9, dword ptr [r8+4]
0x1400179aa  neg     eax
0x1400179ac  movsxd  rdx, eax
0x1400179af  add     r9, r10
0x1400179b2  and     r9, rdx
0x1400179b5  jmp     short loc_1400179BA
0x1400179b7  mov     r9, r10
0x1400179ba  movsxd  rax, ecx
0x1400179bd  mov     rdx, [rax+r9]
0x1400179c1  mov     rax, [r11+10h]
0x1400179c5  mov     ecx, [rax+8]
0x1400179c8  mov     rax, [r11+8]
0x1400179cc  movzx   r8d, byte ptr [rcx+rax+3]
0x1400179d2  test    r8b, 0Fh
0x1400179d6  jz      short loc_1400179E8
0x1400179d8  mov     eax, r8d
0x1400179db  mov     ecx, 0FFFFFFF0h
0x1400179e0  and     rax, rcx
0x1400179e3  add     rax, r10
0x1400179e6  jmp     short loc_1400179EB
0x1400179e8  mov     rax, r10
0x1400179eb  xor     rdx, rax
0x1400179ee  mov     rcx, rdx; StackCookie
0x1400179f1  call    __security_check_cookie
0x1400179f6  add     rsp, 28h
0x1400179fa  retn
```
