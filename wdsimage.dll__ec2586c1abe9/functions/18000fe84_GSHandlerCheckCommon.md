# __GSHandlerCheckCommon

- ea: `0x18000fe84`
- end: `0x18000fedf`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fe60`

## callees

- `0x18000fe84`
- `0x18000ff10`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x18000fe84  push    rbx
0x18000fe86  mov     r11d, [r8]
0x18000fe89  mov     rbx, rdx
0x18000fe8c  and     r11d, 0FFFFFFF8h
0x18000fe90  mov     r9, rcx
0x18000fe93  test    byte ptr [r8], 4
0x18000fe97  mov     r10, rcx
0x18000fe9a  jz      short loc_18000FEAF
0x18000fe9c  mov     eax, [r8+8]
0x18000fea0  movsxd  r10, dword ptr [r8+4]
0x18000fea4  neg     eax
0x18000fea6  add     r10, rcx
0x18000fea9  movsxd  rcx, eax
0x18000feac  and     r10, rcx
0x18000feaf  movsxd  rax, r11d
0x18000feb2  mov     rdx, [rax+r10]
0x18000feb6  mov     rax, [rbx+10h]
0x18000feba  mov     ecx, [rax+8]
0x18000febd  mov     rax, [rbx+8]
0x18000fec1  test    byte ptr [rcx+rax+3], 0Fh
0x18000fec6  jz      short loc_18000FED3
0x18000fec8  movzx   eax, byte ptr [rcx+rax+3]
0x18000fecd  and     eax, 0FFFFFFF0h
0x18000fed0  add     r9, rax
0x18000fed3  xor     r9, rdx
0x18000fed6  mov     rcx, r9; StackCookie
0x18000fed9  pop     rbx
0x18000feda  jmp     __security_check_cookie
```
