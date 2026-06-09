# MinAsn1ParseRfc3161TimeStampToken

- ea: `0x18004cfb4`
- end: `0x18004cff5`
- name: `MinAsn1ParseRfc3161TimeStampToken`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015360`

## callees

- `0x18004cfb4`
- `0x18004de78`

## pseudocode

```c
__int64 __fastcall MinAsn1ParseRfc3161TimeStampToken(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  unsigned int v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = 14;
  result = MinAsn1ExtractValues(*(_BYTE **)(a1 + 8), *(_DWORD *)a1, &v4, (__int64)&qword_1800364C0, 6u, a2);
  if ( (int)result > 0 )
    return *(unsigned int *)(a2 + 16);
  return result;
}

```

## disassembly

```asm
0x18004cfb4  mov     rax, rsp
0x18004cfb7  push    rbx
0x18004cfb8  sub     rsp, 30h
0x18004cfbc  mov     [rax-10h], rdx
0x18004cfc0  lea     r9, qword_1800364C0
0x18004cfc7  mov     rbx, rdx
0x18004cfca  mov     dword ptr [rax+8], 0Eh
0x18004cfd1  mov     edx, [rcx]
0x18004cfd3  lea     r8, [rax+8]
0x18004cfd7  mov     rcx, [rcx+8]
0x18004cfdb  mov     dword ptr [rax-18h], 6
0x18004cfe2  call    MinAsn1ExtractValues
0x18004cfe7  test    eax, eax
0x18004cfe9  jle     short loc_18004CFEE
0x18004cfeb  mov     eax, [rbx+10h]
0x18004cfee  add     rsp, 30h
0x18004cff2  pop     rbx
0x18004cff3  retn
```
