# __GSHandlerCheckCommon

- ea: `0x140001044`
- end: `0x1400010b4`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001020`

## callees

- `0x140001044`
- `0x140006330`

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
0x140001044  sub     rsp, 28h
0x140001048  mov     eax, [r8]
0x14000104b  mov     r10, rcx
0x14000104e  mov     ecx, eax
0x140001050  mov     r11, rdx
0x140001053  and     ecx, 0FFFFFFF8h
0x140001056  test    al, 4
0x140001058  jz      short loc_14000106F
0x14000105a  mov     eax, [r8+8]
0x14000105e  movsxd  r9, dword ptr [r8+4]
0x140001062  neg     eax
0x140001064  movsxd  rdx, eax
0x140001067  add     r9, r10
0x14000106a  and     r9, rdx
0x14000106d  jmp     short loc_140001072
0x14000106f  mov     r9, r10
0x140001072  movsxd  rax, ecx
0x140001075  mov     rdx, [rax+r9]
0x140001079  mov     rax, [r11+10h]
0x14000107d  mov     ecx, [rax+8]
0x140001080  mov     rax, [r11+8]
0x140001084  movzx   r8d, byte ptr [rcx+rax+3]
0x14000108a  test    r8b, 0Fh
0x14000108e  jz      short loc_1400010A0
0x140001090  mov     eax, r8d
0x140001093  mov     ecx, 0FFFFFFF0h
0x140001098  and     rax, rcx
0x14000109b  add     rax, r10
0x14000109e  jmp     short loc_1400010A3
0x1400010a0  mov     rax, r10
0x1400010a3  xor     rdx, rax
0x1400010a6  mov     rcx, rdx; StackCookie
0x1400010a9  call    __security_check_cookie
0x1400010ae  add     rsp, 28h
0x1400010b2  retn
```
