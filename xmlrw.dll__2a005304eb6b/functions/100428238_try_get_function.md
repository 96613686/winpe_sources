# try_get_function

- ea: `0x100428238`
- end: `0x100428386`
- name: `try_get_function`
- size: `334`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10042838c`
- `0x1004283d8`
- `0x100428424`
- `0x100428470`
- `0x1004284c8`

## callees

- `0x100428238`
- `0x10042d920`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1004282cb`
- `KERNEL32!GetLastError` at `0x1004282cb`
- `KERNEL32!FreeLibrary` at `0x10042833b`
- `KERNEL32!FreeLibrary` at `0x10042833b`
- `KERNEL32!GetProcAddress` at `0x100428347`
- `KERNEL32!GetProcAddress` at `0x100428347`
- `KERNEL32!LoadLibraryExW` at `0x1004282bd`
- `KERNEL32!LoadLibraryExW` at `0x1004282f5`
- `KERNEL32!LoadLibraryExW` at `0x1004282bd`
- `KERNEL32!LoadLibraryExW` at `0x1004282f5`

## pseudocode

```c
FARPROC __fastcall try_get_function(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // rdi
  unsigned int *v6; // rbp
  FARPROC result; // rax
  bool i; // zf
  __int64 v10; // rsi
  HMODULE Library; // rbx
  const WCHAR *v12; // r15

  v4 = a1;
  v6 = a3;
  result = (FARPROC)qword_100451378[a1];
  if ( result != (FARPROC)-1LL )
  {
    if ( result )
      return result;
    for ( i = a3 == a4; !i; i = v6 == a4 )
    {
      v10 = *v6;
      Library = (HMODULE)qword_100451360[v10];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_16;
      }
      else
      {
        v12 = off_10043DB28[v10];
        Library = LoadLibraryExW(v12, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v12, L"api-ms-", 7u) && (Library = LoadLibraryExW(v12, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_100451360[v10], (__int64)Library) )
            FreeLibrary(Library);
LABEL_16:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_100451378[v4], (__int64)result);
            return result;
          }
          break;
        }
        _InterlockedExchange64(&qword_100451360[v10], -1);
      }
      ++v6;
    }
    _InterlockedExchange64(&qword_100451378[v4], -1);
  }
  return 0;
}

```

## disassembly

```asm
0x100428238  mov     [rsp+arg_0], rbx
0x10042823d  mov     [rsp+arg_8], rbp
0x100428242  mov     [rsp+arg_10], rsi
0x100428247  push    rdi
0x100428248  push    r12
0x10042824a  push    r13
0x10042824c  push    r14
0x10042824e  push    r15
0x100428250  sub     rsp, 20h
0x100428254  mov     edi, ecx
0x100428256  lea     r15, __ImageBase
0x10042825d  or      r14, 0FFFFFFFFFFFFFFFFh
0x100428261  mov     r12, r9
0x100428264  mov     rbp, r8
0x100428267  mov     r13, rdx
0x10042826a  mov     rax, rva qword_100451378[r15+rdi*8]
0x100428272  nop
0x100428273  cmp     rax, r14
0x100428276  jz      loc_100428367
0x10042827c  test    rax, rax
0x10042827f  jnz     loc_100428369
0x100428285  cmp     r8, r9
0x100428288  jz      loc_10042835F
0x10042828e  mov     esi, [rbp+0]
0x100428291  mov     rbx, rva qword_100451360[r15+rsi*8]
0x100428299  nop
0x10042829a  test    rbx, rbx
0x10042829d  jz      short loc_1004282AA
0x10042829f  cmp     rbx, r14
0x1004282a2  jnz     loc_100428341
0x1004282a8  jmp     short loc_100428315
0x1004282aa  mov     r15, ds:rva off_10043DB28[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x1004282b2  xor     edx, edx; hFile
0x1004282b4  mov     rcx, r15; lpLibFileName
0x1004282b7  mov     r8d, 800h; dwFlags
0x1004282bd  call    cs:__imp_LoadLibraryExW
0x1004282c3  mov     rbx, rax
0x1004282c6  test    rax, rax
0x1004282c9  jnz     short loc_100428321
0x1004282cb  call    cs:__imp_GetLastError
0x1004282d1  cmp     eax, 57h ; 'W'
0x1004282d4  jnz     short loc_100428303
0x1004282d6  lea     r8d, [rbx+7]; MaxCount
0x1004282da  mov     rcx, r15; String1
0x1004282dd  lea     rdx, aApiMs; "api-ms-"
0x1004282e4  call    wcsncmp
0x1004282e9  test    eax, eax
0x1004282eb  jz      short loc_100428303
0x1004282ed  xor     r8d, r8d; dwFlags
0x1004282f0  xor     edx, edx; hFile
0x1004282f2  mov     rcx, r15; lpLibFileName
0x1004282f5  call    cs:__imp_LoadLibraryExW
0x1004282fb  mov     rbx, rax
0x1004282fe  test    rax, rax
0x100428301  jnz     short loc_100428321
0x100428303  mov     rax, r14
0x100428306  lea     r15, __ImageBase
0x10042830d  xchg    rax, rva qword_100451360[r15+rsi*8]
0x100428315  add     rbp, 4
0x100428319  cmp     rbp, r12
0x10042831c  jmp     loc_100428288
0x100428321  mov     rax, rbx
0x100428324  lea     r15, __ImageBase
0x10042832b  xchg    rax, rva qword_100451360[r15+rsi*8]
0x100428333  test    rax, rax
0x100428336  jz      short loc_100428341
0x100428338  mov     rcx, rbx; hLibModule
0x10042833b  call    cs:__imp_FreeLibrary
0x100428341  mov     rdx, r13; lpProcName
0x100428344  mov     rcx, rbx; hModule
0x100428347  call    cs:__imp_GetProcAddress
0x10042834d  test    rax, rax
0x100428350  jz      short loc_10042835F
0x100428352  mov     rcx, rax
0x100428355  xchg    rcx, rva qword_100451378[r15+rdi*8]
0x10042835d  jmp     short loc_100428369
0x10042835f  xchg    r14, rva qword_100451378[r15+rdi*8]
0x100428367  xor     eax, eax
0x100428369  mov     rbx, [rsp+48h+arg_0]
0x10042836e  mov     rbp, [rsp+48h+arg_8]
0x100428373  mov     rsi, [rsp+48h+arg_10]
0x100428378  add     rsp, 20h
0x10042837c  pop     r15
0x10042837e  pop     r14
0x100428380  pop     r13
0x100428382  pop     r12
0x100428384  pop     rdi
0x100428385  retn
```
