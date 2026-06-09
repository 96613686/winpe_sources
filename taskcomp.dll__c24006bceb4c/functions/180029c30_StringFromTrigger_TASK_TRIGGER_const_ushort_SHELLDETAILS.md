# StringFromTrigger(_TASK_TRIGGER * const,ushort * *,_SHELLDETAILS *)

- ea: `0x180029c30`
- end: `0x18002a5b9`
- name: `?StringFromTrigger@@YAJQEAU_TASK_TRIGGER@@PEAPEAGPEAU_SHELLDETAILS@@@Z`
- size: `2441`
- prototype: `__int64 __fastcall(struct _TASK_TRIGGER *const, unsigned __int16 **, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026140`

## callees

- `0x180003ef0`
- `0x180005f7c`
- `0x180029610`
- `0x1800298c0`
- `0x180029c30`
- `0x18002e572`
- `0x18002e5b0`
- `0x18002e670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a114`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180029da4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180029e42`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180029ee3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180029f51`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a033`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a0a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a106`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a13b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a1b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a23a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a352`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a3ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a53d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180029da4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180029e42`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180029ee3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180029f51`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a033`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a0a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a106`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a13b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a1b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a23a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a352`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a3ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a53d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180029e7a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a0d9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a3eb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a498`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180029e7a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a0d9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a3eb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a498`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18002a191`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18002a2bf`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18002a191`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18002a2bf`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002a438`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002a4ec`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002a438`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002a4ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029f7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029f7c`

## pseudocode

```c
signed int __fastcall StringFromTrigger(
        struct _TASK_TRIGGER *const a1,
        unsigned __int16 **a2,
        struct _SHELLDETAILS *a3)
{
  bool v5; // zf
  UINT v6; // r15d
  UINT v7; // edi
  TASK_TRIGGER_TYPE TriggerType; // ecx
  __int32 v9; // ecx
  __int32 v10; // ecx
  __int32 v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  signed int result; // eax
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  WORD rgfMonths; // cx
  UINT v19; // edx
  DWORD StringW; // eax
  unsigned __int16 v21; // r14
  __int16 v22; // bx
  unsigned __int16 i; // dx
  UINT v24; // edx
  __int64 DaysInterval; // r9
  DWORD v26; // eax
  __int64 v27; // rax
  unsigned __int64 v28; // rbx
  unsigned __int16 *v29; // rax
  unsigned int v30; // r8d
  UINT v31; // edx
  WORD wStartHour; // ax
  DWORD MinutesInterval; // edi
  __int64 v34; // r9
  unsigned int v35; // ebx
  unsigned __int16 j; // cx
  UINT v37; // edx
  DWORD MinutesDuration; // edi
  __int64 v39; // r9
  unsigned int v40; // ebx
  UINT v41; // edx
  SYSTEMTIME Time; // [rsp+40h] [rbp-C0h] BYREF
  va_list Arguments[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v44; // [rsp+60h] [rbp-A0h]
  WCHAR *v45; // [rsp+70h] [rbp-90h]
  unsigned __int16 v46[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v47; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 v48[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v49; // [rsp+90h] [rbp-70h]
  WCHAR Source[80]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v51[16]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v52[16]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR Buffer[32]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR TimeStr[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR v55[32]; // [rsp+200h] [rbp+100h] BYREF
  WCHAR v56[32]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR DateStr[64]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR lpBuffer[256]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR v59[64]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v60[256]; // [rsp+580h] [rbp+480h] BYREF
  WCHAR v61[256]; // [rsp+780h] [rbp+680h] BYREF
  WCHAR v62[512]; // [rsp+980h] [rbp+880h] BYREF
  unsigned __int16 v63[512]; // [rsp+D80h] [rbp+C80h] BYREF

  *a2 = 0;
  *(_DWORD *)v46 = *(_DWORD *)L"%d";
  v47 = aD[2];
  *(_OWORD *)v48 = 0;
  v49 = 0;
  memset_0(v60, 0, sizeof(v60));
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v63, 0, sizeof(v63));
  memset_0(Source, 0, sizeof(Source));
  memset_0(lpBuffer, 0, sizeof(lpBuffer));
  v5 = (a1->rgFlags & 0x10000) == 0;
  v45 = 0;
  *(_OWORD *)Arguments = 0;
  v6 = 1078;
  v44 = 0;
  if ( !v5 )
  {
    v7 = 1123;
    goto LABEL_35;
  }
  TriggerType = a1->TriggerType;
  v7 = 0;
  if ( TriggerType )
  {
    v9 = TriggerType - 1;
    if ( !v9 )
    {
      if ( a1->Type.Daily.DaysInterval == 1 )
      {
        StringW = LoadStringW(g_hInstance, 0x458u, lpBuffer, 256);
LABEL_56:
        if ( !StringW )
          goto LABEL_57;
        goto LABEL_35;
      }
      if ( !LoadStringW(g_hInstance, 0x457u, Source, 80) )
        goto LABEL_57;
      DaysInterval = a1->Type.Daily.DaysInterval;
LABEL_34:
      StringCchPrintfW(lpBuffer, 0x100u, Source, DaysInterval);
      goto LABEL_35;
    }
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 != 1 )
                return -2147024883;
              v7 = 1130;
            }
            else
            {
              v7 = 1091;
            }
          }
          else
          {
            v7 = 1090;
          }
          goto LABEL_35;
        }
        if ( !LoadStringW(g_hInstance, a1->Type.Daily.DaysInterval + 1078, Buffer, 32) )
          goto LABEL_57;
        result = GetDaysOfWeekString(a1->Type.Weekly.rgfDaysOfTheWeek, v60, v16);
        if ( result < 0 )
          return result;
        rgfMonths = a1->Type.MonthlyDate.rgfMonths;
        if ( rgfMonths == 4095 )
        {
          v19 = 1118;
          Arguments[0] = (va_list)Buffer;
          Arguments[1] = (va_list)v60;
        }
        else
        {
          result = GetMonthsString(rgfMonths, v63, v17);
          if ( result < 0 )
            return result;
          v19 = 1119;
          Arguments[0] = (va_list)Buffer;
          Arguments[1] = (va_list)v60;
          *(_QWORD *)&v44 = v63;
        }
        if ( !LoadStringW(g_hInstance, v19, Source, 80) )
          goto LABEL_57;
        StringW = FormatMessageW(0x2400u, Source, 0, 0, lpBuffer, 0x100u, Arguments);
        goto LABEL_56;
      }
      v21 = 0;
      v22 = 0;
      for ( i = 0; i < 0x1Fu; ++i )
      {
        if ( ((a1->Type.MonthlyDate.rgfDays >> i) & 1) != 0 && ++v22 == 1 )
          v21 = i + 1;
      }
      if ( a1->Type.MonthlyDate.rgfMonths == 4095 )
      {
        v24 = 1116;
        if ( v22 != 1 )
          v24 = 1124;
        if ( !LoadStringW(g_hInstance, v24, Source, 80) )
          goto LABEL_57;
        DaysInterval = v21;
        goto LABEL_34;
      }
      StringCchPrintfW(v48, 0x10u, v46, v21);
      result = GetMonthsString(a1->Type.MonthlyDate.rgfMonths, v63, v30);
      if ( result < 0 )
        return result;
      v31 = 1117;
      Arguments[0] = (va_list)v48;
      Arguments[1] = (va_list)v63;
      if ( v22 != 1 )
        v31 = 1125;
    }
    else
    {
      result = GetDaysOfWeekString(a1->Type.Weekly.rgfDaysOfTheWeek, v60, 1u);
      if ( result < 0 )
        return result;
      if ( a1->Type.Daily.DaysInterval == 1 )
      {
        if ( !LoadStringW(g_hInstance, 0x45Au, Source, 80) )
          goto LABEL_57;
        StringCchPrintfW(lpBuffer, 0x100u, Source, v60);
        goto LABEL_35;
      }
      StringCchPrintfW(v48, 0x10u, v46, a1->Type.Daily.DaysInterval);
      v31 = 1115;
      Arguments[0] = (va_list)v60;
      Arguments[1] = (va_list)v48;
    }
    if ( !LoadStringW(g_hInstance, v31, Source, 80)
      || !FormatMessageW(0x2400u, Source, 0, 0, lpBuffer, 0x100u, Arguments) )
    {
      goto LABEL_57;
    }
  }
LABEL_35:
  if ( v7 )
  {
    v26 = LoadStringW(g_hInstance, v7, v62, 512);
    goto LABEL_37;
  }
  wStartHour = a1->wStartHour;
  Time = 0;
  Time.wHour = wStartHour;
  Time.wMinute = a1->wStartMinute;
  if ( !GetTimeFormatW(0x400u, 2u, &Time, 0, TimeStr, 32) )
    goto LABEL_57;
  MinutesInterval = a1->MinutesInterval;
  if ( MinutesInterval )
  {
    v34 = MinutesInterval;
    v35 = 60 * (MinutesInterval / 0x3C);
    if ( MinutesInterval == v35 )
      v34 = MinutesInterval / 0x3C;
    StringCchPrintfW(v51, 0x10u, v46, v34);
    if ( !LoadStringW(g_hInstance, (MinutesInterval != v35) + 1097, v56, 32) )
      goto LABEL_57;
    if ( (a1->rgFlags & 0x20000) != 0 )
    {
      for ( j = a1->wStartMinute + LOWORD(a1->MinutesDuration) + 60 * a1->wStartHour; j > 0x5A0u; j -= 1440 )
        ;
      Time.wHour = j / 0x3Cu;
      Time.wMinute = j % 0x3Cu;
      if ( !GetTimeFormatW(0x400u, 2u, &Time, 0, v55, 32) )
        goto LABEL_57;
      v37 = 1094;
      Arguments[0] = (va_list)v51;
      Arguments[1] = (va_list)v56;
      *(_QWORD *)&v44 = TimeStr;
      *((_QWORD *)&v44 + 1) = v55;
    }
    else
    {
      MinutesDuration = a1->MinutesDuration;
      v39 = MinutesDuration;
      v40 = 60 * (MinutesDuration / 0x3C);
      if ( MinutesDuration == v40 )
        v39 = MinutesDuration / 0x3C;
      StringCchPrintfW(v52, 0x10u, v46, v39);
      if ( MinutesDuration == v40 )
        v6 = 1097;
      if ( !LoadStringW(g_hInstance, v6, v55, 32) )
        goto LABEL_57;
      v37 = 1122;
      Arguments[0] = (va_list)v51;
      Arguments[1] = (va_list)v56;
      *(_QWORD *)&v44 = TimeStr;
      *((_QWORD *)&v44 + 1) = v52;
      v45 = v55;
    }
    if ( !LoadStringW(g_hInstance, v37, Source, 80) || !FormatMessageW(0x2400u, Source, 0, 0, v61, 0x100u, Arguments) )
      goto LABEL_57;
  }
  else
  {
    if ( !LoadStringW(g_hInstance, 0x445u, Source, 80) )
      goto LABEL_57;
    StringCchPrintfW(v61, 0x100u, Source, TimeStr);
  }
  Time.wYear = a1->wBeginYear;
  Time.wMonth = a1->wBeginMonth;
  Time.wDay = a1->wBeginDay;
  if ( !GetDateFormatW(0x400u, 1u, &Time, 0, DateStr, 64) )
    goto LABEL_57;
  if ( a1->TriggerType )
  {
    if ( (a1->rgFlags & 1) != 0 )
    {
      Time.wYear = a1->wEndYear;
      Time.wMonth = a1->wEndMonth;
      Time.wDay = a1->wEndDay;
      if ( !GetDateFormatW(0x400u, 1u, &Time, 0, v59, 64) )
        goto LABEL_57;
      v41 = 1095;
      Arguments[0] = (va_list)v61;
      Arguments[1] = (va_list)lpBuffer;
      *(_QWORD *)&v44 = DateStr;
      *((_QWORD *)&v44 + 1) = v59;
    }
    else
    {
      v41 = 1096;
      Arguments[0] = (va_list)v61;
      Arguments[1] = (va_list)lpBuffer;
      *(_QWORD *)&v44 = DateStr;
    }
  }
  else
  {
    v41 = 1110;
    Arguments[0] = (va_list)v61;
    Arguments[1] = (va_list)DateStr;
  }
  if ( LoadStringW(g_hInstance, v41, Source, 80) )
  {
    v26 = FormatMessageW(0x2400u, Source, 0, 0, v62, 0x200u, Arguments);
LABEL_37:
    if ( v26 )
    {
      v27 = -1;
      do
        ++v27;
      while ( v62[v27] );
      v28 = (unsigned int)(v27 + 1);
      v29 = (unsigned __int16 *)CoTaskMemAlloc(2 * v28);
      *a2 = v29;
      if ( !v29 )
        return -2147024882;
      StringCchCopyW(v29, v28, v62);
      return 0;
    }
  }
LABEL_57:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180029c30  mov     [rsp-8+arg_10], rbx
0x180029c35  push    rbp
0x180029c36  push    rsi
0x180029c37  push    rdi
0x180029c38  push    r12
0x180029c3a  push    r13
0x180029c3c  push    r14
0x180029c3e  push    r15
0x180029c40  lea     rbp, [rsp-1090h]
0x180029c48  mov     eax, 1190h
0x180029c4d  call    _alloca_probe
0x180029c52  sub     rsp, rax
0x180029c55  mov     rax, cs:__security_cookie
0x180029c5c  xor     rax, rsp
0x180029c5f  mov     [rbp+10C0h+var_40], rax
0x180029c66  xorps   xmm0, xmm0
0x180029c69  mov     r12, rdx
0x180029c6c  mov     rsi, rcx
0x180029c6f  xor     r13d, r13d
0x180029c72  mov     [rdx], r13
0x180029c75  lea     rcx, [rbp+10C0h+var_C40]; void *
0x180029c7c  mov     eax, dword ptr cs:aD; "%d"
0x180029c82  mov     ebx, 200h
0x180029c87  mov     dword ptr [rsp+11C0h+var_1148], eax
0x180029c8b  mov     r8d, ebx; Size
0x180029c8e  movzx   eax, word ptr cs:aD+4; ""
0x180029c95  xor     edx, edx; Val
0x180029c97  mov     [rsp+11C0h+var_1144], ax
0x180029c9c  movups  xmmword ptr [rbp+10C0h+var_1140], xmm0
0x180029ca0  movups  [rbp+10C0h+var_1130], xmm0
0x180029ca4  call    memset_0
0x180029ca9  xor     edx, edx; Val
0x180029cab  lea     r8d, [r13+40h]; Size
0x180029caf  lea     rcx, [rbp+10C0h+Buffer]; void *
0x180029cb6  call    memset_0
0x180029cbb  xor     edx, edx; Val
0x180029cbd  lea     rcx, [rbp+10C0h+var_440]; void *
0x180029cc4  mov     r8d, 400h; Size
0x180029cca  call    memset_0
0x180029ccf  xor     edx, edx; Val
0x180029cd1  lea     rcx, [rbp+10C0h+Source]; void *
0x180029cd5  mov     r8d, 0A0h; Size
0x180029cdb  call    memset_0
0x180029ce0  mov     r8d, ebx; Size
0x180029ce3  lea     rcx, [rbp+10C0h+var_EC0]; void *
0x180029cea  xor     edx, edx; Val
0x180029cec  call    memset_0
0x180029cf1  xor     eax, eax
0x180029cf3  lea     r8d, [r13+1]; unsigned int
0x180029cf7  test    dword ptr [rsi+1Ch], 10000h
0x180029cfe  lea     r9d, [r13+1Fh]
0x180029d02  xorps   xmm0, xmm0
0x180029d05  mov     [rsp+11C0h+var_1150], rax
0x180029d0a  movups  xmmword ptr [rsp+11C0h+var_1170], xmm0
0x180029d0f  lea     ebx, [rax+50h]
0x180029d12  mov     r15d, 436h
0x180029d18  movups  [rsp+11C0h+var_1160], xmm0
0x180029d1d  mov     r14d, 100h
0x180029d23  jz      short loc_180029D31
0x180029d25  lea     edi, [r15+2Dh]
0x180029d29  mov     r14d, r8d
0x180029d2c  jmp     loc_180029F16
0x180029d31  mov     ecx, [rsi+20h]
0x180029d34  mov     edi, r13d
0x180029d37  test    ecx, ecx
0x180029d39  jz      short loc_180029D29
0x180029d3b  sub     ecx, r8d
0x180029d3e  jz      loc_18002A0E9
0x180029d44  sub     ecx, r8d
0x180029d47  jz      loc_180029FFB
0x180029d4d  sub     ecx, r8d
0x180029d50  jz      loc_180029E85
0x180029d56  sub     ecx, r8d
0x180029d59  jz      short loc_180029D89
0x180029d5b  sub     ecx, r8d
0x180029d5e  jz      short loc_180029D82
0x180029d60  sub     ecx, r8d
0x180029d63  jz      short loc_180029D7B
0x180029d65  cmp     ecx, r8d
0x180029d68  jz      short loc_180029D74
0x180029d6a  mov     eax, 8007000Dh
0x180029d6f  jmp     loc_18002A58F
0x180029d74  mov     edi, 46Ah
0x180029d79  jmp     short loc_180029D29
0x180029d7b  mov     edi, 443h
0x180029d80  jmp     short loc_180029D29
0x180029d82  mov     edi, 442h
0x180029d87  jmp     short loc_180029D29
0x180029d89  movzx   edx, word ptr [rsi+24h]
0x180029d8d  lea     r8, [rbp+10C0h+Buffer]; lpBuffer
0x180029d94  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180029d9b  add     edx, r15d; uID
0x180029d9e  mov     r9d, 20h ; ' '; cchBufferMax
0x180029da4  call    cs:__imp_LoadStringW
0x180029daa  test    eax, eax
0x180029dac  jz      loc_18002A114
0x180029db2  movzx   ecx, word ptr [rsi+26h]; unsigned __int16
0x180029db6  lea     rdx, [rbp+10C0h+var_C40]; unsigned __int16 *
0x180029dbd  call    ?GetDaysOfWeekString@@YAJGPEAGI@Z; GetDaysOfWeekString(ushort,ushort *,uint)
0x180029dc2  test    eax, eax
0x180029dc4  js      loc_18002A58F
0x180029dca  movzx   ecx, word ptr [rsi+28h]; unsigned __int16
0x180029dce  mov     eax, 0FFFh
0x180029dd3  cmp     cx, ax
0x180029dd6  jnz     short loc_180029DF7
0x180029dd8  lea     rax, [rbp+10C0h+Buffer]
0x180029ddf  mov     edx, 45Eh
0x180029de4  mov     [rsp+11C0h+var_1170], rax
0x180029de9  lea     rax, [rbp+10C0h+var_C40]
0x180029df0  mov     [rsp+11C0h+var_1170+8], rax
0x180029df5  jmp     short loc_180029E34
0x180029df7  lea     rdx, [rbp+10C0h+var_440]; unsigned __int16 *
0x180029dfe  call    ?GetMonthsString@@YAJGPEAGI@Z; GetMonthsString(ushort,ushort *,uint)
0x180029e03  test    eax, eax
0x180029e05  js      loc_18002A58F
0x180029e0b  lea     rax, [rbp+10C0h+Buffer]
0x180029e12  mov     edx, 45Fh; uID
0x180029e17  mov     [rsp+11C0h+var_1170], rax
0x180029e1c  lea     rax, [rbp+10C0h+var_C40]
0x180029e23  mov     [rsp+11C0h+var_1170+8], rax
0x180029e28  lea     rax, [rbp+10C0h+var_440]
0x180029e2f  mov     qword ptr [rsp+11C0h+var_1160], rax
0x180029e34  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180029e3b  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x180029e3f  mov     r9d, ebx; cchBufferMax
0x180029e42  call    cs:__imp_LoadStringW
0x180029e48  test    eax, eax
0x180029e4a  jz      loc_18002A114
0x180029e50  lea     rax, [rsp+11C0h+var_1170]
0x180029e55  xor     r9d, r9d; dwLanguageId
0x180029e58  mov     [rsp+11C0h+Arguments], rax; Arguments
0x180029e5d  lea     rdx, [rbp+10C0h+Source]; lpSource
0x180029e61  lea     rax, [rbp+10C0h+var_EC0]
0x180029e68  mov     [rsp+11C0h+nSize], r14d; nSize
0x180029e6d  xor     r8d, r8d; dwMessageId
0x180029e70  mov     [rsp+11C0h+lpBuffer], rax; lpBuffer
0x180029e75  mov     ecx, 2400h; dwFlags
0x180029e7a  call    cs:__imp_FormatMessageW
0x180029e80  jmp     loc_18002A10C
0x180029e85  mov     r14d, r13d
0x180029e88  mov     ebx, r13d
0x180029e8b  mov     edx, r13d
0x180029e8e  mov     eax, [rsi+24h]
0x180029e91  mov     cl, dl
0x180029e93  shr     eax, cl
0x180029e95  test    r8b, al
0x180029e98  jz      short loc_180029EA8
0x180029e9a  add     bx, r8w
0x180029e9e  cmp     bx, r8w
0x180029ea2  jnz     short loc_180029EA8
0x180029ea4  lea     r14d, [r8+rdx]
0x180029ea8  add     dx, r8w
0x180029eac  cmp     dx, r9w
0x180029eb0  jb      short loc_180029E8E
0x180029eb2  mov     eax, 0FFFh
0x180029eb7  cmp     [rsi+28h], ax
0x180029ebb  jnz     loc_180029F99
0x180029ec1  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180029ec8  cmp     bx, r8w
0x180029ecc  mov     edx, 45Ch
0x180029ed1  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x180029ed5  mov     ebx, 50h ; 'P'
0x180029eda  mov     r9d, ebx; cchBufferMax
0x180029edd  lea     eax, [rdx+8]
0x180029ee0  cmovnz  edx, eax; uID
0x180029ee3  call    cs:__imp_LoadStringW
0x180029ee9  test    eax, eax
0x180029eeb  jz      loc_18002A114
0x180029ef1  movzx   r9d, r14w
0x180029ef5  mov     edx, 100h; unsigned __int64
0x180029efa  lea     r8, [rbp+10C0h+Source]; unsigned __int16 *
0x180029efe  lea     rcx, [rbp+10C0h+var_EC0]; unsigned __int16 *
0x180029f05  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029f0a  mov     r14d, 1
0x180029f10  mov     r9d, 1Fh
0x180029f16  mov     eax, edi
0x180029f18  test    edi, edi
0x180029f1a  jz      loc_18002A152
0x180029f20  sub     eax, 442h
0x180029f25  jz      short loc_180029F3B
0x180029f27  sub     eax, 1
0x180029f2a  jz      short loc_180029F3B
0x180029f2c  sub     eax, 1
0x180029f2f  jz      short loc_180029F3B
0x180029f31  sub     eax, r9d
0x180029f34  jz      short loc_180029F3B
0x180029f36  cmp     eax, 7
0x180029f39  jnz     short loc_180029F5F
0x180029f3b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180029f42  lea     r8, [rbp+10C0h+var_840]; lpBuffer
0x180029f49  mov     r9d, 200h; cchBufferMax
0x180029f4f  mov     edx, edi; uID
0x180029f51  call    cs:__imp_LoadStringW
0x180029f57  test    eax, eax
0x180029f59  jz      loc_18002A114
0x180029f5f  lea     rcx, [rbp+10C0h+var_840]
0x180029f66  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029f6a  inc     rax
0x180029f6d  cmp     [rcx+rax*2], r13w
0x180029f72  jnz     short loc_180029F6A
0x180029f74  inc     eax
0x180029f76  mov     ebx, eax
0x180029f78  lea     rcx, [rax+rax]; cb
0x180029f7c  call    cs:__imp_CoTaskMemAlloc
0x180029f82  mov     [r12], rax
0x180029f86  test    rax, rax
0x180029f89  jnz     loc_18002A57B
0x180029f8f  mov     eax, 8007000Eh
0x180029f94  jmp     loc_18002A58F
0x180029f99  movzx   r9d, r14w
0x180029f9d  lea     r8, [rsp+11C0h+var_1148]; unsigned __int16 *
0x180029fa2  mov     edx, 10h; unsigned __int64
0x180029fa7  lea     rcx, [rbp+10C0h+var_1140]; unsigned __int16 *
0x180029fab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029fb0  movzx   ecx, word ptr [rsi+28h]; unsigned __int16
0x180029fb4  lea     rdx, [rbp+10C0h+var_440]; unsigned __int16 *
0x180029fbb  call    ?GetMonthsString@@YAJGPEAGI@Z; GetMonthsString(ushort,ushort *,uint)
0x180029fc0  test    eax, eax
0x180029fc2  js      loc_18002A58F
0x180029fc8  lea     rax, [rbp+10C0h+var_1140]
0x180029fcc  mov     edx, 45Dh
0x180029fd1  mov     [rsp+11C0h+var_1170], rax
0x180029fd6  mov     r14d, 1
0x180029fdc  lea     rax, [rbp+10C0h+var_440]
0x180029fe3  cmp     bx, r14w
0x180029fe7  mov     [rsp+11C0h+var_1170+8], rax
0x180029fec  lea     eax, [rdx+8]
0x180029fef  cmovnz  edx, eax
0x180029ff2  lea     ebx, [r14+4Fh]
0x180029ff6  jmp     loc_18002A094
0x180029ffb  movzx   ecx, word ptr [rsi+26h]; unsigned __int16
0x180029fff  lea     rdx, [rbp+10C0h+var_C40]; unsigned __int16 *
0x18002a006  call    ?GetDaysOfWeekString@@YAJGPEAGI@Z; GetDaysOfWeekString(ushort,ushort *,uint)
0x18002a00b  test    eax, eax
0x18002a00d  js      loc_18002A58F
0x18002a013  mov     r14d, 1
0x18002a019  cmp     [rsi+24h], r14w
0x18002a01e  jnz     short loc_18002A062
0x18002a020  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002a027  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x18002a02b  mov     r9d, ebx; cchBufferMax
0x18002a02e  mov     edx, 45Ah; uID
0x18002a033  call    cs:__imp_LoadStringW
0x18002a039  test    eax, eax
0x18002a03b  jz      loc_18002A114
0x18002a041  lea     r9, [rbp+10C0h+var_C40]
0x18002a048  mov     edx, 100h; unsigned __int64
0x18002a04d  lea     r8, [rbp+10C0h+Source]; unsigned __int16 *
0x18002a051  lea     rcx, [rbp+10C0h+var_EC0]; unsigned __int16 *
0x18002a058  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a05d  jmp     loc_180029F10
0x18002a062  movzx   r9d, word ptr [rsi+24h]
0x18002a067  lea     r8, [rsp+11C0h+var_1148]; unsigned __int16 *
0x18002a06c  mov     edx, 10h; unsigned __int64
0x18002a071  lea     rcx, [rbp+10C0h+var_1140]; unsigned __int16 *
0x18002a075  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a07a  lea     rax, [rbp+10C0h+var_C40]
0x18002a081  mov     edx, 45Bh; uID
0x18002a086  mov     [rsp+11C0h+var_1170], rax
0x18002a08b  lea     rax, [rbp+10C0h+var_1140]
0x18002a08f  mov     [rsp+11C0h+var_1170+8], rax
0x18002a094  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002a09b  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x18002a09f  mov     r9d, ebx; cchBufferMax
0x18002a0a2  call    cs:__imp_LoadStringW
0x18002a0a8  test    eax, eax
0x18002a0aa  jz      short loc_18002A114
0x18002a0ac  lea     rax, [rsp+11C0h+var_1170]
0x18002a0b1  xor     r9d, r9d; dwLanguageId
0x18002a0b4  mov     [rsp+11C0h+Arguments], rax; Arguments
0x18002a0b9  lea     rdx, [rbp+10C0h+Source]; lpSource
0x18002a0bd  lea     rax, [rbp+10C0h+var_EC0]
0x18002a0c4  mov     [rsp+11C0h+nSize], 100h; nSize
0x18002a0cc  xor     r8d, r8d; dwMessageId
0x18002a0cf  mov     [rsp+11C0h+lpBuffer], rax; lpBuffer
0x18002a0d4  mov     ecx, 2400h; dwFlags
0x18002a0d9  call    cs:__imp_FormatMessageW
0x18002a0df  test    eax, eax
0x18002a0e1  jnz     loc_180029F10
0x18002a0e7  jmp     short loc_18002A114
0x18002a0e9  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002a0f0  cmp     [rsi+24h], r8w
0x18002a0f5  jnz     short loc_18002A12F
0x18002a0f7  mov     r9d, r14d; cchBufferMax
0x18002a0fa  lea     r8, [rbp+10C0h+var_EC0]; lpBuffer
0x18002a101  mov     edx, 458h; uID
0x18002a106  call    cs:__imp_LoadStringW
0x18002a10c  test    eax, eax
0x18002a10e  jnz     loc_180029F0A
0x18002a114  call    cs:__imp_GetLastError
0x18002a11a  test    eax, eax
0x18002a11c  jle     loc_18002A58F
0x18002a122  movzx   eax, ax
0x18002a125  or      eax, 80070000h
0x18002a12a  jmp     loc_18002A58F
0x18002a12f  mov     r9d, ebx; cchBufferMax
0x18002a132  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x18002a136  mov     edx, 457h; uID
0x18002a13b  call    cs:__imp_LoadStringW
0x18002a141  test    eax, eax
  ... truncated ...
```
