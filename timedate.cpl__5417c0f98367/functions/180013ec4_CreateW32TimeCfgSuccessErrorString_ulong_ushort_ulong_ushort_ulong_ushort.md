# CreateW32TimeCfgSuccessErrorString(ulong,ushort *,ulong,ushort *,ulong,ushort *)

- ea: `0x180013ec4`
- end: `0x18001464e`
- name: `?CreateW32TimeCfgSuccessErrorString@@YAJKPEAGK0K0@Z`
- size: `1930`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, PCWSTR)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001d040`

## callees

- `0x180006dd8`
- `0x180008a0c`
- `0x1800092c4`
- `0x180013dd8`
- `0x180013ec4`
- `0x180014654`
- `0x18001473c`
- `0x180015b60`
- `0x1800168c8`
- `0x180028f60`
- `0x180028ff0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013fed`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180014243`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013fed`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180014243`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013fc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014062`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800141f3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001428f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800142f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001440a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014449`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001448a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800144f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014594`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013fc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014062`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800141f3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001428f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800142f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001440a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014449`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001448a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800144f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014594`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180014033`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180014043`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180014033`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180014043`

## pseudocode

```c
__int64 __fastcall CreateW32TimeCfgSuccessErrorString(
        int a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        PCWSTR a6)
{
  unsigned __int64 v6; // r12
  int ErrorInfoWrapHelper; // eax
  unsigned int v11; // r13d
  unsigned int v12; // r9d
  int DateTimeString; // eax
  unsigned int v14; // r9d
  __int64 v15; // rdx
  unsigned int v16; // r8d
  int v17; // eax
  int v18; // edi
  __int64 v19; // rdx
  bool v20; // zf
  UINT v21; // edx
  int v22; // eax
  unsigned int v23; // r9d
  int v24; // eax
  unsigned int v25; // r9d
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // r9d
  int v31; // eax
  unsigned int v32; // r9d
  __int64 v33; // rdx
  unsigned int v34; // r9d
  unsigned int v35; // r9d
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *lpBuffera; // [rsp+20h] [rbp-E0h]
  WCHAR *lpBufferb; // [rsp+20h] [rbp-E0h]
  unsigned int v40; // [rsp+40h] [rbp-C0h]
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwMessageId; // [rsp+54h] [rbp-ACh] BYREF
  FILETIME v43; // [rsp+58h] [rbp-A8h] BYREF
  FILETIME v44; // [rsp+60h] [rbp-A0h] BYREF
  int v45; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v46; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v47; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+78h] [rbp-88h] BYREF
  FILETIME FileTime; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v51[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v52[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR v53[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  WCHAR v54[2088]; // [rsp+8D0h] [rbp+7D0h] BYREF
  unsigned __int16 v55[2088]; // [rsp+1920h] [rbp+1820h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+29B8h] [rbp+28B8h]

  v6 = a3;
  v47 = 0;
  *a2 = 0;
  *a4 = 0;
  FileTime = 0;
  v44 = 0;
  LocalFileTime = 0;
  v43 = 0;
  dwMessageId = 0;
  v45 = 0;
  v41 = 0;
  v46 = 0;
  ErrorInfoWrapHelper = W32TimeGetErrorInfoWrapHelper(
                          &v47,
                          &v46,
                          &FileTime,
                          &v44,
                          &v41,
                          &dwMessageId,
                          &v45,
                          v53,
                          v40,
                          a6);
  v11 = ErrorInfoWrapHelper;
  if ( ErrorInfoWrapHelper >= 0 )
  {
    FileTimeToLocalFileTime(&FileTime, &LocalFileTime);
    FileTimeToLocalFileTime(&v44, &v43);
    LoadStringW(g_hInst, 0x1F5u, Buffer, 260);
    DateTimeString = GetDateTimeString(&LocalFileTime, 1, v51, v12);
    if ( DateTimeString >= 0 )
    {
      DateTimeString = GetDateTimeString(&LocalFileTime, 0, v52, v14);
      if ( DateTimeString >= 0 )
      {
        lpBuffera = v52;
        v17 = FormatMessageWedge(Buffer, a4, a5, v51);
        if ( v17 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4AF,
            (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
            (const char *)(unsigned int)v17,
            (int)v52);
          *a4 = 0;
        }
LABEL_13:
        if ( a1 )
        {
          if ( a1 != 4 )
          {
            if ( a1 != 1 && a1 != 2 )
            {
              v18 = v41;
LABEL_25:
              v20 = v18 == 0;
              if ( v18 < 0 )
                goto LABEL_28;
              v18 = -2147467259;
              wil::details::in1diag3::Log_Hr(
                retaddr,
                (void *)0x4D3,
                (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
                (const char *)0x80004005LL,
                (int)lpBuffera);
LABEL_27:
              v20 = v18 == 0;
LABEL_28:
              if ( v20 )
              {
                if ( !v44.dwLowDateTime && !v44.dwHighDateTime )
                  return v11;
                if ( v53[0] )
                {
                  LoadStringW(g_hInst, 0x1F6u, Buffer, 260);
                  v31 = GetDateTimeString(&v43, 1, v51, v30);
                  if ( v31 >= 0 )
                  {
                    v31 = GetDateTimeString(&v43, 0, v52, v32);
                    if ( v31 >= 0 )
                    {
                      lpBuffera = v52;
                      v28 = FormatMessageWedge(Buffer, a2, v6, v51);
                      if ( v28 >= 0 )
                        return v11;
                      v29 = 1252;
                      goto LABEL_79;
                    }
                    v33 = 1251;
                  }
                  else
                  {
                    v33 = 1250;
                  }
                }
                else
                {
                  LoadStringW(g_hInst, 0x1F7u, Buffer, 260);
                  v31 = GetDateTimeString(&v43, 1, v51, v34);
                  if ( v31 >= 0 )
                  {
                    v31 = GetDateTimeString(&v43, 0, v52, v35);
                    if ( v31 >= 0 )
                    {
                      lpBuffera = v52;
                      v28 = FormatMessageWedge(Buffer, a2, v6, v51);
                      if ( v28 >= 0 )
                        return v11;
                      v29 = 1264;
                      goto LABEL_79;
                    }
                    v33 = 1263;
                  }
                  else
                  {
                    v33 = 1262;
                  }
                }
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)v33,
                  (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
                  (const char *)(unsigned int)v31,
                  (int)lpBuffera);
                return v11;
              }
              if ( v18 == 1 )
              {
                *a2 = 0;
                return v11;
              }
              if ( !v46 || !v44.dwLowDateTime && !v44.dwHighDateTime )
              {
                if ( dwMessageId )
                {
                  v55[0] = 0;
                  GetW32TimeErrorMessage(dwMessageId, v54, v16);
                  if ( v53[0] )
                  {
                    LoadStringW(g_hInst, 0x1F8u, Buffer, 260);
                    lpBuffera = v54;
                    v28 = FormatMessageWedge(Buffer, a2, v6, v53);
                    if ( v28 >= 0 )
                      return v11;
                    v29 = 1349;
                  }
                  else
                  {
                    LoadStringW(g_hInst, 0x1FFu, Buffer, 260);
                    v28 = FormatMessageWedge(Buffer, a2, v6, v54);
                    if ( v28 >= 0 )
                      return v11;
                    v29 = 1357;
                  }
                }
                else
                {
                  LoadStringW(g_hInst, 0x1F9u, Buffer, 260);
                  v28 = FormatMessageWedge(Buffer, a2, v6, v53);
                  if ( v28 >= 0 )
                    return v11;
                  v29 = 1370;
                }
                goto LABEL_79;
              }
              v54[0] = 0;
              v55[0] = 0;
              if ( a1 == 4 )
              {
                LoadStringW(g_hInst, 0x1FCu, v54, 2084);
              }
              else
              {
                if ( !dwMessageId )
                  goto LABEL_38;
                GetW32TimeErrorMessage(dwMessageId, v54, v16);
              }
              if ( v54[0] )
              {
LABEL_40:
                v21 = 504;
                goto LABEL_43;
              }
LABEL_38:
              if ( FormatMessageW(0x1000u, 0, (unsigned __int16)v18, 0, v54, 0x824u, 0) )
              {
                CleanUpErrorString(v54);
                if ( v54[0] )
                  goto LABEL_40;
              }
              else
              {
                v54[0] = 0;
              }
              v21 = 505;
LABEL_43:
              LoadStringW(g_hInst, v21, Buffer, 260);
              lpBufferb = v54;
              v22 = FormatMessageWedge(Buffer, v55, 0x824u, v53);
              if ( v22 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x522,
                  (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
                  (const char *)(unsigned int)v22,
                  (int)v54);
                v55[0] = 0;
              }
              LoadStringW(g_hInst, 0x1FAu, Buffer, 260);
              v24 = GetDateTimeString(&v43, 1, v51, v23);
              if ( v24 >= 0 )
              {
                v24 = GetDateTimeString(&v43, 0, v52, v25);
                if ( v24 >= 0 )
                {
                  v27 = FormatMessageWedge(Buffer, v54, 0x824u, v51);
                  if ( v27 < 0 )
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x52E,
                      (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
                      (const char *)(unsigned int)v27,
                      (int)v52);
                    v54[0] = 0;
                  }
                  goto LABEL_52;
                }
                v26 = 1325;
              }
              else
              {
                v26 = 1324;
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)v26,
                (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
                (const char *)(unsigned int)v24,
                (int)lpBufferb);
LABEL_52:
              v28 = StringCchPrintfW(a2, v6, L"%s\n\n%s", v55, v54);
              if ( v28 >= 0 )
                return v11;
              v29 = 1332;
LABEL_79:
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)v29,
                (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
                (const char *)(unsigned int)v28,
                (int)lpBuffera);
              *a2 = 0;
              return v11;
            }
            v18 = v41;
            v20 = v41 == 0;
            if ( v41 < 0 )
              goto LABEL_28;
            v18 = -2147023436;
            v19 = 1227;
LABEL_24:
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)v19,
              (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
              (const char *)(unsigned int)v18,
              (int)lpBuffera);
            goto LABEL_25;
          }
        }
        else
        {
          if ( !v45 )
          {
            v18 = v41;
            goto LABEL_27;
          }
          a1 = 4;
        }
        v18 = -2147467259;
        v19 = 1220;
        goto LABEL_24;
      }
      v15 = 1198;
    }
    else
    {
      v15 = 1197;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
      (const char *)(unsigned int)DateTimeString,
      lpBuffer);
    goto LABEL_13;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x4A5,
    (unsigned int)"shell\\cpls\\utc\\inettime.cpp",
    (const char *)(unsigned int)ErrorInfoWrapHelper,
    lpBuffer);
  LoadStringW(g_hInst, 0x1FDu, Buffer, 260);
  if ( FormatMessageW(0x1000u, 0, (unsigned __int16)v11, 0, v51, 0x104u, 0) )
    CleanUpErrorString(v51);
  else
    v51[0] = 0;
  return (unsigned int)FormatMessageWedge(Buffer, a2, v6, v51);
}

```

## disassembly

```asm
0x180013ec4  mov     [rsp-8+arg_0], rbx
0x180013ec9  push    rbp
0x180013eca  push    rsi
0x180013ecb  push    rdi
0x180013ecc  push    r12
0x180013ece  push    r13
0x180013ed0  push    r14
0x180013ed2  push    r15
0x180013ed4  lea     rbp, [rsp-2880h]
0x180013edc  mov     eax, 2980h
0x180013ee1  call    _alloca_probe
0x180013ee6  sub     rsp, rax
0x180013ee9  mov     rax, cs:__security_cookie
0x180013ef0  xor     rax, rsp
0x180013ef3  mov     [rbp+28B0h+var_40], rax
0x180013efa  xor     ebx, ebx
0x180013efc  mov     r12d, r8d
0x180013eff  mov     rsi, rdx
0x180013f02  mov     [rsp+29B0h+var_2940], ebx
0x180013f06  mov     rdx, [rbp+28B0h+arg_28]
0x180013f0d  lea     rax, [rbp+28B0h+var_22F0]
0x180013f14  mov     [rsp+29B0h+var_2968], rdx; PCWSTR
0x180013f19  lea     r8, [rbp+28B0h+FileTime]; struct _FILETIME *
0x180013f1d  mov     [rsp+29B0h+var_2978], rax; PCWSTR
0x180013f22  lea     rdx, [rsp+29B0h+var_2944]; unsigned int *
0x180013f27  lea     rax, [rsp+29B0h+var_2948]
0x180013f2c  mov     [rsi], bx
0x180013f2f  mov     [rsp+29B0h+Arguments], rax; int *
0x180013f34  mov     rdi, r9
0x180013f37  lea     rax, [rsp+29B0h+dwMessageId]
0x180013f3c  mov     [r9], bx
0x180013f40  mov     qword ptr [rsp+29B0h+nSize], rax; unsigned int *
0x180013f45  lea     r9, [rsp+29B0h+var_2950]; struct _FILETIME *
0x180013f4a  lea     rax, [rsp+29B0h+var_2960]
0x180013f4f  mov     qword ptr [rbp+28B0h+FileTime.dwLowDateTime], rbx
0x180013f53  mov     r14d, ecx
0x180013f56  mov     [rsp+29B0h+lpBuffer], rax; int
0x180013f5b  lea     rcx, [rsp+29B0h+var_2940]; unsigned int *
0x180013f60  mov     qword ptr [rsp+29B0h+var_2950.dwLowDateTime], rbx
0x180013f65  mov     qword ptr [rsp+29B0h+LocalFileTime.dwLowDateTime], rbx
0x180013f6a  mov     qword ptr [rsp+29B0h+var_2958.dwLowDateTime], rbx
0x180013f6f  mov     [rsp+29B0h+dwMessageId], ebx
0x180013f73  mov     [rsp+29B0h+var_2948], ebx
0x180013f77  mov     [rsp+29B0h+var_2960], ebx
0x180013f7b  mov     [rsp+29B0h+var_2944], ebx
0x180013f7f  call    ?W32TimeGetErrorInfoWrapHelper@@YAJPEAIPEAKPEAU_FILETIME@@2PEAJ0PEAHPEAGK5@Z; W32TimeGetErrorInfoWrapHelper(uint *,ulong *,_FILETIME *,_FILETIME *,long *,uint *,int *,ushort *,ulong,ushort *)
0x180013f84  mov     r13d, eax
0x180013f87  test    eax, eax
0x180013f89  jns     loc_18001402A
0x180013f8f  mov     rcx, [rbp+28B8h]; this
0x180013f96  lea     r8, aShellCplsUtcIn_0; "shell\\cpls\\utc\\inettime.cpp"
0x180013f9d  mov     r9d, eax; char *
0x180013fa0  mov     edx, 4A5h; void *
0x180013fa5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013faa  mov     rcx, cs:g_hInst; hInstance
0x180013fb1  lea     r8, [rbp+28B0h+Buffer]; lpBuffer
0x180013fb5  mov     r15d, 104h
0x180013fbb  mov     edx, 1FDh; uID
0x180013fc0  mov     r9d, r15d; cchBufferMax
0x180013fc3  call    cs:__imp_LoadStringW
0x180013fc9  lea     rax, [rbp+28B0h+var_2710]
0x180013fd0  mov     [rsp+29B0h+Arguments], rbx; Arguments
0x180013fd5  movzx   r8d, r13w; dwMessageId
0x180013fd9  xor     r9d, r9d; dwLanguageId
0x180013fdc  mov     [rsp+29B0h+nSize], r15d; nSize
0x180013fe1  xor     edx, edx; lpSource
0x180013fe3  mov     ecx, 1000h; dwFlags
0x180013fe8  mov     [rsp+29B0h+lpBuffer], rax; lpBuffer
0x180013fed  call    cs:__imp_FormatMessageW
0x180013ff3  test    eax, eax
0x180013ff5  jnz     short loc_180014000
0x180013ff7  mov     [rbp+28B0h+var_2710], bx
0x180013ffe  jmp     short loc_18001400C
0x180014000  lea     rcx, [rbp+28B0h+var_2710]; unsigned __int16 *
0x180014007  call    ?CleanUpErrorString@@YAJPEAG@Z; CleanUpErrorString(ushort *)
0x18001400c  lea     r9, [rbp+28B0h+var_2710]
0x180014013  mov     r8d, r12d; unsigned int
0x180014016  mov     rdx, rsi; unsigned __int16 *
0x180014019  lea     rcx, [rbp+28B0h+Buffer]; lpSource
0x18001401d  call    ?FormatMessageWedge@@YAJPEBGPEAGKZZ; FormatMessageWedge(ushort const *,ushort *,ulong,...)
0x180014022  mov     r13d, eax
0x180014025  jmp     loc_180014621
0x18001402a  lea     rdx, [rsp+29B0h+LocalFileTime]; lpLocalFileTime
0x18001402f  lea     rcx, [rbp+28B0h+FileTime]; lpFileTime
0x180014033  call    cs:__imp_FileTimeToLocalFileTime
0x180014039  lea     rdx, [rsp+29B0h+var_2958]; lpLocalFileTime
0x18001403e  lea     rcx, [rsp+29B0h+var_2950]; lpFileTime
0x180014043  call    cs:__imp_FileTimeToLocalFileTime
0x180014049  mov     rcx, cs:g_hInst; hInstance
0x180014050  lea     r8, [rbp+28B0h+Buffer]; lpBuffer
0x180014054  mov     r15d, 104h
0x18001405a  mov     edx, 1F5h; uID
0x18001405f  mov     r9d, r15d; cchBufferMax
0x180014062  call    cs:__imp_LoadStringW
0x180014068  lea     r8, [rbp+28B0h+var_2710]; unsigned __int16 *
0x18001406f  mov     edx, 1; int
0x180014074  lea     rcx, [rsp+29B0h+LocalFileTime]; lpFileTime
0x180014079  call    ?GetDateTimeString@@YAJPEBU_FILETIME@@HPEAGK@Z; GetDateTimeString(_FILETIME const *,int,ushort *,ulong)
0x18001407e  lea     rbx, aShellCplsUtcIn_0; "shell\\cpls\\utc\\inettime.cpp"
0x180014085  test    eax, eax
0x180014087  jns     short loc_1800140A5
0x180014089  mov     edx, 4ADh; void *
0x18001408e  mov     rcx, [rbp+28B8h]; this
0x180014095  mov     r8, rbx; unsigned int
0x180014098  mov     r9d, eax; char *
0x18001409b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800140a0  xor     r9d, r9d
0x1800140a3  jmp     short loc_18001410E
0x1800140a5  lea     r8, [rbp+28B0h+var_2500]; unsigned __int16 *
0x1800140ac  xor     edx, edx; int
0x1800140ae  lea     rcx, [rsp+29B0h+LocalFileTime]; lpFileTime
0x1800140b3  call    ?GetDateTimeString@@YAJPEBU_FILETIME@@HPEAGK@Z; GetDateTimeString(_FILETIME const *,int,ushort *,ulong)
0x1800140b8  test    eax, eax
0x1800140ba  jns     short loc_1800140C3
0x1800140bc  mov     edx, 4AEh
0x1800140c1  jmp     short loc_18001408E
0x1800140c3  mov     r8d, [rbp+28B0h+arg_20]; unsigned int
0x1800140ca  lea     rax, [rbp+28B0h+var_2500]
0x1800140d1  lea     r9, [rbp+28B0h+var_2710]
0x1800140d8  mov     [rsp+29B0h+lpBuffer], rax; int
0x1800140dd  mov     rdx, rdi; unsigned __int16 *
0x1800140e0  lea     rcx, [rbp+28B0h+Buffer]; lpSource
0x1800140e4  call    ?FormatMessageWedge@@YAJPEBGPEAGKZZ; FormatMessageWedge(ushort const *,ushort *,ulong,...)
0x1800140e9  xor     r9d, r9d
0x1800140ec  test    eax, eax
0x1800140ee  jns     short loc_18001410E
0x1800140f0  mov     rcx, [rbp+28B8h]; this
0x1800140f7  mov     r9d, eax; char *
0x1800140fa  mov     r8, rbx; unsigned int
0x1800140fd  mov     edx, 4AFh; void *
0x180014102  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014107  xor     r9d, r9d
0x18001410a  mov     [rdi], r9w
0x18001410e  test    r14d, r14d
0x180014111  jnz     short loc_180014128
0x180014113  cmp     [rsp+29B0h+var_2948], r9d
0x180014118  jz      short loc_180014122
0x18001411a  mov     r14d, 4
0x180014120  jmp     short loc_18001412E
0x180014122  mov     edi, [rsp+29B0h+var_2960]
0x180014126  jmp     short loc_180014196
0x180014128  cmp     r14d, 4
0x18001412c  jnz     short loc_18001413A
0x18001412e  mov     edi, 80004005h
0x180014133  mov     edx, 4C4h
0x180014138  jmp     short loc_18001415E
0x18001413a  cmp     r14d, 1
0x18001413e  jz      short loc_18001414C
0x180014140  cmp     r14d, 2
0x180014144  jz      short loc_18001414C
0x180014146  mov     edi, [rsp+29B0h+var_2960]
0x18001414a  jmp     short loc_180014173
0x18001414c  mov     edi, [rsp+29B0h+var_2960]
0x180014150  test    edi, edi
0x180014152  js      short loc_180014198
0x180014154  mov     edi, 800705B4h
0x180014159  mov     edx, 4CBh; void *
0x18001415e  mov     rcx, [rbp+28B8h]; this
0x180014165  mov     r9d, edi; char *
0x180014168  mov     r8, rbx; unsigned int
0x18001416b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180014170  xor     r9d, r9d
0x180014173  test    edi, edi
0x180014175  js      short loc_180014198
0x180014177  mov     rcx, [rbp+28B8h]; this
0x18001417e  mov     edi, 80004005h
0x180014183  mov     r9d, edi; char *
0x180014186  mov     r8, rbx; unsigned int
0x180014189  mov     edx, 4D3h; void *
0x18001418e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180014193  xor     r9d, r9d
0x180014196  test    edi, edi
0x180014198  jz      loc_1800144C3
0x18001419e  cmp     edi, 1
0x1800141a1  jz      loc_1800144BA
0x1800141a7  cmp     [rsp+29B0h+var_2944], r9d
0x1800141ac  jz      loc_1800143CC
0x1800141b2  cmp     [rsp+29B0h+var_2950.dwLowDateTime], r9d
0x1800141b7  jnz     short loc_1800141C4
0x1800141b9  cmp     [rsp+29B0h+var_2950.dwHighDateTime], r9d
0x1800141be  jz      loc_1800143CC
0x1800141c4  mov     [rbp+28B0h+var_20E0], r9w
0x1800141cc  mov     [rbp+28B0h+var_1090], r9w
0x1800141d4  cmp     r14d, 4
0x1800141d8  jnz     short loc_1800141FB
0x1800141da  mov     rcx, cs:g_hInst; hInstance
0x1800141e1  lea     r8, [rbp+28B0h+var_20E0]; lpBuffer
0x1800141e8  mov     r9d, 824h; cchBufferMax
0x1800141ee  mov     edx, 1FCh; uID
0x1800141f3  call    cs:__imp_LoadStringW
0x1800141f9  jmp     short loc_18001420F
0x1800141fb  mov     ecx, [rsp+29B0h+dwMessageId]; dwMessageId
0x1800141ff  test    ecx, ecx
0x180014201  jz      short loc_18001421C
0x180014203  lea     rdx, [rbp+28B0h+var_20E0]; unsigned __int16 *
0x18001420a  call    ?GetW32TimeErrorMessage@@YAXIPEAGK@Z; GetW32TimeErrorMessage(uint,ushort *,ulong)
0x18001420f  xor     r9d, r9d
0x180014212  cmp     r9w, [rbp+28B0h+var_20E0]
0x18001421a  jnz     short loc_180014269
0x18001421c  mov     [rsp+29B0h+Arguments], r9; Arguments
0x180014221  lea     rax, [rbp+28B0h+var_20E0]
0x180014228  mov     [rsp+29B0h+nSize], 824h; nSize
0x180014230  xor     r9d, r9d; dwLanguageId
0x180014233  movzx   r8d, di; dwMessageId
0x180014237  xor     edx, edx; lpSource
0x180014239  mov     ecx, 1000h; dwFlags
0x18001423e  mov     [rsp+29B0h+lpBuffer], rax; lpBuffer
0x180014243  call    cs:__imp_FormatMessageW
0x180014249  xor     r9d, r9d
0x18001424c  test    eax, eax
0x18001424e  jz      short loc_180014272
0x180014250  lea     rcx, [rbp+28B0h+var_20E0]; unsigned __int16 *
0x180014257  call    ?CleanUpErrorString@@YAJPEAG@Z; CleanUpErrorString(ushort *)
0x18001425c  xor     edi, edi
0x18001425e  cmp     [rbp+28B0h+var_20E0], di
0x180014265  jz      short loc_18001427C
0x180014267  jmp     short loc_18001426B
0x180014269  xor     edi, edi
0x18001426b  mov     edx, 1F8h
0x180014270  jmp     short loc_180014281
0x180014272  mov     [rbp+28B0h+var_20E0], r9w
0x18001427a  xor     edi, edi
0x18001427c  mov     edx, 1F9h; uID
0x180014281  mov     rcx, cs:g_hInst; hInstance
0x180014288  lea     r8, [rbp+28B0h+Buffer]; lpBuffer
0x18001428c  mov     r9d, r15d; cchBufferMax
0x18001428f  call    cs:__imp_LoadStringW
0x180014295  lea     rax, [rbp+28B0h+var_20E0]
0x18001429c  mov     r14d, 824h
0x1800142a2  mov     r8d, r14d; unsigned int
0x1800142a5  mov     [rsp+29B0h+lpBuffer], rax; int
0x1800142aa  lea     r9, [rbp+28B0h+var_22F0]
0x1800142b1  lea     rdx, [rbp+28B0h+var_1090]; unsigned __int16 *
0x1800142b8  lea     rcx, [rbp+28B0h+Buffer]; lpSource
0x1800142bc  call    ?FormatMessageWedge@@YAJPEBGPEAGKZZ; FormatMessageWedge(ushort const *,ushort *,ulong,...)
0x1800142c1  test    eax, eax
0x1800142c3  jns     short loc_1800142E3
0x1800142c5  mov     rcx, [rbp+28B8h]; this
0x1800142cc  mov     r9d, eax; char *
0x1800142cf  mov     r8, rbx; unsigned int
0x1800142d2  mov     edx, 522h; void *
0x1800142d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800142dc  mov     [rbp+28B0h+var_1090], di
0x1800142e3  mov     rcx, cs:g_hInst; hInstance
0x1800142ea  lea     r8, [rbp+28B0h+Buffer]; lpBuffer
0x1800142ee  mov     r9d, r15d; cchBufferMax
0x1800142f1  mov     edx, 1FAh; uID
0x1800142f6  call    cs:__imp_LoadStringW
0x1800142fc  lea     r8, [rbp+28B0h+var_2710]; unsigned __int16 *
0x180014303  mov     edx, 1; int
0x180014308  lea     rcx, [rsp+29B0h+var_2958]; lpFileTime
0x18001430d  call    ?GetDateTimeString@@YAJPEBU_FILETIME@@HPEAGK@Z; GetDateTimeString(_FILETIME const *,int,ushort *,ulong)
0x180014312  test    eax, eax
0x180014314  jns     short loc_18001432F
0x180014316  mov     edx, 52Ch; void *
0x18001431b  mov     rcx, [rbp+28B8h]; this
0x180014322  mov     r8, rbx; unsigned int
0x180014325  mov     r9d, eax; char *
0x180014328  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001432d  jmp     short loc_180014395
0x18001432f  lea     r8, [rbp+28B0h+var_2500]; unsigned __int16 *
0x180014336  xor     edx, edx; int
0x180014338  lea     rcx, [rsp+29B0h+var_2958]; lpFileTime
0x18001433d  call    ?GetDateTimeString@@YAJPEBU_FILETIME@@HPEAGK@Z; GetDateTimeString(_FILETIME const *,int,ushort *,ulong)
0x180014342  test    eax, eax
0x180014344  jns     short loc_18001434D
0x180014346  mov     edx, 52Dh
0x18001434b  jmp     short loc_18001431B
0x18001434d  lea     rax, [rbp+28B0h+var_2500]
0x180014354  mov     r8d, r14d; unsigned int
0x180014357  lea     r9, [rbp+28B0h+var_2710]
0x18001435e  mov     [rsp+29B0h+lpBuffer], rax; int
0x180014363  lea     rdx, [rbp+28B0h+var_20E0]; unsigned __int16 *
0x18001436a  lea     rcx, [rbp+28B0h+Buffer]; lpSource
0x18001436e  call    ?FormatMessageWedge@@YAJPEBGPEAGKZZ; FormatMessageWedge(ushort const *,ushort *,ulong,...)
0x180014373  test    eax, eax
0x180014375  jns     short loc_180014395
0x180014377  mov     rcx, [rbp+28B8h]; this
0x18001437e  mov     r9d, eax; char *
0x180014381  mov     r8, rbx; unsigned int
0x180014384  mov     edx, 52Eh; void *
0x180014389  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001438e  mov     [rbp+28B0h+var_20E0], di
0x180014395  lea     rax, [rbp+28B0h+var_20E0]
0x18001439c  mov     rdx, r12; unsigned __int64
0x18001439f  lea     r9, [rbp+28B0h+var_1090]
0x1800143a6  mov     [rsp+29B0h+lpBuffer], rax
0x1800143ab  lea     r8, aSS_2; "%s\n\n%s"
0x1800143b2  mov     rcx, rsi; unsigned __int16 *
0x1800143b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800143ba  test    eax, eax
0x1800143bc  jns     loc_180014621
0x1800143c2  mov     edx, 534h
0x1800143c7  jmp     loc_18001460C
0x1800143cc  mov     ecx, [rsp+29B0h+dwMessageId]; dwMessageId
0x1800143d0  test    ecx, ecx
0x1800143d2  jz      loc_180014477
0x1800143d8  lea     rdx, [rbp+28B0h+var_20E0]; unsigned __int16 *
0x1800143df  mov     [rbp+28B0h+var_1090], r9w
0x1800143e7  call    ?GetW32TimeErrorMessage@@YAXIPEAGK@Z; GetW32TimeErrorMessage(uint,ushort *,ulong)
  ... truncated ...
```
