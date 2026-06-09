# StringCbPrintfW

- ea: `0x180008834`
- end: `0x1800088b8`
- name: `StringCbPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180004b50`

## callees

- `0x180005fe4`
- `0x180008834`

## pseudocode

```c
HRESULT StringCbPrintfW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  size_t v4; // rax
  HRESULT v5; // edx
  unsigned __int64 v6; // rbx
  int v7; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  v4 = cbDest >> 1;
  if ( !(cbDest >> 1) )
    return -2147024809;
  if ( v4 <= 0x7FFFFFFF )
  {
    v6 = v4 - 1;
    v7 = vsnwprintf(pszDest, v4 - 1, pszFormat, Args);
    if ( v7 < 0 || v7 > v6 )
    {
      v5 = -2147024774;
      pszDest[v6] = 0;
    }
    else
    {
      v5 = 0;
      if ( v7 == v6 )
        pszDest[v6] = 0;
    }
  }
  else
  {
    v5 = -2147024809;
    *pszDest = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180008834  mov     [rsp+arg_10], r8
0x180008839  mov     qword ptr [rsp+Args], r9
0x18000883e  push    rbx
0x18000883f  push    rdi
0x180008840  sub     rsp, 38h
0x180008844  mov     rax, rdx
0x180008847  mov     rdi, rcx
0x18000884a  shr     rax, 1
0x18000884d  jz      short loc_18000889F
0x18000884f  cmp     rax, 7FFFFFFFh
0x180008855  jbe     short loc_18000885E
0x180008857  mov     edx, 80070057h
0x18000885c  jmp     short loc_1800088A9
0x18000885e  lea     rbx, [rax-1]
0x180008862  mov     [rsp+48h+var_28], 0
0x18000886b  mov     rdx, rbx; BufferCount
0x18000886e  lea     r9, [rsp+48h+Args]; Args
0x180008873  call    _vsnwprintf
0x180008878  test    eax, eax
0x18000887a  js      short loc_180008892
0x18000887c  cdqe
0x18000887e  cmp     rax, rbx
0x180008881  ja      short loc_180008892
0x180008883  xor     edx, edx
0x180008885  cmp     rax, rbx
0x180008888  jnz     short loc_1800088AE
0x18000888a  xor     eax, eax
0x18000888c  mov     [rdi+rbx*2], ax
0x180008890  jmp     short loc_1800088AE
0x180008892  xor     eax, eax
0x180008894  mov     edx, 8007007Ah
0x180008899  mov     [rdi+rbx*2], ax
0x18000889d  jmp     short loc_1800088AE
0x18000889f  mov     edx, 80070057h
0x1800088a4  test    rax, rax
0x1800088a7  jz      short loc_1800088AE
0x1800088a9  xor     ecx, ecx
0x1800088ab  mov     [rdi], cx
0x1800088ae  mov     eax, edx
0x1800088b0  add     rsp, 38h
0x1800088b4  pop     rdi
0x1800088b5  pop     rbx
0x1800088b6  retn
```
