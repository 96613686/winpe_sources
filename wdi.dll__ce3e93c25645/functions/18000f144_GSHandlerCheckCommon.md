# __GSHandlerCheckCommon

- ea: `0x18000f144`
- end: `0x18000f1a7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f120`

## callees

- `0x18000f144`
- `0x18000f1f0`

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
0x18000f144  mov     r10, rcx
0x18000f147  mov     r11, rdx
0x18000f14a  mov     ecx, [r8]
0x18000f14d  and     ecx, 0FFFFFFF8h
0x18000f150  test    byte ptr [r8], 4
0x18000f154  jz      short loc_18000F16B
0x18000f156  mov     eax, [r8+8]
0x18000f15a  movsxd  r9, dword ptr [r8+4]
0x18000f15e  neg     eax
0x18000f160  movsxd  rdx, eax
0x18000f163  add     r9, r10
0x18000f166  and     r9, rdx
0x18000f169  jmp     short loc_18000F16E
0x18000f16b  mov     r9, r10
0x18000f16e  movsxd  rax, ecx
0x18000f171  mov     rdx, [rax+r9]
0x18000f175  mov     rax, [r11+10h]
0x18000f179  mov     ecx, [rax+8]
0x18000f17c  mov     rax, [r11+8]
0x18000f180  test    byte ptr [rcx+rax+3], 0Fh
0x18000f185  jz      short loc_18000F199
0x18000f187  movzx   eax, byte ptr [rcx+rax+3]
0x18000f18c  mov     ecx, 0FFFFFFF0h
0x18000f191  and     rax, rcx
0x18000f194  add     rax, r10
0x18000f197  jmp     short loc_18000F19C
0x18000f199  mov     rax, r10
0x18000f19c  xor     rdx, rax
0x18000f19f  mov     rcx, rdx; StackCookie
0x18000f1a2  jmp     __security_check_cookie
```
