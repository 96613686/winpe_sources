# ComputeSizeOfSubnetFilterInfoRequired

- ea: `0x1400143e4`
- end: `0x14001441a`
- name: `ComputeSizeOfSubnetFilterInfoRequired`
- size: `54`
- prototype: `__int64 __fastcall(unsigned int, int, _DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001324c`
- `0x140014964`
- `0x140014c7c`

## callees

- `0x1400143e4`

## pseudocode

```c
__int64 __fastcall ComputeSizeOfSubnetFilterInfoRequired(unsigned int a1, int a2, _DWORD *a3)
{
  unsigned __int64 v3; // r9
  __int64 result; // rax

  v3 = a1 * ((-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 200);
  if ( v3 > 0xFFFFFFFF || (int)v3 + 8 < (unsigned int)v3 )
    return 3221225621LL;
  result = 0;
  *a3 = v3 + 8;
  return result;
}

```

## disassembly

```asm
0x1400143e4  neg     edx
0x1400143e6  mov     eax, ecx
0x1400143e8  sbb     r9, r9
0x1400143eb  and     r9, 0FFFFFFFFFFFFFFF0h
0x1400143ef  add     r9, 0C8h
0x1400143f6  imul    r9, rax
0x1400143fa  mov     eax, 0FFFFFFFFh
0x1400143ff  cmp     r9, rax
0x140014402  ja      short loc_140014414
0x140014404  lea     ecx, [r9+8]
0x140014408  cmp     ecx, r9d
0x14001440b  jb      short loc_140014414
0x14001440d  xor     eax, eax
0x14001440f  mov     [r8], ecx
0x140014412  retn
0x140014414  mov     eax, 0C0000095h
0x140014419  retn
```
