# CVersionManagerServer::_DownloadBlockListToTempFile(void *,ushort *,ulong)

- ea: `0x180101fec`
- end: `0x1801022ba`
- name: `?_DownloadBlockListToTempFile@CVersionManagerServer@@AEAAJPEAXPEAGK@Z`
- size: `718`
- prototype: `__int64 __fastcall(CVersionManagerServer *this, void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x1801022c0`

## callees

- `0x18005cb10`
- `0x1801018e0`
- `0x180101fec`
- `0x1801285fe`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801020bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801020bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102267`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180102096`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180102096`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010220c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010220c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801020b1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801020b1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010227a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010227a`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1801020ff`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1801020ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180102132`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180102132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180102184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180102184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180102258`
- `WININET!InternetReadFile` at `0x1801021d6`
- `WININET!InternetReadFile` at `0x1801021d6`

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
0x180101fec  mov     [rsp-8+arg_18], rbx
0x180101ff1  push    rbp
0x180101ff2  push    rsi
0x180101ff3  push    rdi
0x180101ff4  push    r12
0x180101ff6  push    r13
0x180101ff8  push    r14
0x180101ffa  push    r15
0x180101ffc  lea     rbp, [rsp-170h]
0x180102004  sub     rsp, 270h
0x18010200b  mov     rax, cs:__security_cookie
0x180102012  xor     rax, rsp
0x180102015  mov     [rbp+1A0h+var_40], rax
0x18010201c  xor     r14d, r14d
0x18010201f  mov     rsi, r8
0x180102022  mov     r12, rdx
0x180102025  mov     r13, rcx
0x180102028  test    rdx, rdx
0x18010202b  jz      loc_18010228A
0x180102031  test    r8, r8
0x180102034  jz      loc_18010228A
0x18010203a  mov     [r8], r14w
0x18010203e  lea     rcx, [rsp+2A0h+pszPath]; void *
0x180102043  mov     r8d, 208h; Size
0x180102049  xor     edx, edx; Val
0x18010204b  call    memset_0
0x180102050  lea     r8, [r13+1Eh]; unsigned __int16 *
0x180102054  mov     [rsp+2A0h+dwFlagsAndAttributes], r14d; unsigned int
0x180102059  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; unsigned __int16 **
0x18010205e  mov     qword ptr [rsp+2A0h+NumberOfBytesWritten], r14
0x180102063  mov     edx, 104h; unsigned __int64
0x180102068  mov     qword ptr [rsp+2A0h+dwCreationDisposition], r14; unsigned __int64 *
0x18010206d  lea     rcx, [rsp+2A0h+pszPath]; pszDest
0x180102072  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180102077  mov     ebx, eax
0x180102079  test    eax, eax
0x18010207b  js      loc_180102286
0x180102081  mov     rdx, qword ptr [rsp+2A0h+NumberOfBytesWritten]
0x180102086  lea     rax, [rsp+2A0h+pszPath]
0x18010208b  sub     rdx, rax
0x18010208e  lea     rcx, [rsp+2A0h+pszPath]; pszPath
0x180102093  sar     rdx, 1; cchPath
0x180102096  call    cs:__imp_PathCchRemoveFileSpec
0x18010209d  nop     dword ptr [rax+rax+00h]
0x1801020a2  mov     ebx, eax
0x1801020a4  test    eax, eax
0x1801020a6  js      loc_180102286
0x1801020ac  lea     rcx, [rsp+2A0h+pszPath]; lpFileName
0x1801020b1  call    cs:__imp_GetFileAttributesW
0x1801020b8  nop     dword ptr [rax+rax+00h]
0x1801020bd  mov     edi, eax
0x1801020bf  call    cs:__imp_GetLastError
0x1801020c6  nop     dword ptr [rax+rax+00h]
0x1801020cb  cmp     edi, 0FFFFFFFFh
0x1801020ce  jnz     loc_18010216B
0x1801020d4  cmp     eax, 2
0x1801020d7  jnz     short loc_1801020ED
0x1801020d9  lea     rdx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x1801020de  call    ?_CreateLocalDirectory@CVersionManagerServer@@AEAAJPEBG@Z; CVersionManagerServer::_CreateLocalDirectory(ushort const *)
0x1801020e3  mov     ebx, eax
0x1801020e5  test    eax, eax
0x1801020e7  js      loc_180102286
0x1801020ed  mov     r9, rsi; lpTempFileName
0x1801020f0  lea     rdx, aVer; "ver"
0x1801020f7  xor     r8d, r8d; uUnique
0x1801020fa  lea     rcx, [rsp+2A0h+pszPath]; lpPathName
0x1801020ff  call    cs:__imp_GetTempFileNameW
0x180102106  nop     dword ptr [rax+rax+00h]
0x18010210b  test    eax, eax
0x18010210d  jz      short loc_180102147
0x18010210f  mov     [rsp+2A0h+hTemplateFile], r14; hTemplateFile
0x180102114  xor     r9d, r9d; lpSecurityAttributes
0x180102117  mov     [rsp+2A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18010211f  xor     r8d, r8d; dwShareMode
0x180102122  mov     edx, 40000000h; dwDesiredAccess
0x180102127  mov     [rsp+2A0h+dwCreationDisposition], 2; dwCreationDisposition
0x18010212f  mov     rcx, rsi; lpFileName
0x180102132  call    cs:__imp_CreateFileW
0x180102139  nop     dword ptr [rax+rax+00h]
0x18010213e  mov     r15, rax
0x180102141  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180102145  jnz     short loc_18010217F
0x180102147  call    cs:__imp_GetLastError
0x18010214e  nop     dword ptr [rax+rax+00h]
0x180102153  mov     ebx, eax
0x180102155  test    eax, eax
0x180102157  jle     loc_180102286
0x18010215d  movzx   ebx, ax
0x180102160  or      ebx, 80070000h
0x180102166  jmp     loc_180102286
0x18010216b  test    dil, 10h
0x18010216f  jnz     loc_1801020ED
0x180102175  mov     ebx, 800700A1h
0x18010217a  jmp     loc_180102286
0x18010217f  mov     ecx, 1000h; cb
0x180102184  call    cs:__imp_CoTaskMemAlloc
0x18010218b  nop     dword ptr [rax+rax+00h]
0x180102190  mov     r14, rax
0x180102193  test    rax, rax
0x180102196  jnz     short loc_1801021A2
0x180102198  mov     ebx, 8007000Eh
0x18010219d  jmp     loc_180102264
0x1801021a2  mov     edi, 80070000h
0x1801021a7  test    ebx, ebx
0x1801021a9  js      loc_180102255
0x1801021af  cmp     byte ptr [r13+7D0h], 0
0x1801021b7  jnz     loc_180102250
0x1801021bd  lea     r9, [rsp+2A0h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1801021c2  mov     [rsp+2A0h+dwNumberOfBytesRead], 0
0x1801021ca  mov     r8d, 1000h; dwNumberOfBytesToRead
0x1801021d0  mov     rdx, r14; lpBuffer
0x1801021d3  mov     rcx, r12; hFile
0x1801021d6  call    cs:__imp_InternetReadFile
0x1801021dd  nop     dword ptr [rax+rax+00h]
0x1801021e2  test    eax, eax
0x1801021e4  jz      short loc_180102230
0x1801021e6  mov     r8d, [rsp+2A0h+dwNumberOfBytesRead]; nNumberOfBytesToWrite
0x1801021eb  test    r8d, r8d
0x1801021ee  jz      short loc_180102255
0x1801021f0  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801021f5  mov     [rsp+2A0h+NumberOfBytesWritten], 0
0x1801021fd  mov     rdx, r14; lpBuffer
0x180102200  mov     qword ptr [rsp+2A0h+dwCreationDisposition], 0; lpOverlapped
0x180102209  mov     rcx, r15; hFile
0x18010220c  call    cs:__imp_WriteFile
0x180102213  nop     dword ptr [rax+rax+00h]
0x180102218  test    eax, eax
0x18010221a  jz      short loc_180102230
0x18010221c  mov     eax, [rsp+2A0h+dwNumberOfBytesRead]
0x180102220  cmp     [rsp+2A0h+NumberOfBytesWritten], eax
0x180102224  jz      short loc_1801021A7
0x180102226  mov     ebx, 8007001Dh
0x18010222b  jmp     loc_1801021A7
0x180102230  call    cs:__imp_GetLastError
0x180102237  nop     dword ptr [rax+rax+00h]
0x18010223c  mov     ebx, eax
0x18010223e  test    eax, eax
0x180102240  jle     loc_1801021A7
0x180102246  movzx   ebx, ax
0x180102249  or      ebx, edi
0x18010224b  jmp     loc_1801021A7
0x180102250  mov     ebx, 800703E3h
0x180102255  mov     rcx, r14; pv
0x180102258  call    cs:__imp_CoTaskMemFree
0x18010225f  nop     dword ptr [rax+rax+00h]
0x180102264  mov     rcx, r15; hObject
0x180102267  call    cs:__imp_CloseHandle
0x18010226e  nop     dword ptr [rax+rax+00h]
0x180102273  test    ebx, ebx
0x180102275  jns     short loc_180102286
0x180102277  mov     rcx, rsi; lpFileName
0x18010227a  call    cs:__imp_DeleteFileW
0x180102281  nop     dword ptr [rax+rax+00h]
0x180102286  mov     eax, ebx
0x180102288  jmp     short loc_18010228F
0x18010228a  mov     eax, 80070057h
0x18010228f  mov     rcx, [rbp+1A0h+var_40]
0x180102296  xor     rcx, rsp; StackCookie
0x180102299  call    __security_check_cookie
0x18010229e  mov     rbx, [rsp+2A0h+arg_18]
0x1801022a6  add     rsp, 270h
0x1801022ad  pop     r15
0x1801022af  pop     r14
0x1801022b1  pop     r13
0x1801022b3  pop     r12
0x1801022b5  pop     rdi
0x1801022b6  pop     rsi
0x1801022b7  pop     rbp
0x1801022b8  retn
```
