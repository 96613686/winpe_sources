# StringCchPrintfW

- ea: `0x140001bc0`
- end: `0x140001c4c`
- name: `StringCchPrintfW`
- size: `140`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001970`
- `0x140006520`

## callees

- `0x140001bc0`
- `0x1400059bc`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  size_t v4; // rdi
  HRESULT v5; // ebx
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
    if ( v6 != v4 )
      return v5;
    pszDest[v4] = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001bc0  mov     [rsp+arg_10], r8
0x140001bc5  mov     qword ptr [rsp+Args], r9
0x140001bca  push    rbx
0x140001bcb  push    rsi
0x140001bcc  sub     rsp, 38h
0x140001bd0  mov     rsi, rcx
0x140001bd3  test    rdx, rdx
0x140001bd6  jz      short loc_140001C3D
0x140001bd8  cmp     rdx, 7FFFFFFFh
0x140001bdf  ja      short loc_140001C33
0x140001be1  mov     [rsp+48h+var_18], rdi
0x140001be6  lea     r9, [rsp+48h+Args]; Args
0x140001beb  lea     rdi, [rdx-1]
0x140001bef  xor     ebx, ebx
0x140001bf1  mov     rdx, rdi; BufferCount
0x140001bf4  call    _vsnwprintf
0x140001bf9  test    eax, eax
0x140001bfb  js      short loc_140001C15
0x140001bfd  cdqe
0x140001bff  cmp     rax, rdi
0x140001c02  ja      short loc_140001C15
0x140001c04  jz      short loc_140001C20
0x140001c06  mov     rdi, [rsp+48h+var_18]
0x140001c0b  mov     eax, ebx
0x140001c0d  add     rsp, 38h
0x140001c11  pop     rsi
0x140001c12  pop     rbx
0x140001c13  retn
0x140001c15  mov     [rsi+rdi*2], bx
0x140001c19  mov     ebx, 8007007Ah
0x140001c1e  jmp     short loc_140001C06
0x140001c20  mov     [rsi+rdi*2], bx
0x140001c24  mov     eax, ebx
0x140001c26  mov     rdi, [rsp+48h+var_18]
0x140001c2b  add     rsp, 38h
0x140001c2f  pop     rsi
0x140001c30  pop     rbx
0x140001c31  retn
0x140001c33  mov     eax, 80070057h
0x140001c38  jmp     loc_140008E16
0x140001c3d  mov     eax, 80070057h
0x140001c42  test    rdx, rdx
0x140001c45  jz      short loc_140001C0D
0x140001c47  jmp     loc_140008E16
0x140008e16  xor     ebx, ebx
0x140008e18  mov     [rcx], bx
0x140008e1b  jmp     loc_140001C0D
```
