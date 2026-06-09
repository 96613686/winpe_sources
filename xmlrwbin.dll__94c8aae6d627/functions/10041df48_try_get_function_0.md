# try_get_function_0

- ea: `0x10041df48`
- end: `0x10041e104`
- name: `try_get_function_0`
- size: `444`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10041e10c`
- `0x10041e16c`
- `0x10041e1f8`
- `0x10041e270`
- `0x10041e364`

## callees

- `0x10041b390`
- `0x10041df48`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10041dffa`
- `KERNEL32!GetLastError` at `0x10041dffa`
- `KERNEL32!FreeLibrary` at `0x10041e0c4`
- `KERNEL32!FreeLibrary` at `0x10041e0c4`
- `KERNEL32!GetProcAddress` at `0x10041e0d0`
- `KERNEL32!GetProcAddress` at `0x10041e0d0`
- `KERNEL32!LoadLibraryExW` at `0x10041dfe8`
- `KERNEL32!LoadLibraryExW` at `0x10041e03c`
- `KERNEL32!LoadLibraryExW` at `0x10041dfe8`
- `KERNEL32!LoadLibraryExW` at `0x10041e03c`

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
  v9 = __ROR8__(_security_cookie ^ qword_1004358F0[a1], _security_cookie & 0x3F);
  if ( v9 == -1 )
    return 0;
  if ( v9 )
    return (FARPROC)v9;
  if ( a3 == a4 )
  {
LABEL_16:
    _InterlockedExchange64(&qword_1004358F0[v4], v8 ^ __ROR8__(-1, 64 - ((unsigned __int8)v8 & 0x3Fu)));
    return 0;
  }
  while ( 1 )
  {
    v11 = *v6;
    Library = (HMODULE)qword_100435840[v11];
    if ( Library )
    {
      if ( Library != (HMODULE)-1LL )
        goto LABEL_20;
      goto LABEL_14;
    }
    v13 = off_100427CA0[v11];
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
    _InterlockedExchange64(&qword_100435840[v11], -1);
LABEL_14:
    if ( ++v6 == a4 )
      goto LABEL_15;
  }
  if ( _InterlockedExchange64(&qword_100435840[v11], (__int64)Library) )
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
    &qword_1004358F0[v4],
    _security_cookie ^ __ROR8__(result, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)));
  return result;
}

```

## disassembly

```asm
0x10041df48  mov     [rsp+arg_0], rbx
0x10041df4d  mov     [rsp+arg_8], rbp
0x10041df52  mov     [rsp+arg_10], rsi
0x10041df57  push    rdi
0x10041df58  push    r12
0x10041df5a  push    r13
0x10041df5c  push    r14
0x10041df5e  push    r15
0x10041df60  sub     rsp, 20h
0x10041df64  mov     r15d, ecx
0x10041df67  lea     r14, __ImageBase
0x10041df6e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x10041df72  mov     r12, r9
0x10041df75  mov     rbp, r8
0x10041df78  mov     r13, rdx
0x10041df7b  mov     r10, rva qword_1004358F0[r14+r15*8]
0x10041df83  nop
0x10041df84  mov     r11, cs:__security_cookie
0x10041df8b  xor     r10, r11
0x10041df8e  mov     ecx, r11d
0x10041df91  and     ecx, 3Fh
0x10041df94  ror     r10, cl
0x10041df97  cmp     r10, rdi
0x10041df9a  jz      loc_10041E08B
0x10041dfa0  test    r10, r10
0x10041dfa3  jz      short loc_10041DFAD
0x10041dfa5  mov     rax, r10
0x10041dfa8  jmp     loc_10041E08D
0x10041dfad  cmp     r8, r12
0x10041dfb0  jz      loc_10041E070
0x10041dfb6  mov     esi, [rbp+0]
0x10041dfb9  mov     rbx, rva qword_100435840[r14+rsi*8]
0x10041dfc1  nop
0x10041dfc2  test    rbx, rbx
0x10041dfc5  jz      short loc_10041DFD5
0x10041dfc7  cmp     rbx, rdi
0x10041dfca  jnz     loc_10041E0CA
0x10041dfd0  jmp     loc_10041E05C
0x10041dfd5  mov     r14, ds:rva off_100427CA0[r14+rsi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x10041dfdd  xor     edx, edx; hFile
0x10041dfdf  mov     rcx, r14; lpLibFileName
0x10041dfe2  mov     r8d, 800h; dwFlags
0x10041dfe8  call    cs:__imp_LoadLibraryExW
0x10041dfee  mov     rbx, rax
0x10041dff1  test    rax, rax
0x10041dff4  jnz     loc_10041E0AA
0x10041dffa  call    cs:__imp_GetLastError
0x10041e000  cmp     eax, 57h ; 'W'
0x10041e003  jnz     short loc_10041E04A
0x10041e005  lea     ebx, [rax-50h]
0x10041e008  mov     rcx, r14; String1
0x10041e00b  mov     r8d, ebx; MaxCount
0x10041e00e  lea     rdx, aApiMs; "api-ms-"
0x10041e015  call    wcsncmp
0x10041e01a  test    eax, eax
0x10041e01c  jz      short loc_10041E04A
0x10041e01e  mov     r8d, ebx; MaxCount
0x10041e021  lea     rdx, aExtMs; "ext-ms-"
0x10041e028  mov     rcx, r14; String1
0x10041e02b  call    wcsncmp
0x10041e030  test    eax, eax
0x10041e032  jz      short loc_10041E04A
0x10041e034  xor     r8d, r8d; dwFlags
0x10041e037  xor     edx, edx; hFile
0x10041e039  mov     rcx, r14; lpLibFileName
0x10041e03c  call    cs:__imp_LoadLibraryExW
0x10041e042  mov     rbx, rax
0x10041e045  test    rax, rax
0x10041e048  jnz     short loc_10041E0AA
0x10041e04a  mov     rax, rdi
0x10041e04d  lea     r14, __ImageBase
0x10041e054  xchg    rax, rva qword_100435840[r14+rsi*8]
0x10041e05c  add     rbp, 4
0x10041e060  cmp     rbp, r12
0x10041e063  jnz     loc_10041DFB6
0x10041e069  mov     r11, cs:__security_cookie
0x10041e070  mov     eax, r11d
0x10041e073  mov     ecx, 40h ; '@'
0x10041e078  and     eax, 3Fh
0x10041e07b  sub     ecx, eax
0x10041e07d  ror     rdi, cl
0x10041e080  xor     rdi, r11
0x10041e083  xchg    rdi, rva qword_1004358F0[r14+r15*8]
0x10041e08b  xor     eax, eax
0x10041e08d  mov     rbx, [rsp+48h+arg_0]
0x10041e092  mov     rbp, [rsp+48h+arg_8]
0x10041e097  mov     rsi, [rsp+48h+arg_10]
0x10041e09c  add     rsp, 20h
0x10041e0a0  pop     r15
0x10041e0a2  pop     r14
0x10041e0a4  pop     r13
0x10041e0a6  pop     r12
0x10041e0a8  pop     rdi
0x10041e0a9  retn
0x10041e0aa  mov     rax, rbx
0x10041e0ad  lea     r14, __ImageBase
0x10041e0b4  xchg    rax, rva qword_100435840[r14+rsi*8]
0x10041e0bc  test    rax, rax
0x10041e0bf  jz      short loc_10041E0CA
0x10041e0c1  mov     rcx, rbx; hLibModule
0x10041e0c4  call    cs:__imp_FreeLibrary
0x10041e0ca  mov     rdx, r13; lpProcName
0x10041e0cd  mov     rcx, rbx; hModule
0x10041e0d0  call    cs:__imp_GetProcAddress
0x10041e0d6  test    rax, rax
0x10041e0d9  jz      short loc_10041E069
0x10041e0db  mov     r8, cs:__security_cookie
0x10041e0e2  mov     edx, 40h ; '@'
0x10041e0e7  mov     ecx, r8d
0x10041e0ea  and     ecx, 3Fh
0x10041e0ed  sub     edx, ecx
0x10041e0ef  mov     cl, dl
0x10041e0f1  mov     rdx, rax
0x10041e0f4  ror     rdx, cl
0x10041e0f7  xor     rdx, r8
0x10041e0fa  xchg    rdx, rva qword_1004358F0[r14+r15*8]
0x10041e102  jmp     short loc_10041E08D
```
