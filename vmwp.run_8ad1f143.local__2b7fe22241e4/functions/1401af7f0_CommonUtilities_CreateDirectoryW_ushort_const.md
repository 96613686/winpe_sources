# CommonUtilities::CreateDirectoryW(ushort const *)

- ea: `0x1401af7f0`
- end: `0x1401af960`
- name: `?CreateDirectoryW@CommonUtilities@@YAKPEBG@Z`
- size: `368`
- prototype: `unsigned int __fastcall(CommonUtilities *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1400820bc`

## callees

- `0x1400d69f8`
- `0x140132960`
- `0x1401af7f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401af846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401af8ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401af846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401af8ed`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1401af832`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1401af8dd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1401af832`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1401af8dd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1401af905`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1401af905`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1401af817`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1401af817`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1401af89a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1401af89a`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1401af881`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1401af881`

## pseudocode

```c
DWORD __fastcall CommonUtilities::CreateDirectoryW(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD result; // eax
  unsigned int v4; // r11d
  LPWSTR v5; // rbx
  WCHAR v6; // ax
  DWORD FileAttributesW; // eax
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( !PathIsRelativeW(this) )
  {
    if ( CreateDirectoryW(this, 0) )
      return 0;
    result = GetLastError();
    if ( result != 3 )
      return result;
    if ( StringCchCopyW(pszPath, 0x104u, this) < 0 || PathCchAddBackslash(pszPath, v4) < 0 )
      return 206;
    v5 = PathSkipRootW(pszPath);
    if ( v5 )
    {
      while ( 1 )
      {
        v6 = *v5;
        if ( !*v5 )
          break;
        do
        {
          if ( v6 == 92 )
            break;
          v6 = *++v5;
        }
        while ( *v5 );
        if ( *v5 )
        {
          *v5 = 0;
          if ( !CreateDirectoryW(pszPath, 0) )
          {
            result = GetLastError();
            if ( result != 183 )
              return result;
            FileAttributesW = GetFileAttributesW(pszPath);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
              return 183;
          }
        }
        *v5++ = 92;
      }
      return 0;
    }
  }
  return 161;
}

```

## disassembly

```asm
0x1401af7f0  mov     [rsp+arg_8], rbx
0x1401af7f5  mov     [rsp+arg_10], rbp
0x1401af7fa  push    rdi
0x1401af7fb  sub     rsp, 240h
0x1401af802  mov     rax, cs:__security_cookie
0x1401af809  xor     rax, rsp
0x1401af80c  mov     [rsp+248h+var_18], rax
0x1401af814  mov     rbx, rcx
0x1401af817  call    cs:__imp_PathIsRelativeW
0x1401af81e  nop     dword ptr [rax+rax+00h]
0x1401af823  xor     edi, edi
0x1401af825  test    eax, eax
0x1401af827  jnz     loc_1401AF935
0x1401af82d  xor     edx, edx; lpSecurityAttributes
0x1401af82f  mov     rcx, rbx; lpPathName
0x1401af832  call    cs:__imp_CreateDirectoryW
0x1401af839  nop     dword ptr [rax+rax+00h]
0x1401af83e  test    eax, eax
0x1401af840  jnz     loc_1401AF931
0x1401af846  call    cs:__imp_GetLastError
0x1401af84d  nop     dword ptr [rax+rax+00h]
0x1401af852  cmp     eax, 3
0x1401af855  jnz     loc_1401AF93A
0x1401af85b  mov     r11d, 104h
0x1401af861  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x1401af866  mov     edx, r11d; unsigned __int64
0x1401af869  mov     r8, rbx; unsigned __int16 *
0x1401af86c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1401af871  test    eax, eax
0x1401af873  js      loc_1401AF92A
0x1401af879  mov     edx, r11d; cchPath
0x1401af87c  lea     rcx, [rsp+248h+pszPath]; pszPath
0x1401af881  call    cs:__imp_PathCchAddBackslash
0x1401af888  nop     dword ptr [rax+rax+00h]
0x1401af88d  test    eax, eax
0x1401af88f  js      loc_1401AF92A
0x1401af895  lea     rcx, [rsp+248h+pszPath]; pszPath
0x1401af89a  call    cs:__imp_PathSkipRootW
0x1401af8a1  nop     dword ptr [rax+rax+00h]
0x1401af8a6  mov     rbx, rax
0x1401af8a9  test    rax, rax
0x1401af8ac  jz      loc_1401AF935
0x1401af8b2  lea     ebp, [rdi+5Ch]
0x1401af8b5  movzx   eax, word ptr [rbx]
0x1401af8b8  test    ax, ax
0x1401af8bb  jz      short loc_1401AF931
0x1401af8bd  cmp     ax, bp
0x1401af8c0  jz      short loc_1401AF8CE
0x1401af8c2  add     rbx, 2
0x1401af8c6  movzx   eax, word ptr [rbx]
0x1401af8c9  test    ax, ax
0x1401af8cc  jnz     short loc_1401AF8BD
0x1401af8ce  cmp     [rbx], di
0x1401af8d1  jz      short loc_1401AF91A
0x1401af8d3  xor     edx, edx; lpSecurityAttributes
0x1401af8d5  mov     [rbx], di
0x1401af8d8  lea     rcx, [rsp+248h+pszPath]; lpPathName
0x1401af8dd  call    cs:__imp_CreateDirectoryW
0x1401af8e4  nop     dword ptr [rax+rax+00h]
0x1401af8e9  test    eax, eax
0x1401af8eb  jnz     short loc_1401AF91A
0x1401af8ed  call    cs:__imp_GetLastError
0x1401af8f4  nop     dword ptr [rax+rax+00h]
0x1401af8f9  cmp     eax, 0B7h
0x1401af8fe  jnz     short loc_1401AF93A
0x1401af900  lea     rcx, [rsp+248h+pszPath]; lpFileName
0x1401af905  call    cs:__imp_GetFileAttributesW
0x1401af90c  nop     dword ptr [rax+rax+00h]
0x1401af911  cmp     eax, 0FFFFFFFFh
0x1401af914  jz      short loc_1401AF923
0x1401af916  test    al, 10h
0x1401af918  jz      short loc_1401AF923
0x1401af91a  mov     [rbx], bp
0x1401af91d  add     rbx, 2
0x1401af921  jmp     short loc_1401AF8B5
0x1401af923  mov     eax, 0B7h
0x1401af928  jmp     short loc_1401AF93A
0x1401af92a  mov     eax, 0CEh
0x1401af92f  jmp     short loc_1401AF93A
0x1401af931  xor     eax, eax
0x1401af933  jmp     short loc_1401AF93A
0x1401af935  mov     eax, 0A1h
0x1401af93a  mov     rcx, [rsp+248h+var_18]
0x1401af942  xor     rcx, rsp; StackCookie
0x1401af945  call    __security_check_cookie
0x1401af94a  lea     r11, [rsp+248h+var_8]
0x1401af952  mov     rbx, [r11+18h]
0x1401af956  mov     rbp, [r11+20h]
0x1401af95a  mov     rsp, r11
0x1401af95d  pop     rdi
0x1401af95e  retn
```
