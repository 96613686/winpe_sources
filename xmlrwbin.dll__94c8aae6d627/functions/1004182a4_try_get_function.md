# try_get_function

- ea: `0x1004182a4`
- end: `0x1004183f2`
- name: `try_get_function`
- size: `334`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1004183f8`
- `0x100418444`
- `0x100418490`
- `0x1004184dc`
- `0x100418534`

## callees

- `0x1004182a4`
- `0x10041b390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100418337`
- `KERNEL32!GetLastError` at `0x100418337`
- `KERNEL32!FreeLibrary` at `0x1004183a7`
- `KERNEL32!FreeLibrary` at `0x1004183a7`
- `KERNEL32!GetProcAddress` at `0x1004183b3`
- `KERNEL32!GetProcAddress` at `0x1004183b3`
- `KERNEL32!LoadLibraryExW` at `0x100418329`
- `KERNEL32!LoadLibraryExW` at `0x100418361`
- `KERNEL32!LoadLibraryExW` at `0x100418329`
- `KERNEL32!LoadLibraryExW` at `0x100418361`

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
  result = (FARPROC)qword_100435408[a1];
  if ( result != (FARPROC)-1LL )
  {
    if ( result )
      return result;
    for ( i = a3 == a4; !i; i = v6 == a4 )
    {
      v10 = *v6;
      Library = (HMODULE)qword_1004353F0[v10];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_16;
      }
      else
      {
        v12 = off_100427698[v10];
        Library = LoadLibraryExW(v12, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v12, L"api-ms-", 7u) && (Library = LoadLibraryExW(v12, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_1004353F0[v10], (__int64)Library) )
            FreeLibrary(Library);
LABEL_16:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_100435408[v4], (__int64)result);
            return result;
          }
          break;
        }
        _InterlockedExchange64(&qword_1004353F0[v10], -1);
      }
      ++v6;
    }
    _InterlockedExchange64(&qword_100435408[v4], -1);
  }
  return 0;
}

```

## disassembly

```asm
0x1004182a4  mov     [rsp+arg_0], rbx
0x1004182a9  mov     [rsp+arg_8], rbp
0x1004182ae  mov     [rsp+arg_10], rsi
0x1004182b3  push    rdi
0x1004182b4  push    r12
0x1004182b6  push    r13
0x1004182b8  push    r14
0x1004182ba  push    r15
0x1004182bc  sub     rsp, 20h
0x1004182c0  mov     edi, ecx
0x1004182c2  lea     r15, __ImageBase
0x1004182c9  or      r14, 0FFFFFFFFFFFFFFFFh
0x1004182cd  mov     r12, r9
0x1004182d0  mov     rbp, r8
0x1004182d3  mov     r13, rdx
0x1004182d6  mov     rax, rva qword_100435408[r15+rdi*8]
0x1004182de  nop
0x1004182df  cmp     rax, r14
0x1004182e2  jz      loc_1004183D3
0x1004182e8  test    rax, rax
0x1004182eb  jnz     loc_1004183D5
0x1004182f1  cmp     r8, r9
0x1004182f4  jz      loc_1004183CB
0x1004182fa  mov     esi, [rbp+0]
0x1004182fd  mov     rbx, rva qword_1004353F0[r15+rsi*8]
0x100418305  nop
0x100418306  test    rbx, rbx
0x100418309  jz      short loc_100418316
0x10041830b  cmp     rbx, r14
0x10041830e  jnz     loc_1004183AD
0x100418314  jmp     short loc_100418381
0x100418316  mov     r15, ds:rva off_100427698[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x10041831e  xor     edx, edx; hFile
0x100418320  mov     rcx, r15; lpLibFileName
0x100418323  mov     r8d, 800h; dwFlags
0x100418329  call    cs:__imp_LoadLibraryExW
0x10041832f  mov     rbx, rax
0x100418332  test    rax, rax
0x100418335  jnz     short loc_10041838D
0x100418337  call    cs:__imp_GetLastError
0x10041833d  cmp     eax, 57h ; 'W'
0x100418340  jnz     short loc_10041836F
0x100418342  lea     r8d, [rbx+7]; MaxCount
0x100418346  mov     rcx, r15; String1
0x100418349  lea     rdx, aApiMs; "api-ms-"
0x100418350  call    wcsncmp
0x100418355  test    eax, eax
0x100418357  jz      short loc_10041836F
0x100418359  xor     r8d, r8d; dwFlags
0x10041835c  xor     edx, edx; hFile
0x10041835e  mov     rcx, r15; lpLibFileName
0x100418361  call    cs:__imp_LoadLibraryExW
0x100418367  mov     rbx, rax
0x10041836a  test    rax, rax
0x10041836d  jnz     short loc_10041838D
0x10041836f  mov     rax, r14
0x100418372  lea     r15, __ImageBase
0x100418379  xchg    rax, rva qword_1004353F0[r15+rsi*8]
0x100418381  add     rbp, 4
0x100418385  cmp     rbp, r12
0x100418388  jmp     loc_1004182F4
0x10041838d  mov     rax, rbx
0x100418390  lea     r15, __ImageBase
0x100418397  xchg    rax, rva qword_1004353F0[r15+rsi*8]
0x10041839f  test    rax, rax
0x1004183a2  jz      short loc_1004183AD
0x1004183a4  mov     rcx, rbx; hLibModule
0x1004183a7  call    cs:__imp_FreeLibrary
0x1004183ad  mov     rdx, r13; lpProcName
0x1004183b0  mov     rcx, rbx; hModule
0x1004183b3  call    cs:__imp_GetProcAddress
0x1004183b9  test    rax, rax
0x1004183bc  jz      short loc_1004183CB
0x1004183be  mov     rcx, rax
0x1004183c1  xchg    rcx, rva qword_100435408[r15+rdi*8]
0x1004183c9  jmp     short loc_1004183D5
0x1004183cb  xchg    r14, rva qword_100435408[r15+rdi*8]
0x1004183d3  xor     eax, eax
0x1004183d5  mov     rbx, [rsp+48h+arg_0]
0x1004183da  mov     rbp, [rsp+48h+arg_8]
0x1004183df  mov     rsi, [rsp+48h+arg_10]
0x1004183e4  add     rsp, 20h
0x1004183e8  pop     r15
0x1004183ea  pop     r14
0x1004183ec  pop     r13
0x1004183ee  pop     r12
0x1004183f0  pop     rdi
0x1004183f1  retn
```
