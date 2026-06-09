# StringCchLengthW

- ea: `0x18003ae3c`
- end: `0x18003ae98`
- name: `StringCchLengthW`
- size: `92`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## callees

- `0x18003ae3c`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  __int64 v3; // rdx
  HRESULT result; // eax

  if ( !psz )
  {
    result = -2147024809;
    goto LABEL_12;
  }
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*psz )
      break;
    ++psz;
    --v3;
  }
  while ( v3 );
  result = v3 == 0 ? 0x80070057 : 0;
  if ( !pcchLength )
  {
    if ( v3 )
      return result;
LABEL_12:
    if ( !pcchLength )
      return result;
    goto LABEL_13;
  }
  if ( v3 )
  {
    *pcchLength = 0x7FFFFFFF - v3;
    return result;
  }
  *pcchLength = 0;
LABEL_13:
  *pcchLength = 0;
  return result;
}

```

## disassembly

```asm
0x18003ae3c  xor     r10d, r10d
0x18003ae3f  test    rcx, rcx
0x18003ae42  jz      short loc_18003AE8A
0x18003ae44  mov     r9d, 7FFFFFFFh
0x18003ae4a  mov     edx, r9d
0x18003ae4d  cmp     [rcx], r10w
0x18003ae51  jz      short loc_18003AE5D
0x18003ae53  add     rcx, 2
0x18003ae57  sub     rdx, 1
0x18003ae5b  jnz     short loc_18003AE4D
0x18003ae5d  mov     rax, rdx
0x18003ae60  neg     rax
0x18003ae63  sbb     eax, eax
0x18003ae65  not     eax
0x18003ae67  and     eax, 80070057h
0x18003ae6c  test    r8, r8
0x18003ae6f  jz      short loc_18003AE83
0x18003ae71  test    rdx, rdx
0x18003ae74  jz      short loc_18003AE7E
0x18003ae76  sub     r9, rdx
0x18003ae79  mov     [r8], r9
0x18003ae7c  retn
0x18003ae7e  mov     [r8], r10
0x18003ae81  jmp     short loc_18003AE94
0x18003ae83  test    rdx, rdx
0x18003ae86  jnz     short locret_18003AE97
0x18003ae88  jmp     short loc_18003AE8F
0x18003ae8a  mov     eax, 80070057h
0x18003ae8f  test    r8, r8
0x18003ae92  jz      short locret_18003AE97
0x18003ae94  mov     [r8], r10
0x18003ae97  retn
```
