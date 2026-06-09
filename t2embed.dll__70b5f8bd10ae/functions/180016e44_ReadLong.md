# ReadLong

- ea: `0x180016e44`
- end: `0x180016e92`
- name: `ReadLong`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f298`
- `0x1800156e8`
- `0x18001b538`
- `0x18001ce6c`

## callees

- `0x180016e44`

## pseudocode

```c
__int64 __fastcall ReadLong(__int64 a1, int *a2, unsigned int a3)
{
  __int64 result; // rax

  if ( !*(_QWORD *)a1 || a3 + 4 < a3 || a3 + 4 > *(_DWORD *)(a1 + 8) )
    return 1001;
  result = 0;
  *a2 = *(unsigned __int8 *)(a3 + *(_QWORD *)a1 + 3LL)
      | ((*(unsigned __int8 *)(a3 + *(_QWORD *)a1 + 2LL)
        | ((*(unsigned __int8 *)(a3 + *(_QWORD *)a1 + 1LL) | (*(unsigned __int8 *)(a3 + *(_QWORD *)a1) << 8)) << 8)) << 8);
  return result;
}

```

## disassembly

```asm
0x180016e44  mov     r9, [rcx]
0x180016e47  mov     r10, rdx
0x180016e4a  test    r9, r9
0x180016e4d  jz      short loc_180016E5D
0x180016e4f  lea     eax, [r8+4]
0x180016e53  cmp     eax, r8d
0x180016e56  jb      short loc_180016E5D
0x180016e58  cmp     eax, [rcx+8]
0x180016e5b  jbe     short loc_180016E63
0x180016e5d  mov     eax, 3E9h
0x180016e62  retn
0x180016e63  mov     ecx, r8d
0x180016e66  movzx   eax, byte ptr [rcx+r9+1]
0x180016e6c  movzx   edx, byte ptr [rcx+r9]
0x180016e71  shl     edx, 8
0x180016e74  or      edx, eax
0x180016e76  movzx   eax, byte ptr [rcx+r9+2]
0x180016e7c  shl     edx, 8
0x180016e7f  or      edx, eax
0x180016e81  movzx   eax, byte ptr [rcx+r9+3]
0x180016e87  shl     edx, 8
0x180016e8a  or      edx, eax
0x180016e8c  xor     eax, eax
0x180016e8e  mov     [r10], edx
0x180016e91  retn
```
