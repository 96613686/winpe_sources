# __GSHandlerCheckCommon

- ea: `0x180004620`
- end: `0x180004683`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800045fc`
- `0x18000468c`

## callees

- `0x180004620`
- `0x180004720`

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
0x180004620  mov     r10, rcx
0x180004623  mov     r11, rdx
0x180004626  mov     ecx, [r8]
0x180004629  and     ecx, 0FFFFFFF8h
0x18000462c  test    byte ptr [r8], 4
0x180004630  jz      short loc_180004647
0x180004632  mov     eax, [r8+8]
0x180004636  movsxd  r9, dword ptr [r8+4]
0x18000463a  neg     eax
0x18000463c  movsxd  rdx, eax
0x18000463f  add     r9, r10
0x180004642  and     r9, rdx
0x180004645  jmp     short loc_18000464A
0x180004647  mov     r9, r10
0x18000464a  movsxd  rax, ecx
0x18000464d  mov     rdx, [rax+r9]
0x180004651  mov     rax, [r11+10h]
0x180004655  mov     ecx, [rax+8]
0x180004658  mov     rax, [r11+8]
0x18000465c  test    byte ptr [rcx+rax+3], 0Fh
0x180004661  jz      short loc_180004675
0x180004663  movzx   eax, byte ptr [rcx+rax+3]
0x180004668  mov     ecx, 0FFFFFFF0h
0x18000466d  and     rax, rcx
0x180004670  add     rax, r10
0x180004673  jmp     short loc_180004678
0x180004675  mov     rax, r10
0x180004678  xor     rdx, rax
0x18000467b  mov     rcx, rdx; StackCookie
0x18000467e  jmp     __security_check_cookie
```
