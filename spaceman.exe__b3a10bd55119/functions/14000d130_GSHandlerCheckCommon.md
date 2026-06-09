# __GSHandlerCheckCommon

- ea: `0x14000d130`
- end: `0x14000d193`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d10c`

## callees

- `0x14000d130`
- `0x14000d1f0`

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
0x14000d130  mov     r10, rcx
0x14000d133  mov     r11, rdx
0x14000d136  mov     ecx, [r8]
0x14000d139  and     ecx, 0FFFFFFF8h
0x14000d13c  test    byte ptr [r8], 4
0x14000d140  jz      short loc_14000D157
0x14000d142  mov     eax, [r8+8]
0x14000d146  movsxd  r9, dword ptr [r8+4]
0x14000d14a  neg     eax
0x14000d14c  movsxd  rdx, eax
0x14000d14f  add     r9, r10
0x14000d152  and     r9, rdx
0x14000d155  jmp     short loc_14000D15A
0x14000d157  mov     r9, r10
0x14000d15a  movsxd  rax, ecx
0x14000d15d  mov     rdx, [rax+r9]
0x14000d161  mov     rax, [r11+10h]
0x14000d165  mov     ecx, [rax+8]
0x14000d168  mov     rax, [r11+8]
0x14000d16c  test    byte ptr [rcx+rax+3], 0Fh
0x14000d171  jz      short loc_14000D185
0x14000d173  movzx   eax, byte ptr [rcx+rax+3]
0x14000d178  mov     ecx, 0FFFFFFF0h
0x14000d17d  and     rax, rcx
0x14000d180  add     rax, r10
0x14000d183  jmp     short loc_14000D188
0x14000d185  mov     rax, r10
0x14000d188  xor     rdx, rax
0x14000d18b  mov     rcx, rdx; StackCookie
0x14000d18e  jmp     __security_check_cookie
```
