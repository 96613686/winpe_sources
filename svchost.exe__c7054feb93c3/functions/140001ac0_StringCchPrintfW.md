# StringCchPrintfW

- ea: `0x140001ac0`
- end: `0x140001b4a`
- name: `StringCchPrintfW`
- size: `138`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400018d0`
- `0x140006080`

## callees

- `0x140001ac0`
- `0x1400055dc`

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
0x140001ac0  mov     [rsp+arg_10], r8
0x140001ac5  mov     qword ptr [rsp+Args], r9
0x140001aca  push    rbx
0x140001acb  push    rsi
0x140001acc  sub     rsp, 38h
0x140001ad0  mov     rsi, rcx
0x140001ad3  test    rdx, rdx
0x140001ad6  jz      short loc_140001B3B
0x140001ad8  cmp     rdx, 7FFFFFFFh
0x140001adf  ja      short loc_140001B31
0x140001ae1  mov     [rsp+48h+var_18], rdi
0x140001ae6  lea     r9, [rsp+48h+Args]; Args
0x140001aeb  lea     rdi, [rdx-1]
0x140001aef  xor     ebx, ebx
0x140001af1  mov     rdx, rdi; BufferCount
0x140001af4  call    _vsnwprintf
0x140001af9  test    eax, eax
0x140001afb  js      short loc_140001B14
0x140001afd  cdqe
0x140001aff  cmp     rax, rdi
0x140001b02  ja      short loc_140001B14
0x140001b04  jz      short loc_140001B1F
0x140001b06  mov     rdi, [rsp+48h+var_18]
0x140001b0b  mov     eax, ebx
0x140001b0d  add     rsp, 38h
0x140001b11  pop     rsi
0x140001b12  pop     rbx
0x140001b13  retn
0x140001b14  mov     [rsi+rdi*2], bx
0x140001b18  mov     ebx, 8007007Ah
0x140001b1d  jmp     short loc_140001B06
0x140001b1f  mov     [rsi+rdi*2], bx
0x140001b23  mov     eax, ebx
0x140001b25  mov     rdi, [rsp+48h+var_18]
0x140001b2a  add     rsp, 38h
0x140001b2e  pop     rsi
0x140001b2f  pop     rbx
0x140001b30  retn
0x140001b31  mov     eax, 80070057h
0x140001b36  jmp     loc_140008790
0x140001b3b  mov     eax, 80070057h
0x140001b40  test    rdx, rdx
0x140001b43  jz      short loc_140001B0D
0x140001b45  jmp     loc_140008790
0x140008790  xor     ebx, ebx
0x140008792  mov     [rcx], bx
0x140008795  jmp     loc_140001B0D
```
