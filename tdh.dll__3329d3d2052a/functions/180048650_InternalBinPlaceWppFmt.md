# InternalBinPlaceWppFmt

- ea: `0x180048650`
- end: `0x180048b84`
- name: `InternalBinPlaceWppFmt`
- size: `1332`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180049cf0`

## callees

- `0x180018318`
- `0x180018a3c`
- `0x1800207c0`
- `0x1800212ea`
- `0x180021724`
- `0x1800218cc`
- `0x180042240`
- `0x180047a74`
- `0x180047ca4`
- `0x180047fdc`
- `0x180048360`
- `0x180048650`
- `0x18004996c`
- `0x180049a08`
- `0x180049c28`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180048a9c`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180048afd`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180048a9c`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180048afd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048b26`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180048b26`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004887b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004887b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004874d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004874d`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180048778`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180048778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800489ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800489ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048837`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004878f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004878f`
- `dbghelp!SymSearch` at `0x18004891b`
- `dbghelp!SymSearch` at `0x18004891b`
- `dbghelp!SymEnumTypesByName` at `0x1800489b9`
- `dbghelp!SymEnumTypesByName` at `0x1800489b9`
- `dbghelp!SymCleanup` at `0x180048b3d`
- `dbghelp!SymCleanup` at `0x180048b3d`
- `dbghelp!SymSetOptions` at `0x180048b4c`
- `dbghelp!SymSetOptions` at `0x180048b4c`
- `dbghelp!SymGetOptions` at `0x1800486c6`
- `dbghelp!SymGetOptions` at `0x1800486c6`

## string_xrefs

- `0x180048806`: `// PDB:  Last Updated :%04d-%02d-%02d:%02d:%02d:%02d:%03d (UTC) [%ls]\n`

## pseudocode

```c
__int64 __fastcall InternalBinPlaceWppFmt(
        struct _SYSTEMTIME *a1,
        _QWORD *a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        void (__fastcall *a6)(_QWORD, _QWORD, __int64))
{
  int v9; // r9d
  DWORD Options; // edi
  DWORD LastError; // esi
  __int64 v12; // r8
  FILE *v13; // rax
  const wchar_t *v14; // rdi
  HANDLE FileW; // rax
  void *v16; // rsi
  int v17; // eax
  unsigned __int64 v18; // r10
  __int64 v19; // r11
  DWORD v20; // ebx
  FILE *v21; // rax
  unsigned __int16 v22; // r15
  const char *v23; // rdi
  DWORD v24; // ebx
  FILE *v25; // rax
  __int64 v26; // r10
  __int64 v27; // r11
  __int64 v28; // r8
  FILE *v29; // rax
  const wchar_t *v30; // rbx
  FILE *v31; // rax
  DWORD v33; // [rsp+60h] [rbp-89h]
  struct _FILETIME LastWriteTime; // [rsp+68h] [rbp-81h] BYREF
  void *v35; // [rsp+70h] [rbp-79h] BYREF
  void (__fastcall *v36)(_QWORD, _QWORD, __int64); // [rsp+78h] [rbp-71h]
  __int128 UserContext; // [rsp+80h] [rbp-69h] BYREF
  __int128 v38; // [rsp+90h] [rbp-59h]
  __int128 v39; // [rsp+A0h] [rbp-49h]
  __int64 v40; // [rsp+B0h] [rbp-39h]
  LPCWSTR v41; // [rsp+B8h] [rbp-31h]
  _QWORD v42[4]; // [rsp+C0h] [rbp-29h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+E0h] [rbp-9h] BYREF

  v36 = a6;
  v35 = 0;
  v40 = 0;
  UserContext = 0;
  v38 = 0;
  v39 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v42);
  g_fVerbose = v9;
  ClassWrittenToMof = 0;
  Options = SymGetOptions();
  v33 = Options;
  if ( !InitializeGlobals() )
  {
    LastError = 1;
    goto LABEL_47;
  }
  v12 = a2[1];
  if ( v12
    && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v42,
                           *a2,
                           v12) )
  {
    LastError = 14;
    v13 = o___acrt_iob_func_0(2u);
    fprintf(v13, "WPPFMT : error : out of memory calling WideToMbcs\n");
    goto LABEL_47;
  }
  v41 = *(LPCWSTR *)&a1->wYear;
  v14 = v41;
  FileW = CreateFileW(v41, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v16 = FileW;
  if ( FileW )
  {
    LastWriteTime = 0;
    SystemTime = 0;
    if ( GetFileTime(FileW, 0, 0, &LastWriteTime) && FileTimeToSystemTime(&LastWriteTime, &SystemTime) )
    {
      if ( sprintf_s(FirstLine, 0x204u, "// PDB:  %ls\n", v14) <= 0 )
        byte_18006CD72 = 10;
      v17 = sprintf_s(
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
              (const wchar_t *)g_CurrentModuleFileName);
      v14 = *(const wchar_t **)&a1->wYear;
      if ( v17 <= 0 )
        byte_18006BE12 = 10;
    }
    CloseHandle(v16);
  }
  SystemTime = *a1;
  g_fTraceAnnotationFound = 0;
  if ( !(unsigned int)fnLoad(&SystemTime) )
  {
    LastError = GetLastError();
LABEL_41:
    if ( TraceFileP )
    {
      fclose(TraceFileP);
      TraceFileP = 0;
    }
    fnUnload();
    if ( !g_fTraceAnnotationFound && g_fVerbose )
    {
      v30 = (const wchar_t *)g_CurrentModuleFileName;
      v31 = o___acrt_iob_func_0(2u);
      fprintf(v31, "%ls : info : WPPFMT No Trace entries found in %ls\n", v30, v14);
    }
    goto LABEL_46;
  }
  if ( !a5 )
  {
LABEL_19:
    v18 = a3[1];
    v19 = *a3;
    *((_QWORD *)&UserContext + 1) = v14;
    *(_QWORD *)&v38 = v42[0];
    if ( v18 == 7 )
    {
      if ( !(unsigned int)utl::_Char16TraitsBase<unsigned short>::compare(v19, L"GEN_TMC") )
      {
        GenTMCFile = 1;
LABEL_22:
        LastError = 0;
        if ( !SymSearch(gSymHandle, gBase, 0, 0, 0, 0, (PSYM_ENUMERATESYMBOLS_CALLBACK)cbEnumSymbols, &UserContext, 2u) )
        {
          v20 = GetLastError();
          v21 = o___acrt_iob_func_0(2u);
          fprintf(v21, "WPPFMT : error : 0x%X calling SymSearch()\n", v20);
        }
        if ( a5 )
        {
          v36(*(_QWORD *)UserContext, HIDWORD(v39), a5);
          LOBYTE(v40) = 0;
        }
        if ( PostProcessEnums && NextFreeGuid )
        {
          v22 = 0;
          if ( NextFreeEnum )
          {
            do
            {
              if ( !SymEnumTypesByName(gSymHandle, gBase, *((PCSTR *)EnumHead + 3 * v22), EnumerateEnumsCallback, 0) )
              {
                v23 = (const char *)*((_QWORD *)EnumHead + 3 * v22);
                v24 = GetLastError();
                v25 = o___acrt_iob_func_0(2u);
                fprintf(v25, "WPPFMT : error : 0x%X calling SymSearch(%hs)\n", v24, v23);
              }
              ++v22;
            }
            while ( v22 < NextFreeEnum );
            v14 = v41;
          }
          HIDWORD(v39) = 0;
          DumpEnumsToTMF(&UserContext);
        }
        goto LABEL_41;
      }
    }
    else if ( v18 < 5 )
    {
      goto LABEL_22;
    }
    if ( !(unsigned int)utl::_Char16TraitsBase<unsigned short>::compare(L"FILE:", v19) )
    {
      SingleFile = 1;
      v28 = -1;
      if ( v26 != 4 )
        v28 = v26 - 5;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               &g_SingleFileName,
                               v27 + 10,
                               v28) )
      {
        LastError = 14;
        v29 = o___acrt_iob_func_0(2u);
        fprintf(v29, "WPPFMT : error : out of memory\n");
        goto LABEL_46;
      }
    }
    goto LABEL_22;
  }
  *((_QWORD *)&v38 + 1) = v36;
  *(_QWORD *)&v39 = a5;
  v35 = malloc(0x10000u);
  if ( v35 )
  {
    DWORD2(v39) = 0x10000;
    *(_QWORD *)&UserContext = &v35;
    goto LABEL_19;
  }
  LastError = 14;
LABEL_46:
  Options = v33;
LABEL_47:
  if ( MofFile )
  {
    AddLevelDescriptionToMof();
    fclose(MofFile);
    AddLevelDescriptionToMofFile = 0;
    MofFile = 0;
  }
  if ( a5 && (_QWORD)UserContext && *(_QWORD *)UserContext )
    free(*(void **)UserContext);
  FreeAllEnumPdbInfo();
  if ( gSymHandle )
  {
    SymCleanup(gSymHandle);
    gSymHandle = 0;
  }
  SymSetOptions(Options);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v42);
  return LastError;
}

```

## disassembly

```asm
0x180048650  mov     [rsp-8+arg_18], rbx
0x180048655  push    rbp
0x180048656  push    rsi
0x180048657  push    rdi
0x180048658  push    r12
0x18004865a  push    r13
0x18004865c  push    r14
0x18004865e  push    r15
0x180048660  lea     rbp, [rsp-17h]
0x180048665  sub     rsp, 100h
0x18004866c  mov     rax, cs:__security_cookie
0x180048673  xor     rax, rsp
0x180048676  mov     [rbp+47h+var_40], rax
0x18004867a  mov     rax, [rbp+47h+arg_28]
0x18004867e  xorps   xmm0, xmm0
0x180048681  mov     r13, [rbp+47h+arg_20]
0x180048685  mov     r14, rcx
0x180048688  mov     [rbp+47h+var_B8], rax
0x18004868c  lea     rcx, [rbp+47h+var_70]
0x180048690  xor     eax, eax
0x180048692  mov     [rbp+47h+var_C0], 0
0x18004869a  mov     [rbp+47h+var_80], rax
0x18004869e  mov     r15, r8
0x1800486a1  mov     rbx, rdx
0x1800486a4  movups  [rbp+47h+var_B0], xmm0
0x1800486a8  movups  [rbp+47h+var_A0], xmm0
0x1800486ac  movups  [rbp+47h+var_90], xmm0
0x1800486b0  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800486b5  mov     cs:?g_fVerbose@@3HA, r9d; int g_fVerbose
0x1800486bc  mov     cs:?ClassWrittenToMof@@3HA, 0; int ClassWrittenToMof
0x1800486c6  call    cs:__imp_SymGetOptions
0x1800486cc  mov     edi, eax
0x1800486ce  mov     [rsp+130h+var_D0], eax
0x1800486d2  call    InitializeGlobals
0x1800486d7  test    al, al
0x1800486d9  jnz     short loc_1800486E7
0x1800486db  mov     esi, 1
0x1800486e0  xor     ebx, ebx
0x1800486e2  jmp     loc_180048AE8
0x1800486e7  mov     r8, [rbx+8]
0x1800486eb  test    r8, r8
0x1800486ee  jz      short loc_180048721
0x1800486f0  mov     rdx, [rbx]
0x1800486f3  lea     rcx, [rbp+47h+var_70]
0x1800486f7  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800486fc  xor     ebx, ebx
0x1800486fe  test    al, al
0x180048700  jnz     short loc_180048723
0x180048702  lea     ecx, [rbx+2]; Ix
0x180048705  lea     esi, [rbx+0Eh]
0x180048708  call    _o___acrt_iob_func_0
0x18004870d  mov     rcx, rax; Stream
0x180048710  lea     rdx, aWppfmtErrorOut_0; "WPPFMT : error : out of memory calling "...
0x180048717  call    fprintf
0x18004871c  jmp     loc_180048AE8
0x180048721  xor     ebx, ebx
0x180048723  mov     rdi, [r14]
0x180048726  xor     r9d, r9d; lpSecurityAttributes
0x180048729  mov     [rsp+130h+hTemplateFile], rbx; hTemplateFile
0x18004872e  mov     rcx, rdi; lpFileName
0x180048731  mov     [rsp+130h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180048739  xor     r8d, r8d; dwShareMode
0x18004873c  mov     edx, 80000000h; dwDesiredAccess
0x180048741  mov     [rbp+47h+var_78], rdi
0x180048745  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x18004874d  call    cs:__imp_CreateFileW
0x180048753  mov     rsi, rax
0x180048756  test    rax, rax
0x180048759  jz      loc_18004883D
0x18004875f  xorps   xmm0, xmm0
0x180048762  mov     qword ptr [rsp+130h+LastWriteTime.dwLowDateTime], rbx
0x180048767  lea     r9, [rsp+130h+LastWriteTime]; lpLastWriteTime
0x18004876c  xor     r8d, r8d; lpLastAccessTime
0x18004876f  xor     edx, edx; lpCreationTime
0x180048771  mov     rcx, rax; hFile
0x180048774  movups  xmmword ptr [rbp+47h+SystemTime.wYear], xmm0
0x180048778  call    cs:__imp_GetFileTime
0x18004877e  test    eax, eax
0x180048780  jz      loc_180048834
0x180048786  lea     rdx, [rbp+47h+SystemTime]; lpSystemTime
0x18004878a  lea     rcx, [rsp+130h+LastWriteTime]; lpFileTime
0x18004878f  call    cs:__imp_FileTimeToSystemTime
0x180048795  test    eax, eax
0x180048797  jz      loc_180048834
0x18004879d  mov     r12d, 204h
0x1800487a3  lea     r8, aPdbLs; "// PDB:  %ls\n"
0x1800487aa  mov     edx, r12d; BufferCount
0x1800487ad  lea     rcx, ?FirstLine@@3PADA; Buffer
0x1800487b4  mov     r9, rdi
0x1800487b7  call    sprintf_s
0x1800487bc  test    eax, eax
0x1800487be  jg      short loc_1800487C7
0x1800487c0  mov     cs:byte_18006CD72, 0Ah
0x1800487c7  movzx   ecx, [rbp+47h+SystemTime.wMilliseconds]
0x1800487cb  mov     rdx, r12; BufferCount
0x1800487ce  movzx   r8d, [rbp+47h+SystemTime.wSecond]
0x1800487d3  mov     rax, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x1800487da  movzx   r10d, [rbp+47h+SystemTime.wMinute]
0x1800487df  movzx   r11d, [rbp+47h+SystemTime.wHour]
0x1800487e4  movzx   ebx, [rbp+47h+SystemTime.wDay]
0x1800487e8  movzx   edi, [rbp+47h+SystemTime.wMonth]
0x1800487ec  movzx   r9d, [rbp+47h+SystemTime.wYear]
0x1800487f1  mov     [rsp+130h+var_E0], rax
0x1800487f6  mov     [rsp+130h+var_E8], ecx
0x1800487fa  lea     rcx, ?SecondLine@@3PADA; Buffer
0x180048801  mov     [rsp+130h+Options], r8d
0x180048806  lea     r8, aPdbLastUpdated; "// PDB:  Last Updated :%04d-%02d-%02d:%"...
0x18004880d  mov     dword ptr [rsp+130h+UserContext], r10d
0x180048812  mov     dword ptr [rsp+130h+hTemplateFile], r11d
0x180048817  mov     [rsp+130h+dwFlagsAndAttributes], ebx
0x18004881b  mov     [rsp+130h+dwCreationDisposition], edi
0x18004881f  call    sprintf_s
0x180048824  mov     rdi, [r14]
0x180048827  xor     ebx, ebx
0x180048829  test    eax, eax
0x18004882b  jg      short loc_180048834
0x18004882d  mov     cs:byte_18006BE12, 0Ah
0x180048834  mov     rcx, rsi; hObject
0x180048837  call    cs:__imp_CloseHandle
0x18004883d  movaps  xmm0, xmmword ptr [r14]
0x180048841  lea     rcx, [rbp+47h+SystemTime]
0x180048845  movdqa  xmmword ptr [rbp+47h+SystemTime.wYear], xmm0
0x18004884a  mov     cs:?g_fTraceAnnotationFound@@3_NA, bl; bool g_fTraceAnnotationFound
0x180048850  call    fnLoad
0x180048855  mov     r12d, 2
0x18004885b  test    eax, eax
0x18004885d  jz      loc_180048A88
0x180048863  test    r13, r13
0x180048866  jz      short loc_18004889D
0x180048868  mov     rax, [rbp+47h+var_B8]
0x18004886c  mov     esi, 10000h
0x180048871  mov     ecx, esi; Size
0x180048873  mov     qword ptr [rbp+47h+var_A0+8], rax
0x180048877  mov     qword ptr [rbp+47h+var_90], r13
0x18004887b  call    cs:__imp_malloc
0x180048881  mov     [rbp+47h+var_C0], rax
0x180048885  test    rax, rax
0x180048888  jnz     short loc_180048892
0x18004888a  lea     esi, [rax+0Eh]
0x18004888d  jmp     loc_180048AE4
0x180048892  lea     rax, [rbp+47h+var_C0]
0x180048896  mov     dword ptr [rbp+47h+var_90+8], esi
0x180048899  mov     qword ptr [rbp+47h+var_B0], rax
0x18004889d  mov     r10, [r15+8]
0x1800488a1  mov     r14d, 1
0x1800488a7  mov     rax, [rbp+47h+var_70]
0x1800488ab  mov     r11, [r15]
0x1800488ae  mov     qword ptr [rbp+47h+var_B0+8], rdi
0x1800488b2  lea     r8d, [r14+6]
0x1800488b6  mov     qword ptr [rbp+47h+var_A0], rax
0x1800488ba  cmp     r10, r8
0x1800488bd  jnz     loc_180048A15
0x1800488c3  lea     rdx, aGenTmc; "GEN_TMC"
0x1800488ca  mov     rcx, r11
0x1800488cd  call    ?compare@?$_Char16TraitsBase@G@utl@@SAHPEBG0_K@Z; utl::_Char16TraitsBase<ushort>::compare(ushort const *,ushort const *,unsigned __int64)
0x1800488d2  test    eax, eax
0x1800488d4  jnz     loc_180048A1F
0x1800488da  mov     cs:?GenTMCFile@@3HA, r14d; int GenTMCFile
0x1800488e1  mov     rdx, cs:?gBase@@3_KA; BaseOfDll
0x1800488e8  lea     rax, [rbp+47h+var_B0]
0x1800488ec  mov     rcx, cs:?gSymHandle@@3PEAXEA; hProcess
0x1800488f3  xor     r9d, r9d; SymTag
0x1800488f6  mov     [rsp+130h+Options], r12d; Options
0x1800488fb  xor     r8d, r8d; Index
0x1800488fe  mov     [rsp+130h+UserContext], rax; UserContext
0x180048903  mov     esi, ebx
0x180048905  lea     rax, cbEnumSymbols
0x18004890c  mov     [rsp+130h+hTemplateFile], rax; EnumSymbolsCallback
0x180048911  mov     qword ptr [rsp+130h+dwFlagsAndAttributes], rbx; Address
0x180048916  mov     qword ptr [rsp+130h+dwCreationDisposition], rbx; Mask
0x18004891b  call    cs:__imp_SymSearch
0x180048921  test    eax, eax
0x180048923  jnz     short loc_180048949
0x180048925  call    cs:__imp_GetLastError
0x18004892b  mov     ecx, r12d; Ix
0x18004892e  mov     ebx, eax
0x180048930  call    _o___acrt_iob_func_0
0x180048935  mov     r8d, ebx
0x180048938  lea     rdx, aWppfmtError0xX_3; "WPPFMT : error : 0x%X calling SymSearch"...
0x18004893f  mov     rcx, rax; Stream
0x180048942  call    fprintf
0x180048947  xor     ebx, ebx
0x180048949  test    r13, r13
0x18004894c  jz      short loc_180048967
0x18004894e  mov     rcx, qword ptr [rbp+47h+var_B0]
0x180048952  mov     r8, r13
0x180048955  mov     edx, dword ptr [rbp+47h+var_90+0Ch]
0x180048958  mov     rax, [rbp+47h+var_B8]
0x18004895c  mov     rcx, [rcx]
0x18004895f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048964  mov     byte ptr [rbp+47h+var_80], bl
0x180048967  cmp     cs:?PostProcessEnums@@3_NA, bl; bool PostProcessEnums
0x18004896d  jz      loc_180048A90
0x180048973  cmp     cs:?NextFreeGuid@@3GA, bx; ushort NextFreeGuid
0x18004897a  jbe     loc_180048A90
0x180048980  cmp     bx, cs:?NextFreeEnum@@3GA; ushort NextFreeEnum
0x180048987  mov     r15d, ebx
0x18004898a  jnb     short loc_180048A07
0x18004898c  mov     r8, cs:?EnumHead@@3PEAUENUMDATA@@EA; ENUMDATA * EnumHead
0x180048993  lea     r9, EnumerateEnumsCallback; EnumSymbolsCallback
0x18004899a  mov     rdx, cs:?gBase@@3_KA; BaseOfDll
0x1800489a1  mov     rcx, cs:?gSymHandle@@3PEAXEA; hProcess
0x1800489a8  movzx   eax, r15w
0x1800489ac  mov     qword ptr [rsp+130h+dwCreationDisposition], rbx; UserContext
0x1800489b1  lea     rdi, [rax+rax*2]
0x1800489b5  mov     r8, [r8+rdi*8]; mask
0x1800489b9  call    cs:__imp_SymEnumTypesByName
0x1800489bf  test    eax, eax
0x1800489c1  jnz     short loc_1800489F5
0x1800489c3  mov     rax, cs:?EnumHead@@3PEAUENUMDATA@@EA; ENUMDATA * EnumHead
0x1800489ca  mov     rdi, [rax+rdi*8]
0x1800489ce  call    cs:__imp_GetLastError
0x1800489d4  mov     ecx, r12d; Ix
0x1800489d7  mov     ebx, eax
0x1800489d9  call    _o___acrt_iob_func_0
0x1800489de  mov     r9, rdi
0x1800489e1  lea     rdx, aWppfmtError0xX_2; "WPPFMT : error : 0x%X calling SymSearch"...
0x1800489e8  mov     r8d, ebx
0x1800489eb  mov     rcx, rax; Stream
0x1800489ee  call    fprintf
0x1800489f3  xor     ebx, ebx
0x1800489f5  add     r15w, r14w
0x1800489f9  cmp     r15w, cs:?NextFreeEnum@@3GA; ushort NextFreeEnum
0x180048a01  jb      short loc_18004898C
0x180048a03  mov     rdi, [rbp+47h+var_78]
0x180048a07  lea     rcx, [rbp+47h+var_B0]
0x180048a0b  mov     dword ptr [rbp+47h+var_90+0Ch], ebx
0x180048a0e  call    DumpEnumsToTMF
0x180048a13  jmp     short loc_180048A90
0x180048a15  cmp     r10, 5
0x180048a19  jb      loc_1800488E1
0x180048a1f  mov     r8d, 5
0x180048a25  lea     rcx, aFile; "FILE:"
0x180048a2c  mov     rdx, r11
0x180048a2f  call    ?compare@?$_Char16TraitsBase@G@utl@@SAHPEBG0_K@Z; utl::_Char16TraitsBase<ushort>::compare(ushort const *,ushort const *,unsigned __int64)
0x180048a34  test    eax, eax
0x180048a36  jnz     loc_1800488E1
0x180048a3c  lea     rax, [r10-5]
0x180048a40  mov     cs:?SingleFile@@3HA, r14d; int SingleFile
0x180048a47  or      r8, 0FFFFFFFFFFFFFFFFh
0x180048a4b  lea     rdx, [r11+0Ah]
0x180048a4f  cmp     rax, r8
0x180048a52  lea     rcx, ?g_SingleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_SingleFileName
0x180048a59  cmovb   r8, rax
0x180048a5d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180048a62  test    al, al
0x180048a64  jnz     loc_1800488E1
0x180048a6a  mov     ecx, r12d; Ix
0x180048a6d  mov     esi, 0Eh
0x180048a72  call    _o___acrt_iob_func_0
0x180048a77  mov     rcx, rax; Stream
0x180048a7a  lea     rdx, aWppfmtErrorOut_2; "WPPFMT : error : out of memory\n"
0x180048a81  call    fprintf
0x180048a86  jmp     short loc_180048AE4
0x180048a88  call    cs:__imp_GetLastError
0x180048a8e  mov     esi, eax
0x180048a90  mov     rcx, cs:?TraceFileP@@3PEAU_iobuf@@EA; Stream
0x180048a97  test    rcx, rcx
0x180048a9a  jz      short loc_180048AA9
0x180048a9c  call    cs:__imp_fclose
0x180048aa2  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, rbx; _iobuf * TraceFileP
0x180048aa9  call    fnUnload
0x180048aae  cmp     cs:?g_fTraceAnnotationFound@@3_NA, bl; bool g_fTraceAnnotationFound
0x180048ab4  jnz     short loc_180048AE4
0x180048ab6  cmp     cs:?g_fVerbose@@3HA, ebx; int g_fVerbose
0x180048abc  jz      short loc_180048AE4
0x180048abe  mov     rbx, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x180048ac5  mov     ecx, r12d; Ix
0x180048ac8  call    _o___acrt_iob_func_0
0x180048acd  mov     r9, rdi
0x180048ad0  lea     rdx, aLsInfoWppfmtNo; "%ls : info : WPPFMT No Trace entries fo"...
0x180048ad7  mov     r8, rbx
0x180048ada  mov     rcx, rax; Stream
0x180048add  call    fprintf
0x180048ae2  xor     ebx, ebx
0x180048ae4  mov     edi, [rsp+130h+var_D0]
0x180048ae8  cmp     cs:?MofFile@@3PEAU_iobuf@@EA, rbx; _iobuf * MofFile
0x180048aef  jz      short loc_180048B10
0x180048af1  call    AddLevelDescriptionToMof
0x180048af6  mov     rcx, cs:?MofFile@@3PEAU_iobuf@@EA; Stream
0x180048afd  call    cs:__imp_fclose
0x180048b03  mov     cs:?AddLevelDescriptionToMofFile@@3HA, ebx; int AddLevelDescriptionToMofFile
0x180048b09  mov     cs:?MofFile@@3PEAU_iobuf@@EA, rbx; _iobuf * MofFile
0x180048b10  test    r13, r13
0x180048b13  jz      short loc_180048B2C
0x180048b15  mov     rax, qword ptr [rbp+47h+var_B0]
0x180048b19  test    rax, rax
0x180048b1c  jz      short loc_180048B2C
0x180048b1e  mov     rcx, [rax]; Block
0x180048b21  test    rcx, rcx
0x180048b24  jz      short loc_180048B2C
0x180048b26  call    cs:__imp_free
0x180048b2c  call    FreeAllEnumPdbInfo
0x180048b31  mov     rcx, cs:?gSymHandle@@3PEAXEA; hProcess
0x180048b38  test    rcx, rcx
0x180048b3b  jz      short loc_180048B4A
0x180048b3d  call    cs:__imp_SymCleanup
0x180048b43  mov     cs:?gSymHandle@@3PEAXEA, rbx; void * gSymHandle
0x180048b4a  mov     ecx, edi; SymOptions
0x180048b4c  call    cs:__imp_SymSetOptions
  ... truncated ...
```
