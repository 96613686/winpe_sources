# __GSHandlerCheckCommon

- ea: `0x180003620`
- end: `0x180003683`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800035fc`

## callees

- `0x180003620`
- `0x1800036c0`

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
0x180003620  mov     r10, rcx
0x180003623  mov     r11, rdx
0x180003626  mov     ecx, [r8]
0x180003629  and     ecx, 0FFFFFFF8h
0x18000362c  test    byte ptr [r8], 4
0x180003630  jz      short loc_180003647
0x180003632  mov     eax, [r8+8]
0x180003636  movsxd  r9, dword ptr [r8+4]
0x18000363a  neg     eax
0x18000363c  movsxd  rdx, eax
0x18000363f  add     r9, r10
0x180003642  and     r9, rdx
0x180003645  jmp     short loc_18000364A
0x180003647  mov     r9, r10
0x18000364a  movsxd  rax, ecx
0x18000364d  mov     rdx, [rax+r9]
0x180003651  mov     rax, [r11+10h]
0x180003655  mov     ecx, [rax+8]
0x180003658  mov     rax, [r11+8]
0x18000365c  test    byte ptr [rcx+rax+3], 0Fh
0x180003661  jz      short loc_180003675
0x180003663  movzx   eax, byte ptr [rcx+rax+3]
0x180003668  mov     ecx, 0FFFFFFF0h
0x18000366d  and     rax, rcx
0x180003670  add     rax, r10
0x180003673  jmp     short loc_180003678
0x180003675  mov     rax, r10
0x180003678  xor     rdx, rax
0x18000367b  mov     rcx, rdx; StackCookie
0x18000367e  jmp     __security_check_cookie
```
