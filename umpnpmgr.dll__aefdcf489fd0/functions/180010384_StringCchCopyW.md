# StringCchCopyW

- ea: `0x180010384`
- end: `0x1800103ef`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cba0`
- `0x18000fe68`
- `0x180016424`
- `0x180016818`
- `0x180016dd4`
- `0x1800180b0`

## callees

- `0x180010384`

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
0x180010384  xor     r10d, r10d
0x180010387  mov     r9, rcx
0x18001038a  test    rdx, rdx
0x18001038d  jz      short loc_1800103E0
0x18001038f  cmp     rdx, 7FFFFFFFh
0x180010396  jbe     short loc_18001039F
0x180010398  mov     eax, 80070057h
0x18001039d  jmp     short loc_1800103EA
0x18001039f  mov     eax, 7FFFFFFEh
0x1800103a4  test    rax, rax
0x1800103a7  jz      short loc_1800103C7
0x1800103a9  movzx   ecx, word ptr [r8]
0x1800103ad  test    cx, cx
0x1800103b0  jz      short loc_1800103C7
0x1800103b2  mov     [r9], cx
0x1800103b6  add     r8, 2
0x1800103ba  add     r9, 2
0x1800103be  dec     rax
0x1800103c1  sub     rdx, 1
0x1800103c5  jnz     short loc_1800103A4
0x1800103c7  test    rdx, rdx
0x1800103ca  lea     rcx, [r9-2]
0x1800103ce  cmovnz  rcx, r9
0x1800103d2  neg     rdx
0x1800103d5  sbb     eax, eax
0x1800103d7  not     eax
0x1800103d9  and     eax, 8007007Ah
0x1800103de  jmp     short loc_1800103EA
0x1800103e0  mov     eax, 80070057h
0x1800103e5  test    rdx, rdx
0x1800103e8  jz      short locret_1800103EE
0x1800103ea  mov     [rcx], r10w
0x1800103ee  retn
```
