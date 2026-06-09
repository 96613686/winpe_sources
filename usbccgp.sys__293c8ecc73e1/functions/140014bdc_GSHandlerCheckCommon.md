# __GSHandlerCheckCommon

- ea: `0x140014bdc`
- end: `0x140014c4c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140014bb8`

## callees

- `0x140014bdc`
- `0x140014d10`

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
0x140014bdc  sub     rsp, 28h
0x140014be0  mov     eax, [r8]
0x140014be3  mov     r10, rcx
0x140014be6  mov     ecx, eax
0x140014be8  mov     r11, rdx
0x140014beb  and     ecx, 0FFFFFFF8h
0x140014bee  test    al, 4
0x140014bf0  jz      short loc_140014C07
0x140014bf2  mov     eax, [r8+8]
0x140014bf6  movsxd  r9, dword ptr [r8+4]
0x140014bfa  neg     eax
0x140014bfc  movsxd  rdx, eax
0x140014bff  add     r9, r10
0x140014c02  and     r9, rdx
0x140014c05  jmp     short loc_140014C0A
0x140014c07  mov     r9, r10
0x140014c0a  movsxd  rax, ecx
0x140014c0d  mov     rdx, [rax+r9]
0x140014c11  mov     rax, [r11+10h]
0x140014c15  mov     ecx, [rax+8]
0x140014c18  mov     rax, [r11+8]
0x140014c1c  movzx   r8d, byte ptr [rcx+rax+3]
0x140014c22  test    r8b, 0Fh
0x140014c26  jz      short loc_140014C38
0x140014c28  mov     eax, r8d
0x140014c2b  mov     ecx, 0FFFFFFF0h
0x140014c30  and     rax, rcx
0x140014c33  add     rax, r10
0x140014c36  jmp     short loc_140014C3B
0x140014c38  mov     rax, r10
0x140014c3b  xor     rdx, rax
0x140014c3e  mov     rcx, rdx; StackCookie
0x140014c41  call    __security_check_cookie
0x140014c46  add     rsp, 28h
0x140014c4a  retn
```
