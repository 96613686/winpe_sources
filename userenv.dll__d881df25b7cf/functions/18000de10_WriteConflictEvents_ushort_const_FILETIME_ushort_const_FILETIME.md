# _WriteConflictEvents(ushort const *,_FILETIME *,ushort const *,_FILETIME *)

- ea: `0x18000de10`
- end: `0x18000e080`
- name: `?_WriteConflictEvents@@YAXPEBGPEAU_FILETIME@@01@Z`
- size: `624`
- prototype: `void __fastcall(const unsigned __int16 *, FILETIME *lpFileTime, const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008dd8`

## callees

- `0x180007f80`
- `0x18000de10`
- `0x18000e088`
- `0x18000e640`
- `0x18001b3b4`
- `0x18001be90`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dfe1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e010`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dfe1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e010`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000de55`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000dee7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000de55`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000dee7`

## string_xrefs

- `0x18000debd`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

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
  int lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  wchar_t v18[200]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[200]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  SystemTime = 0;
  FileTimeToSystemTime(lpFileTime, &SystemTime);
  v7 = StringCchPrintfExW(Buffer, 0xC8u, 0, 0, 0x800u, L"Year: %d, Month %d, Day %d, Hour %d, Minute %d");
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v7,
      lpString2);
  FileTimeToSystemTime(a4, &SystemTime);
  v8 = StringCchPrintfExW(v18, 0xC8u, 0, 0, 0x800u, L"Year: %d, Month %d, Day %d, Hour %d, Minute %d");
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v8,
      lpString2a);
  v16 = 0;
  v9 = StringCchLengthW(a1, 0x7FFFFFFFu, &v16);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v9,
      lpString2a);
    return;
  }
  for ( i = &a1[v16]; i >= a1 && *i != 92; --i )
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
  McTemplateU0zzzz_EventWriteTransfer(v12, (_DWORD)v13, (_DWORD)a1, (unsigned int)Buffer, (__int64)a3, (__int64)v18);
}

```

## disassembly

```asm
0x18000de10  push    rbp
0x18000de12  push    rbx
0x18000de13  push    rsi
0x18000de14  push    rdi
0x18000de15  push    r13
0x18000de17  push    r14
0x18000de19  lea     rbp, [rsp-2B8h]
0x18000de21  sub     rsp, 3B8h
0x18000de28  mov     rax, cs:__security_cookie
0x18000de2f  xor     rax, rsp
0x18000de32  mov     [rbp+2E0h+var_40], rax
0x18000de39  mov     rax, rdx
0x18000de3c  mov     rbx, rcx
0x18000de3f  xorps   xmm0, xmm0
0x18000de42  lea     rdx, [rsp+3E0h+SystemTime]; lpSystemTime
0x18000de47  mov     rcx, rax; lpFileTime
0x18000de4a  mov     rdi, r9
0x18000de4d  mov     rsi, r8
0x18000de50  movups  xmmword ptr [rsp+3E0h+SystemTime.wYear], xmm0
0x18000de55  call    cs:__imp_FileTimeToSystemTime
0x18000de5c  nop     dword ptr [rax+rax+00h]
0x18000de61  movzx   ecx, [rsp+3E0h+SystemTime.wHour]
0x18000de66  lea     r13, aYearDMonthDDay; "Year: %d, Month %d, Day %d, Hour %d, Mi"...
0x18000de6d  movzx   edx, [rsp+3E0h+SystemTime.wDay]
0x18000de72  movzx   r8d, [rsp+3E0h+SystemTime.wMonth]
0x18000de78  movzx   r9d, [rsp+3E0h+SystemTime.wYear]
0x18000de7e  movzx   eax, [rsp+3E0h+SystemTime.wMinute]
0x18000de83  mov     [rsp+3E0h+var_390], eax
0x18000de87  mov     [rsp+3E0h+var_398], ecx
0x18000de8b  lea     rcx, [rbp+2E0h+Buffer]; Buffer
0x18000de92  mov     [rsp+3E0h+var_3A0], edx
0x18000de96  mov     edx, 0C8h; unsigned __int64
0x18000de9b  mov     [rsp+3E0h+var_3A8], r8d
0x18000dea0  xor     r8d, r8d; unsigned __int16 **
0x18000dea3  mov     [rsp+3E0h+var_3B0], r9d
0x18000dea8  xor     r9d, r9d; unsigned __int64 *
0x18000deab  mov     qword ptr [rsp+3E0h+cchCount2], r13; unsigned __int16 *
0x18000deb0  mov     dword ptr [rsp+3E0h+lpString2], 800h; int
0x18000deb8  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000debd  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000dec4  test    eax, eax
0x18000dec6  jns     short loc_18000DEDF
0x18000dec8  mov     rcx, [rbp+2E8h]; this
0x18000decf  mov     r9d, eax; char *
0x18000ded2  mov     r8, r14; unsigned int
0x18000ded5  mov     edx, 1E3h; void *
0x18000deda  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dedf  lea     rdx, [rsp+3E0h+SystemTime]; lpSystemTime
0x18000dee4  mov     rcx, rdi; lpFileTime
0x18000dee7  call    cs:__imp_FileTimeToSystemTime
0x18000deee  nop     dword ptr [rax+rax+00h]
0x18000def3  movzx   ecx, [rsp+3E0h+SystemTime.wHour]
0x18000def8  mov     edx, 0C8h; unsigned __int64
0x18000defd  movzx   r8d, [rsp+3E0h+SystemTime.wDay]
0x18000df03  movzx   r9d, [rsp+3E0h+SystemTime.wMonth]
0x18000df09  movzx   eax, [rsp+3E0h+SystemTime.wMinute]
0x18000df0e  movzx   r10d, [rsp+3E0h+SystemTime.wYear]
0x18000df14  mov     [rsp+3E0h+var_390], eax
0x18000df18  mov     [rsp+3E0h+var_398], ecx
0x18000df1c  lea     rcx, [rbp+2E0h+var_360]; Buffer
0x18000df20  mov     [rsp+3E0h+var_3A0], r8d
0x18000df25  xor     r8d, r8d; unsigned __int16 **
0x18000df28  mov     [rsp+3E0h+var_3A8], r9d
0x18000df2d  xor     r9d, r9d; unsigned __int64 *
0x18000df30  mov     [rsp+3E0h+var_3B0], r10d
0x18000df35  mov     qword ptr [rsp+3E0h+cchCount2], r13; unsigned __int16 *
0x18000df3a  mov     dword ptr [rsp+3E0h+lpString2], 800h; int
0x18000df42  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000df47  test    eax, eax
0x18000df49  jns     short loc_18000DF62
0x18000df4b  mov     rcx, [rbp+2E8h]; this
0x18000df52  mov     r9d, eax; char *
0x18000df55  mov     r8, r14; unsigned int
0x18000df58  mov     edx, 1FBh; void *
0x18000df5d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000df62  lea     r8, [rsp+3E0h+var_380]; unsigned __int64 *
0x18000df67  mov     [rsp+3E0h+var_380], 0
0x18000df70  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000df75  mov     rcx, rbx; unsigned __int16 *
0x18000df78  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000df7d  test    eax, eax
0x18000df7f  jns     short loc_18000DF9D
0x18000df81  mov     rcx, [rbp+2E8h]; this
0x18000df88  mov     r9d, eax; char *
0x18000df8b  mov     r8, r14; unsigned int
0x18000df8e  mov     edx, 208h; void *
0x18000df93  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000df98  jmp     loc_18000E060
0x18000df9d  mov     rax, [rsp+3E0h+var_380]
0x18000dfa2  lea     rcx, [rbx+rax*2]
0x18000dfa6  jmp     short loc_18000DFB6
0x18000dfa8  mov     eax, 5Ch ; '\'
0x18000dfad  cmp     ax, [rcx]
0x18000dfb0  jz      short loc_18000DFBB
0x18000dfb2  sub     rcx, 2
0x18000dfb6  cmp     rcx, rbx
0x18000dfb9  jnb     short loc_18000DFA8
0x18000dfbb  or      r14d, 0FFFFFFFFh
0x18000dfbf  lea     rdi, [rcx+2]
0x18000dfc3  lea     rax, aNtuserDat; "ntuser.dat"
0x18000dfca  mov     [rsp+3E0h+cchCount2], r14d; cchCount2
0x18000dfcf  mov     r9d, r14d; cchCount1
0x18000dfd2  mov     [rsp+3E0h+lpString2], rax; lpString2
0x18000dfd7  mov     r8, rdi; lpString1
0x18000dfda  lea     edx, [r14+2]; dwCmpFlags
0x18000dfde  lea     ecx, [rdx+7Eh]; Locale
0x18000dfe1  call    cs:__imp_CompareStringW
0x18000dfe8  nop     dword ptr [rax+rax+00h]
0x18000dfed  cmp     eax, 2
0x18000dff0  jz      short loc_18000E033
0x18000dff2  lea     edx, [r14+2]; dwCmpFlags
0x18000dff6  mov     [rsp+3E0h+cchCount2], r14d; cchCount2
0x18000dffb  lea     rax, aNtuserMan; "ntuser.man"
0x18000e002  mov     r9d, r14d; cchCount1
0x18000e005  lea     ecx, [rdx+7Eh]; Locale
0x18000e008  mov     [rsp+3E0h+lpString2], rax; lpString2
0x18000e00d  mov     r8, rdi; lpString1
0x18000e010  call    cs:__imp_CompareStringW
0x18000e017  nop     dword ptr [rax+rax+00h]
0x18000e01c  cmp     eax, 2
0x18000e01f  jz      short loc_18000E033
0x18000e021  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 10h
0x18000e028  jz      short loc_18000E060
0x18000e02a  lea     rdx, EVENT_RUP_TIMESTAMP_CONFLICT
0x18000e031  jmp     short loc_18000E043
0x18000e033  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 2
0x18000e03a  jz      short loc_18000E060
0x18000e03c  lea     rdx, EVENT_RUP_NTUSER_TIMESTAMP_CONFLICT
0x18000e043  lea     rax, [rbp+2E0h+var_360]
0x18000e047  mov     r8, rbx
0x18000e04a  mov     qword ptr [rsp+3E0h+cchCount2], rax
0x18000e04f  lea     r9, [rbp+2E0h+Buffer]
0x18000e056  mov     [rsp+3E0h+lpString2], rsi
0x18000e05b  call    McTemplateU0zzzz_EventWriteTransfer
0x18000e060  mov     rcx, [rbp+2E0h+var_40]
0x18000e067  xor     rcx, rsp; StackCookie
0x18000e06a  call    __security_check_cookie
0x18000e06f  add     rsp, 3B8h
0x18000e076  pop     r14
0x18000e078  pop     r13
0x18000e07a  pop     rdi
0x18000e07b  pop     rsi
0x18000e07c  pop     rbx
0x18000e07d  pop     rbp
0x18000e07e  retn
```
