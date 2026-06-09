# StringCchCopyW

- ea: `0x18000e970`
- end: `0x18000e9da`
- name: `StringCchCopyW`
- size: `106`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000259c`
- `0x180002708`
- `0x18000e8a8`

## callees

- `0x18000e970`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // r9
  signed __int64 v4; // r10
  wchar_t v5; // ax
  STRSAFE_LPWSTR v6; // rax
  HRESULT result; // eax

  if ( cchDest - 1 > 0x7FFFFFFE )
  {
    result = -2147024809;
    if ( cchDest )
      *pszDest = 0;
  }
  else
  {
    v3 = 2147483646 - cchDest;
    v4 = (char *)pszSrc - (char *)pszDest;
    do
    {
      if ( !(v3 + cchDest) )
        break;
      v5 = *(STRSAFE_LPWSTR)((char *)pszDest + v4);
      if ( !v5 )
        break;
      *pszDest++ = v5;
      --cchDest;
    }
    while ( cchDest );
    v6 = pszDest - 1;
    if ( cchDest )
      v6 = pszDest;
    *v6 = 0;
    return cchDest == 0 ? 0x8007007A : 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000e970  lea     rax, [rdx-1]
0x18000e974  mov     r9d, 7FFFFFFEh
0x18000e97a  mov     r10, r8
0x18000e97d  cmp     rax, r9
0x18000e980  ja      short loc_18000E9C8
0x18000e982  sub     r9, rdx
0x18000e985  sub     r10, rcx
0x18000e988  xor     r8d, r8d
0x18000e98b  lea     rax, [r9+rdx]
0x18000e98f  test    rax, rax
0x18000e992  jz      short loc_18000E9AB
0x18000e994  movzx   eax, word ptr [r10+rcx]
0x18000e999  test    ax, ax
0x18000e99c  jz      short loc_18000E9AB
0x18000e99e  mov     [rcx], ax
0x18000e9a1  add     rcx, 2
0x18000e9a5  sub     rdx, 1
0x18000e9a9  jnz     short loc_18000E98B
0x18000e9ab  test    rdx, rdx
0x18000e9ae  lea     rax, [rcx-2]
0x18000e9b2  cmovnz  rax, rcx
0x18000e9b6  neg     rdx
0x18000e9b9  mov     [rax], r8w
0x18000e9bd  sbb     eax, eax
0x18000e9bf  not     eax
0x18000e9c1  and     eax, 8007007Ah
0x18000e9c6  retn
0x18000e9c8  xor     r8d, r8d
0x18000e9cb  mov     eax, 80070057h
0x18000e9d0  test    rdx, rdx
0x18000e9d3  jz      short locret_18000E9D9
0x18000e9d5  mov     [rcx], r8w
0x18000e9d9  retn
```
