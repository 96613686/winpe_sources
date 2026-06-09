# Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles(ushort const *)

- ea: `0x140029710`
- end: `0x140029ae7`
- name: `?ClearTempDirectoryOfMatchingTempFiles@SdbFileData@Utils@MergeSdb@Pca@@SAKPEBG@Z`
- size: `983`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x140024958`

## callees

- `0x14001008c`
- `0x140021934`
- `0x14002198c`
- `0x14002840c`
- `0x140029710`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400298dc`
- `KERNEL32!GetLastError` at `0x14002991e`
- `KERNEL32!GetLastError` at `0x1400299d4`
- `KERNEL32!GetLastError` at `0x1400298dc`
- `KERNEL32!GetLastError` at `0x14002991e`
- `KERNEL32!GetLastError` at `0x1400299d4`
- `KERNEL32!DeleteFileW` at `0x1400298d2`
- `KERNEL32!DeleteFileW` at `0x1400298d2`
- `KERNEL32!GetProcessHeap` at `0x140029932`
- `KERNEL32!GetProcessHeap` at `0x140029994`
- `KERNEL32!GetProcessHeap` at `0x1400299b8`
- `KERNEL32!GetProcessHeap` at `0x140029a26`
- `KERNEL32!GetProcessHeap` at `0x140029a5a`
- `KERNEL32!GetProcessHeap` at `0x140029aae`
- `KERNEL32!GetProcessHeap` at `0x140029932`
- `KERNEL32!GetProcessHeap` at `0x140029994`
- `KERNEL32!GetProcessHeap` at `0x1400299b8`
- `KERNEL32!GetProcessHeap` at `0x140029a26`
- `KERNEL32!GetProcessHeap` at `0x140029a5a`
- `KERNEL32!GetProcessHeap` at `0x140029aae`
- `KERNEL32!FindFirstFileExW` at `0x140029827`
- `KERNEL32!FindFirstFileExW` at `0x140029827`
- `KERNEL32!FindClose` at `0x1400299ac`
- `KERNEL32!FindClose` at `0x140029a1a`
- `KERNEL32!FindClose` at `0x140029a4e`
- `KERNEL32!FindClose` at `0x1400299ac`
- `KERNEL32!FindClose` at `0x140029a1a`
- `KERNEL32!FindClose` at `0x140029a4e`
- `KERNEL32!FindNextFileW` at `0x14002990f`
- `KERNEL32!FindNextFileW` at `0x14002990f`
- `KERNEL32!HeapFree` at `0x140029940`
- `KERNEL32!HeapFree` at `0x1400299a2`
- `KERNEL32!HeapFree` at `0x1400299c6`
- `KERNEL32!HeapFree` at `0x140029a34`
- `KERNEL32!HeapFree` at `0x140029a68`
- `KERNEL32!HeapFree` at `0x140029abc`
- `KERNEL32!HeapFree` at `0x140029940`
- `KERNEL32!HeapFree` at `0x1400299a2`
- `KERNEL32!HeapFree` at `0x1400299c6`
- `KERNEL32!HeapFree` at `0x140029a34`
- `KERNEL32!HeapFree` at `0x140029a68`
- `KERNEL32!HeapFree` at `0x140029abc`

## string_xrefs

- `0x1400298ec`: `DeleteFileW failed to delete sdb file (%d)`
- `0x14002996d`: `Failed to build full path for sdb to delete (%d)`
- `0x140029795`: `temp.????????????????.sdb`
- `0x140029a8b`: `Failed to concat temp dir search path (%d)`
- `0x1400299f0`: `FindFirstFileExW failed to search temp dir for temp sdb files (%d)`
- `0x1400298f9`: `Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles`
- `0x14002997a`: `Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles`
- `0x1400299fd`: `Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles`
- `0x140029a92`: `Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles(const unsigned __int16 *a1)
{
  __int64 v2; // rdx
  int v3; // eax
  unsigned int v4; // edi
  __int64 v5; // r8
  __int64 v6; // r8
  int v7; // eax
  WCHAR *v8; // rbx
  char *FirstFile; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // r15d
  WCHAR *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // r15d
  HANDLE v17; // rax
  WCHAR *v18; // rsi
  HANDLE v19; // rax
  HANDLE v20; // rax
  DWORD LastError; // esi
  HANDLE v23; // rax
  HANDLE v24; // rax
  WCHAR *v25; // rbx
  HANDLE ProcessHeap; // rax
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *cFileName; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h]
  _QWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v32[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v33[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v34[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v28[0] = a1;
  lpFileName[0] = 0;
  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  if ( a1[v2 - 1] == 92 )
  {
    v6 = -1;
    do
      ++v6;
    while ( aTempSdb[v6] );
    v31[0] = L"temp.????????????????.sdb";
    v31[1] = v6;
    v28[0] = a1;
    v28[1] = (LPCWSTR)(v2 & -(__int64)(a1 != 0));
    cFileName = 0;
    v30 = 0;
    v7 = wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(
           lpFileName,
           &cFileName,
           v28,
           v31);
    v4 = v7;
    if ( v7 < 0 )
    {
      if ( (v7 & 0x1FFF0000) == 0x70000 )
        v4 = (unsigned __int16)v7;
      v5 = 2393;
      goto LABEL_55;
    }
  }
  else
  {
    v3 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const *,unsigned short [2],unsigned short [26]>(
           lpFileName,
           v28);
    v4 = v3;
    if ( v3 < 0 )
    {
      if ( (v3 & 0x1FFF0000) == 0x70000 )
        v4 = (unsigned __int16)v3;
      v5 = 2384;
LABEL_55:
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles",
        v5,
        "Failed to concat temp dir search path (%d)",
        v4);
      v25 = (WCHAR *)lpFileName[0];
      if ( lpFileName[0] )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v25);
      }
      return v4;
    }
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v8 = (WCHAR *)lpFileName[0];
  FirstFile = (char *)FindFirstFileExW(lpFileName[0], FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  v31[0] = FirstFile;
  if ( (unsigned __int64)(FirstFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1;
    if ( ((LastError - 2) & 0xFFFFFFEF) != 0 )
    {
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles",
        2409,
        "FindFirstFileExW failed to search temp dir for temp sdb files (%d)",
        LastError);
      if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        FindClose(FirstFile);
      if ( v8 )
      {
        v23 = GetProcessHeap();
        HeapFree(v23, 0, v8);
      }
      return LastError;
    }
    else
    {
LABEL_47:
      if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        FindClose(FirstFile);
      if ( v8 )
      {
        v24 = GetProcessHeap();
        HeapFree(v24, 0, v8);
      }
      return 0;
    }
  }
  else
  {
    while ( 1 )
    {
      v28[0] = 0;
      v10 = -1;
      do
        ++v10;
      while ( FindFileData.cFileName[v10] );
      if ( a1 )
      {
        v11 = -1;
        do
          ++v11;
        while ( a1[v11] );
      }
      else
      {
        v11 = 0;
      }
      cFileName = FindFileData.cFileName;
      v30 = v10;
      v32[0] = L"\\";
      v32[1] = 1;
      v33[0] = a1;
      v33[1] = v11;
      v34[0] = 0;
      v34[1] = 0;
      v12 = wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(
              (unsigned int)v28,
              (unsigned int)v34,
              (unsigned int)v33,
              (unsigned int)v32,
              (__int64)&cFileName);
      v13 = v12;
      if ( v12 < 0 )
        break;
      v14 = (WCHAR *)v28[0];
      if ( !DeleteFileW(v28[0]) )
      {
        v15 = GetLastError();
        if ( !v15 )
          v15 = 1;
        AslLogCallPrintf(
          1,
          "Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles",
          2428,
          "DeleteFileW failed to delete sdb file (%d)",
          v15);
      }
      if ( FindNextFileW(FirstFile, &FindFileData) )
      {
        v16 = 0;
      }
      else
      {
        v16 = GetLastError();
        if ( !v16 )
          v16 = 1;
      }
      if ( v14 )
      {
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v14);
      }
      if ( v16 )
        goto LABEL_47;
    }
    if ( (v12 & 0x1FFF0000) == 0x70000 )
      v13 = (unsigned __int16)v12;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::ClearTempDirectoryOfMatchingTempFiles",
      2422,
      "Failed to build full path for sdb to delete (%d)",
      v13);
    v18 = (WCHAR *)v28[0];
    if ( v28[0] )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v18);
    }
    FindClose(FirstFile);
    if ( v8 )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v8);
    }
    return v13;
  }
}

```

## disassembly

```asm
0x140029710  push    rbp
0x140029712  push    rbx
0x140029713  push    rsi
0x140029714  push    rdi
0x140029715  push    r12
0x140029717  push    r13
0x140029719  push    r14
0x14002971b  push    r15
0x14002971d  lea     rbp, [rsp-208h]
0x140029725  sub     rsp, 308h
0x14002972c  mov     rax, cs:__security_cookie
0x140029733  xor     rax, rsp
0x140029736  mov     [rbp+240h+var_50], rax
0x14002973d  mov     r12, rcx
0x140029740  mov     [rsp+340h+var_300], rcx
0x140029745  xor     r13d, r13d
0x140029748  mov     [rsp+340h+lpFileName], r13
0x14002974d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140029751  mov     rdx, rsi
0x140029754  inc     rdx
0x140029757  cmp     [rcx+rdx*2], r13w
0x14002975c  jnz     short loc_140029754
0x14002975e  cmp     word ptr [rcx+rdx*2-2], 5Ch ; '\'
0x140029764  jz      short loc_140029795
0x140029766  lea     rdx, [rsp+340h+var_300]
0x14002976b  lea     rcx, [rsp+340h+lpFileName]
0x140029770  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG$$BY01G$$BY0BK@G@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEBGAEAY01$$CBGAEAY0BK@$$CBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort const *,ushort [2],ushort [26]>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * const &,ushort const (&)[2],ushort const (&)[26])
0x140029775  mov     edi, eax
0x140029777  test    eax, eax
0x140029779  jns     short loc_1400297F6
0x14002977b  and     eax, 1FFF0000h
0x140029780  cmp     eax, 70000h
0x140029785  jnz     short loc_14002978A
0x140029787  movzx   edi, di
0x14002978a  mov     r8d, 950h
0x140029790  jmp     loc_140029A87
0x140029795  lea     r9, aTempSdb; "temp.????????????????.sdb"
0x14002979c  mov     r8, rsi
0x14002979f  inc     r8
0x1400297a2  cmp     [r9+r8*2], r13w
0x1400297a7  jnz     short loc_14002979F
0x1400297a9  mov     rax, r12
0x1400297ac  neg     rax
0x1400297af  sbb     rcx, rcx
0x1400297b2  and     rcx, rdx
0x1400297b5  mov     [rsp+340h+var_2E0], r9
0x1400297ba  mov     [rsp+340h+var_2D8], r8
0x1400297bf  mov     [rsp+340h+var_300], r12
0x1400297c4  mov     [rsp+340h+var_2F8], rcx
0x1400297c9  mov     [rsp+340h+var_2F0], r13
0x1400297ce  mov     [rsp+340h+var_2E8], r13
0x1400297d3  lea     r9, [rsp+340h+var_2E0]
0x1400297d8  lea     r8, [rsp+340h+var_300]
0x1400297dd  lea     rdx, [rsp+340h+var_2F0]
0x1400297e2  lea     rcx, [rsp+340h+lpFileName]
0x1400297e7  call    ??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Ustring_view_t@details@2@U342@U342@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@Ustring_view_t@01@11@Z; wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t)
0x1400297ec  mov     edi, eax
0x1400297ee  test    eax, eax
0x1400297f0  js      loc_140029A72
0x1400297f6  xor     edx, edx; Val
0x1400297f8  mov     r8d, 250h; Size
0x1400297fe  lea     rcx, [rbp+240h+FindFileData]; void *
0x140029802  call    memset_0
0x140029807  mov     [rsp+340h+dwAdditionalFlags], r13d; dwAdditionalFlags
0x14002980c  mov     [rsp+340h+lpSearchFilter], r13; lpSearchFilter
0x140029811  xor     r9d, r9d; fSearchOp
0x140029814  lea     r8, [rbp+240h+FindFileData]; lpFindFileData
0x140029818  lea     r14d, [r9+1]
0x14002981c  mov     edx, r14d; fInfoLevelId
0x14002981f  mov     rbx, [rsp+340h+lpFileName]
0x140029824  mov     rcx, rbx; lpFileName
0x140029827  call    cs:__imp_FindFirstFileExW
0x14002982d  mov     rdi, rax
0x140029830  mov     [rsp+340h+var_2E0], rax
0x140029835  dec     rax
0x140029838  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002983c  ja      loc_1400299D4
0x140029842  mov     [rsp+340h+var_300], r13
0x140029847  lea     rax, [rbp+240h+var_274]
0x14002984b  mov     rcx, rsi
0x14002984e  inc     rcx
0x140029851  cmp     [rax+rcx*2], r13w
0x140029856  jnz     short loc_14002984E
0x140029858  test    r12, r12
0x14002985b  jz      short loc_14002986C
0x14002985d  mov     rax, rsi
0x140029860  inc     rax
0x140029863  cmp     [r12+rax*2], r13w
0x140029868  jnz     short loc_140029860
0x14002986a  jmp     short loc_14002986F
0x14002986c  mov     rax, r13
0x14002986f  lea     rdx, [rbp+240h+var_274]
0x140029873  mov     [rsp+340h+var_2F0], rdx
0x140029878  mov     [rsp+340h+var_2E8], rcx
0x14002987d  lea     rcx, asc_1400326D0; "\\"
0x140029884  mov     [rsp+340h+var_2D0], rcx
0x140029889  mov     [rsp+340h+var_2C8], r14
0x14002988e  mov     [rbp+240h+var_2C0], r12
0x140029892  mov     [rbp+240h+var_2B8], rax
0x140029896  mov     [rbp+240h+var_2B0], r13
0x14002989a  mov     [rbp+240h+var_2A8], r13
0x14002989e  lea     rax, [rsp+340h+var_2F0]
0x1400298a3  mov     [rsp+340h+lpSearchFilter], rax
0x1400298a8  lea     r9, [rsp+340h+var_2D0]
0x1400298ad  lea     r8, [rbp+240h+var_2C0]
0x1400298b1  lea     rdx, [rbp+240h+var_2B0]
0x1400298b5  lea     rcx, [rsp+340h+var_300]
0x1400298ba  call    ??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Ustring_view_t@details@2@U342@U342@U342@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@Ustring_view_t@01@111@Z; wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t)
0x1400298bf  mov     r15d, eax
0x1400298c2  test    eax, eax
0x1400298c4  js      loc_140029958
0x1400298ca  mov     rsi, [rsp+340h+var_300]
0x1400298cf  mov     rcx, rsi; lpFileName
0x1400298d2  call    cs:__imp_DeleteFileW
0x1400298d8  test    eax, eax
0x1400298da  jnz     short loc_140029908
0x1400298dc  call    cs:__imp_GetLastError
0x1400298e2  test    eax, eax
0x1400298e4  cmovz   eax, r14d
0x1400298e8  mov     dword ptr [rsp+340h+lpSearchFilter], eax
0x1400298ec  lea     r9, aDeletefilewFai; "DeleteFileW failed to delete sdb file ("...
0x1400298f3  mov     r8d, 97Ch
0x1400298f9  lea     rdx, aPcaMergesdbUti_18; "Pca::MergeSdb::Utils::SdbFileData::Clea"...
0x140029900  mov     ecx, r14d
0x140029903  call    AslLogCallPrintf
0x140029908  lea     rdx, [rbp+240h+FindFileData]; lpFindFileData
0x14002990c  mov     rcx, rdi; hFindFile
0x14002990f  call    cs:__imp_FindNextFileW
0x140029915  test    eax, eax
0x140029917  jz      short loc_14002991E
0x140029919  mov     r15d, r13d
0x14002991c  jmp     short loc_14002992D
0x14002991e  call    cs:__imp_GetLastError
0x140029924  mov     r15d, eax
0x140029927  test    eax, eax
0x140029929  cmovz   r15d, r14d
0x14002992d  test    rsi, rsi
0x140029930  jz      short loc_140029946
0x140029932  call    cs:__imp_GetProcessHeap
0x140029938  mov     rcx, rax; hHeap
0x14002993b  mov     r8, rsi; lpMem
0x14002993e  xor     edx, edx; dwFlags
0x140029940  call    cs:__imp_HeapFree
0x140029946  test    r15d, r15d
0x140029949  jnz     loc_140029A41
0x14002994f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140029953  jmp     loc_140029842
0x140029958  and     eax, 1FFF0000h
0x14002995d  cmp     eax, 70000h
0x140029962  jnz     short loc_140029968
0x140029964  movzx   r15d, r15w
0x140029968  mov     dword ptr [rsp+340h+lpSearchFilter], r15d
0x14002996d  lea     r9, aFailedToBuildF; "Failed to build full path for sdb to de"...
0x140029974  mov     r8d, 976h
0x14002997a  lea     rdx, aPcaMergesdbUti_18; "Pca::MergeSdb::Utils::SdbFileData::Clea"...
0x140029981  mov     ecx, r14d
0x140029984  call    AslLogCallPrintf
0x140029989  nop
0x14002998a  mov     rsi, [rsp+340h+var_300]
0x14002998f  test    rsi, rsi
0x140029992  jz      short loc_1400299A9
0x140029994  call    cs:__imp_GetProcessHeap
0x14002999a  mov     rcx, rax; hHeap
0x14002999d  mov     r8, rsi; lpMem
0x1400299a0  xor     edx, edx; dwFlags
0x1400299a2  call    cs:__imp_HeapFree
0x1400299a8  nop
0x1400299a9  mov     rcx, rdi; hFindFile
0x1400299ac  call    cs:__imp_FindClose
0x1400299b2  nop
0x1400299b3  test    rbx, rbx
0x1400299b6  jz      short loc_1400299CC
0x1400299b8  call    cs:__imp_GetProcessHeap
0x1400299be  mov     rcx, rax; hHeap
0x1400299c1  mov     r8, rbx; lpMem
0x1400299c4  xor     edx, edx; dwFlags
0x1400299c6  call    cs:__imp_HeapFree
0x1400299cc  mov     eax, r15d
0x1400299cf  jmp     loc_140029AC4
0x1400299d4  call    cs:__imp_GetLastError
0x1400299da  mov     esi, eax
0x1400299dc  test    eax, eax
0x1400299de  cmovz   esi, r14d
0x1400299e2  lea     eax, [rsi-2]
0x1400299e5  test    eax, 0FFFFFFEFh
0x1400299ea  jz      short loc_140029A41
0x1400299ec  mov     dword ptr [rsp+340h+lpSearchFilter], esi
0x1400299f0  lea     r9, aFindfirstfilee_0; "FindFirstFileExW failed to search temp "...
0x1400299f7  mov     r8d, 969h
0x1400299fd  lea     rdx, aPcaMergesdbUti_18; "Pca::MergeSdb::Utils::SdbFileData::Clea"...
0x140029a04  mov     ecx, r14d
0x140029a07  call    AslLogCallPrintf
0x140029a0c  nop
0x140029a0d  lea     rax, [rdi-1]
0x140029a11  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140029a15  ja      short loc_140029A21
0x140029a17  mov     rcx, rdi; hFindFile
0x140029a1a  call    cs:__imp_FindClose
0x140029a20  nop
0x140029a21  test    rbx, rbx
0x140029a24  jz      short loc_140029A3A
0x140029a26  call    cs:__imp_GetProcessHeap
0x140029a2c  mov     rcx, rax; hHeap
0x140029a2f  mov     r8, rbx; lpMem
0x140029a32  xor     edx, edx; dwFlags
0x140029a34  call    cs:__imp_HeapFree
0x140029a3a  mov     eax, esi
0x140029a3c  jmp     loc_140029AC4
0x140029a41  lea     rax, [rdi-1]
0x140029a45  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140029a49  ja      short loc_140029A55
0x140029a4b  mov     rcx, rdi; hFindFile
0x140029a4e  call    cs:__imp_FindClose
0x140029a54  nop
0x140029a55  test    rbx, rbx
0x140029a58  jz      short loc_140029A6E
0x140029a5a  call    cs:__imp_GetProcessHeap
0x140029a60  mov     rcx, rax; hHeap
0x140029a63  mov     r8, rbx; lpMem
0x140029a66  xor     edx, edx; dwFlags
0x140029a68  call    cs:__imp_HeapFree
0x140029a6e  xor     eax, eax
0x140029a70  jmp     short loc_140029AC4
0x140029a72  and     eax, 1FFF0000h
0x140029a77  cmp     eax, 70000h
0x140029a7c  jnz     short loc_140029A81
0x140029a7e  movzx   edi, di
0x140029a81  mov     r8d, 959h
0x140029a87  mov     dword ptr [rsp+340h+lpSearchFilter], edi
0x140029a8b  lea     r9, aFailedToConcat; "Failed to concat temp dir search path ("...
0x140029a92  lea     rdx, aPcaMergesdbUti_18; "Pca::MergeSdb::Utils::SdbFileData::Clea"...
0x140029a99  mov     ecx, 1
0x140029a9e  call    AslLogCallPrintf
0x140029aa3  nop
0x140029aa4  mov     rbx, [rsp+340h+lpFileName]
0x140029aa9  test    rbx, rbx
0x140029aac  jz      short loc_140029AC2
0x140029aae  call    cs:__imp_GetProcessHeap
0x140029ab4  mov     r8, rbx; lpMem
0x140029ab7  xor     edx, edx; dwFlags
0x140029ab9  mov     rcx, rax; hHeap
0x140029abc  call    cs:__imp_HeapFree
0x140029ac2  mov     eax, edi
0x140029ac4  mov     rcx, [rbp+240h+var_50]
0x140029acb  xor     rcx, rsp; StackCookie
0x140029ace  call    __security_check_cookie
0x140029ad3  add     rsp, 308h
0x140029ada  pop     r15
0x140029adc  pop     r14
0x140029ade  pop     r13
0x140029ae0  pop     r12
0x140029ae2  pop     rdi
0x140029ae3  pop     rsi
0x140029ae4  pop     rbx
0x140029ae5  pop     rbp
0x140029ae6  retn
```
