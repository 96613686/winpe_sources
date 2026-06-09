# CZoneIdentifier::_SaveBatchedHelper(ulong)

- ea: `0x180106a24`
- end: `0x180106d91`
- name: `?_SaveBatchedHelper@CZoneIdentifier@@AEAAJK@Z`
- size: `877`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18009a230`
- `0x1801061c8`

## callees

- `0x1800478b0`
- `0x1800877ec`
- `0x18008b74c`
- `0x18009a6a0`
- `0x180104160`
- `0x180104184`
- `0x18010662c`
- `0x180106a24`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180106bc5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180106c5e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180106bc5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180106c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106d28`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180106cf9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180106cf9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180106cb3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180106cb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180106ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180106c1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180106ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180106c1b`

## pseudocode

```c
__int64 __fastcall CZoneIdentifier::_SaveBatchedHelper(LPCWSTR *this, unsigned int a2)
{
  unsigned int v5; // esi
  int v6; // eax
  signed int v7; // ebx
  int v8; // eax
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  LPVOID v11; // rax
  unsigned __int16 *v12; // rbx
  int v13; // eax
  __int64 v14; // r8
  signed int v15; // esi
  unsigned int v16; // esi
  int v17; // eax
  signed int v18; // r14d
  unsigned int v19; // eax
  DWORD cbMultiByte; // edi
  signed int v21; // eax
  CHAR *v22; // rax
  CHAR *v23; // rsi
  signed int v24; // eax
  HANDLE FileW; // rax
  signed int LastError; // eax
  signed int v27; // eax
  int lpMultiByteStr; // [rsp+20h] [rbp-49h]
  int lpMultiByteStra; // [rsp+20h] [rbp-49h]
  LPCWCH lpWideCharStr; // [rsp+40h] [rbp-29h] BYREF
  CHAR *v31; // [rsp+48h] [rbp-21h] BYREF
  __int64 v32; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v33; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 *v34; // [rsp+60h] [rbp-9h] BYREF
  _QWORD v35[11]; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int cchWideChar; // [rsp+D8h] [rbp+6Fh] BYREF
  SIZE_T cb; // [rsp+E0h] [rbp+77h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( !a2 )
    return 0;
  v32 = -1;
  v35[1] = &v34;
  v35[2] = &v33;
  v35[3] = &cchWideChar;
  cchWideChar = 15;
  v5 = 0;
  v31 = 0;
  lpWideCharStr = 0;
  v34 = 0;
  v33 = 0;
  v35[0] = this;
  do
  {
    v6 = lambda_041e48295cf5f1f2c99b9224c3980f99_::operator()(v35, v5, 0);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = (unsigned int)v6;
      v10 = 489;
      goto LABEL_42;
    }
    ++v5;
  }
  while ( v5 < a2 );
  LODWORD(cb) = 0;
  v8 = LongLongToULong(2LL * (unsigned int)cchWideChar, (unsigned int *)&cb);
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = (unsigned int)v8;
    v10 = 493;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
      (const char *)v9,
      lpMultiByteStr);
    goto LABEL_43;
  }
  v11 = CoTaskMemAlloc((unsigned int)cb);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpWideCharStr,
    v11);
  v12 = (unsigned __int16 *)lpWideCharStr;
  if ( !lpWideCharStr )
  {
    v7 = -2147024882;
    v10 = 497;
LABEL_41:
    v9 = (unsigned int)v7;
    goto LABEL_42;
  }
  *lpWideCharStr = 0;
  v33 = (unsigned int)cchWideChar;
  v34 = v12;
  v13 = StringCchPrintfExW(v12, (unsigned int)cchWideChar, &v34, &v33, 0x800u, L"[%s]");
  v15 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
      (const char *)(unsigned int)v13,
      lpMultiByteStra);
    v7 = v15;
    goto LABEL_43;
  }
  v16 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      LOBYTE(v14) = 1;
      v17 = lambda_041e48295cf5f1f2c99b9224c3980f99_::operator()(v35, v16, v14);
      v18 = v17;
      if ( v17 < 0 )
        break;
      if ( ++v16 >= a2 )
        goto LABEL_16;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
      (const char *)(unsigned int)v17,
      lpMultiByteStra);
    v7 = v18;
  }
  else
  {
LABEL_16:
    v19 = WideCharToMultiByte(0, 0x400u, v12, cchWideChar, 0, 0, "?", 0);
    cbMultiByte = v19;
    if ( v19 )
    {
      v22 = (CHAR *)CoTaskMemAlloc(v19);
      v31 = v22;
      v23 = v22;
      if ( !v22 )
      {
        v7 = -2147024882;
        v10 = 538;
        goto LABEL_41;
      }
      *v22 = 0;
      if ( WideCharToMultiByte(0, 0x400u, v12, cchWideChar, v22, cbMultiByte, "?", 0) )
      {
        FileW = CreateFileW(this[6], 0x40000000u, 0, 0, 2u, 0x8000080u, 0);
        v32 = (__int64)FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( v7 < 0 )
          {
            v10 = 566;
            goto LABEL_41;
          }
        }
        else
        {
          NumberOfBytesWritten = 0;
          if ( WriteFile(FileW, v23, cbMultiByte, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == cbMultiByte )
          {
            wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&lpWideCharStr);
            wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v31);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
            return 0;
          }
          v27 = GetLastError();
          v7 = v27;
          if ( v27 > 0 )
            v7 = (unsigned __int16)v27 | 0x80070000;
          if ( v7 < 0 )
          {
            v10 = 577;
            goto LABEL_41;
          }
        }
      }
      else
      {
        v24 = GetLastError();
        v7 = v24;
        if ( v24 > 0 )
          v7 = (unsigned __int16)v24 | 0x80070000;
        if ( v7 < 0 )
        {
          v10 = 553;
          goto LABEL_41;
        }
      }
    }
    else
    {
      v21 = GetLastError();
      v7 = v21;
      if ( v21 > 0 )
        v7 = (unsigned __int16)v21 | 0x80070000;
      if ( v7 < 0 )
      {
        v10 = 534;
        goto LABEL_41;
      }
    }
  }
LABEL_43:
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&lpWideCharStr);
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v31);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180106a24  mov     [rsp-8+arg_0], rbx
0x180106a29  push    rbp
0x180106a2a  push    rsi
0x180106a2b  push    rdi
0x180106a2c  push    r12
0x180106a2e  push    r13
0x180106a30  push    r14
0x180106a32  push    r15
0x180106a34  lea     rbp, [rsp-27h]
0x180106a39  sub     rsp, 90h
0x180106a40  xor     r12d, r12d
0x180106a43  mov     edi, edx
0x180106a45  mov     r15, rcx
0x180106a48  test    edx, edx
0x180106a4a  jnz     short loc_180106A53
0x180106a4c  xor     eax, eax
0x180106a4e  jmp     loc_180106D76
0x180106a53  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x180106a5b  lea     rax, [rbp+57h+var_60]
0x180106a5f  mov     [rbp+57h+var_50], rax
0x180106a63  lea     rax, [rbp+57h+var_68]
0x180106a67  mov     [rbp+57h+var_48], rax
0x180106a6b  lea     rax, [rbp+57h+cchWideChar]
0x180106a6f  mov     [rbp+57h+var_40], rax
0x180106a73  mov     eax, 0Fh
0x180106a78  mov     [rbp+57h+cchWideChar], eax
0x180106a7b  mov     esi, r12d
0x180106a7e  mov     [rbp+57h+var_78], r12
0x180106a82  mov     [rbp+57h+lpWideCharStr], r12
0x180106a86  mov     [rbp+57h+var_60], r12
0x180106a8a  mov     [rbp+57h+var_68], r12
0x180106a8e  mov     [rbp+57h+var_58], r15
0x180106a92  test    edi, edi
0x180106a94  jz      short loc_180106AB3
0x180106a96  xor     r8d, r8d
0x180106a99  lea     rcx, [rbp+57h+var_58]
0x180106a9d  mov     edx, esi
0x180106a9f  call    _lambda_041e48295cf5f1f2c99b9224c3980f99___operator__
0x180106aa4  mov     ebx, eax
0x180106aa6  test    eax, eax
0x180106aa8  js      short loc_180106AD8
0x180106aaa  inc     esi
0x180106aac  cmp     esi, edi
0x180106aae  jb      short loc_180106A96
0x180106ab0  mov     eax, [rbp+57h+cchWideChar]
0x180106ab3  mov     ecx, eax
0x180106ab5  lea     rdx, [rbp+57h+cb]; unsigned int *
0x180106ab9  add     rcx, rcx; __int64
0x180106abc  mov     dword ptr [rbp+57h+cb], r12d
0x180106ac0  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180106ac5  mov     ebx, eax
0x180106ac7  test    eax, eax
0x180106ac9  jns     short loc_180106AE5
0x180106acb  mov     r9d, eax
0x180106ace  mov     edx, 1EDh
0x180106ad3  jmp     loc_180106D49
0x180106ad8  mov     r9d, eax
0x180106adb  mov     edx, 1E9h
0x180106ae0  jmp     loc_180106D49
0x180106ae5  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180106ae8  call    cs:__imp_CoTaskMemAlloc
0x180106aee  mov     rdx, rax
0x180106af1  lea     rcx, [rbp+57h+lpWideCharStr]
0x180106af5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180106afa  mov     rbx, [rbp+57h+lpWideCharStr]
0x180106afe  test    rbx, rbx
0x180106b01  jnz     short loc_180106B12
0x180106b03  mov     ebx, 8007000Eh
0x180106b08  mov     edx, 1F1h
0x180106b0d  jmp     loc_180106D46
0x180106b12  mov     [rbx], r12w
0x180106b16  lea     rax, AppName; "ZoneTransfer"
0x180106b1d  mov     edx, [rbp+57h+cchWideChar]; unsigned __int64
0x180106b20  lea     r9, [rbp+57h+var_68]; unsigned __int64 *
0x180106b24  mov     [rsp+0C0h+lpDefaultChar], rax
0x180106b29  lea     r8, [rbp+57h+var_60]; unsigned __int16 **
0x180106b2d  lea     rax, aS_0; "[%s]"
0x180106b34  mov     [rbp+57h+var_68], rdx
0x180106b38  mov     qword ptr [rsp+0C0h+cbMultiByte], rax; unsigned __int16 *
0x180106b3d  mov     rcx, rbx; pszDest
0x180106b40  mov     dword ptr [rsp+0C0h+lpMultiByteStr], 800h; int
0x180106b48  mov     [rbp+57h+var_60], rbx
0x180106b4c  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180106b51  mov     esi, eax
0x180106b53  test    eax, eax
0x180106b55  jns     short loc_180106B76
0x180106b57  mov     rcx, [rbp+5Fh]; this
0x180106b5b  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180106b62  mov     r9d, eax; char *
0x180106b65  mov     edx, 202h; void *
0x180106b6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106b6f  mov     ebx, esi
0x180106b71  jmp     loc_180106D59
0x180106b76  mov     esi, r12d
0x180106b79  test    edi, edi
0x180106b7b  jz      short loc_180106B98
0x180106b7d  mov     r8b, 1
0x180106b80  lea     rcx, [rbp+57h+var_58]
0x180106b84  mov     edx, esi
0x180106b86  call    _lambda_041e48295cf5f1f2c99b9224c3980f99___operator__
0x180106b8b  mov     r14d, eax
0x180106b8e  test    eax, eax
0x180106b90  js      short loc_180106BF8
0x180106b92  inc     esi
0x180106b94  cmp     esi, edi
0x180106b96  jb      short loc_180106B7D
0x180106b98  mov     r9d, [rbp+57h+cchWideChar]; cchWideChar
0x180106b9c  lea     r13, DefaultChar; "?"
0x180106ba3  mov     [rsp+0C0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180106ba8  mov     r14d, 400h
0x180106bae  mov     [rsp+0C0h+lpDefaultChar], r13; lpDefaultChar
0x180106bb3  mov     r8, rbx; lpWideCharStr
0x180106bb6  mov     [rsp+0C0h+cbMultiByte], r12d; cbMultiByte
0x180106bbb  mov     edx, r14d; dwFlags
0x180106bbe  xor     ecx, ecx; CodePage
0x180106bc0  mov     [rsp+0C0h+lpMultiByteStr], r12; lpMultiByteStr
0x180106bc5  call    cs:__imp_WideCharToMultiByte
0x180106bcb  mov     edi, eax
0x180106bcd  test    eax, eax
0x180106bcf  jnz     short loc_180106C18
0x180106bd1  call    cs:__imp_GetLastError
0x180106bd7  mov     ebx, eax
0x180106bd9  test    eax, eax
0x180106bdb  jle     short loc_180106BE6
0x180106bdd  movzx   ebx, ax
0x180106be0  or      ebx, 80070000h
0x180106be6  test    ebx, ebx
0x180106be8  jns     loc_180106D59
0x180106bee  mov     edx, 216h
0x180106bf3  jmp     loc_180106D46
0x180106bf8  mov     rcx, [rbp+5Fh]; this
0x180106bfc  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180106c03  mov     r9d, r14d; char *
0x180106c06  mov     edx, 206h; void *
0x180106c0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106c10  mov     ebx, r14d
0x180106c13  jmp     loc_180106D59
0x180106c18  mov     rcx, rdi; cb
0x180106c1b  call    cs:__imp_CoTaskMemAlloc
0x180106c21  mov     [rbp+57h+var_78], rax
0x180106c25  mov     rsi, rax
0x180106c28  test    rax, rax
0x180106c2b  jnz     short loc_180106C3C
0x180106c2d  mov     ebx, 8007000Eh
0x180106c32  mov     edx, 21Ah
0x180106c37  jmp     loc_180106D46
0x180106c3c  mov     [rsp+0C0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180106c41  mov     r8, rbx; lpWideCharStr
0x180106c44  mov     [rsp+0C0h+lpDefaultChar], r13; lpDefaultChar
0x180106c49  mov     edx, r14d; dwFlags
0x180106c4c  mov     [rax], r12b
0x180106c4f  xor     ecx, ecx; CodePage
0x180106c51  mov     r9d, [rbp+57h+cchWideChar]; cchWideChar
0x180106c55  mov     [rsp+0C0h+cbMultiByte], edi; cbMultiByte
0x180106c59  mov     [rsp+0C0h+lpMultiByteStr], rsi; lpMultiByteStr
0x180106c5e  call    cs:__imp_WideCharToMultiByte
0x180106c64  test    eax, eax
0x180106c66  jnz     short loc_180106C8F
0x180106c68  call    cs:__imp_GetLastError
0x180106c6e  mov     ebx, eax
0x180106c70  test    eax, eax
0x180106c72  jle     short loc_180106C7D
0x180106c74  movzx   ebx, ax
0x180106c77  or      ebx, 80070000h
0x180106c7d  test    ebx, ebx
0x180106c7f  jns     loc_180106D59
0x180106c85  mov     edx, 229h
0x180106c8a  jmp     loc_180106D46
0x180106c8f  mov     rcx, [r15+30h]; lpFileName
0x180106c93  xor     r9d, r9d; lpSecurityAttributes
0x180106c96  mov     [rsp+0C0h+lpDefaultChar], r12; hTemplateFile
0x180106c9b  xor     r8d, r8d; dwShareMode
0x180106c9e  mov     [rsp+0C0h+cbMultiByte], 8000080h; dwFlagsAndAttributes
0x180106ca6  mov     edx, 40000000h; dwDesiredAccess
0x180106cab  mov     dword ptr [rsp+0C0h+lpMultiByteStr], 2; dwCreationDisposition
0x180106cb3  call    cs:__imp_CreateFileW
0x180106cb9  mov     [rbp+57h+var_70], rax
0x180106cbd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180106cc1  jnz     short loc_180106CE3
0x180106cc3  call    cs:__imp_GetLastError
0x180106cc9  mov     ebx, eax
0x180106ccb  test    eax, eax
0x180106ccd  jle     short loc_180106CD8
0x180106ccf  movzx   ebx, ax
0x180106cd2  or      ebx, 80070000h
0x180106cd8  test    ebx, ebx
0x180106cda  jns     short loc_180106D59
0x180106cdc  mov     edx, 236h
0x180106ce1  jmp     short loc_180106D46
0x180106ce3  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180106ce7  mov     [rbp+57h+NumberOfBytesWritten], r12d
0x180106ceb  mov     r8d, edi; nNumberOfBytesToWrite
0x180106cee  mov     [rsp+0C0h+lpMultiByteStr], r12; int
0x180106cf3  mov     rdx, rsi; lpBuffer
0x180106cf6  mov     rcx, rax; hFile
0x180106cf9  call    cs:__imp_WriteFile
0x180106cff  test    eax, eax
0x180106d01  jz      short loc_180106D28
0x180106d03  cmp     [rbp+57h+NumberOfBytesWritten], edi
0x180106d06  jnz     short loc_180106D28
0x180106d08  lea     rcx, [rbp+57h+lpWideCharStr]
0x180106d0c  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180106d11  lea     rcx, [rbp+57h+var_78]
0x180106d15  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180106d1a  lea     rcx, [rbp+57h+var_70]
0x180106d1e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180106d23  jmp     loc_180106A4C
0x180106d28  call    cs:__imp_GetLastError
0x180106d2e  mov     ebx, eax
0x180106d30  test    eax, eax
0x180106d32  jle     short loc_180106D3D
0x180106d34  movzx   ebx, ax
0x180106d37  or      ebx, 80070000h
0x180106d3d  test    ebx, ebx
0x180106d3f  jns     short loc_180106D59
0x180106d41  mov     edx, 241h; void *
0x180106d46  mov     r9d, ebx; char *
0x180106d49  mov     rcx, [rbp+5Fh]; this
0x180106d4d  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180106d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106d59  lea     rcx, [rbp+57h+lpWideCharStr]
0x180106d5d  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180106d62  lea     rcx, [rbp+57h+var_78]
0x180106d66  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180106d6b  lea     rcx, [rbp+57h+var_70]
0x180106d6f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180106d74  mov     eax, ebx
0x180106d76  mov     rbx, [rsp+0C0h+arg_0]
0x180106d7e  add     rsp, 90h
0x180106d85  pop     r15
0x180106d87  pop     r14
0x180106d89  pop     r13
0x180106d8b  pop     r12
0x180106d8d  pop     rdi
0x180106d8e  pop     rsi
0x180106d8f  pop     rbp
0x180106d90  retn
```
