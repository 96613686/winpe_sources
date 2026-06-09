# ReadSiteHttpLogInfo(INativeConfigurationElement *,SITE_HTTP_LOG_SETTINGS *)

- ea: `0x180013ed8`
- end: `0x1800143d5`
- name: `?ReadSiteHttpLogInfo@@YAJPEAVINativeConfigurationElement@@PEAUSITE_HTTP_LOG_SETTINGS@@@Z`
- size: `1277`
- prototype: `__int64 __fastcall(struct INativeConfigurationElement *, struct SITE_HTTP_LOG_SETTINGS *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800108c0`
- `0x180012b5c`

## callees

- `0x180013ed8`
- `0x1800160a0`
- `0x180017010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180014345`
- `msvcrt!_ultow_s` at `0x180014345`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013f0a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180013f0a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800143a9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800143a9`
- `iisutil!PuDbgPrintError` at `0x180013f8e`
- `iisutil!PuDbgPrintError` at `0x1800141ff`
- `iisutil!PuDbgPrintError` at `0x180013f8e`
- `iisutil!PuDbgPrintError` at `0x1800141ff`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800142ac`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180014384`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800142ac`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180014384`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014272`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014272`

## string_xrefs

- `0x180013f80`: `ReadSiteHttpLogInfo`
- `0x1800141e3`: `ReadSiteHttpLogInfo`
- `0x180013f87`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\sitelogutil.cxx`
- `0x1800141f8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\sitelogutil.cxx`
- `0x180013fd0`: ` Failed reading property \n`
- `0x180014034`: ` Failed reading property \n`
- `0x180014086`: ` Failed reading property \n`
- `0x1800140e2`: ` Failed reading property \n`
- `0x180014138`: ` Failed reading property \n`
- `0x18001418e`: ` Failed reading property \n`
- `0x180014253`: ` Failed reading property \n`
- `0x18001428b`: ` Failed reading property \n`
- `0x1800142f1`: ` Failed reading property \n`
- `0x18001422d`: `directory`

## pseudocode

```c
__int64 __fastcall ReadSiteHttpLogInfo(struct INativeConfigurationElement *a1, struct SITE_HTTP_LOG_SETTINGS *a2)
{
  __int64 v4; // rax
  __int64 (__fastcall *v5)(struct INativeConfigurationElement *, const wchar_t *, __int64 *); // rax
  int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+38h] [rbp-31h] BYREF
  int v14; // [rsp+40h] [rbp-29h] BYREF
  unsigned int Value; // [rsp+44h] [rbp-25h] BYREF
  const unsigned __int16 *v16; // [rsp+48h] [rbp-21h] BYREF
  __int64 v17; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v18[56]; // [rsp+58h] [rbp-11h] BYREF
  wchar_t Buffer[12]; // [rsp+90h] [rbp+27h] BYREF

  STRU::STRU((STRU *)v18);
  v13 = 0;
  v12 = 0;
  memset(Buffer, 0, 22);
  v4 = *(_QWORD *)a1;
  v16 = 0;
  v17 = 0;
  Value = 0;
  v5 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(v4 + 32);
  v14 = 0;
  v6 = v5(a1, L"logFile", &v13);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_59;
    v7 = " Failed to get logging settings for site \n";
    v8 = 47;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\sitelogutil.cxx",
      v8,
      "ReadSiteHttpLogInfo",
      v6,
      v7);
    goto LABEL_59;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, __int64 *, _QWORD))(*(_QWORD *)v13 + 72LL))(
         v13,
         L"enabled",
         (char *)a2 + 20,
         &v12,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_59;
    v7 = " Failed reading property \n";
    v8 = 60;
    goto LABEL_4;
  }
  v9 = v12;
  if ( v12 )
    goto LABEL_10;
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct SITE_HTTP_LOG_SETTINGS *, __int64 *, _QWORD))(*(_QWORD *)v13 + 48LL))(
         v13,
         L"period",
         a2,
         &v12,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_59;
    v7 = " Failed reading property \n";
    v8 = 80;
    goto LABEL_4;
  }
  v9 = v12;
  if ( v12 )
    goto LABEL_10;
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v13 + 56LL))(
         v13,
         L"truncateSize",
         &v17,
         &v12,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_59;
    v7 = " Failed reading property \n";
    v8 = 100;
    goto LABEL_4;
  }
  v9 = v12;
  if ( v12 )
    goto LABEL_10;
  v10 = v13;
  *((_DWORD *)a2 + 1) = v17;
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, __int64 *, _QWORD))(*(_QWORD *)v10 + 48LL))(
         v10,
         L"logExtFileFlags",
         (char *)a2 + 8,
         &v12,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_59;
    v7 = " Failed reading property \n";
    v8 = 123;
    goto LABEL_4;
  }
  v9 = v12;
  if ( v12 )
    goto LABEL_10;
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, __int64 *, _QWORD))(*(_QWORD *)v13 + 72LL))(
         v13,
         L"localTimeRollover",
         (char *)a2 + 16,
         &v12,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_59;
    v7 = " Failed reading property \n";
    v8 = 142;
    goto LABEL_4;
  }
  v9 = v12;
  if ( v12 )
    goto LABEL_10;
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, __int64 *, _QWORD))(*(_QWORD *)v13 + 48LL))(
         v13,
         L"logFormat",
         &v14,
         &v12,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_59;
    v7 = " Failed reading property \n";
    v8 = 162;
    goto LABEL_4;
  }
  v9 = v12;
  if ( v12 )
  {
LABEL_10:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v6 = -2147019873;
LABEL_61:
    v12 = 0;
    goto LABEL_62;
  }
  if ( v14 == 3 )
    goto LABEL_62;
  if ( v14 )
  {
    if ( v14 == 1 )
    {
      *((_DWORD *)a2 + 3) = 2;
    }
    else if ( v14 == 2 )
    {
      *((_DWORD *)a2 + 3) = 0;
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\sitelogutil.cxx",
        196,
        "ReadSiteHttpLogInfo",
        -2147467259,
        "Unknown log format\n");
    }
  }
  else
  {
    *((_DWORD *)a2 + 3) = 1;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
         v13,
         L"directory",
         &v16,
         0,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_59;
    v7 = " Failed reading property \n";
    v8 = 210;
    goto LABEL_4;
  }
  if ( v16 )
  {
    v6 = STRU::Copy((struct SITE_HTTP_LOG_SETTINGS *)((char *)a2 + 24), v16);
    if ( v6 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_59;
      v7 = " Failed reading property \n";
      v8 = 222;
      goto LABEL_4;
    }
    v16 = 0;
  }
  v6 = STRU::Append((struct SITE_HTTP_LOG_SETTINGS *)((char *)a2 + 24), L"\\W3SVC");
  if ( v6 < 0 )
    goto LABEL_59;
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)a1 + 48LL))(
         a1,
         L"id",
         &Value,
         0,
         0);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_59;
    v7 = " Failed reading property \n";
    v8 = 291;
    goto LABEL_4;
  }
  if ( Value )
  {
    if ( _ultow_s(Value, Buffer, 0xBu, 10) )
    {
      v6 = -2147467259;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\sitelogutil.cxx",
          305,
          "ReadSiteHttpLogInfo",
          -2147467259,
          "Invalid site id \n");
    }
    else
    {
      v6 = STRU::Append((struct SITE_HTTP_LOG_SETTINGS *)((char *)a2 + 24), Buffer);
    }
  }
  else
  {
    v6 = -2147024883;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\sitelogutil.cxx",
        298,
        "ReadSiteHttpLogInfo",
        -2147024883,
        "Invalid site id \n");
  }
LABEL_59:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_61;
  }
LABEL_62:
  STRU::~STRU((STRU *)v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013ed8  mov     [rsp-8+arg_10], rbx
0x180013edd  mov     [rsp-8+arg_18], rsi
0x180013ee2  push    rbp
0x180013ee3  push    rdi
0x180013ee4  push    r14
0x180013ee6  lea     rbp, [rsp-47h]
0x180013eeb  sub     rsp, 0B0h
0x180013ef2  mov     rax, cs:__security_cookie
0x180013ef9  xor     rax, rsp
0x180013efc  mov     [rbp+57h+var_18], rax
0x180013f00  mov     rsi, rcx
0x180013f03  mov     rdi, rdx
0x180013f06  lea     rcx, [rbp+57h+var_68]
0x180013f0a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180013f10  xor     r14d, r14d
0x180013f13  lea     r8, [rbp+57h+var_88]
0x180013f17  xor     eax, eax
0x180013f19  mov     [rbp+57h+var_88], r14
0x180013f1d  xorps   xmm0, xmm0
0x180013f20  mov     [rbp+57h+var_90], r14
0x180013f24  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180013f28  mov     qword ptr [rbp+57h+Buffer+0Eh], rax
0x180013f2c  lea     rdx, aLogfile; "logFile"
0x180013f33  mov     rax, [rsi]
0x180013f36  mov     rcx, rsi
0x180013f39  mov     [rbp+57h+var_78], r14
0x180013f3d  mov     [rbp+57h+var_70], r14
0x180013f41  mov     [rbp+57h+Value], r14d
0x180013f45  mov     rax, [rax+20h]
0x180013f49  mov     [rbp+57h+var_80], r14d
0x180013f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f52  mov     ebx, eax
0x180013f54  test    eax, eax
0x180013f56  jns     short loc_180013F99
0x180013f58  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180013f5f  jz      loc_18001438C
0x180013f65  lea     rax, aFailedToGetLog; " Failed to get logging settings for sit"...
0x180013f6c  lea     r8d, [r14+2Fh]
0x180013f70  mov     [rsp+0C0h+var_98], rax
0x180013f75  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180013f79  mov     rcx, cs:g_pDebug
0x180013f80  lea     r9, aReadsitehttplo; "ReadSiteHttpLogInfo"
0x180013f87  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180013f8e  call    cs:__imp_PuDbgPrintError
0x180013f94  jmp     loc_18001438C
0x180013f99  mov     rcx, [rbp+57h+var_88]
0x180013f9d  lea     r8, [rdi+14h]
0x180013fa1  lea     r9, [rbp+57h+var_90]
0x180013fa5  mov     [rsp+0C0h+var_A0], r14
0x180013faa  lea     rdx, aEnabled; "enabled"
0x180013fb1  mov     rax, [rcx]
0x180013fb4  mov     rax, [rax+48h]
0x180013fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fbd  mov     ebx, eax
0x180013fbf  test    eax, eax
0x180013fc1  jns     short loc_180013FDF
0x180013fc3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180013fca  jz      loc_18001438C
0x180013fd0  lea     rax, aFailedReadingP; " Failed reading property \n"
0x180013fd7  mov     r8d, 3Ch ; '<'
0x180013fdd  jmp     short loc_180013F70
0x180013fdf  mov     rcx, [rbp+57h+var_90]
0x180013fe3  test    rcx, rcx
0x180013fe6  jz      short loc_180013FFE
0x180013fe8  mov     rax, [rcx]
0x180013feb  mov     rax, [rax+10h]
0x180013fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ff4  mov     ebx, 8007139Fh
0x180013ff9  jmp     loc_1800143A1
0x180013ffe  mov     rcx, [rbp+57h+var_88]
0x180014002  lea     r9, [rbp+57h+var_90]
0x180014006  mov     r8, rdi
0x180014009  mov     [rsp+0C0h+var_A0], r14
0x18001400e  lea     rdx, aPeriod; "period"
0x180014015  mov     rax, [rcx]
0x180014018  mov     rax, [rax+30h]
0x18001401c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014021  mov     ebx, eax
0x180014023  test    eax, eax
0x180014025  jns     short loc_180014046
0x180014027  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001402e  jz      loc_18001438C
0x180014034  lea     rax, aFailedReadingP; " Failed reading property \n"
0x18001403b  mov     r8d, 50h ; 'P'
0x180014041  jmp     loc_180013F70
0x180014046  mov     rcx, [rbp+57h+var_90]
0x18001404a  test    rcx, rcx
0x18001404d  jnz     short loc_180013FE8
0x18001404f  mov     rcx, [rbp+57h+var_88]
0x180014053  lea     r9, [rbp+57h+var_90]
0x180014057  lea     r8, [rbp+57h+var_70]
0x18001405b  mov     [rsp+0C0h+var_A0], r14
0x180014060  lea     rdx, aTruncatesize; "truncateSize"
0x180014067  mov     rax, [rcx]
0x18001406a  mov     rax, [rax+38h]
0x18001406e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014073  mov     ebx, eax
0x180014075  test    eax, eax
0x180014077  jns     short loc_180014098
0x180014079  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180014080  jz      loc_18001438C
0x180014086  lea     rax, aFailedReadingP; " Failed reading property \n"
0x18001408d  mov     r8d, 64h ; 'd'
0x180014093  jmp     loc_180013F70
0x180014098  mov     rcx, [rbp+57h+var_90]
0x18001409c  test    rcx, rcx
0x18001409f  jnz     loc_180013FE8
0x1800140a5  mov     eax, dword ptr [rbp+57h+var_70]
0x1800140a8  lea     r8, [rdi+8]
0x1800140ac  mov     rcx, [rbp+57h+var_88]
0x1800140b0  lea     r9, [rbp+57h+var_90]
0x1800140b4  mov     [rdi+4], eax
0x1800140b7  lea     rdx, aLogextfileflag; "logExtFileFlags"
0x1800140be  mov     [rsp+0C0h+var_A0], r14
0x1800140c3  mov     rax, [rcx]
0x1800140c6  mov     rax, [rax+30h]
0x1800140ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140cf  mov     ebx, eax
0x1800140d1  test    eax, eax
0x1800140d3  jns     short loc_1800140F4
0x1800140d5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800140dc  jz      loc_18001438C
0x1800140e2  lea     rax, aFailedReadingP; " Failed reading property \n"
0x1800140e9  mov     r8d, 7Bh ; '{'
0x1800140ef  jmp     loc_180013F70
0x1800140f4  mov     rcx, [rbp+57h+var_90]
0x1800140f8  test    rcx, rcx
0x1800140fb  jnz     loc_180013FE8
0x180014101  mov     rcx, [rbp+57h+var_88]
0x180014105  lea     r8, [rdi+10h]
0x180014109  lea     r9, [rbp+57h+var_90]
0x18001410d  mov     [rsp+0C0h+var_A0], r14
0x180014112  lea     rdx, aLocaltimerollo; "localTimeRollover"
0x180014119  mov     rax, [rcx]
0x18001411c  mov     rax, [rax+48h]
0x180014120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014125  mov     ebx, eax
0x180014127  test    eax, eax
0x180014129  jns     short loc_18001414A
0x18001412b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180014132  jz      loc_18001438C
0x180014138  lea     rax, aFailedReadingP; " Failed reading property \n"
0x18001413f  mov     r8d, 8Eh
0x180014145  jmp     loc_180013F70
0x18001414a  mov     rcx, [rbp+57h+var_90]
0x18001414e  test    rcx, rcx
0x180014151  jnz     loc_180013FE8
0x180014157  mov     rcx, [rbp+57h+var_88]
0x18001415b  lea     r9, [rbp+57h+var_90]
0x18001415f  lea     r8, [rbp+57h+var_80]
0x180014163  mov     [rsp+0C0h+var_A0], r14
0x180014168  lea     rdx, aLogformat; "logFormat"
0x18001416f  mov     rax, [rcx]
0x180014172  mov     rax, [rax+30h]
0x180014176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001417b  mov     ebx, eax
0x18001417d  test    eax, eax
0x18001417f  jns     short loc_1800141A0
0x180014181  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180014188  jz      loc_18001438C
0x18001418e  lea     rax, aFailedReadingP; " Failed reading property \n"
0x180014195  mov     r8d, 0A2h
0x18001419b  jmp     loc_180013F70
0x1800141a0  mov     rcx, [rbp+57h+var_90]
0x1800141a4  test    rcx, rcx
0x1800141a7  jnz     loc_180013FE8
0x1800141ad  mov     eax, [rbp+57h+var_80]
0x1800141b0  cmp     eax, 3
0x1800141b3  jz      loc_1800143A5
0x1800141b9  test    eax, eax
0x1800141bb  jz      short loc_180014216
0x1800141bd  sub     eax, 1
0x1800141c0  jz      short loc_18001420D
0x1800141c2  cmp     eax, 1
0x1800141c5  jz      short loc_180014207
0x1800141c7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800141ce  jz      short loc_18001421D
0x1800141d0  mov     rcx, cs:g_pDebug
0x1800141d7  lea     rax, aUnknownLogForm; "Unknown log format\n"
0x1800141de  mov     [rsp+0C0h+var_98], rax
0x1800141e3  lea     r9, aReadsitehttplo; "ReadSiteHttpLogInfo"
0x1800141ea  mov     r8d, 0C4h
0x1800141f0  mov     dword ptr [rsp+0C0h+var_A0], 80004005h
0x1800141f8  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800141ff  call    cs:__imp_PuDbgPrintError
0x180014205  jmp     short loc_18001421D
0x180014207  mov     [rdi+0Ch], r14d
0x18001420b  jmp     short loc_18001421D
0x18001420d  mov     dword ptr [rdi+0Ch], 2
0x180014214  jmp     short loc_18001421D
0x180014216  mov     dword ptr [rdi+0Ch], 1
0x18001421d  mov     rcx, [rbp+57h+var_88]
0x180014221  lea     r8, [rbp+57h+var_78]
0x180014225  xor     r9d, r9d
0x180014228  mov     [rsp+0C0h+var_A0], r14
0x18001422d  lea     rdx, aDirectory; "directory"
0x180014234  mov     rax, [rcx]
0x180014237  mov     rax, [rax+40h]
0x18001423b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014240  mov     ebx, eax
0x180014242  test    eax, eax
0x180014244  jns     short loc_180014265
0x180014246  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001424d  jz      loc_18001438C
0x180014253  lea     rax, aFailedReadingP; " Failed reading property \n"
0x18001425a  mov     r8d, 0D2h
0x180014260  jmp     loc_180013F70
0x180014265  mov     rdx, [rbp+57h+var_78]
0x180014269  test    rdx, rdx
0x18001426c  jz      short loc_1800142A1
0x18001426e  lea     rcx, [rdi+18h]
0x180014272  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180014278  mov     ebx, eax
0x18001427a  test    eax, eax
0x18001427c  jns     short loc_18001429D
0x18001427e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180014285  jz      loc_18001438C
0x18001428b  lea     rax, aFailedReadingP; " Failed reading property \n"
0x180014292  mov     r8d, 0DEh
0x180014298  jmp     loc_180013F70
0x18001429d  mov     [rbp+57h+var_78], r14
0x1800142a1  lea     rdx, aW3svc; "\\W3SVC"
0x1800142a8  lea     rcx, [rdi+18h]
0x1800142ac  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800142b2  mov     ebx, eax
0x1800142b4  test    eax, eax
0x1800142b6  js      loc_18001438C
0x1800142bc  mov     rax, [rsi]
0x1800142bf  lea     r8, [rbp+57h+Value]
0x1800142c3  xor     r9d, r9d
0x1800142c6  mov     [rsp+0C0h+var_A0], r14
0x1800142cb  lea     rdx, aId; "id"
0x1800142d2  mov     rcx, rsi
0x1800142d5  mov     rax, [rax+30h]
0x1800142d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142de  mov     ebx, eax
0x1800142e0  test    eax, eax
0x1800142e2  jns     short loc_180014303
0x1800142e4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800142eb  jz      loc_18001438C
0x1800142f1  lea     rax, aFailedReadingP; " Failed reading property \n"
0x1800142f8  mov     r8d, 123h
0x1800142fe  jmp     loc_180013F70
0x180014303  mov     ecx, [rbp+57h+Value]; Value
0x180014306  test    ecx, ecx
0x180014308  jnz     short loc_180014337
0x18001430a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180014311  mov     ebx, 8007000Dh
0x180014316  jz      short loc_18001438C
0x180014318  lea     rax, aInvalidSiteId; "Invalid site id \n"
0x18001431f  mov     r8d, 12Ah
0x180014325  mov     [rsp+0C0h+var_98], rax
0x18001432a  mov     dword ptr [rsp+0C0h+var_A0], 8007000Dh
0x180014332  jmp     loc_180013F79
0x180014337  mov     r9d, 0Ah; Radix
0x18001433d  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180014341  lea     r8d, [r9+1]; BufferCount
0x180014345  call    cs:__imp__ultow_s
0x18001434b  test    eax, eax
0x18001434d  jz      short loc_18001437C
0x18001434f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180014356  mov     ebx, 80004005h
0x18001435b  jz      short loc_18001438C
0x18001435d  lea     rax, aInvalidSiteId; "Invalid site id \n"
0x180014364  mov     r8d, 131h
0x18001436a  mov     [rsp+0C0h+var_98], rax
0x18001436f  mov     dword ptr [rsp+0C0h+var_A0], 80004005h
0x180014377  jmp     loc_180013F79
0x18001437c  lea     rdx, [rbp+57h+Buffer]
0x180014380  lea     rcx, [rdi+18h]
0x180014384  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001438a  mov     ebx, eax
0x18001438c  mov     rcx, [rbp+57h+var_90]
0x180014390  test    rcx, rcx
0x180014393  jz      short loc_1800143A5
0x180014395  mov     rax, [rcx]
0x180014398  mov     rax, [rax+10h]
0x18001439c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143a1  mov     [rbp+57h+var_90], r14
0x1800143a5  lea     rcx, [rbp+57h+var_68]
0x1800143a9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800143af  mov     eax, ebx
0x1800143b1  mov     rcx, [rbp+57h+var_18]
0x1800143b5  xor     rcx, rsp; StackCookie
0x1800143b8  call    __security_check_cookie
0x1800143bd  lea     r11, [rsp+0C0h+var_10]
0x1800143c5  mov     rbx, [r11+30h]
0x1800143c9  mov     rsi, [r11+38h]
0x1800143cd  mov     rsp, r11
0x1800143d0  pop     r14
0x1800143d2  pop     rdi
0x1800143d3  pop     rbp
0x1800143d4  retn
```
