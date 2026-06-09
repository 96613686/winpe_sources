# CreateMappedTempFile(long,ushort * *,void * *,uchar * *)

- ea: `0x180058354`
- end: `0x1800586d2`
- name: `?CreateMappedTempFile@@YAJJPEAPEAGPEAPEAXPEAPEAE@Z`
- size: `894`
- prototype: `__int64 __fastcall(int, unsigned __int16 **, void **, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18006e160`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002de18`
- `0x18002def8`
- `0x180058354`
- `0x180059190`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005861f`
- `KERNEL32!CloseHandle` at `0x1800586b2`
- `KERNEL32!CloseHandle` at `0x18005861f`
- `KERNEL32!CloseHandle` at `0x1800586b2`
- `ole32!CoTaskMemFree` at `0x1800586a3`
- `ole32!CoTaskMemFree` at `0x1800586a3`
- `ole32!CoTaskMemAlloc` at `0x1800583a2`
- `ole32!CoTaskMemAlloc` at `0x1800583a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800584ad`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800584ad`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800583e8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800583e8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180058592`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180058592`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800585bb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800585bb`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800583bc`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800583bc`
- `SHELL32!__imp_SHCreateDirectory` at `0x1800583d2`
- `SHELL32!__imp_SHCreateDirectory` at `0x1800583d2`

## string_xrefs

- `0x180058435`: `GetTempPathW failed, hr = %x`
- `0x18005845d`: `GetTempPathW failed, hr = %x`
- `0x180058514`: `Failed to allocate temporary file name`
- `0x18005853a`: `Failed to allocate temporary file name`
- `0x1800583fd`: `GetTempFileNameW failed, hr = %x`
- `0x180058425`: `GetTempFileNameW failed, hr = %x`
- `0x18005840e`: `CreateMappedTempFile`
- `0x180058446`: `CreateMappedTempFile`
- `0x180058476`: `CreateMappedTempFile`
- `0x1800584d8`: `CreateMappedTempFile`
- `0x180058506`: `CreateMappedTempFile`
- `0x180058523`: `CreateMappedTempFile`
- `0x180058551`: `CreateMappedTempFile`
- `0x1800585e1`: `CreateMappedTempFile`
- `0x180058610`: `CreateMappedTempFile`
- `0x18005863f`: `CreateMappedTempFile`
- `0x18005866f`: `CreateMappedTempFile`
- `0x18005862e`: `CreateFileMapping failed, hr = 0x%X`
- `0x180058658`: `CreateFileMapping failed, hr = 0x%X`
- `0x1800584c7`: `CreateFile failed, hr = 0x%X`
- `0x1800584f1`: `CreateFile failed, hr = 0x%X`

## pseudocode

```c
__int64 __fastcall CreateMappedTempFile(int a1, unsigned __int16 **a2, void **a3, unsigned __int8 **a4)
{
  __int64 FileW; // rbp
  SIZE_T v5; // r15
  unsigned __int8 *v6; // r12
  void **v8; // r14
  WCHAR *v9; // rax
  WCHAR *v10; // rsi
  int LastErrorHRESULT; // edi
  char *v12; // rbx
  void *v13; // rdx
  void *v14; // rax
  int v15; // edx
  int v16; // ecx
  char *v17; // rbx
  void *v18; // rdx
  char *v19; // rbx
  void *v20; // rdx
  void *v21; // rax
  int v22; // edx
  int v23; // ecx
  char *v24; // rbx
  void *v25; // rdx
  void *v26; // rax
  int v27; // edx
  int v28; // ecx
  HANDLE FileMappingW; // rax
  void *v30; // r14
  char *v31; // rbx
  void *v32; // rdx
  void *v33; // rax
  int v34; // edx
  int v35; // ecx
  char *v36; // rbx
  void *v37; // rdx
  void *v38; // rax
  int v39; // edx
  int v40; // ecx

  FileW = -1;
  v5 = a1;
  v6 = 0;
  v8 = a3;
  if ( !a2 || !a3 || !a4 )
  {
    v10 = 0;
    LastErrorHRESULT = -2147024809;
    goto LABEL_14;
  }
  v9 = (WCHAR *)CoTaskMemAlloc(0x208u);
  v10 = v9;
  if ( !v9 )
  {
    v24 = (char *)WiaTrace_TraceLog("Failed to allocate temporary file name");
    WriteDbgTraceErrorWI("CreateMappedTempFile", v24);
    WiaTrcLib::Free((WiaTrcLib *)v24, v25);
    v26 = (void *)WiaTrace_Trace("Failed to allocate temporary file name");
    WiaTrace_ProcessTrace_Ex(v28, v27, (int)"CreateMappedTempFile", 1, v26);
    LastErrorHRESULT = -2147024882;
    goto LABEL_14;
  }
  if ( (unsigned int)GetTempPath2W(260, v9) - 1 > 0x102 )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v17 = (char *)WiaTrace_TraceLog("GetTempPathW failed, hr = %x");
    WriteDbgTraceErrorWI("CreateMappedTempFile", v17);
    WiaTrcLib::Free((WiaTrcLib *)v17, v18);
    v14 = (void *)WiaTrace_Trace("GetTempPathW failed, hr = %x", (unsigned int)LastErrorHRESULT);
LABEL_9:
    WiaTrace_ProcessTrace_Ex(v16, v15, (int)"CreateMappedTempFile", 1, v14);
    if ( LastErrorHRESULT < 0 )
      goto LABEL_14;
    goto LABEL_10;
  }
  LastErrorHRESULT = 0;
  SHCreateDirectory(0, v10);
  if ( !GetTempFileNameW(v10, L"WIA", 0, v10) )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v12 = (char *)WiaTrace_TraceLog("GetTempFileNameW failed, hr = %x");
    WriteDbgTraceErrorWI("CreateMappedTempFile", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void *)WiaTrace_Trace("GetTempFileNameW failed, hr = %x", (unsigned int)LastErrorHRESULT);
    goto LABEL_9;
  }
LABEL_10:
  FileW = (__int64)CreateFileW(v10, 0xC0000000, 2u, 0, 2u, 0x100u, 0);
  if ( FileW == -1 )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v19 = (char *)WiaTrace_TraceLog("CreateFile failed, hr = 0x%X");
    WriteDbgTraceErrorWI("CreateMappedTempFile", v19);
    WiaTrcLib::Free((WiaTrcLib *)v19, v20);
    v21 = (void *)WiaTrace_Trace("CreateFile failed, hr = 0x%X", LastErrorHRESULT);
    WiaTrace_ProcessTrace_Ex(v23, v22, (int)"CreateMappedTempFile", 1, v21);
  }
LABEL_14:
  if ( (_DWORD)v5 )
  {
    if ( LastErrorHRESULT < 0 )
      goto LABEL_24;
    FileMappingW = CreateFileMappingW((HANDLE)FileW, 0, 4u, 0, v5, 0);
    v30 = FileMappingW;
    if ( FileMappingW )
    {
      v6 = (unsigned __int8 *)MapViewOfFileEx(FileMappingW, 6u, 0, 0, v5, 0);
      if ( !v6 )
      {
        LastErrorHRESULT = GetLastErrorHRESULT();
        v31 = (char *)WiaTrace_TraceLog("MapViewOfFileEx failed, hr = 0x%X");
        WriteDbgTraceErrorWI("CreateMappedTempFile", v31);
        WiaTrcLib::Free((WiaTrcLib *)v31, v32);
        v33 = (void *)WiaTrace_Trace("MapViewOfFileEx failed, hr = 0x%X", LastErrorHRESULT);
        WiaTrace_ProcessTrace_Ex(v35, v34, (int)"CreateMappedTempFile", 1, v33);
      }
      CloseHandle(v30);
    }
    else
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      v36 = (char *)WiaTrace_TraceLog("CreateFileMapping failed, hr = 0x%X");
      WriteDbgTraceErrorWI("CreateMappedTempFile", v36);
      WiaTrcLib::Free((WiaTrcLib *)v36, v37);
      v38 = (void *)WiaTrace_Trace("CreateFileMapping failed, hr = 0x%X", LastErrorHRESULT);
      WiaTrace_ProcessTrace_Ex(v40, v39, (int)"CreateMappedTempFile", 1, v38);
    }
    v8 = a3;
  }
  if ( LastErrorHRESULT >= 0 )
  {
    *v8 = (void *)FileW;
    *a4 = v6;
    *a2 = v10;
    return (unsigned int)LastErrorHRESULT;
  }
LABEL_24:
  if ( v10 )
    CoTaskMemFree(v10);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)LastErrorHRESULT;
}

```

## disassembly

```asm
0x180058354  mov     [rsp+arg_0], rbx
0x180058359  mov     [rsp+arg_10], r8
0x18005835e  mov     [rsp+arg_8], rdx
0x180058363  push    rbp
0x180058364  push    rsi
0x180058365  push    rdi
0x180058366  push    r12
0x180058368  push    r13
0x18005836a  push    r14
0x18005836c  push    r15
0x18005836e  sub     rsp, 40h
0x180058372  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180058376  movsxd  r15, ecx
0x180058379  xor     r12d, r12d
0x18005837c  mov     r13, r9
0x18005837f  mov     r14, r8
0x180058382  test    rdx, rdx
0x180058385  jz      loc_180058564
0x18005838b  test    r8, r8
0x18005838e  jz      loc_180058564
0x180058394  test    r9, r9
0x180058397  jz      loc_180058564
0x18005839d  mov     ecx, 208h; cb
0x1800583a2  call    cs:__imp_CoTaskMemAlloc
0x1800583a8  mov     rsi, rax
0x1800583ab  test    rax, rax
0x1800583ae  jz      loc_180058514
0x1800583b4  mov     rdx, rax
0x1800583b7  mov     ecx, 104h
0x1800583bc  call    cs:__imp_GetTempPath2W
0x1800583c2  dec     eax
0x1800583c4  cmp     eax, 102h
0x1800583c9  ja      short loc_18005842E
0x1800583cb  mov     rdx, rsi; pszPath
0x1800583ce  xor     ecx, ecx; hwnd
0x1800583d0  xor     edi, edi
0x1800583d2  call    cs:__imp_SHCreateDirectory
0x1800583d8  mov     r9, rsi; lpTempFileName
0x1800583db  lea     rdx, PrefixString; "WIA"
0x1800583e2  xor     r8d, r8d; uUnique
0x1800583e5  mov     rcx, rsi; lpPathName
0x1800583e8  call    cs:__imp_GetTempFileNameW
0x1800583ee  test    eax, eax
0x1800583f0  jnz     loc_18005848A
0x1800583f6  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800583fb  mov     edx, eax
0x1800583fd  lea     rcx, aGettempfilenam; "GetTempFileNameW failed, hr = %x"
0x180058404  mov     edi, eax
0x180058406  call    WiaTrace_TraceLog
0x18005840b  mov     rdx, rax; char *
0x18005840e  lea     rcx, aCreatemappedte; "CreateMappedTempFile"
0x180058415  mov     rbx, rax
0x180058418  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005841d  mov     rcx, rbx; this
0x180058420  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058425  lea     rcx, aGettempfilenam; "GetTempFileNameW failed, hr = %x"
0x18005842c  jmp     short loc_180058464
0x18005842e  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180058433  mov     edx, eax
0x180058435  lea     rcx, aGettemppathwFa; "GetTempPathW failed, hr = %x"
0x18005843c  mov     edi, eax
0x18005843e  call    WiaTrace_TraceLog
0x180058443  mov     rdx, rax; char *
0x180058446  lea     rcx, aCreatemappedte; "CreateMappedTempFile"
0x18005844d  mov     rbx, rax
0x180058450  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180058455  mov     rcx, rbx; this
0x180058458  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005845d  lea     rcx, aGettemppathwFa; "GetTempPathW failed, hr = %x"
0x180058464  mov     edx, edi
0x180058466  call    WiaTrace_Trace
0x18005846b  mov     r9d, 1; int
0x180058471  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpMem
0x180058476  lea     r8, aCreatemappedte; "CreateMappedTempFile"
0x18005847d  call    WiaTrace_ProcessTrace_Ex
0x180058482  test    edi, edi
0x180058484  js      loc_18005856B
0x18005848a  mov     [rsp+78h+hTemplateFile], r12; hTemplateFile
0x18005848f  mov     r8d, 2; dwShareMode
0x180058495  mov     [rsp+78h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x18005849d  xor     r9d, r9d; lpSecurityAttributes
0x1800584a0  mov     edx, 0C0000000h; dwDesiredAccess
0x1800584a5  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800584aa  mov     rcx, rsi; lpFileName
0x1800584ad  call    cs:__imp_CreateFileW
0x1800584b3  mov     rbp, rax
0x1800584b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800584ba  jnz     loc_18005856B
0x1800584c0  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800584c5  mov     edx, eax
0x1800584c7  lea     rcx, aCreatefileFail; "CreateFile failed, hr = 0x%X"
0x1800584ce  mov     edi, eax
0x1800584d0  call    WiaTrace_TraceLog
0x1800584d5  mov     rdx, rax; char *
0x1800584d8  lea     rcx, aCreatemappedte; "CreateMappedTempFile"
0x1800584df  mov     rbx, rax
0x1800584e2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800584e7  mov     rcx, rbx; this
0x1800584ea  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800584ef  mov     edx, edi
0x1800584f1  lea     rcx, aCreatefileFail; "CreateFile failed, hr = 0x%X"
0x1800584f8  call    WiaTrace_Trace
0x1800584fd  lea     r9d, [rbp+2]; int
0x180058501  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpMem
0x180058506  lea     r8, aCreatemappedte; "CreateMappedTempFile"
0x18005850d  call    WiaTrace_ProcessTrace_Ex
0x180058512  jmp     short loc_18005856B
0x180058514  lea     rcx, aFailedToAlloca; "Failed to allocate temporary file name"
0x18005851b  call    WiaTrace_TraceLog
0x180058520  mov     rdx, rax; char *
0x180058523  lea     rcx, aCreatemappedte; "CreateMappedTempFile"
0x18005852a  mov     rbx, rax
0x18005852d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180058532  mov     rcx, rbx; this
0x180058535  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005853a  lea     rcx, aFailedToAlloca; "Failed to allocate temporary file name"
0x180058541  call    WiaTrace_Trace
0x180058546  mov     r9d, 1; int
0x18005854c  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpMem
0x180058551  lea     r8, aCreatemappedte; "CreateMappedTempFile"
0x180058558  call    WiaTrace_ProcessTrace_Ex
0x18005855d  mov     edi, 8007000Eh
0x180058562  jmp     short loc_18005856B
0x180058564  xor     esi, esi
0x180058566  mov     edi, 80070057h
0x18005856b  test    r15d, r15d
0x18005856e  jz      loc_180058683
0x180058574  test    edi, edi
0x180058576  js      loc_18005869B
0x18005857c  xor     r9d, r9d; dwMaximumSizeHigh
0x18005857f  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r12; lpName
0x180058584  xor     edx, edx; lpFileMappingAttributes
0x180058586  mov     [rsp+78h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x18005858b  mov     rcx, rbp; hFile
0x18005858e  lea     r8d, [r9+4]; flProtect
0x180058592  call    cs:__imp_CreateFileMappingW
0x180058598  mov     r14, rax
0x18005859b  test    rax, rax
0x18005859e  jz      loc_180058627
0x1800585a4  xor     r9d, r9d; dwFileOffsetLow
0x1800585a7  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r12; lpBaseAddress
0x1800585ac  xor     r8d, r8d; dwFileOffsetHigh
0x1800585af  mov     qword ptr [rsp+78h+dwCreationDisposition], r15; dwNumberOfBytesToMap
0x1800585b4  mov     rcx, rax; hFileMappingObject
0x1800585b7  lea     edx, [r9+6]; dwDesiredAccess
0x1800585bb  call    cs:__imp_MapViewOfFileEx
0x1800585c1  mov     r12, rax
0x1800585c4  test    rax, rax
0x1800585c7  jnz     short loc_18005861C
0x1800585c9  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800585ce  mov     edx, eax
0x1800585d0  lea     rcx, aMapviewoffilee; "MapViewOfFileEx failed, hr = 0x%X"
0x1800585d7  mov     edi, eax
0x1800585d9  call    WiaTrace_TraceLog
0x1800585de  mov     rdx, rax; char *
0x1800585e1  lea     rcx, aCreatemappedte; "CreateMappedTempFile"
0x1800585e8  mov     rbx, rax
0x1800585eb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800585f0  mov     rcx, rbx; this
0x1800585f3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800585f8  mov     edx, edi
0x1800585fa  lea     rcx, aMapviewoffilee; "MapViewOfFileEx failed, hr = 0x%X"
0x180058601  call    WiaTrace_Trace
0x180058606  lea     r9d, [r12+1]; int
0x18005860b  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpMem
0x180058610  lea     r8, aCreatemappedte; "CreateMappedTempFile"
0x180058617  call    WiaTrace_ProcessTrace_Ex
0x18005861c  mov     rcx, r14; hObject
0x18005861f  call    cs:__imp_CloseHandle
0x180058625  jmp     short loc_18005867B
0x180058627  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18005862c  mov     edx, eax
0x18005862e  lea     rcx, aCreatefilemapp; "CreateFileMapping failed, hr = 0x%X"
0x180058635  mov     edi, eax
0x180058637  call    WiaTrace_TraceLog
0x18005863c  mov     rdx, rax; char *
0x18005863f  lea     rcx, aCreatemappedte; "CreateMappedTempFile"
0x180058646  mov     rbx, rax
0x180058649  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005864e  mov     rcx, rbx; this
0x180058651  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058656  mov     edx, edi
0x180058658  lea     rcx, aCreatefilemapp; "CreateFileMapping failed, hr = 0x%X"
0x18005865f  call    WiaTrace_Trace
0x180058664  mov     r9d, 1; int
0x18005866a  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpMem
0x18005866f  lea     r8, aCreatemappedte; "CreateMappedTempFile"
0x180058676  call    WiaTrace_ProcessTrace_Ex
0x18005867b  mov     r14, [rsp+78h+arg_10]
0x180058683  test    edi, edi
0x180058685  js      short loc_18005869B
0x180058687  mov     rax, [rsp+78h+arg_8]
0x18005868f  mov     [r14], rbp
0x180058692  mov     [r13+0], r12
0x180058696  mov     [rax], rsi
0x180058699  jmp     short loc_1800586B8
0x18005869b  test    rsi, rsi
0x18005869e  jz      short loc_1800586A9
0x1800586a0  mov     rcx, rsi; pv
0x1800586a3  call    cs:__imp_CoTaskMemFree
0x1800586a9  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800586ad  jz      short loc_1800586B8
0x1800586af  mov     rcx, rbp; hObject
0x1800586b2  call    cs:__imp_CloseHandle
0x1800586b8  mov     rbx, [rsp+78h+arg_0]
0x1800586c0  mov     eax, edi
0x1800586c2  add     rsp, 40h
0x1800586c6  pop     r15
0x1800586c8  pop     r14
0x1800586ca  pop     r13
0x1800586cc  pop     r12
0x1800586ce  pop     rdi
0x1800586cf  pop     rsi
0x1800586d0  pop     rbp
0x1800586d1  retn
```
