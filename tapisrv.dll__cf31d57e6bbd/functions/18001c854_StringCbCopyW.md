# StringCbCopyW

- ea: `0x18001c854`
- end: `0x18001c89d`
- name: `StringCbCopyW`
- size: `73`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038cc`
- `0x180007028`
- `0x180008d20`
- `0x180009010`
- `0x18000d180`
- `0x18000d980`
- `0x18000dfc0`
- `0x18000e420`
- `0x180010750`
- `0x180014710`
- `0x180017be0`
- `0x18001fb28`
- `0x180022210`
- `0x180022580`
- `0x180023060`
- `0x180026d60`
- `0x18002bc98`
- `0x18002c8fc`
- `0x18002fc10`
- `0x180030218`
- `0x180030f40`
- `0x180031650`
- `0x1800330a8`
- `0x180034154`
- `0x180037264`
- `0x180037344`
- `0x18003a938`
- `0x18003a9ec`
- `0x18003cf88`

## callees

- `0x18001c854`
- `0x18001c930`

## pseudocode

```c
HRESULT __stdcall StringCbCopyW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx

  if ( !(cbDest >> 1) )
    return -2147024809;
  if ( cbDest >> 1 <= 0x7FFFFFFF )
    return StringCopyWorkerW(pszDest, cbDest >> 1, (size_t *)pszSrc, pszSrc, 0x7FFFFFFEu);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x18001c854  sub     rsp, 38h
0x18001c858  mov     rax, rdx
0x18001c85b  shr     rax, 1
0x18001c85e  jz      short loc_18001C887
0x18001c860  cmp     rax, 7FFFFFFFh
0x18001c866  jbe     short loc_18001C86F
0x18001c868  mov     edx, 80070057h
0x18001c86d  jmp     short loc_18001C891
0x18001c86f  mov     r9, r8; pszSrc
0x18001c872  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18001c87b  mov     rdx, rax; cchDest
0x18001c87e  call    StringCopyWorkerW
0x18001c883  mov     edx, eax
0x18001c885  jmp     short loc_18001C896
0x18001c887  mov     edx, 80070057h
0x18001c88c  test    rax, rax
0x18001c88f  jz      short loc_18001C896
0x18001c891  xor     eax, eax
0x18001c893  mov     [rcx], ax
0x18001c896  mov     eax, edx
0x18001c898  add     rsp, 38h
0x18001c89c  retn
```
