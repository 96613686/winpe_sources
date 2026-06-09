# StringCbCopyW

- ea: `0x18000b4f0`
- end: `0x18000b55c`
- name: `StringCbCopyW`
- size: `108`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031d0`
- `0x180005970`
- `0x180005de4`
- `0x180007e10`
- `0x180008c50`
- `0x1800091e0`
- `0x180009740`
- `0x18000a370`
- `0x18000a770`
- `0x18000b060`
- `0x18000c350`
- `0x18000c628`
- `0x18000d9e4`
- `0x180010ffc`
- `0x180011c8c`
- `0x180017624`
- `0x18001bd74`
- `0x18001c6e8`
- `0x18001ca70`
- `0x18001dfc0`
- `0x180021008`
- `0x180021628`
- `0x18002b1e0`

## callees

- `0x18000b4f0`

## pseudocode

```c
HRESULT __stdcall StringCbCopyW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // rdx
  HRESULT result; // eax
  __int64 v5; // rax
  STRSAFE_LPWSTR v6; // rax

  v3 = cbDest >> 1;
  if ( !v3 )
    return -2147024809;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = pszDest - 1;
    if ( v3 )
      v6 = pszDest;
    *v6 = 0;
    return v3 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b4f0  xor     r9d, r9d
0x18000b4f3  shr     rdx, 1
0x18000b4f6  jz      short loc_18000B54D
0x18000b4f8  cmp     rdx, 7FFFFFFFh
0x18000b4ff  jbe     short loc_18000B508
0x18000b501  mov     eax, 80070057h
0x18000b506  jmp     short loc_18000B557
0x18000b508  mov     eax, 7FFFFFFEh
0x18000b50d  test    rax, rax
0x18000b510  jz      short loc_18000B531
0x18000b512  movzx   r10d, word ptr [r8]
0x18000b516  test    r10w, r10w
0x18000b51a  jz      short loc_18000B531
0x18000b51c  mov     [rcx], r10w
0x18000b520  add     r8, 2
0x18000b524  add     rcx, 2
0x18000b528  dec     rax
0x18000b52b  sub     rdx, 1
0x18000b52f  jnz     short loc_18000B50D
0x18000b531  test    rdx, rdx
0x18000b534  lea     rax, [rcx-2]
0x18000b538  cmovnz  rax, rcx
0x18000b53c  neg     rdx
0x18000b53f  mov     [rax], r9w
0x18000b543  sbb     eax, eax
0x18000b545  not     eax
0x18000b547  and     eax, 8007007Ah
0x18000b54c  retn
0x18000b54d  mov     eax, 80070057h
0x18000b552  test    rdx, rdx
0x18000b555  jz      short locret_18000B55B
0x18000b557  mov     [rcx], r9w
0x18000b55b  retn
```
