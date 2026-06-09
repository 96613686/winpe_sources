# __GSHandlerCheckCommon

- ea: `0x18000c310`
- end: `0x18000c373`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c2ec`

## callees

- `0x18000c310`
- `0x18000c3d0`

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
0x18000c310  mov     r10, rcx
0x18000c313  mov     r11, rdx
0x18000c316  mov     ecx, [r8]
0x18000c319  and     ecx, 0FFFFFFF8h
0x18000c31c  test    byte ptr [r8], 4
0x18000c320  jz      short loc_18000C337
0x18000c322  mov     eax, [r8+8]
0x18000c326  movsxd  r9, dword ptr [r8+4]
0x18000c32a  neg     eax
0x18000c32c  movsxd  rdx, eax
0x18000c32f  add     r9, r10
0x18000c332  and     r9, rdx
0x18000c335  jmp     short loc_18000C33A
0x18000c337  mov     r9, r10
0x18000c33a  movsxd  rax, ecx
0x18000c33d  mov     rdx, [rax+r9]
0x18000c341  mov     rax, [r11+10h]
0x18000c345  mov     ecx, [rax+8]
0x18000c348  mov     rax, [r11+8]
0x18000c34c  test    byte ptr [rcx+rax+3], 0Fh
0x18000c351  jz      short loc_18000C365
0x18000c353  movzx   eax, byte ptr [rcx+rax+3]
0x18000c358  mov     ecx, 0FFFFFFF0h
0x18000c35d  and     rax, rcx
0x18000c360  add     rax, r10
0x18000c363  jmp     short loc_18000C368
0x18000c365  mov     rax, r10
0x18000c368  xor     rdx, rax
0x18000c36b  mov     rcx, rdx; StackCookie
0x18000c36e  jmp     __security_check_cookie
```
