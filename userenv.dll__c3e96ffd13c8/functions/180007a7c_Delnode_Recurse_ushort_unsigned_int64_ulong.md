# _Delnode_Recurse(ushort *,unsigned __int64,ulong)

- ea: `0x180007a7c`
- end: `0x180007f06`
- name: `?_Delnode_Recurse@@YAJPEAG_KK@Z`
- size: `1162`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180007a7c`
- `0x180018ff4`

## callees

- `0x180007a7c`
- `0x18000804c`
- `0x1800080b4`
- `0x18000814c`
- `0x1800082d0`
- `0x180008314`
- `0x18000cfe4`
- `0x180018a2c`
- `0x1800191fc`
- `0x18001992c`
- `0x18001995c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b7e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007ba2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b7e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007ba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007efb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007efb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007d72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007c6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007d72`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180007b4e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180007de3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180007b4e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180007de3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180007bf4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180007c95`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180007bf4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180007c95`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180007be3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180007be3`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x180007afc`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x180007afc`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x180007ece`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x180007ece`

## string_xrefs

- `0x180007c77`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180007cf5`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180007d22`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180007d5e`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180007e36`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180007e7d`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall _Delnode_Recurse(unsigned __int16 *a1, unsigned __int64 a2, unsigned int a3)
{
  char v3; // r13
  __int64 StringLengthHr; // rax
  unsigned int v7; // ebx
  struct _WIN32_FIND_DATAW *v8; // rdi
  unsigned __int16 *v9; // rsi
  HRESULT v10; // eax
  wil::details::in1diag3 *v11; // rcx
  struct _WIN32_FIND_DATAW *v12; // rax
  HANDLE FirstFileW; // r14
  int v14; // eax
  char *v16; // r13
  char v17; // bl
  __int64 v18; // rdx
  signed int v19; // eax
  int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  unsigned __int16 *v24; // rax
  __int64 v25; // rdx
  DWORD LastError; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-30h]
  PWSTR ppszEnd; // [rsp+30h] [rbp-20h] BYREF
  size_t pcchRemaining; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v31; // [rsp+40h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  char *v35; // [rsp+A8h] [rbp+58h] BYREF

  v3 = a3;
  LODWORD(v35) = -2147467259;
  ppszEnd = 0;
  pcchRemaining = 0;
  StringLengthHr = anonymous_namespace_::_GetStringLengthHr(&v35, a1);
  v7 = (unsigned int)v35;
  if ( (int)v35 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xCC3,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v35,
      bIgnoreCase);
    return v7;
  }
  v8 = 0;
  if ( a2 >= StringLengthHr + 262 )
  {
    LODWORD(v35) = 0;
    v9 = a1;
    v31 = a1;
    goto LABEL_4;
  }
  a2 += 520LL;
  v24 = (unsigned __int16 *)ProfAlloc(2 * a2);
  v9 = v24;
  v31 = v24;
  if ( v24 )
  {
    LODWORD(v35) = 1;
    v20 = StringCchCopyW(v24, a2, a1);
    v7 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCD7,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
LABEL_36:
      LocalFree(v9);
LABEL_17:
      if ( v8 )
        LocalFree(v8);
      return v7;
    }
LABEL_4:
    v10 = PathCchAddBackslashEx(v9, a2, &ppszEnd, &pcchRemaining);
    v7 = v10;
    v11 = retaddr;
    if ( v10 >= 0 )
    {
      v10 = StringCchCopyW(ppszEnd, pcchRemaining, L"*.*");
      v7 = v10;
      v11 = retaddr;
      if ( v10 < 0 )
      {
        v25 = 3310;
        goto LABEL_53;
      }
      v12 = (struct _WIN32_FIND_DATAW *)ProfAlloc(0x250u);
      v8 = v12;
      if ( v12 )
      {
        FirstFileW = FindFirstFileW(v9, v12);
        if ( FirstFileW != (HANDLE)-1LL )
        {
          while ( 1 )
          {
LABEL_8:
            if ( CompareStringOrdinal(v8->cFileName, -1, L".", -1, 1) != 2
              && CompareStringOrdinal(v8->cFileName, -1, L"..", -1, 1) != 2 )
            {
              v14 = StringCchCopyW(ppszEnd, pcchRemaining, v8->cFileName);
              v7 = v14;
              if ( v14 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xD51,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                  (const char *)(unsigned int)v14,
                  bIgnoreCasea);
                FindClose(FirstFileW);
                goto LABEL_16;
              }
              if ( (v8->dwFileAttributes & 0x10) != 0 )
              {
                wil::TryCreateFileCanRecurseIntoDirectory(&hObject, v9, v8);
                v16 = (char *)hObject;
                if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                {
                  v17 = 0;
                  if ( (v8->dwFileAttributes & 0x400) != 0 && !byte_180028688 )
                  {
                    if ( (CfGetPlaceholderStateFromAttributeTag(v8->dwFileAttributes, v8->dwReserved0) & 2) != 0 )
                    {
                      v17 = 1;
                      byte_180028688 = 1;
                      UserenvTelemetry::EnterAndDeleteCloudFilesFolder();
                    }
                    else
                    {
                      UserenvTelemetry::EnterAndDeleteNotCloudFilesReparsePointsFolder<unsigned short * &>(&v31);
                    }
                  }
                  _Delnode_Recurse(v9, a2, a3);
                  StringCchCopyW(ppszEnd, pcchRemaining, v8->cFileName);
                  if ( v17 )
                    byte_180028688 = 0;
                }
                _TryBestToDelete(v9, v8->dwFileAttributes, a3);
                if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  CloseHandle(v16);
                v3 = a3;
              }
              else
              {
                _TryBestToDelete(v9, v8->dwFileAttributes, v3);
              }
            }
            if ( !FindNextFileW(FirstFileW, v8) )
            {
              FindClose(FirstFileW);
              goto LABEL_15;
            }
          }
        }
        LastError = GetLastError();
        if ( LastError - 2 <= 1 )
        {
LABEL_15:
          v7 = 0;
          goto LABEL_16;
        }
        if ( LastError == 5 && (v3 & 2) != 0 )
        {
          *ppszEnd = 0;
          v10 = _TakeOwnerAndAddAccess(v9);
          v7 = v10;
          v11 = retaddr;
          if ( v10 < 0 )
          {
            v25 = 3353;
          }
          else
          {
            v10 = StringCchCopyW(ppszEnd, pcchRemaining, L"*.*");
            v7 = v10;
            v11 = retaddr;
            if ( v10 >= 0 )
            {
              FirstFileW = FindFirstFileW(v9, v8);
              if ( FirstFileW != (HANDLE)-1LL )
                goto LABEL_8;
              v22 = GetLastError();
              v7 = v22;
              if ( v22 > 0 )
                v7 = (unsigned __int16)v22 | 0x80070000;
              v18 = 3374;
              goto LABEL_30;
            }
            v25 = 3363;
          }
LABEL_53:
          wil::details::in1diag3::_Log_Hr(
            v11,
            (void *)v25,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
            (const char *)(unsigned int)v10,
            bIgnoreCase);
LABEL_16:
          if ( !(_DWORD)v35 )
            goto LABEL_17;
          goto LABEL_36;
        }
        v23 = GetLastError();
        v7 = v23;
        if ( v23 > 0 )
          v7 = (unsigned __int16)v23 | 0x80070000;
        v18 = 3382;
      }
      else
      {
        v21 = GetLastError();
        v7 = v21;
        if ( v21 > 0 )
          v7 = (unsigned __int16)v21 | 0x80070000;
        v18 = 3323;
      }
LABEL_30:
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)v7,
        bIgnoreCase);
      goto LABEL_16;
    }
    v25 = 3304;
    goto LABEL_53;
  }
  v19 = GetLastError();
  v7 = v19;
  if ( v19 > 0 )
    v7 = (unsigned __int16)v19 | 0x80070000;
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0xCD0,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)v7,
    bIgnoreCase);
  return v7;
}

```

## disassembly

```asm
0x180007a7c  mov     [rsp-38h+arg_0], rbx
0x180007a81  mov     [rsp-38h+arg_10], r8d
0x180007a86  push    rbp
0x180007a87  push    rsi
0x180007a88  push    rdi
0x180007a89  push    r12
0x180007a8b  push    r13
0x180007a8d  push    r14
0x180007a8f  push    r15
0x180007a91  mov     rbp, rsp
0x180007a94  sub     rsp, 50h
0x180007a98  mov     r13d, r8d
0x180007a9b  mov     r15, rdx
0x180007a9e  mov     r14, rcx
0x180007aa1  mov     dword ptr [rbp+arg_18], 80004005h
0x180007aa8  mov     [rbp+ppszEnd], 0
0x180007ab0  mov     [rbp+pcchRemaining], 0
0x180007ab8  mov     rdx, rcx
0x180007abb  lea     rcx, [rbp+arg_18]
0x180007abf  call    _anonymous_namespace____GetStringLengthHr
0x180007ac4  mov     ebx, dword ptr [rbp+arg_18]
0x180007ac7  mov     rcx, [rbp+38h]; this
0x180007acb  test    ebx, ebx
0x180007acd  js      loc_180007E33
0x180007ad3  xor     edi, edi
0x180007ad5  add     rax, 106h
0x180007adb  cmp     r15, rax
0x180007ade  jb      loc_180007E4C
0x180007ae4  mov     dword ptr [rbp+arg_18], edi
0x180007ae7  mov     rsi, r14
0x180007aea  mov     [rbp+var_10], r14
0x180007aee  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x180007af2  lea     r8, [rbp+ppszEnd]; ppszEnd
0x180007af6  mov     rdx, r15; cchPath
0x180007af9  mov     rcx, rsi; pszPath
0x180007afc  call    cs:__imp_PathCchAddBackslashEx
0x180007b02  mov     ebx, eax
0x180007b04  mov     rcx, [rbp+38h]
0x180007b08  test    eax, eax
0x180007b0a  js      loc_180007E71
0x180007b10  lea     r8, asc_18001EAF8; "*.*"
0x180007b17  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x180007b1b  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x180007b1f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007b24  mov     ebx, eax
0x180007b26  mov     rcx, [rbp+38h]
0x180007b2a  test    eax, eax
0x180007b2c  js      loc_180007E91
0x180007b32  mov     ecx, 250h; dwBytes
0x180007b37  call    ?ProfAlloc@@YAPEAX_K@Z; ProfAlloc(unsigned __int64)
0x180007b3c  mov     rdi, rax
0x180007b3f  test    rax, rax
0x180007b42  jz      loc_180007D7D
0x180007b48  mov     rdx, rax; lpFindFileData
0x180007b4b  mov     rcx, rsi; lpFileName
0x180007b4e  call    cs:__imp_FindFirstFileW
0x180007b54  mov     r14, rax
0x180007b57  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007b5b  jz      loc_180007E98
0x180007b61  lea     r12, [rdi+2Ch]
0x180007b65  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x180007b6d  or      r9d, 0FFFFFFFFh; cchCount2
0x180007b71  lea     r8, asc_18001EAE8; "."
0x180007b78  or      edx, r9d; cchCount1
0x180007b7b  mov     rcx, r12; lpString1
0x180007b7e  call    cs:__imp_CompareStringOrdinal
0x180007b84  cmp     eax, 2
0x180007b87  jz      short loc_180007BDD
0x180007b89  mov     [rsp+50h+bIgnoreCase], 1; int
0x180007b91  or      r9d, 0FFFFFFFFh; cchCount2
0x180007b95  lea     r8, asc_18001EAEC; ".."
0x180007b9c  or      edx, r9d; cchCount1
0x180007b9f  mov     rcx, r12; lpString1
0x180007ba2  call    cs:__imp_CompareStringOrdinal
0x180007ba8  cmp     eax, 2
0x180007bab  jz      short loc_180007BDD
0x180007bad  mov     r8, r12; unsigned __int16 *
0x180007bb0  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x180007bb4  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x180007bb8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007bbd  mov     ebx, eax
0x180007bbf  mov     rcx, [rbp+38h]; this
0x180007bc3  test    eax, eax
0x180007bc5  js      loc_180007C74
0x180007bcb  test    byte ptr [rdi], 10h
0x180007bce  jnz     short loc_180007C25
0x180007bd0  mov     r8d, r13d; unsigned int
0x180007bd3  mov     edx, [rdi]; unsigned int
0x180007bd5  mov     rcx, rsi; lpFileName
0x180007bd8  call    ?_TryBestToDelete@@YAJPEBGKK@Z; _TryBestToDelete(ushort const *,ulong,ulong)
0x180007bdd  mov     rdx, rdi; lpFindFileData
0x180007be0  mov     rcx, r14; hFindFile
0x180007be3  call    cs:__imp_FindNextFileW
0x180007be9  test    eax, eax
0x180007beb  jnz     loc_180007B65
0x180007bf1  mov     rcx, r14; hFindFile
0x180007bf4  call    cs:__imp_FindClose
0x180007bfa  xor     ebx, ebx
0x180007bfc  cmp     dword ptr [rbp+arg_18], 0
0x180007c00  jnz     loc_180007D6F
0x180007c06  test    rdi, rdi
0x180007c09  jnz     short loc_180007C69
0x180007c0b  mov     eax, ebx
0x180007c0d  mov     rbx, [rsp+50h+arg_0]
0x180007c15  add     rsp, 50h
0x180007c19  pop     r15
0x180007c1b  pop     r14
0x180007c1d  pop     r13
0x180007c1f  pop     r12
0x180007c21  pop     rdi
0x180007c22  pop     rsi
0x180007c23  pop     rbp
0x180007c24  retn
0x180007c25  mov     r8, rdi
0x180007c28  mov     rdx, rsi
0x180007c2b  lea     rcx, [rbp+hObject]
0x180007c2f  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x180007c34  nop
0x180007c35  mov     r13, [rbp+hObject]
0x180007c39  lea     rax, [r13-1]
0x180007c3d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007c41  jbe     short loc_180007CA0
0x180007c43  mov     r8d, [rbp+arg_10]; unsigned int
0x180007c47  mov     edx, [rdi]; unsigned int
0x180007c49  mov     rcx, rsi; lpFileName
0x180007c4c  call    ?_TryBestToDelete@@YAJPEBGKK@Z; _TryBestToDelete(ushort const *,ulong,ulong)
0x180007c51  nop
0x180007c52  lea     rax, [r13-1]
0x180007c56  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007c5a  jbe     loc_180007EF8
0x180007c60  mov     r13d, [rbp+arg_10]
0x180007c64  jmp     loc_180007BDD
0x180007c69  mov     rcx, rdi; hMem
0x180007c6c  call    cs:__imp_LocalFree
0x180007c72  jmp     short loc_180007C0B
0x180007c74  mov     r9d, eax; char *
0x180007c77  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180007c7e  mov     edx, 0D51h; void *
0x180007c83  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007c88  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180007c8c  jz      loc_180007BFC
0x180007c92  mov     rcx, r14; hFindFile
0x180007c95  call    cs:__imp_FindClose
0x180007c9b  jmp     loc_180007BFC
0x180007ca0  xor     bl, bl
0x180007ca2  test    dword ptr [rdi], 400h
0x180007ca8  jz      short loc_180007CB6
0x180007caa  cmp     cs:byte_180028688, bl
0x180007cb0  jz      loc_180007EC9
0x180007cb6  mov     r8d, [rbp+arg_10]; unsigned int
0x180007cba  mov     rdx, r15; unsigned __int64
0x180007cbd  mov     rcx, rsi; unsigned __int16 *
0x180007cc0  call    ?_Delnode_Recurse@@YAJPEAG_KK@Z; _Delnode_Recurse(ushort *,unsigned __int64,ulong)
0x180007cc5  mov     r8, r12; unsigned __int16 *
0x180007cc8  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x180007ccc  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x180007cd0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007cd5  test    bl, bl
0x180007cd7  jz      loc_180007C43
0x180007cdd  mov     cs:byte_180028688, 0
0x180007ce4  jmp     loc_180007C43
0x180007ce9  mov     edx, 0D2Eh; void *
0x180007cee  mov     rcx, [rbp+38h]; this
0x180007cf2  mov     r9d, ebx; char *
0x180007cf5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180007cfc  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180007d01  jmp     loc_180007BFC
0x180007d06  call    cs:__imp_GetLastError
0x180007d0c  mov     ebx, eax
0x180007d0e  test    eax, eax
0x180007d10  jle     short loc_180007D1B
0x180007d12  movzx   ebx, ax
0x180007d15  or      ebx, 80070000h
0x180007d1b  mov     rcx, [rbp+38h]; this
0x180007d1f  mov     r9d, ebx; char *
0x180007d22  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180007d29  mov     edx, 0CD0h; void *
0x180007d2e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180007d33  jmp     loc_180007C0B
0x180007d38  mov     dword ptr [rbp+arg_18], 1
0x180007d3f  mov     r8, r14; unsigned __int16 *
0x180007d42  mov     rdx, r15; unsigned __int64
0x180007d45  mov     rcx, rax; unsigned __int16 *
0x180007d48  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007d4d  mov     ebx, eax
0x180007d4f  mov     rcx, [rbp+38h]; this
0x180007d53  test    eax, eax
0x180007d55  jns     loc_180007AEE
0x180007d5b  mov     r9d, eax; char *
0x180007d5e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180007d65  mov     edx, 0CD7h; void *
0x180007d6a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007d6f  mov     rcx, rsi; hMem
0x180007d72  call    cs:__imp_LocalFree
0x180007d78  jmp     loc_180007C06
0x180007d7d  call    cs:__imp_GetLastError
0x180007d83  mov     ebx, eax
0x180007d85  test    eax, eax
0x180007d87  jle     short loc_180007D92
0x180007d89  movzx   ebx, ax
0x180007d8c  or      ebx, 80070000h
0x180007d92  mov     edx, 0CFBh
0x180007d97  jmp     loc_180007CEE
0x180007d9c  xor     ecx, ecx
0x180007d9e  mov     rax, [rbp+ppszEnd]
0x180007da2  mov     [rax], cx
0x180007da5  mov     rcx, rsi; pObjectName
0x180007da8  call    ?_TakeOwnerAndAddAccess@@YAJPEBG@Z; _TakeOwnerAndAddAccess(ushort const *)
0x180007dad  mov     ebx, eax
0x180007daf  mov     rcx, [rbp+38h]
0x180007db3  test    eax, eax
0x180007db5  js      loc_180007EC2
0x180007dbb  lea     r8, asc_18001EAF8; "*.*"
0x180007dc2  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x180007dc6  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x180007dca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007dcf  mov     ebx, eax
0x180007dd1  mov     rcx, [rbp+38h]; this
0x180007dd5  test    eax, eax
0x180007dd7  js      loc_180007E78
0x180007ddd  mov     rdx, rdi; lpFindFileData
0x180007de0  mov     rcx, rsi; lpFileName
0x180007de3  call    cs:__imp_FindFirstFileW
0x180007de9  mov     r14, rax
0x180007dec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007df0  jnz     loc_180007B61
0x180007df6  call    cs:__imp_GetLastError
0x180007dfc  mov     ebx, eax
0x180007dfe  test    eax, eax
0x180007e00  jle     loc_180007CE9
0x180007e06  movzx   ebx, ax
0x180007e09  or      ebx, 80070000h
0x180007e0f  jmp     loc_180007CE9
0x180007e14  call    cs:__imp_GetLastError
0x180007e1a  mov     ebx, eax
0x180007e1c  test    eax, eax
0x180007e1e  jle     short loc_180007E29
0x180007e20  movzx   ebx, ax
0x180007e23  or      ebx, 80070000h
0x180007e29  mov     edx, 0D36h
0x180007e2e  jmp     loc_180007CEE
0x180007e33  mov     r9d, ebx; char *
0x180007e36  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180007e3d  mov     edx, 0CC3h; void *
0x180007e42  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007e47  jmp     loc_180007C0B
0x180007e4c  add     r15, 208h
0x180007e53  lea     rcx, [r15+r15]; dwBytes
0x180007e57  call    ?ProfAlloc@@YAPEAX_K@Z; ProfAlloc(unsigned __int64)
0x180007e5c  mov     rsi, rax
0x180007e5f  mov     [rbp+var_10], rax
0x180007e63  test    rax, rax
0x180007e66  jnz     loc_180007D38
0x180007e6c  jmp     loc_180007D06
0x180007e71  mov     edx, 0CE8h
0x180007e76  jmp     short loc_180007E7D
0x180007e78  mov     edx, 0D23h; void *
0x180007e7d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180007e84  mov     r9d, eax; char *
0x180007e87  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007e8c  jmp     loc_180007BFC
0x180007e91  mov     edx, 0CEEh
0x180007e96  jmp     short loc_180007E7D
0x180007e98  call    cs:__imp_GetLastError
0x180007e9e  lea     ecx, [rax-2]
0x180007ea1  cmp     ecx, 1
0x180007ea4  jbe     loc_180007BFA
0x180007eaa  cmp     eax, 5
0x180007ead  jnz     loc_180007E14
0x180007eb3  test    r13b, 2
0x180007eb7  jz      loc_180007E14
0x180007ebd  jmp     loc_180007D9C
0x180007ec2  mov     edx, 0D19h
0x180007ec7  jmp     short loc_180007E7D
0x180007ec9  mov     edx, [rdi+24h]
0x180007ecc  mov     ecx, [rdi]
0x180007ece  call    cs:__imp_CfGetPlaceholderStateFromAttributeTag
0x180007ed4  test    al, 2
0x180007ed6  jz      short loc_180007EEA
0x180007ed8  mov     bl, 1
0x180007eda  mov     cs:byte_180028688, bl
0x180007ee0  call    ?EnterAndDeleteCloudFilesFolder@UserenvTelemetry@@SAXXZ; UserenvTelemetry::EnterAndDeleteCloudFilesFolder(void)
0x180007ee5  jmp     loc_180007CB6
0x180007eea  lea     rcx, [rbp+var_10]
0x180007eee  call    ??$EnterAndDeleteNotCloudFilesReparsePointsFolder@AEAPEAG@UserenvTelemetry@@SAXAEAPEAG@Z; UserenvTelemetry::EnterAndDeleteNotCloudFilesReparsePointsFolder<ushort * &>(ushort * &)
0x180007ef3  jmp     loc_180007CB6
0x180007ef8  mov     rcx, r13; hObject
0x180007efb  call    cs:__imp_CloseHandle
0x180007f01  jmp     loc_180007C60
```
