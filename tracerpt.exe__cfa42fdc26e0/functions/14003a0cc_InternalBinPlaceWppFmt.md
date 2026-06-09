# InternalBinPlaceWppFmt

- ea: `0x14003a0cc`
- end: `0x14003a6dc`
- name: `InternalBinPlaceWppFmt`
- size: `1552`
- prototype: `__int64 __fastcall(LPCWSTR *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x14003b824`

## callees

- `0x1400020e4`
- `0x140002bf0`
- `0x140038850`
- `0x1400397ac`
- `0x140039d80`
- `0x14003a0cc`
- `0x14003b53c`
- `0x14003b760`
- `0x140040130`

## import_xrefs

- `msvcrt!free` at `0x14003a5af`
- `msvcrt!free` at `0x14003a5c1`
- `msvcrt!free` at `0x14003a634`
- `msvcrt!free` at `0x14003a63f`
- `msvcrt!free` at `0x14003a663`
- `msvcrt!free` at `0x14003a5af`
- `msvcrt!free` at `0x14003a5c1`
- `msvcrt!free` at `0x14003a634`
- `msvcrt!free` at `0x14003a63f`
- `msvcrt!free` at `0x14003a663`
- `msvcrt!sprintf_s` at `0x14003a225`
- `msvcrt!sprintf_s` at `0x14003a290`
- `msvcrt!sprintf_s` at `0x14003a225`
- `msvcrt!sprintf_s` at `0x14003a290`
- `msvcrt!fprintf` at `0x14003a191`
- `msvcrt!fprintf` at `0x14003a381`
- `msvcrt!fprintf` at `0x14003a41c`
- `msvcrt!fprintf` at `0x14003a4c4`
- `msvcrt!fprintf` at `0x14003a525`
- `msvcrt!fprintf` at `0x14003a54c`
- `msvcrt!fprintf` at `0x14003a560`
- `msvcrt!fprintf` at `0x14003a191`
- `msvcrt!fprintf` at `0x14003a381`
- `msvcrt!fprintf` at `0x14003a41c`
- `msvcrt!fprintf` at `0x14003a4c4`
- `msvcrt!fprintf` at `0x14003a525`
- `msvcrt!fprintf` at `0x14003a54c`
- `msvcrt!fprintf` at `0x14003a560`
- `msvcrt!fclose` at `0x14003a4e4`
- `msvcrt!fclose` at `0x14003a56d`
- `msvcrt!fclose` at `0x14003a4e4`
- `msvcrt!fclose` at `0x14003a56d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a4cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a4cc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14003a201`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14003a201`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003a617`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003a617`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003a1c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003a1c2`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x14003a1eb`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x14003a1eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a2a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a2a6`
- `imagehlp!SymCleanup` at `0x14003a683`
- `imagehlp!SymCleanup` at `0x14003a683`
- `imagehlp!SymSetOptions` at `0x14003a693`
- `imagehlp!SymSetOptions` at `0x14003a693`
- `imagehlp!SymEnumTypesByName` at `0x14003a3e8`
- `imagehlp!SymEnumTypesByName` at `0x14003a3e8`
- `imagehlp!SymGetOptions` at `0x14003a136`
- `imagehlp!SymGetOptions` at `0x14003a136`
- `dbghelp!SymSearch` at `0x14003a35b`
- `dbghelp!SymSearch` at `0x14003a35b`

## string_xrefs

- `0x14003a277`: `// PDB:  Last Updated :%04d-%02d-%02d:%02d:%02d:%02d:%03d (UTC) [%ls]\n`

## pseudocode

```c
__int64 __fastcall InternalBinPlaceWppFmt(LPCWSTR *a1, __int64 a2, _QWORD *a3)
{
  DWORD Options; // r13d
  DWORD dwLowDateTime; // r14d
  unsigned __int64 v8; // r8
  FILE *v9; // rax
  const wchar_t *v10; // r12
  HANDLE FileW; // rax
  void *v12; // rsi
  unsigned __int64 v13; // r9
  __int64 v14; // rcx
  _WORD *v15; // r10
  _WORD *v16; // rdx
  const wchar_t *v17; // r8
  DWORD LastError; // ebx
  FILE *v19; // rax
  unsigned __int16 v20; // r15
  const char *v21; // rdi
  DWORD v22; // ebx
  FILE *v23; // rax
  __int64 v24; // rcx
  _WORD *v25; // rdx
  const wchar_t *v26; // r8
  FILE *v27; // rax
  const wchar_t *v28; // rbx
  FILE *v29; // rax
  FILE *v30; // rcx
  void **v31; // rsi
  unsigned __int16 v32; // bx
  unsigned __int16 i; // di
  unsigned __int16 v34; // r15
  unsigned __int16 v35; // si
  _DWORD *v36; // r13
  unsigned int v37; // ebx
  __int64 v38; // rdi
  void *v39; // rcx
  struct _FILETIME LastWriteTime; // [rsp+60h] [rbp-79h] BYREF
  DWORD v42; // [rsp+68h] [rbp-71h]
  void *v43[2]; // [rsp+70h] [rbp-69h] BYREF
  _WORD v44[8]; // [rsp+80h] [rbp-59h] BYREF
  __int128 UserContext; // [rsp+90h] [rbp-49h] BYREF
  __int128 v46; // [rsp+A0h] [rbp-39h]
  __int128 v47; // [rsp+B0h] [rbp-29h]
  __int64 v48; // [rsp+C0h] [rbp-19h]
  struct _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-9h] BYREF

  v48 = 0;
  v44[0] = 0;
  v43[0] = v44;
  g_fVerbose = 0;
  v43[1] = v44;
  ClassWrittenToMof = 0;
  UserContext = 0;
  v46 = 0;
  v47 = 0;
  Options = SymGetOptions();
  v42 = Options;
  if ( InitializeGlobals() )
  {
    v8 = *(_QWORD *)(a2 + 8);
    if ( !v8
      || utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
           (__int64)v43,
           *(const void **)a2,
           v8) )
    {
      v10 = *a1;
      FileW = CreateFileW(*a1, 0x80000000, 0, 0, 3u, 0x80u, 0);
      v12 = FileW;
      if ( FileW )
      {
        LastWriteTime = 0;
        SystemTime = 0;
        if ( GetFileTime(FileW, 0, 0, &LastWriteTime) && FileTimeToSystemTime(&LastWriteTime, &SystemTime) )
        {
          if ( sprintf_s(FirstLine, 0x204u, "// PDB:  %ls\n", v10) <= 0 )
            byte_140083402 = 10;
          if ( sprintf_s(
                 SecondLine,
                 0x204u,
                 "// PDB:  Last Updated :%04d-%02d-%02d:%02d:%02d:%02d:%03d (UTC) [%ls]\n",
                 SystemTime.wYear,
                 SystemTime.wMonth,
                 SystemTime.wDay,
                 SystemTime.wHour,
                 SystemTime.wMinute,
                 SystemTime.wSecond,
                 SystemTime.wMilliseconds,
                 (const wchar_t *)g_CurrentModuleFileName) <= 0 )
            byte_1400824B2 = 10;
        }
        CloseHandle(v12);
      }
      SystemTime = *(struct _SYSTEMTIME *)a1;
      g_fTraceAnnotationFound = 0;
      if ( (unsigned int)fnLoad((__int64)&SystemTime) )
      {
        v13 = a3[1];
        v14 = 7;
        v15 = (_WORD *)*a3;
        *((_QWORD *)&UserContext + 1) = v10;
        *(void **)&v46 = v43[0];
        if ( v13 == 7 )
        {
          v16 = v15;
          v17 = L"GEN_TMC";
          while ( *v16 == *v17 )
          {
            ++v16;
            ++v17;
            if ( !--v14 )
            {
              GenTMCFile = 1;
              goto LABEL_20;
            }
          }
        }
        v24 = 5;
        if ( v13 >= 5 )
        {
          v25 = v15;
          v26 = L"FILE:";
          while ( *v26 == *v25 )
          {
            ++v26;
            ++v25;
            if ( !--v24 )
            {
              SingleFile = 1;
              if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                     (__int64)&g_SingleFileName,
                     v15 + 5,
                     v13 - 5) )
              {
                break;
              }
              dwLowDateTime = 14;
              LastWriteTime.dwLowDateTime = 14;
              v27 = _acrt_iob_func(2u);
              fprintf(v27, "WPPFMT : error : out of memory\n");
              goto LABEL_42;
            }
          }
        }
LABEL_20:
        dwLowDateTime = 0;
        LastWriteTime.dwLowDateTime = 0;
        if ( !SymSearch(gSymHandle, gBase, 0, 0, 0, 0, (PSYM_ENUMERATESYMBOLS_CALLBACK)cbEnumSymbols, &UserContext, 2u) )
        {
          LastError = GetLastError();
          v19 = _acrt_iob_func(2u);
          fprintf(v19, "WPPFMT : error : 0x%X calling SymSearch()\n", LastError);
        }
        if ( PostProcessEnums && NextFreeGuid )
        {
          v20 = 0;
          if ( NextFreeEnum )
          {
            do
            {
              if ( !SymEnumTypesByName(gSymHandle, gBase, *((PCSTR *)EnumHead + 3 * v20), EnumerateEnumsCallback, 0) )
              {
                v21 = (const char *)*((_QWORD *)EnumHead + 3 * v20);
                v22 = GetLastError();
                v23 = _acrt_iob_func(2u);
                fprintf(v23, "WPPFMT : error : 0x%X calling SymSearch(%hs)\n", v22, v21);
              }
              ++v20;
            }
            while ( v20 < NextFreeEnum );
            Options = v42;
          }
          HIDWORD(v47) = 0;
          DumpEnumsToTMF((__int64)&UserContext);
        }
      }
      else
      {
        dwLowDateTime = GetLastError();
        LastWriteTime.dwLowDateTime = dwLowDateTime;
      }
      if ( TraceFileP )
      {
        fclose(TraceFileP);
        TraceFileP = 0;
      }
      fnUnload();
      if ( !g_fTraceAnnotationFound && g_fVerbose )
      {
        v28 = (const wchar_t *)g_CurrentModuleFileName;
        v29 = _acrt_iob_func(2u);
        fprintf(v29, "%ls : info : WPPFMT No Trace entries found in %ls\n", v28, v10);
      }
    }
    else
    {
      dwLowDateTime = 14;
      LastWriteTime.dwLowDateTime = 14;
      v9 = _acrt_iob_func(2u);
      fprintf(v9, "WPPFMT : error : out of memory calling WideToMbcs\n");
    }
  }
  else
  {
    dwLowDateTime = 1;
    LastWriteTime.dwLowDateTime = 1;
  }
LABEL_42:
  v30 = MofFile;
  if ( MofFile )
  {
    if ( AddLevelDescriptionToMofFile )
    {
      fprintf(
        MofFile,
        "    [Description (\"Levels\") : amended,\n"
        "        ValueDescriptions{\n"
        "            \"Abnormal exit or termination\",\n"
        "            \"Severe errors that need logging\",\n"
        "            \"Warnings such as allocation failure\",\n"
        "            \"Includes non-error cases\",\n"
        "            \"Detailed traces from intermediate steps\" } : amended,\n"
        "         DefineValues{\n"
        "            \"TRACE_LEVEL_FATAL\",\n"
        "            \"TRACE_LEVEL_ERROR\",\n"
        "            \"TRACE_LEVEL_WARNING\"\n"
        "            \"TRACE_LEVEL_INFORMATION\",\n"
        "            \"TRACE_LEVEL_VERBOSE\" },\n"
        "        Values{\n"
        "            \"Fatal\",\n"
        "            \"Error\",\n"
        "            \"Warning\",\n"
        "            \"Information\",\n"
        "            \"Verbose\" },\n"
        "        ValueMap{\n"
        "            \"0x1\",\n"
        "            \"0x2\",\n"
        "            \"0x3\",\n"
        "            \"0x4\",\n"
        "            \"0x5\" },\n"
        "        ValueType(\"index\")\n"
        "    ]\n"
        "    uint32 Level;\n");
      v30 = MofFile;
    }
    fprintf(v30, "};\n");
    fclose(MofFile);
    AddLevelDescriptionToMofFile = 0;
    MofFile = 0;
  }
  if ( PostProcessEnums )
  {
    v31 = *(void ***)&GuidHead.Data1;
    v32 = 0;
    for ( i = NextFreeGuid; v32 < i; ++v32 )
      free(v31[7 * v32]);
    free(v31);
    v34 = NextFreeEnum;
    *(_QWORD *)&GuidHead.Data1 = 0;
    v35 = 0;
    if ( NextFreeEnum )
    {
      do
      {
        v36 = EnumHead;
        v37 = 0;
        v38 = 6LL * v35;
        if ( *(_DWORD *)((char *)EnumHead + v38 * 4 + 16) )
        {
          do
          {
            v39 = *(void **)(*(_QWORD *)&v36[v38 + 2] + 16LL * v37);
            if ( v39 )
              LocalFree(v39);
            ++v37;
          }
          while ( v37 < v36[6 * v35 + 4] );
          v34 = NextFreeEnum;
        }
        free(*(void **)&v36[v38 + 2]);
        free(*(void **)&v36[6 * v35++]);
      }
      while ( v35 < v34 );
      dwLowDateTime = LastWriteTime.dwLowDateTime;
      Options = v42;
    }
    free(EnumHead);
    EnumHead = 0;
    PostProcessEnums = 0;
  }
  if ( gSymHandle )
  {
    SymCleanup(gSymHandle);
    gSymHandle = 0;
  }
  SymSetOptions(Options);
  if ( v43[0] != v44 )
    operator delete(v43[0], (const struct std::nothrow_t *)&std::nothrow);
  return dwLowDateTime;
}

```

## disassembly

```asm
0x14003a0cc  mov     [rsp-8+arg_10], rbx
0x14003a0d1  push    rbp
0x14003a0d2  push    rsi
0x14003a0d3  push    rdi
0x14003a0d4  push    r12
0x14003a0d6  push    r13
0x14003a0d8  push    r14
0x14003a0da  push    r15
0x14003a0dc  lea     rbp, [rsp-17h]
0x14003a0e1  sub     rsp, 0F0h
0x14003a0e8  mov     rax, cs:__security_cookie
0x14003a0ef  xor     rax, rsp
0x14003a0f2  mov     [rbp+47h+var_40], rax
0x14003a0f6  xor     eax, eax
0x14003a0f8  xorps   xmm0, xmm0
0x14003a0fb  mov     [rbp+47h+var_60], rax
0x14003a0ff  xor     edi, edi
0x14003a101  lea     rax, [rbp+47h+var_A0]
0x14003a105  mov     [rbp+47h+var_A0], di
0x14003a109  mov     [rbp+47h+var_B0], rax
0x14003a10d  mov     r14, r8
0x14003a110  lea     rax, [rbp+47h+var_A0]
0x14003a114  mov     cs:?g_fVerbose@@3HA, edi; int g_fVerbose
0x14003a11a  mov     [rbp+47h+var_A8], rax
0x14003a11e  mov     rbx, rdx
0x14003a121  mov     r15, rcx
0x14003a124  mov     cs:?ClassWrittenToMof@@3HA, edi; int ClassWrittenToMof
0x14003a12a  movups  [rbp+47h+var_90], xmm0
0x14003a12e  movups  [rbp+47h+var_80], xmm0
0x14003a132  movups  [rbp+47h+var_70], xmm0
0x14003a136  call    cs:__imp_SymGetOptions
0x14003a13c  mov     r13d, eax
0x14003a13f  mov     [rbp+47h+var_B8], eax
0x14003a142  call    InitializeGlobals
0x14003a147  test    al, al
0x14003a149  jnz     short loc_14003A15B
0x14003a14b  lea     r15d, [rdi+1]
0x14003a14f  mov     r14d, r15d
0x14003a152  mov     [rbp+47h+LastWriteTime.dwLowDateTime], r15d
0x14003a156  jmp     loc_14003A531
0x14003a15b  mov     r8, [rbx+8]
0x14003a15f  test    r8, r8
0x14003a162  jz      short loc_14003A19C
0x14003a164  mov     rdx, [rbx]
0x14003a167  lea     rcx, [rbp+47h+var_B0]
0x14003a16b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14003a170  test    al, al
0x14003a172  jnz     short loc_14003A19C
0x14003a174  mov     r14d, 0Eh
0x14003a17a  mov     [rbp+47h+LastWriteTime.dwLowDateTime], r14d
0x14003a17e  lea     ecx, [r14-0Ch]; Ix
0x14003a182  call    __acrt_iob_func
0x14003a187  mov     rcx, rax; Stream
0x14003a18a  lea     rdx, aWppfmtErrorOut_0; "WPPFMT : error : out of memory calling "...
0x14003a191  call    cs:__imp_fprintf
0x14003a197  jmp     loc_14003A52B
0x14003a19c  mov     r12, [r15]
0x14003a19f  xor     r9d, r9d; lpSecurityAttributes
0x14003a1a2  mov     [rsp+120h+hTemplateFile], rdi; hTemplateFile
0x14003a1a7  mov     rcx, r12; lpFileName
0x14003a1aa  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14003a1b2  xor     r8d, r8d; dwShareMode
0x14003a1b5  mov     edx, 80000000h; dwDesiredAccess
0x14003a1ba  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x14003a1c2  call    cs:__imp_CreateFileW
0x14003a1c8  mov     rsi, rax
0x14003a1cb  test    rax, rax
0x14003a1ce  jz      loc_14003A2AC
0x14003a1d4  xorps   xmm0, xmm0
0x14003a1d7  mov     qword ptr [rbp+47h+LastWriteTime.dwLowDateTime], rdi
0x14003a1db  lea     r9, [rbp+47h+LastWriteTime]; lpLastWriteTime
0x14003a1df  xor     r8d, r8d; lpLastAccessTime
0x14003a1e2  xor     edx, edx; lpCreationTime
0x14003a1e4  mov     rcx, rax; hFile
0x14003a1e7  movups  xmmword ptr [rbp+47h+SystemTime.wYear], xmm0
0x14003a1eb  call    cs:__imp_GetFileTime
0x14003a1f1  test    eax, eax
0x14003a1f3  jz      loc_14003A2A3
0x14003a1f9  lea     rdx, [rbp+47h+SystemTime]; lpSystemTime
0x14003a1fd  lea     rcx, [rbp+47h+LastWriteTime]; lpFileTime
0x14003a201  call    cs:__imp_FileTimeToSystemTime
0x14003a207  test    eax, eax
0x14003a209  jz      loc_14003A2A3
0x14003a20f  mov     r9, r12
0x14003a212  lea     r8, aPdbLs; "// PDB:  %ls\n"
0x14003a219  mov     edx, 204h; BufferCount
0x14003a21e  lea     rcx, ?FirstLine@@3PADA; Buffer
0x14003a225  call    cs:__imp_sprintf_s
0x14003a22b  test    eax, eax
0x14003a22d  jg      short loc_14003A236
0x14003a22f  mov     cs:byte_140083402, 0Ah
0x14003a236  movzx   ecx, [rbp+47h+SystemTime.wMilliseconds]
0x14003a23a  mov     edx, 204h; BufferCount
0x14003a23f  movzx   r8d, [rbp+47h+SystemTime.wSecond]
0x14003a244  mov     rax, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x14003a24b  movzx   r10d, [rbp+47h+SystemTime.wMinute]
0x14003a250  movzx   r11d, [rbp+47h+SystemTime.wHour]
0x14003a255  movzx   ebx, [rbp+47h+SystemTime.wDay]
0x14003a259  movzx   edi, [rbp+47h+SystemTime.wMonth]
0x14003a25d  movzx   r9d, [rbp+47h+SystemTime.wYear]
0x14003a262  mov     [rsp+120h+var_D0], rax
0x14003a267  mov     [rsp+120h+var_D8], ecx
0x14003a26b  lea     rcx, ?SecondLine@@3PADA; Buffer
0x14003a272  mov     [rsp+120h+Options], r8d
0x14003a277  lea     r8, aPdbLastUpdated; "// PDB:  Last Updated :%04d-%02d-%02d:%"...
0x14003a27e  mov     dword ptr [rsp+120h+UserContext], r10d
0x14003a283  mov     dword ptr [rsp+120h+hTemplateFile], r11d
0x14003a288  mov     [rsp+120h+dwFlagsAndAttributes], ebx
0x14003a28c  mov     [rsp+120h+dwCreationDisposition], edi
0x14003a290  call    cs:__imp_sprintf_s
0x14003a296  xor     edi, edi
0x14003a298  test    eax, eax
0x14003a29a  jg      short loc_14003A2A3
0x14003a29c  mov     cs:byte_1400824B2, 0Ah
0x14003a2a3  mov     rcx, rsi; hObject
0x14003a2a6  call    cs:__imp_CloseHandle
0x14003a2ac  movaps  xmm0, xmmword ptr [r15]
0x14003a2b0  lea     rcx, [rbp+47h+SystemTime]
0x14003a2b4  movdqa  xmmword ptr [rbp+47h+SystemTime.wYear], xmm0
0x14003a2b9  mov     cs:?g_fTraceAnnotationFound@@3_NA, dil; bool g_fTraceAnnotationFound
0x14003a2c0  call    fnLoad
0x14003a2c5  mov     esi, 2
0x14003a2ca  test    eax, eax
0x14003a2cc  jz      loc_14003A4CC
0x14003a2d2  mov     r9, [r14+8]
0x14003a2d6  lea     ecx, [rsi+5]
0x14003a2d9  mov     rax, [rbp+47h+var_B0]
0x14003a2dd  mov     r10, [r14]
0x14003a2e0  mov     qword ptr [rbp+47h+var_90+8], r12
0x14003a2e4  mov     qword ptr [rbp+47h+var_80], rax
0x14003a2e8  cmp     r9, rcx
0x14003a2eb  jnz     loc_14003A447
0x14003a2f1  mov     rdx, r10
0x14003a2f4  lea     r8, aGenTmc; "GEN_TMC"
0x14003a2fb  lea     r15d, [rsi-1]
0x14003a2ff  movzx   eax, word ptr [r8]
0x14003a303  cmp     [rdx], ax
0x14003a306  jnz     loc_14003A447
0x14003a30c  add     rdx, rsi
0x14003a30f  add     r8, rsi
0x14003a312  sub     rcx, r15
0x14003a315  jnz     short loc_14003A2FF
0x14003a317  mov     cs:?GenTMCFile@@3HA, r15d; int GenTMCFile
0x14003a31e  mov     rdx, cs:?gBase@@3_KA; BaseOfDll
0x14003a325  lea     rax, [rbp+47h+var_90]
0x14003a329  mov     rcx, cs:?gSymHandle@@3PEAXEA; hProcess
0x14003a330  xor     r9d, r9d; SymTag
0x14003a333  mov     [rsp+120h+Options], esi; Options
0x14003a337  xor     r8d, r8d; Index
0x14003a33a  mov     [rsp+120h+UserContext], rax; UserContext
0x14003a33f  mov     r14d, edi
0x14003a342  lea     rax, cbEnumSymbols
0x14003a349  mov     [rbp+47h+LastWriteTime.dwLowDateTime], edi
0x14003a34c  mov     [rsp+120h+hTemplateFile], rax; EnumSymbolsCallback
0x14003a351  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rdi; Address
0x14003a356  mov     qword ptr [rsp+120h+dwCreationDisposition], rdi; Mask
0x14003a35b  call    cs:__imp_SymSearch
0x14003a361  test    eax, eax
0x14003a363  jnz     short loc_14003A387
0x14003a365  call    cs:__imp_GetLastError
0x14003a36b  mov     ecx, esi; Ix
0x14003a36d  mov     ebx, eax
0x14003a36f  call    __acrt_iob_func
0x14003a374  mov     r8d, ebx
0x14003a377  lea     rdx, aWppfmtError0xX_3; "WPPFMT : error : 0x%X calling SymSearch"...
0x14003a37e  mov     rcx, rax; Stream
0x14003a381  call    cs:__imp_fprintf
0x14003a387  cmp     cs:?PostProcessEnums@@3_NA, dil; bool PostProcessEnums
0x14003a38e  jz      loc_14003A4D8
0x14003a394  cmp     cs:?NextFreeGuid@@3GA, di; ushort NextFreeGuid
0x14003a39b  jbe     loc_14003A4D8
0x14003a3a1  cmp     di, cs:?NextFreeEnum@@3GA; ushort NextFreeEnum
0x14003a3a8  mov     r15d, edi
0x14003a3ab  jnb     loc_14003A436
0x14003a3b1  mov     r13d, 1
0x14003a3b7  mov     r8, cs:?EnumHead@@3PEAUENUMDATA@@EA; ENUMDATA * EnumHead
0x14003a3be  lea     r9, EnumerateEnumsCallback; EnumSymbolsCallback
0x14003a3c5  mov     rdx, cs:?gBase@@3_KA; BaseOfDll
0x14003a3cc  mov     rcx, cs:?gSymHandle@@3PEAXEA; hProcess
0x14003a3d3  movzx   eax, r15w
0x14003a3d7  mov     qword ptr [rsp+120h+dwCreationDisposition], 0; UserContext
0x14003a3e0  lea     rdi, [rax+rax*2]
0x14003a3e4  mov     r8, [r8+rdi*8]; mask
0x14003a3e8  call    cs:__imp_SymEnumTypesByName
0x14003a3ee  test    eax, eax
0x14003a3f0  jnz     short loc_14003A422
0x14003a3f2  mov     rax, cs:?EnumHead@@3PEAUENUMDATA@@EA; ENUMDATA * EnumHead
0x14003a3f9  mov     rdi, [rax+rdi*8]
0x14003a3fd  call    cs:__imp_GetLastError
0x14003a403  mov     ecx, esi; Ix
0x14003a405  mov     ebx, eax
0x14003a407  call    __acrt_iob_func
0x14003a40c  mov     r9, rdi
0x14003a40f  lea     rdx, aWppfmtError0xX_2; "WPPFMT : error : 0x%X calling SymSearch"...
0x14003a416  mov     r8d, ebx
0x14003a419  mov     rcx, rax; Stream
0x14003a41c  call    cs:__imp_fprintf
0x14003a422  add     r15w, r13w
0x14003a426  cmp     r15w, cs:?NextFreeEnum@@3GA; ushort NextFreeEnum
0x14003a42e  jb      short loc_14003A3B7
0x14003a430  mov     r13d, [rbp+47h+var_B8]
0x14003a434  xor     edi, edi
0x14003a436  lea     rcx, [rbp+47h+var_90]
0x14003a43a  mov     dword ptr [rbp+47h+var_70+0Ch], edi
0x14003a43d  call    DumpEnumsToTMF
0x14003a442  jmp     loc_14003A4D8
0x14003a447  mov     ecx, 5
0x14003a44c  cmp     r9, rcx
0x14003a44f  jb      loc_14003A31E
0x14003a455  mov     rdx, r10
0x14003a458  lea     r8, aFile_0; "FILE:"
0x14003a45f  lea     r15d, [rcx-4]
0x14003a463  movzx   eax, word ptr [rdx]
0x14003a466  cmp     [r8], ax
0x14003a46a  jnz     loc_14003A31E
0x14003a470  add     r8, rsi
0x14003a473  add     rdx, rsi
0x14003a476  sub     rcx, r15
0x14003a479  jnz     short loc_14003A463
0x14003a47b  lea     rax, [r9-5]
0x14003a47f  mov     cs:?SingleFile@@3HA, r15d; int SingleFile
0x14003a486  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003a48a  lea     rdx, [r10+0Ah]
0x14003a48e  cmp     rax, r8
0x14003a491  lea     rcx, ?g_SingleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_SingleFileName
0x14003a498  cmovb   r8, rax
0x14003a49c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14003a4a1  test    al, al
0x14003a4a3  jnz     loc_14003A31E
0x14003a4a9  mov     r14d, 0Eh
0x14003a4af  mov     ecx, esi; Ix
0x14003a4b1  mov     [rbp+47h+LastWriteTime.dwLowDateTime], r14d
0x14003a4b5  call    __acrt_iob_func
0x14003a4ba  mov     rcx, rax; Stream
0x14003a4bd  lea     rdx, aWppfmtErrorOut_2; "WPPFMT : error : out of memory\n"
0x14003a4c4  call    cs:__imp_fprintf
0x14003a4ca  jmp     short loc_14003A531
0x14003a4cc  call    cs:__imp_GetLastError
0x14003a4d2  mov     r14d, eax
0x14003a4d5  mov     [rbp+47h+LastWriteTime.dwLowDateTime], eax
0x14003a4d8  mov     rcx, cs:?TraceFileP@@3PEAU_iobuf@@EA; Stream
0x14003a4df  test    rcx, rcx
0x14003a4e2  jz      short loc_14003A4F1
0x14003a4e4  call    cs:__imp_fclose
0x14003a4ea  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, rdi; _iobuf * TraceFileP
0x14003a4f1  call    fnUnload
0x14003a4f6  cmp     cs:?g_fTraceAnnotationFound@@3_NA, dil; bool g_fTraceAnnotationFound
0x14003a4fd  jnz     short loc_14003A52B
0x14003a4ff  cmp     cs:?g_fVerbose@@3HA, edi; int g_fVerbose
0x14003a505  jz      short loc_14003A52B
0x14003a507  mov     rbx, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x14003a50e  mov     ecx, esi; Ix
0x14003a510  call    __acrt_iob_func
0x14003a515  mov     r9, r12
0x14003a518  lea     rdx, aLsInfoWppfmtNo; "%ls : info : WPPFMT No Trace entries fo"...
0x14003a51f  mov     r8, rbx
0x14003a522  mov     rcx, rax; Stream
0x14003a525  call    cs:__imp_fprintf
0x14003a52b  mov     r15d, 1
0x14003a531  mov     rcx, cs:?MofFile@@3PEAU_iobuf@@EA; Stream
0x14003a538  test    rcx, rcx
0x14003a53b  jz      short loc_14003A580
0x14003a53d  cmp     cs:?AddLevelDescriptionToMofFile@@3HA, edi; int AddLevelDescriptionToMofFile
0x14003a543  jz      short loc_14003A559
0x14003a545  lea     rdx, aDescriptionLev; "    [Description (\"Levels\") : amended"...
0x14003a54c  call    cs:__imp_fprintf
0x14003a552  mov     rcx, cs:?MofFile@@3PEAU_iobuf@@EA; Stream
0x14003a559  lea     rdx, asc_14005A1E0; "};\n"
0x14003a560  call    cs:__imp_fprintf
0x14003a566  mov     rcx, cs:?MofFile@@3PEAU_iobuf@@EA; Stream
0x14003a56d  call    cs:__imp_fclose
0x14003a573  mov     cs:?AddLevelDescriptionToMofFile@@3HA, edi; int AddLevelDescriptionToMofFile
0x14003a579  mov     cs:?MofFile@@3PEAU_iobuf@@EA, rdi; _iobuf * MofFile
0x14003a580  cmp     cs:?PostProcessEnums@@3_NA, dil; bool PostProcessEnums
0x14003a587  jz      loc_14003A677
0x14003a58d  mov     rsi, qword ptr cs:?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data1; GUID_POST_PROCESS_DATA * GuidHead ...
0x14003a594  mov     eax, edi
0x14003a596  mov     ebx, edi
0x14003a598  movzx   edi, cs:?NextFreeGuid@@3GA; ushort NextFreeGuid
0x14003a59f  cmp     ax, di
0x14003a5a2  jnb     short loc_14003A5BE
0x14003a5a4  movzx   eax, bx
0x14003a5a7  imul    rcx, rax, 38h ; '8'
0x14003a5ab  mov     rcx, [rcx+rsi]; Block
0x14003a5af  call    cs:__imp_free
0x14003a5b5  add     bx, r15w
0x14003a5b9  cmp     bx, di
0x14003a5bc  jb      short loc_14003A5A4
0x14003a5be  mov     rcx, rsi; Block
0x14003a5c1  call    cs:__imp_free
0x14003a5c7  movzx   r15d, cs:?NextFreeEnum@@3GA; ushort NextFreeEnum
0x14003a5cf  xor     edi, edi
0x14003a5d1  mov     qword ptr cs:?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data1, rdi; GUID_POST_PROCESS_DATA * GuidHead ...
0x14003a5d8  mov     esi, edi
0x14003a5da  cmp     di, r15w
0x14003a5de  jnb     short loc_14003A65C
0x14003a5e0  lea     r14d, [rdi+1]
0x14003a5e4  mov     r13, cs:?EnumHead@@3PEAUENUMDATA@@EA; ENUMDATA * EnumHead
0x14003a5eb  mov     ebx, edi
0x14003a5ed  movzx   eax, si
  ... truncated ...
```
