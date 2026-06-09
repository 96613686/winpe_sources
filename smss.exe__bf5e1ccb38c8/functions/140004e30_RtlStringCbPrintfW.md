# RtlStringCbPrintfW

- ea: `0x140004e30`
- end: `0x140004eba`
- name: `RtlStringCbPrintfW`
- size: `138`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400036d0`
- `0x140004610`
- `0x140009100`
- `0x14000c638`
- `0x14000e2e8`
- `0x14000f3ec`
- `0x140010344`
- `0x140011ac4`
- `0x140011c50`
- `0x140013a40`
- `0x140014fc4`

## callees

- `0x140004e30`

## import_xrefs

- `ntdll!_vsnwprintf_s` at `0x140004e73`
- `ntdll!_vsnwprintf_s` at `0x140004e73`

## pseudocode

```c
NTSTATUS RtlStringCbPrintfW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  size_t v3; // rdx
  NTSTATUS result; // eax
  unsigned __int64 v6; // rsi
  NTSTATUS v7; // ebx
  int v8; // eax
  va_list va; // [rsp+78h] [rbp+20h] BYREF

  va_start(va, pszFormat);
  v3 = cbDest >> 1;
  if ( !v3 )
    return -1073741811;
  if ( v3 <= 0x7FFFFFFF )
  {
    v6 = v3 - 1;
    v7 = 0;
    v8 = _vsnwprintf_s(pszDest, v3, v3 - 1, pszFormat, va);
    if ( v8 < 0 || v8 > v6 )
    {
      pszDest[v6] = 0;
      return -2147483643;
    }
    else if ( v8 == v6 )
    {
      pszDest[v6] = 0;
    }
    return v7;
  }
  else
  {
    result = -1073741811;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004e30  mov     [rsp+arg_10], r8
0x140004e35  mov     qword ptr [rsp+arg_18], r9
0x140004e3a  push    rbx
0x140004e3b  push    rdi
0x140004e3c  sub     rsp, 48h
0x140004e40  shr     rdx, 1; SizeInWords
0x140004e43  mov     rdi, rcx
0x140004e46  jz      short loc_140004EA4
0x140004e48  cmp     rdx, 7FFFFFFFh
0x140004e4f  jbe     short loc_140004E58
0x140004e51  mov     eax, 0C000000Dh
0x140004e56  jmp     short loc_140004EAE
0x140004e58  lea     rax, [rsp+58h+arg_18]
0x140004e5d  mov     [rsp+58h+var_18], rsi
0x140004e62  lea     rsi, [rdx-1]
0x140004e66  mov     [rsp+58h+ArgList], rax; ArgList
0x140004e6b  mov     r9, r8; Format
0x140004e6e  xor     ebx, ebx
0x140004e70  mov     r8, rsi; MaxCount
0x140004e73  call    cs:__imp__vsnwprintf_s
0x140004e79  test    eax, eax
0x140004e7b  js      short loc_140004E8D
0x140004e7d  movsxd  rcx, eax
0x140004e80  cmp     rcx, rsi
0x140004e83  ja      short loc_140004E8D
0x140004e85  jnz     short loc_140004E96
0x140004e87  mov     [rdi+rsi*2], bx
0x140004e8b  jmp     short loc_140004E96
0x140004e8d  mov     [rdi+rsi*2], bx
0x140004e91  mov     ebx, 80000005h
0x140004e96  mov     rsi, [rsp+58h+var_18]
0x140004e9b  mov     eax, ebx
0x140004e9d  add     rsp, 48h
0x140004ea1  pop     rdi
0x140004ea2  pop     rbx
0x140004ea3  retn
0x140004ea4  mov     eax, 0C000000Dh
0x140004ea9  test    rdx, rdx
0x140004eac  jz      short loc_140004EB3
0x140004eae  xor     ebx, ebx
0x140004eb0  mov     [rcx], bx
0x140004eb3  add     rsp, 48h
0x140004eb7  pop     rdi
0x140004eb8  pop     rbx
0x140004eb9  retn
```
