# UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x1800127a8`
- end: `0x180012b46`
- name: `?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `926`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x180012b4c`

## callees

- `0x18000113c`
- `0x1800011dc`
- `0x18000126c`
- `0x18000134c`
- `0x1800029d0`
- `0x18000e8a8`
- `0x1800117f4`
- `0x1800127a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012a86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012aa7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012a86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012863`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012851`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012851`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b16`

## pseudocode

```c
__int64 __fastcall UtilGetFinalPath(LPCWSTR lpFileName, LPCWSTR *a2, int a3, int a4)
{
  char *FileW; // rbx
  signed int LastError; // eax
  signed int v8; // ecx
  __int64 v9; // rax
  WCHAR v10; // r14
  int FinalPathByHandle; // edx
  const WCHAR *v12; // rax
  _WORD *v13; // rcx
  _WORD *v14; // rax
  __int64 v15; // r14
  int v16; // eax
  unsigned int v17; // edi
  LPCWSTR v19; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR v20; // [rsp+48h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+50h] [rbp-9h] BYREF
  LPCWSTR *v22; // [rsp+70h] [rbp+17h]
  __int64 v23; // [rsp+78h] [rbp+1Fh]

  if ( !lpFileName )
  {
    FileW = 0;
LABEL_45:
    v17 = 0;
    goto LABEL_46;
  }
  if ( (unsigned int)dword_180047000 > 4 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
  {
    v19 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_180047018,
      (unsigned int)&unk_18003F391,
      a3,
      a4,
      (__int64)&v19);
  }
  FileW = (char *)CreateFileW(lpFileName, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      LODWORD(v19) = v8;
      v20 = lpFileName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)&unk_18003F355,
        a3,
        a4,
        (__int64)&v20,
        (__int64)&v19);
    }
    goto LABEL_45;
  }
  v9 = -1;
  do
    ++v9;
  while ( lpFileName[v9] );
  v10 = lpFileName[v9 - 1];
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(FileW, (__int64)a2);
  if ( FinalPathByHandle < 0 )
  {
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      LODWORD(v19) = FinalPathByHandle;
      v22 = &v19;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180047000, byte_18003F32A, 0, 0, 3u, &v21);
    }
    goto LABEL_45;
  }
  if ( v10 == 92 )
  {
    v12 = a2[1];
    if ( (*a2 == v12 || *(v12 - 1) != 92)
      && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             a2,
                             92) )
    {
      v13 = *a2;
      a2[1] = *a2;
      *v13 = 0;
      goto LABEL_45;
    }
  }
  v14 = *a2;
  if ( *a2 && *v14 == 92 && v14[1] == 92 && v14[2] == 63 && v14[3] == 92 )
  {
    if ( (unsigned int)dword_180047000 > 5 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      v20 = *a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_180047018,
        (unsigned int)&unk_18003F2EC,
        a3,
        a4,
        (__int64)&v20);
    }
    v15 = 4;
  }
  else
  {
    v15 = 0;
  }
  if ( (unsigned int)dword_180047000 > 5 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
  {
    v20 = *a2;
    v19 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      qword_180047018,
      (unsigned int)&unk_18003F2A7,
      a3,
      a4,
      (__int64)&v19,
      (__int64)&v20);
  }
  if ( !(unsigned int)_o__wcsnicmp(lpFileName, *a2, a2[1] - *a2) )
    goto LABEL_45;
  v16 = _o__wcsnicmp(lpFileName, &(*a2)[v15], a2[1] - *a2 - v15);
  v17 = 1;
  if ( !v16 )
    goto LABEL_45;
LABEL_46:
  if ( (unsigned int)dword_180047000 > 4 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
  {
    v20 = *a2;
    LODWORD(v19) = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      qword_180047018,
      (unsigned int)&unk_18003F26D,
      a3,
      a4,
      (__int64)&v20,
      (__int64)&v19);
  }
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return v17;
}

```

## disassembly

```asm
0x1800127a8  mov     [rsp-8+arg_10], rbx
0x1800127ad  mov     [rsp-8+arg_18], rsi
0x1800127b2  push    rbp
0x1800127b3  push    rdi
0x1800127b4  push    r13
0x1800127b6  push    r14
0x1800127b8  push    r15
0x1800127ba  lea     rbp, [rsp-37h]
0x1800127bf  sub     rsp, 90h
0x1800127c6  mov     rax, cs:__security_cookie
0x1800127cd  xor     rax, rsp
0x1800127d0  mov     [rbp+57h+var_30], rax
0x1800127d4  xor     r15d, r15d
0x1800127d7  mov     rsi, rdx
0x1800127da  mov     rdi, rcx
0x1800127dd  test    rcx, rcx
0x1800127e0  jnz     short loc_1800127EA
0x1800127e2  mov     ebx, r15d
0x1800127e5  jmp     loc_180012AB6
0x1800127ea  mov     eax, cs:dword_180047000
0x1800127f0  cmp     eax, 4
0x1800127f3  jbe     short loc_18001282B
0x1800127f5  mov     rcx, cs:qword_180047018
0x1800127fc  mov     rax, cs:qword_180047010
0x180012803  test    al, 8
0x180012805  jz      short loc_18001282B
0x180012807  mov     rax, rcx
0x18001280a  and     eax, 8
0x18001280d  cmp     rax, rcx
0x180012810  jnz     short loc_18001282B
0x180012812  lea     rax, [rbp+57h+var_70]
0x180012816  mov     [rbp+57h+var_70], rdi
0x18001281a  lea     rdx, unk_18003F391
0x180012821  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x180012826  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18001282b  mov     r13d, 3
0x180012831  mov     [rsp+0B0h+hTemplateFile], r15; hTemplateFile
0x180012836  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18001283e  xor     r9d, r9d; lpSecurityAttributes
0x180012841  mov     rcx, rdi; lpFileName
0x180012844  mov     [rsp+0B0h+dwCreationDisposition], r13d; dwCreationDisposition
0x180012849  lea     edx, [r13+7Dh]; dwDesiredAccess
0x18001284d  lea     r8d, [r13-2]; dwShareMode
0x180012851  call    cs:__imp_CreateFileW
0x180012857  mov     rbx, rax
0x18001285a  inc     rax
0x18001285d  cmp     rax, 1
0x180012861  ja      short loc_1800128E0
0x180012863  call    cs:__imp_GetLastError
0x180012869  mov     ecx, eax
0x18001286b  test    eax, eax
0x18001286d  jle     short loc_180012878
0x18001286f  movzx   ecx, ax
0x180012872  or      ecx, 80070000h
0x180012878  test    ecx, ecx
0x18001287a  mov     eax, 80004005h
0x18001287f  cmovns  ecx, eax
0x180012882  mov     eax, cs:dword_180047000
0x180012888  cmp     eax, 2
0x18001288b  jbe     loc_180012AB6
0x180012891  mov     rdx, cs:qword_180047018
0x180012898  mov     rax, cs:qword_180047010
0x18001289f  test    al, 8
0x1800128a1  jz      loc_180012AB6
0x1800128a7  mov     rax, rdx
0x1800128aa  and     eax, 8
0x1800128ad  cmp     rax, rdx
0x1800128b0  jnz     loc_180012AB6
0x1800128b6  lea     rax, [rbp+57h+var_70]
0x1800128ba  mov     dword ptr [rbp+57h+var_70], ecx
0x1800128bd  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x1800128c2  lea     rdx, unk_18003F355
0x1800128c9  lea     rax, [rbp+57h+var_68]
0x1800128cd  mov     [rbp+57h+var_68], rdi
0x1800128d1  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1800128d6  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800128db  jmp     loc_180012AB6
0x1800128e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800128e4  inc     rax
0x1800128e7  cmp     [rdi+rax*2], r15w
0x1800128ec  jnz     short loc_1800128E4
0x1800128ee  movzx   r14d, word ptr [rdi+rax*2-2]
0x1800128f4  mov     rdx, rsi
0x1800128f7  mov     rcx, rbx; hFile
0x1800128fa  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800128ff  mov     edx, eax
0x180012901  test    eax, eax
0x180012903  jns     short loc_180012978
0x180012905  mov     eax, cs:dword_180047000
0x18001290b  cmp     eax, 2
0x18001290e  jbe     loc_180012AB6
0x180012914  mov     rcx, cs:qword_180047018
0x18001291b  mov     rax, cs:qword_180047010
0x180012922  test    al, 8
0x180012924  jz      loc_180012AB6
0x18001292a  mov     rax, rcx
0x18001292d  and     eax, 8
0x180012930  cmp     rax, rcx
0x180012933  jnz     loc_180012AB6
0x180012939  lea     rax, [rbp+57h+var_70]
0x18001293d  mov     dword ptr [rbp+57h+var_70], edx
0x180012940  mov     [rbp+57h+var_40], rax
0x180012944  lea     rdx, byte_18003F32A
0x18001294b  lea     rax, [rbp+57h+var_60]
0x18001294f  mov     [rbp+57h+var_38], 4
0x180012957  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x18001295c  lea     rcx, dword_180047000
0x180012963  xor     r9d, r9d
0x180012966  mov     [rsp+0B0h+dwCreationDisposition], r13d
0x18001296b  xor     r8d, r8d
0x18001296e  call    _tlgWriteTransfer_EventWriteTransfer
0x180012973  jmp     loc_180012AB6
0x180012978  mov     r13d, 5Ch ; '\'
0x18001297e  cmp     r14w, r13w
0x180012982  jnz     short loc_1800129B3
0x180012984  mov     rax, [rsi+8]
0x180012988  cmp     [rsi], rax
0x18001298b  jz      short loc_180012994
0x18001298d  cmp     r13w, [rax-2]
0x180012992  jz      short loc_1800129B3
0x180012994  mov     edx, r13d
0x180012997  mov     rcx, rsi
0x18001299a  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18001299f  test    al, al
0x1800129a1  jnz     short loc_1800129B3
0x1800129a3  mov     rcx, [rsi]
0x1800129a6  mov     [rsi+8], rcx
0x1800129aa  mov     [rcx], r15w
0x1800129ae  jmp     loc_180012AB6
0x1800129b3  mov     rax, [rsi]
0x1800129b6  test    rax, rax
0x1800129b9  jz      short loc_180012A22
0x1800129bb  cmp     [rax], r13w
0x1800129bf  jnz     short loc_180012A22
0x1800129c1  cmp     [rax+2], r13w
0x1800129c6  jnz     short loc_180012A22
0x1800129c8  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800129cd  jnz     short loc_180012A22
0x1800129cf  cmp     [rax+6], r13w
0x1800129d4  jnz     short loc_180012A22
0x1800129d6  mov     eax, cs:dword_180047000
0x1800129dc  cmp     eax, 5
0x1800129df  jbe     short loc_180012A1A
0x1800129e1  mov     rcx, cs:qword_180047018
0x1800129e8  mov     rax, cs:qword_180047010
0x1800129ef  test    al, 8
0x1800129f1  jz      short loc_180012A1A
0x1800129f3  mov     rax, rcx
0x1800129f6  and     eax, 8
0x1800129f9  cmp     rax, rcx
0x1800129fc  jnz     short loc_180012A1A
0x1800129fe  mov     rax, [rsi]
0x180012a01  lea     rdx, unk_18003F2EC
0x180012a08  mov     [rbp+57h+var_68], rax
0x180012a0c  lea     rax, [rbp+57h+var_68]
0x180012a10  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x180012a15  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180012a1a  mov     r14d, 4
0x180012a20  jmp     short loc_180012A25
0x180012a22  mov     r14, r15
0x180012a25  mov     eax, cs:dword_180047000
0x180012a2b  cmp     eax, 5
0x180012a2e  jbe     short loc_180012A76
0x180012a30  mov     rcx, cs:qword_180047018
0x180012a37  mov     rax, cs:qword_180047010
0x180012a3e  test    al, 8
0x180012a40  jz      short loc_180012A76
0x180012a42  mov     rax, rcx
0x180012a45  and     eax, 8
0x180012a48  cmp     rax, rcx
0x180012a4b  jnz     short loc_180012A76
0x180012a4d  mov     rax, [rsi]
0x180012a50  lea     rdx, unk_18003F2A7
0x180012a57  mov     [rbp+57h+var_68], rax
0x180012a5b  lea     rax, [rbp+57h+var_68]
0x180012a5f  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x180012a64  lea     rax, [rbp+57h+var_70]
0x180012a68  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x180012a6d  mov     [rbp+57h+var_70], rdi
0x180012a71  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180012a76  mov     r8, [rsi+8]
0x180012a7a  mov     rcx, rdi
0x180012a7d  sub     r8, [rsi]
0x180012a80  mov     rdx, [rsi]
0x180012a83  sar     r8, 1
0x180012a86  call    cs:__imp__o__wcsnicmp
0x180012a8c  test    eax, eax
0x180012a8e  jz      short loc_180012AB6
0x180012a90  mov     rax, [rsi]
0x180012a93  mov     rcx, rdi
0x180012a96  mov     r8, [rsi+8]
0x180012a9a  sub     r8, rax
0x180012a9d  sar     r8, 1
0x180012aa0  sub     r8, r14
0x180012aa3  lea     rdx, [rax+r14*2]
0x180012aa7  call    cs:__imp__o__wcsnicmp
0x180012aad  mov     edi, 1
0x180012ab2  test    eax, eax
0x180012ab4  jnz     short loc_180012AB9
0x180012ab6  mov     edi, r15d
0x180012ab9  mov     eax, cs:dword_180047000
0x180012abf  cmp     eax, 4
0x180012ac2  jbe     short loc_180012B09
0x180012ac4  mov     rcx, cs:qword_180047018
0x180012acb  mov     rax, cs:qword_180047010
0x180012ad2  test    al, 8
0x180012ad4  jz      short loc_180012B09
0x180012ad6  mov     rax, rcx
0x180012ad9  and     eax, 8
0x180012adc  cmp     rax, rcx
0x180012adf  jnz     short loc_180012B09
0x180012ae1  mov     rax, [rsi]
0x180012ae4  lea     rdx, unk_18003F26D
0x180012aeb  mov     [rbp+57h+var_68], rax
0x180012aef  lea     rax, [rbp+57h+var_70]
0x180012af3  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x180012af8  lea     rax, [rbp+57h+var_68]
0x180012afc  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x180012b01  mov     dword ptr [rbp+57h+var_70], edi
0x180012b04  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180012b09  lea     rcx, [rbx+1]
0x180012b0d  cmp     rcx, 1
0x180012b11  jbe     short loc_180012B1C
0x180012b13  mov     rcx, rbx; hObject
0x180012b16  call    cs:__imp_CloseHandle
0x180012b1c  mov     eax, edi
0x180012b1e  mov     rcx, [rbp+57h+var_30]
0x180012b22  xor     rcx, rsp; StackCookie
0x180012b25  call    __security_check_cookie
0x180012b2a  lea     r11, [rsp+0B0h+var_20]
0x180012b32  mov     rbx, [r11+40h]
0x180012b36  mov     rsi, [r11+48h]
0x180012b3a  mov     rsp, r11
0x180012b3d  pop     r15
0x180012b3f  pop     r14
0x180012b41  pop     r13
0x180012b43  pop     rdi
0x180012b44  pop     rbp
0x180012b45  retn
```
