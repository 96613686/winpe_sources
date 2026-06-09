# __GSHandlerCheckCommon

- ea: `0x1400408ec`
- end: `0x14004095c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400408c8`

## callees

- `0x1400408ec`
- `0x140040a30`

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
0x1400408ec  sub     rsp, 28h
0x1400408f0  mov     eax, [r8]
0x1400408f3  mov     r10, rcx
0x1400408f6  mov     ecx, eax
0x1400408f8  mov     r11, rdx
0x1400408fb  and     ecx, 0FFFFFFF8h
0x1400408fe  test    al, 4
0x140040900  jz      short loc_140040917
0x140040902  mov     eax, [r8+8]
0x140040906  movsxd  r9, dword ptr [r8+4]
0x14004090a  neg     eax
0x14004090c  movsxd  rdx, eax
0x14004090f  add     r9, r10
0x140040912  and     r9, rdx
0x140040915  jmp     short loc_14004091A
0x140040917  mov     r9, r10
0x14004091a  movsxd  rax, ecx
0x14004091d  mov     rdx, [rax+r9]
0x140040921  mov     rax, [r11+10h]
0x140040925  mov     ecx, [rax+8]
0x140040928  mov     rax, [r11+8]
0x14004092c  movzx   r8d, byte ptr [rcx+rax+3]
0x140040932  test    r8b, 0Fh
0x140040936  jz      short loc_140040948
0x140040938  mov     eax, r8d
0x14004093b  mov     ecx, 0FFFFFFF0h
0x140040940  and     rax, rcx
0x140040943  add     rax, r10
0x140040946  jmp     short loc_14004094B
0x140040948  mov     rax, r10
0x14004094b  xor     rdx, rax
0x14004094e  mov     rcx, rdx; StackCookie
0x140040951  call    __security_check_cookie
0x140040956  add     rsp, 28h
0x14004095a  retn
```
