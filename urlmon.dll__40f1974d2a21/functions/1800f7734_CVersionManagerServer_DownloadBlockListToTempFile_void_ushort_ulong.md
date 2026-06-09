# CVersionManagerServer::_DownloadBlockListToTempFile(void *,ushort *,ulong)

- ea: `0x1800f7734`
- end: `0x1800f79a8`
- name: `?_DownloadBlockListToTempFile@CVersionManagerServer@@AEAAJPEAXPEAGK@Z`
- size: `628`
- prototype: `int(CVersionManagerServer *__hidden this, void *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x1800f79b0`

## callees

- `0x180057040`
- `0x1800f70dc`
- `0x1800f7734`
- `0x18011ba3e`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f77fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f77fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f7962`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f7962`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800f77de`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800f77de`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f791c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f791c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f77f3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f77f3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f796f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f796f`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800f7835`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800f7835`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f7862`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f7862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f78a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f78a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f7959`
- `WININET!InternetReadFile` at `0x1800f78ec`
- `WININET!InternetReadFile` at `0x1800f78ec`

## pseudocode

```c
__int64 __fastcall CVersionManagerServer::_DownloadBlockListToTempFile(
        CVersionManagerServer *this,
        void *a2,
        unsigned __int16 *a3)
{
  int LocalDirectory; // ebx
  DWORD FileAttributesW; // edi
  DWORD LastError; // eax
  CVersionManagerServer *v9; // rcx
  HANDLE FileW; // r15
  signed int v11; // eax
  void *v12; // r14
  signed int v13; // eax
  DWORD dwNumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( a2 && a3 )
  {
    *a3 = 0;
    memset_0(pszPath, 0, 0x208u);
    *(_QWORD *)NumberOfBytesWritten = 0;
    LocalDirectory = StringCchCopyExW(
                       pszPath,
                       0x104u,
                       (const unsigned __int16 *)this + 15,
                       (unsigned __int16 **)NumberOfBytesWritten,
                       0,
                       0);
    if ( LocalDirectory >= 0 )
    {
      LocalDirectory = PathCchRemoveFileSpec(pszPath, (__int64)(*(_QWORD *)NumberOfBytesWritten - (_QWORD)pszPath) >> 1);
      if ( LocalDirectory >= 0 )
      {
        FileAttributesW = GetFileAttributesW(pszPath);
        LastError = GetLastError();
        if ( FileAttributesW == -1 )
        {
          if ( LastError != 2
            || (LocalDirectory = CVersionManagerServer::_CreateLocalDirectory(v9, pszPath), LocalDirectory >= 0) )
          {
LABEL_8:
            if ( GetTempFileNameW(pszPath, L"ver", 0, a3)
              && (FileW = CreateFileW(a3, 0x40000000u, 0, 0, 2u, 0x80u, 0), FileW != (HANDLE)-1LL) )
            {
              v12 = CoTaskMemAlloc(0x1000u);
              if ( v12 )
              {
                while ( LocalDirectory >= 0 )
                {
                  if ( *((_BYTE *)this + 2000) )
                  {
                    LocalDirectory = -2147023901;
                    break;
                  }
                  dwNumberOfBytesRead = 0;
                  if ( !InternetReadFile(a2, v12, 0x1000u, &dwNumberOfBytesRead) )
                    goto LABEL_23;
                  if ( !dwNumberOfBytesRead )
                    break;
                  NumberOfBytesWritten[0] = 0;
                  if ( WriteFile(FileW, v12, dwNumberOfBytesRead, NumberOfBytesWritten, 0) )
                  {
                    if ( NumberOfBytesWritten[0] != dwNumberOfBytesRead )
                      LocalDirectory = -2147024867;
                  }
                  else
                  {
LABEL_23:
                    v13 = GetLastError();
                    LocalDirectory = v13;
                    if ( v13 > 0 )
                      LocalDirectory = (unsigned __int16)v13 | 0x80070000;
                  }
                }
                CoTaskMemFree(v12);
              }
              else
              {
                LocalDirectory = -2147024882;
              }
              CloseHandle(FileW);
              if ( LocalDirectory < 0 )
                DeleteFileW(a3);
            }
            else
            {
              v11 = GetLastError();
              LocalDirectory = v11;
              if ( v11 > 0 )
                return (unsigned __int16)v11 | 0x80070000;
            }
          }
        }
        else
        {
          if ( (FileAttributesW & 0x10) != 0 )
            goto LABEL_8;
          return (unsigned int)-2147024735;
        }
      }
    }
    return (unsigned int)LocalDirectory;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800f7734  mov     [rsp-8+arg_18], rbx
0x1800f7739  push    rbp
0x1800f773a  push    rsi
0x1800f773b  push    rdi
0x1800f773c  push    r12
0x1800f773e  push    r13
0x1800f7740  push    r14
0x1800f7742  push    r15
0x1800f7744  lea     rbp, [rsp-170h]
0x1800f774c  sub     rsp, 270h
0x1800f7753  mov     rax, cs:__security_cookie
0x1800f775a  xor     rax, rsp
0x1800f775d  mov     [rbp+1A0h+var_40], rax
0x1800f7764  xor     r14d, r14d
0x1800f7767  mov     rsi, r8
0x1800f776a  mov     r12, rdx
0x1800f776d  mov     r13, rcx
0x1800f7770  test    rdx, rdx
0x1800f7773  jz      loc_1800F7979
0x1800f7779  test    r8, r8
0x1800f777c  jz      loc_1800F7979
0x1800f7782  mov     [r8], r14w
0x1800f7786  lea     rcx, [rsp+2A0h+pszPath]; void *
0x1800f778b  mov     r8d, 208h; Size
0x1800f7791  xor     edx, edx; Val
0x1800f7793  call    memset_0
0x1800f7798  lea     r8, [r13+1Eh]; unsigned __int16 *
0x1800f779c  mov     [rsp+2A0h+dwFlagsAndAttributes], r14d; unsigned int
0x1800f77a1  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; unsigned __int16 **
0x1800f77a6  mov     qword ptr [rsp+2A0h+NumberOfBytesWritten], r14
0x1800f77ab  mov     edx, 104h; unsigned __int64
0x1800f77b0  mov     qword ptr [rsp+2A0h+dwCreationDisposition], r14; unsigned __int64 *
0x1800f77b5  lea     rcx, [rsp+2A0h+pszPath]; pszDest
0x1800f77ba  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800f77bf  mov     ebx, eax
0x1800f77c1  test    eax, eax
0x1800f77c3  js      loc_1800F7975
0x1800f77c9  mov     rdx, qword ptr [rsp+2A0h+NumberOfBytesWritten]
0x1800f77ce  lea     rax, [rsp+2A0h+pszPath]
0x1800f77d3  sub     rdx, rax
0x1800f77d6  lea     rcx, [rsp+2A0h+pszPath]; pszPath
0x1800f77db  sar     rdx, 1; cchPath
0x1800f77de  call    cs:__imp_PathCchRemoveFileSpec
0x1800f77e4  mov     ebx, eax
0x1800f77e6  test    eax, eax
0x1800f77e8  js      loc_1800F7975
0x1800f77ee  lea     rcx, [rsp+2A0h+pszPath]; lpFileName
0x1800f77f3  call    cs:__imp_GetFileAttributesW
0x1800f77f9  mov     edi, eax
0x1800f77fb  call    cs:__imp_GetLastError
0x1800f7801  cmp     edi, 0FFFFFFFFh
0x1800f7804  jnz     loc_1800F788F
0x1800f780a  cmp     eax, 2
0x1800f780d  jnz     short loc_1800F7823
0x1800f780f  lea     rdx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x1800f7814  call    ?_CreateLocalDirectory@CVersionManagerServer@@AEAAJPEBG@Z; CVersionManagerServer::_CreateLocalDirectory(ushort const *)
0x1800f7819  mov     ebx, eax
0x1800f781b  test    eax, eax
0x1800f781d  js      loc_1800F7975
0x1800f7823  mov     r9, rsi; lpTempFileName
0x1800f7826  lea     rdx, aVer; "ver"
0x1800f782d  xor     r8d, r8d; uUnique
0x1800f7830  lea     rcx, [rsp+2A0h+pszPath]; lpPathName
0x1800f7835  call    cs:__imp_GetTempFileNameW
0x1800f783b  test    eax, eax
0x1800f783d  jz      short loc_1800F7871
0x1800f783f  mov     [rsp+2A0h+hTemplateFile], r14; hTemplateFile
0x1800f7844  xor     r9d, r9d; lpSecurityAttributes
0x1800f7847  mov     [rsp+2A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800f784f  xor     r8d, r8d; dwShareMode
0x1800f7852  mov     edx, 40000000h; dwDesiredAccess
0x1800f7857  mov     [rsp+2A0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800f785f  mov     rcx, rsi; lpFileName
0x1800f7862  call    cs:__imp_CreateFileW
0x1800f7868  mov     r15, rax
0x1800f786b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f786f  jnz     short loc_1800F789F
0x1800f7871  call    cs:__imp_GetLastError
0x1800f7877  mov     ebx, eax
0x1800f7879  test    eax, eax
0x1800f787b  jle     loc_1800F7975
0x1800f7881  movzx   ebx, ax
0x1800f7884  or      ebx, 80070000h
0x1800f788a  jmp     loc_1800F7975
0x1800f788f  test    dil, 10h
0x1800f7893  jnz     short loc_1800F7823
0x1800f7895  mov     ebx, 800700A1h
0x1800f789a  jmp     loc_1800F7975
0x1800f789f  mov     ecx, 1000h; cb
0x1800f78a4  call    cs:__imp_CoTaskMemAlloc
0x1800f78aa  mov     r14, rax
0x1800f78ad  test    rax, rax
0x1800f78b0  jnz     short loc_1800F78BC
0x1800f78b2  mov     ebx, 8007000Eh
0x1800f78b7  jmp     loc_1800F795F
0x1800f78bc  mov     edi, 80070000h
0x1800f78c1  test    ebx, ebx
0x1800f78c3  js      loc_1800F7956
0x1800f78c9  cmp     byte ptr [r13+7D0h], 0
0x1800f78d1  jnz     short loc_1800F7951
0x1800f78d3  lea     r9, [rsp+2A0h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800f78d8  mov     [rsp+2A0h+dwNumberOfBytesRead], 0
0x1800f78e0  mov     r8d, 1000h; dwNumberOfBytesToRead
0x1800f78e6  mov     rdx, r14; lpBuffer
0x1800f78e9  mov     rcx, r12; hFile
0x1800f78ec  call    cs:__imp_InternetReadFile
0x1800f78f2  test    eax, eax
0x1800f78f4  jz      short loc_1800F7937
0x1800f78f6  mov     r8d, [rsp+2A0h+dwNumberOfBytesRead]; nNumberOfBytesToWrite
0x1800f78fb  test    r8d, r8d
0x1800f78fe  jz      short loc_1800F7956
0x1800f7900  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800f7905  mov     [rsp+2A0h+NumberOfBytesWritten], 0
0x1800f790d  mov     rdx, r14; lpBuffer
0x1800f7910  mov     qword ptr [rsp+2A0h+dwCreationDisposition], 0; lpOverlapped
0x1800f7919  mov     rcx, r15; hFile
0x1800f791c  call    cs:__imp_WriteFile
0x1800f7922  test    eax, eax
0x1800f7924  jz      short loc_1800F7937
0x1800f7926  mov     eax, [rsp+2A0h+dwNumberOfBytesRead]
0x1800f792a  cmp     [rsp+2A0h+NumberOfBytesWritten], eax
0x1800f792e  jz      short loc_1800F78C1
0x1800f7930  mov     ebx, 8007001Dh
0x1800f7935  jmp     short loc_1800F78C1
0x1800f7937  call    cs:__imp_GetLastError
0x1800f793d  mov     ebx, eax
0x1800f793f  test    eax, eax
0x1800f7941  jle     loc_1800F78C1
0x1800f7947  movzx   ebx, ax
0x1800f794a  or      ebx, edi
0x1800f794c  jmp     loc_1800F78C1
0x1800f7951  mov     ebx, 800703E3h
0x1800f7956  mov     rcx, r14; pv
0x1800f7959  call    cs:__imp_CoTaskMemFree
0x1800f795f  mov     rcx, r15; hObject
0x1800f7962  call    cs:__imp_CloseHandle
0x1800f7968  test    ebx, ebx
0x1800f796a  jns     short loc_1800F7975
0x1800f796c  mov     rcx, rsi; lpFileName
0x1800f796f  call    cs:__imp_DeleteFileW
0x1800f7975  mov     eax, ebx
0x1800f7977  jmp     short loc_1800F797E
0x1800f7979  mov     eax, 80070057h
0x1800f797e  mov     rcx, [rbp+1A0h+var_40]
0x1800f7985  xor     rcx, rsp; StackCookie
0x1800f7988  call    __security_check_cookie
0x1800f798d  mov     rbx, [rsp+2A0h+arg_18]
0x1800f7995  add     rsp, 270h
0x1800f799c  pop     r15
0x1800f799e  pop     r14
0x1800f79a0  pop     r13
0x1800f79a2  pop     r12
0x1800f79a4  pop     rdi
0x1800f79a5  pop     rsi
0x1800f79a6  pop     rbp
0x1800f79a7  retn
```
