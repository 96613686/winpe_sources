# CRecycleBinBase::_ReadRecycleData(ushort const *,RecycleDataV2 *)

- ea: `0x18001f1d8`
- end: `0x18001f54a`
- name: `?_ReadRecycleData@CRecycleBinBase@@IEAAJPEBGPEAURecycleDataV2@@@Z`
- size: `882`
- prototype: `int(CRecycleBinBase *__hidden this, const unsigned __int16 *, struct RecycleDataV2 *)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180070770`
- `0x180070d64`
- `0x180072310`
- `0x180073730`
- `0x180437930`

## callees

- `0x18001f1d8`
- `0x18001f630`
- `0x1800208d8`
- `0x180020904`
- `0x180233280`
- `0x1802342fc`
- `0x180437d78`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001f520`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001f520`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f416`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f416`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f273`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f2ca`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f44c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f4c3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f273`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f2ca`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f44c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001f4c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f30f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f30f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f23b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f23b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f3c4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f3c4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001f3a5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001f3a5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001f213`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001f213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f306`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f471`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f306`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f471`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecycleBinBase::_ReadRecycleData(
        CRecycleBinBase *this,
        const unsigned __int16 *a2,
        struct RecycleDataV2 *a3)
{
  const unsigned __int16 *v4; // rbx
  LPWSTR FileNameW; // rdi
  signed int Error; // esi
  HANDLE FileW; // r14
  _DWORD *v8; // rdi
  __int64 v9; // rcx
  void *v10; // rbx
  __int64 v12; // rax
  __int64 v13; // rdx
  WCHAR *v14; // r8
  unsigned __int16 v15; // cx
  WCHAR *v16; // rcx
  DWORD v17; // edi
  void *v18; // rdi
  void *v19; // rcx
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Buffer[544]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+270h] [rbp+170h] BYREF

  v4 = a2;
  FileNameW = PathFindFileNameW(a2);
  Error = -2147024809;
  if ( CompareStringOrdinal(FileNameW, 2, L"$R", -1, 1) != 2 )
    goto LABEL_2;
  v12 = 2147483646;
  v13 = 260;
  v14 = pszPath;
  do
  {
    if ( !v12 )
      break;
    v15 = *v4;
    if ( !*v4 )
      break;
    ++v4;
    *v14++ = v15;
    --v12;
    --v13;
  }
  while ( v13 );
  Error = v13 == 0 ? 0x8007007A : 0;
  v16 = v14 - 1;
  if ( v13 )
    v16 = v14;
  *v16 = 0;
  if ( !v13 )
    goto LABEL_2;
  if ( !PathRemoveFileSpecW(pszPath) )
  {
    Error = -2147467259;
LABEL_2:
    FileW = 0;
    goto LABEL_3;
  }
  Error = PathCchAppend(pszPath, 0x104u, L"$I");
  if ( Error < 0 )
    goto LABEL_2;
  Error = StringCchCatW(pszPath, 0x104u, FileNameW + 2);
  if ( Error < 0 )
    goto LABEL_2;
  FileW = CreateFileW(pszPath, 0x10001u, 5u, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_4;
  Error = ResultFromKnownLastError();
LABEL_3:
  if ( Error >= 0 )
  {
LABEL_4:
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, a3, 0x18u, &NumberOfBytesRead, 0) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_14;
    }
    if ( NumberOfBytesRead == 24 && *(_DWORD *)a3 )
    {
      if ( *(_DWORD *)a3 != 1 )
      {
        Error = 0;
        if ( *(_DWORD *)a3 == 2 )
        {
          v8 = (_DWORD *)((char *)a3 + 24);
          if ( ReadFile(FileW, (char *)a3 + 24, 4u, &NumberOfBytesRead, 0)
            || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            if ( *v8 )
            {
              pv = 0;
              Error = _AllocArray<unsigned short,CTCoAllocPolicy>(v9, 1, (unsigned int)*v8, &pv);
              v10 = pv;
              if ( Error >= 0 )
              {
                v17 = 2 * *v8;
                if ( ReadFile(FileW, pv, v17, &NumberOfBytesRead, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
                {
                  if ( NumberOfBytesRead == v17 )
                  {
                    Error = 0;
                    v18 = v10;
                    v10 = 0;
                    v19 = (void *)*((_QWORD *)a3 + 4);
                    *((_QWORD *)a3 + 4) = 0;
                    CoTaskMemFree(v19);
                    *((_QWORD *)a3 + 4) = v18;
                  }
                  else
                  {
                    Error = -2147467259;
                  }
                }
              }
              CoTaskMemFree(v10);
            }
          }
        }
        goto LABEL_14;
      }
      memset_0(Buffer, 0, sizeof(Buffer));
      if ( SetFilePointer(FileW, 0, 0, 0) == -1 && (Error = ResultFromKnownLastError(), Error < 0)
        || !ReadFile(FileW, Buffer, 0x220u, &NumberOfBytesRead, 0) && (Error = ResultFromKnownLastError(), Error < 0) )
      {
LABEL_14:
        CloseHandle(FileW);
        return (unsigned int)Error;
      }
      if ( NumberOfBytesRead == 544 )
      {
        Error = 0;
        RecycleDataV2::_Initialize((const struct RecycleDataV1 *)Buffer, a3);
        goto LABEL_14;
      }
    }
    Error = -2147467259;
    goto LABEL_14;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001f1d8  mov     [rsp-8+arg_0], rbx
0x18001f1dd  mov     [rsp-8+arg_18], rsi
0x18001f1e2  push    rbp
0x18001f1e3  push    rdi
0x18001f1e4  push    r12
0x18001f1e6  push    r14
0x18001f1e8  push    r15
0x18001f1ea  lea     rbp, [rsp-390h]
0x18001f1f2  sub     rsp, 490h
0x18001f1f9  mov     rax, cs:__security_cookie
0x18001f200  xor     rax, rsp
0x18001f203  mov     [rbp+3B0h+var_30], rax
0x18001f20a  mov     r15, r8
0x18001f20d  mov     rbx, rdx
0x18001f210  mov     rcx, rdx; pszPath
0x18001f213  call    cs:__imp_PathFindFileNameW
0x18001f219  mov     rdi, rax
0x18001f21c  mov     esi, 80070057h
0x18001f221  mov     [rsp+4B0h+bIgnoreCase], 1; bIgnoreCase
0x18001f229  or      r9d, 0FFFFFFFFh; cchCount2
0x18001f22d  lea     r8, aR_0; "$R"
0x18001f234  lea     edx, [r9+3]; cchCount1
0x18001f238  mov     rcx, rax; lpString1
0x18001f23b  call    cs:__imp_CompareStringOrdinal
0x18001f241  xor     r12d, r12d
0x18001f244  cmp     eax, 2
0x18001f247  jz      loc_18001F342
0x18001f24d  mov     r14, r12
0x18001f250  test    esi, esi
0x18001f252  js      loc_18001F315
0x18001f258  mov     [rsp+4B0h+NumberOfBytesRead], r12d
0x18001f25d  mov     qword ptr [rsp+4B0h+bIgnoreCase], r12; lpOverlapped
0x18001f262  lea     r9, [rsp+4B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001f267  mov     r8d, 18h; nNumberOfBytesToRead
0x18001f26d  mov     rdx, r15; lpBuffer
0x18001f270  mov     rcx, r14; hFile
0x18001f273  call    cs:__imp_ReadFile
0x18001f279  test    eax, eax
0x18001f27b  jnz     short loc_18001F28C
0x18001f27d  call    ResultFromKnownLastError
0x18001f282  mov     esi, eax
0x18001f284  test    eax, eax
0x18001f286  js      loc_18001F30C
0x18001f28c  cmp     [rsp+4B0h+NumberOfBytesRead], 18h
0x18001f291  jnz     loc_18001F4A4
0x18001f297  cmp     dword ptr [r15], 1
0x18001f29b  jb      loc_18001F4A4
0x18001f2a1  jz      loc_18001F501
0x18001f2a7  mov     esi, r12d
0x18001f2aa  cmp     dword ptr [r15], 2
0x18001f2ae  jnz     short loc_18001F30C
0x18001f2b0  lea     rdi, [r15+18h]
0x18001f2b4  mov     qword ptr [rsp+4B0h+bIgnoreCase], r12; lpOverlapped
0x18001f2b9  lea     r9, [rsp+4B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001f2be  mov     r8d, 4; nNumberOfBytesToRead
0x18001f2c4  mov     rdx, rdi; lpBuffer
0x18001f2c7  mov     rcx, r14; hFile
0x18001f2ca  call    cs:__imp_ReadFile
0x18001f2d0  test    eax, eax
0x18001f2d2  jz      loc_18001F480
0x18001f2d8  cmp     [rdi], r12d
0x18001f2db  jz      short loc_18001F30C
0x18001f2dd  mov     [rsp+4B0h+pv], r12
0x18001f2e2  mov     r8d, [rdi]
0x18001f2e5  lea     r9, [rsp+4B0h+pv]
0x18001f2ea  mov     edx, 1
0x18001f2ef  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18001f2f4  mov     esi, eax
0x18001f2f6  mov     rbx, [rsp+4B0h+pv]
0x18001f2fb  test    eax, eax
0x18001f2fd  jns     loc_18001F435
0x18001f303  mov     rcx, rbx; pv
0x18001f306  call    cs:__imp_CoTaskMemFree
0x18001f30c  mov     rcx, r14; hObject
0x18001f30f  call    cs:__imp_CloseHandle
0x18001f315  mov     eax, esi
0x18001f317  mov     rcx, [rbp+3B0h+var_30]
0x18001f31e  xor     rcx, rsp; StackCookie
0x18001f321  call    __security_check_cookie
0x18001f326  lea     r11, [rsp+4B0h+var_20]
0x18001f32e  mov     rbx, [r11+30h]
0x18001f332  mov     rsi, [r11+48h]
0x18001f336  mov     rsp, r11
0x18001f339  pop     r15
0x18001f33b  pop     r14
0x18001f33d  pop     r12
0x18001f33f  pop     rdi
0x18001f340  pop     rbp
0x18001f341  retn
0x18001f342  mov     eax, 7FFFFFFEh
0x18001f347  mov     r14d, 104h
0x18001f34d  mov     edx, r14d
0x18001f350  lea     r8, [rbp+3B0h+pszPath]
0x18001f357  test    rax, rax
0x18001f35a  jz      short loc_18001F379
0x18001f35c  movzx   ecx, word ptr [rbx]
0x18001f35f  test    cx, cx
0x18001f362  jz      short loc_18001F379
0x18001f364  add     rbx, 2
0x18001f368  mov     [r8], cx
0x18001f36c  add     r8, 2
0x18001f370  dec     rax
0x18001f373  sub     rdx, 1
0x18001f377  jnz     short loc_18001F357
0x18001f379  mov     rax, rdx
0x18001f37c  neg     rax
0x18001f37f  sbb     esi, esi
0x18001f381  not     esi
0x18001f383  and     esi, 8007007Ah
0x18001f389  lea     rcx, [r8-2]
0x18001f38d  test    rdx, rdx
0x18001f390  cmovnz  rcx, r8
0x18001f394  mov     [rcx], r12w
0x18001f398  jz      loc_18001F24D
0x18001f39e  lea     rcx, [rbp+3B0h+pszPath]; pszPath
0x18001f3a5  call    cs:__imp_PathRemoveFileSpecW
0x18001f3ab  test    eax, eax
0x18001f3ad  jz      loc_18001F4F7
0x18001f3b3  lea     r8, pszMore; "$I"
0x18001f3ba  mov     rdx, r14; cchPath
0x18001f3bd  lea     rcx, [rbp+3B0h+pszPath]; pszPath
0x18001f3c4  call    cs:__imp_PathCchAppend
0x18001f3ca  mov     esi, eax
0x18001f3cc  test    eax, eax
0x18001f3ce  js      loc_18001F24D
0x18001f3d4  lea     r8, [rdi+4]; unsigned __int16 *
0x18001f3d8  mov     rdx, r14; unsigned __int64
0x18001f3db  lea     rcx, [rbp+3B0h+pszPath]; unsigned __int16 *
0x18001f3e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f3e7  mov     esi, eax
0x18001f3e9  test    eax, eax
0x18001f3eb  js      loc_18001F24D
0x18001f3f1  mov     [rsp+4B0h+hTemplateFile], r12; hTemplateFile
0x18001f3f6  mov     [rsp+4B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18001f3fb  mov     [rsp+4B0h+bIgnoreCase], 3; dwCreationDisposition
0x18001f403  xor     r9d, r9d; lpSecurityAttributes
0x18001f406  mov     edx, 10001h; dwDesiredAccess
0x18001f40b  lea     r8d, [r9+5]; dwShareMode
0x18001f40f  lea     rcx, [rbp+3B0h+pszPath]; lpFileName
0x18001f416  call    cs:__imp_CreateFileW
0x18001f41c  mov     r14, rax
0x18001f41f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f423  jnz     loc_18001F258
0x18001f429  call    ResultFromKnownLastError
0x18001f42e  mov     esi, eax
0x18001f430  jmp     loc_18001F250
0x18001f435  mov     edi, [rdi]
0x18001f437  add     edi, edi
0x18001f439  mov     qword ptr [rsp+4B0h+bIgnoreCase], r12; lpOverlapped
0x18001f43e  lea     r9, [rsp+4B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001f443  mov     r8d, edi; nNumberOfBytesToRead
0x18001f446  mov     rdx, rbx; lpBuffer
0x18001f449  mov     rcx, r14; hFile
0x18001f44c  call    cs:__imp_ReadFile
0x18001f452  test    eax, eax
0x18001f454  jz      short loc_18001F494
0x18001f456  cmp     [rsp+4B0h+NumberOfBytesRead], edi
0x18001f45a  jnz     loc_18001F53F
0x18001f460  mov     esi, r12d
0x18001f463  mov     rdi, rbx
0x18001f466  mov     rbx, r12
0x18001f469  mov     rcx, [r15+20h]; pv
0x18001f46d  mov     [r15+20h], r12
0x18001f471  call    cs:__imp_CoTaskMemFree
0x18001f477  mov     [r15+20h], rdi
0x18001f47b  jmp     loc_18001F303
0x18001f480  call    ResultFromKnownLastError
0x18001f485  mov     esi, eax
0x18001f487  test    eax, eax
0x18001f489  js      loc_18001F30C
0x18001f48f  jmp     loc_18001F2D8
0x18001f494  call    ResultFromKnownLastError
0x18001f499  mov     esi, eax
0x18001f49b  test    eax, eax
0x18001f49d  jns     short loc_18001F456
0x18001f49f  jmp     loc_18001F303
0x18001f4a4  mov     esi, 80004005h
0x18001f4a9  jmp     loc_18001F30C
0x18001f4ae  mov     qword ptr [rsp+4B0h+bIgnoreCase], r12; lpOverlapped
0x18001f4b3  lea     r9, [rsp+4B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001f4b8  mov     r8d, ebx; nNumberOfBytesToRead
0x18001f4bb  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x18001f4c0  mov     rcx, r14; hFile
0x18001f4c3  call    cs:__imp_ReadFile
0x18001f4c9  test    eax, eax
0x18001f4cb  jnz     short loc_18001F4DC
0x18001f4cd  call    ResultFromKnownLastError
0x18001f4d2  mov     esi, eax
0x18001f4d4  test    eax, eax
0x18001f4d6  js      loc_18001F30C
0x18001f4dc  cmp     [rsp+4B0h+NumberOfBytesRead], ebx
0x18001f4e0  jnz     short loc_18001F4A4
0x18001f4e2  mov     esi, r12d
0x18001f4e5  mov     rdx, r15; struct RecycleDataV2 *
0x18001f4e8  lea     rcx, [rsp+4B0h+Buffer]; struct RecycleDataV1 *
0x18001f4ed  call    ?_Initialize@RecycleDataV2@@SAJPEBURecycleDataV1@@PEAU1@@Z; RecycleDataV2::_Initialize(RecycleDataV1 const *,RecycleDataV2 *)
0x18001f4f2  jmp     loc_18001F30C
0x18001f4f7  mov     esi, 80004005h
0x18001f4fc  jmp     loc_18001F24D
0x18001f501  mov     ebx, 220h
0x18001f506  mov     r8d, ebx; Size
0x18001f509  xor     edx, edx; Val
0x18001f50b  lea     rcx, [rsp+4B0h+Buffer]; void *
0x18001f510  call    memset_0
0x18001f515  xor     r9d, r9d; dwMoveMethod
0x18001f518  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001f51b  xor     edx, edx; lDistanceToMove
0x18001f51d  mov     rcx, r14; hFile
0x18001f520  call    cs:__imp_SetFilePointer
0x18001f526  cmp     eax, 0FFFFFFFFh
0x18001f529  jnz     short loc_18001F4AE
0x18001f52b  call    ResultFromKnownLastError
0x18001f530  mov     esi, eax
0x18001f532  test    eax, eax
0x18001f534  js      loc_18001F30C
0x18001f53a  jmp     loc_18001F4AE
0x18001f53f  mov     esi, 80004005h
0x18001f544  jmp     loc_18001F303
```
