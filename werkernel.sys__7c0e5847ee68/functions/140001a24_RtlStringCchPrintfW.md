# RtlStringCchPrintfW

- ea: `0x140001a24`
- end: `0x140001aaf`
- name: `RtlStringCchPrintfW`
- size: `139`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dc94`
- `0x14000f6d8`

## callees

- `0x140001a24`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x140001a63`
- `ntoskrnl!_vsnwprintf` at `0x140001a63`

## pseudocode

```c
NTSTATUS RtlStringCchPrintfW(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  NTSTATUS v4; // edx
  size_t v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cchDest )
    return -1073741811;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = cchDest - 1;
    v6 = _vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
    if ( v6 < 0 || v6 > v5 )
    {
      v4 = -2147483643;
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
    v4 = -1073741811;
    *pszDest = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x140001a24  mov     [rsp+arg_10], r8
0x140001a29  mov     qword ptr [rsp+Args], r9
0x140001a2e  push    rbx
0x140001a2f  push    rdi
0x140001a30  sub     rsp, 38h
0x140001a34  mov     rax, rdx
0x140001a37  mov     rdi, rcx
0x140001a3a  test    rdx, rdx
0x140001a3d  jz      short loc_140001A96
0x140001a3f  cmp     rax, 7FFFFFFFh
0x140001a45  jbe     short loc_140001A4E
0x140001a47  mov     edx, 0C000000Dh
0x140001a4c  jmp     short loc_140001AA0
0x140001a4e  lea     rbx, [rdx-1]
0x140001a52  mov     [rsp+48h+var_28], 0
0x140001a5b  mov     rdx, rbx; Count
0x140001a5e  lea     r9, [rsp+48h+Args]; Args
0x140001a63  call    cs:__imp__vsnwprintf
0x140001a6a  nop     dword ptr [rax+rax+00h]
0x140001a6f  test    eax, eax
0x140001a71  js      short loc_140001A89
0x140001a73  cdqe
0x140001a75  cmp     rax, rbx
0x140001a78  ja      short loc_140001A89
0x140001a7a  xor     edx, edx
0x140001a7c  cmp     rax, rbx
0x140001a7f  jnz     short loc_140001AA5
0x140001a81  xor     eax, eax
0x140001a83  mov     [rdi+rbx*2], ax
0x140001a87  jmp     short loc_140001AA5
0x140001a89  xor     eax, eax
0x140001a8b  mov     edx, 80000005h
0x140001a90  mov     [rdi+rbx*2], ax
0x140001a94  jmp     short loc_140001AA5
0x140001a96  mov     edx, 0C000000Dh
0x140001a9b  test    rax, rax
0x140001a9e  jz      short loc_140001AA5
0x140001aa0  xor     ecx, ecx
0x140001aa2  mov     [rdi], cx
0x140001aa5  mov     eax, edx
0x140001aa7  add     rsp, 38h
0x140001aab  pop     rdi
0x140001aac  pop     rbx
0x140001aad  retn
```
