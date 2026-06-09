# __GSHandlerCheckCommon

- ea: `0x18000a700`
- end: `0x18000a763`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a6dc`

## callees

- `0x180003bb0`
- `0x18000a700`

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
0x18000a700  mov     r10, rcx
0x18000a703  mov     r11, rdx
0x18000a706  mov     ecx, [r8]
0x18000a709  and     ecx, 0FFFFFFF8h
0x18000a70c  test    byte ptr [r8], 4
0x18000a710  jz      short loc_18000A727
0x18000a712  mov     eax, [r8+8]
0x18000a716  movsxd  r9, dword ptr [r8+4]
0x18000a71a  neg     eax
0x18000a71c  movsxd  rdx, eax
0x18000a71f  add     r9, r10
0x18000a722  and     r9, rdx
0x18000a725  jmp     short loc_18000A72A
0x18000a727  mov     r9, r10
0x18000a72a  movsxd  rax, ecx
0x18000a72d  mov     rdx, [rax+r9]
0x18000a731  mov     rax, [r11+10h]
0x18000a735  mov     ecx, [rax+8]
0x18000a738  mov     rax, [r11+8]
0x18000a73c  test    byte ptr [rcx+rax+3], 0Fh
0x18000a741  jz      short loc_18000A755
0x18000a743  movzx   eax, byte ptr [rcx+rax+3]
0x18000a748  mov     ecx, 0FFFFFFF0h
0x18000a74d  and     rax, rcx
0x18000a750  add     rax, r10
0x18000a753  jmp     short loc_18000A758
0x18000a755  mov     rax, r10
0x18000a758  xor     rdx, rax
0x18000a75b  mov     rcx, rdx; StackCookie
0x18000a75e  jmp     __security_check_cookie
```
