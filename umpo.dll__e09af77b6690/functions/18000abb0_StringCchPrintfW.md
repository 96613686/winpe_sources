# StringCchPrintfW

- ea: `0x18000abb0`
- end: `0x18000ac2d`
- name: `StringCchPrintfW`
- size: `125`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180011c1c`
- `0x180012254`
- `0x18001257c`

## callees

- `0x18000abb0`
- `0x180010954`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  size_t v4; // rbx
  HRESULT v5; // edi
  int v6; // eax
  HRESULT result; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -2147024809;
    *pszDest = 0;
  }
  else
  {
    v4 = cchDest - 1;
    v5 = 0;
    v6 = vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
    if ( v6 < 0 || v6 > v4 )
    {
      pszDest[v4] = 0;
      return -2147024774;
    }
    else if ( v6 == v4 )
    {
      pszDest[v4] = 0;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000abb0  mov     [rsp+arg_10], r8
0x18000abb5  mov     qword ptr [rsp+Args], r9
0x18000abba  push    rsi
0x18000abbb  push    rdi
0x18000abbc  sub     rsp, 38h
0x18000abc0  mov     rsi, rcx
0x18000abc3  test    rdx, rdx
0x18000abc6  jz      short loc_18000AC1C
0x18000abc8  cmp     rdx, 7FFFFFFFh
0x18000abcf  ja      short loc_18000AC0F
0x18000abd1  mov     [rsp+48h+var_18], rbx
0x18000abd6  lea     r9, [rsp+48h+Args]; Args
0x18000abdb  lea     rbx, [rdx-1]
0x18000abdf  xor     edi, edi
0x18000abe1  mov     rdx, rbx; BufferCount
0x18000abe4  call    _vsnwprintf
0x18000abe9  test    eax, eax
0x18000abeb  js      short loc_18000AC04
0x18000abed  cdqe
0x18000abef  cmp     rax, rbx
0x18000abf2  ja      short loc_18000AC04
0x18000abf4  jz      short loc_18000AC16
0x18000abf6  mov     rbx, [rsp+48h+var_18]
0x18000abfb  mov     eax, edi
0x18000abfd  add     rsp, 38h
0x18000ac01  pop     rdi
0x18000ac02  pop     rsi
0x18000ac03  retn
0x18000ac04  mov     [rsi+rbx*2], di
0x18000ac08  mov     edi, 8007007Ah
0x18000ac0d  jmp     short loc_18000ABF6
0x18000ac0f  mov     eax, 80070057h
0x18000ac14  jmp     short loc_18000AC26
0x18000ac16  mov     [rsi+rbx*2], di
0x18000ac1a  jmp     short loc_18000ABF6
0x18000ac1c  mov     eax, 80070057h
0x18000ac21  test    rdx, rdx
0x18000ac24  jz      short loc_18000ABFD
0x18000ac26  xor     edi, edi
0x18000ac28  mov     [rcx], di
0x18000ac2b  jmp     short loc_18000ABFD
```
