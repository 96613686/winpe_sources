# UtilRecursiveRemoveDirectory(ushort const *,int,ushort const *,ushort const *,int)

- ea: `0x18000576c`
- end: `0x180005c22`
- name: `?UtilRecursiveRemoveDirectory@@YAJPEBGH00H@Z`
- size: `1206`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180003ab0`
- `0x18000576c`

## callees

- `0x180001008`
- `0x180001178`
- `0x180001270`
- `0x18000131c`
- `0x180001680`
- `0x180002938`
- `0x18000440c`
- `0x18000576c`
- `0x18001218a`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800059fc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800059fc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180005b43`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180005b43`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005851`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005851`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005b58`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005bf3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005b58`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005bf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a0b`

## pseudocode

```c
__int64 __fastcall UtilRecursiveRemoveDirectory(
        WCHAR *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 FirstFileW; // rbx
  DWORD FileAttributesW; // eax
  int v8; // r8d
  int v9; // r9d
  signed int LastError; // eax
  signed int v11; // edi
  int v12; // ecx
  __int16 *v13; // rdx
  signed int v14; // eax
  int v15; // r8d
  int v16; // r9d
  void *v17; // rcx
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *cFileName; // [rsp+48h] [rbp-B8h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v21[8]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v22; // [rsp+70h] [rbp-90h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+2D0h] [rbp+1D0h] BYREF

  Block[0] = v21;
  Block[1] = v21;
  v21[0] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001C008, (unsigned __int8 *)byte_1800184C1, 0, 0, 2u, &v24);
    if ( Block[0] != v21 )
      operator delete(Block[0]);
    return 2147942487LL;
  }
  FirstFileW = -1;
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    if ( (unsigned int)dword_18001C008 <= 2 )
      goto LABEL_62;
    v12 = qword_18001C020;
    if ( (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
      goto LABEL_62;
    v18 = v11;
    v13 = word_1800184F2;
    goto LABEL_18;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    v11 = -2147024809;
    if ( (unsigned int)dword_18001C008 <= 2 )
      goto LABEL_62;
    v12 = qword_18001C020;
    if ( (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
      goto LABEL_62;
    v18 = -2147024809;
    v13 = (__int16 *)byte_180018809;
LABEL_18:
    cFileName = a1;
    goto LABEL_19;
  }
  if ( (FileAttributesW & 0x400) != 0 )
  {
    v11 = -2147024809;
    if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      cFileName = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        qword_18001C020,
        (unsigned int)&dword_1800185B4,
        v8,
        v9,
        (__int64)&cFileName);
    }
    goto LABEL_62;
  }
  if ( (int)tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
              Block,
              L"%ls\\*",
              a1) < 0 )
  {
    v11 = -2147024809;
    if ( (unsigned int)dword_18001C008 <= 2 )
      goto LABEL_62;
    v12 = qword_18001C020;
    if ( (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
      goto LABEL_62;
    v18 = -2147024809;
    v13 = &word_180018A96;
    goto LABEL_18;
  }
  FirstFileW = (__int64)FindFirstFileW((LPCWSTR)Block[0], &FindFileData);
  if ( FirstFileW == -1 )
  {
    v14 = GetLastError();
    v11 = v14;
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
    if ( (unsigned int)dword_18001C008 <= 2 )
      goto LABEL_62;
    v12 = qword_18001C020;
    if ( (qword_18001C018 & 8) == 0 || (qword_18001C020 & 8) != qword_18001C020 )
      goto LABEL_62;
    v13 = (__int16 *)&dword_180018744;
    cFileName = (WCHAR *)Block[0];
    v18 = v11;
LABEL_19:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v13,
      v8,
      v9,
      (__int64)&cFileName,
      (__int64)&v18);
    goto LABEL_62;
  }
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_56;
    }
    v11 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
            Block,
            L"%ls\\%ls",
            a1,
            FindFileData.cFileName);
    if ( v11 < 0 )
    {
      if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
      {
        v18 = v11;
        cFileName = FindFileData.cFileName;
        v22 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          qword_18001C020,
          (unsigned int)byte_180018401,
          v15,
          v16,
          (__int64)&v22,
          (__int64)&cFileName,
          (__int64)&v18);
      }
      goto LABEL_62;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      UtilDeleteFilePath((WCHAR *)Block[0]);
      goto LABEL_56;
    }
    v11 = UtilRecursiveRemoveDirectory((const unsigned __int16 *)Block[0], 0, 0, 0, 0);
    if ( v11 < 0 )
      break;
LABEL_56:
    if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
    {
      v17 = (void *)FirstFileW;
      FirstFileW = -1;
      FindClose(v17);
      UtilDeleteFilePath(a1);
      v11 = 0;
      goto LABEL_62;
    }
  }
  if ( (unsigned int)dword_18001C008 > 2 )
  {
    v12 = qword_18001C020;
    if ( (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      v13 = (__int16 *)byte_180018B4D;
      cFileName = (WCHAR *)Block[0];
      v18 = v11;
      goto LABEL_19;
    }
  }
LABEL_62:
  if ( Block[0] != v21 )
    operator delete(Block[0]);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000576c  mov     [rsp-8+arg_8], rbx
0x180005771  mov     [rsp-8+arg_10], rsi
0x180005776  push    rbp
0x180005777  push    rdi
0x180005778  push    r14
0x18000577a  lea     rbp, [rsp-200h]
0x180005782  sub     rsp, 300h
0x180005789  mov     rax, cs:__security_cookie
0x180005790  xor     rax, rsp
0x180005793  mov     [rbp+210h+var_20], rax
0x18000579a  lea     rax, [rsp+310h+var_2B0]
0x18000579f  mov     rsi, rcx
0x1800057a2  mov     [rsp+310h+Block], rax
0x1800057a7  lea     rcx, [rbp+210h+FindFileData]; void *
0x1800057ab  lea     rax, [rsp+310h+var_2B0]
0x1800057b0  xor     r14d, r14d
0x1800057b3  xor     edx, edx; Val
0x1800057b5  mov     [rsp+310h+var_2B8], rax
0x1800057ba  mov     r8d, 250h; Size
0x1800057c0  mov     [rsp+310h+var_2B0], r14w
0x1800057c6  call    memset_0
0x1800057cb  test    rsi, rsi
0x1800057ce  jnz     short loc_18000584A
0x1800057d0  mov     eax, cs:dword_18001C008
0x1800057d6  cmp     eax, 2
0x1800057d9  jbe     short loc_180005825
0x1800057db  mov     rcx, cs:qword_18001C020
0x1800057e2  mov     rax, cs:qword_18001C018
0x1800057e9  test    al, 8
0x1800057eb  jz      short loc_180005825
0x1800057ed  mov     rax, rcx
0x1800057f0  and     eax, 8
0x1800057f3  cmp     rax, rcx
0x1800057f6  jnz     short loc_180005825
0x1800057f8  lea     rax, [rbp+210h+var_40]
0x1800057ff  xor     r9d, r9d
0x180005802  mov     [rsp+310h+var_2E8], rax
0x180005807  lea     rdx, byte_1800184C1
0x18000580e  xor     r8d, r8d
0x180005811  mov     [rsp+310h+var_2F0], 2
0x180005819  lea     rcx, dword_18001C008
0x180005820  call    _tlgWriteTransfer_EventWriteTransfer
0x180005825  mov     rcx, [rsp+310h+Block]; Block
0x18000582a  lea     rax, [rsp+310h+var_2B0]
0x18000582f  cmp     rcx, rax
0x180005832  jz      short loc_180005840
0x180005834  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000583b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005840  mov     eax, 80070057h
0x180005845  jmp     loc_180005BFB
0x18000584a  mov     rcx, rsi; lpFileName
0x18000584d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005851  call    cs:__imp_GetFileAttributesW
0x180005857  cmp     eax, 0FFFFFFFFh
0x18000585a  jnz     loc_1800058E1
0x180005860  call    cs:__imp_GetLastError
0x180005866  mov     edi, eax
0x180005868  test    eax, eax
0x18000586a  jle     short loc_180005875
0x18000586c  movzx   edi, ax
0x18000586f  or      edi, 80070000h
0x180005875  test    edi, edi
0x180005877  mov     eax, 80004005h
0x18000587c  cmovns  edi, eax
0x18000587f  mov     eax, cs:dword_18001C008
0x180005885  cmp     eax, 2
0x180005888  jbe     loc_180005BCF
0x18000588e  mov     rcx, cs:qword_18001C020
0x180005895  mov     rax, cs:qword_18001C018
0x18000589c  test    al, 8
0x18000589e  jz      loc_180005BCF
0x1800058a4  mov     rax, rcx
0x1800058a7  and     eax, 8
0x1800058aa  cmp     rax, rcx
0x1800058ad  jnz     loc_180005BCF
0x1800058b3  mov     [rsp+310h+var_2D0], edi
0x1800058b7  lea     rdx, word_1800184F2
0x1800058be  mov     [rsp+310h+var_2C8], rsi
0x1800058c3  lea     rax, [rsp+310h+var_2D0]
0x1800058c8  mov     [rsp+310h+var_2E8], rax
0x1800058cd  lea     rax, [rsp+310h+var_2C8]
0x1800058d2  mov     qword ptr [rsp+310h+var_2F0], rax
0x1800058d7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800058dc  jmp     loc_180005BCF
0x1800058e1  test    al, 10h
0x1800058e3  jnz     short loc_18000592F
0x1800058e5  mov     eax, cs:dword_18001C008
0x1800058eb  mov     edi, 80070057h
0x1800058f0  cmp     eax, 2
0x1800058f3  jbe     loc_180005BCF
0x1800058f9  mov     rcx, cs:qword_18001C020
0x180005900  mov     rax, cs:qword_18001C018
0x180005907  test    al, 8
0x180005909  jz      loc_180005BCF
0x18000590f  mov     rax, rcx
0x180005912  and     eax, 8
0x180005915  cmp     rax, rcx
0x180005918  jnz     loc_180005BCF
0x18000591e  mov     [rsp+310h+var_2D0], 80070057h
0x180005926  lea     rdx, byte_180018809
0x18000592d  jmp     short loc_1800058BE
0x18000592f  bt      eax, 0Ah
0x180005933  jnb     short loc_18000598E
0x180005935  mov     eax, cs:dword_18001C008
0x18000593b  mov     edi, 80070057h
0x180005940  cmp     eax, 2
0x180005943  jbe     loc_180005BCF
0x180005949  mov     rcx, cs:qword_18001C020
0x180005950  mov     rax, cs:qword_18001C018
0x180005957  test    al, 8
0x180005959  jz      loc_180005BCF
0x18000595f  mov     rax, rcx
0x180005962  and     eax, 8
0x180005965  cmp     rax, rcx
0x180005968  jnz     loc_180005BCF
0x18000596e  lea     rax, [rsp+310h+var_2C8]
0x180005973  mov     [rsp+310h+var_2C8], rsi
0x180005978  lea     rdx, dword_1800185B4
0x18000597f  mov     qword ptr [rsp+310h+var_2F0], rax
0x180005984  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180005989  jmp     loc_180005BCF
0x18000598e  mov     r8, rsi
0x180005991  lea     rdx, aLs; "%ls\\*"
0x180005998  lea     rcx, [rsp+310h+Block]
0x18000599d  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800059a2  test    eax, eax
0x1800059a4  jns     short loc_1800059F3
0x1800059a6  mov     eax, cs:dword_18001C008
0x1800059ac  mov     edi, 80070057h
0x1800059b1  cmp     eax, 2
0x1800059b4  jbe     loc_180005BCF
0x1800059ba  mov     rcx, cs:qword_18001C020
0x1800059c1  mov     rax, cs:qword_18001C018
0x1800059c8  test    al, 8
0x1800059ca  jz      loc_180005BCF
0x1800059d0  mov     rax, rcx
0x1800059d3  and     eax, 8
0x1800059d6  cmp     rax, rcx
0x1800059d9  jnz     loc_180005BCF
0x1800059df  mov     [rsp+310h+var_2D0], 80070057h
0x1800059e7  lea     rdx, word_180018A96
0x1800059ee  jmp     loc_1800058BE
0x1800059f3  mov     rcx, [rsp+310h+Block]; lpFileName
0x1800059f8  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x1800059fc  call    cs:__imp_FindFirstFileW
0x180005a02  mov     rbx, rax
0x180005a05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005a09  jnz     short loc_180005A78
0x180005a0b  call    cs:__imp_GetLastError
0x180005a11  mov     edi, eax
0x180005a13  test    eax, eax
0x180005a15  jle     short loc_180005A20
0x180005a17  movzx   edi, ax
0x180005a1a  or      edi, 80070000h
0x180005a20  test    edi, edi
0x180005a22  mov     eax, 80004005h
0x180005a27  cmovns  edi, eax
0x180005a2a  mov     eax, cs:dword_18001C008
0x180005a30  cmp     eax, 2
0x180005a33  jbe     loc_180005BCF
0x180005a39  mov     rcx, cs:qword_18001C020
0x180005a40  mov     rax, cs:qword_18001C018
0x180005a47  test    al, 8
0x180005a49  jz      loc_180005BCF
0x180005a4f  mov     rax, rcx
0x180005a52  and     eax, 8
0x180005a55  cmp     rax, rcx
0x180005a58  jnz     loc_180005BCF
0x180005a5e  mov     rax, [rsp+310h+Block]
0x180005a63  lea     rdx, dword_180018744
0x180005a6a  mov     [rsp+310h+var_2C8], rax
0x180005a6f  mov     [rsp+310h+var_2D0], edi
0x180005a73  jmp     loc_1800058C3
0x180005a78  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x180005a7d  movzx   eax, [rbp+210h+FindFileData.cFileName+2]
0x180005a81  jnz     short loc_180005AA4
0x180005a83  test    ax, ax
0x180005a86  jz      loc_180005B3C
0x180005a8c  cmp     [rbp+210h+FindFileData.cFileName], 2Eh ; '.'
0x180005a91  jnz     short loc_180005AA4
0x180005a93  cmp     ax, 2Eh ; '.'
0x180005a97  jnz     short loc_180005AA4
0x180005a99  cmp     [rbp+210h+FindFileData.cFileName+4], r14w
0x180005a9e  jz      loc_180005B3C
0x180005aa4  lea     r9, [rbp+210h+FindFileData.cFileName]
0x180005aa8  mov     r8, rsi
0x180005aab  lea     rdx, aLsLs; "%ls\\%ls"
0x180005ab2  lea     rcx, [rsp+310h+Block]
0x180005ab7  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180005abc  mov     edi, eax
0x180005abe  test    eax, eax
0x180005ac0  js      loc_180005B6B
0x180005ac6  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x180005aca  mov     rcx, [rsp+310h+Block]; unsigned __int16 *
0x180005acf  jz      short loc_180005B37
0x180005ad1  xor     r9d, r9d; unsigned __int16 *
0x180005ad4  mov     [rsp+310h+var_2F0], r14d; int
0x180005ad9  xor     r8d, r8d; unsigned __int16 *
0x180005adc  xor     edx, edx; int
0x180005ade  call    ?UtilRecursiveRemoveDirectory@@YAJPEBGH00H@Z; UtilRecursiveRemoveDirectory(ushort const *,int,ushort const *,ushort const *,int)
0x180005ae3  mov     edi, eax
0x180005ae5  test    eax, eax
0x180005ae7  jns     short loc_180005B3C
0x180005ae9  mov     eax, cs:dword_18001C008
0x180005aef  cmp     eax, 2
0x180005af2  jbe     loc_180005BCF
0x180005af8  mov     rcx, cs:qword_18001C020
0x180005aff  mov     rax, cs:qword_18001C018
0x180005b06  test    al, 8
0x180005b08  jz      loc_180005BCF
0x180005b0e  mov     rax, rcx
0x180005b11  and     eax, 8
0x180005b14  cmp     rax, rcx
0x180005b17  jnz     loc_180005BCF
0x180005b1d  mov     rax, [rsp+310h+Block]
0x180005b22  lea     rdx, byte_180018B4D
0x180005b29  mov     [rsp+310h+var_2C8], rax
0x180005b2e  mov     [rsp+310h+var_2D0], edi
0x180005b32  jmp     loc_1800058C3
0x180005b37  call    ?UtilDeleteFilePath@@YAJPEBG@Z; UtilDeleteFilePath(ushort const *)
0x180005b3c  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x180005b40  mov     rcx, rbx; hFindFile
0x180005b43  call    cs:__imp_FindNextFileW
0x180005b49  test    eax, eax
0x180005b4b  jnz     loc_180005A78
0x180005b51  mov     rcx, rbx; hFindFile
0x180005b54  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005b58  call    cs:__imp_FindClose
0x180005b5e  mov     rcx, rsi; unsigned __int16 *
0x180005b61  call    ?UtilDeleteFilePath@@YAJPEBG@Z; UtilDeleteFilePath(ushort const *)
0x180005b66  mov     edi, r14d
0x180005b69  jmp     short loc_180005BCF
0x180005b6b  mov     eax, cs:dword_18001C008
0x180005b71  cmp     eax, 2
0x180005b74  jbe     short loc_180005BCF
0x180005b76  mov     rcx, cs:qword_18001C020
0x180005b7d  mov     rax, cs:qword_18001C018
0x180005b84  test    al, 8
0x180005b86  jz      short loc_180005BCF
0x180005b88  mov     rax, rcx
0x180005b8b  and     eax, 8
0x180005b8e  cmp     rax, rcx
0x180005b91  jnz     short loc_180005BCF
0x180005b93  lea     rax, [rbp+210h+FindFileData.cFileName]
0x180005b97  mov     [rsp+310h+var_2D0], edi
0x180005b9b  mov     [rsp+310h+var_2C8], rax
0x180005ba0  lea     rdx, byte_180018401
0x180005ba7  lea     rax, [rsp+310h+var_2D0]
0x180005bac  mov     [rsp+310h+var_2A0], rsi
0x180005bb1  mov     [rsp+310h+var_2E0], rax
0x180005bb6  lea     rax, [rsp+310h+var_2C8]
0x180005bbb  mov     [rsp+310h+var_2E8], rax
0x180005bc0  lea     rax, [rsp+310h+var_2A0]
0x180005bc5  mov     qword ptr [rsp+310h+var_2F0], rax
0x180005bca  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180005bcf  mov     rcx, [rsp+310h+Block]; Block
0x180005bd4  lea     rax, [rsp+310h+var_2B0]
0x180005bd9  cmp     rcx, rax
0x180005bdc  jz      short loc_180005BEA
0x180005bde  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180005be5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005bea  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005bee  jz      short loc_180005BF9
0x180005bf0  mov     rcx, rbx; hFindFile
0x180005bf3  call    cs:__imp_FindClose
0x180005bf9  mov     eax, edi
0x180005bfb  mov     rcx, [rbp+210h+var_20]
0x180005c02  xor     rcx, rsp; StackCookie
0x180005c05  call    __security_check_cookie
0x180005c0a  lea     r11, [rsp+310h+var_10]
0x180005c12  mov     rbx, [r11+28h]
0x180005c16  mov     rsi, [r11+30h]
0x180005c1a  mov     rsp, r11
0x180005c1d  pop     r14
0x180005c1f  pop     rdi
0x180005c20  pop     rbp
0x180005c21  retn
```
