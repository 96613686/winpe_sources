# __GSHandlerCheckCommon

- ea: `0x14000261c`
- end: `0x14000268c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400025f8`

## callees

- `0x14000261c`
- `0x140002750`

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
0x14000261c  sub     rsp, 28h
0x140002620  mov     eax, [r8]
0x140002623  mov     r10, rcx
0x140002626  mov     ecx, eax
0x140002628  mov     r11, rdx
0x14000262b  and     ecx, 0FFFFFFF8h
0x14000262e  test    al, 4
0x140002630  jz      short loc_140002647
0x140002632  mov     eax, [r8+8]
0x140002636  movsxd  r9, dword ptr [r8+4]
0x14000263a  neg     eax
0x14000263c  movsxd  rdx, eax
0x14000263f  add     r9, r10
0x140002642  and     r9, rdx
0x140002645  jmp     short loc_14000264A
0x140002647  mov     r9, r10
0x14000264a  movsxd  rax, ecx
0x14000264d  mov     rdx, [rax+r9]
0x140002651  mov     rax, [r11+10h]
0x140002655  mov     ecx, [rax+8]
0x140002658  mov     rax, [r11+8]
0x14000265c  movzx   r8d, byte ptr [rcx+rax+3]
0x140002662  test    r8b, 0Fh
0x140002666  jz      short loc_140002678
0x140002668  mov     eax, r8d
0x14000266b  mov     ecx, 0FFFFFFF0h
0x140002670  and     rax, rcx
0x140002673  add     rax, r10
0x140002676  jmp     short loc_14000267B
0x140002678  mov     rax, r10
0x14000267b  xor     rdx, rax
0x14000267e  mov     rcx, rdx; StackCookie
0x140002681  call    __security_check_cookie
0x140002686  add     rsp, 28h
0x14000268a  retn
```
