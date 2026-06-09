# CaseInsensitiveCompareEnumProc

- ea: `0x180025cb0`
- end: `0x180025d0e`
- name: `CaseInsensitiveCompareEnumProc`
- size: `94`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180024910`
- `0x180025cb0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180025cd8`
- `KERNEL32!CompareStringOrdinal` at `0x180025cd8`

## pseudocode

```c
__int64 __fastcall CaseInsensitiveCompareEnumProc(STRSAFE_LPCWSTR pszSrc, __int64 a2)
{
  unsigned int v3; // ebx

  v3 = 1;
  if ( CompareStringOrdinal(pszSrc, -1, *(LPCWCH *)(a2 + 24), -1, 1) == 2 )
  {
    v3 = 0;
    *(_DWORD *)a2 = StringCchCopyW(*(STRSAFE_LPWSTR *)(a2 + 8), *(int *)(a2 + 16), pszSrc) >= 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180025cb0  mov     [rsp+arg_0], rbx
0x180025cb5  mov     [rsp+arg_8], rsi
0x180025cba  push    rdi
0x180025cbb  sub     rsp, 30h
0x180025cbf  mov     rdi, rdx
0x180025cc2  mov     ebx, 1
0x180025cc7  or      edx, 0FFFFFFFFh; cchCount1
0x180025cca  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x180025cce  mov     r9d, edx; cchCount2
0x180025cd1  mov     rsi, rcx
0x180025cd4  mov     r8, [rdi+18h]; lpString2
0x180025cd8  call    cs:__imp_CompareStringOrdinal
0x180025cde  cmp     eax, 2
0x180025ce1  jnz     short loc_180025CFC
0x180025ce3  movsxd  rdx, dword ptr [rdi+10h]; cchDest
0x180025ce7  mov     r8, rsi; pszSrc
0x180025cea  mov     rcx, [rdi+8]; pszDest
0x180025cee  xor     ebx, ebx
0x180025cf0  call    StringCchCopyW
0x180025cf5  not     eax
0x180025cf7  shr     eax, 1Fh
0x180025cfa  mov     [rdi], eax
0x180025cfc  mov     rsi, [rsp+38h+arg_8]
0x180025d01  mov     eax, ebx
0x180025d03  mov     rbx, [rsp+38h+arg_0]
0x180025d08  add     rsp, 30h
0x180025d0c  pop     rdi
0x180025d0d  retn
```
