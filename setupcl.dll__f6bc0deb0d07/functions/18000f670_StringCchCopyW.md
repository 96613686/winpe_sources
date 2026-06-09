# StringCchCopyW

- ea: `0x18000f670`
- end: `0x18000f6db`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e834`
- `0x180013e38`
- `0x180013e8c`
- `0x180013ee0`
- `0x180013f98`
- `0x180013fec`
- `0x180014a40`
- `0x180014b1c`
- `0x180014b70`
- `0x180015130`
- `0x1800156f8`

## callees

- `0x18000f670`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  HRESULT result; // eax
  __int64 v5; // rax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v5;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x18000f670  xor     r10d, r10d
0x18000f673  mov     r9, rcx
0x18000f676  test    rdx, rdx
0x18000f679  jz      short loc_18000F6CC
0x18000f67b  cmp     rdx, 7FFFFFFFh
0x18000f682  jbe     short loc_18000F68B
0x18000f684  mov     eax, 80070057h
0x18000f689  jmp     short loc_18000F6D6
0x18000f68b  mov     eax, 7FFFFFFEh
0x18000f690  test    rax, rax
0x18000f693  jz      short loc_18000F6B3
0x18000f695  movzx   ecx, word ptr [r8]
0x18000f699  test    cx, cx
0x18000f69c  jz      short loc_18000F6B3
0x18000f69e  mov     [r9], cx
0x18000f6a2  add     r8, 2
0x18000f6a6  add     r9, 2
0x18000f6aa  dec     rax
0x18000f6ad  sub     rdx, 1
0x18000f6b1  jnz     short loc_18000F690
0x18000f6b3  test    rdx, rdx
0x18000f6b6  lea     rcx, [r9-2]
0x18000f6ba  cmovnz  rcx, r9
0x18000f6be  neg     rdx
0x18000f6c1  sbb     eax, eax
0x18000f6c3  not     eax
0x18000f6c5  and     eax, 8007007Ah
0x18000f6ca  jmp     short loc_18000F6D6
0x18000f6cc  mov     eax, 80070057h
0x18000f6d1  test    rdx, rdx
0x18000f6d4  jz      short locret_18000F6DA
0x18000f6d6  mov     [rcx], r10w
0x18000f6da  retn
```
