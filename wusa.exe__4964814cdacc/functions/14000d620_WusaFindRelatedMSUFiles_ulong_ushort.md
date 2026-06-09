# WusaFindRelatedMSUFiles(ulong *,ushort * * *)

- ea: `0x14000d620`
- end: `0x14000db47`
- name: `?WusaFindRelatedMSUFiles@@YAJPEAKPEAPEAPEAG@Z`
- size: `1319`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400075b0`

## callees

- `0x140001a63`
- `0x1400044e0`
- `0x14000cf70`
- `0x14000d028`
- `0x14000d620`
- `0x140013490`
- `0x140014910`
- `0x1400149a0`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x14000d810`
- `KERNEL32!FindFirstFileW` at `0x14000d810`
- `KERNEL32!FindClose` at `0x14000db15`
- `KERNEL32!FindClose` at `0x14000db15`
- `KERNEL32!GetFullPathNameW` at `0x14000d7f6`
- `KERNEL32!GetFullPathNameW` at `0x14000d7f6`
- `KERNEL32!GetLastError` at `0x14000d81f`
- `KERNEL32!GetLastError` at `0x14000d994`
- `KERNEL32!GetLastError` at `0x14000dabc`
- `KERNEL32!GetLastError` at `0x14000d81f`
- `KERNEL32!GetLastError` at `0x14000d994`
- `KERNEL32!GetLastError` at `0x14000dabc`
- `KERNEL32!FindNextFileW` at `0x14000d986`
- `KERNEL32!FindNextFileW` at `0x14000d986`
- `msvcrt!_wsplitpath_s` at `0x14000d6c5`
- `msvcrt!_wsplitpath_s` at `0x14000d91f`
- `msvcrt!_wsplitpath_s` at `0x14000d6c5`
- `msvcrt!_wsplitpath_s` at `0x14000d91f`
- `msvcrt!_wcsicmp` at `0x14000d93d`
- `msvcrt!_wcsicmp` at `0x14000d957`
- `msvcrt!_wcsicmp` at `0x14000d93d`
- `msvcrt!_wcsicmp` at `0x14000d957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000da31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000da31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db02`

## string_xrefs

- `0x14000d6d8`: `Failed to get parent folder path for %ls`
- `0x14000d72d`: `Failed to append pattern to parent folder path`
- `0x14000dad1`: `Failed to get full path name for pattern %ls`
- `0x14000d9e1`: `Failed to get file name from full path %ls`

## pseudocode

```c
__int64 __fastcall WusaFindRelatedMSUFiles(unsigned int *a1, unsigned __int16 ***a2)
{
  unsigned int v4; // r13d
  int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 FirstFileW; // rbx
  int v9; // eax
  wchar_t *v10; // r15
  __int64 v11; // rdx
  signed int v12; // eax
  const char *v13; // r8
  __int64 v14; // rdx
  unsigned int v15; // r14d
  __int64 v16; // rcx
  __int64 v17; // rax
  wchar_t *v18; // rsi
  __int64 v19; // rax
  DWORD v20; // eax
  __int64 v21; // rcx
  wchar_t *v22; // rcx
  unsigned __int16 ***v23; // rsi
  unsigned int i; // edx
  unsigned __int16 *v25; // r9
  signed int LastError; // eax
  wchar_t *FullPath; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 ***v29; // [rsp+58h] [rbp-A8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v31[6]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t Drive[8]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR FileName[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v34[264]; // [rsp+500h] [rbp+400h] BYREF
  wchar_t String2[256]; // [rsp+710h] [rbp+610h] BYREF
  wchar_t String1[256]; // [rsp+910h] [rbp+810h] BYREF
  wchar_t Ext[256]; // [rsp+B10h] [rbp+A10h] BYREF
  wchar_t v38[256]; // [rsp+D10h] [rbp+C10h] BYREF
  wchar_t Dir[264]; // [rsp+F10h] [rbp+E10h] BYREF
  WCHAR Buffer[264]; // [rsp+1120h] [rbp+1020h] BYREF

  v29 = a2;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = 0;
  FullPath = 0;
  v5 = _wsplitpath_s(pszPath, Drive, 3u, Dir, 0x104u, String2, 0x100u, Ext, 0x100u);
  if ( v5 < 0 )
  {
    WusaLogDebugEventA(L"WusaFindRelatedMSUFiles", 702, "Failed to get parent folder path for %ls", pszPath);
    return (unsigned int)v5;
  }
  v5 = StringCchPrintfW(v34, 0x105u, L"%s%s", Drive, Dir);
  if ( v5 < 0 )
  {
    v6 = 705;
LABEL_5:
    WusaLogDebugEventA(L"WusaFindRelatedMSUFiles", v6, "Failed to append pattern to parent folder path");
    return (unsigned int)v5;
  }
  v5 = StringCchPrintfW(FileName, 0x105u, L"%s*.msu", v34);
  if ( v5 < 0 )
  {
    v6 = 708;
    goto LABEL_5;
  }
  if ( !a1 )
  {
    WusaLogDebugEventA(L"WusaFindRelatedMSUFiles", 710, "filesCount cannot be null");
    return (unsigned int)-2147024882;
  }
  if ( !a2 )
  {
    WusaLogDebugEventA(L"WusaFindRelatedMSUFiles", 711, "files cannot be null");
    return (unsigned int)-2147024882;
  }
  FirstFileW = -1;
  v9 = CoAllocArray<unsigned short *>(v7, 256, &FullPath);
  v10 = FullPath;
  v5 = v9;
  if ( v9 < 0 )
  {
    v11 = 714;
    goto LABEL_15;
  }
  if ( !GetFullPathNameW(FileName, 0x104u, Buffer, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v13 = "Failed to get full path name for pattern %ls";
    v14 = 719;
    goto LABEL_56;
  }
  FirstFileW = (__int64)FindFirstFileW(Buffer, &FindFileData);
  if ( FirstFileW == -1 )
  {
    v12 = GetLastError();
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    v13 = "Failed to find first file for pattern %ls";
    v14 = 725;
LABEL_56:
    if ( v5 >= 0 )
      v5 = -2147467259;
    WusaLogDebugEventA(L"WusaFindRelatedMSUFiles", v14, v13, FileName);
    goto LABEL_59;
  }
  v15 = 0;
  while ( v15 < 0x100 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      FullPath = 0;
      v16 = -1;
      do
        ++v16;
      while ( FindFileData.cFileName[v16] );
      v17 = -1;
      do
        ++v17;
      while ( v34[v17] );
      v31[3] = v17;
      v31[2] = v34;
      v31[5] = v16;
      v31[0] = 0;
      v31[1] = 0;
      v31[4] = FindFileData.cFileName;
      v5 = wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
             &FullPath,
             v31);
      if ( v5 < 0 )
      {
        WusaLogDebugEventA(
          L"WusaFindRelatedMSUFiles",
          746,
          "Failed to concatenate file name %ls",
          FindFileData.cFileName);
        v22 = FullPath;
        if ( !FullPath )
          goto LABEL_59;
        goto LABEL_43;
      }
      v18 = FullPath;
      v5 = _wsplitpath_s(FullPath, 0, 0, 0, 0, String1, 0x100u, v38, 0x100u);
      if ( v5 < 0 )
      {
        WusaLogDebugEventA(L"WusaFindRelatedMSUFiles", 751, "Failed to get file name from full path %ls", v18);
        if ( !v18 )
          goto LABEL_59;
        v22 = v18;
LABEL_43:
        CoTaskMemFree(v22);
        goto LABEL_59;
      }
      if ( _wcsicmp(String1, String2) || _wcsicmp(v38, Ext) )
      {
        v19 = v4++;
        ++v15;
        *(_QWORD *)&v10[4 * v19] = v18;
      }
      else if ( v18 )
      {
        CoTaskMemFree(v18);
      }
    }
    if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
      break;
  }
  v20 = GetLastError();
  v5 = v20;
  if ( v20 != 18 && v20 )
  {
    WusaLogDebugEventA(L"WusaFindRelatedMSUFiles", 765, "Failed: FindNextFile()");
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    goto LABEL_59;
  }
  if ( !v15 )
  {
    WusaLogDebugEventA(L"WusaFindRelatedMSUFiles", 768, "No files found for pattern %ls", FileName);
    v5 = 0;
    goto LABEL_59;
  }
  v23 = v29;
  v5 = CoAllocArray<unsigned short *>(v21, v15, v29);
  if ( v5 >= 0 )
  {
    *a1 = 0;
    for ( i = 0; i < v15; ++i )
    {
      v25 = *(unsigned __int16 **)&v10[4 * i];
      if ( v25 )
      {
        (*v23)[(*a1)++] = v25;
        *(_QWORD *)&v10[4 * i] = 0;
      }
    }
    goto LABEL_59;
  }
  v11 = 771;
LABEL_15:
  WusaLogDebugEventA(L"WusaFindRelatedMSUFiles", v11, "Failed to allocate file names array");
LABEL_59:
  if ( v10 )
    CoTaskMemFree(v10);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000d620  mov     [rsp-8+arg_10], rbx
0x14000d625  push    rbp
0x14000d626  push    rsi
0x14000d627  push    rdi
0x14000d628  push    r12
0x14000d62a  push    r13
0x14000d62c  push    r14
0x14000d62e  push    r15
0x14000d630  lea     rbp, [rsp-1240h]
0x14000d638  mov     eax, 1340h
0x14000d63d  call    _alloca_probe
0x14000d642  sub     rsp, rax
0x14000d645  mov     rax, cs:__security_cookie
0x14000d64c  xor     rax, rsp
0x14000d64f  mov     [rbp+1270h+var_40], rax
0x14000d656  mov     rsi, rdx
0x14000d659  mov     [rsp+1370h+var_1318], rdx
0x14000d65e  mov     r12, rcx
0x14000d661  xor     edx, edx; Val
0x14000d663  lea     rcx, [rsp+1370h+FindFileData]; void *
0x14000d668  mov     r8d, 250h; Size
0x14000d66e  call    memset_0
0x14000d673  mov     rcx, cs:pszPath; FullPath
0x14000d67a  lea     rax, [rbp+1270h+var_860]
0x14000d681  mov     r15d, 100h
0x14000d687  lea     r9, [rbp+1270h+Dir]; Dir
0x14000d68e  mov     [rsp+1370h+ExtCount], r15; ExtCount
0x14000d693  lea     rdx, [rbp+1270h+Drive]; Drive
0x14000d69a  mov     [rsp+1370h+Ext], rax; Ext
0x14000d69f  xor     r13d, r13d
0x14000d6a2  lea     rax, [rbp+1270h+String2]
0x14000d6a9  mov     [rsp+1370h+FilenameCount], r15; FilenameCount
0x14000d6ae  mov     [rsp+1370h+Filename], rax; Filename
0x14000d6b3  lea     r14d, [r15+4]
0x14000d6b7  mov     [rsp+1370h+DirCount], r14; DirCount
0x14000d6bc  lea     r8d, [r13+3]; DriveCount
0x14000d6c0  mov     [rsp+1370h+FullPath], r13
0x14000d6c5  call    cs:__imp__wsplitpath_s
0x14000d6cb  mov     edi, eax
0x14000d6cd  test    eax, eax
0x14000d6cf  jns     short loc_14000D6F5
0x14000d6d1  mov     r9, cs:pszPath
0x14000d6d8  lea     r8, aFailedToGetPar; "Failed to get parent folder path for %l"...
0x14000d6df  mov     edx, 2BEh
0x14000d6e4  lea     rcx, aWusafindrelate; "WusaFindRelatedMSUFiles"
0x14000d6eb  call    WusaLogDebugEventA
0x14000d6f0  jmp     loc_14000DB1B
0x14000d6f5  lea     rax, [rbp+1270h+Dir]
0x14000d6fc  mov     ebx, 105h
0x14000d701  mov     edx, ebx; unsigned __int64
0x14000d703  mov     [rsp+1370h+DirCount], rax
0x14000d708  lea     r9, [rbp+1270h+Drive]
0x14000d70f  lea     r8, aSS_0; "%s%s"
0x14000d716  lea     rcx, [rbp+1270h+var_E70]; unsigned __int16 *
0x14000d71d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d722  mov     edi, eax
0x14000d724  test    eax, eax
0x14000d726  jns     short loc_14000D745
0x14000d728  mov     edx, 2C1h
0x14000d72d  lea     r8, aFailedToAppend_0; "Failed to append pattern to parent fold"...
0x14000d734  lea     rcx, aWusafindrelate; "WusaFindRelatedMSUFiles"
0x14000d73b  call    WusaLogDebugEventA
0x14000d740  jmp     loc_14000DB1B
0x14000d745  lea     r9, [rbp+1270h+var_E70]
0x14000d74c  mov     rdx, rbx; unsigned __int64
0x14000d74f  lea     r8, aSMsu; "%s*.msu"
0x14000d756  lea     rcx, [rbp+1270h+FileName]; unsigned __int16 *
0x14000d75d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d762  mov     edi, eax
0x14000d764  test    eax, eax
0x14000d766  jns     short loc_14000D76F
0x14000d768  mov     edx, 2C4h
0x14000d76d  jmp     short loc_14000D72D
0x14000d76f  test    r12, r12
0x14000d772  jnz     short loc_14000D796
0x14000d774  lea     r8, aFilescountCann; "filesCount cannot be null"
0x14000d77b  mov     edx, 2C6h
0x14000d780  lea     rcx, aWusafindrelate; "WusaFindRelatedMSUFiles"
0x14000d787  call    WusaLogDebugEventA
0x14000d78c  mov     edi, 8007000Eh
0x14000d791  jmp     loc_14000DB1B
0x14000d796  test    rsi, rsi
0x14000d799  jnz     short loc_14000D7A9
0x14000d79b  lea     r8, aFilesCannotBeN; "files cannot be null"
0x14000d7a2  mov     edx, 2C7h
0x14000d7a7  jmp     short loc_14000D780
0x14000d7a9  lea     r8, [rsp+1370h+FullPath]
0x14000d7ae  mov     rdx, r15
0x14000d7b1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000d7b5  call    ??$CoAllocArray@PEAG@@YAJK_KPEAPEAPEAG@Z; CoAllocArray<ushort *>(ulong,unsigned __int64,ushort * * *)
0x14000d7ba  mov     r15, [rsp+1370h+FullPath]
0x14000d7bf  mov     edi, eax
0x14000d7c1  test    eax, eax
0x14000d7c3  jns     short loc_14000D7E2
0x14000d7c5  mov     edx, 2CAh
0x14000d7ca  lea     r8, aFailedToAlloca_9; "Failed to allocate file names array"
0x14000d7d1  lea     rcx, aWusafindrelate; "WusaFindRelatedMSUFiles"
0x14000d7d8  call    WusaLogDebugEventA
0x14000d7dd  jmp     loc_14000DAFA
0x14000d7e2  xor     r9d, r9d; lpFilePart
0x14000d7e5  lea     r8, [rbp+1270h+Buffer]; lpBuffer
0x14000d7ec  mov     edx, r14d; nBufferLength
0x14000d7ef  lea     rcx, [rbp+1270h+FileName]; lpFileName
0x14000d7f6  call    cs:__imp_GetFullPathNameW
0x14000d7fc  test    eax, eax
0x14000d7fe  jz      loc_14000DABC
0x14000d804  lea     rdx, [rsp+1370h+FindFileData]; lpFindFileData
0x14000d809  lea     rcx, [rbp+1270h+Buffer]; lpFileName
0x14000d810  call    cs:__imp_FindFirstFileW
0x14000d816  mov     rbx, rax
0x14000d819  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d81d  jnz     short loc_14000D845
0x14000d81f  call    cs:__imp_GetLastError
0x14000d825  mov     edi, eax
0x14000d827  test    eax, eax
0x14000d829  jle     short loc_14000D834
0x14000d82b  movzx   edi, ax
0x14000d82e  or      edi, 80070000h
0x14000d834  lea     r8, aFailedToFindFi; "Failed to find first file for pattern %"...
0x14000d83b  mov     edx, 2D5h
0x14000d840  jmp     loc_14000DADD
0x14000d845  mov     r14d, r13d
0x14000d848  xor     edi, edi
0x14000d84a  cmp     r14d, 100h
0x14000d851  jnb     loc_14000D994
0x14000d857  test    byte ptr [rsp+1370h+FindFileData.dwFileAttributes], 10h
0x14000d85c  jnz     loc_14000D97E
0x14000d862  mov     [rsp+1370h+FullPath], rdi
0x14000d867  lea     rax, [rbp+1270h+FindFileData.cFileName]
0x14000d86b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000d86f  inc     rcx
0x14000d872  cmp     [rax+rcx*2], di
0x14000d876  jnz     short loc_14000D86F
0x14000d878  lea     rdx, [rbp+1270h+var_E70]
0x14000d87f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d883  inc     rax
0x14000d886  cmp     [rdx+rax*2], di
0x14000d88a  jnz     short loc_14000D883
0x14000d88c  lea     rdx, [rbp+1270h+var_E70]
0x14000d893  mov     [rbp+1270h+var_10A8], rax
0x14000d89a  mov     [rbp+1270h+var_10B0], rdx
0x14000d8a1  lea     rax, [rbp+1270h+FindFileData.cFileName]
0x14000d8a5  mov     [rbp+1270h+var_1098], rcx
0x14000d8ac  lea     rdx, [rbp+1270h+var_10C0]
0x14000d8b3  lea     rcx, [rsp+1370h+FullPath]
0x14000d8b8  mov     [rbp+1270h+var_10C0], rdi
0x14000d8bf  mov     [rbp+1270h+var_10B8], rdi
0x14000d8c6  mov     [rbp+1270h+var_10A0], rax
0x14000d8cd  call    ??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z; wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)
0x14000d8d2  mov     edi, eax
0x14000d8d4  test    eax, eax
0x14000d8d6  js      loc_14000DA07
0x14000d8dc  mov     rsi, [rsp+1370h+FullPath]
0x14000d8e1  lea     rax, [rbp+1270h+var_660]
0x14000d8e8  mov     [rsp+1370h+ExtCount], 100h; ExtCount
0x14000d8f1  xor     r9d, r9d; Dir
0x14000d8f4  mov     [rsp+1370h+Ext], rax; Ext
0x14000d8f9  xor     r8d, r8d; DriveCount
0x14000d8fc  lea     rax, [rbp+1270h+String1]
0x14000d903  mov     [rsp+1370h+FilenameCount], 100h; FilenameCount
0x14000d90c  mov     [rsp+1370h+Filename], rax; Filename
0x14000d911  xor     edx, edx; Drive
0x14000d913  mov     rcx, rsi; FullPath
0x14000d916  mov     [rsp+1370h+DirCount], 0; DirCount
0x14000d91f  call    cs:__imp__wsplitpath_s
0x14000d925  mov     edi, eax
0x14000d927  test    eax, eax
0x14000d929  js      loc_14000D9DE
0x14000d92f  lea     rdx, [rbp+1270h+String2]; String2
0x14000d936  lea     rcx, [rbp+1270h+String1]; String1
0x14000d93d  call    cs:__imp__wcsicmp
0x14000d943  xor     edi, edi
0x14000d945  test    eax, eax
0x14000d947  jnz     short loc_14000D971
0x14000d949  lea     rdx, [rbp+1270h+var_860]; String2
0x14000d950  lea     rcx, [rbp+1270h+var_660]; String1
0x14000d957  call    cs:__imp__wcsicmp
0x14000d95d  test    eax, eax
0x14000d95f  jnz     short loc_14000D971
0x14000d961  test    rsi, rsi
0x14000d964  jz      short loc_14000D97E
0x14000d966  mov     rcx, rsi; pv
0x14000d969  call    cs:__imp_CoTaskMemFree
0x14000d96f  jmp     short loc_14000D97E
0x14000d971  mov     eax, r13d
0x14000d974  inc     r13d
0x14000d977  inc     r14d
0x14000d97a  mov     [r15+rax*8], rsi
0x14000d97e  lea     rdx, [rsp+1370h+FindFileData]; lpFindFileData
0x14000d983  mov     rcx, rbx; hFindFile
0x14000d986  call    cs:__imp_FindNextFileW
0x14000d98c  test    eax, eax
0x14000d98e  jnz     loc_14000D84A
0x14000d994  call    cs:__imp_GetLastError
0x14000d99a  xor     r13d, r13d
0x14000d99d  mov     edi, eax
0x14000d99f  cmp     eax, 12h
0x14000d9a2  jz      loc_14000DA3C
0x14000d9a8  test    eax, eax
0x14000d9aa  jz      loc_14000DA3C
0x14000d9b0  lea     r8, aFailedFindnext; "Failed: FindNextFile()"
0x14000d9b7  mov     edx, 2FDh
0x14000d9bc  lea     rcx, aWusafindrelate; "WusaFindRelatedMSUFiles"
0x14000d9c3  call    WusaLogDebugEventA
0x14000d9c8  test    edi, edi
0x14000d9ca  jle     loc_14000DAFA
0x14000d9d0  movzx   edi, di
0x14000d9d3  or      edi, 80070000h
0x14000d9d9  jmp     loc_14000DAFA
0x14000d9de  mov     r9, rsi
0x14000d9e1  lea     r8, aFailedToGetFil; "Failed to get file name from full path "...
0x14000d9e8  mov     edx, 2EFh
0x14000d9ed  lea     rcx, aWusafindrelate; "WusaFindRelatedMSUFiles"
0x14000d9f4  call    WusaLogDebugEventA
0x14000d9f9  test    rsi, rsi
0x14000d9fc  jz      loc_14000DAFA
0x14000da02  mov     rcx, rsi
0x14000da05  jmp     short loc_14000DA31
0x14000da07  lea     r9, [rbp+1270h+FindFileData.cFileName]
0x14000da0b  mov     edx, 2EAh
0x14000da10  lea     r8, aFailedToConcat; "Failed to concatenate file name %ls"
0x14000da17  lea     rcx, aWusafindrelate; "WusaFindRelatedMSUFiles"
0x14000da1e  call    WusaLogDebugEventA
0x14000da23  mov     rcx, [rsp+1370h+FullPath]; pv
0x14000da28  test    rcx, rcx
0x14000da2b  jz      loc_14000DAFA
0x14000da31  call    cs:__imp_CoTaskMemFree
0x14000da37  jmp     loc_14000DAFA
0x14000da3c  test    r14d, r14d
0x14000da3f  jnz     short loc_14000DA68
0x14000da41  lea     r9, [rbp+1270h+FileName]
0x14000da48  mov     edx, 300h
0x14000da4d  lea     r8, aNoFilesFoundFo; "No files found for pattern %ls"
0x14000da54  lea     rcx, aWusafindrelate; "WusaFindRelatedMSUFiles"
0x14000da5b  call    WusaLogDebugEventA
0x14000da60  mov     edi, r13d
0x14000da63  jmp     loc_14000DAFA
0x14000da68  mov     rsi, [rsp+1370h+var_1318]
0x14000da6d  mov     r8, rsi
0x14000da70  mov     edx, r14d
0x14000da73  call    ??$CoAllocArray@PEAG@@YAJK_KPEAPEAPEAG@Z; CoAllocArray<ushort *>(ulong,unsigned __int64,ushort * * *)
0x14000da78  mov     edi, eax
0x14000da7a  test    eax, eax
0x14000da7c  jns     short loc_14000DA88
0x14000da7e  mov     edx, 303h
0x14000da83  jmp     loc_14000D7CA
0x14000da88  mov     [r12], r13d
0x14000da8c  mov     edx, r13d
0x14000da8f  test    r14d, r14d
0x14000da92  jz      short loc_14000DAFA
0x14000da94  mov     r8d, edx
0x14000da97  mov     r9, [r15+r8*8]
0x14000da9b  test    r9, r9
0x14000da9e  jz      short loc_14000DAB3
0x14000daa0  mov     ecx, [r12]
0x14000daa4  mov     rax, [rsi]
0x14000daa7  mov     [rax+rcx*8], r9
0x14000daab  inc     dword ptr [r12]
0x14000daaf  mov     [r15+r8*8], r13
0x14000dab3  inc     edx
0x14000dab5  cmp     edx, r14d
0x14000dab8  jb      short loc_14000DA94
0x14000daba  jmp     short loc_14000DAFA
0x14000dabc  call    cs:__imp_GetLastError
0x14000dac2  mov     edi, eax
0x14000dac4  test    eax, eax
0x14000dac6  jle     short loc_14000DAD1
0x14000dac8  movzx   edi, ax
0x14000dacb  or      edi, 80070000h
0x14000dad1  lea     r8, aFailedToGetFul; "Failed to get full path name for patter"...
0x14000dad8  mov     edx, 2CFh
0x14000dadd  test    edi, edi
0x14000dadf  lea     r9, [rbp+1270h+FileName]
0x14000dae6  mov     eax, 80004005h
0x14000daeb  lea     rcx, aWusafindrelate; "WusaFindRelatedMSUFiles"
0x14000daf2  cmovns  edi, eax
0x14000daf5  call    WusaLogDebugEventA
0x14000dafa  test    r15, r15
0x14000dafd  jz      short loc_14000DB08
0x14000daff  mov     rcx, r15; pv
0x14000db02  call    cs:__imp_CoTaskMemFree
0x14000db08  lea     rax, [rbx-1]
0x14000db0c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000db10  ja      short loc_14000DB1B
0x14000db12  mov     rcx, rbx; hFindFile
0x14000db15  call    cs:__imp_FindClose
0x14000db1b  mov     eax, edi
0x14000db1d  mov     rcx, [rbp+1270h+var_40]
0x14000db24  xor     rcx, rsp; StackCookie
0x14000db27  call    __security_check_cookie
0x14000db2c  mov     rbx, [rsp+1370h+arg_10]
0x14000db34  add     rsp, 1340h
0x14000db3b  pop     r15
0x14000db3d  pop     r14
0x14000db3f  pop     r13
0x14000db41  pop     r12
0x14000db43  pop     rdi
0x14000db44  pop     rsi
0x14000db45  pop     rbp
0x14000db46  retn
  ... truncated ...
```
