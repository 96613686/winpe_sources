# UtilGetFinalPath(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800045cc`
- end: `0x180004967`
- name: `?UtilGetFinalPath@@YAHPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `923`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x18000531c`

## callees

- `0x180001008`
- `0x180001098`
- `0x180001270`
- `0x18000131c`
- `0x1800045cc`
- `0x180004970`
- `0x180006828`
- `0x1800121b0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800048a7`
- `msvcrt!_wcsnicmp` at `0x1800048c8`
- `msvcrt!_wcsnicmp` at `0x1800048a7`
- `msvcrt!_wcsnicmp` at `0x1800048c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004675`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004687`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004937`

## pseudocode

```c
__int64 __fastcall UtilGetFinalPath(wchar_t *String1, __int64 a2, int a3, int a4)
{
  char *FileW; // rbx
  signed int LastError; // eax
  signed int v8; // ecx
  __int64 v9; // rax
  wchar_t v10; // r14
  int FinalPathByHandle; // edx
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  const wchar_t *v14; // rax
  __int64 v15; // r14
  int v16; // eax
  unsigned int v17; // edi
  wchar_t *v19; // [rsp+40h] [rbp-19h] BYREF
  wchar_t *v20; // [rsp+48h] [rbp-11h] BYREF
  char v21[32]; // [rsp+50h] [rbp-9h] BYREF
  wchar_t **v22; // [rsp+70h] [rbp+17h]
  __int64 v23; // [rsp+78h] [rbp+1Fh]

  if ( !String1 )
  {
    FileW = 0;
LABEL_45:
    v17 = 0;
    goto LABEL_46;
  }
  if ( (unsigned int)dword_18001C008 > 4 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
  {
    v19 = String1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      qword_18001C020,
      (unsigned int)byte_180018C5B,
      a3,
      a4,
      (__int64)&v19);
  }
  FileW = (char *)CreateFileW(String1, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      LODWORD(v19) = v8;
      v20 = String1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)&byte_180018D47,
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
  while ( String1[v9] );
  v10 = String1[v9 - 1];
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(FileW, a2);
  if ( FinalPathByHandle < 0 )
  {
    if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      LODWORD(v19) = FinalPathByHandle;
      v22 = &v19;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, &unk_1800188E8, 0, 0, 3, v21);
    }
    goto LABEL_45;
  }
  if ( v10 == 92 )
  {
    v12 = *(_QWORD *)(a2 + 8);
    if ( (*(_QWORD *)a2 == v12 || *(_WORD *)(v12 - 2) != 92)
      && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::push_back(a2) )
    {
      v13 = *(const wchar_t **)a2;
      *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
      *v13 = 0;
      goto LABEL_45;
    }
  }
  v14 = *(const wchar_t **)a2;
  if ( *(_QWORD *)a2 && *v14 == 92 && v14[1] == 92 && v14[2] == 63 && v14[3] == 92 )
  {
    if ( (unsigned int)dword_18001C008 > 5 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      v20 = *(wchar_t **)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        qword_18001C020,
        (unsigned int)word_180018BDA,
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
  if ( (unsigned int)dword_18001C008 > 5 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
  {
    v20 = *(wchar_t **)a2;
    v19 = String1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      qword_18001C020,
      (unsigned int)&dword_180018854,
      a3,
      a4,
      (__int64)&v19,
      (__int64)&v20);
  }
  if ( !_wcsnicmp(String1, *(const wchar_t **)a2, (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) )
    goto LABEL_45;
  v16 = _wcsnicmp(
          String1,
          (const wchar_t *)(*(_QWORD *)a2 + 2 * v15),
          ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) - v15);
  v17 = 1;
  if ( !v16 )
    goto LABEL_45;
LABEL_46:
  if ( (unsigned int)dword_18001C008 > 4 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
  {
    v20 = *(wchar_t **)a2;
    LODWORD(v19) = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      qword_18001C020,
      (unsigned int)&byte_180018487,
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
0x1800045cc  mov     [rsp-8+arg_10], rbx
0x1800045d1  mov     [rsp-8+arg_18], rsi
0x1800045d6  push    rbp
0x1800045d7  push    rdi
0x1800045d8  push    r13
0x1800045da  push    r14
0x1800045dc  push    r15
0x1800045de  lea     rbp, [rsp-37h]
0x1800045e3  sub     rsp, 90h
0x1800045ea  mov     rax, cs:__security_cookie
0x1800045f1  xor     rax, rsp
0x1800045f4  mov     [rbp+57h+var_30], rax
0x1800045f8  xor     r15d, r15d
0x1800045fb  mov     rsi, rdx
0x1800045fe  mov     rdi, rcx
0x180004601  test    rcx, rcx
0x180004604  jnz     short loc_18000460E
0x180004606  mov     ebx, r15d
0x180004609  jmp     loc_1800048D7
0x18000460e  mov     eax, cs:dword_18001C008
0x180004614  cmp     eax, 4
0x180004617  jbe     short loc_18000464F
0x180004619  mov     rcx, cs:qword_18001C020
0x180004620  mov     rax, cs:qword_18001C018
0x180004627  test    al, 8
0x180004629  jz      short loc_18000464F
0x18000462b  mov     rax, rcx
0x18000462e  and     eax, 8
0x180004631  cmp     rax, rcx
0x180004634  jnz     short loc_18000464F
0x180004636  lea     rax, [rbp+57h+var_70]
0x18000463a  mov     [rbp+57h+var_70], rdi
0x18000463e  lea     rdx, byte_180018C5B
0x180004645  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18000464a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000464f  mov     r13d, 3
0x180004655  mov     [rsp+0B0h+hTemplateFile], r15; hTemplateFile
0x18000465a  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180004662  xor     r9d, r9d; lpSecurityAttributes
0x180004665  mov     rcx, rdi; lpFileName
0x180004668  mov     [rsp+0B0h+dwCreationDisposition], r13d; dwCreationDisposition
0x18000466d  lea     edx, [r13+7Dh]; dwDesiredAccess
0x180004671  lea     r8d, [r13-2]; dwShareMode
0x180004675  call    cs:__imp_CreateFileW
0x18000467b  mov     rbx, rax
0x18000467e  inc     rax
0x180004681  cmp     rax, 1
0x180004685  ja      short loc_180004704
0x180004687  call    cs:__imp_GetLastError
0x18000468d  mov     ecx, eax
0x18000468f  test    eax, eax
0x180004691  jle     short loc_18000469C
0x180004693  movzx   ecx, ax
0x180004696  or      ecx, 80070000h
0x18000469c  test    ecx, ecx
0x18000469e  mov     eax, 80004005h
0x1800046a3  cmovns  ecx, eax
0x1800046a6  mov     eax, cs:dword_18001C008
0x1800046ac  cmp     eax, 2
0x1800046af  jbe     loc_1800048D7
0x1800046b5  mov     rdx, cs:qword_18001C020
0x1800046bc  mov     rax, cs:qword_18001C018
0x1800046c3  test    al, 8
0x1800046c5  jz      loc_1800048D7
0x1800046cb  mov     rax, rdx
0x1800046ce  and     eax, 8
0x1800046d1  cmp     rax, rdx
0x1800046d4  jnz     loc_1800048D7
0x1800046da  lea     rax, [rbp+57h+var_70]
0x1800046de  mov     dword ptr [rbp+57h+var_70], ecx
0x1800046e1  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x1800046e6  lea     rdx, byte_180018D47
0x1800046ed  lea     rax, [rbp+57h+var_68]
0x1800046f1  mov     [rbp+57h+var_68], rdi
0x1800046f5  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1800046fa  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800046ff  jmp     loc_1800048D7
0x180004704  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004708  inc     rax
0x18000470b  cmp     [rdi+rax*2], r15w
0x180004710  jnz     short loc_180004708
0x180004712  movzx   r14d, word ptr [rdi+rax*2-2]
0x180004718  mov     rdx, rsi
0x18000471b  mov     rcx, rbx; hFile
0x18000471e  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180004723  mov     edx, eax
0x180004725  test    eax, eax
0x180004727  jns     short loc_18000479C
0x180004729  mov     eax, cs:dword_18001C008
0x18000472f  cmp     eax, 2
0x180004732  jbe     loc_1800048D7
0x180004738  mov     rcx, cs:qword_18001C020
0x18000473f  mov     rax, cs:qword_18001C018
0x180004746  test    al, 8
0x180004748  jz      loc_1800048D7
0x18000474e  mov     rax, rcx
0x180004751  and     eax, 8
0x180004754  cmp     rax, rcx
0x180004757  jnz     loc_1800048D7
0x18000475d  lea     rax, [rbp+57h+var_70]
0x180004761  mov     dword ptr [rbp+57h+var_70], edx
0x180004764  mov     [rbp+57h+var_40], rax
0x180004768  lea     rdx, unk_1800188E8
0x18000476f  lea     rax, [rbp+57h+var_60]
0x180004773  mov     [rbp+57h+var_38], 4
0x18000477b  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x180004780  lea     rcx, dword_18001C008
0x180004787  xor     r9d, r9d
0x18000478a  mov     [rsp+0B0h+dwCreationDisposition], r13d
0x18000478f  xor     r8d, r8d
0x180004792  call    _tlgWriteTransfer_EventWriteTransfer
0x180004797  jmp     loc_1800048D7
0x18000479c  mov     r13d, 5Ch ; '\'
0x1800047a2  cmp     r14w, r13w
0x1800047a6  jnz     short loc_1800047D4
0x1800047a8  mov     rax, [rsi+8]
0x1800047ac  cmp     [rsi], rax
0x1800047af  jz      short loc_1800047B8
0x1800047b1  cmp     r13w, [rax-2]
0x1800047b6  jz      short loc_1800047D4
0x1800047b8  mov     rcx, rsi
0x1800047bb  call    ?push_back@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::push_back(ushort)
0x1800047c0  test    al, al
0x1800047c2  jnz     short loc_1800047D4
0x1800047c4  mov     rcx, [rsi]
0x1800047c7  mov     [rsi+8], rcx
0x1800047cb  mov     [rcx], r15w
0x1800047cf  jmp     loc_1800048D7
0x1800047d4  mov     rax, [rsi]
0x1800047d7  test    rax, rax
0x1800047da  jz      short loc_180004843
0x1800047dc  cmp     [rax], r13w
0x1800047e0  jnz     short loc_180004843
0x1800047e2  cmp     [rax+2], r13w
0x1800047e7  jnz     short loc_180004843
0x1800047e9  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800047ee  jnz     short loc_180004843
0x1800047f0  cmp     [rax+6], r13w
0x1800047f5  jnz     short loc_180004843
0x1800047f7  mov     eax, cs:dword_18001C008
0x1800047fd  cmp     eax, 5
0x180004800  jbe     short loc_18000483B
0x180004802  mov     rcx, cs:qword_18001C020
0x180004809  mov     rax, cs:qword_18001C018
0x180004810  test    al, 8
0x180004812  jz      short loc_18000483B
0x180004814  mov     rax, rcx
0x180004817  and     eax, 8
0x18000481a  cmp     rax, rcx
0x18000481d  jnz     short loc_18000483B
0x18000481f  mov     rax, [rsi]
0x180004822  lea     rdx, word_180018BDA
0x180004829  mov     [rbp+57h+var_68], rax
0x18000482d  lea     rax, [rbp+57h+var_68]
0x180004831  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x180004836  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000483b  mov     r14d, 4
0x180004841  jmp     short loc_180004846
0x180004843  mov     r14, r15
0x180004846  mov     eax, cs:dword_18001C008
0x18000484c  cmp     eax, 5
0x18000484f  jbe     short loc_180004897
0x180004851  mov     rcx, cs:qword_18001C020
0x180004858  mov     rax, cs:qword_18001C018
0x18000485f  test    al, 8
0x180004861  jz      short loc_180004897
0x180004863  mov     rax, rcx
0x180004866  and     eax, 8
0x180004869  cmp     rax, rcx
0x18000486c  jnz     short loc_180004897
0x18000486e  mov     rax, [rsi]
0x180004871  lea     rdx, dword_180018854
0x180004878  mov     [rbp+57h+var_68], rax
0x18000487c  lea     rax, [rbp+57h+var_68]
0x180004880  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x180004885  lea     rax, [rbp+57h+var_70]
0x180004889  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18000488e  mov     [rbp+57h+var_70], rdi
0x180004892  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180004897  mov     r8, [rsi+8]
0x18000489b  mov     rcx, rdi; String1
0x18000489e  sub     r8, [rsi]
0x1800048a1  mov     rdx, [rsi]; String2
0x1800048a4  sar     r8, 1; MaxCount
0x1800048a7  call    cs:__imp__wcsnicmp
0x1800048ad  test    eax, eax
0x1800048af  jz      short loc_1800048D7
0x1800048b1  mov     rax, [rsi]
0x1800048b4  mov     rcx, rdi; String1
0x1800048b7  mov     r8, [rsi+8]
0x1800048bb  sub     r8, rax
0x1800048be  sar     r8, 1
0x1800048c1  sub     r8, r14; MaxCount
0x1800048c4  lea     rdx, [rax+r14*2]; String2
0x1800048c8  call    cs:__imp__wcsnicmp
0x1800048ce  mov     edi, 1
0x1800048d3  test    eax, eax
0x1800048d5  jnz     short loc_1800048DA
0x1800048d7  mov     edi, r15d
0x1800048da  mov     eax, cs:dword_18001C008
0x1800048e0  cmp     eax, 4
0x1800048e3  jbe     short loc_18000492A
0x1800048e5  mov     rcx, cs:qword_18001C020
0x1800048ec  mov     rax, cs:qword_18001C018
0x1800048f3  test    al, 8
0x1800048f5  jz      short loc_18000492A
0x1800048f7  mov     rax, rcx
0x1800048fa  and     eax, 8
0x1800048fd  cmp     rax, rcx
0x180004900  jnz     short loc_18000492A
0x180004902  mov     rax, [rsi]
0x180004905  lea     rdx, byte_180018487
0x18000490c  mov     [rbp+57h+var_68], rax
0x180004910  lea     rax, [rbp+57h+var_70]
0x180004914  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x180004919  lea     rax, [rbp+57h+var_68]
0x18000491d  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x180004922  mov     dword ptr [rbp+57h+var_70], edi
0x180004925  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000492a  lea     rcx, [rbx+1]
0x18000492e  cmp     rcx, 1
0x180004932  jbe     short loc_18000493D
0x180004934  mov     rcx, rbx; hObject
0x180004937  call    cs:__imp_CloseHandle
0x18000493d  mov     eax, edi
0x18000493f  mov     rcx, [rbp+57h+var_30]
0x180004943  xor     rcx, rsp; StackCookie
0x180004946  call    __security_check_cookie
0x18000494b  lea     r11, [rsp+0B0h+var_20]
0x180004953  mov     rbx, [r11+40h]
0x180004957  mov     rsi, [r11+48h]
0x18000495b  mov     rsp, r11
0x18000495e  pop     r15
0x180004960  pop     r14
0x180004962  pop     r13
0x180004964  pop     rdi
0x180004965  pop     rbp
0x180004966  retn
```
