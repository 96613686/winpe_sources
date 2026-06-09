# __GSHandlerCheckCommon

- ea: `0x1800047c4`
- end: `0x180004827`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800047a0`

## callees

- `0x1800047c4`
- `0x180004880`

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
0x1800047c4  mov     r10, rcx
0x1800047c7  mov     r11, rdx
0x1800047ca  mov     ecx, [r8]
0x1800047cd  and     ecx, 0FFFFFFF8h
0x1800047d0  test    byte ptr [r8], 4
0x1800047d4  jz      short loc_1800047EB
0x1800047d6  mov     eax, [r8+8]
0x1800047da  movsxd  r9, dword ptr [r8+4]
0x1800047de  neg     eax
0x1800047e0  movsxd  rdx, eax
0x1800047e3  add     r9, r10
0x1800047e6  and     r9, rdx
0x1800047e9  jmp     short loc_1800047EE
0x1800047eb  mov     r9, r10
0x1800047ee  movsxd  rax, ecx
0x1800047f1  mov     rdx, [rax+r9]
0x1800047f5  mov     rax, [r11+10h]
0x1800047f9  mov     ecx, [rax+8]
0x1800047fc  mov     rax, [r11+8]
0x180004800  test    byte ptr [rcx+rax+3], 0Fh
0x180004805  jz      short loc_180004819
0x180004807  movzx   eax, byte ptr [rcx+rax+3]
0x18000480c  mov     ecx, 0FFFFFFF0h
0x180004811  and     rax, rcx
0x180004814  add     rax, r10
0x180004817  jmp     short loc_18000481C
0x180004819  mov     rax, r10
0x18000481c  xor     rdx, rax
0x18000481f  mov     rcx, rdx; StackCookie
0x180004822  jmp     __security_check_cookie
```
