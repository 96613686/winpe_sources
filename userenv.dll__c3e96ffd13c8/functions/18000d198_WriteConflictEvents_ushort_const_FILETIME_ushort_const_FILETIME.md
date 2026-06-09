# _WriteConflictEvents(ushort const *,_FILETIME *,ushort const *,_FILETIME *)

- ea: `0x18000d198`
- end: `0x18000d3ef`
- name: `?_WriteConflictEvents@@YAXPEBGPEAU_FILETIME@@01@Z`
- size: `599`
- prototype: `void __fastcall(const unsigned __int16 *, FILETIME *lpFileTime, const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800085b0`

## callees

- `0x1800072a0`
- `0x18000d198`
- `0x18000d3f8`
- `0x18000d9b0`
- `0x18001992c`
- `0x18001a3d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d35d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d386`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d35d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d386`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000d1dd`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000d269`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000d1dd`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000d269`

## string_xrefs

- `0x18000d23f`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
void __fastcall _WriteConflictEvents(
        const unsigned __int16 *a1,
        FILETIME *lpFileTime,
        const unsigned __int16 *a3,
        struct _FILETIME *a4)
{
  int v7; // eax
  int v8; // eax
  int v9; // eax
  const unsigned __int16 *i; // rcx
  const WCHAR *v11; // rdi
  int v12; // ecx
  __int64 *v13; // rdx
  int wYear; // [rsp+30h] [rbp-D0h]
  __int64 v15; // [rsp+30h] [rbp-D0h]
  int wMonth; // [rsp+38h] [rbp-C8h]
  __int64 v17; // [rsp+38h] [rbp-C8h]
  int wDay; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+40h] [rbp-C0h]
  int wHour; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+48h] [rbp-B8h]
  int wMinute; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  wchar_t v26[200]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[200]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  SystemTime = 0;
  FileTimeToSystemTime(lpFileTime, &SystemTime);
  wMinute = SystemTime.wMinute;
  wHour = SystemTime.wHour;
  wDay = SystemTime.wDay;
  wMonth = SystemTime.wMonth;
  wYear = SystemTime.wYear;
  v7 = StringCchPrintfExW(
         Buffer,
         0xC8u,
         0,
         0,
         0x800u,
         L"Year: %d, Month %d, Day %d, Hour %d, Minute %d",
         wYear,
         wMonth,
         wDay,
         wHour,
         wMinute);
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1E3,
      (int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v7);
  FileTimeToSystemTime(a4, &SystemTime);
  LODWORD(v23) = SystemTime.wMinute;
  LODWORD(v21) = SystemTime.wHour;
  LODWORD(v19) = SystemTime.wDay;
  LODWORD(v17) = SystemTime.wMonth;
  LODWORD(v15) = SystemTime.wYear;
  v8 = StringCchPrintfExW(
         v26,
         0xC8u,
         0,
         0,
         0x800u,
         L"Year: %d, Month %d, Day %d, Hour %d, Minute %d",
         v15,
         v17,
         v19,
         v21,
         v23);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1FB,
      (int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v8);
  v24 = 0;
  v9 = StringCchLengthW(a1, 0x7FFFFFFFu, &v24);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x208,
      (int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v9);
    return;
  }
  for ( i = &a1[v24]; i >= a1 && *i != 92; --i )
    ;
  v11 = i + 1;
  if ( CompareStringW(0x7Fu, 1u, i + 1, -1, L"ntuser.dat", -1) == 2
    || CompareStringW(0x7Fu, 1u, v11, -1, L"ntuser.man", -1) == 2 )
  {
    if ( (Microsoft_Windows_User_Profiles_GeneralEnableBits & 2) == 0 )
      return;
    v13 = EVENT_RUP_NTUSER_TIMESTAMP_CONFLICT;
  }
  else
  {
    if ( (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x10) == 0 )
      return;
    v13 = EVENT_RUP_TIMESTAMP_CONFLICT;
  }
  McTemplateU0zzzz_EventWriteTransfer(v12, (_DWORD)v13, (_DWORD)a1, (unsigned int)Buffer, (__int64)a3, (__int64)v26);
}

```

## disassembly

```asm
0x18000d198  push    rbp
0x18000d19a  push    rbx
0x18000d19b  push    rsi
0x18000d19c  push    rdi
0x18000d19d  push    r13
0x18000d19f  push    r14
0x18000d1a1  lea     rbp, [rsp-2B8h]
0x18000d1a9  sub     rsp, 3B8h
0x18000d1b0  mov     rax, cs:__security_cookie
0x18000d1b7  xor     rax, rsp
0x18000d1ba  mov     [rbp+2E0h+var_40], rax
0x18000d1c1  mov     rax, rdx
0x18000d1c4  mov     rbx, rcx
0x18000d1c7  xorps   xmm0, xmm0
0x18000d1ca  lea     rdx, [rsp+3E0h+SystemTime]; lpSystemTime
0x18000d1cf  mov     rcx, rax; lpFileTime
0x18000d1d2  mov     rdi, r9
0x18000d1d5  mov     rsi, r8
0x18000d1d8  movups  xmmword ptr [rsp+3E0h+SystemTime.wYear], xmm0
0x18000d1dd  call    cs:__imp_FileTimeToSystemTime
0x18000d1e3  movzx   ecx, [rsp+3E0h+SystemTime.wHour]
0x18000d1e8  lea     r13, aYearDMonthDDay; "Year: %d, Month %d, Day %d, Hour %d, Mi"...
0x18000d1ef  movzx   edx, [rsp+3E0h+SystemTime.wDay]
0x18000d1f4  movzx   r8d, [rsp+3E0h+SystemTime.wMonth]
0x18000d1fa  movzx   r9d, [rsp+3E0h+SystemTime.wYear]
0x18000d200  movzx   eax, [rsp+3E0h+SystemTime.wMinute]
0x18000d205  mov     [rsp+3E0h+var_390], eax
0x18000d209  mov     dword ptr [rsp+3E0h+var_398], ecx
0x18000d20d  lea     rcx, [rbp+2E0h+Buffer]; Buffer
0x18000d214  mov     dword ptr [rsp+3E0h+var_3A0], edx
0x18000d218  mov     edx, 0C8h; unsigned __int64
0x18000d21d  mov     dword ptr [rsp+3E0h+var_3A8], r8d
0x18000d222  xor     r8d, r8d; unsigned __int16 **
0x18000d225  mov     dword ptr [rsp+3E0h+var_3B0], r9d
0x18000d22a  xor     r9d, r9d; unsigned __int64 *
0x18000d22d  mov     qword ptr [rsp+3E0h+cchCount2], r13; unsigned __int16 *
0x18000d232  mov     dword ptr [rsp+3E0h+lpString2], 800h; int
0x18000d23a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000d23f  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000d246  test    eax, eax
0x18000d248  jns     short loc_18000D261
0x18000d24a  mov     rcx, [rbp+2E8h]; this
0x18000d251  mov     r9d, eax; char *
0x18000d254  mov     r8, r14; unsigned int
0x18000d257  mov     edx, 1E3h; void *
0x18000d25c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d261  lea     rdx, [rsp+3E0h+SystemTime]; lpSystemTime
0x18000d266  mov     rcx, rdi; lpFileTime
0x18000d269  call    cs:__imp_FileTimeToSystemTime
0x18000d26f  movzx   ecx, [rsp+3E0h+SystemTime.wHour]
0x18000d274  mov     edx, 0C8h; unsigned __int64
0x18000d279  movzx   r8d, [rsp+3E0h+SystemTime.wDay]
0x18000d27f  movzx   r9d, [rsp+3E0h+SystemTime.wMonth]
0x18000d285  movzx   eax, [rsp+3E0h+SystemTime.wMinute]
0x18000d28a  movzx   r10d, [rsp+3E0h+SystemTime.wYear]
0x18000d290  mov     [rsp+3E0h+var_390], eax
0x18000d294  mov     dword ptr [rsp+3E0h+var_398], ecx
0x18000d298  lea     rcx, [rbp+2E0h+var_360]; Buffer
0x18000d29c  mov     dword ptr [rsp+3E0h+var_3A0], r8d
0x18000d2a1  xor     r8d, r8d; unsigned __int16 **
0x18000d2a4  mov     dword ptr [rsp+3E0h+var_3A8], r9d
0x18000d2a9  xor     r9d, r9d; unsigned __int64 *
0x18000d2ac  mov     dword ptr [rsp+3E0h+var_3B0], r10d
0x18000d2b1  mov     qword ptr [rsp+3E0h+cchCount2], r13; unsigned __int16 *
0x18000d2b6  mov     dword ptr [rsp+3E0h+lpString2], 800h; int
0x18000d2be  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000d2c3  test    eax, eax
0x18000d2c5  jns     short loc_18000D2DE
0x18000d2c7  mov     rcx, [rbp+2E8h]; this
0x18000d2ce  mov     r9d, eax; char *
0x18000d2d1  mov     r8, r14; unsigned int
0x18000d2d4  mov     edx, 1FBh; void *
0x18000d2d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d2de  lea     r8, [rsp+3E0h+var_380]; unsigned __int64 *
0x18000d2e3  mov     [rsp+3E0h+var_380], 0
0x18000d2ec  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000d2f1  mov     rcx, rbx; unsigned __int16 *
0x18000d2f4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000d2f9  test    eax, eax
0x18000d2fb  jns     short loc_18000D319
0x18000d2fd  mov     rcx, [rbp+2E8h]; this
0x18000d304  mov     r9d, eax; char *
0x18000d307  mov     r8, r14; unsigned int
0x18000d30a  mov     edx, 208h; void *
0x18000d30f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d314  jmp     loc_18000D3D0
0x18000d319  mov     rax, [rsp+3E0h+var_380]
0x18000d31e  lea     rcx, [rbx+rax*2]
0x18000d322  jmp     short loc_18000D332
0x18000d324  mov     eax, 5Ch ; '\'
0x18000d329  cmp     ax, [rcx]
0x18000d32c  jz      short loc_18000D337
0x18000d32e  sub     rcx, 2
0x18000d332  cmp     rcx, rbx
0x18000d335  jnb     short loc_18000D324
0x18000d337  or      r14d, 0FFFFFFFFh
0x18000d33b  lea     rdi, [rcx+2]
0x18000d33f  lea     rax, aNtuserDat; "ntuser.dat"
0x18000d346  mov     [rsp+3E0h+cchCount2], r14d; cchCount2
0x18000d34b  mov     r9d, r14d; cchCount1
0x18000d34e  mov     [rsp+3E0h+lpString2], rax; lpString2
0x18000d353  mov     r8, rdi; lpString1
0x18000d356  lea     edx, [r14+2]; dwCmpFlags
0x18000d35a  lea     ecx, [rdx+7Eh]; Locale
0x18000d35d  call    cs:__imp_CompareStringW
0x18000d363  cmp     eax, 2
0x18000d366  jz      short loc_18000D3A3
0x18000d368  lea     edx, [r14+2]; dwCmpFlags
0x18000d36c  mov     [rsp+3E0h+cchCount2], r14d; cchCount2
0x18000d371  lea     rax, aNtuserMan; "ntuser.man"
0x18000d378  mov     r9d, r14d; cchCount1
0x18000d37b  lea     ecx, [rdx+7Eh]; Locale
0x18000d37e  mov     [rsp+3E0h+lpString2], rax; lpString2
0x18000d383  mov     r8, rdi; lpString1
0x18000d386  call    cs:__imp_CompareStringW
0x18000d38c  cmp     eax, 2
0x18000d38f  jz      short loc_18000D3A3
0x18000d391  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 10h
0x18000d398  jz      short loc_18000D3D0
0x18000d39a  lea     rdx, EVENT_RUP_TIMESTAMP_CONFLICT
0x18000d3a1  jmp     short loc_18000D3B3
0x18000d3a3  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 2
0x18000d3aa  jz      short loc_18000D3D0
0x18000d3ac  lea     rdx, EVENT_RUP_NTUSER_TIMESTAMP_CONFLICT
0x18000d3b3  lea     rax, [rbp+2E0h+var_360]
0x18000d3b7  mov     r8, rbx
0x18000d3ba  mov     qword ptr [rsp+3E0h+cchCount2], rax
0x18000d3bf  lea     r9, [rbp+2E0h+Buffer]
0x18000d3c6  mov     [rsp+3E0h+lpString2], rsi
0x18000d3cb  call    McTemplateU0zzzz_EventWriteTransfer
0x18000d3d0  mov     rcx, [rbp+2E0h+var_40]
0x18000d3d7  xor     rcx, rsp; StackCookie
0x18000d3da  call    __security_check_cookie
0x18000d3df  add     rsp, 3B8h
0x18000d3e6  pop     r14
0x18000d3e8  pop     r13
0x18000d3ea  pop     rdi
0x18000d3eb  pop     rsi
0x18000d3ec  pop     rbx
0x18000d3ed  pop     rbp
0x18000d3ee  retn
```
