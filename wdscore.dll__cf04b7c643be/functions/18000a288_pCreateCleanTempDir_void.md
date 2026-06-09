# pCreateCleanTempDir(void)

- ea: `0x18000a288`
- end: `0x18000a61b`
- name: `?pCreateCleanTempDir@@YAHXZ`
- size: `915`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18000c1a0`
- `0x18000d1c0`

## callees

- `0x180002250`
- `0x180008d30`
- `0x180008e78`
- `0x180009e30`
- `0x18000a288`
- `0x18000a624`
- `0x18001dc70`
- `0x180021c30`
- `0x1800225e4`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000a4ad`
- `msvcrt!wcsrchr` at `0x18000a4ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a3ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a3ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a58b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a58b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18000a3b6`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18000a3b6`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000a36d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000a36d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a4ec`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a4ec`

## string_xrefs

- `0x18000a31e`: `pCreateCleanTempDir`
- `0x18000a47b`: `pCreateCleanTempDir`
- `0x18000a54b`: `pCreateCleanTempDir`
- `0x18000a5cd`: `pCreateCleanTempDir`
- `0x18000a2fa`: `No working dir has been given to panther.  The temp dir for modules will be unavailable.  Call WdsInitialize(ReInit=TRUE) to specify a working directory`
- `0x18000a457`: `GetModuleFileName failed in engine::pCleanOutTempDir`
- `0x18000a527`: `Directory %s is not useable by panther`
- `0x18000a5a9`: `StringCchCopy fails for %s`

## pseudocode

```c
__int64 pCreateCleanTempDir(void)
{
  unsigned int v0; // esi
  DWORD v1; // ebx
  int v2; // eax
  int v3; // edi
  SIZE_T v4; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbx
  DWORD v8; // ebx
  int v9; // eax
  wchar_t *v10; // rax
  DWORD v11; // ebx
  int v12; // eax
  DWORD LastError; // ebx
  int v14; // eax
  CHAR v16[272]; // [rsp+70h] [rbp-578h] BYREF
  WCHAR PathName[264]; // [rsp+180h] [rbp-468h] BYREF
  WCHAR Filename[264]; // [rsp+390h] [rbp-258h] BYREF
  LPCWSTR lpModuleName; // [rsp+5E8h] [rbp+0h]

  v0 = 0;
  memset_0(PathName, 0, 0x208u);
  memset_0(Filename, 0, 0x208u);
  if ( g_WorkingDir )
  {
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
      goto LABEL_13;
    v3 = 1;
    if ( GetLastError() == 120 )
    {
      memset_0(v16, 0, 0x104u);
      if ( GetModuleFileNameA(0, v16, 0x104u) )
      {
        v4 = (int)(2 * SizeOfStringA(v16));
        ProcessHeap = GetProcessHeap();
        v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v4);
        v7 = v6;
        if ( v6 )
          StringCbPrintfW(v6, v4, L"%S", v16);
        if ( v7 )
        {
          StringCchCopyW(Filename, 0x104u, v7);
          v3 = 0;
          pDestructContentsFile((struct CONTENTS_FILE *)v7);
        }
      }
    }
    if ( !v3 )
    {
LABEL_13:
      v10 = wcsrchr(Filename, 0x5Cu);
      if ( v10 && (unsigned int)ConstructPathName(&g_WorkingDir, v10 + 1, PathName) )
      {
        CreateDirectoryW(PathName, 0);
        if ( IsDirectoryUseable(PathName) )
        {
          if ( StringCchCopyW(&g_TempDir, 0x104u, PathName) >= 0 )
          {
            return 1;
          }
          else
          {
            LastError = GetLastError();
            v14 = (unsigned int)ConstructPartialMsgW(0x3000013u, "StringCchCopy fails for %s", (const char *)PathName);
            WdsSetupLogMessageW(
              v14,
              589824,
              (int)L"D",
              0,
              788,
              L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
              (__int64)L"pCreateCleanTempDir",
              lpModuleName,
              LastError,
              0,
              0);
          }
        }
        else
        {
          v11 = GetLastError();
          v12 = (unsigned int)ConstructPartialMsgW(
                                0x3000012u,
                                "Directory %s is not useable by panther",
                                (const char *)PathName);
          WdsSetupLogMessageW(
            v12,
            589824,
            (int)L"D",
            0,
            782,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            (__int64)L"pCreateCleanTempDir",
            lpModuleName,
            v11,
            0,
            0);
        }
      }
    }
    else
    {
      v8 = GetLastError();
      v9 = (unsigned int)ConstructPartialMsgW(0x3000011u, "GetModuleFileName failed in engine::pCleanOutTempDir");
      WdsSetupLogMessageW(
        v9,
        589824,
        (int)L"D",
        0,
        752,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        (__int64)L"pCreateCleanTempDir",
        lpModuleName,
        v8,
        0,
        0);
    }
  }
  else
  {
    v1 = GetLastError();
    v2 = (unsigned int)ConstructPartialMsgW(
                         0x3000010u,
                         "No working dir has been given to panther.  The temp dir for modules will be unavailable.  Call "
                         "WdsInitialize(ReInit=TRUE) to specify a working directory");
    WdsSetupLogMessageW(
      v2,
      589824,
      (int)L"D",
      0,
      728,
      L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
      (__int64)L"pCreateCleanTempDir",
      lpModuleName,
      v1,
      0,
      0);
  }
  return v0;
}

```

## disassembly

```asm
0x18000a288  push    rbx
0x18000a28a  push    rsi
0x18000a28b  push    rdi
0x18000a28c  push    r12
0x18000a28e  push    r14
0x18000a290  push    r15
0x18000a292  sub     rsp, 5B8h
0x18000a299  mov     rax, cs:__security_cookie
0x18000a2a0  xor     rax, rsp
0x18000a2a3  mov     [rsp+5E8h+var_48], rax
0x18000a2ab  xor     r15d, r15d
0x18000a2ae  mov     esi, r15d
0x18000a2b1  mov     ebx, 208h
0x18000a2b6  mov     r8d, ebx; Size
0x18000a2b9  xor     edx, edx; Val
0x18000a2bb  lea     rcx, [rsp+5E8h+PathName]; void *
0x18000a2c3  call    memset_0
0x18000a2c8  mov     r8d, ebx; Size
0x18000a2cb  xor     edx, edx; Val
0x18000a2cd  lea     rcx, [rsp+5E8h+Filename]; void *
0x18000a2d5  call    memset_0
0x18000a2da  cmp     cs:?g_WorkingDir@@3PAGA, r15w; ushort near * g_WorkingDir
0x18000a2e2  jnz     short loc_18000A35A
0x18000a2e4  call    cs:__imp_GetLastError
0x18000a2eb  nop     dword ptr [rax+rax+00h]
0x18000a2f0  mov     ebx, eax
0x18000a2f2  mov     rdi, [rsp+5E8h]
0x18000a2fa  lea     rdx, aNoWorkingDirHa; "No working dir has been given to panthe"...
0x18000a301  mov     ecx, 3000010h; unsigned int
0x18000a306  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000a30b  mov     [rsp+5E8h+var_598], r15d; int
0x18000a310  mov     [rsp+5E8h+var_5A0], r15; __int64
0x18000a315  mov     [rsp+5E8h+var_5A8], ebx; int
0x18000a319  mov     [rsp+5E8h+lpModuleName], rdi; lpModuleName
0x18000a31e  lea     rcx, aPcreatecleante; "pCreateCleanTempDir"
0x18000a325  mov     [rsp+5E8h+var_5B8], rcx; __int64
0x18000a32a  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000a331  mov     [rsp+5E8h+var_5C0], rcx; unsigned __int16 *
0x18000a336  mov     [rsp+5E8h+var_5C8], 2D8h; int
0x18000a33e  xor     r9d, r9d; int
0x18000a341  lea     r8, aD_1; "D"
0x18000a348  mov     edx, 90000h; int
0x18000a34d  mov     rcx, rax; int
0x18000a350  call    WdsSetupLogMessageW
0x18000a355  jmp     loc_18000A5F7
0x18000a35a  mov     r12d, 104h
0x18000a360  mov     r8d, r12d; nSize
0x18000a363  lea     rdx, [rsp+5E8h+Filename]; lpFilename
0x18000a36b  xor     ecx, ecx; hModule
0x18000a36d  call    cs:__imp_GetModuleFileNameW
0x18000a374  nop     dword ptr [rax+rax+00h]
0x18000a379  test    eax, eax
0x18000a37b  jnz     loc_18000A4A0
0x18000a381  lea     edi, [rax+1]
0x18000a384  mov     [rsp+5E8h+var_588], edi
0x18000a388  call    cs:__imp_GetLastError
0x18000a38f  nop     dword ptr [rax+rax+00h]
0x18000a394  cmp     eax, 78h ; 'x'
0x18000a397  jnz     loc_18000A43D
0x18000a39d  mov     r8d, r12d; Size
0x18000a3a0  xor     edx, edx; Val
0x18000a3a2  lea     rcx, [rsp+5E8h+var_578]; void *
0x18000a3a7  call    memset_0
0x18000a3ac  mov     r8d, r12d; nSize
0x18000a3af  lea     rdx, [rsp+5E8h+var_578]; lpFilename
0x18000a3b4  xor     ecx, ecx; hModule
0x18000a3b6  call    cs:__imp_GetModuleFileNameA
0x18000a3bd  nop     dword ptr [rax+rax+00h]
0x18000a3c2  test    eax, eax
0x18000a3c4  jz      short loc_18000A43D
0x18000a3c6  lea     rcx, [rsp+5E8h+var_578]
0x18000a3cb  call    SizeOfStringA
0x18000a3d0  add     eax, eax
0x18000a3d2  movsxd  r14, eax
0x18000a3d5  call    cs:__imp_GetProcessHeap
0x18000a3dc  nop     dword ptr [rax+rax+00h]
0x18000a3e1  mov     rcx, rax; hHeap
0x18000a3e4  mov     r8, r14; dwBytes
0x18000a3e7  lea     edx, [rdi+7]; dwFlags
0x18000a3ea  call    cs:__imp_HeapAlloc
0x18000a3f1  nop     dword ptr [rax+rax+00h]
0x18000a3f6  mov     rbx, rax
0x18000a3f9  test    rax, rax
0x18000a3fc  jz      short loc_18000A415
0x18000a3fe  lea     r9, [rsp+5E8h+var_578]
0x18000a403  lea     r8, aS_5; "%S"
0x18000a40a  mov     rdx, r14; unsigned __int64
0x18000a40d  mov     rcx, rax; unsigned __int16 *
0x18000a410  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a415  test    rbx, rbx
0x18000a418  jz      short loc_18000A43D
0x18000a41a  mov     r8, rbx; unsigned __int16 *
0x18000a41d  mov     rdx, r12; unsigned __int64
0x18000a420  lea     rcx, [rsp+5E8h+Filename]; unsigned __int16 *
0x18000a428  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a42d  mov     edi, r15d
0x18000a430  mov     [rsp+5E8h+var_588], r15d
0x18000a435  mov     rcx, rbx; struct CONTENTS_FILE *
0x18000a438  call    ?pDestructContentsFile@@YAXPEAUCONTENTS_FILE@@@Z; pDestructContentsFile(CONTENTS_FILE *)
0x18000a43d  test    edi, edi
0x18000a43f  jz      short loc_18000A4A0
0x18000a441  call    cs:__imp_GetLastError
0x18000a448  nop     dword ptr [rax+rax+00h]
0x18000a44d  mov     ebx, eax
0x18000a44f  mov     rdi, [rsp+5E8h]
0x18000a457  lea     rdx, aGetmodulefilen; "GetModuleFileName failed in engine::pCl"...
0x18000a45e  mov     ecx, 3000011h; unsigned int
0x18000a463  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000a468  mov     [rsp+5E8h+var_598], r15d
0x18000a46d  mov     [rsp+5E8h+var_5A0], r15
0x18000a472  mov     [rsp+5E8h+var_5A8], ebx
0x18000a476  mov     [rsp+5E8h+lpModuleName], rdi
0x18000a47b  lea     rcx, aPcreatecleante; "pCreateCleanTempDir"
0x18000a482  mov     [rsp+5E8h+var_5B8], rcx
0x18000a487  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000a48e  mov     [rsp+5E8h+var_5C0], rcx
0x18000a493  mov     [rsp+5E8h+var_5C8], 2F0h
0x18000a49b  jmp     loc_18000A33E
0x18000a4a0  mov     edx, 5Ch ; '\'; Ch
0x18000a4a5  lea     rcx, [rsp+5E8h+Filename]; Str
0x18000a4ad  call    cs:__imp_wcsrchr
0x18000a4b4  nop     dword ptr [rax+rax+00h]
0x18000a4b9  test    rax, rax
0x18000a4bc  jz      loc_18000A5F7
0x18000a4c2  lea     rdx, [rax+2]; STRSAFE_LPCWSTR
0x18000a4c6  lea     r8, [rsp+5E8h+PathName]; unsigned __int16 *
0x18000a4ce  lea     rcx, ?g_WorkingDir@@3PAGA; pszSrc
0x18000a4d5  call    ConstructPathName
0x18000a4da  test    eax, eax
0x18000a4dc  jz      loc_18000A5F7
0x18000a4e2  xor     edx, edx; lpSecurityAttributes
0x18000a4e4  lea     rcx, [rsp+5E8h+PathName]; lpPathName
0x18000a4ec  call    cs:__imp_CreateDirectoryW
0x18000a4f3  nop     dword ptr [rax+rax+00h]
0x18000a4f8  lea     rcx, [rsp+5E8h+PathName]
0x18000a500  call    IsDirectoryUseable
0x18000a505  test    eax, eax
0x18000a507  jnz     short loc_18000A570
0x18000a509  call    cs:__imp_GetLastError
0x18000a510  nop     dword ptr [rax+rax+00h]
0x18000a515  mov     ebx, eax
0x18000a517  mov     rdi, [rsp+5E8h]
0x18000a51f  lea     r8, [rsp+5E8h+PathName]
0x18000a527  lea     rdx, aDirectorySIsNo; "Directory %s is not useable by panther"
0x18000a52e  mov     ecx, 3000012h; unsigned int
0x18000a533  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000a538  mov     [rsp+5E8h+var_598], r15d
0x18000a53d  mov     [rsp+5E8h+var_5A0], r15
0x18000a542  mov     [rsp+5E8h+var_5A8], ebx
0x18000a546  mov     [rsp+5E8h+lpModuleName], rdi
0x18000a54b  lea     rcx, aPcreatecleante; "pCreateCleanTempDir"
0x18000a552  mov     [rsp+5E8h+var_5B8], rcx
0x18000a557  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000a55e  mov     [rsp+5E8h+var_5C0], rcx
0x18000a563  mov     [rsp+5E8h+var_5C8], 30Eh
0x18000a56b  jmp     loc_18000A33E
0x18000a570  lea     r8, [rsp+5E8h+PathName]; unsigned __int16 *
0x18000a578  mov     rdx, r12; unsigned __int64
0x18000a57b  lea     rcx, ?g_TempDir@@3PAGA; unsigned __int16 *
0x18000a582  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a587  test    eax, eax
0x18000a589  jns     short loc_18000A5F2
0x18000a58b  call    cs:__imp_GetLastError
0x18000a592  nop     dword ptr [rax+rax+00h]
0x18000a597  mov     ebx, eax
0x18000a599  mov     rdi, [rsp+5E8h]
0x18000a5a1  lea     r8, [rsp+5E8h+PathName]
0x18000a5a9  lea     rdx, aStringcchcopyF; "StringCchCopy fails for %s"
0x18000a5b0  mov     ecx, 3000013h; unsigned int
0x18000a5b5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000a5ba  mov     [rsp+5E8h+var_598], r15d
0x18000a5bf  mov     [rsp+5E8h+var_5A0], r15
0x18000a5c4  mov     [rsp+5E8h+var_5A8], ebx
0x18000a5c8  mov     [rsp+5E8h+lpModuleName], rdi
0x18000a5cd  lea     rcx, aPcreatecleante; "pCreateCleanTempDir"
0x18000a5d4  mov     [rsp+5E8h+var_5B8], rcx
0x18000a5d9  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000a5e0  mov     [rsp+5E8h+var_5C0], rcx
0x18000a5e5  mov     [rsp+5E8h+var_5C8], 314h
0x18000a5ed  jmp     loc_18000A33E
0x18000a5f2  mov     esi, 1
0x18000a5f7  mov     eax, esi
0x18000a5f9  mov     rcx, [rsp+5E8h+var_48]
0x18000a601  xor     rcx, rsp; StackCookie
0x18000a604  call    __security_check_cookie
0x18000a609  add     rsp, 5B8h
0x18000a610  pop     r15
0x18000a612  pop     r14
0x18000a614  pop     r12
0x18000a616  pop     rdi
0x18000a617  pop     rsi
0x18000a618  pop     rbx
0x18000a619  retn
0x180027ab6  push    rbp
0x180027ab8  sub     rsp, 60h
0x180027abc  mov     rbp, rdx
0x180027abf  add     rsp, 60h
0x180027ac3  pop     rbp
0x180027ac4  retn
```
