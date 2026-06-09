# __GSHandlerCheckCommon

- ea: `0x1800027f8`
- end: `0x18000285b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800027d4`

## callees

- `0x1800027f8`
- `0x180002890`

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
0x1800027f8  mov     r10, rcx
0x1800027fb  mov     r11, rdx
0x1800027fe  mov     ecx, [r8]
0x180002801  and     ecx, 0FFFFFFF8h
0x180002804  test    byte ptr [r8], 4
0x180002808  jz      short loc_18000281F
0x18000280a  mov     eax, [r8+8]
0x18000280e  movsxd  r9, dword ptr [r8+4]
0x180002812  neg     eax
0x180002814  movsxd  rdx, eax
0x180002817  add     r9, r10
0x18000281a  and     r9, rdx
0x18000281d  jmp     short loc_180002822
0x18000281f  mov     r9, r10
0x180002822  movsxd  rax, ecx
0x180002825  mov     rdx, [rax+r9]
0x180002829  mov     rax, [r11+10h]
0x18000282d  mov     ecx, [rax+8]
0x180002830  mov     rax, [r11+8]
0x180002834  test    byte ptr [rcx+rax+3], 0Fh
0x180002839  jz      short loc_18000284D
0x18000283b  movzx   eax, byte ptr [rcx+rax+3]
0x180002840  mov     ecx, 0FFFFFFF0h
0x180002845  and     rax, rcx
0x180002848  add     rax, r10
0x18000284b  jmp     short loc_180002850
0x18000284d  mov     rax, r10
0x180002850  xor     rdx, rax
0x180002853  mov     rcx, rdx; StackCookie
0x180002856  jmp     __security_check_cookie
```
