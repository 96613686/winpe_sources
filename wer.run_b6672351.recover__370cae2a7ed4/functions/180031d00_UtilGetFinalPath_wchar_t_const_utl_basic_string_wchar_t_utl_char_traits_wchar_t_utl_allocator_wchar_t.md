# UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x180031d00`
- end: `0x180031fec`
- name: `?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `748`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `5`
- callee_count: `13`
- tags: `file_ops, reparse_path`

## callers

- `0x18000a9f0`
- `0x18001d718`
- `0x180032790`
- `0x180046150`
- `0x18009a5dc`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x1800172c0`
- `0x18001b044`
- `0x18001c368`
- `0x1800235c8`
- `0x180023d28`
- `0x18002850c`
- `0x18002e5a4`
- `0x180031cd0`
- `0x180031d00`
- `0x180031ff4`
- `0x18004cab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180031f4c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180031f73`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180031f4c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180031f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031db5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031db5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031d90`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031d90`

## pseudocode

```c
__int64 __fastcall UtilGetFinalPath(_werDetail *lpFileName, _werDetail **a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // edi
  HANDLE FileW; // rax
  DWORD LastError; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  WCHAR v14; // r14
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rdx
  _werDetail *v19; // rcx
  __int64 v20; // r14
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  _werDetail *v29; // rcx
  _werDetail *v31; // [rsp+80h] [rbp+40h] BYREF
  HANDLE hFile; // [rsp+90h] [rbp+50h] BYREF
  LPCWSTR v33; // [rsp+98h] [rbp+58h] BYREF

  hFile = 0;
  if ( !lpFileName )
    goto LABEL_29;
  if ( (unsigned int)dword_1800DE000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    v31 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v4,
      (unsigned int)&dword_1800CC37C,
      v5,
      v6,
      (__int64)&v31);
  }
  v7 = 1;
  FileW = CreateFileW((LPCWSTR)lpFileName, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  if ( (unsigned __int64)hFile + 1 <= 1 )
  {
    LastError = GetLastError();
    ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      LODWORD(v31) = v11;
      v33 = (LPCWSTR)lpFileName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&word_1800CC3AE,
        v11,
        v12,
        (__int64)&v33,
        (__int64)&v31);
    }
    goto LABEL_29;
  }
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)lpFileName + v13) );
  v14 = *((_WORD *)lpFileName + v13 - 1);
  if ( (int)_werDetail::UtilGetFinalPathByHandle(hFile, (__int64)a2) < 0 )
  {
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      LODWORD(v31) = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v15,
        (unsigned int)word_1800CC3EA,
        v16,
        v17,
        (__int64)&v31);
    }
    goto LABEL_29;
  }
  v18 = 92;
  if ( v14 == 92
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(a2)
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           a2,
                           v18) )
  {
    v19 = *a2;
    a2[1] = *a2;
    *(_WORD *)v19 = 0;
LABEL_29:
    v7 = 0;
    goto LABEL_30;
  }
  v20 = 0;
  if ( (unsigned int)_werDetail::HasExtendedLengthPathPrefix(*a2, (const wchar_t *)v18) )
  {
    if ( (unsigned int)dword_1800DE000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      v31 = *a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v21,
        (unsigned int)byte_1800CC415,
        v22,
        v23,
        (__int64)&v31);
    }
    v20 = 4;
  }
  if ( (unsigned int)dword_1800DE000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    v31 = *a2;
    v33 = (LPCWSTR)lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      v24,
      (unsigned int)byte_1800CC453,
      v25,
      v26,
      (__int64)&v33,
      (__int64)&v31);
  }
  if ( !(unsigned int)_o__wcsnicmp(lpFileName, *a2, (a2[1] - *a2) >> 1)
    || !(unsigned int)_o__wcsnicmp(lpFileName, (char *)*a2 + 2 * v20, ((a2[1] - *a2) >> 1) - v20) )
  {
    goto LABEL_29;
  }
LABEL_30:
  if ( (unsigned int)dword_1800DE000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    v29 = *a2;
    LODWORD(v31) = v7;
    v33 = (LPCWSTR)v29;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      (_DWORD)v29,
      (unsigned int)&unk_1800CC498,
      v27,
      v28,
      (__int64)&v33,
      (__int64)&v31);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return v7;
}

```

## disassembly

```asm
0x180031d00  mov     [rsp-38h+arg_8], rbx
0x180031d05  push    rbp
0x180031d06  push    rsi
0x180031d07  push    rdi
0x180031d08  push    r12
0x180031d0a  push    r13
0x180031d0c  push    r14
0x180031d0e  push    r15
0x180031d10  mov     rbp, rsp
0x180031d13  sub     rsp, 40h
0x180031d17  xor     r15d, r15d
0x180031d1a  lea     r13, dword_1800DE000
0x180031d21  mov     [rbp+hFile], r15
0x180031d25  mov     rbx, rdx
0x180031d28  mov     rsi, rcx
0x180031d2b  lea     r12d, [r15+8]
0x180031d2f  test    rcx, rcx
0x180031d32  jz      loc_180031F83
0x180031d38  mov     eax, cs:dword_1800DE000
0x180031d3e  cmp     eax, 4
0x180031d41  jbe     short loc_180031D6B
0x180031d43  mov     edx, r12d
0x180031d46  mov     rcx, r13
0x180031d49  call    _tlgKeywordOn
0x180031d4e  test    al, al
0x180031d50  jz      short loc_180031D6B
0x180031d52  lea     rax, [rbp+arg_0]
0x180031d56  mov     [rbp+arg_0], rsi
0x180031d5a  lea     rdx, dword_1800CC37C
0x180031d61  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x180031d66  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180031d6b  xor     r9d, r9d; lpSecurityAttributes
0x180031d6e  mov     [rsp+40h+hTemplateFile], r15; hTemplateFile
0x180031d73  mov     [rsp+40h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180031d7b  mov     rcx, rsi; lpFileName
0x180031d7e  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x180031d86  lea     edi, [r9+1]
0x180031d8a  mov     r8d, edi; dwShareMode
0x180031d8d  lea     edx, [rdi+7Fh]; dwDesiredAccess
0x180031d90  call    cs:__imp_CreateFileW
0x180031d97  nop     dword ptr [rax+rax+00h]
0x180031d9c  mov     rdx, rax
0x180031d9f  lea     rcx, [rbp+hFile]
0x180031da3  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180031da8  mov     rcx, [rbp+hFile]; hFile
0x180031dac  lea     rax, [rcx+1]
0x180031db0  cmp     rax, rdi
0x180031db3  ja      short loc_180031E18
0x180031db5  call    cs:__imp_GetLastError
0x180031dbc  nop     dword ptr [rax+rax+00h]
0x180031dc1  mov     ecx, eax; unsigned int
0x180031dc3  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180031dc8  mov     ecx, cs:dword_1800DE000
0x180031dce  mov     r8d, eax
0x180031dd1  cmp     ecx, 2
0x180031dd4  jbe     loc_180031F83
0x180031dda  mov     rdx, r12
0x180031ddd  mov     rcx, r13
0x180031de0  call    _tlgKeywordOn
0x180031de5  test    al, al
0x180031de7  jz      loc_180031F83
0x180031ded  lea     rax, [rbp+arg_0]
0x180031df1  mov     dword ptr [rbp+arg_0], r8d
0x180031df5  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], rax
0x180031dfa  lea     rdx, word_1800CC3AE
0x180031e01  lea     rax, [rbp+arg_18]
0x180031e05  mov     [rbp+arg_18], rsi
0x180031e09  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x180031e0e  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180031e13  jmp     loc_180031F83
0x180031e18  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031e1c  inc     rax
0x180031e1f  cmp     [rsi+rax*2], r15w
0x180031e24  jnz     short loc_180031E1C
0x180031e26  movzx   r14d, word ptr [rsi+rax*2-2]
0x180031e2c  mov     rdx, rbx
0x180031e2f  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180031e34  mov     r8d, eax
0x180031e37  test    eax, eax
0x180031e39  jns     short loc_180031E7B
0x180031e3b  mov     ecx, cs:dword_1800DE000
0x180031e41  cmp     ecx, 2
0x180031e44  jbe     loc_180031F83
0x180031e4a  mov     rdx, r12
0x180031e4d  mov     rcx, r13
0x180031e50  call    _tlgKeywordOn
0x180031e55  test    al, al
0x180031e57  jz      loc_180031F83
0x180031e5d  lea     rax, [rbp+arg_0]
0x180031e61  mov     dword ptr [rbp+arg_0], r8d
0x180031e65  lea     rdx, word_1800CC3EA
0x180031e6c  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x180031e71  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180031e76  jmp     loc_180031F83
0x180031e7b  mov     edx, 5Ch ; '\'; wchar_t *
0x180031e80  cmp     r14w, dx
0x180031e84  jnz     short loc_180031EAE
0x180031e86  mov     rcx, rbx
0x180031e89  call    ?ends_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(wchar_t)
0x180031e8e  test    al, al
0x180031e90  jnz     short loc_180031EAE
0x180031e92  mov     rcx, rbx
0x180031e95  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180031e9a  test    al, al
0x180031e9c  jnz     short loc_180031EAE
0x180031e9e  mov     rcx, [rbx]
0x180031ea1  mov     [rbx+8], rcx
0x180031ea5  mov     [rcx], r15w
0x180031ea9  jmp     loc_180031F83
0x180031eae  mov     rcx, [rbx]; this
0x180031eb1  mov     r14, r15
0x180031eb4  call    ?HasExtendedLengthPathPrefix@_werDetail@@YAHPEB_W@Z; _werDetail::HasExtendedLengthPathPrefix(wchar_t const *)
0x180031eb9  test    eax, eax
0x180031ebb  jz      short loc_180031EF9
0x180031ebd  mov     eax, cs:dword_1800DE000
0x180031ec3  cmp     eax, 5
0x180031ec6  jbe     short loc_180031EF3
0x180031ec8  mov     rdx, r12
0x180031ecb  mov     rcx, r13
0x180031ece  call    _tlgKeywordOn
0x180031ed3  test    al, al
0x180031ed5  jz      short loc_180031EF3
0x180031ed7  mov     rax, [rbx]
0x180031eda  lea     rdx, byte_1800CC415
0x180031ee1  mov     [rbp+arg_0], rax
0x180031ee5  lea     rax, [rbp+arg_0]
0x180031ee9  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x180031eee  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180031ef3  mov     r14d, 4
0x180031ef9  mov     eax, cs:dword_1800DE000
0x180031eff  cmp     eax, 5
0x180031f02  jbe     short loc_180031F3C
0x180031f04  mov     rdx, r12
0x180031f07  mov     rcx, r13
0x180031f0a  call    _tlgKeywordOn
0x180031f0f  test    al, al
0x180031f11  jz      short loc_180031F3C
0x180031f13  mov     rax, [rbx]
0x180031f16  lea     rdx, byte_1800CC453
0x180031f1d  mov     [rbp+arg_0], rax
0x180031f21  lea     rax, [rbp+arg_0]
0x180031f25  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], rax
0x180031f2a  lea     rax, [rbp+arg_18]
0x180031f2e  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x180031f33  mov     [rbp+arg_18], rsi
0x180031f37  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180031f3c  mov     r8, [rbx+8]
0x180031f40  mov     rcx, rsi
0x180031f43  sub     r8, [rbx]
0x180031f46  mov     rdx, [rbx]
0x180031f49  sar     r8, 1
0x180031f4c  call    cs:__imp__o__wcsnicmp
0x180031f53  nop     dword ptr [rax+rax+00h]
0x180031f58  test    eax, eax
0x180031f5a  jz      short loc_180031F83
0x180031f5c  mov     rax, [rbx]
0x180031f5f  mov     rcx, rsi
0x180031f62  mov     r8, [rbx+8]
0x180031f66  sub     r8, rax
0x180031f69  sar     r8, 1
0x180031f6c  sub     r8, r14
0x180031f6f  lea     rdx, [rax+r14*2]
0x180031f73  call    cs:__imp__o__wcsnicmp
0x180031f7a  nop     dword ptr [rax+rax+00h]
0x180031f7f  test    eax, eax
0x180031f81  jnz     short loc_180031F86
0x180031f83  mov     edi, r15d
0x180031f86  mov     eax, cs:dword_1800DE000
0x180031f8c  cmp     eax, 4
0x180031f8f  jbe     short loc_180031FC8
0x180031f91  mov     rdx, r12
0x180031f94  mov     rcx, r13
0x180031f97  call    _tlgKeywordOn
0x180031f9c  test    al, al
0x180031f9e  jz      short loc_180031FC8
0x180031fa0  mov     rcx, [rbx]
0x180031fa3  lea     rax, [rbp+arg_0]
0x180031fa7  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], rax
0x180031fac  lea     rdx, unk_1800CC498
0x180031fb3  lea     rax, [rbp+arg_18]
0x180031fb7  mov     dword ptr [rbp+arg_0], edi
0x180031fba  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x180031fbf  mov     [rbp+arg_18], rcx
0x180031fc3  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180031fc8  lea     rcx, [rbp+hFile]
0x180031fcc  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180031fd1  mov     rbx, [rsp+40h+arg_8]
0x180031fd9  mov     eax, edi
0x180031fdb  add     rsp, 40h
0x180031fdf  pop     r15
0x180031fe1  pop     r14
0x180031fe3  pop     r13
0x180031fe5  pop     r12
0x180031fe7  pop     rdi
0x180031fe8  pop     rsi
0x180031fe9  pop     rbp
0x180031fea  retn
```
