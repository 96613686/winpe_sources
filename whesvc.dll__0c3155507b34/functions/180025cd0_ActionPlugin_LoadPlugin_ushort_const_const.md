# ActionPlugin::LoadPlugin(ushort const * const)

- ea: `0x180025cd0`
- end: `0x180025dc4`
- name: `?LoadPlugin@ActionPlugin@@QEAAJQEBG@Z`
- size: `244`
- prototype: `int __fastcall(HMODULE *this, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180018c10`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x180025cd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025d60`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025d7b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025d60`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025d7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025d90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025d90`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180025d17`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180025d17`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180025d3a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180025d3a`

## pseudocode

```c
int __fastcall ActionPlugin::LoadPlugin(HMODULE *this, const WCHAR *a2)
{
  int result; // eax
  HMODULE LibraryW; // rsi
  HMODULE v6; // rbp
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  char v9; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-238h] BYREF

  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(a2, Dst, 0x104u) )
  {
    LibraryW = LoadLibraryW(Dst);
    if ( this == (HMODULE *)&v9 )
    {
      if ( LibraryW )
        FreeLibrary(LibraryW);
    }
    else
    {
      v6 = *this;
      if ( *this )
      {
        LastError = GetLastError();
        FreeLibrary(v6);
        SetLastError(LastError);
      }
      *this = LibraryW;
    }
    if ( *this )
    {
      ProcAddress = GetProcAddress(*this, "InvokeWhesvcAction");
      this[1] = (HMODULE)ProcAddress;
      if ( ProcAddress )
        return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025cd0  mov     [rsp+arg_10], rbx
0x180025cd5  push    rbp
0x180025cd6  push    rsi
0x180025cd7  push    rdi
0x180025cd8  sub     rsp, 250h
0x180025cdf  mov     rax, cs:__security_cookie
0x180025ce6  xor     rax, rsp
0x180025ce9  mov     [rsp+268h+var_28], rax
0x180025cf1  mov     rbx, rdx
0x180025cf4  mov     rdi, rcx
0x180025cf7  xor     edx, edx; Val
0x180025cf9  lea     rcx, [rsp+268h+Dst]; void *
0x180025cfe  mov     r8d, 208h; Size
0x180025d04  call    memset_0
0x180025d09  mov     r8d, 104h; nSize
0x180025d0f  lea     rdx, [rsp+268h+Dst]; lpDst
0x180025d14  mov     rcx, rbx; lpSrc
0x180025d17  call    cs:__imp_ExpandEnvironmentStringsW
0x180025d1d  test    eax, eax
0x180025d1f  jnz     short loc_180025D35
0x180025d21  call    cs:__imp_GetLastError
0x180025d27  test    eax, eax
0x180025d29  jle     short loc_180025DA1
0x180025d2b  movzx   eax, ax
0x180025d2e  or      eax, 80070000h
0x180025d33  jmp     short loc_180025DA1
0x180025d35  lea     rcx, [rsp+268h+Dst]; lpLibFileName
0x180025d3a  call    cs:__imp_LoadLibraryW
0x180025d40  mov     rsi, rax
0x180025d43  lea     rax, [rsp+268h+var_248]
0x180025d48  cmp     rdi, rax
0x180025d4b  jz      short loc_180025D73
0x180025d4d  mov     rbp, [rdi]
0x180025d50  test    rbp, rbp
0x180025d53  jz      short loc_180025D6E
0x180025d55  call    cs:__imp_GetLastError
0x180025d5b  mov     rcx, rbp; hLibModule
0x180025d5e  mov     ebx, eax
0x180025d60  call    cs:__imp_FreeLibrary
0x180025d66  mov     ecx, ebx; dwErrCode
0x180025d68  call    cs:__imp_SetLastError
0x180025d6e  mov     [rdi], rsi
0x180025d71  jmp     short loc_180025D81
0x180025d73  test    rsi, rsi
0x180025d76  jz      short loc_180025D81
0x180025d78  mov     rcx, rsi; hLibModule
0x180025d7b  call    cs:__imp_FreeLibrary
0x180025d81  mov     rcx, [rdi]; hModule
0x180025d84  test    rcx, rcx
0x180025d87  jz      short loc_180025D21
0x180025d89  lea     rdx, aInvokewhesvcac; "InvokeWhesvcAction"
0x180025d90  call    cs:__imp_GetProcAddress
0x180025d96  mov     [rdi+8], rax
0x180025d9a  test    rax, rax
0x180025d9d  jz      short loc_180025D21
0x180025d9f  xor     eax, eax
0x180025da1  mov     rcx, [rsp+268h+var_28]
0x180025da9  xor     rcx, rsp; StackCookie
0x180025dac  call    __security_check_cookie
0x180025db1  mov     rbx, [rsp+268h+arg_10]
0x180025db9  add     rsp, 250h
0x180025dc0  pop     rdi
0x180025dc1  pop     rsi
0x180025dc2  pop     rbp
0x180025dc3  retn
```
