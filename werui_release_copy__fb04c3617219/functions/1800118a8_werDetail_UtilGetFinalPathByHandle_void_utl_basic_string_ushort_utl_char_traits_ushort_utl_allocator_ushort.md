# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800118a8`
- end: `0x180011ae8`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x180012d68`

## callees

- `0x180001234`
- `0x180001740`
- `0x1800017a4`
- `0x180003fe4`
- `0x180009580`
- `0x18000aea4`
- `0x18000af28`
- `0x18000f764`
- `0x1800118a8`
- `0x180011af0`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x18001194e`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180011a60`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18001194e`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180011a60`
- `KERNEL32!GetLastError` at `0x18001195a`
- `KERNEL32!GetLastError` at `0x180011a83`
- `KERNEL32!GetLastError` at `0x18001195a`
- `KERNEL32!GetLastError` at `0x180011a83`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathByHandle(HANDLE hFile, __int64 a2)
{
  unsigned __int64 v4; // rdi
  __int64 v5; // rcx
  unsigned int FinalPathOnUnmountedVolume; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  void *v10; // rdx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v12; // rcx
  DWORD LastError; // eax
  __int64 v14; // rcx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int *v18; // rdx
  __int64 v19; // rdx
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  DWORD v22; // eax
  DWORD v23; // eax
  __int64 v24; // rcx
  LPWSTR lpszFilePath; // [rsp+30h] [rbp-20h] BYREF
  _WORD *v27; // [rsp+38h] [rbp-18h]
  _WORD v28[8]; // [rsp+40h] [rbp-10h] BYREF
  int v29; // [rsp+80h] [rbp+30h] BYREF
  int v30; // [rsp+88h] [rbp+38h] BYREF

  lpszFilePath = v28;
  LODWORD(v4) = 261;
  v27 = v28;
  v28[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                           &lpszFilePath,
                           261) )
  {
    FinalPathOnUnmountedVolume = -2147024882;
    if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v5, 8) )
    {
      v10 = &unk_18001C548;
LABEL_5:
      v30 = v4;
      v29 = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (_DWORD)v10,
        v8,
        v9,
        (__int64)&v30,
        (__int64)&v29);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, lpszFilePath, v27 - lpszFilePath, 0);
  v4 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      FinalPathOnUnmountedVolume = _werDetail::UtilGetFinalPathOnUnmountedVolume(hFile, a2);
      goto LABEL_31;
    }
    FinalPathOnUnmountedVolume = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v14, 8) )
      goto LABEL_31;
    v18 = &dword_18001C514;
    goto LABEL_12;
  }
  v19 = FinalPathNameByHandleW;
  v20 = v27 - lpszFilePath;
  if ( v4 == v20 )
  {
    FinalPathOnUnmountedVolume = -2147418113;
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v12, 8) )
      goto LABEL_31;
    v29 = -2147418113;
    v18 = (int *)&byte_18001C4D7;
LABEL_13:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v15,
      (_DWORD)v18,
      v16,
      v17,
      (__int64)&v29);
    goto LABEL_31;
  }
  if ( v4 <= v20 )
    goto LABEL_30;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                          &lpszFilePath,
                          v19) )
  {
    v22 = GetFinalPathNameByHandleW(hFile, lpszFilePath, v27 - lpszFilePath, 0);
    LODWORD(v4) = v22;
    if ( !v22 )
    {
      v23 = GetLastError();
LABEL_27:
      FinalPathOnUnmountedVolume = ERROR_HR_FROM_WIN32(v23);
      if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v24, 8) )
        goto LABEL_31;
      v18 = &dword_18001C45C;
LABEL_12:
      v29 = FinalPathOnUnmountedVolume;
      goto LABEL_13;
    }
    if ( v22 >= (unsigned __int64)(v27 - lpszFilePath) )
    {
      v23 = 111;
      goto LABEL_27;
    }
LABEL_30:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::erase(
      &lpszFilePath,
      (unsigned int)v4);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      a2,
      &lpszFilePath);
    FinalPathOnUnmountedVolume = 0;
    goto LABEL_31;
  }
  FinalPathOnUnmountedVolume = -2147024882;
  if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v21, 8) )
  {
    v10 = &unk_18001C490;
    goto LABEL_5;
  }
LABEL_31:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&lpszFilePath);
  return FinalPathOnUnmountedVolume;
}

```

## disassembly

```asm
0x1800118a8  mov     [rsp-18h+arg_0], rbx
0x1800118ad  push    rbp
0x1800118ae  push    rsi
0x1800118af  push    rdi
0x1800118b0  mov     rbp, rsp
0x1800118b3  sub     rsp, 50h
0x1800118b7  lea     rax, [rbp+var_10]
0x1800118bb  mov     rsi, rdx
0x1800118be  mov     [rbp+lpszFilePath], rax
0x1800118c2  mov     rbx, rcx
0x1800118c5  lea     rax, [rbp+var_10]
0x1800118c9  mov     edi, 105h
0x1800118ce  mov     [rbp+var_18], rax
0x1800118d2  lea     rcx, [rbp+lpszFilePath]
0x1800118d6  xor     eax, eax
0x1800118d8  mov     edx, edi
0x1800118da  mov     [rbp+var_10], ax
0x1800118de  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x1800118e3  test    al, al
0x1800118e5  jnz     short loc_18001193A
0x1800118e7  mov     eax, cs:dword_180022000
0x1800118ed  mov     ebx, 8007000Eh
0x1800118f2  cmp     eax, 2
0x1800118f5  jbe     loc_180011AD0
0x1800118fb  mov     edx, 8
0x180011900  call    _tlgKeywordOn
0x180011905  test    al, al
0x180011907  jz      loc_180011AD0
0x18001190d  lea     rdx, unk_18001C548
0x180011914  lea     rax, [rbp+arg_10]
0x180011918  mov     [rbp+arg_18], edi
0x18001191b  mov     [rsp+50h+var_28], rax
0x180011920  lea     rax, [rbp+arg_18]
0x180011924  mov     [rsp+50h+var_30], rax
0x180011929  mov     [rbp+arg_10], 8007000Eh
0x180011930  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011935  jmp     loc_180011AD0
0x18001193a  mov     rdx, [rbp+lpszFilePath]; lpszFilePath
0x18001193e  xor     r9d, r9d; dwFlags
0x180011941  mov     r8, [rbp+var_18]
0x180011945  mov     rcx, rbx; hFile
0x180011948  sub     r8, rdx
0x18001194b  sar     r8, 1; cchFilePath
0x18001194e  call    cs:__imp_GetFinalPathNameByHandleW
0x180011954  mov     edi, eax
0x180011956  test    eax, eax
0x180011958  jnz     short loc_1800119BE
0x18001195a  call    cs:__imp_GetLastError
0x180011960  cmp     eax, 3
0x180011963  jnz     short loc_180011977
0x180011965  mov     rdx, rsi
0x180011968  mov     rcx, rbx
0x18001196b  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180011970  mov     ebx, eax
0x180011972  jmp     loc_180011AD0
0x180011977  mov     ecx, eax; unsigned int
0x180011979  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001197e  mov     ebx, eax
0x180011980  mov     eax, cs:dword_180022000
0x180011986  cmp     eax, 2
0x180011989  jbe     loc_180011AD0
0x18001198f  mov     edx, 8
0x180011994  call    _tlgKeywordOn
0x180011999  test    al, al
0x18001199b  jz      loc_180011AD0
0x1800119a1  lea     rdx, dword_18001C514
0x1800119a8  mov     [rbp+arg_10], ebx
0x1800119ab  lea     rax, [rbp+arg_10]
0x1800119af  mov     [rsp+50h+var_30], rax
0x1800119b4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800119b9  jmp     loc_180011AD0
0x1800119be  mov     rax, [rbp+var_18]
0x1800119c2  mov     rdx, rdi
0x1800119c5  sub     rax, [rbp+lpszFilePath]
0x1800119c9  sar     rax, 1
0x1800119cc  cmp     rdi, rax
0x1800119cf  jnz     short loc_180011A07
0x1800119d1  mov     eax, cs:dword_180022000
0x1800119d7  mov     ebx, 8000FFFFh
0x1800119dc  cmp     eax, 2
0x1800119df  jbe     loc_180011AD0
0x1800119e5  mov     edx, 8
0x1800119ea  call    _tlgKeywordOn
0x1800119ef  test    al, al
0x1800119f1  jz      loc_180011AD0
0x1800119f7  mov     [rbp+arg_10], 8000FFFFh
0x1800119fe  lea     rdx, byte_18001C4D7
0x180011a05  jmp     short loc_1800119AB
0x180011a07  jbe     loc_180011AB7
0x180011a0d  lea     rcx, [rbp+lpszFilePath]
0x180011a11  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x180011a16  test    al, al
0x180011a18  jnz     short loc_180011A4C
0x180011a1a  mov     eax, cs:dword_180022000
0x180011a20  mov     ebx, 8007000Eh
0x180011a25  cmp     eax, 2
0x180011a28  jbe     loc_180011AD0
0x180011a2e  mov     edx, 8
0x180011a33  call    _tlgKeywordOn
0x180011a38  test    al, al
0x180011a3a  jz      loc_180011AD0
0x180011a40  lea     rdx, unk_18001C490
0x180011a47  jmp     loc_180011914
0x180011a4c  mov     rdx, [rbp+lpszFilePath]; lpszFilePath
0x180011a50  xor     r9d, r9d; dwFlags
0x180011a53  mov     r8, [rbp+var_18]
0x180011a57  mov     rcx, rbx; hFile
0x180011a5a  sub     r8, rdx
0x180011a5d  sar     r8, 1; cchFilePath
0x180011a60  call    cs:__imp_GetFinalPathNameByHandleW
0x180011a66  mov     edi, eax
0x180011a68  test    eax, eax
0x180011a6a  jz      short loc_180011A83
0x180011a6c  mov     rcx, [rbp+var_18]
0x180011a70  sub     rcx, [rbp+lpszFilePath]
0x180011a74  sar     rcx, 1
0x180011a77  cmp     rdi, rcx
0x180011a7a  jb      short loc_180011AB7
0x180011a7c  mov     eax, 6Fh ; 'o'
0x180011a81  jmp     short loc_180011A89
0x180011a83  call    cs:__imp_GetLastError
0x180011a89  mov     ecx, eax; unsigned int
0x180011a8b  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180011a90  mov     ebx, eax
0x180011a92  mov     eax, cs:dword_180022000
0x180011a98  cmp     eax, 2
0x180011a9b  jbe     short loc_180011AD0
0x180011a9d  mov     edx, 8
0x180011aa2  call    _tlgKeywordOn
0x180011aa7  test    al, al
0x180011aa9  jz      short loc_180011AD0
0x180011aab  lea     rdx, dword_18001C45C
0x180011ab2  jmp     loc_1800119A8
0x180011ab7  mov     edx, edi
0x180011ab9  lea     rcx, [rbp+lpszFilePath]
0x180011abd  call    ?erase@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::erase(unsigned __int64)
0x180011ac2  lea     rdx, [rbp+lpszFilePath]
0x180011ac6  mov     rcx, rsi
0x180011ac9  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180011ace  xor     ebx, ebx
0x180011ad0  lea     rcx, [rbp+lpszFilePath]
0x180011ad4  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180011ad9  mov     eax, ebx
0x180011adb  mov     rbx, [rsp+50h+arg_0]
0x180011ae0  add     rsp, 50h
0x180011ae4  pop     rdi
0x180011ae5  pop     rsi
0x180011ae6  pop     rbp
0x180011ae7  retn
```
