# CSQMUtil::WriteSQM(void)

- ea: `0x180015240`
- end: `0x180015481`
- name: `?WriteSQM@CSQMUtil@@SAJXZ`
- size: `577`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180040a30`

## callees

- `0x180003f30`
- `0x180015240`
- `0x180017b30`
- `0x18001a280`
- `0x18001ad5c`
- `0x180041818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001543b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001543b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180015355`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180015355`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800153f0`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800153f0`
- `SQMAPI!SqmFlushSession` at `0x180015431`
- `SQMAPI!SqmFlushSession` at `0x180015431`
- `SQMAPI!SqmAddToStreamString` at `0x1800153bf`
- `SQMAPI!SqmAddToStreamString` at `0x1800153bf`
- `SQMAPI!SqmAddToStreamDWord` at `0x1800152f9`
- `SQMAPI!SqmAddToStreamDWord` at `0x180015342`
- `SQMAPI!SqmAddToStreamDWord` at `0x1800152f9`
- `SQMAPI!SqmAddToStreamDWord` at `0x180015342`

## string_xrefs

- `0x1800152c2`: `CSQMUtil::WriteSQM`

## pseudocode

```c
__int64 CSQMUtil::WriteSQM(void)
{
  int CountersValues; // eax
  signed int v1; // eax
  unsigned int v2; // ebx
  unsigned int i; // ebx
  signed int v4; // eax
  signed int LastError; // eax
  int wMonth; // [rsp+20h] [rbp-E0h]
  int wDay; // [rsp+28h] [rbp-D8h]
  int wHour; // [rsp+30h] [rbp-D0h]
  int wMinute; // [rsp+38h] [rbp-C8h]
  int wSecond; // [rsp+40h] [rbp-C0h]
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v13[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v14; // [rsp+70h] [rbp-90h]
  __int128 v15; // [rsp+80h] [rbp-80h]
  int v16; // [rsp+90h] [rbp-70h]
  unsigned __int16 v17[264]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v18[528]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v19[1024]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v16 = 0;
  *(_OWORD *)v13 = 0;
  v14 = 0;
  v15 = 0;
  SystemTime = 0;
  memset_0(v17, 0, 0x208u);
  memset_0(v18, 0, 0x208u);
  memset_0(v19, 0, sizeof(v19));
  CountersValues = CSQMUtil::RetrieveCountersValues(v13);
  if ( CountersValues )
    _DbgPrintMessage(4, "CSQMUtil::RetrieveCountersValues() failed: 0x%x in %s", CountersValues, "CSQMUtil::WriteSQM");
  if ( (unsigned int)SqmAddToStreamDWord(CSQMUtil::m_hSQMSession, 6513, 15) )
  {
    for ( i = 0; i < 0xD; ++i )
    {
      if ( !(unsigned int)SqmAddToStreamDWord(CSQMUtil::m_hSQMSession, 6513, 15) )
        goto LABEL_4;
    }
    GetLocalTime(&SystemTime);
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wDay = SystemTime.wDay;
    wMonth = SystemTime.wMonth;
    StringCchPrintfW(v17, 0x104u, L"%d/%d/%d %d:%d:%d", SystemTime.wYear, wMonth, wDay, wHour, wMinute, wSecond);
    if ( (unsigned int)SqmAddToStreamString(CSQMUtil::m_hSQMSession, 6513, 15, v17) )
    {
      GetTempPath2W(260, v18);
      v2 = StringCchPrintfW(v19, 0x400u, L"%s%s.sqm", v18, L"tsSessEnv");
      if ( !(unsigned int)SqmFlushSession(CSQMUtil::m_hSQMSession, v19) )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(4, "SqmFlushSession failed: 0x%x in %s", v2, "CSQMUtil::WriteSQM");
      }
    }
    else
    {
      v4 = GetLastError();
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      _DbgPrintMessage(4, "SqmAddToStreamString failed: 0x%x in %s", v2, "CSQMUtil::WriteSQM");
    }
  }
  else
  {
LABEL_4:
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    _DbgPrintMessage(4, "SqmAddToStreamDWord failed: 0x%x in %s", v2, "CSQMUtil::WriteSQM");
  }
  return v2;
}

```

## disassembly

```asm
0x180015240  push    rbp
0x180015242  push    rbx
0x180015243  push    rsi
0x180015244  push    rdi
0x180015245  lea     rbp, [rsp-0BD8h]
0x18001524d  sub     rsp, 0CD8h
0x180015254  mov     rax, cs:__security_cookie
0x18001525b  xor     rax, rsp
0x18001525e  mov     [rbp+0BF0h+var_30], rax
0x180015265  xorps   xmm0, xmm0
0x180015268  lea     rcx, [rbp+0BF0h+var_C50]; void *
0x18001526c  xor     eax, eax
0x18001526e  mov     ebx, 208h
0x180015273  mov     r8d, ebx; Size
0x180015276  mov     [rbp+0BF0h+var_C60], eax
0x180015279  xor     edx, edx; Val
0x18001527b  movups  xmmword ptr [rsp+0CF0h+var_C90], xmm0
0x180015280  movups  [rsp+0CF0h+var_C80], xmm0
0x180015285  movups  [rbp+0BF0h+var_C70], xmm0
0x180015289  movups  xmmword ptr [rsp+0CF0h+SystemTime.wYear], xmm0
0x18001528e  call    memset_0
0x180015293  mov     r8d, ebx; Size
0x180015296  lea     rcx, [rbp+0BF0h+var_A40]; void *
0x18001529d  xor     edx, edx; Val
0x18001529f  call    memset_0
0x1800152a4  xor     edx, edx; Val
0x1800152a6  lea     rcx, [rbp+0BF0h+var_830]; void *
0x1800152ad  mov     r8d, 800h; Size
0x1800152b3  call    memset_0
0x1800152b8  lea     rcx, [rsp+0CF0h+var_C90]; unsigned int *
0x1800152bd  call    ?RetrieveCountersValues@CSQMUtil@@CAJPEAK@Z; CSQMUtil::RetrieveCountersValues(ulong *)
0x1800152c2  lea     rdi, aCsqmutilWrites_1; "CSQMUtil::WriteSQM"
0x1800152c9  mov     esi, 4
0x1800152ce  test    eax, eax
0x1800152d0  jz      short loc_1800152E6
0x1800152d2  mov     r9, rdi
0x1800152d5  lea     rdx, aCsqmutilRetrie; "CSQMUtil::RetrieveCountersValues() fail"...
0x1800152dc  mov     r8d, eax
0x1800152df  mov     ecx, esi; int
0x1800152e1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800152e6  mov     rcx, cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x1800152ed  xor     r9d, r9d
0x1800152f0  mov     edx, 1971h
0x1800152f5  lea     r8d, [r9+0Fh]
0x1800152f9  call    cs:__imp_SqmAddToStreamDWord
0x1800152ff  test    eax, eax
0x180015301  jnz     short loc_180015324
0x180015303  call    cs:__imp_GetLastError
0x180015309  mov     ebx, eax
0x18001530b  test    eax, eax
0x18001530d  jle     short loc_180015318
0x18001530f  movzx   ebx, ax
0x180015312  or      ebx, 80070000h
0x180015318  lea     rdx, aSqmaddtostream_3; "SqmAddToStreamDWord failed: 0x%x in %s"
0x18001531f  jmp     loc_180015457
0x180015324  xor     ebx, ebx
0x180015326  cmp     ebx, 0Dh
0x180015329  jnb     short loc_180015350
0x18001532b  mov     r9d, [rsp+rbx*4+0CF0h+var_C90]
0x180015330  mov     edx, 1971h
0x180015335  mov     rcx, cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x18001533c  mov     r8d, 0Fh
0x180015342  call    cs:__imp_SqmAddToStreamDWord
0x180015348  test    eax, eax
0x18001534a  jz      short loc_180015303
0x18001534c  inc     ebx
0x18001534e  jmp     short loc_180015326
0x180015350  lea     rcx, [rsp+0CF0h+SystemTime]; lpSystemTime
0x180015355  call    cs:__imp_GetLocalTime
0x18001535b  movzx   ecx, [rsp+0CF0h+SystemTime.wMinute]
0x180015360  lea     r8, aDDDDDD; "%d/%d/%d %d:%d:%d"
0x180015367  movzx   ebx, [rsp+0CF0h+SystemTime.wMonth]
0x18001536c  movzx   eax, [rsp+0CF0h+SystemTime.wSecond]
0x180015371  movzx   r10d, [rsp+0CF0h+SystemTime.wHour]
0x180015377  movzx   r11d, [rsp+0CF0h+SystemTime.wDay]
0x18001537d  movzx   r9d, [rsp+0CF0h+SystemTime.wYear]
0x180015383  mov     [rsp+0CF0h+var_CB0], eax
0x180015387  mov     [rsp+0CF0h+var_CB8], ecx
0x18001538b  lea     rcx, [rbp+0BF0h+var_C50]; unsigned __int16 *
0x18001538f  mov     [rsp+0CF0h+var_CC0], r10d
0x180015394  mov     [rsp+0CF0h+var_CC8], r11d
0x180015399  mov     dword ptr [rsp+0CF0h+var_CD0], ebx
0x18001539d  mov     ebx, 104h
0x1800153a2  mov     edx, ebx; unsigned __int64
0x1800153a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800153a9  mov     rcx, cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x1800153b0  lea     r9, [rbp+0BF0h+var_C50]
0x1800153b4  mov     edx, 1971h
0x1800153b9  mov     r8d, 0Fh
0x1800153bf  call    cs:__imp_SqmAddToStreamString
0x1800153c5  test    eax, eax
0x1800153c7  jnz     short loc_1800153E7
0x1800153c9  call    cs:__imp_GetLastError
0x1800153cf  mov     ebx, eax
0x1800153d1  test    eax, eax
0x1800153d3  jle     short loc_1800153DE
0x1800153d5  movzx   ebx, ax
0x1800153d8  or      ebx, 80070000h
0x1800153de  lea     rdx, aSqmaddtostream_2; "SqmAddToStreamString failed: 0x%x in %s"
0x1800153e5  jmp     short loc_180015457
0x1800153e7  lea     rdx, [rbp+0BF0h+var_A40]
0x1800153ee  mov     ecx, ebx
0x1800153f0  call    cs:__imp_GetTempPath2W
0x1800153f6  lea     rax, aTssessenv; "tsSessEnv"
0x1800153fd  mov     edx, 400h; unsigned __int64
0x180015402  lea     r9, [rbp+0BF0h+var_A40]
0x180015409  mov     [rsp+0CF0h+var_CD0], rax
0x18001540e  lea     r8, aSSSqm; "%s%s.sqm"
0x180015415  lea     rcx, [rbp+0BF0h+var_830]; unsigned __int16 *
0x18001541c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015421  mov     rcx, cs:?m_hSQMSession@CSQMUtil@@0PEAUHSQMSESSION__@@EA; HSQMSESSION__ * CSQMUtil::m_hSQMSession
0x180015428  lea     rdx, [rbp+0BF0h+var_830]
0x18001542f  mov     ebx, eax
0x180015431  call    cs:__imp_SqmFlushSession
0x180015437  test    eax, eax
0x180015439  jnz     short loc_180015464
0x18001543b  call    cs:__imp_GetLastError
0x180015441  mov     ebx, eax
0x180015443  test    eax, eax
0x180015445  jle     short loc_180015450
0x180015447  movzx   ebx, ax
0x18001544a  or      ebx, 80070000h
0x180015450  lea     rdx, aSqmflushsessio_0; "SqmFlushSession failed: 0x%x in %s"
0x180015457  mov     r9, rdi
0x18001545a  mov     r8d, ebx
0x18001545d  mov     ecx, esi; int
0x18001545f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015464  mov     eax, ebx
0x180015466  mov     rcx, [rbp+0BF0h+var_30]
0x18001546d  xor     rcx, rsp; StackCookie
0x180015470  call    __security_check_cookie
0x180015475  add     rsp, 0CD8h
0x18001547c  pop     rdi
0x18001547d  pop     rsi
0x18001547e  pop     rbx
0x18001547f  pop     rbp
0x180015480  retn
```
