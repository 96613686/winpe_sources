# UtilVerifyFilePath(wchar_t const *,void *)

- ea: `0x14000c798`
- end: `0x14000cfa2`
- name: `?UtilVerifyFilePath@@YAJPEB_WPEAX@Z`
- size: `2058`
- prototype: `__int64 __fastcall(wchar_t *, void *, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000a804`
- `0x14000b0d8`

## callees

- `0x140001008`
- `0x14000162c`
- `0x140003200`
- `0x140003224`
- `0x1400046cc`
- `0x14000473c`
- `0x14000b354`
- `0x14000bd00`
- `0x14000c798`
- `0x14000db44`
- `0x14001a504`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000c868`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000c868`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000c889`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000c889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cbb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cbb2`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x14000cd6c`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x14000cd6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c8cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c8cf`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x14000cba2`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x14000cc70`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x14000cba2`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x14000cc70`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000cd5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000cd5e`

## pseudocode

```c
__int64 __fastcall UtilVerifyFilePath(wchar_t *a1, void *a2, int a3, int a4)
{
  int *v5; // r14
  signed int FinalPathByHandle; // edi
  HANDLE CurrentProcess; // rbx
  void **v8; // rax
  signed int LastError; // eax
  signed int IsLowRightsToken; // ebx
  int *v11; // rdx
  __int64 v12; // r15
  __int64 v13; // r8
  char v14; // di
  unsigned int v15; // ebx
  __int64 v16; // rax
  unsigned __int16 v17; // ax
  __int64 v18; // rcx
  unsigned __int16 v19; // cx
  int *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // eax
  DWORD LongPathNameW; // eax
  DWORD v24; // edi
  signed int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  _WORD *v27; // rsi
  __int64 v28; // r8
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rax
  unsigned __int16 v37; // ax
  __int64 v38; // rcx
  unsigned __int16 v39; // cx
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v42; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpszShortPath; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v44; // [rsp+48h] [rbp-B8h]
  _WORD v45[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v46; // [rsp+60h] [rbp-A0h]
  char *v47; // [rsp+68h] [rbp-98h]
  _WORD v48[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v50; // [rsp+88h] [rbp-78h] BYREF
  void *v51; // [rsp+90h] [rbp-70h]
  unsigned __int16 v52; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v53; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v54; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE *p_hObject; // [rsp+C0h] [rbp-40h]
  __int64 v56; // [rsp+C8h] [rbp-38h]
  WCHAR szLongPath[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v58; // [rsp+F0h] [rbp-10h]
  __int64 v59; // [rsp+F8h] [rbp-8h]
  int *v60; // [rsp+100h] [rbp+0h]
  __int64 v61; // [rsp+108h] [rbp+8h]
  _WORD *v62; // [rsp+110h] [rbp+10h]
  __int64 v63; // [rsp+118h] [rbp+18h]
  LPCWSTR v64; // [rsp+120h] [rbp+20h]
  __int64 v65; // [rsp+128h] [rbp+28h]
  LPCWSTR v66; // [rsp+130h] [rbp+30h]
  __int64 v67; // [rsp+138h] [rbp+38h]
  void *v68; // [rsp+140h] [rbp+40h]
  int v69; // [rsp+148h] [rbp+48h]
  int v70; // [rsp+14Ch] [rbp+4Ch]
  HANDLE *v71; // [rsp+150h] [rbp+50h]
  __int64 v72; // [rsp+158h] [rbp+58h]

  v5 = (int *)a1;
  v46 = v48;
  v47 = (char *)v48;
  v48[0] = 0;
  lpszShortPath = v45;
  v44 = v45;
  v45[0] = 0;
  if ( (unsigned int)dword_14002C000 > 4 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
  {
    hObject = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (_DWORD)a1,
      (unsigned int)byte_1400268B3,
      a3,
      a4,
      (__int64)&hObject);
  }
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(a2);
  if ( FinalPathByHandle == -2147024891 )
  {
    CurrentProcess = GetCurrentProcess();
    hObject = 0;
    v8 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
    if ( OpenProcessToken(CurrentProcess, 8u, v8) )
    {
      IsLowRightsToken = UtilIsLowRightsToken(hObject);
    }
    else
    {
      LastError = GetLastError();
      IsLowRightsToken = LastError;
      if ( LastError > 0 )
        IsLowRightsToken = (unsigned __int16)LastError | 0x80070000;
      if ( IsLowRightsToken >= 0 )
        IsLowRightsToken = -2147467259;
    }
    if ( (unsigned __int64)hObject + 1 > 1 )
      CloseHandle(hObject);
    if ( !IsLowRightsToken )
    {
      if ( (unsigned int)dword_14002C000 > 4 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
        tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, word_140026882, 0, 0, 2, &v53);
      FinalPathByHandle = 0;
      goto LABEL_109;
    }
    goto LABEL_22;
  }
  if ( FinalPathByHandle < 0 )
  {
LABEL_22:
    if ( (unsigned int)dword_14002C000 <= 2 || (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
      goto LABEL_109;
    LODWORD(hObject) = FinalPathByHandle;
    v11 = &dword_140026854;
    goto LABEL_26;
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)v5 + v13) );
  if ( !v13 )
  {
    FinalPathByHandle = -2147024809;
    goto LABEL_109;
  }
  if ( v46 == v47 || (v14 = 1, *((_WORD *)v47 - 1) != 92) )
    v14 = 0;
  if ( *((_WORD *)v5 + v13 - 1) == 92 && !v14 )
    --v13;
  v15 = 2;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           v5,
                           v13) )
  {
    FinalPathByHandle = -2147024882;
    if ( (unsigned int)dword_14002C000 <= 2 || (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
      goto LABEL_109;
    LODWORD(hObject) = -2147024882;
    v11 = (int *)&byte_14002681F;
LABEL_26:
    p_hObject = &hObject;
    v56 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, v11, 0, 0, 3, &v53);
    goto LABEL_109;
  }
  if ( v14
    && (unsigned int)dword_14002C000 > 4
    && (qword_14002C010 & 8) != 0
    && (qword_14002C018 & 8) == qword_14002C018 )
  {
    v16 = v44 - lpszShortPath;
    if ( (unsigned __int16)v16 > 0x7FFFu )
      v17 = -2;
    else
      v17 = 2 * v16;
    v49 = (__int64)lpszShortPath;
    v50 = v17;
    v18 = (v47 - (_BYTE *)v46) >> 1;
    if ( (unsigned __int16)v18 > 0x7FFFu )
      v19 = -2;
    else
      v19 = 2 * v18;
    hObject = v46;
    v42 = v19;
    v64 = &v50;
    v65 = 2;
    v66 = lpszShortPath;
    v67 = v17;
    v60 = (int *)&v42;
    v61 = 2;
    v62 = v46;
    v63 = v19;
    if ( v5 )
    {
      v20 = v5;
      v21 = -1;
      do
        ++v21;
      while ( *((_WORD *)v5 + v21) );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v20 = &dword_1400241F4;
      v22 = 2;
    }
    v58 = (__int64 *)v20;
    v59 = v22;
    tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, &word_1400267BE, 0, 0, 7, szLongPath);
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, szLongPath, 0x105u);
  v24 = LongPathNameW;
  if ( !LongPathNameW )
  {
    v25 = GetLastError();
    FinalPathByHandle = v25;
    if ( v25 > 0 )
      FinalPathByHandle = (unsigned __int16)v25 | 0x80070000;
    if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      LODWORD(hObject) = FinalPathByHandle;
      p_hObject = &hObject;
      v56 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, byte_140026785, 0, 0, 3, &v53);
    }
    goto LABEL_78;
  }
  if ( LongPathNameW > 0x105 )
  {
    utl::make_unique_for_overwrite<wchar_t [0],0>(&hObject, LongPathNameW);
    v27 = hObject;
    if ( hObject )
    {
      if ( v24 > GetLongPathNameW(lpszShortPath, (LPWSTR)hObject, v24) )
      {
        if ( v27 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v27[v28] );
        }
        else
        {
          v28 = 0;
        }
        v26 = (const struct std::nothrow_t *)(unsigned int)-((unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                                                                &lpszShortPath,
                                                                                v27,
                                                                                v28) == 0);
        FinalPathByHandle = (unsigned int)v26 & 0x8007000E;
      }
      else
      {
        FinalPathByHandle = -2147418113;
      }
    }
    else
    {
      FinalPathByHandle = -2147024882;
    }
    if ( v27 )
      operator delete(v27, v26);
LABEL_78:
    if ( FinalPathByHandle < 0 )
      goto LABEL_109;
    goto LABEL_84;
  }
  v29 = -1;
  do
    ++v29;
  while ( szLongPath[v29] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           szLongPath,
                           v29) )
  {
    FinalPathByHandle = -2147024882;
    goto LABEL_109;
  }
  FinalPathByHandle = 0;
LABEL_84:
  if ( !lpszShortPath
    || *lpszShortPath != 92
    || lpszShortPath[1] != 92
    || lpszShortPath[2] != 63
    || (v30 = 0, lpszShortPath[3] != 92) )
  {
    v30 = 1;
  }
  v31 = (unsigned int)(4 * v30);
  v32 = v44 - lpszShortPath;
  if ( v32 != ((v47 - (_BYTE *)v46) >> 1) - v31
    || CompareStringOrdinal(lpszShortPath, v32, (LPCWCH)v46 + v31, v32, 1) != 2 )
  {
    if ( (unsigned int)TelGetWerTelemetryMode() == 3 && (unsigned int)dword_14002C000 > 2 )
    {
      v34 = qword_14002C018;
      v33 = 0x200000000008LL;
      if ( (qword_14002C010 & 0x200000000008LL) != 0 && (qword_14002C018 & 0x200000000008LL) == qword_14002C018 )
      {
        LODWORD(hObject) = v31;
        v36 = (v47 - (_BYTE *)v46) >> 1;
        if ( (unsigned __int16)v36 > 0x7FFFu )
          v37 = -2;
        else
          v37 = 2 * v36;
        v51 = v46;
        v52 = v37;
        v38 = v44 - lpszShortPath;
        if ( (unsigned __int16)v38 > 0x7FFFu )
          v39 = -2;
        else
          v39 = 2 * v38;
        v53 = lpszShortPath;
        v54 = v39;
        v49 = 0x1000000;
        v71 = &hObject;
        v72 = 4;
        v66 = &v52;
        v67 = 2;
        v68 = v46;
        v69 = v37;
        v70 = 0;
        v62 = &v54;
        v63 = 2;
        v64 = lpszShortPath;
        v65 = v39;
        if ( v5 )
        {
          do
            ++v12;
          while ( *((_WORD *)v5 + v12) );
          v15 = 2 * v12 + 2;
        }
        else
        {
          v5 = &dword_1400241F4;
        }
        v60 = v5;
        v61 = v15;
        v58 = &v49;
        v59 = 8;
        tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, byte_140026711, 0, 0, 9, szLongPath);
      }
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v34, v33, v35);
    FinalPathByHandle = -2147024735;
  }
LABEL_109:
  if ( (unsigned int)dword_14002C000 > 4 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
  {
    LODWORD(hObject) = FinalPathByHandle;
    p_hObject = &hObject;
    v56 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, &dword_1400266E4, 0, 0, 3, &v53);
  }
  if ( lpszShortPath != v45 )
    operator delete((void *)lpszShortPath, (const struct std::nothrow_t *)&std::nothrow);
  if ( v46 != v48 )
    operator delete(v46, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)FinalPathByHandle;
}

```

## disassembly

```asm
0x14000c798  mov     [rsp-8+arg_10], rbx
0x14000c79d  push    rbp
0x14000c79e  push    rsi
0x14000c79f  push    rdi
0x14000c7a0  push    r12
0x14000c7a2  push    r13
0x14000c7a4  push    r14
0x14000c7a6  push    r15
0x14000c7a8  lea     rbp, [rsp-1F0h]
0x14000c7b0  sub     rsp, 2F0h
0x14000c7b7  mov     rax, cs:__security_cookie
0x14000c7be  xor     rax, rsp
0x14000c7c1  mov     [rbp+220h+var_40], rax
0x14000c7c8  mov     rbx, rdx
0x14000c7cb  mov     r14, rcx
0x14000c7ce  lea     rax, [rsp+320h+var_2B0]
0x14000c7d3  mov     [rsp+320h+var_2C0], rax
0x14000c7d8  lea     rax, [rsp+320h+var_2B0]
0x14000c7dd  mov     [rsp+320h+var_2B8], rax
0x14000c7e2  xor     r12d, r12d
0x14000c7e5  mov     [rsp+320h+var_2B0], r12w
0x14000c7eb  lea     rax, [rsp+320h+var_2D0]
0x14000c7f0  mov     [rsp+320h+lpszShortPath], rax
0x14000c7f5  lea     rax, [rsp+320h+var_2D0]
0x14000c7fa  mov     [rsp+320h+var_2D8], rax
0x14000c7ff  mov     [rsp+320h+var_2D0], r12w
0x14000c805  mov     eax, cs:dword_14002C000
0x14000c80b  lea     r13d, [r12+8]
0x14000c810  cmp     eax, 4
0x14000c813  jbe     short loc_14000C84E
0x14000c815  mov     rdx, cs:qword_14002C018
0x14000c81c  mov     rax, cs:qword_14002C010
0x14000c823  test    r13b, al
0x14000c826  jz      short loc_14000C84E
0x14000c828  mov     rax, rdx
0x14000c82b  and     rax, r13
0x14000c82e  cmp     rax, rdx
0x14000c831  jnz     short loc_14000C84E
0x14000c833  mov     [rsp+320h+hObject], rcx
0x14000c838  lea     rax, [rsp+320h+hObject]
0x14000c83d  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x14000c842  lea     rdx, byte_1400268B3
0x14000c849  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14000c84e  lea     rdx, [rsp+320h+var_2C0]
0x14000c853  mov     rcx, rbx; hFile
0x14000c856  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14000c85b  mov     edi, eax
0x14000c85d  cmp     eax, 80070005h
0x14000c862  jnz     loc_14000C934
0x14000c868  call    cs:__imp_GetCurrentProcess
0x14000c86e  mov     rbx, rax
0x14000c871  mov     [rsp+320h+hObject], r12
0x14000c876  lea     rcx, [rsp+320h+hObject]
0x14000c87b  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x14000c880  mov     r8, rax; TokenHandle
0x14000c883  mov     edx, r13d; DesiredAccess
0x14000c886  mov     rcx, rbx; ProcessHandle
0x14000c889  call    cs:__imp_OpenProcessToken
0x14000c88f  test    eax, eax
0x14000c891  jnz     short loc_14000C8B4
0x14000c893  call    cs:__imp_GetLastError
0x14000c899  mov     ebx, eax
0x14000c89b  test    eax, eax
0x14000c89d  jle     short loc_14000C8A8
0x14000c89f  movzx   ebx, ax
0x14000c8a2  or      ebx, 80070000h
0x14000c8a8  mov     eax, 80004005h
0x14000c8ad  test    ebx, ebx
0x14000c8af  cmovns  ebx, eax
0x14000c8b2  jmp     short loc_14000C8C0
0x14000c8b4  mov     rcx, [rsp+320h+hObject]; TokenHandle
0x14000c8b9  call    ?UtilIsLowRightsToken@@YAJPEAX@Z; UtilIsLowRightsToken(void *)
0x14000c8be  mov     ebx, eax
0x14000c8c0  mov     rcx, [rsp+320h+hObject]; hObject
0x14000c8c5  lea     rdx, [rcx+1]
0x14000c8c9  cmp     rdx, 1
0x14000c8cd  jbe     short loc_14000C8D5
0x14000c8cf  call    cs:__imp_CloseHandle
0x14000c8d5  test    ebx, ebx
0x14000c8d7  jnz     short loc_14000C938
0x14000c8d9  mov     eax, cs:dword_14002C000
0x14000c8df  cmp     eax, 4
0x14000c8e2  jbe     short loc_14000C92C
0x14000c8e4  mov     rcx, cs:qword_14002C018
0x14000c8eb  mov     rax, cs:qword_14002C010
0x14000c8f2  test    r13b, al
0x14000c8f5  jz      short loc_14000C92C
0x14000c8f7  mov     rax, rcx
0x14000c8fa  and     rax, r13
0x14000c8fd  cmp     rax, rcx
0x14000c900  jnz     short loc_14000C92C
0x14000c902  lea     rax, [rbp+220h+var_280]
0x14000c906  mov     [rsp+320h+var_2F8], rax
0x14000c90b  mov     [rsp+320h+bIgnoreCase], 2
0x14000c913  xor     r9d, r9d
0x14000c916  xor     r8d, r8d
0x14000c919  lea     rdx, word_140026882
0x14000c920  lea     rcx, dword_14002C000
0x14000c927  call    _tlgWriteTransfer_EventWriteTransfer
0x14000c92c  mov     edi, r12d
0x14000c92f  jmp     loc_14000CED6
0x14000c934  test    edi, edi
0x14000c936  jns     short loc_14000C9B5
0x14000c938  mov     eax, cs:dword_14002C000
0x14000c93e  mov     ebx, 2
0x14000c943  cmp     eax, ebx
0x14000c945  jbe     loc_14000CED6
0x14000c94b  mov     rcx, cs:qword_14002C018
0x14000c952  mov     rax, cs:qword_14002C010
0x14000c959  test    r13b, al
0x14000c95c  jz      loc_14000CED6
0x14000c962  mov     rax, rcx
0x14000c965  and     rax, r13
0x14000c968  cmp     rax, rcx
0x14000c96b  jnz     loc_14000CED6
0x14000c971  mov     dword ptr [rsp+320h+hObject], edi
0x14000c975  lea     rdx, dword_140026854
0x14000c97c  lea     rax, [rsp+320h+hObject]
0x14000c981  mov     [rbp+220h+var_260], rax
0x14000c985  lea     rax, [rbp+220h+var_280]
0x14000c989  xor     r9d, r9d
0x14000c98c  mov     [rsp+320h+var_2F8], rax
0x14000c991  xor     r8d, r8d
0x14000c994  mov     [rsp+320h+bIgnoreCase], 3
0x14000c99c  mov     [rbp+220h+var_258], 4
0x14000c9a4  lea     rcx, dword_14002C000
0x14000c9ab  call    _tlgWriteTransfer_EventWriteTransfer
0x14000c9b0  jmp     loc_14000CED6
0x14000c9b5  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000c9b9  mov     r8, r15
0x14000c9bc  inc     r8
0x14000c9bf  cmp     [r14+r8*2], r12w
0x14000c9c4  jnz     short loc_14000C9BC
0x14000c9c6  cmp     r8, 1
0x14000c9ca  jnb     short loc_14000C9D6
0x14000c9cc  mov     edi, 80070057h
0x14000c9d1  jmp     loc_14000CED6
0x14000c9d6  mov     ecx, 5Ch ; '\'
0x14000c9db  mov     rax, [rsp+320h+var_2B8]
0x14000c9e0  cmp     [rsp+320h+var_2C0], rax
0x14000c9e5  jz      short loc_14000C9F0
0x14000c9e7  cmp     cx, [rax-2]
0x14000c9eb  mov     dil, 1
0x14000c9ee  jz      short loc_14000C9F3
0x14000c9f0  mov     dil, r12b
0x14000c9f3  cmp     [r14+r8*2-2], cx
0x14000c9f9  jnz     short loc_14000CA03
0x14000c9fb  test    dil, dil
0x14000c9fe  jnz     short loc_14000CA03
0x14000ca00  dec     r8
0x14000ca03  mov     rdx, r14
0x14000ca06  lea     rcx, [rsp+320h+lpszShortPath]
0x14000ca0b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14000ca10  mov     ebx, 2
0x14000ca15  test    al, al
0x14000ca17  jnz     short loc_14000CA66
0x14000ca19  mov     edi, 8007000Eh
0x14000ca1e  mov     eax, cs:dword_14002C000
0x14000ca24  cmp     eax, ebx
0x14000ca26  jbe     loc_14000CED6
0x14000ca2c  mov     rcx, cs:qword_14002C018
0x14000ca33  mov     rax, cs:qword_14002C010
0x14000ca3a  test    r13b, al
0x14000ca3d  jz      loc_14000CED6
0x14000ca43  mov     rax, rcx
0x14000ca46  and     rax, r13
0x14000ca49  cmp     rax, rcx
0x14000ca4c  jnz     loc_14000CED6
0x14000ca52  mov     dword ptr [rsp+320h+hObject], 8007000Eh
0x14000ca5a  lea     rdx, byte_14002681F
0x14000ca61  jmp     loc_14000C97C
0x14000ca66  mov     r10d, 7FFFh
0x14000ca6c  mov     r9d, 0FFFEh
0x14000ca72  test    dil, dil
0x14000ca75  jz      loc_14000CB91
0x14000ca7b  mov     eax, cs:dword_14002C000
0x14000ca81  cmp     eax, 4
0x14000ca84  jbe     loc_14000CB91
0x14000ca8a  mov     rcx, cs:qword_14002C018
0x14000ca91  mov     rax, cs:qword_14002C010
0x14000ca98  test    r13b, al
0x14000ca9b  jz      loc_14000CB91
0x14000caa1  mov     rax, rcx
0x14000caa4  and     rax, r13
0x14000caa7  cmp     rax, rcx
0x14000caaa  jnz     loc_14000CB91
0x14000cab0  mov     rax, [rsp+320h+var_2D8]
0x14000cab5  mov     r8, [rsp+320h+lpszShortPath]
0x14000caba  sub     rax, r8
0x14000cabd  sar     rax, 1
0x14000cac0  cmp     ax, r10w
0x14000cac4  ja      short loc_14000CACB
0x14000cac6  add     ax, ax
0x14000cac9  jmp     short loc_14000CACF
0x14000cacb  movzx   eax, r9w
0x14000cacf  mov     [rbp+220h+var_2A0], r8
0x14000cad3  mov     [rbp+220h+var_298], ax
0x14000cad7  mov     rcx, [rsp+320h+var_2B8]
0x14000cadc  mov     rdx, [rsp+320h+var_2C0]
0x14000cae1  sub     rcx, rdx
0x14000cae4  sar     rcx, 1
0x14000cae7  cmp     cx, r10w
0x14000caeb  ja      short loc_14000CAF2
0x14000caed  add     cx, cx
0x14000caf0  jmp     short loc_14000CAF6
0x14000caf2  movzx   ecx, r9w
0x14000caf6  mov     [rsp+320h+hObject], rdx
0x14000cafb  mov     [rsp+320h+var_2E8], cx
0x14000cb00  lea     r9, [rbp+220h+var_298]
0x14000cb04  mov     [rbp+220h+var_200], r9
0x14000cb08  mov     [rbp+220h+var_1F8], rbx
0x14000cb0c  mov     [rbp+220h+var_1F0], r8
0x14000cb10  movzx   eax, ax
0x14000cb13  mov     dword ptr [rbp+220h+var_1E8], eax
0x14000cb16  mov     dword ptr [rbp+220h+var_1E8+4], r12d
0x14000cb1a  lea     rax, [rsp+320h+var_2E8]
0x14000cb1f  mov     [rbp+220h+var_220], rax
0x14000cb23  mov     [rbp+220h+var_218], rbx
0x14000cb27  mov     [rbp+220h+var_210], rdx
0x14000cb2b  movzx   eax, cx
0x14000cb2e  mov     dword ptr [rbp+220h+var_208], eax
0x14000cb31  mov     dword ptr [rbp+220h+var_208+4], r12d
0x14000cb35  test    r14, r14
0x14000cb38  jz      short loc_14000CB53
0x14000cb3a  mov     rcx, r14
0x14000cb3d  mov     rax, r15
0x14000cb40  inc     rax
0x14000cb43  cmp     [r14+rax*2], r12w
0x14000cb48  jnz     short loc_14000CB40
0x14000cb4a  lea     eax, ds:2[rax*2]
0x14000cb51  jmp     short loc_14000CB5C
0x14000cb53  lea     rcx, dword_1400241F4
0x14000cb5a  mov     eax, ebx
0x14000cb5c  mov     [rbp+220h+var_230], rcx
0x14000cb60  mov     dword ptr [rbp+220h+var_228], eax
0x14000cb63  mov     dword ptr [rbp+220h+var_228+4], r12d
0x14000cb67  lea     rax, [rbp+220h+szLongPath]
0x14000cb6b  mov     [rsp+320h+var_2F8], rax
0x14000cb70  mov     [rsp+320h+bIgnoreCase], 7
0x14000cb78  xor     r9d, r9d
0x14000cb7b  xor     r8d, r8d
0x14000cb7e  lea     rdx, word_1400267BE
0x14000cb85  lea     rcx, dword_14002C000
0x14000cb8c  call    _tlgWriteTransfer_EventWriteTransfer
0x14000cb91  mov     esi, 105h
0x14000cb96  mov     r8d, esi; cchBuffer
0x14000cb99  lea     rdx, [rbp+220h+szLongPath]; lpszLongPath
0x14000cb9d  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x14000cba2  call    cs:__imp_GetLongPathNameW
0x14000cba8  mov     edi, eax
0x14000cbaa  test    eax, eax
0x14000cbac  jnz     loc_14000CC3F
0x14000cbb2  call    cs:__imp_GetLastError
0x14000cbb8  mov     edi, eax
0x14000cbba  test    eax, eax
0x14000cbbc  jle     short loc_14000CBC7
0x14000cbbe  movzx   edi, ax
0x14000cbc1  or      edi, 80070000h
0x14000cbc7  mov     eax, cs:dword_14002C000
0x14000cbcd  cmp     eax, ebx
0x14000cbcf  jbe     loc_14000CCBF
0x14000cbd5  mov     rcx, cs:qword_14002C018
0x14000cbdc  mov     rax, cs:qword_14002C010
0x14000cbe3  test    r13b, al
0x14000cbe6  jz      loc_14000CCBF
0x14000cbec  mov     rax, rcx
0x14000cbef  and     rax, r13
0x14000cbf2  cmp     rax, rcx
0x14000cbf5  jnz     loc_14000CCBF
0x14000cbfb  mov     dword ptr [rsp+320h+hObject], edi
0x14000cbff  lea     rax, [rsp+320h+hObject]
0x14000cc04  mov     [rbp+220h+var_260], rax
0x14000cc08  mov     [rbp+220h+var_258], 4
0x14000cc10  lea     rax, [rbp+220h+var_280]
0x14000cc14  mov     [rsp+320h+var_2F8], rax
0x14000cc19  mov     [rsp+320h+bIgnoreCase], 3
0x14000cc21  xor     r9d, r9d
0x14000cc24  xor     r8d, r8d
0x14000cc27  lea     rdx, byte_140026785
0x14000cc2e  lea     rcx, dword_14002C000
0x14000cc35  call    _tlgWriteTransfer_EventWriteTransfer
0x14000cc3a  jmp     loc_14000CCBF
0x14000cc3f  cmp     edi, esi
0x14000cc41  jbe     loc_14000CCC9
0x14000cc47  mov     rdx, rdi
0x14000cc4a  lea     rcx, [rsp+320h+hObject]
0x14000cc4f  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14000cc54  mov     rsi, [rsp+320h+hObject]
0x14000cc59  test    rsi, rsi
0x14000cc5c  jnz     short loc_14000CC65
0x14000cc5e  mov     edi, 8007000Eh
0x14000cc63  jmp     short loc_14000CCB2
0x14000cc65  mov     r8d, edi; cchBuffer
0x14000cc68  mov     rdx, rsi; lpszLongPath
0x14000cc6b  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x14000cc70  call    cs:__imp_GetLongPathNameW
0x14000cc76  cmp     edi, eax
0x14000cc78  ja      short loc_14000CC81
0x14000cc7a  mov     edi, 8000FFFFh
0x14000cc7f  jmp     short loc_14000CCB2
  ... truncated ...
```
