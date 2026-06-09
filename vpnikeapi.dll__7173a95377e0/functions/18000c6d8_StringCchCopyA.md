# StringCchCopyA

- ea: `0x18000c6d8`
- end: `0x18000c73a`
- name: `StringCchCopyA`
- size: `98`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e14`

## callees

- `0x18000c6d8`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  __int64 v4; // rax
  STRSAFE_LPSTR v5; // rax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    v5 = pszDest - 1;
    if ( cchDest )
      v5 = pszDest;
    *v5 = 0;
    return cchDest == 0 ? 0x8007007A : 0;
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
0x18000c6d8  test    rdx, rdx
0x18000c6db  jz      short loc_18000C72C
0x18000c6dd  cmp     rdx, 7FFFFFFFh
0x18000c6e4  jbe     short loc_18000C6ED
0x18000c6e6  mov     eax, 80070057h
0x18000c6eb  jmp     short loc_18000C736
0x18000c6ed  mov     eax, 7FFFFFFEh
0x18000c6f2  test    rax, rax
0x18000c6f5  jz      short loc_18000C711
0x18000c6f7  mov     r9b, [r8]
0x18000c6fa  test    r9b, r9b
0x18000c6fd  jz      short loc_18000C711
0x18000c6ff  mov     [rcx], r9b
0x18000c702  inc     r8
0x18000c705  inc     rcx
0x18000c708  dec     rax
0x18000c70b  sub     rdx, 1
0x18000c70f  jnz     short loc_18000C6F2
0x18000c711  test    rdx, rdx
0x18000c714  lea     rax, [rcx-1]
0x18000c718  cmovnz  rax, rcx
0x18000c71c  neg     rdx
0x18000c71f  mov     byte ptr [rax], 0
0x18000c722  sbb     eax, eax
0x18000c724  not     eax
0x18000c726  and     eax, 8007007Ah
0x18000c72b  retn
0x18000c72c  mov     eax, 80070057h
0x18000c731  test    rdx, rdx
0x18000c734  jz      short locret_18000C739
0x18000c736  mov     byte ptr [rcx], 0
0x18000c739  retn
```
