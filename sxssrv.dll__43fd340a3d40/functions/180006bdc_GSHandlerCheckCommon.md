# __GSHandlerCheckCommon

- ea: `0x180006bdc`
- end: `0x180006c3f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006bb8`
- `0x180006c48`

## callees

- `0x180006bdc`
- `0x180006cf0`

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
0x180006bdc  mov     r10, rcx
0x180006bdf  mov     r11, rdx
0x180006be2  mov     ecx, [r8]
0x180006be5  and     ecx, 0FFFFFFF8h
0x180006be8  test    byte ptr [r8], 4
0x180006bec  jz      short loc_180006C03
0x180006bee  mov     eax, [r8+8]
0x180006bf2  movsxd  r9, dword ptr [r8+4]
0x180006bf6  neg     eax
0x180006bf8  movsxd  rdx, eax
0x180006bfb  add     r9, r10
0x180006bfe  and     r9, rdx
0x180006c01  jmp     short loc_180006C06
0x180006c03  mov     r9, r10
0x180006c06  movsxd  rax, ecx
0x180006c09  mov     rdx, [rax+r9]
0x180006c0d  mov     rax, [r11+10h]
0x180006c11  mov     ecx, [rax+8]
0x180006c14  mov     rax, [r11+8]
0x180006c18  test    byte ptr [rcx+rax+3], 0Fh
0x180006c1d  jz      short loc_180006C31
0x180006c1f  movzx   eax, byte ptr [rcx+rax+3]
0x180006c24  mov     ecx, 0FFFFFFF0h
0x180006c29  and     rax, rcx
0x180006c2c  add     rax, r10
0x180006c2f  jmp     short loc_180006C34
0x180006c31  mov     rax, r10
0x180006c34  xor     rdx, rax
0x180006c37  mov     rcx, rdx; StackCookie
0x180006c3a  jmp     __security_check_cookie
```
