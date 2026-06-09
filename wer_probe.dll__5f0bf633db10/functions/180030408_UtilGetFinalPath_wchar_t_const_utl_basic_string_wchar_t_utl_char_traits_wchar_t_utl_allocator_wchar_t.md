# UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x180030408`
- end: `0x1800306db`
- name: `?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `5`
- callee_count: `13`
- tags: `file_ops, reparse_path`

## callers

- `0x180009758`
- `0x18001d128`
- `0x180030e40`
- `0x180044230`
- `0x18009633c`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x180013a20`
- `0x180019808`
- `0x180023dc4`
- `0x180023e8c`
- `0x180027480`
- `0x18002d010`
- `0x1800303dc`
- `0x180030408`
- `0x1800306e4`
- `0x18004ac4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030648`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030669`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030648`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030498`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030498`

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
  __int64 v21; // r9
  int v22; // ecx
  int v23; // r8d
  int v24; // ecx
  int v25; // r8d
  __int64 v26; // r9
  int v27; // r8d
  int v28; // r9d
  _werDetail *v29; // rcx
  _werDetail *v31; // [rsp+80h] [rbp+40h] BYREF
  HANDLE hFile; // [rsp+90h] [rbp+50h] BYREF
  LPCWSTR v33; // [rsp+98h] [rbp+58h] BYREF

  hFile = 0;
  if ( !lpFileName )
    goto LABEL_29;
  if ( (unsigned int)dword_1800D9000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
  {
    v31 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v4,
      (unsigned int)&unk_1800C72CC,
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
    if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
    {
      LODWORD(v31) = v11;
      v33 = (LPCWSTR)lpFileName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&unk_1800C72FE,
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
    if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
    {
      LODWORD(v31) = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v15,
        (unsigned int)&unk_1800C733A,
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
    if ( (unsigned int)dword_1800D9000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
    {
      v31 = *a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v22,
        (unsigned int)&unk_1800C7365,
        v23,
        v21,
        (__int64)&v31);
    }
    v20 = 4;
  }
  if ( (unsigned int)dword_1800D9000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
  {
    v31 = *a2;
    v33 = (LPCWSTR)lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      v24,
      (unsigned int)&unk_1800C73A3,
      v25,
      v21,
      (__int64)&v33,
      (__int64)&v31);
  }
  if ( !(unsigned int)_o__wcsnicmp(lpFileName, *a2, (a2[1] - *a2) >> 1, v21)
    || !(unsigned int)_o__wcsnicmp(lpFileName, (char *)*a2 + 2 * v20, ((a2[1] - *a2) >> 1) - v20, v26) )
  {
    goto LABEL_29;
  }
LABEL_30:
  if ( (unsigned int)dword_1800D9000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
  {
    v29 = *a2;
    LODWORD(v31) = v7;
    v33 = (LPCWSTR)v29;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      (_DWORD)v29,
      (unsigned int)&unk_1800C73E8,
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
0x180030408  mov     [rsp-38h+arg_8], rbx
0x18003040d  push    rbp
0x18003040e  push    rsi
0x18003040f  push    rdi
0x180030410  push    r12
0x180030412  push    r13
0x180030414  push    r14
0x180030416  push    r15
0x180030418  mov     rbp, rsp
0x18003041b  sub     rsp, 40h
0x18003041f  xor     r15d, r15d
0x180030422  lea     r13, dword_1800D9000
0x180030429  mov     [rbp+hFile], r15
0x18003042d  mov     rbx, rdx
0x180030430  mov     rsi, rcx
0x180030433  lea     r12d, [r15+8]
0x180030437  test    rcx, rcx
0x18003043a  jz      loc_180030673
0x180030440  mov     eax, cs:dword_1800D9000
0x180030446  cmp     eax, 4
0x180030449  jbe     short loc_180030473
0x18003044b  mov     edx, r12d
0x18003044e  mov     rcx, r13
0x180030451  call    _tlgKeywordOn
0x180030456  test    al, al
0x180030458  jz      short loc_180030473
0x18003045a  lea     rax, [rbp+arg_0]
0x18003045e  mov     [rbp+arg_0], rsi
0x180030462  lea     rdx, unk_1800C72CC
0x180030469  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x18003046e  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180030473  xor     r9d, r9d; lpSecurityAttributes
0x180030476  mov     [rsp+40h+hTemplateFile], r15; hTemplateFile
0x18003047b  mov     [rsp+40h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180030483  mov     rcx, rsi; lpFileName
0x180030486  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x18003048e  lea     edi, [r9+1]
0x180030492  mov     r8d, edi; dwShareMode
0x180030495  lea     edx, [rdi+7Fh]; dwDesiredAccess
0x180030498  call    cs:__imp_CreateFileW
0x18003049e  mov     rdx, rax
0x1800304a1  lea     rcx, [rbp+hFile]
0x1800304a5  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800304aa  mov     rcx, [rbp+hFile]; hFile
0x1800304ae  lea     rax, [rcx+1]
0x1800304b2  cmp     rax, rdi
0x1800304b5  ja      short loc_180030514
0x1800304b7  call    cs:__imp_GetLastError
0x1800304bd  mov     ecx, eax; unsigned int
0x1800304bf  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800304c4  mov     ecx, cs:dword_1800D9000
0x1800304ca  mov     r8d, eax
0x1800304cd  cmp     ecx, 2
0x1800304d0  jbe     loc_180030673
0x1800304d6  mov     rdx, r12
0x1800304d9  mov     rcx, r13
0x1800304dc  call    _tlgKeywordOn
0x1800304e1  test    al, al
0x1800304e3  jz      loc_180030673
0x1800304e9  lea     rax, [rbp+arg_0]
0x1800304ed  mov     dword ptr [rbp+arg_0], r8d
0x1800304f1  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], rax
0x1800304f6  lea     rdx, unk_1800C72FE
0x1800304fd  lea     rax, [rbp+arg_18]
0x180030501  mov     [rbp+arg_18], rsi
0x180030505  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x18003050a  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18003050f  jmp     loc_180030673
0x180030514  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030518  inc     rax
0x18003051b  cmp     [rsi+rax*2], r15w
0x180030520  jnz     short loc_180030518
0x180030522  movzx   r14d, word ptr [rsi+rax*2-2]
0x180030528  mov     rdx, rbx
0x18003052b  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180030530  mov     r8d, eax
0x180030533  test    eax, eax
0x180030535  jns     short loc_180030577
0x180030537  mov     ecx, cs:dword_1800D9000
0x18003053d  cmp     ecx, 2
0x180030540  jbe     loc_180030673
0x180030546  mov     rdx, r12
0x180030549  mov     rcx, r13
0x18003054c  call    _tlgKeywordOn
0x180030551  test    al, al
0x180030553  jz      loc_180030673
0x180030559  lea     rax, [rbp+arg_0]
0x18003055d  mov     dword ptr [rbp+arg_0], r8d
0x180030561  lea     rdx, unk_1800C733A
0x180030568  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x18003056d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180030572  jmp     loc_180030673
0x180030577  mov     edx, 5Ch ; '\'; wchar_t *
0x18003057c  cmp     r14w, dx
0x180030580  jnz     short loc_1800305AA
0x180030582  mov     rcx, rbx
0x180030585  call    ?ends_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(wchar_t)
0x18003058a  test    al, al
0x18003058c  jnz     short loc_1800305AA
0x18003058e  mov     rcx, rbx
0x180030591  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180030596  test    al, al
0x180030598  jnz     short loc_1800305AA
0x18003059a  mov     rcx, [rbx]
0x18003059d  mov     [rbx+8], rcx
0x1800305a1  mov     [rcx], r15w
0x1800305a5  jmp     loc_180030673
0x1800305aa  mov     rcx, [rbx]; this
0x1800305ad  mov     r14, r15
0x1800305b0  call    ?HasExtendedLengthPathPrefix@_werDetail@@YAHPEB_W@Z; _werDetail::HasExtendedLengthPathPrefix(wchar_t const *)
0x1800305b5  test    eax, eax
0x1800305b7  jz      short loc_1800305F5
0x1800305b9  mov     eax, cs:dword_1800D9000
0x1800305bf  cmp     eax, 5
0x1800305c2  jbe     short loc_1800305EF
0x1800305c4  mov     rdx, r12
0x1800305c7  mov     rcx, r13
0x1800305ca  call    _tlgKeywordOn
0x1800305cf  test    al, al
0x1800305d1  jz      short loc_1800305EF
0x1800305d3  mov     rax, [rbx]
0x1800305d6  lea     rdx, unk_1800C7365
0x1800305dd  mov     [rbp+arg_0], rax
0x1800305e1  lea     rax, [rbp+arg_0]
0x1800305e5  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x1800305ea  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800305ef  mov     r14d, 4
0x1800305f5  mov     eax, cs:dword_1800D9000
0x1800305fb  cmp     eax, 5
0x1800305fe  jbe     short loc_180030638
0x180030600  mov     rdx, r12
0x180030603  mov     rcx, r13
0x180030606  call    _tlgKeywordOn
0x18003060b  test    al, al
0x18003060d  jz      short loc_180030638
0x18003060f  mov     rax, [rbx]
0x180030612  lea     rdx, unk_1800C73A3
0x180030619  mov     [rbp+arg_0], rax
0x18003061d  lea     rax, [rbp+arg_0]
0x180030621  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], rax
0x180030626  lea     rax, [rbp+arg_18]
0x18003062a  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x18003062f  mov     [rbp+arg_18], rsi
0x180030633  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180030638  mov     r8, [rbx+8]
0x18003063c  mov     rcx, rsi
0x18003063f  sub     r8, [rbx]
0x180030642  mov     rdx, [rbx]
0x180030645  sar     r8, 1
0x180030648  call    cs:__imp__o__wcsnicmp
0x18003064e  test    eax, eax
0x180030650  jz      short loc_180030673
0x180030652  mov     rax, [rbx]
0x180030655  mov     rcx, rsi
0x180030658  mov     r8, [rbx+8]
0x18003065c  sub     r8, rax
0x18003065f  sar     r8, 1
0x180030662  sub     r8, r14
0x180030665  lea     rdx, [rax+r14*2]
0x180030669  call    cs:__imp__o__wcsnicmp
0x18003066f  test    eax, eax
0x180030671  jnz     short loc_180030676
0x180030673  mov     edi, r15d
0x180030676  mov     eax, cs:dword_1800D9000
0x18003067c  cmp     eax, 4
0x18003067f  jbe     short loc_1800306B8
0x180030681  mov     rdx, r12
0x180030684  mov     rcx, r13
0x180030687  call    _tlgKeywordOn
0x18003068c  test    al, al
0x18003068e  jz      short loc_1800306B8
0x180030690  mov     rcx, [rbx]
0x180030693  lea     rax, [rbp+arg_0]
0x180030697  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], rax
0x18003069c  lea     rdx, unk_1800C73E8
0x1800306a3  lea     rax, [rbp+arg_18]
0x1800306a7  mov     dword ptr [rbp+arg_0], edi
0x1800306aa  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x1800306af  mov     [rbp+arg_18], rcx
0x1800306b3  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800306b8  lea     rcx, [rbp+hFile]
0x1800306bc  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800306c1  mov     rbx, [rsp+40h+arg_8]
0x1800306c9  mov     eax, edi
0x1800306cb  add     rsp, 40h
0x1800306cf  pop     r15
0x1800306d1  pop     r14
0x1800306d3  pop     r13
0x1800306d5  pop     r12
0x1800306d7  pop     rdi
0x1800306d8  pop     rsi
0x1800306d9  pop     rbp
0x1800306da  retn
```
