# CZoneIdentifier::_SaveBatchedHelper(ulong)

- ea: `0x180111f34`
- end: `0x1801122e2`
- name: `?_SaveBatchedHelper@CZoneIdentifier@@AEAAJK@Z`
- size: `942`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a0b60`
- `0x180111654`

## callees

- `0x180088604`
- `0x18008cf94`
- `0x1800912b4`
- `0x1800a11c0`
- `0x18010f520`
- `0x18010f54c`
- `0x180111b1c`
- `0x180111f34`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1801120db`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180112186`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1801120db`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180112186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801120ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801121fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801120ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801121fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112272`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18011223d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18011223d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801121e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801121e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180111ff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011213d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180111ff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011213d`

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
  signed int v14; // esi
  unsigned int v15; // esi
  int v16; // eax
  signed int v17; // r14d
  unsigned int v18; // eax
  DWORD cbMultiByte; // edi
  signed int v20; // eax
  CHAR *v21; // rax
  CHAR *v22; // rsi
  signed int v23; // eax
  HANDLE FileW; // rax
  signed int LastError; // eax
  signed int v26; // eax
  int lpMultiByteStr; // [rsp+20h] [rbp-49h]
  int lpMultiByteStra; // [rsp+20h] [rbp-49h]
  LPCWCH lpWideCharStr; // [rsp+40h] [rbp-29h] BYREF
  CHAR *v30; // [rsp+48h] [rbp-21h] BYREF
  __int64 v31; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v32; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 *v33; // [rsp+60h] [rbp-9h] BYREF
  __int64 v34[11]; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int cchWideChar; // [rsp+D8h] [rbp+6Fh] BYREF
  SIZE_T cb; // [rsp+E0h] [rbp+77h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( !a2 )
    return 0;
  v31 = -1;
  v34[1] = (__int64)&v33;
  v34[2] = (__int64)&v32;
  v34[3] = (__int64)&cchWideChar;
  cchWideChar = 15;
  v5 = 0;
  v30 = 0;
  lpWideCharStr = 0;
  v33 = 0;
  v32 = 0;
  v34[0] = (__int64)this;
  do
  {
    v6 = lambda_041e48295cf5f1f2c99b9224c3980f99_::operator()(v34, v5, 0);
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
  v32 = (unsigned int)cchWideChar;
  v33 = v12;
  v13 = StringCchPrintfExW(v12, (unsigned int)cchWideChar, &v33, &v32, 0x800u, L"[%s]");
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
      (const char *)(unsigned int)v13,
      lpMultiByteStra);
    v7 = v14;
    goto LABEL_43;
  }
  v15 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v16 = lambda_041e48295cf5f1f2c99b9224c3980f99_::operator()(v34, v15, 1);
      v17 = v16;
      if ( v16 < 0 )
        break;
      if ( ++v15 >= a2 )
        goto LABEL_16;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
      (const char *)(unsigned int)v16,
      lpMultiByteStra);
    v7 = v17;
  }
  else
  {
LABEL_16:
    v18 = WideCharToMultiByte(0, 0x400u, v12, cchWideChar, 0, 0, "?", 0);
    cbMultiByte = v18;
    if ( v18 )
    {
      v21 = (CHAR *)CoTaskMemAlloc(v18);
      v30 = v21;
      v22 = v21;
      if ( !v21 )
      {
        v7 = -2147024882;
        v10 = 538;
        goto LABEL_41;
      }
      *v21 = 0;
      if ( WideCharToMultiByte(0, 0x400u, v12, cchWideChar, v21, cbMultiByte, "?", 0) )
      {
        FileW = CreateFileW(this[6], 0x40000000u, 0, 0, 2u, 0x8000080u, 0);
        v31 = (__int64)FileW;
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
          if ( WriteFile(FileW, v22, cbMultiByte, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == cbMultiByte )
          {
            wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&lpWideCharStr);
            wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v30);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v31);
            return 0;
          }
          v26 = GetLastError();
          v7 = v26;
          if ( v26 > 0 )
            v7 = (unsigned __int16)v26 | 0x80070000;
          if ( v7 < 0 )
          {
            v10 = 577;
            goto LABEL_41;
          }
        }
      }
      else
      {
        v23 = GetLastError();
        v7 = v23;
        if ( v23 > 0 )
          v7 = (unsigned __int16)v23 | 0x80070000;
        if ( v7 < 0 )
        {
          v10 = 553;
          goto LABEL_41;
        }
      }
    }
    else
    {
      v20 = GetLastError();
      v7 = v20;
      if ( v20 > 0 )
        v7 = (unsigned __int16)v20 | 0x80070000;
      if ( v7 < 0 )
      {
        v10 = 534;
        goto LABEL_41;
      }
    }
  }
LABEL_43:
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&lpWideCharStr);
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&v30);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v31);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180111f34  mov     [rsp-8+arg_0], rbx
0x180111f39  push    rbp
0x180111f3a  push    rsi
0x180111f3b  push    rdi
0x180111f3c  push    r12
0x180111f3e  push    r13
0x180111f40  push    r14
0x180111f42  push    r15
0x180111f44  lea     rbp, [rsp-27h]
0x180111f49  sub     rsp, 90h
0x180111f50  xor     r12d, r12d
0x180111f53  mov     edi, edx
0x180111f55  mov     r15, rcx
0x180111f58  test    edx, edx
0x180111f5a  jnz     short loc_180111F63
0x180111f5c  xor     eax, eax
0x180111f5e  jmp     loc_1801122C6
0x180111f63  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x180111f6b  lea     rax, [rbp+57h+var_60]
0x180111f6f  mov     [rbp+57h+var_50], rax
0x180111f73  lea     rax, [rbp+57h+var_68]
0x180111f77  mov     [rbp+57h+var_48], rax
0x180111f7b  lea     rax, [rbp+57h+cchWideChar]
0x180111f7f  mov     [rbp+57h+var_40], rax
0x180111f83  mov     eax, 0Fh
0x180111f88  mov     [rbp+57h+cchWideChar], eax
0x180111f8b  mov     esi, r12d
0x180111f8e  mov     [rbp+57h+var_78], r12
0x180111f92  mov     [rbp+57h+lpWideCharStr], r12
0x180111f96  mov     [rbp+57h+var_60], r12
0x180111f9a  mov     [rbp+57h+var_68], r12
0x180111f9e  mov     [rbp+57h+var_58], r15
0x180111fa2  test    edi, edi
0x180111fa4  jz      short loc_180111FC3
0x180111fa6  xor     r8d, r8d
0x180111fa9  lea     rcx, [rbp+57h+var_58]
0x180111fad  mov     edx, esi
0x180111faf  call    _lambda_041e48295cf5f1f2c99b9224c3980f99___operator__
0x180111fb4  mov     ebx, eax
0x180111fb6  test    eax, eax
0x180111fb8  js      short loc_180111FE8
0x180111fba  inc     esi
0x180111fbc  cmp     esi, edi
0x180111fbe  jb      short loc_180111FA6
0x180111fc0  mov     eax, [rbp+57h+cchWideChar]
0x180111fc3  mov     ecx, eax
0x180111fc5  lea     rdx, [rbp+57h+cb]; unsigned int *
0x180111fc9  add     rcx, rcx; __int64
0x180111fcc  mov     dword ptr [rbp+57h+cb], r12d
0x180111fd0  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180111fd5  mov     ebx, eax
0x180111fd7  test    eax, eax
0x180111fd9  jns     short loc_180111FF5
0x180111fdb  mov     r9d, eax
0x180111fde  mov     edx, 1EDh
0x180111fe3  jmp     loc_180112299
0x180111fe8  mov     r9d, eax
0x180111feb  mov     edx, 1E9h
0x180111ff0  jmp     loc_180112299
0x180111ff5  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180111ff8  call    cs:__imp_CoTaskMemAlloc
0x180111fff  nop     dword ptr [rax+rax+00h]
0x180112004  mov     rdx, rax
0x180112007  lea     rcx, [rbp+57h+lpWideCharStr]
0x18011200b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180112010  mov     rbx, [rbp+57h+lpWideCharStr]
0x180112014  test    rbx, rbx
0x180112017  jnz     short loc_180112028
0x180112019  mov     ebx, 8007000Eh
0x18011201e  mov     edx, 1F1h
0x180112023  jmp     loc_180112296
0x180112028  mov     [rbx], r12w
0x18011202c  lea     rax, AppName; "ZoneTransfer"
0x180112033  mov     edx, [rbp+57h+cchWideChar]; unsigned __int64
0x180112036  lea     r9, [rbp+57h+var_68]; unsigned __int64 *
0x18011203a  mov     [rsp+0C0h+lpDefaultChar], rax
0x18011203f  lea     r8, [rbp+57h+var_60]; unsigned __int16 **
0x180112043  lea     rax, aS_0; "[%s]"
0x18011204a  mov     [rbp+57h+var_68], rdx
0x18011204e  mov     qword ptr [rsp+0C0h+cbMultiByte], rax; unsigned __int16 *
0x180112053  mov     rcx, rbx; pszDest
0x180112056  mov     dword ptr [rsp+0C0h+lpMultiByteStr], 800h; int
0x18011205e  mov     [rbp+57h+var_60], rbx
0x180112062  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180112067  mov     esi, eax
0x180112069  test    eax, eax
0x18011206b  jns     short loc_18011208C
0x18011206d  mov     rcx, [rbp+5Fh]; this
0x180112071  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180112078  mov     r9d, eax; char *
0x18011207b  mov     edx, 202h; void *
0x180112080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112085  mov     ebx, esi
0x180112087  jmp     loc_1801122A9
0x18011208c  mov     esi, r12d
0x18011208f  test    edi, edi
0x180112091  jz      short loc_1801120AE
0x180112093  mov     r8b, 1
0x180112096  lea     rcx, [rbp+57h+var_58]
0x18011209a  mov     edx, esi
0x18011209c  call    _lambda_041e48295cf5f1f2c99b9224c3980f99___operator__
0x1801120a1  mov     r14d, eax
0x1801120a4  test    eax, eax
0x1801120a6  js      short loc_18011211A
0x1801120a8  inc     esi
0x1801120aa  cmp     esi, edi
0x1801120ac  jb      short loc_180112093
0x1801120ae  mov     r9d, [rbp+57h+cchWideChar]; cchWideChar
0x1801120b2  lea     r13, DefaultChar; "?"
0x1801120b9  mov     [rsp+0C0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1801120be  mov     r14d, 400h
0x1801120c4  mov     [rsp+0C0h+lpDefaultChar], r13; lpDefaultChar
0x1801120c9  mov     r8, rbx; lpWideCharStr
0x1801120cc  mov     [rsp+0C0h+cbMultiByte], r12d; cbMultiByte
0x1801120d1  mov     edx, r14d; dwFlags
0x1801120d4  xor     ecx, ecx; CodePage
0x1801120d6  mov     [rsp+0C0h+lpMultiByteStr], r12; lpMultiByteStr
0x1801120db  call    cs:__imp_WideCharToMultiByte
0x1801120e2  nop     dword ptr [rax+rax+00h]
0x1801120e7  mov     edi, eax
0x1801120e9  test    eax, eax
0x1801120eb  jnz     short loc_18011213A
0x1801120ed  call    cs:__imp_GetLastError
0x1801120f4  nop     dword ptr [rax+rax+00h]
0x1801120f9  mov     ebx, eax
0x1801120fb  test    eax, eax
0x1801120fd  jle     short loc_180112108
0x1801120ff  movzx   ebx, ax
0x180112102  or      ebx, 80070000h
0x180112108  test    ebx, ebx
0x18011210a  jns     loc_1801122A9
0x180112110  mov     edx, 216h
0x180112115  jmp     loc_180112296
0x18011211a  mov     rcx, [rbp+5Fh]; this
0x18011211e  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180112125  mov     r9d, r14d; char *
0x180112128  mov     edx, 206h; void *
0x18011212d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112132  mov     ebx, r14d
0x180112135  jmp     loc_1801122A9
0x18011213a  mov     rcx, rdi; cb
0x18011213d  call    cs:__imp_CoTaskMemAlloc
0x180112144  nop     dword ptr [rax+rax+00h]
0x180112149  mov     [rbp+57h+var_78], rax
0x18011214d  mov     rsi, rax
0x180112150  test    rax, rax
0x180112153  jnz     short loc_180112164
0x180112155  mov     ebx, 8007000Eh
0x18011215a  mov     edx, 21Ah
0x18011215f  jmp     loc_180112296
0x180112164  mov     [rsp+0C0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180112169  mov     r8, rbx; lpWideCharStr
0x18011216c  mov     [rsp+0C0h+lpDefaultChar], r13; lpDefaultChar
0x180112171  mov     edx, r14d; dwFlags
0x180112174  mov     [rax], r12b
0x180112177  xor     ecx, ecx; CodePage
0x180112179  mov     r9d, [rbp+57h+cchWideChar]; cchWideChar
0x18011217d  mov     [rsp+0C0h+cbMultiByte], edi; cbMultiByte
0x180112181  mov     [rsp+0C0h+lpMultiByteStr], rsi; lpMultiByteStr
0x180112186  call    cs:__imp_WideCharToMultiByte
0x18011218d  nop     dword ptr [rax+rax+00h]
0x180112192  test    eax, eax
0x180112194  jnz     short loc_1801121C3
0x180112196  call    cs:__imp_GetLastError
0x18011219d  nop     dword ptr [rax+rax+00h]
0x1801121a2  mov     ebx, eax
0x1801121a4  test    eax, eax
0x1801121a6  jle     short loc_1801121B1
0x1801121a8  movzx   ebx, ax
0x1801121ab  or      ebx, 80070000h
0x1801121b1  test    ebx, ebx
0x1801121b3  jns     loc_1801122A9
0x1801121b9  mov     edx, 229h
0x1801121be  jmp     loc_180112296
0x1801121c3  mov     rcx, [r15+30h]; lpFileName
0x1801121c7  xor     r9d, r9d; lpSecurityAttributes
0x1801121ca  mov     [rsp+0C0h+lpDefaultChar], r12; hTemplateFile
0x1801121cf  xor     r8d, r8d; dwShareMode
0x1801121d2  mov     [rsp+0C0h+cbMultiByte], 8000080h; dwFlagsAndAttributes
0x1801121da  mov     edx, 40000000h; dwDesiredAccess
0x1801121df  mov     dword ptr [rsp+0C0h+lpMultiByteStr], 2; dwCreationDisposition
0x1801121e7  call    cs:__imp_CreateFileW
0x1801121ee  nop     dword ptr [rax+rax+00h]
0x1801121f3  mov     [rbp+57h+var_70], rax
0x1801121f7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801121fb  jnz     short loc_180112227
0x1801121fd  call    cs:__imp_GetLastError
0x180112204  nop     dword ptr [rax+rax+00h]
0x180112209  mov     ebx, eax
0x18011220b  test    eax, eax
0x18011220d  jle     short loc_180112218
0x18011220f  movzx   ebx, ax
0x180112212  or      ebx, 80070000h
0x180112218  test    ebx, ebx
0x18011221a  jns     loc_1801122A9
0x180112220  mov     edx, 236h
0x180112225  jmp     short loc_180112296
0x180112227  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18011222b  mov     [rbp+57h+NumberOfBytesWritten], r12d
0x18011222f  mov     r8d, edi; nNumberOfBytesToWrite
0x180112232  mov     [rsp+0C0h+lpMultiByteStr], r12; int
0x180112237  mov     rdx, rsi; lpBuffer
0x18011223a  mov     rcx, rax; hFile
0x18011223d  call    cs:__imp_WriteFile
0x180112244  nop     dword ptr [rax+rax+00h]
0x180112249  test    eax, eax
0x18011224b  jz      short loc_180112272
0x18011224d  cmp     [rbp+57h+NumberOfBytesWritten], edi
0x180112250  jnz     short loc_180112272
0x180112252  lea     rcx, [rbp+57h+lpWideCharStr]
0x180112256  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18011225b  lea     rcx, [rbp+57h+var_78]
0x18011225f  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180112264  lea     rcx, [rbp+57h+var_70]
0x180112268  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011226d  jmp     loc_180111F5C
0x180112272  call    cs:__imp_GetLastError
0x180112279  nop     dword ptr [rax+rax+00h]
0x18011227e  mov     ebx, eax
0x180112280  test    eax, eax
0x180112282  jle     short loc_18011228D
0x180112284  movzx   ebx, ax
0x180112287  or      ebx, 80070000h
0x18011228d  test    ebx, ebx
0x18011228f  jns     short loc_1801122A9
0x180112291  mov     edx, 241h; void *
0x180112296  mov     r9d, ebx; char *
0x180112299  mov     rcx, [rbp+5Fh]; this
0x18011229d  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x1801122a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801122a9  lea     rcx, [rbp+57h+lpWideCharStr]
0x1801122ad  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1801122b2  lea     rcx, [rbp+57h+var_78]
0x1801122b6  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1801122bb  lea     rcx, [rbp+57h+var_70]
0x1801122bf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801122c4  mov     eax, ebx
0x1801122c6  mov     rbx, [rsp+0C0h+arg_0]
0x1801122ce  add     rsp, 90h
0x1801122d5  pop     r15
0x1801122d7  pop     r14
0x1801122d9  pop     r13
0x1801122db  pop     r12
0x1801122dd  pop     rdi
0x1801122de  pop     rsi
0x1801122df  pop     rbp
0x1801122e0  retn
```
