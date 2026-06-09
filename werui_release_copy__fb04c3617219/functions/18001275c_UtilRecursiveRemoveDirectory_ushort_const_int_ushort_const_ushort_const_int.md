# UtilRecursiveRemoveDirectory(ushort const *,int,ushort const *,ushort const *,int)

- ea: `0x18001275c`
- end: `0x180012b06`
- name: `?UtilRecursiveRemoveDirectory@@YAJPEBGH00H@Z`
- size: `938`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180010df0`
- `0x18001275c`

## callees

- `0x180001234`
- `0x180001300`
- `0x180001350`
- `0x1800014c0`
- `0x180001694`
- `0x180003fe4`
- `0x180005c20`
- `0x180009580`
- `0x18000f690`
- `0x1800115c4`
- `0x18001275c`
- `0x18001378c`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800127ee`
- `KERNEL32!GetFileAttributesW` at `0x1800127ee`
- `KERNEL32!FindFirstFileW` at `0x180012939`
- `KERNEL32!FindFirstFileW` at `0x180012939`
- `KERNEL32!FindNextFileW` at `0x180012a56`
- `KERNEL32!FindNextFileW` at `0x180012a56`
- `KERNEL32!GetLastError` at `0x1800127f9`
- `KERNEL32!GetLastError` at `0x180012954`
- `KERNEL32!GetLastError` at `0x1800127f9`
- `KERNEL32!GetLastError` at `0x180012954`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilRecursiveRemoveDirectory(
        WCHAR *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // ebx
  DWORD FileAttributesW; // eax
  __int64 v9; // rcx
  DWORD LastError; // eax
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int16 *v15; // rdx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rcx
  HANDLE FirstFileW; // rax
  DWORD v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *cFileName; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFindFile; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v33[8]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR *v34; // [rsp+78h] [rbp-88h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  hFindFile = (HANDLE)-1LL;
  lpFileName[0] = v33;
  lpFileName[1] = v33;
  v33[0] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v5, 8) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v6,
        byte_18001C165);
    v7 = -2147024809;
    goto LABEL_44;
  }
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v11, 8) )
      goto LABEL_44;
    v29 = v7;
    v15 = (__int16 *)byte_18001C119;
LABEL_10:
    cFileName = a1;
    goto LABEL_11;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    v7 = -2147024809;
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v9, 8) )
      goto LABEL_44;
    v29 = -2147024809;
    v15 = &word_18001C0CE;
    goto LABEL_10;
  }
  if ( (FileAttributesW & 0x400) != 0 )
  {
    v7 = -2147024809;
    if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v9, 8) )
    {
      cFileName = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v16,
        (unsigned int)byte_18001C08D,
        v17,
        v18,
        (__int64)&cFileName);
    }
    goto LABEL_44;
  }
  if ( (int)tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
              lpFileName,
              L"%ls\\*",
              a1) < 0 )
  {
    v7 = -2147024809;
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v19, 8) )
      goto LABEL_44;
    v29 = -2147024809;
    v15 = &word_18001C046;
    goto LABEL_10;
  }
  FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
  tlx::unique_any<tlx::find_handle_traits>::reset(&hFindFile, FirstFileW);
  if ( hFindFile == (HANDLE)-1LL )
  {
    v21 = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(v21);
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v22, 8) )
      goto LABEL_44;
    v29 = v7;
    cFileName = (WCHAR *)lpFileName[0];
    v15 = &word_18001BFFE;
LABEL_11:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v15,
      v13,
      v14,
      (__int64)&cFileName,
      (__int64)&v29);
    goto LABEL_44;
  }
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_39;
    }
    v7 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
           lpFileName,
           L"%ls\\%ls",
           a1,
           FindFileData.cFileName);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v23, 8) )
      {
        v29 = v7;
        cFileName = FindFileData.cFileName;
        v34 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)&dword_18001BFAC,
          v26,
          v27,
          (__int64)&v34,
          (__int64)&cFileName,
          (__int64)&v29);
      }
      goto LABEL_44;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      UtilDeleteFilePath((WCHAR *)lpFileName[0]);
      goto LABEL_39;
    }
    v7 = UtilRecursiveRemoveDirectory(lpFileName[0], 0, 0, 0, 0);
    if ( v7 < 0 )
      break;
LABEL_39:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
    {
      tlx::unique_any<tlx::find_handle_traits>::reset(&hFindFile, -1);
      UtilDeleteFilePath(a1);
      v7 = 0;
      goto LABEL_44;
    }
  }
  if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v24, 8) )
  {
    v29 = v7;
    cFileName = (WCHAR *)lpFileName[0];
    v15 = (__int16 *)&dword_18001BF64;
    goto LABEL_11;
  }
LABEL_44:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
  tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(&hFindFile);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001275c  push    rbp
0x18001275e  push    rbx
0x18001275f  push    rsi
0x180012760  push    rdi
0x180012761  lea     rbp, [rsp-1E8h]
0x180012769  sub     rsp, 2E8h
0x180012770  mov     rax, cs:__security_cookie
0x180012777  xor     rax, rsp
0x18001277a  mov     [rbp+200h+var_30], rax
0x180012781  mov     rdi, rcx
0x180012784  mov     [rsp+300h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18001278d  lea     rax, [rsp+300h+var_298]
0x180012792  mov     [rsp+300h+lpFileName], rax
0x180012797  lea     rax, [rsp+300h+var_298]
0x18001279c  mov     [rsp+300h+var_2A0], rax
0x1800127a1  xor     esi, esi
0x1800127a3  mov     [rsp+300h+var_298], si
0x1800127a8  xor     edx, edx; Val
0x1800127aa  mov     r8d, 250h; Size
0x1800127b0  lea     rcx, [rbp+200h+FindFileData]; void *
0x1800127b4  call    memset_0
0x1800127b9  test    rdi, rdi
0x1800127bc  jnz     short loc_1800127EB
0x1800127be  mov     eax, cs:dword_180022000
0x1800127c4  cmp     eax, 2
0x1800127c7  jbe     short loc_1800127E1
0x1800127c9  lea     edx, [rsi+8]
0x1800127cc  call    _tlgKeywordOn
0x1800127d1  test    al, al
0x1800127d3  jz      short loc_1800127E1
0x1800127d5  lea     rdx, byte_18001C165
0x1800127dc  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800127e1  mov     ebx, 80070057h
0x1800127e6  jmp     loc_180012AD4
0x1800127eb  mov     rcx, rdi; lpFileName
0x1800127ee  call    cs:__imp_GetFileAttributesW
0x1800127f4  cmp     eax, 0FFFFFFFFh
0x1800127f7  jnz     short loc_180012857
0x1800127f9  call    cs:__imp_GetLastError
0x1800127ff  mov     ecx, eax; unsigned int
0x180012801  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180012806  mov     ebx, eax
0x180012808  mov     eax, cs:dword_180022000
0x18001280e  cmp     eax, 2
0x180012811  jbe     loc_180012AD4
0x180012817  mov     edx, 8
0x18001281c  call    _tlgKeywordOn
0x180012821  test    al, al
0x180012823  jz      loc_180012AD4
0x180012829  mov     [rsp+300h+var_2C0], ebx
0x18001282d  lea     rdx, byte_18001C119
0x180012834  mov     [rsp+300h+var_2B8], rdi
0x180012839  lea     rax, [rsp+300h+var_2C0]
0x18001283e  mov     [rsp+300h+var_2D8], rax
0x180012843  lea     rax, [rsp+300h+var_2B8]
0x180012848  mov     qword ptr [rsp+300h+var_2E0], rax
0x18001284d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180012852  jmp     loc_180012AD4
0x180012857  test    al, 10h
0x180012859  jnz     short loc_180012892
0x18001285b  mov     ebx, 80070057h
0x180012860  mov     eax, cs:dword_180022000
0x180012866  cmp     eax, 2
0x180012869  jbe     loc_180012AD4
0x18001286f  mov     edx, 8
0x180012874  call    _tlgKeywordOn
0x180012879  test    al, al
0x18001287b  jz      loc_180012AD4
0x180012881  mov     [rsp+300h+var_2C0], 80070057h
0x180012889  lea     rdx, word_18001C0CE
0x180012890  jmp     short loc_180012834
0x180012892  bt      eax, 0Ah
0x180012896  jnb     short loc_1800128DE
0x180012898  mov     ebx, 80070057h
0x18001289d  mov     eax, cs:dword_180022000
0x1800128a3  cmp     eax, 2
0x1800128a6  jbe     loc_180012AD4
0x1800128ac  mov     edx, 8
0x1800128b1  call    _tlgKeywordOn
0x1800128b6  test    al, al
0x1800128b8  jz      loc_180012AD4
0x1800128be  mov     [rsp+300h+var_2B8], rdi
0x1800128c3  lea     rax, [rsp+300h+var_2B8]
0x1800128c8  mov     qword ptr [rsp+300h+var_2E0], rax
0x1800128cd  lea     rdx, byte_18001C08D
0x1800128d4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800128d9  jmp     loc_180012AD4
0x1800128de  mov     r8, rdi
0x1800128e1  lea     rdx, aLs; "%ls\\*"
0x1800128e8  lea     rcx, [rsp+300h+lpFileName]
0x1800128ed  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800128f2  test    eax, eax
0x1800128f4  jns     short loc_180012930
0x1800128f6  mov     ebx, 80070057h
0x1800128fb  mov     eax, cs:dword_180022000
0x180012901  cmp     eax, 2
0x180012904  jbe     loc_180012AD4
0x18001290a  mov     edx, 8
0x18001290f  call    _tlgKeywordOn
0x180012914  test    al, al
0x180012916  jz      loc_180012AD4
0x18001291c  mov     [rsp+300h+var_2C0], 80070057h
0x180012924  lea     rdx, word_18001C046
0x18001292b  jmp     loc_180012834
0x180012930  lea     rdx, [rbp+200h+FindFileData]; lpFindFileData
0x180012934  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x180012939  call    cs:__imp_FindFirstFileW
0x18001293f  mov     rdx, rax
0x180012942  lea     rcx, [rsp+300h+hFindFile]
0x180012947  call    ?reset@?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::find_handle_traits>::reset(void *)
0x18001294c  cmp     [rsp+300h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x180012952  jnz     short loc_18001299E
0x180012954  call    cs:__imp_GetLastError
0x18001295a  mov     ecx, eax; unsigned int
0x18001295c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180012961  mov     ebx, eax
0x180012963  mov     eax, cs:dword_180022000
0x180012969  cmp     eax, 2
0x18001296c  jbe     loc_180012AD4
0x180012972  mov     edx, 8
0x180012977  call    _tlgKeywordOn
0x18001297c  test    al, al
0x18001297e  jz      loc_180012AD4
0x180012984  mov     [rsp+300h+var_2C0], ebx
0x180012988  mov     rax, [rsp+300h+lpFileName]
0x18001298d  mov     [rsp+300h+var_2B8], rax
0x180012992  lea     rdx, word_18001BFFE
0x180012999  jmp     loc_180012839
0x18001299e  movzx   eax, [rbp+200h+FindFileData.cFileName+2]
0x1800129a2  cmp     [rbp+200h+FindFileData.cFileName], 2Eh ; '.'
0x1800129a7  jnz     short loc_1800129C9
0x1800129a9  test    ax, ax
0x1800129ac  jz      loc_180012A4D
0x1800129b2  cmp     [rbp+200h+FindFileData.cFileName], 2Eh ; '.'
0x1800129b7  jnz     short loc_1800129C9
0x1800129b9  cmp     ax, 2Eh ; '.'
0x1800129bd  jnz     short loc_1800129C9
0x1800129bf  cmp     [rbp+200h+FindFileData.cFileName+4], si
0x1800129c3  jz      loc_180012A4D
0x1800129c9  lea     r9, [rbp+200h+FindFileData.cFileName]
0x1800129cd  mov     r8, rdi
0x1800129d0  lea     rdx, aLsLs; "%ls\\%ls"
0x1800129d7  lea     rcx, [rsp+300h+lpFileName]
0x1800129dc  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800129e1  mov     ebx, eax
0x1800129e3  test    eax, eax
0x1800129e5  js      loc_180012A7E
0x1800129eb  mov     rcx, [rsp+300h+lpFileName]; unsigned __int16 *
0x1800129f0  test    byte ptr [rbp+200h+FindFileData.dwFileAttributes], 10h
0x1800129f4  jz      short loc_180012A48
0x1800129f6  mov     [rsp+300h+var_2E0], esi; int
0x1800129fa  xor     r9d, r9d; unsigned __int16 *
0x1800129fd  xor     r8d, r8d; unsigned __int16 *
0x180012a00  xor     edx, edx; int
0x180012a02  call    ?UtilRecursiveRemoveDirectory@@YAJPEBGH00H@Z; UtilRecursiveRemoveDirectory(ushort const *,int,ushort const *,ushort const *,int)
0x180012a07  mov     ebx, eax
0x180012a09  test    eax, eax
0x180012a0b  jns     short loc_180012A4D
0x180012a0d  mov     eax, cs:dword_180022000
0x180012a13  cmp     eax, 2
0x180012a16  jbe     loc_180012AD4
0x180012a1c  mov     edx, 8
0x180012a21  call    _tlgKeywordOn
0x180012a26  test    al, al
0x180012a28  jz      loc_180012AD4
0x180012a2e  mov     [rsp+300h+var_2C0], ebx
0x180012a32  mov     rax, [rsp+300h+lpFileName]
0x180012a37  mov     [rsp+300h+var_2B8], rax
0x180012a3c  lea     rdx, dword_18001BF64
0x180012a43  jmp     loc_180012839
0x180012a48  call    ?UtilDeleteFilePath@@YAJPEBG@Z; UtilDeleteFilePath(ushort const *)
0x180012a4d  lea     rdx, [rbp+200h+FindFileData]; lpFindFileData
0x180012a51  mov     rcx, [rsp+300h+hFindFile]; hFindFile
0x180012a56  call    cs:__imp_FindNextFileW
0x180012a5c  test    eax, eax
0x180012a5e  jnz     loc_18001299E
0x180012a64  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180012a68  lea     rcx, [rsp+300h+hFindFile]
0x180012a6d  call    ?reset@?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::find_handle_traits>::reset(void *)
0x180012a72  mov     rcx, rdi; unsigned __int16 *
0x180012a75  call    ?UtilDeleteFilePath@@YAJPEBG@Z; UtilDeleteFilePath(ushort const *)
0x180012a7a  mov     ebx, esi
0x180012a7c  jmp     short loc_180012AD4
0x180012a7e  mov     eax, cs:dword_180022000
0x180012a84  cmp     eax, 2
0x180012a87  jbe     short loc_180012AD4
0x180012a89  mov     edx, 8
0x180012a8e  call    _tlgKeywordOn
0x180012a93  test    al, al
0x180012a95  jz      short loc_180012AD4
0x180012a97  mov     [rsp+300h+var_2C0], ebx
0x180012a9b  lea     rax, [rbp+200h+FindFileData.cFileName]
0x180012a9f  mov     [rsp+300h+var_2B8], rax
0x180012aa4  mov     [rsp+300h+var_288], rdi
0x180012aa9  lea     rax, [rsp+300h+var_2C0]
0x180012aae  mov     [rsp+300h+var_2D0], rax
0x180012ab3  lea     rax, [rsp+300h+var_2B8]
0x180012ab8  mov     [rsp+300h+var_2D8], rax
0x180012abd  lea     rax, [rsp+300h+var_288]
0x180012ac2  mov     qword ptr [rsp+300h+var_2E0], rax
0x180012ac7  lea     rdx, dword_18001BFAC
0x180012ace  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180012ad3  nop
0x180012ad4  lea     rcx, [rsp+300h+lpFileName]
0x180012ad9  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180012ade  nop
0x180012adf  lea     rcx, [rsp+300h+hFindFile]
0x180012ae4  call    ??1?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(void)
0x180012ae9  mov     eax, ebx
0x180012aeb  mov     rcx, [rbp+200h+var_30]
0x180012af2  xor     rcx, rsp; StackCookie
0x180012af5  call    __security_check_cookie
0x180012afa  add     rsp, 2E8h
0x180012b01  pop     rdi
0x180012b02  pop     rsi
0x180012b03  pop     rbx
0x180012b04  pop     rbp
0x180012b05  retn
```
