# PrintDateStringXmlTag

- ea: `0x14001f0f8`
- end: `0x14001f32a`
- name: `PrintDateStringXmlTag`
- size: `562`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400208e4`

## callees

- `0x140009c78`
- `0x14001f0f8`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14001f15e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x14001f15e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x14001f18a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x14001f18a`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x14001f20e`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x14001f20e`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x14001f1ef`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x14001f1ef`

## pseudocode

```c
__int64 __fastcall PrintDateStringXmlTag(unsigned __int16 *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, char a6)
{
  unsigned int v9; // ecx
  LPWSTR lpDateStr; // [rsp+20h] [rbp-E0h]
  __int64 cchDate; // [rsp+28h] [rbp-D8h]
  FILETIME FileTime; // [rsp+70h] [rbp-90h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  WCHAR TimeStr[128]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR DateStr[128]; // [rsp+1A0h] [rbp+A0h] BYREF

  FileTime = (FILETIME)a5;
  SystemTime = 0;
  LocalTime = 0;
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) && SystemTime.wMonth <= 0xCu )
  {
    if ( a6 )
    {
      if ( !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
        goto LABEL_5;
    }
    else
    {
      LocalTime = SystemTime;
    }
    if ( LocalTime.wMonth <= 0xCu )
    {
      DateStr[0] = 0;
      TimeStr[0] = 0;
      GetDateFormatW(0x400u, 2u, &LocalTime, 0, DateStr, 128);
      GetTimeFormatW(0x400u, 0, &LocalTime, 0, TimeStr, 128);
      if ( a4 )
      {
        LODWORD(cchDate) = LocalTime.wYear;
        return (unsigned int)StringCchPrintfW(
                               a1,
                               0x400u,
                               L"\t\t<Data name='%s' %s year='%d' month='%d' day='%d' weekday='%d' hour='%d' minute='%d' s"
                                "econd='%d'>%s %s</Data>\r\n",
                               a3,
                               a4,
                               cchDate,
                               LocalTime.wMonth,
                               LocalTime.wDay,
                               LocalTime.wDayOfWeek,
                               LocalTime.wHour,
                               LocalTime.wMinute,
                               LocalTime.wSecond,
                               DateStr,
                               TimeStr);
      }
      else
      {
        LODWORD(cchDate) = LocalTime.wMonth;
        LODWORD(lpDateStr) = LocalTime.wYear;
        return (unsigned int)StringCchPrintfW(
                               a1,
                               0x400u,
                               L"\t\t<Data name='%s' year='%d' month='%d' day='%d' weekday='%d' hour='%d' minute='%d' seco"
                                "nd='%d'>%s %s</Data>\r\n",
                               a3,
                               lpDateStr,
                               cchDate,
                               LocalTime.wDay,
                               LocalTime.wDayOfWeek,
                               LocalTime.wHour,
                               LocalTime.wMinute,
                               LocalTime.wSecond,
                               DateStr,
                               TimeStr);
      }
    }
LABEL_5:
    v9 = 0;
    *a1 = 0;
    return v9;
  }
  *a1 = 0;
  return 1;
}

```

## disassembly

```asm
0x14001f0f8  mov     [rsp-8+arg_8], rbx
0x14001f0fd  push    rbp
0x14001f0fe  push    rsi
0x14001f0ff  push    rdi
0x14001f100  push    r12
0x14001f102  push    r13
0x14001f104  push    r14
0x14001f106  push    r15
0x14001f108  lea     rbp, [rsp-1B0h]
0x14001f110  sub     rsp, 2B0h
0x14001f117  mov     rax, cs:__security_cookie
0x14001f11e  xor     rax, rsp
0x14001f121  mov     [rbp+1E0h+var_40], rax
0x14001f128  mov     r14, rcx
0x14001f12b  lea     rdx, [rbp+1E0h+SystemTime]; lpSystemTime
0x14001f12f  mov     rcx, [rbp+1E0h+arg_20]
0x14001f136  xorps   xmm0, xmm0
0x14001f139  mov     rax, rcx
0x14001f13c  mov     [rsp+2E0h+FileTime.dwLowDateTime], ecx
0x14001f140  shr     rax, 20h
0x14001f144  lea     rcx, [rsp+2E0h+FileTime]; lpFileTime
0x14001f149  xorps   xmm1, xmm1
0x14001f14c  mov     [rsp+2E0h+FileTime.dwHighDateTime], eax
0x14001f150  mov     r15, r9
0x14001f153  mov     r12, r8
0x14001f156  movups  xmmword ptr [rbp+1E0h+SystemTime.wYear], xmm0
0x14001f15a  movups  xmmword ptr [rbp+1E0h+LocalTime.wYear], xmm1
0x14001f15e  call    cs:__imp_FileTimeToSystemTime
0x14001f164  test    eax, eax
0x14001f166  jz      loc_14001F2F5
0x14001f16c  cmp     [rbp+1E0h+SystemTime.wMonth], 0Ch
0x14001f171  ja      loc_14001F2F5
0x14001f177  cmp     [rbp+1E0h+arg_28], 0
0x14001f17e  jz      short loc_14001F1A3
0x14001f180  lea     r8, [rbp+1E0h+LocalTime]; lpLocalTime
0x14001f184  xor     ecx, ecx; lpTimeZoneInformation
0x14001f186  lea     rdx, [rbp+1E0h+SystemTime]; lpUniversalTime
0x14001f18a  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x14001f190  test    eax, eax
0x14001f192  jnz     short loc_14001F1AC
0x14001f194  xor     ecx, ecx
0x14001f196  xor     eax, eax
0x14001f198  mov     [r14], ax
0x14001f19c  mov     eax, ecx
0x14001f19e  jmp     loc_14001F300
0x14001f1a3  movaps  xmm0, xmmword ptr [rbp+1E0h+SystemTime.wYear]
0x14001f1a7  movdqa  xmmword ptr [rbp+1E0h+LocalTime.wYear], xmm0
0x14001f1ac  mov     rax, qword ptr [rbp+1E0h+LocalTime.wYear]
0x14001f1b0  shr     rax, 10h
0x14001f1b4  cmp     ax, 0Ch
0x14001f1b8  ja      short loc_14001F194
0x14001f1ba  xor     eax, eax
0x14001f1bc  lea     r8, [rbp+1E0h+LocalTime]; lpDate
0x14001f1c0  mov     ebx, 80h
0x14001f1c5  mov     [rbp+1E0h+DateStr], ax
0x14001f1cc  mov     [rbp+1E0h+TimeStr], ax
0x14001f1d0  mov     r13d, 400h
0x14001f1d6  lea     rax, [rbp+1E0h+DateStr]
0x14001f1dd  mov     dword ptr [rsp+2E0h+cchDate], ebx; cchDate
0x14001f1e1  xor     r9d, r9d; lpFormat
0x14001f1e4  mov     [rsp+2E0h+lpDateStr], rax; lpDateStr
0x14001f1e9  lea     edx, [rbx-7Eh]; dwFlags
0x14001f1ec  mov     ecx, r13d; Locale
0x14001f1ef  call    cs:__imp_GetDateFormatW
0x14001f1f5  lea     rax, [rbp+1E0h+TimeStr]
0x14001f1f9  mov     dword ptr [rsp+2E0h+cchDate], ebx; cchTime
0x14001f1fd  xor     r9d, r9d; lpFormat
0x14001f200  mov     [rsp+2E0h+lpDateStr], rax; lpTimeStr
0x14001f205  lea     r8, [rbp+1E0h+LocalTime]; lpTime
0x14001f209  xor     edx, edx; dwFlags
0x14001f20b  mov     ecx, r13d; Locale
0x14001f20e  call    cs:__imp_GetTimeFormatW
0x14001f214  movzx   eax, [rbp+1E0h+LocalTime.wSecond]
0x14001f218  test    r15, r15
0x14001f21b  jz      short loc_14001F28D
0x14001f21d  movzx   r8d, [rbp+1E0h+LocalTime.wMinute]
0x14001f222  lea     rcx, [rbp+1E0h+TimeStr]
0x14001f226  movzx   r10d, [rbp+1E0h+LocalTime.wHour]
0x14001f22b  mov     r9, r12
0x14001f22e  movzx   r11d, [rbp+1E0h+LocalTime.wDayOfWeek]
0x14001f233  mov     edx, r13d; unsigned __int64
0x14001f236  movzx   ebx, [rbp+1E0h+LocalTime.wDay]
0x14001f23a  movzx   edi, [rbp+1E0h+LocalTime.wMonth]
0x14001f23e  movzx   esi, [rbp+1E0h+LocalTime.wYear]
0x14001f242  mov     [rsp+2E0h+var_278], rcx
0x14001f247  lea     rcx, [rbp+1E0h+DateStr]
0x14001f24e  mov     [rsp+2E0h+var_280], rcx
0x14001f253  mov     rcx, r14; unsigned __int16 *
0x14001f256  mov     dword ptr [rsp+2E0h+var_288], eax
0x14001f25a  mov     [rsp+2E0h+var_290], r8d
0x14001f25f  lea     r8, aDataNameSSYear; "\t\t<Data name='%s' %s year='%d' month="...
0x14001f266  mov     [rsp+2E0h+var_298], r10d
0x14001f26b  mov     [rsp+2E0h+var_2A0], r11d
0x14001f270  mov     [rsp+2E0h+var_2A8], ebx
0x14001f274  mov     [rsp+2E0h+var_2B0], edi
0x14001f278  mov     dword ptr [rsp+2E0h+cchDate], esi
0x14001f27c  mov     [rsp+2E0h+lpDateStr], r15
0x14001f281  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001f286  mov     ecx, eax
0x14001f288  jmp     loc_14001F19C
0x14001f28d  movzx   ecx, [rbp+1E0h+LocalTime.wMinute]
0x14001f291  lea     rbx, [rbp+1E0h+TimeStr]
0x14001f295  movzx   edx, [rbp+1E0h+LocalTime.wHour]
0x14001f299  movzx   r8d, [rbp+1E0h+LocalTime.wDayOfWeek]
0x14001f29e  movzx   r9d, [rbp+1E0h+LocalTime.wDay]
0x14001f2a3  movzx   r10d, [rbp+1E0h+LocalTime.wMonth]
0x14001f2a8  movzx   r11d, [rbp+1E0h+LocalTime.wYear]
0x14001f2ad  mov     [rsp+2E0h+var_280], rbx
0x14001f2b2  lea     rbx, [rbp+1E0h+DateStr]
0x14001f2b9  mov     [rsp+2E0h+var_288], rbx
0x14001f2be  mov     [rsp+2E0h+var_290], eax
0x14001f2c2  mov     [rsp+2E0h+var_298], ecx
0x14001f2c6  mov     rcx, r14; unsigned __int16 *
0x14001f2c9  mov     [rsp+2E0h+var_2A0], edx
0x14001f2cd  mov     rdx, r13; unsigned __int64
0x14001f2d0  mov     [rsp+2E0h+var_2A8], r8d
0x14001f2d5  lea     r8, aDataNameSYearD; "\t\t<Data name='%s' year='%d' month='%d"...
0x14001f2dc  mov     [rsp+2E0h+var_2B0], r9d
0x14001f2e1  mov     r9, r12
0x14001f2e4  mov     dword ptr [rsp+2E0h+cchDate], r10d
0x14001f2e9  mov     dword ptr [rsp+2E0h+lpDateStr], r11d
0x14001f2ee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001f2f3  jmp     short loc_14001F286
0x14001f2f5  xor     eax, eax
0x14001f2f7  mov     [r14], ax
0x14001f2fb  mov     eax, 1
0x14001f300  mov     rcx, [rbp+1E0h+var_40]
0x14001f307  xor     rcx, rsp; StackCookie
0x14001f30a  call    __security_check_cookie
0x14001f30f  mov     rbx, [rsp+2E0h+arg_8]
0x14001f317  add     rsp, 2B0h
0x14001f31e  pop     r15
0x14001f320  pop     r14
0x14001f322  pop     r13
0x14001f324  pop     r12
0x14001f326  pop     rdi
0x14001f327  pop     rsi
0x14001f328  pop     rbp
0x14001f329  retn
```
