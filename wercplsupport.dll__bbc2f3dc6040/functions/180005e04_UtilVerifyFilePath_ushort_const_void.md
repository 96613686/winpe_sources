# UtilVerifyFilePath(ushort const *,void *)

- ea: `0x180005e04`
- end: `0x1800065fd`
- name: `?UtilVerifyFilePath@@YAJPEBGPEAX@Z`
- size: `2041`
- prototype: `__int64 __fastcall(unsigned __int16 *, void *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000440c`

## callees

- `0x180001008`
- `0x18000131c`
- `0x180001680`
- `0x180001c3c`
- `0x180002a48`
- `0x180004970`
- `0x180005664`
- `0x180005e04`
- `0x180006754`
- `0x180012028`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18000620e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800062dc`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18000620e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800062dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005ef5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005ef5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005ed4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005ed4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800063bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800063bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000621e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000621e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f3b`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x1800063c9`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x1800063c9`

## pseudocode

```c
__int64 __fastcall UtilVerifyFilePath(unsigned __int16 *a1, void *a2, int a3, int a4)
{
  __int64 *v5; // r14
  signed int FinalPathByHandle; // edi
  HANDLE CurrentProcess; // rax
  void *v8; // rbx
  void **v9; // rax
  signed int LastError; // eax
  signed int IsLowRightsToken; // ebx
  __int16 *v12; // rdx
  __int64 v13; // r15
  __int64 v14; // r8
  char v15; // di
  unsigned int v16; // ebx
  __int64 v17; // rax
  unsigned __int16 v18; // ax
  __int64 v19; // rcx
  unsigned __int16 v20; // cx
  __int64 *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // eax
  DWORD LongPathNameW; // eax
  unsigned __int64 v25; // rdi
  signed int v26; // eax
  unsigned __int64 v27; // rax
  WCHAR *v28; // rax
  WCHAR *v29; // rsi
  __int64 v30; // r8
  __int64 v31; // r8
  int v32; // eax
  __int64 v33; // rsi
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rax
  unsigned __int16 v37; // ax
  __int64 v38; // rcx
  unsigned __int16 v39; // cx
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v42; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpszShortPath; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v44; // [rsp+48h] [rbp-B8h]
  _WORD v45[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h]
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
  __int64 *v60; // [rsp+100h] [rbp+0h]
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

  Block = v48;
  v48[0] = 0;
  v47 = (char *)v48;
  v5 = (__int64 *)a1;
  v45[0] = 0;
  lpszShortPath = v45;
  v44 = v45;
  if ( (unsigned int)dword_18001C008 > 4 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
  {
    hObject = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)a1,
      (unsigned int)&dword_180018A5C,
      a3,
      a4,
      (__int64)&hObject);
  }
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(a2);
  if ( FinalPathByHandle == -2147024891 )
  {
    CurrentProcess = GetCurrentProcess();
    hObject = 0;
    v8 = CurrentProcess;
    v9 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
    if ( OpenProcessToken(v8, 8u, v9) )
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
      if ( (unsigned int)dword_18001C008 > 4 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
        tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, &dword_180018EA4, 0, 0, 2, &v53);
      FinalPathByHandle = 0;
      goto LABEL_106;
    }
    goto LABEL_22;
  }
  if ( FinalPathByHandle < 0 )
  {
LABEL_22:
    if ( (unsigned int)dword_18001C008 <= 2 || (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
      goto LABEL_106;
    LODWORD(hObject) = FinalPathByHandle;
    v12 = word_180018E22;
    goto LABEL_26;
  }
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( *((_WORD *)v5 + v14) );
  if ( !v14 )
  {
    FinalPathByHandle = -2147024809;
    goto LABEL_106;
  }
  if ( Block == v47 || (v15 = 1, *((_WORD *)v47 - 1) != 92) )
    v15 = 0;
  if ( *((_WORD *)v5 + v14 - 1) == 92 && !v15 )
    --v14;
  v16 = 2;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &lpszShortPath,
                           v5,
                           v14) )
  {
    FinalPathByHandle = -2147024882;
    if ( (unsigned int)dword_18001C008 <= 2 || (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
      goto LABEL_106;
    LODWORD(hObject) = -2147024882;
    v12 = (__int16 *)&unk_180018DC0;
LABEL_26:
    v56 = 4;
    p_hObject = &hObject;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, v12, 0, 0, 3, &v53);
    goto LABEL_106;
  }
  if ( v15
    && (unsigned int)dword_18001C008 > 4
    && (qword_18001C018 & 8) != 0
    && (qword_18001C020 & 8) == qword_18001C020 )
  {
    v17 = v44 - lpszShortPath;
    if ( (unsigned __int16)v17 > 0x7FFFu )
      v18 = -2;
    else
      v18 = 2 * v17;
    v49 = (__int64)lpszShortPath;
    v19 = (v47 - (_BYTE *)Block) >> 1;
    v50 = v18;
    if ( (unsigned __int16)v19 > 0x7FFFu )
      v20 = -2;
    else
      v20 = 2 * v19;
    v67 = v18;
    v60 = (__int64 *)&v42;
    v63 = v20;
    hObject = Block;
    v42 = v20;
    v64 = &v50;
    v65 = 2;
    v66 = lpszShortPath;
    v61 = 2;
    v62 = Block;
    if ( v5 )
    {
      v21 = v5;
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)v5 + v22) );
      v23 = 2 * v22 + 2;
    }
    else
    {
      v21 = &qword_180016858;
      v23 = 2;
    }
    v59 = v23;
    v58 = v21;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, byte_1800185F5, 0, 0, 7, szLongPath);
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, szLongPath, 0x105u);
  v25 = LongPathNameW;
  if ( !LongPathNameW )
  {
    v26 = GetLastError();
    FinalPathByHandle = v26;
    if ( v26 > 0 )
      FinalPathByHandle = (unsigned __int16)v26 | 0x80070000;
    if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      LODWORD(hObject) = FinalPathByHandle;
      p_hObject = &hObject;
      v56 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, &word_180018656, 0, 0, 3, &v53);
    }
LABEL_75:
    if ( FinalPathByHandle < 0 )
      goto LABEL_106;
    goto LABEL_81;
  }
  if ( LongPathNameW > 0x105 )
  {
    v27 = 2LL * LongPathNameW;
    if ( !is_mul_ok(v25, 2u) )
      v27 = -1;
    v28 = (WCHAR *)operator new[](v27, (const struct std::nothrow_t *)&std::nothrow);
    v29 = v28;
    if ( v28 )
    {
      if ( (unsigned int)v25 > GetLongPathNameW(lpszShortPath, v28, v25) )
      {
        v30 = -1;
        do
          ++v30;
        while ( v29[v30] );
        FinalPathByHandle = (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                               &lpszShortPath,
                                               v29,
                                               v30) == 0
                          ? 0x8007000E
                          : 0;
      }
      else
      {
        FinalPathByHandle = -2147418113;
      }
      operator delete(v29);
      goto LABEL_75;
    }
LABEL_105:
    FinalPathByHandle = -2147024882;
    goto LABEL_106;
  }
  v31 = -1;
  do
    ++v31;
  while ( szLongPath[v31] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &lpszShortPath,
                           szLongPath,
                           v31) )
    goto LABEL_105;
  FinalPathByHandle = 0;
LABEL_81:
  if ( !lpszShortPath
    || *lpszShortPath != 92
    || lpszShortPath[1] != 92
    || lpszShortPath[2] != 63
    || (v32 = 0, lpszShortPath[3] != 92) )
  {
    v32 = 1;
  }
  v33 = (unsigned int)(4 * v32);
  v34 = v44 - lpszShortPath;
  if ( v34 != ((v47 - (_BYTE *)Block) >> 1) - (unsigned int)v33
    || CompareStringOrdinal(lpszShortPath, v34, (LPCWCH)Block + v33, v34, 1) != 2 )
  {
    if ( (unsigned int)TelGetWerTelemetryMode() == 3 && (unsigned int)dword_18001C008 > 2 )
    {
      v35 = qword_18001C020;
      if ( (qword_18001C018 & 0x200000000008LL) != 0 && (qword_18001C020 & 0x200000000008LL) == qword_18001C020 )
      {
        LODWORD(hObject) = v33;
        v36 = (v47 - (_BYTE *)Block) >> 1;
        if ( (unsigned __int16)v36 > 0x7FFFu )
          v37 = -2;
        else
          v37 = 2 * v36;
        v51 = Block;
        v38 = v44 - lpszShortPath;
        v52 = v37;
        if ( (unsigned __int16)v38 > 0x7FFFu )
          v39 = -2;
        else
          v39 = 2 * v38;
        v69 = v37;
        v62 = &v54;
        v71 = &hObject;
        v65 = v39;
        v53 = lpszShortPath;
        v54 = v39;
        v49 = 0x1000000;
        v72 = 4;
        v66 = &v52;
        v67 = 2;
        v68 = Block;
        v70 = 0;
        v63 = 2;
        v64 = lpszShortPath;
        if ( v5 )
        {
          do
            ++v13;
          while ( *((_WORD *)v5 + v13) );
          v16 = 2 * v13 + 2;
        }
        else
        {
          v5 = &qword_180016858;
        }
        v60 = v5;
        v58 = &v49;
        v61 = v16;
        v59 = 8;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, byte_180018C8D, 0, 0, 9, szLongPath);
      }
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v35);
    FinalPathByHandle = -2147024735;
  }
LABEL_106:
  if ( (unsigned int)dword_18001C008 > 4 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
  {
    LODWORD(hObject) = FinalPathByHandle;
    p_hObject = &hObject;
    v56 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, byte_180018DF5, 0, 0, 3, &v53);
  }
  if ( lpszShortPath != v45 )
    operator delete((void *)lpszShortPath);
  if ( Block != v48 )
    operator delete(Block);
  return (unsigned int)FinalPathByHandle;
}

```

## disassembly

```asm
0x180005e04  mov     [rsp-8+arg_10], rbx
0x180005e09  push    rbp
0x180005e0a  push    rsi
0x180005e0b  push    rdi
0x180005e0c  push    r12
0x180005e0e  push    r13
0x180005e10  push    r14
0x180005e12  push    r15
0x180005e14  lea     rbp, [rsp-1F0h]
0x180005e1c  sub     rsp, 2F0h
0x180005e23  mov     rax, cs:__security_cookie
0x180005e2a  xor     rax, rsp
0x180005e2d  mov     [rbp+220h+var_40], rax
0x180005e34  xor     r12d, r12d
0x180005e37  lea     rax, [rsp+320h+var_2B0]
0x180005e3c  mov     [rsp+320h+Block], rax
0x180005e41  mov     rbx, rdx
0x180005e44  lea     rax, [rsp+320h+var_2B0]
0x180005e49  mov     [rsp+320h+var_2B0], r12w
0x180005e4f  mov     [rsp+320h+var_2B8], rax
0x180005e54  mov     r14, rcx
0x180005e57  lea     rax, [rsp+320h+var_2D0]
0x180005e5c  mov     [rsp+320h+var_2D0], r12w
0x180005e62  mov     [rsp+320h+lpszShortPath], rax
0x180005e67  lea     r13d, [r12+8]
0x180005e6c  lea     rax, [rsp+320h+var_2D0]
0x180005e71  mov     [rsp+320h+var_2D8], rax
0x180005e76  mov     eax, cs:dword_18001C008
0x180005e7c  cmp     eax, 4
0x180005e7f  jbe     short loc_180005EBA
0x180005e81  mov     rdx, cs:qword_18001C020
0x180005e88  mov     rax, cs:qword_18001C018
0x180005e8f  test    r13b, al
0x180005e92  jz      short loc_180005EBA
0x180005e94  mov     rax, rdx
0x180005e97  and     rax, r13
0x180005e9a  cmp     rax, rdx
0x180005e9d  jnz     short loc_180005EBA
0x180005e9f  lea     rax, [rsp+320h+hObject]
0x180005ea4  mov     [rsp+320h+hObject], rcx
0x180005ea9  lea     rdx, dword_180018A5C
0x180005eb0  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x180005eb5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180005eba  lea     rdx, [rsp+320h+Block]
0x180005ebf  mov     rcx, rbx; hFile
0x180005ec2  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180005ec7  mov     edi, eax
0x180005ec9  cmp     eax, 80070005h
0x180005ece  jnz     loc_180005FA0
0x180005ed4  call    cs:__imp_GetCurrentProcess
0x180005eda  lea     rcx, [rsp+320h+hObject]
0x180005edf  mov     [rsp+320h+hObject], r12
0x180005ee4  mov     rbx, rax
0x180005ee7  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180005eec  mov     r8, rax; TokenHandle
0x180005eef  mov     edx, r13d; DesiredAccess
0x180005ef2  mov     rcx, rbx; ProcessHandle
0x180005ef5  call    cs:__imp_OpenProcessToken
0x180005efb  test    eax, eax
0x180005efd  jnz     short loc_180005F20
0x180005eff  call    cs:__imp_GetLastError
0x180005f05  mov     ebx, eax
0x180005f07  test    eax, eax
0x180005f09  jle     short loc_180005F14
0x180005f0b  movzx   ebx, ax
0x180005f0e  or      ebx, 80070000h
0x180005f14  test    ebx, ebx
0x180005f16  mov     eax, 80004005h
0x180005f1b  cmovns  ebx, eax
0x180005f1e  jmp     short loc_180005F2C
0x180005f20  mov     rcx, [rsp+320h+hObject]; TokenHandle
0x180005f25  call    ?UtilIsLowRightsToken@@YAJPEAX@Z; UtilIsLowRightsToken(void *)
0x180005f2a  mov     ebx, eax
0x180005f2c  mov     rcx, [rsp+320h+hObject]; hObject
0x180005f31  lea     rdx, [rcx+1]
0x180005f35  cmp     rdx, 1
0x180005f39  jbe     short loc_180005F41
0x180005f3b  call    cs:__imp_CloseHandle
0x180005f41  test    ebx, ebx
0x180005f43  jnz     short loc_180005FA4
0x180005f45  mov     eax, cs:dword_18001C008
0x180005f4b  cmp     eax, 4
0x180005f4e  jbe     short loc_180005F98
0x180005f50  mov     rcx, cs:qword_18001C020
0x180005f57  mov     rax, cs:qword_18001C018
0x180005f5e  test    r13b, al
0x180005f61  jz      short loc_180005F98
0x180005f63  mov     rax, rcx
0x180005f66  and     rax, r13
0x180005f69  cmp     rax, rcx
0x180005f6c  jnz     short loc_180005F98
0x180005f6e  lea     rax, [rbp+220h+var_280]
0x180005f72  xor     r9d, r9d
0x180005f75  mov     [rsp+320h+var_2F8], rax
0x180005f7a  lea     rdx, dword_180018EA4
0x180005f81  xor     r8d, r8d
0x180005f84  mov     [rsp+320h+bIgnoreCase], 2
0x180005f8c  lea     rcx, dword_18001C008
0x180005f93  call    _tlgWriteTransfer_EventWriteTransfer
0x180005f98  mov     edi, r12d
0x180005f9b  jmp     loc_180006533
0x180005fa0  test    edi, edi
0x180005fa2  jns     short loc_180006021
0x180005fa4  mov     eax, cs:dword_18001C008
0x180005faa  mov     ebx, 2
0x180005faf  cmp     eax, ebx
0x180005fb1  jbe     loc_180006533
0x180005fb7  mov     rcx, cs:qword_18001C020
0x180005fbe  mov     rax, cs:qword_18001C018
0x180005fc5  test    r13b, al
0x180005fc8  jz      loc_180006533
0x180005fce  mov     rax, rcx
0x180005fd1  and     rax, r13
0x180005fd4  cmp     rax, rcx
0x180005fd7  jnz     loc_180006533
0x180005fdd  mov     dword ptr [rsp+320h+hObject], edi
0x180005fe1  lea     rdx, word_180018E22
0x180005fe8  lea     rax, [rsp+320h+hObject]
0x180005fed  mov     [rbp+220h+var_258], 4
0x180005ff5  mov     [rbp+220h+var_260], rax
0x180005ff9  lea     rcx, dword_18001C008
0x180006000  lea     rax, [rbp+220h+var_280]
0x180006004  xor     r9d, r9d
0x180006007  mov     [rsp+320h+var_2F8], rax
0x18000600c  xor     r8d, r8d
0x18000600f  mov     [rsp+320h+bIgnoreCase], 3
0x180006017  call    _tlgWriteTransfer_EventWriteTransfer
0x18000601c  jmp     loc_180006533
0x180006021  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006025  mov     r8, r15
0x180006028  inc     r8
0x18000602b  cmp     [r14+r8*2], r12w
0x180006030  jnz     short loc_180006028
0x180006032  cmp     r8, 1
0x180006036  jnb     short loc_180006042
0x180006038  mov     edi, 80070057h
0x18000603d  jmp     loc_180006533
0x180006042  mov     rax, [rsp+320h+var_2B8]
0x180006047  mov     ecx, 5Ch ; '\'
0x18000604c  cmp     [rsp+320h+Block], rax
0x180006051  jz      short loc_18000605C
0x180006053  mov     dil, 1
0x180006056  cmp     cx, [rax-2]
0x18000605a  jz      short loc_18000605F
0x18000605c  mov     dil, r12b
0x18000605f  cmp     [r14+r8*2-2], cx
0x180006065  jnz     short loc_18000606F
0x180006067  test    dil, dil
0x18000606a  jnz     short loc_18000606F
0x18000606c  dec     r8
0x18000606f  mov     rdx, r14
0x180006072  lea     rcx, [rsp+320h+lpszShortPath]
0x180006077  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000607c  mov     ebx, 2
0x180006081  test    al, al
0x180006083  jnz     short loc_1800060D2
0x180006085  mov     eax, cs:dword_18001C008
0x18000608b  mov     edi, 8007000Eh
0x180006090  cmp     eax, ebx
0x180006092  jbe     loc_180006533
0x180006098  mov     rcx, cs:qword_18001C020
0x18000609f  mov     rax, cs:qword_18001C018
0x1800060a6  test    r13b, al
0x1800060a9  jz      loc_180006533
0x1800060af  mov     rax, rcx
0x1800060b2  and     rax, r13
0x1800060b5  cmp     rax, rcx
0x1800060b8  jnz     loc_180006533
0x1800060be  mov     dword ptr [rsp+320h+hObject], 8007000Eh
0x1800060c6  lea     rdx, unk_180018DC0
0x1800060cd  jmp     loc_180005FE8
0x1800060d2  mov     r10d, 7FFFh
0x1800060d8  mov     r9d, 0FFFEh
0x1800060de  test    dil, dil
0x1800060e1  jz      loc_1800061FD
0x1800060e7  mov     eax, cs:dword_18001C008
0x1800060ed  cmp     eax, 4
0x1800060f0  jbe     loc_1800061FD
0x1800060f6  mov     rcx, cs:qword_18001C020
0x1800060fd  mov     rax, cs:qword_18001C018
0x180006104  test    r13b, al
0x180006107  jz      loc_1800061FD
0x18000610d  mov     rax, rcx
0x180006110  and     rax, r13
0x180006113  cmp     rax, rcx
0x180006116  jnz     loc_1800061FD
0x18000611c  mov     rax, [rsp+320h+var_2D8]
0x180006121  mov     r8, [rsp+320h+lpszShortPath]
0x180006126  sub     rax, r8
0x180006129  sar     rax, 1
0x18000612c  cmp     ax, r10w
0x180006130  ja      short loc_180006137
0x180006132  add     ax, ax
0x180006135  jmp     short loc_18000613B
0x180006137  movzx   eax, r9w
0x18000613b  mov     rcx, [rsp+320h+var_2B8]
0x180006140  mov     rdx, [rsp+320h+Block]
0x180006145  sub     rcx, rdx
0x180006148  mov     [rbp+220h+var_2A0], r8
0x18000614c  sar     rcx, 1
0x18000614f  mov     [rbp+220h+var_298], ax
0x180006153  cmp     cx, r10w
0x180006157  ja      short loc_18000615E
0x180006159  add     cx, cx
0x18000615c  jmp     short loc_180006162
0x18000615e  movzx   ecx, r9w
0x180006162  movzx   eax, ax
0x180006165  lea     r9, [rbp+220h+var_298]
0x180006169  mov     dword ptr [rbp+220h+var_1E8], eax
0x18000616c  lea     rax, [rsp+320h+var_2E8]
0x180006171  mov     [rbp+220h+var_220], rax
0x180006175  movzx   eax, cx
0x180006178  mov     dword ptr [rbp+220h+var_208], eax
0x18000617b  mov     [rsp+320h+hObject], rdx
0x180006180  mov     [rsp+320h+var_2E8], cx
0x180006185  mov     [rbp+220h+var_200], r9
0x180006189  mov     [rbp+220h+var_1F8], rbx
0x18000618d  mov     [rbp+220h+var_1F0], r8
0x180006191  mov     dword ptr [rbp+220h+var_1E8+4], r12d
0x180006195  mov     [rbp+220h+var_218], rbx
0x180006199  mov     [rbp+220h+var_210], rdx
0x18000619d  mov     dword ptr [rbp+220h+var_208+4], r12d
0x1800061a1  test    r14, r14
0x1800061a4  jz      short loc_1800061BF
0x1800061a6  mov     rcx, r14
0x1800061a9  mov     rax, r15
0x1800061ac  inc     rax
0x1800061af  cmp     [r14+rax*2], r12w
0x1800061b4  jnz     short loc_1800061AC
0x1800061b6  lea     eax, ds:2[rax*2]
0x1800061bd  jmp     short loc_1800061C8
0x1800061bf  lea     rcx, qword_180016858
0x1800061c6  mov     eax, ebx
0x1800061c8  mov     dword ptr [rbp+220h+var_228], eax
0x1800061cb  lea     rdx, byte_1800185F5
0x1800061d2  lea     rax, [rbp+220h+szLongPath]
0x1800061d6  mov     [rbp+220h+var_230], rcx
0x1800061da  mov     [rsp+320h+var_2F8], rax
0x1800061df  lea     rcx, dword_18001C008
0x1800061e6  xor     r9d, r9d
0x1800061e9  mov     [rsp+320h+bIgnoreCase], 7
0x1800061f1  xor     r8d, r8d
0x1800061f4  mov     dword ptr [rbp+220h+var_228+4], r12d
0x1800061f8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800061fd  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x180006202  lea     rdx, [rbp+220h+szLongPath]; lpszLongPath
0x180006206  mov     esi, 105h
0x18000620b  mov     r8d, esi; cchBuffer
0x18000620e  call    cs:__imp_GetLongPathNameW
0x180006214  mov     edi, eax
0x180006216  test    eax, eax
0x180006218  jnz     loc_1800062A8
0x18000621e  call    cs:__imp_GetLastError
0x180006224  mov     edi, eax
0x180006226  test    eax, eax
0x180006228  jle     short loc_180006233
0x18000622a  movzx   edi, ax
0x18000622d  or      edi, 80070000h
0x180006233  mov     eax, cs:dword_18001C008
0x180006239  cmp     eax, ebx
0x18000623b  jbe     loc_18000631C
0x180006241  mov     rcx, cs:qword_18001C020
0x180006248  mov     rax, cs:qword_18001C018
0x18000624f  test    r13b, al
0x180006252  jz      loc_18000631C
0x180006258  mov     rax, rcx
0x18000625b  and     rax, r13
0x18000625e  cmp     rax, rcx
0x180006261  jnz     loc_18000631C
0x180006267  lea     rax, [rsp+320h+hObject]
0x18000626c  mov     dword ptr [rsp+320h+hObject], edi
0x180006270  mov     [rbp+220h+var_260], rax
0x180006274  lea     rdx, word_180018656
0x18000627b  lea     rax, [rbp+220h+var_280]
0x18000627f  mov     [rbp+220h+var_258], 4
0x180006287  mov     [rsp+320h+var_2F8], rax
0x18000628c  lea     rcx, dword_18001C008
0x180006293  xor     r9d, r9d
0x180006296  mov     [rsp+320h+bIgnoreCase], 3
0x18000629e  xor     r8d, r8d
0x1800062a1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800062a6  jmp     short loc_18000631C
0x1800062a8  cmp     edi, esi
0x1800062aa  jbe     short loc_180006326
0x1800062ac  mov     rax, rbx
0x1800062af  mul     rdi
0x1800062b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800062b9  cmovb   rax, r15
0x1800062bd  mov     rcx, rax; unsigned __int64
0x1800062c0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800062c5  mov     rsi, rax
0x1800062c8  test    rax, rax
0x1800062cb  jz      loc_18000652E
0x1800062d1  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x1800062d6  mov     r8d, edi; cchBuffer
0x1800062d9  mov     rdx, rax; lpszLongPath
0x1800062dc  call    cs:__imp_GetLongPathNameW
0x1800062e2  cmp     edi, eax
0x1800062e4  ja      short loc_1800062ED
0x1800062e6  mov     edi, 8000FFFFh
  ... truncated ...
```
