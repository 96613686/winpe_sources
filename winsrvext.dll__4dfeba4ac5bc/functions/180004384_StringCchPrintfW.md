# StringCchPrintfW

- ea: `0x180004384`
- end: `0x18000440f`
- name: `StringCchPrintfW`
- size: `139`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003650`
- `0x18000a914`
- `0x18000c050`

## callees

- `0x180004384`

## import_xrefs

- `ntdll!_vsnwprintf` at `0x1800043c3`
- `ntdll!_vsnwprintf` at `0x1800043c3`

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
0x180004384  mov     [rsp+arg_10], r8
0x180004389  mov     qword ptr [rsp+Args], r9
0x18000438e  push    rbx
0x18000438f  push    rdi
0x180004390  sub     rsp, 38h
0x180004394  mov     rax, rdx
0x180004397  mov     rdi, rcx
0x18000439a  test    rdx, rdx
0x18000439d  jz      short loc_1800043F6
0x18000439f  cmp     rax, 7FFFFFFFh
0x1800043a5  jbe     short loc_1800043AE
0x1800043a7  mov     edx, 80070057h
0x1800043ac  jmp     short loc_180004400
0x1800043ae  lea     rbx, [rdx-1]
0x1800043b2  mov     [rsp+48h+var_28], 0
0x1800043bb  mov     rdx, rbx; BufferCount
0x1800043be  lea     r9, [rsp+48h+Args]; Args
0x1800043c3  call    cs:__imp__vsnwprintf
0x1800043ca  nop     dword ptr [rax+rax+00h]
0x1800043cf  test    eax, eax
0x1800043d1  js      short loc_1800043E9
0x1800043d3  cdqe
0x1800043d5  cmp     rax, rbx
0x1800043d8  ja      short loc_1800043E9
0x1800043da  xor     edx, edx
0x1800043dc  cmp     rax, rbx
0x1800043df  jnz     short loc_180004405
0x1800043e1  xor     eax, eax
0x1800043e3  mov     [rdi+rbx*2], ax
0x1800043e7  jmp     short loc_180004405
0x1800043e9  xor     eax, eax
0x1800043eb  mov     edx, 8007007Ah
0x1800043f0  mov     [rdi+rbx*2], ax
0x1800043f4  jmp     short loc_180004405
0x1800043f6  mov     edx, 80070057h
0x1800043fb  test    rax, rax
0x1800043fe  jz      short loc_180004405
0x180004400  xor     ecx, ecx
0x180004402  mov     [rdi], cx
0x180004405  mov     eax, edx
0x180004407  add     rsp, 38h
0x18000440b  pop     rdi
0x18000440c  pop     rbx
0x18000440d  retn
```
