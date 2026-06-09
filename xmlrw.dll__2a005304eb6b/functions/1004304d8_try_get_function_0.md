# try_get_function_0

- ea: `0x1004304d8`
- end: `0x100430694`
- name: `try_get_function_0`
- size: `444`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10043069c`
- `0x1004306fc`
- `0x100430788`
- `0x100430800`
- `0x1004308f4`

## callees

- `0x10042d920`
- `0x1004304d8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10043058a`
- `KERNEL32!GetLastError` at `0x10043058a`
- `KERNEL32!FreeLibrary` at `0x100430654`
- `KERNEL32!FreeLibrary` at `0x100430654`
- `KERNEL32!GetProcAddress` at `0x100430660`
- `KERNEL32!GetProcAddress` at `0x100430660`
- `KERNEL32!LoadLibraryExW` at `0x100430578`
- `KERNEL32!LoadLibraryExW` at `0x1004305cc`
- `KERNEL32!LoadLibraryExW` at `0x100430578`
- `KERNEL32!LoadLibraryExW` at `0x1004305cc`

## pseudocode

```c
FARPROC __fastcall try_get_function_0(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r15
  unsigned int *v6; // rbp
  uintptr_t v8; // r11
  __int64 v9; // r10
  FARPROC result; // rax
  __int64 v11; // rsi
  HMODULE Library; // rbx
  const WCHAR *v13; // r14

  v4 = a1;
  v6 = a3;
  v8 = _security_cookie;
  v9 = __ROR8__(_security_cookie ^ qword_100451860[a1], _security_cookie & 0x3F);
  if ( v9 == -1 )
    return 0;
  if ( v9 )
    return (FARPROC)v9;
  if ( a3 == a4 )
  {
LABEL_16:
    _InterlockedExchange64(&qword_100451860[v4], v8 ^ __ROR8__(-1, 64 - ((unsigned __int8)v8 & 0x3Fu)));
    return 0;
  }
  while ( 1 )
  {
    v11 = *v6;
    Library = (HMODULE)qword_1004517B0[v11];
    if ( Library )
    {
      if ( Library != (HMODULE)-1LL )
        goto LABEL_20;
      goto LABEL_14;
    }
    v13 = off_10043E250[v11];
    Library = LoadLibraryExW(v13, 0, 0x800u);
    if ( Library )
      break;
    if ( GetLastError() == 87 )
    {
      if ( wcsncmp(v13, L"api-ms-", 7u) )
      {
        if ( wcsncmp(v13, L"ext-ms-", 7u) )
        {
          Library = LoadLibraryExW(v13, 0, 0);
          if ( Library )
            break;
        }
      }
    }
    _InterlockedExchange64(&qword_1004517B0[v11], -1);
LABEL_14:
    if ( ++v6 == a4 )
      goto LABEL_15;
  }
  if ( _InterlockedExchange64(&qword_1004517B0[v11], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  result = GetProcAddress(Library, a2);
  if ( !result )
  {
LABEL_15:
    v8 = _security_cookie;
    goto LABEL_16;
  }
  _InterlockedExchange64(
    &qword_100451860[v4],
    _security_cookie ^ __ROR8__(result, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)));
  return result;
}

```

## disassembly

```asm
0x1004304d8  mov     [rsp+arg_0], rbx
0x1004304dd  mov     [rsp+arg_8], rbp
0x1004304e2  mov     [rsp+arg_10], rsi
0x1004304e7  push    rdi
0x1004304e8  push    r12
0x1004304ea  push    r13
0x1004304ec  push    r14
0x1004304ee  push    r15
0x1004304f0  sub     rsp, 20h
0x1004304f4  mov     r15d, ecx
0x1004304f7  lea     r14, __ImageBase
0x1004304fe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x100430502  mov     r12, r9
0x100430505  mov     rbp, r8
0x100430508  mov     r13, rdx
0x10043050b  mov     r10, rva qword_100451860[r14+r15*8]
0x100430513  nop
0x100430514  mov     r11, cs:__security_cookie
0x10043051b  xor     r10, r11
0x10043051e  mov     ecx, r11d
0x100430521  and     ecx, 3Fh
0x100430524  ror     r10, cl
0x100430527  cmp     r10, rdi
0x10043052a  jz      loc_10043061B
0x100430530  test    r10, r10
0x100430533  jz      short loc_10043053D
0x100430535  mov     rax, r10
0x100430538  jmp     loc_10043061D
0x10043053d  cmp     r8, r12
0x100430540  jz      loc_100430600
0x100430546  mov     esi, [rbp+0]
0x100430549  mov     rbx, rva qword_1004517B0[r14+rsi*8]
0x100430551  nop
0x100430552  test    rbx, rbx
0x100430555  jz      short loc_100430565
0x100430557  cmp     rbx, rdi
0x10043055a  jnz     loc_10043065A
0x100430560  jmp     loc_1004305EC
0x100430565  mov     r14, ds:rva off_10043E250[r14+rsi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x10043056d  xor     edx, edx; hFile
0x10043056f  mov     rcx, r14; lpLibFileName
0x100430572  mov     r8d, 800h; dwFlags
0x100430578  call    cs:__imp_LoadLibraryExW
0x10043057e  mov     rbx, rax
0x100430581  test    rax, rax
0x100430584  jnz     loc_10043063A
0x10043058a  call    cs:__imp_GetLastError
0x100430590  cmp     eax, 57h ; 'W'
0x100430593  jnz     short loc_1004305DA
0x100430595  lea     ebx, [rax-50h]
0x100430598  mov     rcx, r14; String1
0x10043059b  mov     r8d, ebx; MaxCount
0x10043059e  lea     rdx, aApiMs; "api-ms-"
0x1004305a5  call    wcsncmp
0x1004305aa  test    eax, eax
0x1004305ac  jz      short loc_1004305DA
0x1004305ae  mov     r8d, ebx; MaxCount
0x1004305b1  lea     rdx, aExtMs; "ext-ms-"
0x1004305b8  mov     rcx, r14; String1
0x1004305bb  call    wcsncmp
0x1004305c0  test    eax, eax
0x1004305c2  jz      short loc_1004305DA
0x1004305c4  xor     r8d, r8d; dwFlags
0x1004305c7  xor     edx, edx; hFile
0x1004305c9  mov     rcx, r14; lpLibFileName
0x1004305cc  call    cs:__imp_LoadLibraryExW
0x1004305d2  mov     rbx, rax
0x1004305d5  test    rax, rax
0x1004305d8  jnz     short loc_10043063A
0x1004305da  mov     rax, rdi
0x1004305dd  lea     r14, __ImageBase
0x1004305e4  xchg    rax, rva qword_1004517B0[r14+rsi*8]
0x1004305ec  add     rbp, 4
0x1004305f0  cmp     rbp, r12
0x1004305f3  jnz     loc_100430546
0x1004305f9  mov     r11, cs:__security_cookie
0x100430600  mov     eax, r11d
0x100430603  mov     ecx, 40h ; '@'
0x100430608  and     eax, 3Fh
0x10043060b  sub     ecx, eax
0x10043060d  ror     rdi, cl
0x100430610  xor     rdi, r11
0x100430613  xchg    rdi, rva qword_100451860[r14+r15*8]
0x10043061b  xor     eax, eax
0x10043061d  mov     rbx, [rsp+48h+arg_0]
0x100430622  mov     rbp, [rsp+48h+arg_8]
0x100430627  mov     rsi, [rsp+48h+arg_10]
0x10043062c  add     rsp, 20h
0x100430630  pop     r15
0x100430632  pop     r14
0x100430634  pop     r13
0x100430636  pop     r12
0x100430638  pop     rdi
0x100430639  retn
0x10043063a  mov     rax, rbx
0x10043063d  lea     r14, __ImageBase
0x100430644  xchg    rax, rva qword_1004517B0[r14+rsi*8]
0x10043064c  test    rax, rax
0x10043064f  jz      short loc_10043065A
0x100430651  mov     rcx, rbx; hLibModule
0x100430654  call    cs:__imp_FreeLibrary
0x10043065a  mov     rdx, r13; lpProcName
0x10043065d  mov     rcx, rbx; hModule
0x100430660  call    cs:__imp_GetProcAddress
0x100430666  test    rax, rax
0x100430669  jz      short loc_1004305F9
0x10043066b  mov     r8, cs:__security_cookie
0x100430672  mov     edx, 40h ; '@'
0x100430677  mov     ecx, r8d
0x10043067a  and     ecx, 3Fh
0x10043067d  sub     edx, ecx
0x10043067f  mov     cl, dl
0x100430681  mov     rdx, rax
0x100430684  ror     rdx, cl
0x100430687  xor     rdx, r8
0x10043068a  xchg    rdx, rva qword_100451860[r14+r15*8]
0x100430692  jmp     short loc_10043061D
```
