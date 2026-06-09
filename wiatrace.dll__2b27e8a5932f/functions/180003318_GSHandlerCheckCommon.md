# __GSHandlerCheckCommon

- ea: `0x180003318`
- end: `0x18000337b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800032f4`

## callees

- `0x180002980`
- `0x180003318`

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
0x180003318  mov     r10, rcx
0x18000331b  mov     r11, rdx
0x18000331e  mov     ecx, [r8]
0x180003321  and     ecx, 0FFFFFFF8h
0x180003324  test    byte ptr [r8], 4
0x180003328  jz      short loc_18000333F
0x18000332a  mov     eax, [r8+8]
0x18000332e  movsxd  r9, dword ptr [r8+4]
0x180003332  neg     eax
0x180003334  movsxd  rdx, eax
0x180003337  add     r9, r10
0x18000333a  and     r9, rdx
0x18000333d  jmp     short loc_180003342
0x18000333f  mov     r9, r10
0x180003342  movsxd  rax, ecx
0x180003345  mov     rdx, [rax+r9]
0x180003349  mov     rax, [r11+10h]
0x18000334d  mov     ecx, [rax+8]
0x180003350  mov     rax, [r11+8]
0x180003354  test    byte ptr [rcx+rax+3], 0Fh
0x180003359  jz      short loc_18000336D
0x18000335b  movzx   eax, byte ptr [rcx+rax+3]
0x180003360  mov     ecx, 0FFFFFFF0h
0x180003365  and     rax, rcx
0x180003368  add     rax, r10
0x18000336b  jmp     short loc_180003370
0x18000336d  mov     rax, r10
0x180003370  xor     rdx, rax
0x180003373  mov     rcx, rdx; StackCookie
0x180003376  jmp     __security_check_cookie
```
