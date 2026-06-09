# CabWriter::FciFileDelete(char *,int *,void *)

- ea: `0x180069690`
- end: `0x18006972d`
- name: `?FciFileDelete@CabWriter@@CAHPEADPEAHPEAX@Z`
- size: `157`
- prototype: `int __cdecl(LPSTR pszFile, int *err, void *pv)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800358c0`
- `0x180068d1c`
- `0x180069690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800696ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800696ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800696e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800696e5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800696f5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800696f5`

## pseudocode

```c
__int64 __fastcall CabWriter::FciFileDelete(const char *pszFile, DWORD *err, unsigned int *pv, unsigned __int64 a4)
{
  unsigned int v5; // edi
  WCHAR String1[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( AnsiToUnicode(*pv, pszFile, String1, a4) < 0 )
    return (unsigned int)-1;
  v5 = 0;
  if ( CompareStringOrdinal(String1, -1, "?", -1, 1) != 2 && !DeleteFileW(String1) )
  {
    *err = GetLastError();
    return (unsigned int)-1;
  }
  return v5;
}

```

## disassembly

```asm
0x180069690  mov     [rsp+arg_18], rsi
0x180069695  push    rdi
0x180069696  sub     rsp, 250h
0x18006969d  mov     rax, cs:__security_cookie
0x1800696a4  xor     rax, rsp
0x1800696a7  mov     [rsp+258h+var_18], rax
0x1800696af  mov     rax, r8
0x1800696b2  mov     rsi, rdx
0x1800696b5  mov     rdx, rcx; char *
0x1800696b8  lea     r8, [rsp+258h+String1]; unsigned __int16 *
0x1800696bd  mov     ecx, [rax]; unsigned int
0x1800696bf  call    ?AnsiToUnicode@@YAJIPEBDPEAG_K@Z; AnsiToUnicode(uint,char const *,ushort *,unsigned __int64)
0x1800696c4  test    eax, eax
0x1800696c6  js      short loc_180069707
0x1800696c8  or      r9d, 0FFFFFFFFh; cchCount2
0x1800696cc  mov     [rsp+258h+bIgnoreCase], 1; bIgnoreCase
0x1800696d4  or      edx, r9d; cchCount1
0x1800696d7  lea     r8, asc_18007B88C; "?"
0x1800696de  lea     rcx, [rsp+258h+String1]; lpString1
0x1800696e3  xor     edi, edi
0x1800696e5  call    cs:__imp_CompareStringOrdinal
0x1800696eb  cmp     eax, 2
0x1800696ee  jz      short loc_18006970A
0x1800696f0  lea     rcx, [rsp+258h+String1]; lpFileName
0x1800696f5  call    cs:__imp_DeleteFileW
0x1800696fb  test    eax, eax
0x1800696fd  jnz     short loc_18006970A
0x1800696ff  call    cs:__imp_GetLastError
0x180069705  mov     [rsi], eax
0x180069707  or      edi, 0FFFFFFFFh
0x18006970a  mov     eax, edi
0x18006970c  mov     rcx, [rsp+258h+var_18]
0x180069714  xor     rcx, rsp; StackCookie
0x180069717  call    __security_check_cookie
0x18006971c  mov     rsi, [rsp+258h+arg_18]
0x180069724  add     rsp, 250h
0x18006972b  pop     rdi
0x18006972c  retn
```
