# UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)

- ea: `0x14000be08`
- end: `0x14000c38b`
- name: `?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z`
- size: `1411`
- prototype: `__int64 __fastcall(const wchar_t *, int, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1400058ec`
- `0x14000be08`

## callees

- `0x140001008`
- `0x140001178`
- `0x140001270`
- `0x14000162c`
- `0x140002fbc`
- `0x140003200`
- `0x140003224`
- `0x1400045bc`
- `0x140008ce4`
- `0x14000b0d8`
- `0x14000be08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c0ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c0ac`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000c095`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000c095`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000c24f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000c24f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000c269`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000c364`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000c269`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000c364`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000beea`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000beea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilRecursiveRemoveDirectory(WCHAR *a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v5; // r14
  DWORD FileAttributesW; // eax
  int v8; // r8d
  int v9; // r9d
  signed int LastError; // eax
  signed int v11; // ebx
  int v12; // ecx
  __int16 *v13; // rdx
  HANDLE FirstFileW; // rsi
  signed int v15; // eax
  const wchar_t *v16; // rdx
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  const wchar_t *v23; // rdx
  int v24; // eax
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v29; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v31[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 cFileName; // [rsp+70h] [rbp-90h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+2D0h] [rbp+1D0h] BYREF

  v5 = -1;
  lpFileName[0] = v31;
  lpFileName[1] = v31;
  v31[0] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002C000, (unsigned __int8 *)byte_1400261C1, 0, 0, 2u, &v34);
    if ( lpFileName[0] != v31 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942487LL;
  }
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    if ( (unsigned int)dword_14002C000 <= 2 )
      goto LABEL_72;
    v12 = qword_14002C018;
    if ( (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
      goto LABEL_72;
    v28 = v11;
    v13 = (__int16 *)byte_140026175;
    goto LABEL_18;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    v11 = -2147024809;
    if ( (unsigned int)dword_14002C000 <= 2 )
      goto LABEL_72;
    v12 = qword_14002C018;
    if ( (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
      goto LABEL_72;
    v28 = -2147024809;
    v13 = word_14002612A;
LABEL_18:
    v29 = a1;
    goto LABEL_19;
  }
  if ( (FileAttributesW & 0x400) != 0 )
  {
    v11 = -2147024809;
    if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      v29 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_14002C018,
        (unsigned int)byte_1400260E9,
        v8,
        v9,
        (__int64)&v29);
    }
    goto LABEL_72;
  }
  if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName, L"%ls\\*", a1) < 0 )
  {
    v11 = -2147024809;
    if ( (unsigned int)dword_14002C000 <= 2 )
      goto LABEL_72;
    v12 = qword_14002C018;
    if ( (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
      goto LABEL_72;
    v28 = -2147024809;
    v13 = word_1400260A2;
    goto LABEL_18;
  }
  FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
  v5 = (__int64)FirstFileW;
  cFileName = (__int64)FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v15 = GetLastError();
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    if ( (unsigned int)dword_14002C000 <= 2 )
      goto LABEL_72;
    v12 = qword_14002C018;
    if ( (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
      goto LABEL_72;
    v28 = v11;
    v29 = lpFileName[0];
    v13 = word_14002605A;
LABEL_19:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v13,
      v8,
      v9,
      (__int64)&v29,
      (__int64)&v28);
    goto LABEL_72;
  }
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] != 46
      || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
    {
      v11 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              lpFileName,
              L"%ls\\%ls",
              a1,
              FindFileData.cFileName);
      if ( v11 < 0 )
      {
        if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
        {
          v28 = v11;
          cFileName = (__int64)FindFileData.cFileName;
          v29 = a1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            qword_14002C018,
            (unsigned int)&unk_140026008,
            v17,
            v18,
            (__int64)&v29,
            (__int64)&cFileName,
            (__int64)&v28);
        }
        goto LABEL_72;
      }
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v19 = _werDetail::PreparePathForDeletion(lpFileName[0], v16);
        if ( v19 < 0 && (unsigned int)dword_14002C000 > 3 && (qword_14002C010 & 8) != 0 )
        {
          v22 = qword_14002C018 & 8;
          if ( v22 == qword_14002C018 )
          {
            v28 = v19;
            v29 = lpFileName[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)byte_140025F79,
              v20,
              v21,
              (__int64)&v29,
              (__int64)&v28);
          }
        }
        UtilDeleteFilePath((WCHAR *)lpFileName[0]);
        goto LABEL_61;
      }
      v11 = UtilRecursiveRemoveDirectory(lpFileName[0], 1, 0, 0, 0);
      if ( v11 < 0 )
        break;
    }
LABEL_61:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v5 = -1;
      cFileName = -1;
      FindClose(FirstFileW);
      v24 = _werDetail::PreparePathForDeletion(a1, v23);
      if ( v24 < 0 && (unsigned int)dword_14002C000 > 3 && (qword_14002C010 & 8) != 0 )
      {
        v27 = qword_14002C018 & 8;
        if ( v27 == qword_14002C018 )
        {
          v28 = v24;
          v29 = a1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v27,
            (unsigned int)word_140025F32,
            v25,
            v26,
            (__int64)&v29,
            (__int64)&v28);
        }
      }
      UtilDeleteFilePath(a1);
      v11 = 0;
      goto LABEL_72;
    }
  }
  if ( (unsigned int)dword_14002C000 > 2 )
  {
    v12 = qword_14002C018;
    if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      v28 = v11;
      v29 = lpFileName[0];
      v13 = (__int16 *)&unk_140025FC0;
      goto LABEL_19;
    }
  }
LABEL_72:
  if ( lpFileName[0] != v31 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 != -1 )
    FindClose((HANDLE)v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000be08  push    rbp
0x14000be0a  push    rbx
0x14000be0b  push    rsi
0x14000be0c  push    rdi
0x14000be0d  push    r14
0x14000be0f  push    r15
0x14000be11  lea     rbp, [rsp-208h]
0x14000be19  sub     rsp, 308h
0x14000be20  mov     rax, cs:__security_cookie
0x14000be27  xor     rax, rsp
0x14000be2a  mov     [rbp+230h+var_40], rax
0x14000be31  mov     rdi, rcx
0x14000be34  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000be38  lea     rax, [rsp+330h+var_2D0]
0x14000be3d  mov     [rsp+330h+lpFileName], rax
0x14000be42  lea     rax, [rsp+330h+var_2D0]
0x14000be47  mov     [rsp+330h+var_2D8], rax
0x14000be4c  xor     r15d, r15d
0x14000be4f  mov     [rsp+330h+var_2D0], r15w
0x14000be55  xor     edx, edx; Val
0x14000be57  mov     r8d, 250h; Size
0x14000be5d  lea     rcx, [rbp+230h+FindFileData]; void *
0x14000be61  call    memset_0
0x14000be66  test    rdi, rdi
0x14000be69  jnz     short loc_14000BEE7
0x14000be6b  mov     eax, cs:dword_14002C000
0x14000be71  cmp     eax, 2
0x14000be74  jbe     short loc_14000BEC1
0x14000be76  mov     rcx, cs:qword_14002C018
0x14000be7d  mov     rax, cs:qword_14002C010
0x14000be84  test    al, 8
0x14000be86  jz      short loc_14000BEC1
0x14000be88  mov     rax, rcx
0x14000be8b  and     eax, 8
0x14000be8e  cmp     rax, rcx
0x14000be91  jnz     short loc_14000BEC1
0x14000be93  lea     rax, [rbp+230h+var_60]
0x14000be9a  mov     [rsp+330h+var_308], rax
0x14000be9f  mov     [rsp+330h+var_310], 2
0x14000bea7  xor     r9d, r9d
0x14000beaa  xor     r8d, r8d
0x14000bead  lea     rdx, byte_1400261C1
0x14000beb4  lea     rcx, dword_14002C000
0x14000bebb  call    _tlgWriteTransfer_EventWriteTransfer
0x14000bec0  nop
0x14000bec1  lea     rax, [rsp+330h+var_2D0]
0x14000bec6  mov     rcx, [rsp+330h+lpFileName]; void *
0x14000becb  cmp     rcx, rax
0x14000bece  jz      short loc_14000BEDD
0x14000bed0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bed7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000bedc  nop
0x14000bedd  mov     eax, 80070057h
0x14000bee2  jmp     loc_14000C36C
0x14000bee7  mov     rcx, rdi; lpFileName
0x14000beea  call    cs:__imp_GetFileAttributesW
0x14000bef0  cmp     eax, 0FFFFFFFFh
0x14000bef3  jnz     loc_14000BF7A
0x14000bef9  call    cs:__imp_GetLastError
0x14000beff  mov     ebx, eax
0x14000bf01  test    eax, eax
0x14000bf03  jle     short loc_14000BF0E
0x14000bf05  movzx   ebx, ax
0x14000bf08  or      ebx, 80070000h
0x14000bf0e  mov     eax, 80004005h
0x14000bf13  test    ebx, ebx
0x14000bf15  cmovns  ebx, eax
0x14000bf18  mov     eax, cs:dword_14002C000
0x14000bf1e  cmp     eax, 2
0x14000bf21  jbe     loc_14000C33F
0x14000bf27  mov     rcx, cs:qword_14002C018
0x14000bf2e  mov     rax, cs:qword_14002C010
0x14000bf35  test    al, 8
0x14000bf37  jz      loc_14000C33F
0x14000bf3d  mov     rax, rcx
0x14000bf40  and     eax, 8
0x14000bf43  cmp     rax, rcx
0x14000bf46  jnz     loc_14000C33F
0x14000bf4c  mov     [rsp+330h+var_2F0], ebx
0x14000bf50  lea     rdx, byte_140026175
0x14000bf57  mov     [rsp+330h+var_2E8], rdi
0x14000bf5c  lea     rax, [rsp+330h+var_2F0]
0x14000bf61  mov     [rsp+330h+var_308], rax
0x14000bf66  lea     rax, [rsp+330h+var_2E8]
0x14000bf6b  mov     qword ptr [rsp+330h+var_310], rax
0x14000bf70  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x14000bf75  jmp     loc_14000C33F
0x14000bf7a  test    al, 10h
0x14000bf7c  jnz     short loc_14000BFC8
0x14000bf7e  mov     ebx, 80070057h
0x14000bf83  mov     eax, cs:dword_14002C000
0x14000bf89  cmp     eax, 2
0x14000bf8c  jbe     loc_14000C33F
0x14000bf92  mov     rcx, cs:qword_14002C018
0x14000bf99  mov     rax, cs:qword_14002C010
0x14000bfa0  test    al, 8
0x14000bfa2  jz      loc_14000C33F
0x14000bfa8  mov     rax, rcx
0x14000bfab  and     eax, 8
0x14000bfae  cmp     rax, rcx
0x14000bfb1  jnz     loc_14000C33F
0x14000bfb7  mov     [rsp+330h+var_2F0], 80070057h
0x14000bfbf  lea     rdx, word_14002612A
0x14000bfc6  jmp     short loc_14000BF57
0x14000bfc8  bt      eax, 0Ah
0x14000bfcc  jnb     short loc_14000C027
0x14000bfce  mov     ebx, 80070057h
0x14000bfd3  mov     eax, cs:dword_14002C000
0x14000bfd9  cmp     eax, 2
0x14000bfdc  jbe     loc_14000C33F
0x14000bfe2  mov     rcx, cs:qword_14002C018
0x14000bfe9  mov     rax, cs:qword_14002C010
0x14000bff0  test    al, 8
0x14000bff2  jz      loc_14000C33F
0x14000bff8  mov     rax, rcx
0x14000bffb  and     eax, 8
0x14000bffe  cmp     rax, rcx
0x14000c001  jnz     loc_14000C33F
0x14000c007  mov     [rsp+330h+var_2E8], rdi
0x14000c00c  lea     rax, [rsp+330h+var_2E8]
0x14000c011  mov     qword ptr [rsp+330h+var_310], rax
0x14000c016  lea     rdx, byte_1400260E9
0x14000c01d  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14000c022  jmp     loc_14000C33F
0x14000c027  mov     r8, rdi
0x14000c02a  lea     rdx, aLs; "%ls\\*"
0x14000c031  lea     rcx, [rsp+330h+lpFileName]
0x14000c036  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14000c03b  test    eax, eax
0x14000c03d  jns     short loc_14000C08C
0x14000c03f  mov     ebx, 80070057h
0x14000c044  mov     eax, cs:dword_14002C000
0x14000c04a  cmp     eax, 2
0x14000c04d  jbe     loc_14000C33F
0x14000c053  mov     rcx, cs:qword_14002C018
0x14000c05a  mov     rax, cs:qword_14002C010
0x14000c061  test    al, 8
0x14000c063  jz      loc_14000C33F
0x14000c069  mov     rax, rcx
0x14000c06c  and     eax, 8
0x14000c06f  cmp     rax, rcx
0x14000c072  jnz     loc_14000C33F
0x14000c078  mov     [rsp+330h+var_2F0], 80070057h
0x14000c080  lea     rdx, word_1400260A2
0x14000c087  jmp     loc_14000BF57
0x14000c08c  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x14000c090  mov     rcx, [rsp+330h+lpFileName]; lpFileName
0x14000c095  call    cs:__imp_FindFirstFileW
0x14000c09b  mov     rsi, rax
0x14000c09e  mov     r14, rax
0x14000c0a1  mov     [rsp+330h+var_2C0], rax
0x14000c0a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c0aa  jnz     short loc_14000C119
0x14000c0ac  call    cs:__imp_GetLastError
0x14000c0b2  mov     ebx, eax
0x14000c0b4  test    eax, eax
0x14000c0b6  jle     short loc_14000C0C1
0x14000c0b8  movzx   ebx, ax
0x14000c0bb  or      ebx, 80070000h
0x14000c0c1  mov     eax, 80004005h
0x14000c0c6  test    ebx, ebx
0x14000c0c8  cmovns  ebx, eax
0x14000c0cb  mov     eax, cs:dword_14002C000
0x14000c0d1  cmp     eax, 2
0x14000c0d4  jbe     loc_14000C33F
0x14000c0da  mov     rcx, cs:qword_14002C018
0x14000c0e1  mov     rax, cs:qword_14002C010
0x14000c0e8  test    al, 8
0x14000c0ea  jz      loc_14000C33F
0x14000c0f0  mov     rax, rcx
0x14000c0f3  and     eax, 8
0x14000c0f6  cmp     rax, rcx
0x14000c0f9  jnz     loc_14000C33F
0x14000c0ff  mov     [rsp+330h+var_2F0], ebx
0x14000c103  mov     rax, [rsp+330h+lpFileName]
0x14000c108  mov     [rsp+330h+var_2E8], rax
0x14000c10d  lea     rdx, word_14002605A
0x14000c114  jmp     loc_14000BF5C
0x14000c119  movzx   eax, [rbp+230h+FindFileData.cFileName+2]
0x14000c11d  cmp     [rbp+230h+FindFileData.cFileName], 2Eh ; '.'
0x14000c122  jnz     short loc_14000C145
0x14000c124  test    ax, ax
0x14000c127  jz      loc_14000C248
0x14000c12d  cmp     [rbp+230h+FindFileData.cFileName], 2Eh ; '.'
0x14000c132  jnz     short loc_14000C145
0x14000c134  cmp     ax, 2Eh ; '.'
0x14000c138  jnz     short loc_14000C145
0x14000c13a  cmp     [rbp+230h+FindFileData.cFileName+4], r15w
0x14000c13f  jz      loc_14000C248
0x14000c145  lea     r9, [rbp+230h+FindFileData.cFileName]
0x14000c149  mov     r8, rdi
0x14000c14c  lea     rdx, aLsLs; "%ls\\%ls"
0x14000c153  lea     rcx, [rsp+330h+lpFileName]
0x14000c158  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x14000c15d  mov     ebx, eax
0x14000c15f  test    eax, eax
0x14000c161  js      loc_14000C2DA
0x14000c167  mov     rcx, [rsp+330h+lpFileName]; lpFileName
0x14000c16c  test    byte ptr [rbp+230h+FindFileData.dwFileAttributes], 10h
0x14000c170  jz      short loc_14000C1DE
0x14000c172  mov     [rsp+330h+var_310], r15d; int
0x14000c177  xor     r9d, r9d; wchar_t *
0x14000c17a  xor     r8d, r8d; wchar_t *
0x14000c17d  lea     edx, [r9+1]; int
0x14000c181  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x14000c186  mov     ebx, eax
0x14000c188  test    eax, eax
0x14000c18a  jns     loc_14000C248
0x14000c190  mov     eax, cs:dword_14002C000
0x14000c196  cmp     eax, 2
0x14000c199  jbe     loc_14000C33F
0x14000c19f  mov     rcx, cs:qword_14002C018
0x14000c1a6  mov     rax, cs:qword_14002C010
0x14000c1ad  test    al, 8
0x14000c1af  jz      loc_14000C33F
0x14000c1b5  mov     rax, rcx
0x14000c1b8  and     eax, 8
0x14000c1bb  cmp     rax, rcx
0x14000c1be  jnz     loc_14000C33F
0x14000c1c4  mov     [rsp+330h+var_2F0], ebx
0x14000c1c8  mov     rax, [rsp+330h+lpFileName]
0x14000c1cd  mov     [rsp+330h+var_2E8], rax
0x14000c1d2  lea     rdx, unk_140025FC0
0x14000c1d9  jmp     loc_14000BF5C
0x14000c1de  call    ?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z; _werDetail::PreparePathForDeletion(wchar_t const *)
0x14000c1e3  test    eax, eax
0x14000c1e5  jns     short loc_14000C23E
0x14000c1e7  mov     ecx, cs:dword_14002C000
0x14000c1ed  cmp     ecx, 3
0x14000c1f0  jbe     short loc_14000C23E
0x14000c1f2  mov     rdx, cs:qword_14002C018
0x14000c1f9  mov     rcx, cs:qword_14002C010
0x14000c200  test    cl, 8
0x14000c203  jz      short loc_14000C23E
0x14000c205  mov     rcx, rdx
0x14000c208  and     ecx, 8
0x14000c20b  cmp     rcx, rdx
0x14000c20e  jnz     short loc_14000C23E
0x14000c210  mov     [rsp+330h+var_2F0], eax
0x14000c214  mov     rax, [rsp+330h+lpFileName]
0x14000c219  mov     [rsp+330h+var_2E8], rax
0x14000c21e  lea     rax, [rsp+330h+var_2F0]
0x14000c223  mov     [rsp+330h+var_308], rax
0x14000c228  lea     rax, [rsp+330h+var_2E8]
0x14000c22d  mov     qword ptr [rsp+330h+var_310], rax
0x14000c232  lea     rdx, byte_140025F79
0x14000c239  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x14000c23e  mov     rcx, [rsp+330h+lpFileName]; wchar_t *
0x14000c243  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x14000c248  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x14000c24c  mov     rcx, rsi; hFindFile
0x14000c24f  call    cs:__imp_FindNextFileW
0x14000c255  test    eax, eax
0x14000c257  jnz     loc_14000C119
0x14000c25d  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000c261  mov     [rsp+330h+var_2C0], r14
0x14000c266  mov     rcx, rsi; hFindFile
0x14000c269  call    cs:__imp_FindClose
0x14000c26f  mov     rcx, rdi; lpFileName
0x14000c272  call    ?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z; _werDetail::PreparePathForDeletion(wchar_t const *)
0x14000c277  test    eax, eax
0x14000c279  jns     short loc_14000C2CD
0x14000c27b  mov     ecx, cs:dword_14002C000
0x14000c281  cmp     ecx, 3
0x14000c284  jbe     short loc_14000C2CD
0x14000c286  mov     rdx, cs:qword_14002C018
0x14000c28d  mov     rcx, cs:qword_14002C010
0x14000c294  test    cl, 8
0x14000c297  jz      short loc_14000C2CD
0x14000c299  mov     rcx, rdx
0x14000c29c  and     ecx, 8
0x14000c29f  cmp     rcx, rdx
0x14000c2a2  jnz     short loc_14000C2CD
0x14000c2a4  mov     [rsp+330h+var_2F0], eax
0x14000c2a8  mov     [rsp+330h+var_2E8], rdi
0x14000c2ad  lea     rax, [rsp+330h+var_2F0]
0x14000c2b2  mov     [rsp+330h+var_308], rax
0x14000c2b7  lea     rax, [rsp+330h+var_2E8]
0x14000c2bc  mov     qword ptr [rsp+330h+var_310], rax
0x14000c2c1  lea     rdx, word_140025F32
0x14000c2c8  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x14000c2cd  mov     rcx, rdi; wchar_t *
0x14000c2d0  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x14000c2d5  mov     ebx, r15d
0x14000c2d8  jmp     short loc_14000C33F
0x14000c2da  mov     eax, cs:dword_14002C000
0x14000c2e0  cmp     eax, 2
0x14000c2e3  jbe     short loc_14000C33F
0x14000c2e5  mov     rcx, cs:qword_14002C018
0x14000c2ec  mov     rax, cs:qword_14002C010
0x14000c2f3  test    al, 8
0x14000c2f5  jz      short loc_14000C33F
0x14000c2f7  mov     rax, rcx
0x14000c2fa  and     eax, 8
0x14000c2fd  cmp     rax, rcx
0x14000c300  jnz     short loc_14000C33F
0x14000c302  mov     [rsp+330h+var_2F0], ebx
0x14000c306  lea     rax, [rbp+230h+FindFileData.cFileName]
0x14000c30a  mov     [rsp+330h+var_2C0], rax
0x14000c30f  mov     [rsp+330h+var_2E8], rdi
  ... truncated ...
```
