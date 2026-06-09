# StringCchPrintfW

- ea: `0x180009e58`
- end: `0x180009edc`
- name: `StringCchPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a20`

## callees

- `0x180009e58`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180009e97`
- `msvcrt!_vsnwprintf` at `0x180009e97`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  HRESULT v4; // edx
  size_t v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = cchDest - 1;
    v6 = _vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
    if ( v6 < 0 || v6 > v5 )
    {
      v4 = -2147024774;
      pszDest[v5] = 0;
    }
    else
    {
      v4 = 0;
      if ( v6 == v5 )
        pszDest[v5] = 0;
    }
  }
  else
  {
    v4 = -2147024809;
    *pszDest = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180009e58  mov     [rsp+arg_10], r8
0x180009e5d  mov     qword ptr [rsp+Args], r9
0x180009e62  push    rbx
0x180009e63  push    rdi
0x180009e64  sub     rsp, 38h
0x180009e68  mov     rax, rdx
0x180009e6b  mov     rdi, rcx
0x180009e6e  test    rdx, rdx
0x180009e71  jz      short loc_180009EC4
0x180009e73  cmp     rax, 7FFFFFFFh
0x180009e79  jbe     short loc_180009E82
0x180009e7b  mov     edx, 80070057h
0x180009e80  jmp     short loc_180009ECE
0x180009e82  lea     rbx, [rdx-1]
0x180009e86  mov     [rsp+48h+var_28], 0
0x180009e8f  mov     rdx, rbx; BufferCount
0x180009e92  lea     r9, [rsp+48h+Args]; Args
0x180009e97  call    cs:__imp__vsnwprintf
0x180009e9d  test    eax, eax
0x180009e9f  js      short loc_180009EB7
0x180009ea1  cdqe
0x180009ea3  cmp     rax, rbx
0x180009ea6  ja      short loc_180009EB7
0x180009ea8  xor     edx, edx
0x180009eaa  cmp     rax, rbx
0x180009ead  jnz     short loc_180009ED3
0x180009eaf  xor     eax, eax
0x180009eb1  mov     [rdi+rbx*2], ax
0x180009eb5  jmp     short loc_180009ED3
0x180009eb7  xor     eax, eax
0x180009eb9  mov     edx, 8007007Ah
0x180009ebe  mov     [rdi+rbx*2], ax
0x180009ec2  jmp     short loc_180009ED3
0x180009ec4  mov     edx, 80070057h
0x180009ec9  test    rax, rax
0x180009ecc  jz      short loc_180009ED3
0x180009ece  xor     ecx, ecx
0x180009ed0  mov     [rdi], cx
0x180009ed3  mov     eax, edx
0x180009ed5  add     rsp, 38h
0x180009ed9  pop     rdi
0x180009eda  pop     rbx
0x180009edb  retn
```
