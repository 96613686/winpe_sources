# cbEnumSymbols

- ea: `0x180048f90`
- end: `0x180049923`
- name: `cbEnumSymbols`
- size: `2451`
- prototype: `BOOL __stdcall(PSYMBOL_INFO pSymInfo, ULONG SymbolSize, PVOID UserContext)`
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180018318`
- `0x180018a3c`
- `0x1800207c0`
- `0x1800212ea`
- `0x180021400`
- `0x180021430`
- `0x18002143c`
- `0x180021490`
- `0x1800215ac`
- `0x180021724`
- `0x180023b05`
- `0x180042240`
- `0x1800431b4`
- `0x1800473bc`
- `0x180047ab4`
- `0x180047bd0`
- `0x180048b8c`
- `0x180048e50`
- `0x180048f90`
- `0x180049fb4`
- `0x180049fc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x1800491f4`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x1800494cb`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x1800495ad`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x1800491f4`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x1800494cb`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x1800495ad`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800492cb`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180049578`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800492cb`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180049578`
- `api-ms-win-crt-private-l1-1-0!_o_fgets` at `0x1800494f6`
- `api-ms-win-crt-private-l1-1-0!_o_fgets` at `0x180049531`
- `api-ms-win-crt-private-l1-1-0!_o_fgets` at `0x1800494f6`
- `api-ms-win-crt-private-l1-1-0!_o_fgets` at `0x180049531`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18004979e`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800497b3`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180049896`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18004979e`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800497b3`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180049896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004920f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004920f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495d2`

## string_xrefs

- `0x1800490d5`: `%ls : warning : WPPFMT Event too complex. This event's decoding information will be omitted from the TMF file: %.80hs %.80hs\n`
- `0x1800491c3`: `%ls : error : WPPFMT Failed to make path %ws\n`
- `0x180049233`: `%ls : warning : WPPFMT Failed Create %ls (0x%0X)\n`
- `0x18004924d`: `#pragma autorecover\n#pragma classflags("forceupdate")\n#pragma namespace("\\\\.\\root\\WMI")\n//\n// WPP Generated File\n`
- `0x1800493e9`: `%ls : error : WPPFMT File + Path\n`
- `0x18004945c`: `%ls : error : WPPFMT Failed to make path %ls\n`
- `0x1800495f7`: `%ls : warning : WPPFMT Failed to open %ls (0x%0X)\n`

## pseudocode

```c
DWORD __fastcall cbEnumSymbols(PSYMBOL_INFO pSymInfo, ULONG SymbolSize, _QWORD *UserContext)
{
  _QWORD *v3; // rdi
  __int64 v5; // rsi
  char v6; // si
  __int64 v7; // r12
  __int64 v8; // rax
  const char *v9; // r15
  const wchar_t *v10; // rbx
  FILE *v11; // rax
  __int64 v13; // rax
  void *v14; // rbx
  FILE *v15; // rax
  FILE *v16; // rax
  DWORD v17; // eax
  const wchar_t *v18; // rdi
  DWORD v19; // ebx
  FILE *v20; // rax
  FILE *v21; // rcx
  unsigned __int64 v22; // rdi
  void *v23; // rbx
  FILE *v24; // rax
  _QWORD *v25; // rbx
  __int64 v26; // rdi
  signed int v27; // eax
  void *v28; // rbx
  FILE *v29; // rax
  const wchar_t *v30; // rbx
  const wchar_t *v31; // rdi
  FILE *v32; // rax
  FILE *v33; // rax
  FILE *v34; // r9
  __int64 v35; // r9
  DWORD LastError; // eax
  const wchar_t *v37; // rdi
  const wchar_t *v38; // rsi
  DWORD v39; // ebx
  FILE *v40; // rax
  const wchar_t *v41; // rbx
  const wchar_t *v42; // rdi
  const wchar_t *v43; // rsi
  FILE *v44; // rax
  void *v45; // rbx
  FILE *v46; // rax
  int v47; // edx
  void *v48; // rbx
  FILE *v49; // rax
  __int64 v50; // rax
  unsigned __int16 v51; // si
  const char *v52; // rbx
  __int64 v53; // rax
  void *v54; // rbx
  FILE *v55; // rax
  __int64 v56; // rdi
  const char *v57; // rdx
  char *v58; // rax
  char *v59; // rcx
  char *v60; // rdx
  char v61; // [rsp+50h] [rbp-B0h]
  __int64 v63; // [rsp+60h] [rbp-A0h]
  char *SubStr; // [rsp+70h] [rbp-90h] BYREF
  const char *v65; // [rsp+78h] [rbp-88h]
  wchar_t *FileName[4]; // [rsp+80h] [rbp-80h] BYREF
  const char *v67; // [rsp+A0h] [rbp-60h]
  wchar_t Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Filename[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v3 = UserContext;
  if ( pSymInfo->Tag == 5 )
  {
    if ( pSymInfo->NameLen >= 0x104 )
      strcpy_s(FuncName, 0x104u, "Unknown");
    else
      o_strncpy_s_0(FuncName, 260, pSymInfo->Name, pSymInfo->NameLen);
    return 1;
  }
  v5 = UserContext[4];
  v63 = v5;
  if ( pSymInfo->Tag != 8 )
    return 1;
  if ( !strcmp_0(pSymInfo->Name, "TMF:") )
  {
    v6 = 0;
    v67 = ".tmf";
  }
  else
  {
    if ( strcmp_0(pSymInfo->Name, "TMC:") || v5 )
      return 1;
    v6 = 1;
    v67 = ".tmc";
  }
  v7 = -1;
  v61 = v6;
  v8 = -1;
  g_fTraceAnnotationFound = 1;
  do
    ++v8;
  while ( pSymInfo->Name[v8] );
  v9 = &pSymInfo->Name[v8 + 1];
  if ( !v6 && pSymInfo->NameLen == pSymInfo->MaxNameLen )
  {
    v10 = (const wchar_t *)g_CurrentModuleFileName;
    v11 = o___acrt_iob_func_0(2u);
    do
      ++v7;
    while ( v9[v7] );
    fprintf(
      v11,
      "%ls : warning : WPPFMT Event too complex. This event's decoding information will be omitted from the TMF file: %.80hs %.80hs\n",
      v10,
      v9,
      &v9[v7 + 1]);
    return 1;
  }
  wsplitpath_s((const wchar_t *)v3[1], 0, 0, 0, 0, Filename, 0x104u, 0, 0);
  if ( MofFile || !v6 )
  {
LABEL_32:
    if ( !strncmp_0(v9, lastguid, 0x24u) )
      goto LABEL_86;
    v21 = TraceFileP;
    *((_BYTE *)v3 + 48) = 1;
    if ( v21 && !SingleFile )
    {
      fclose(v21);
      TraceFileP = 0;
    }
    v22 = -1;
    do
      ++v22;
    while ( v9[v22] );
    if ( v22 < 0x24 )
    {
      if ( !v6 )
      {
        v23 = g_CurrentModuleFileName;
        v24 = o___acrt_iob_func_0(2u);
        fprintf(v24, "%ls : error : WPPFMT GUID buffer too small \n", v23);
        return 0;
      }
      memset_0(lastguid, 0, 0x104u);
      memcpy_0(lastguid, v9, (unsigned int)v22);
    }
    else
    {
      o_strncpy_s_0(lastguid, 260, v9, 36);
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(FileName);
    if ( SingleFile )
    {
      v25 = UserContext;
      v26 = v63;
      v27 = (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               FileName,
                               g_SingleFileName,
                               (qword_18006CDD0 - (__int64)g_SingleFileName) >> 1) == 0
          ? 0x8007000E
          : 0;
    }
    else
    {
      v26 = v63;
      v25 = UserContext;
      if ( v63 )
        goto LABEL_51;
      v27 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
              FileName,
              L"%ls\\%hs%hs",
              UserContext[2],
              lastguid,
              v67);
    }
    if ( v27 < 0 )
    {
      v28 = g_CurrentModuleFileName;
      v29 = o___acrt_iob_func_0(2u);
      fprintf(v29, "%ls : error : WPPFMT File + Path\n", v28);
LABEL_49:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(FileName);
      return 0;
    }
    if ( SingleFile )
    {
LABEL_56:
      if ( !v6 || GenTMCFile )
      {
        swprintf_s(&Fmode, 7u, L"w");
        if ( v26 || SingleFile )
        {
          v34 = TraceFileP;
        }
        else
        {
          v33 = _wfsopen(FileName[0], L"r", 16);
          TraceFileP = v33;
          v34 = v33;
          if ( v33 )
          {
            if ( _o_fgets(g_Line, 516, v33, v33)
              && (strncmp_0(g_Line, FirstLine, 0x204u)
               || _o_fgets(Line2, 516, TraceFileP, v35) && !strncmp_0(Line2, SecondLine, 0x204u)) )
            {
              swprintf_s(&Fmode, 7u, L"a");
            }
            fclose(TraceFileP);
            v34 = 0;
            TraceFileP = 0;
          }
        }
        if ( !v34 && !v26 )
        {
          TraceFileP = _wfsopen(FileName[0], &Fmode, 16);
          v34 = TraceFileP;
          if ( !TraceFileP )
          {
            if ( g_fVerbose )
            {
              LastError = GetLastError();
              v37 = FileName[0];
              v38 = (const wchar_t *)g_CurrentModuleFileName;
              v39 = LastError;
              v40 = o___acrt_iob_func_0(2u);
              fprintf(v40, "%ls : warning : WPPFMT Failed to open %ls (0x%0X)\n", v38, v37, v39);
            }
            goto LABEL_49;
          }
        }
        if ( g_fVerbose )
        {
          v41 = (const wchar_t *)v25[1];
          v42 = FileName[0];
          v43 = (const wchar_t *)g_CurrentModuleFileName;
          v44 = o___acrt_iob_func_0(2u);
          fprintf(v44, "%ls : info : WPPFMT generating %ls for %ls\n", v43, v42, v41);
          v34 = TraceFileP;
          v6 = v61;
          v26 = v63;
        }
        if ( v26 )
        {
          v3 = UserContext;
          if ( (unsigned int)BufferPrintf(UserContext, "%hs\n", v9) )
          {
            if ( g_fVerbose )
            {
              v45 = g_CurrentModuleFileName;
              v46 = o___acrt_iob_func_0(2u);
              fprintf(v46, "%ls : error : WPPFMT Insufficient Buffer\n", v45);
            }
            goto LABEL_49;
          }
          goto LABEL_85;
        }
        v47 = Fmode - 119;
        if ( Fmode == 119 )
          v47 = (unsigned __int16)word_18006A9E2;
        if ( v47 )
        {
          fprintf(v34, "%hs", FirstLine);
          fprintf(TraceFileP, "%hs", SecondLine);
        }
        else
        {
          fprintf(v34, "%hs", FirstLine);
          fprintf(TraceFileP, "%hs", SecondLine);
          fprintf(TraceFileP, "%hs\n", v9);
        }
      }
      v3 = UserContext;
LABEL_85:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(FileName);
LABEL_86:
      if ( !v6 )
      {
        v50 = -1;
        v51 = 0;
        do
          ++v50;
        while ( v9[v50] );
        v52 = &v9[v50 + 1];
        ProcessTmfAnnotation(v3, pSymInfo->Address, v52);
        if ( strstr(v52, "FLAGS") && strstr(v52, "LEVEL") )
          AddLevelDescriptionToMofFile = 1;
        v53 = -1;
        do
          ++v53;
        while ( v52[v53] );
        while ( 1 )
        {
          v52 += v53 + 1;
          if ( !*v52 || v52 >= &pSymInfo->Name[pSymInfo->NameLen] || !strcmp_0(v52, "PUBLIC_TMF:") )
            return 1;
          if ( v63 )
          {
            if ( (unsigned int)BufferPrintf(v3, "%hs\n", v52) )
            {
              if ( g_fVerbose )
              {
                v54 = g_CurrentModuleFileName;
                v55 = o___acrt_iob_func_0(2u);
                fprintf(v55, "%ls : error : WPPFMT Insufficient Buffer\n", v54);
              }
              return 0;
            }
          }
          else
          {
            fprintf(TraceFileP, "%hs\n", v52);
          }
          SubStr = "ItemEnum";
          v65 = "ItemFlagsEnum";
          while ( 1 )
          {
            if ( v51 >= 2u )
            {
              v51 = 0;
              goto LABEL_117;
            }
            v56 = -1;
            v57 = (&SubStr)[v51];
            do
              ++v56;
            while ( v57[v56] );
            v58 = strstr(v52, v57);
            if ( v58 )
            {
              if ( v58[v56] == 40 )
                break;
            }
            ++v51;
          }
          v51 = 0;
          v59 = &v58[v56 + 1];
          v60 = v59;
          if ( *v59 )
          {
            while ( *v60 != 41 )
            {
              if ( !*++v60 )
                goto LABEL_114;
            }
          }
          else
          {
LABEL_114:
            if ( *v60 != 41 )
              goto LABEL_117;
          }
          CheckGuidAndEnum(v59, (unsigned int)((_DWORD)v60 - (_DWORD)v59));
LABEL_117:
          v53 = -1;
          do
            ++v53;
          while ( v52[v53] );
          v3 = UserContext;
        }
      }
      if ( !(unsigned int)AddAnnotationToMofTmc(
                            v9,
                            (unsigned int)pSymInfo + pSymInfo->NameLen - (_DWORD)v9 + 84,
                            Filename) )
      {
        v48 = g_CurrentModuleFileName;
        v49 = o___acrt_iob_func_0(2u);
        fprintf(v49, "%ls : error : WPPFMT Invalid TMC annotation\n", v48);
        return 0;
      }
      return 1;
    }
LABEL_51:
    if ( !TracePathChecked && !v26 )
    {
      SubStr = (char *)FileName[0];
      v65 = (const char *)(FileName[1] - FileName[0]);
      if ( !(unsigned __int8)MakeSureDirectoryPathExistsW(&SubStr) )
      {
        v30 = FileName[0];
        v31 = (const wchar_t *)g_CurrentModuleFileName;
        v32 = o___acrt_iob_func_0(2u);
        fprintf(v32, "%ls : error : WPPFMT Failed to make path %ls\n", v31, v30);
        goto LABEL_49;
      }
      TracePathChecked = 1;
    }
    goto LABEL_56;
  }
  memset_0(Buffer, 0, 0x208u);
  swprintf_s(Buffer, 0x104u, L"%ls\\%ls.mof", v3[2], Filename);
  if ( !TracePathChecked )
  {
    v13 = -1;
    do
      ++v13;
    while ( Buffer[v13] );
    v65 = (const char *)v13;
    SubStr = (char *)Buffer;
    if ( !(unsigned __int8)MakeSureDirectoryPathExistsW(&SubStr) )
    {
      v14 = g_CurrentModuleFileName;
      v15 = o___acrt_iob_func_0(2u);
      fprintf(v15, "%ls : error : WPPFMT Failed to make path %ws\n", v14, Buffer);
      return 0;
    }
    TracePathChecked = 1;
  }
  v16 = _wfsopen(Buffer, L"w", 16);
  MofFile = v16;
  if ( v16 )
  {
    fprintf(
      v16,
      "#pragma autorecover\n"
      "#pragma classflags(\"forceupdate\")\n"
      "#pragma namespace(\"\\\\\\\\.\\\\root\\\\WMI\")\n"
      "//\n"
      "// WPP Generated File\n");
    fprintf(MofFile, "%hs", FirstLine);
    fprintf(MofFile, "%hs//\n", SecondLine);
    goto LABEL_32;
  }
  if ( g_fVerbose )
  {
    v17 = GetLastError();
    v18 = (const wchar_t *)g_CurrentModuleFileName;
    v19 = v17;
    v20 = o___acrt_iob_func_0(2u);
    fprintf(v20, "%ls : warning : WPPFMT Failed Create %ls (0x%0X)\n", v18, Buffer, v19);
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180048f90  mov     [rsp-8+arg_8], rbx
0x180048f95  push    rbp
0x180048f96  push    rsi
0x180048f97  push    rdi
0x180048f98  push    r12
0x180048f9a  push    r13
0x180048f9c  push    r14
0x180048f9e  push    r15
0x180048fa0  lea     rbp, [rsp-3E0h]
0x180048fa8  sub     rsp, 4E0h
0x180048faf  mov     rax, cs:__security_cookie
0x180048fb6  xor     rax, rsp
0x180048fb9  mov     [rbp+410h+var_40], rax
0x180048fc0  cmp     dword ptr [rcx+48h], 5
0x180048fc4  mov     rdi, r8
0x180048fc7  mov     [rsp+510h+var_4B8], r8
0x180048fcc  mov     r13, rcx
0x180048fcf  mov     r15d, 1
0x180048fd5  jnz     short loc_180049014
0x180048fd7  mov     ebx, 104h
0x180048fdc  mov     edx, ebx; SizeInBytes
0x180048fde  cmp     [rcx+4Ch], ebx
0x180048fe1  jnb     short loc_180048FFC
0x180048fe3  mov     r9d, [rcx+4Ch]
0x180048fe7  lea     r8, [rcx+54h]
0x180048feb  lea     rcx, ?FuncName@@3PADA; "Unknown"
0x180048ff2  call    _o_strncpy_s_0
0x180048ff7  jmp     loc_1800498F6
0x180048ffc  lea     r8, aUnknown; "Unknown"
0x180049003  lea     rcx, ?FuncName@@3PADA; "Unknown"
0x18004900a  call    strcpy_s
0x18004900f  jmp     loc_1800498F6
0x180049014  cmp     dword ptr [rcx+48h], 8
0x180049018  mov     rsi, [r8+20h]
0x18004901c  mov     [rsp+510h+var_4B0], rsi
0x180049021  jnz     loc_1800498F6
0x180049027  lea     rdx, aTmf_0; "TMF:"
0x18004902e  add     rcx, 54h ; 'T'; Str1
0x180049032  call    strcmp_0
0x180049037  xor     r14d, r14d
0x18004903a  test    eax, eax
0x18004903c  jnz     short loc_18004904E
0x18004903e  lea     rcx, aTmf; ".tmf"
0x180049045  mov     sil, r14b
0x180049048  mov     [rbp+410h+var_470], rcx
0x18004904c  jmp     short loc_18004907D
0x18004904e  lea     rdx, aTmc_0; "TMC:"
0x180049055  lea     rcx, [r13+54h]; Str1
0x180049059  call    strcmp_0
0x18004905e  test    eax, eax
0x180049060  jnz     loc_1800498F6
0x180049066  test    rsi, rsi
0x180049069  jnz     loc_1800498F6
0x18004906f  lea     rax, aTmc; ".tmc"
0x180049076  mov     sil, r15b
0x180049079  mov     [rbp+410h+var_470], rax
0x18004907d  or      r12, 0FFFFFFFFFFFFFFFFh
0x180049081  mov     [rsp+510h+var_4C0], sil
0x180049086  mov     rax, r12
0x180049089  mov     cs:?g_fTraceAnnotationFound@@3_NA, r15b; bool g_fTraceAnnotationFound
0x180049090  inc     rax
0x180049093  cmp     [r13+rax+54h], r14b
0x180049098  jnz     short loc_180049090
0x18004909a  lea     r15, [r13+55h]
0x18004909e  add     r15, rax
0x1800490a1  test    sil, sil
0x1800490a4  jnz     short loc_1800490F6
0x1800490a6  mov     eax, [r13+50h]
0x1800490aa  cmp     [r13+4Ch], eax
0x1800490ae  jnz     short loc_1800490F6
0x1800490b0  mov     rbx, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x1800490b7  mov     ecx, 2; Ix
0x1800490bc  call    _o___acrt_iob_func_0
0x1800490c1  inc     r12
0x1800490c4  cmp     [r15+r12], r14b
0x1800490c8  jnz     short loc_1800490C1
0x1800490ca  lea     rcx, [r12+1]
0x1800490cf  mov     r9, r15
0x1800490d2  add     rcx, r15
0x1800490d5  lea     rdx, aLsWarningWppfm_0; "%ls : warning : WPPFMT Event too comple"...
0x1800490dc  mov     [rsp+510h+DirCount], rcx
0x1800490e1  mov     r8, rbx
0x1800490e4  mov     rcx, rax; Stream
0x1800490e7  call    fprintf
0x1800490ec  mov     eax, 1
0x1800490f1  jmp     loc_1800498F9
0x1800490f6  mov     rcx, [rdi+8]; FullPath
0x1800490fa  lea     rax, [rbp+410h+var_250]
0x180049101  mov     [rsp+510h+ExtCount], r14; ExtCount
0x180049106  mov     ebx, 104h
0x18004910b  mov     [rsp+510h+Ext], r14; Ext
0x180049110  xor     r9d, r9d; Dir
0x180049113  mov     [rsp+510h+FilenameCount], rbx; FilenameCount
0x180049118  xor     r8d, r8d; DriveCount
0x18004911b  mov     [rsp+510h+Filename], rax; Filename
0x180049120  xor     edx, edx; Drive
0x180049122  mov     [rsp+510h+DirCount], r14; DirCount
0x180049127  call    _wsplitpath_s
0x18004912c  cmp     cs:?MofFile@@3PEAU_iobuf@@EA, r14; _iobuf * MofFile
0x180049133  jnz     loc_180049290
0x180049139  test    sil, sil
0x18004913c  jz      loc_180049290
0x180049142  xor     edx, edx; Val
0x180049144  lea     rcx, [rbp+410h+Buffer]; void *
0x180049148  mov     r8d, 208h; Size
0x18004914e  call    memset_0
0x180049153  mov     r9, [rdi+10h]
0x180049157  lea     rax, [rbp+410h+var_250]
0x18004915e  lea     r8, aLsLsMof; "%ls\\%ls.mof"
0x180049165  mov     [rsp+510h+DirCount], rax
0x18004916a  mov     edx, ebx; BufferCount
0x18004916c  lea     rcx, [rbp+410h+Buffer]; Buffer
0x180049170  call    swprintf_s
0x180049175  cmp     cs:?TracePathChecked@@3HA, r14d; int TracePathChecked
0x18004917c  jnz     short loc_1800491E3
0x18004917e  lea     rcx, [rbp+410h+Buffer]
0x180049182  mov     rax, r12
0x180049185  inc     rax
0x180049188  cmp     [rcx+rax*2], r14w
0x18004918d  jnz     short loc_180049185
0x18004918f  lea     rcx, [rbp+410h+Buffer]
0x180049193  mov     [rsp+510h+var_498], rax
0x180049198  mov     [rsp+510h+SubStr], rcx
0x18004919d  lea     rcx, [rsp+510h+SubStr]
0x1800491a2  call    MakeSureDirectoryPathExistsW
0x1800491a7  test    al, al
0x1800491a9  jnz     short loc_1800491D9
0x1800491ab  mov     rbx, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x1800491b2  mov     ecx, 2; Ix
0x1800491b7  call    _o___acrt_iob_func_0
0x1800491bc  lea     r9, [rbp+410h+Buffer]
0x1800491c0  mov     r8, rbx
0x1800491c3  lea     rdx, aLsErrorWppfmtF; "%ls : error : WPPFMT Failed to make pat"...
0x1800491ca  mov     rcx, rax; Stream
0x1800491cd  call    fprintf
0x1800491d2  xor     eax, eax
0x1800491d4  jmp     loc_1800498F9
0x1800491d9  mov     cs:?TracePathChecked@@3HA, 1; int TracePathChecked
0x1800491e3  mov     r8d, 10h; ShFlag
0x1800491e9  lea     rdx, aW; "w"
0x1800491f0  lea     rcx, [rbp+410h+Buffer]; FileName
0x1800491f4  call    cs:__imp__wfsopen
0x1800491fa  mov     cs:?MofFile@@3PEAU_iobuf@@EA, rax; _iobuf * MofFile
0x180049201  test    rax, rax
0x180049204  jnz     short loc_18004924D
0x180049206  cmp     cs:?g_fVerbose@@3HA, r14d; int g_fVerbose
0x18004920d  jz      short loc_180049242
0x18004920f  call    cs:__imp_GetLastError
0x180049215  mov     rdi, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x18004921c  mov     ecx, 2; Ix
0x180049221  mov     ebx, eax
0x180049223  call    _o___acrt_iob_func_0
0x180049228  lea     r9, [rbp+410h+Buffer]
0x18004922c  mov     dword ptr [rsp+510h+DirCount], ebx
0x180049230  mov     r8, rdi
0x180049233  lea     rdx, aLsWarningWppfm; "%ls : warning : WPPFMT Failed Create %l"...
0x18004923a  mov     rcx, rax; Stream
0x18004923d  call    fprintf
0x180049242  call    cs:__imp_GetLastError
0x180049248  jmp     loc_1800498F9
0x18004924d  lea     rdx, aPragmaAutoreco; "#pragma autorecover\n#pragma classflags"...
0x180049254  mov     rcx, rax; Stream
0x180049257  call    fprintf
0x18004925c  mov     rcx, cs:?MofFile@@3PEAU_iobuf@@EA; Stream
0x180049263  lea     r8, ?FirstLine@@3PADA; char near * FirstLine
0x18004926a  lea     rdx, aHs_1; "%hs"
0x180049271  call    fprintf
0x180049276  mov     rcx, cs:?MofFile@@3PEAU_iobuf@@EA; Stream
0x18004927d  lea     r8, ?SecondLine@@3PADA; char near * SecondLine
0x180049284  lea     rdx, aHs_0; "%hs//\n"
0x18004928b  call    fprintf
0x180049290  mov     r8d, 24h ; '$'; MaxCount
0x180049296  lea     rdx, ?lastguid@@3PADA; Str2
0x18004929d  mov     rcx, r15; Str1
0x1800492a0  call    strncmp_0
0x1800492a5  xor     edx, edx
0x1800492a7  lea     r14d, [rdx+2]
0x1800492ab  test    eax, eax
0x1800492ad  jz      loc_18004972C
0x1800492b3  mov     rcx, cs:?TraceFileP@@3PEAU_iobuf@@EA; Stream
0x1800492ba  mov     byte ptr [rdi+30h], 1
0x1800492be  test    rcx, rcx
0x1800492c1  jz      short loc_1800492DA
0x1800492c3  cmp     cs:?SingleFile@@3HA, edx; int SingleFile
0x1800492c9  jnz     short loc_1800492DA
0x1800492cb  call    cs:__imp_fclose
0x1800492d1  xor     edx, edx
0x1800492d3  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, rdx; _iobuf * TraceFileP
0x1800492da  mov     rdi, r12
0x1800492dd  inc     rdi
0x1800492e0  cmp     [r15+rdi], dl
0x1800492e4  jnz     short loc_1800492DD
0x1800492e6  mov     eax, 24h ; '$'
0x1800492eb  cmp     rdi, rax
0x1800492ee  jb      short loc_180049307
0x1800492f0  mov     r9d, eax
0x1800492f3  lea     rcx, ?lastguid@@3PADA; char near * lastguid
0x1800492fa  mov     r8, r15
0x1800492fd  mov     rdx, rbx
0x180049300  call    _o_strncpy_s_0
0x180049305  jmp     short loc_18004935A
0x180049307  test    sil, sil
0x18004930a  jnz     short loc_180049332
0x18004930c  mov     rbx, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x180049313  mov     ecx, r14d; Ix
0x180049316  call    _o___acrt_iob_func_0
0x18004931b  lea     rdx, aLsErrorWppfmtG; "%ls : error : WPPFMT GUID buffer too sm"...
0x180049322  mov     r8, rbx
0x180049325  mov     rcx, rax; Stream
0x180049328  call    fprintf
0x18004932d  jmp     loc_1800491D2
0x180049332  cmp     edi, eax
0x180049334  lea     rcx, ?lastguid@@3PADA; void *
0x18004933b  mov     r8, rbx; Size
0x18004933e  cmova   edi, eax
0x180049341  xor     edx, edx; Val
0x180049343  call    memset_0
0x180049348  mov     r8d, edi; Size
0x18004934b  lea     rcx, ?lastguid@@3PADA; void *
0x180049352  mov     rdx, r15; Src
0x180049355  call    memcpy_0
0x18004935a  lea     rcx, [rbp+410h+FileName]
0x18004935e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180049363  xor     ecx, ecx
0x180049365  cmp     cs:?SingleFile@@3HA, ecx; int SingleFile
0x18004936b  jz      short loc_1800493A1
0x18004936d  mov     r8, cs:qword_18006CDD0
0x180049374  lea     rcx, [rbp+410h+FileName]
0x180049378  mov     rdx, cs:?g_SingleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_SingleFileName
0x18004937f  sub     r8, rdx
0x180049382  sar     r8, 1
0x180049385  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004938a  mov     rbx, [rsp+510h+var_4B8]
0x18004938f  neg     al
0x180049391  mov     rdi, [rsp+510h+var_4B0]
0x180049396  sbb     eax, eax
0x180049398  not     eax
0x18004939a  and     eax, 8007000Eh
0x18004939f  jmp     short loc_1800493D4
0x1800493a1  mov     rdi, [rsp+510h+var_4B0]
0x1800493a6  mov     rbx, [rsp+510h+var_4B8]
0x1800493ab  test    rdi, rdi
0x1800493ae  jnz     short loc_180049411
0x1800493b0  mov     rax, [rbp+410h+var_470]
0x1800493b4  lea     r9, ?lastguid@@3PADA; char near * lastguid
0x1800493bb  mov     r8, [rbx+10h]
0x1800493bf  lea     rdx, aLsHsHs; "%ls\\%hs%hs"
0x1800493c6  lea     rcx, [rbp+410h+FileName]
0x1800493ca  mov     [rsp+510h+DirCount], rax
0x1800493cf  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800493d4  xor     ecx, ecx
0x1800493d6  test    eax, eax
0x1800493d8  jns     short loc_180049409
0x1800493da  mov     rbx, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x1800493e1  mov     ecx, r14d; Ix
0x1800493e4  call    _o___acrt_iob_func_0
0x1800493e9  lea     rdx, aLsErrorWppfmtF_1; "%ls : error : WPPFMT File + Path\n"
0x1800493f0  mov     r8, rbx
0x1800493f3  mov     rcx, rax; Stream
0x1800493f6  call    fprintf
0x1800493fb  lea     rcx, [rbp+410h+FileName]
0x1800493ff  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180049404  jmp     loc_1800491D2
0x180049409  cmp     cs:?SingleFile@@3HA, ecx; int SingleFile
0x18004940f  jnz     short loc_18004947A
0x180049411  cmp     cs:?TracePathChecked@@3HA, ecx; int TracePathChecked
0x180049417  jnz     short loc_18004947A
0x180049419  test    rdi, rdi
0x18004941c  jnz     short loc_18004947A
0x18004941e  mov     rax, [rbp+410h+FileName]
0x180049422  mov     rcx, [rbp+410h+var_488]
0x180049426  sub     rcx, rax
0x180049429  mov     [rsp+510h+SubStr], rax
0x18004942e  sar     rcx, 1
0x180049431  mov     [rsp+510h+var_498], rcx
0x180049436  lea     rcx, [rsp+510h+SubStr]
0x18004943b  call    MakeSureDirectoryPathExistsW
0x180049440  xor     ecx, ecx
0x180049442  test    al, al
0x180049444  jnz     short loc_180049470
0x180049446  mov     rbx, [rbp+410h+FileName]
0x18004944a  mov     ecx, r14d; Ix
0x18004944d  mov     rdi, cs:?g_CurrentModuleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_CurrentModuleFileName
0x180049454  call    _o___acrt_iob_func_0
0x180049459  mov     r9, rbx
0x18004945c  lea     rdx, aLsErrorWppfmtF_0; "%ls : error : WPPFMT Failed to make pat"...
0x180049463  mov     r8, rdi
0x180049466  mov     rcx, rax; Stream
0x180049469  call    fprintf
0x18004946e  jmp     short loc_1800493FB
0x180049470  mov     cs:?TracePathChecked@@3HA, 1; int TracePathChecked
0x18004947a  test    sil, sil
0x18004947d  jz      short loc_18004948B
0x18004947f  cmp     cs:?GenTMCFile@@3HA, ecx; int GenTMCFile
0x180049485  jz      loc_18004971E
0x18004948b  lea     r8, aW; "w"
0x180049492  mov     edx, 7; BufferCount
0x180049497  lea     rcx, ?Fmode@@3PAGA; Buffer
0x18004949e  call    swprintf_s
0x1800494a3  xor     r8d, r8d
  ... truncated ...
```
