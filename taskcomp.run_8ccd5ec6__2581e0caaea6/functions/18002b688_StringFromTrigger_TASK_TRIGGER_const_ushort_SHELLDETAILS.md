# StringFromTrigger(_TASK_TRIGGER * const,ushort * *,_SHELLDETAILS *)

- ea: `0x18002b688`
- end: `0x18002c09c`
- name: `?StringFromTrigger@@YAJQEAU_TASK_TRIGGER@@PEAPEAGPEAU_SHELLDETAILS@@@Z`
- size: `2580`
- prototype: `__int64 __fastcall(struct _TASK_TRIGGER *const, unsigned __int16 **, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800278f0`

## callees

- `0x1800040c0`
- `0x180006314`
- `0x18002aff4`
- `0x18002b2dc`
- `0x18002b688`
- `0x1800306c2`
- `0x180030700`
- `0x1800307c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bba8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002b7fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002b8a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002b94d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002b9c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002baaf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bb24`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bb94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bbd5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bc5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bce6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002be0a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002be6c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c019`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002b7fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002b8a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002b94d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002b9c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002baaf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bb24`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bb94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bbd5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bc5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002bce6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002be0a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002be6c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c019`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002b8de`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bb61`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002beaf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bf68`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002b8de`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bb61`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002beaf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002bf68`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18002bc31`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18002bd71`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18002bc31`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x18002bd71`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002bf02`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002bfc2`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002bf02`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18002bfc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b9f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b9f2`

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
0x18002b688  mov     [rsp-8+arg_10], rbx
0x18002b68d  push    rbp
0x18002b68e  push    rsi
0x18002b68f  push    rdi
0x18002b690  push    r12
0x18002b692  push    r13
0x18002b694  push    r14
0x18002b696  push    r15
0x18002b698  lea     rbp, [rsp-1090h]
0x18002b6a0  mov     eax, 1190h
0x18002b6a5  call    _alloca_probe
0x18002b6aa  sub     rsp, rax
0x18002b6ad  mov     rax, cs:__security_cookie
0x18002b6b4  xor     rax, rsp
0x18002b6b7  mov     [rbp+10C0h+var_40], rax
0x18002b6be  xorps   xmm0, xmm0
0x18002b6c1  mov     r12, rdx
0x18002b6c4  mov     rsi, rcx
0x18002b6c7  xor     r13d, r13d
0x18002b6ca  mov     [rdx], r13
0x18002b6cd  lea     rcx, [rbp+10C0h+var_C40]; void *
0x18002b6d4  mov     eax, dword ptr cs:aD; "%d"
0x18002b6da  mov     ebx, 200h
0x18002b6df  mov     dword ptr [rsp+11C0h+var_1148], eax
0x18002b6e3  mov     r8d, ebx; Size
0x18002b6e6  movzx   eax, word ptr cs:aD+4; ""
0x18002b6ed  xor     edx, edx; Val
0x18002b6ef  mov     [rsp+11C0h+var_1144], ax
0x18002b6f4  movups  xmmword ptr [rbp+10C0h+var_1140], xmm0
0x18002b6f8  movups  [rbp+10C0h+var_1130], xmm0
0x18002b6fc  call    memset_0
0x18002b701  xor     edx, edx; Val
0x18002b703  lea     r8d, [r13+40h]; Size
0x18002b707  lea     rcx, [rbp+10C0h+Buffer]; void *
0x18002b70e  call    memset_0
0x18002b713  xor     edx, edx; Val
0x18002b715  lea     rcx, [rbp+10C0h+var_440]; void *
0x18002b71c  mov     r8d, 400h; Size
0x18002b722  call    memset_0
0x18002b727  xor     edx, edx; Val
0x18002b729  lea     rcx, [rbp+10C0h+Source]; void *
0x18002b72d  mov     r8d, 0A0h; Size
0x18002b733  call    memset_0
0x18002b738  mov     r8d, ebx; Size
0x18002b73b  lea     rcx, [rbp+10C0h+var_EC0]; void *
0x18002b742  xor     edx, edx; Val
0x18002b744  call    memset_0
0x18002b749  xor     eax, eax
0x18002b74b  lea     r8d, [r13+1]; unsigned int
0x18002b74f  test    dword ptr [rsi+1Ch], 10000h
0x18002b756  lea     r9d, [r13+1Fh]
0x18002b75a  xorps   xmm0, xmm0
0x18002b75d  mov     [rsp+11C0h+var_1150], rax
0x18002b762  movups  xmmword ptr [rsp+11C0h+var_1170], xmm0
0x18002b767  lea     ebx, [rax+50h]
0x18002b76a  mov     r15d, 436h
0x18002b770  movups  [rsp+11C0h+var_1160], xmm0
0x18002b775  mov     r14d, 100h
0x18002b77b  jz      short loc_18002B789
0x18002b77d  lea     edi, [r15+2Dh]
0x18002b781  mov     r14d, r8d
0x18002b784  jmp     loc_18002B986
0x18002b789  mov     ecx, [rsi+20h]
0x18002b78c  mov     edi, r13d
0x18002b78f  test    ecx, ecx
0x18002b791  jz      short loc_18002B781
0x18002b793  sub     ecx, r8d
0x18002b796  jz      loc_18002BB77
0x18002b79c  sub     ecx, r8d
0x18002b79f  jz      loc_18002BA77
0x18002b7a5  sub     ecx, r8d
0x18002b7a8  jz      loc_18002B8EF
0x18002b7ae  sub     ecx, r8d
0x18002b7b1  jz      short loc_18002B7E1
0x18002b7b3  sub     ecx, r8d
0x18002b7b6  jz      short loc_18002B7DA
0x18002b7b8  sub     ecx, r8d
0x18002b7bb  jz      short loc_18002B7D3
0x18002b7bd  cmp     ecx, r8d
0x18002b7c0  jz      short loc_18002B7CC
0x18002b7c2  mov     eax, 8007000Dh
0x18002b7c7  jmp     loc_18002C071
0x18002b7cc  mov     edi, 46Ah
0x18002b7d1  jmp     short loc_18002B781
0x18002b7d3  mov     edi, 443h
0x18002b7d8  jmp     short loc_18002B781
0x18002b7da  mov     edi, 442h
0x18002b7df  jmp     short loc_18002B781
0x18002b7e1  movzx   edx, word ptr [rsi+24h]
0x18002b7e5  lea     r8, [rbp+10C0h+Buffer]; lpBuffer
0x18002b7ec  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002b7f3  add     edx, r15d; uID
0x18002b7f6  mov     r9d, 20h ; ' '; cchBufferMax
0x18002b7fc  call    cs:__imp_LoadStringW
0x18002b803  nop     dword ptr [rax+rax+00h]
0x18002b808  test    eax, eax
0x18002b80a  jz      loc_18002BBA8
0x18002b810  movzx   ecx, word ptr [rsi+26h]; unsigned __int16
0x18002b814  lea     rdx, [rbp+10C0h+var_C40]; unsigned __int16 *
0x18002b81b  call    ?GetDaysOfWeekString@@YAJGPEAGI@Z; GetDaysOfWeekString(ushort,ushort *,uint)
0x18002b820  test    eax, eax
0x18002b822  js      loc_18002C071
0x18002b828  movzx   ecx, word ptr [rsi+28h]; unsigned __int16
0x18002b82c  mov     eax, 0FFFh
0x18002b831  cmp     cx, ax
0x18002b834  jnz     short loc_18002B855
0x18002b836  lea     rax, [rbp+10C0h+Buffer]
0x18002b83d  mov     edx, 45Eh
0x18002b842  mov     [rsp+11C0h+var_1170], rax
0x18002b847  lea     rax, [rbp+10C0h+var_C40]
0x18002b84e  mov     [rsp+11C0h+var_1170+8], rax
0x18002b853  jmp     short loc_18002B892
0x18002b855  lea     rdx, [rbp+10C0h+var_440]; unsigned __int16 *
0x18002b85c  call    ?GetMonthsString@@YAJGPEAGI@Z; GetMonthsString(ushort,ushort *,uint)
0x18002b861  test    eax, eax
0x18002b863  js      loc_18002C071
0x18002b869  lea     rax, [rbp+10C0h+Buffer]
0x18002b870  mov     edx, 45Fh; uID
0x18002b875  mov     [rsp+11C0h+var_1170], rax
0x18002b87a  lea     rax, [rbp+10C0h+var_C40]
0x18002b881  mov     [rsp+11C0h+var_1170+8], rax
0x18002b886  lea     rax, [rbp+10C0h+var_440]
0x18002b88d  mov     qword ptr [rsp+11C0h+var_1160], rax
0x18002b892  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002b899  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x18002b89d  mov     r9d, ebx; cchBufferMax
0x18002b8a0  call    cs:__imp_LoadStringW
0x18002b8a7  nop     dword ptr [rax+rax+00h]
0x18002b8ac  test    eax, eax
0x18002b8ae  jz      loc_18002BBA8
0x18002b8b4  lea     rax, [rsp+11C0h+var_1170]
0x18002b8b9  xor     r9d, r9d; dwLanguageId
0x18002b8bc  mov     [rsp+11C0h+Arguments], rax; Arguments
0x18002b8c1  lea     rdx, [rbp+10C0h+Source]; lpSource
0x18002b8c5  lea     rax, [rbp+10C0h+var_EC0]
0x18002b8cc  mov     [rsp+11C0h+nSize], r14d; nSize
0x18002b8d1  xor     r8d, r8d; dwMessageId
0x18002b8d4  mov     [rsp+11C0h+lpBuffer], rax; lpBuffer
0x18002b8d9  mov     ecx, 2400h; dwFlags
0x18002b8de  call    cs:__imp_FormatMessageW
0x18002b8e5  nop     dword ptr [rax+rax+00h]
0x18002b8ea  jmp     loc_18002BBA0
0x18002b8ef  mov     r14d, r13d
0x18002b8f2  mov     ebx, r13d
0x18002b8f5  mov     edx, r13d
0x18002b8f8  mov     eax, [rsi+24h]
0x18002b8fb  mov     cl, dl
0x18002b8fd  shr     eax, cl
0x18002b8ff  test    r8b, al
0x18002b902  jz      short loc_18002B912
0x18002b904  add     bx, r8w
0x18002b908  cmp     bx, r8w
0x18002b90c  jnz     short loc_18002B912
0x18002b90e  lea     r14d, [r8+rdx]
0x18002b912  add     dx, r8w
0x18002b916  cmp     dx, r9w
0x18002b91a  jb      short loc_18002B8F8
0x18002b91c  mov     eax, 0FFFh
0x18002b921  cmp     [rsi+28h], ax
0x18002b925  jnz     loc_18002BA15
0x18002b92b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002b932  cmp     bx, r8w
0x18002b936  mov     edx, 45Ch
0x18002b93b  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x18002b93f  mov     ebx, 50h ; 'P'
0x18002b944  mov     r9d, ebx; cchBufferMax
0x18002b947  lea     eax, [rdx+8]
0x18002b94a  cmovnz  edx, eax; uID
0x18002b94d  call    cs:__imp_LoadStringW
0x18002b954  nop     dword ptr [rax+rax+00h]
0x18002b959  test    eax, eax
0x18002b95b  jz      loc_18002BBA8
0x18002b961  movzx   r9d, r14w
0x18002b965  mov     edx, 100h; unsigned __int64
0x18002b96a  lea     r8, [rbp+10C0h+Source]; unsigned __int16 *
0x18002b96e  lea     rcx, [rbp+10C0h+var_EC0]; unsigned __int16 *
0x18002b975  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b97a  mov     r14d, 1
0x18002b980  mov     r9d, 1Fh
0x18002b986  mov     eax, edi
0x18002b988  test    edi, edi
0x18002b98a  jz      loc_18002BBF2
0x18002b990  sub     eax, 442h
0x18002b995  jz      short loc_18002B9AB
0x18002b997  sub     eax, 1
0x18002b99a  jz      short loc_18002B9AB
0x18002b99c  sub     eax, 1
0x18002b99f  jz      short loc_18002B9AB
0x18002b9a1  sub     eax, r9d
0x18002b9a4  jz      short loc_18002B9AB
0x18002b9a6  cmp     eax, 7
0x18002b9a9  jnz     short loc_18002B9D5
0x18002b9ab  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002b9b2  lea     r8, [rbp+10C0h+var_840]; lpBuffer
0x18002b9b9  mov     r9d, 200h; cchBufferMax
0x18002b9bf  mov     edx, edi; uID
0x18002b9c1  call    cs:__imp_LoadStringW
0x18002b9c8  nop     dword ptr [rax+rax+00h]
0x18002b9cd  test    eax, eax
0x18002b9cf  jz      loc_18002BBA8
0x18002b9d5  lea     rcx, [rbp+10C0h+var_840]
0x18002b9dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b9e0  inc     rax
0x18002b9e3  cmp     [rcx+rax*2], r13w
0x18002b9e8  jnz     short loc_18002B9E0
0x18002b9ea  inc     eax
0x18002b9ec  mov     ebx, eax
0x18002b9ee  lea     rcx, [rax+rax]; cb
0x18002b9f2  call    cs:__imp_CoTaskMemAlloc
0x18002b9f9  nop     dword ptr [rax+rax+00h]
0x18002b9fe  mov     [r12], rax
0x18002ba02  test    rax, rax
0x18002ba05  jnz     loc_18002C05D
0x18002ba0b  mov     eax, 8007000Eh
0x18002ba10  jmp     loc_18002C071
0x18002ba15  movzx   r9d, r14w
0x18002ba19  lea     r8, [rsp+11C0h+var_1148]; unsigned __int16 *
0x18002ba1e  mov     edx, 10h; unsigned __int64
0x18002ba23  lea     rcx, [rbp+10C0h+var_1140]; unsigned __int16 *
0x18002ba27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ba2c  movzx   ecx, word ptr [rsi+28h]; unsigned __int16
0x18002ba30  lea     rdx, [rbp+10C0h+var_440]; unsigned __int16 *
0x18002ba37  call    ?GetMonthsString@@YAJGPEAGI@Z; GetMonthsString(ushort,ushort *,uint)
0x18002ba3c  test    eax, eax
0x18002ba3e  js      loc_18002C071
0x18002ba44  lea     rax, [rbp+10C0h+var_1140]
0x18002ba48  mov     edx, 45Dh
0x18002ba4d  mov     [rsp+11C0h+var_1170], rax
0x18002ba52  mov     r14d, 1
0x18002ba58  lea     rax, [rbp+10C0h+var_440]
0x18002ba5f  cmp     bx, r14w
0x18002ba63  mov     [rsp+11C0h+var_1170+8], rax
0x18002ba68  lea     eax, [rdx+8]
0x18002ba6b  cmovnz  edx, eax
0x18002ba6e  lea     ebx, [r14+4Fh]
0x18002ba72  jmp     loc_18002BB16
0x18002ba77  movzx   ecx, word ptr [rsi+26h]; unsigned __int16
0x18002ba7b  lea     rdx, [rbp+10C0h+var_C40]; unsigned __int16 *
0x18002ba82  call    ?GetDaysOfWeekString@@YAJGPEAGI@Z; GetDaysOfWeekString(ushort,ushort *,uint)
0x18002ba87  test    eax, eax
0x18002ba89  js      loc_18002C071
0x18002ba8f  mov     r14d, 1
0x18002ba95  cmp     [rsi+24h], r14w
0x18002ba9a  jnz     short loc_18002BAE4
0x18002ba9c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002baa3  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x18002baa7  mov     r9d, ebx; cchBufferMax
0x18002baaa  mov     edx, 45Ah; uID
0x18002baaf  call    cs:__imp_LoadStringW
0x18002bab6  nop     dword ptr [rax+rax+00h]
0x18002babb  test    eax, eax
0x18002babd  jz      loc_18002BBA8
0x18002bac3  lea     r9, [rbp+10C0h+var_C40]
0x18002baca  mov     edx, 100h; unsigned __int64
0x18002bacf  lea     r8, [rbp+10C0h+Source]; unsigned __int16 *
0x18002bad3  lea     rcx, [rbp+10C0h+var_EC0]; unsigned __int16 *
0x18002bada  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002badf  jmp     loc_18002B980
0x18002bae4  movzx   r9d, word ptr [rsi+24h]
0x18002bae9  lea     r8, [rsp+11C0h+var_1148]; unsigned __int16 *
0x18002baee  mov     edx, 10h; unsigned __int64
0x18002baf3  lea     rcx, [rbp+10C0h+var_1140]; unsigned __int16 *
0x18002baf7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bafc  lea     rax, [rbp+10C0h+var_C40]
0x18002bb03  mov     edx, 45Bh; uID
0x18002bb08  mov     [rsp+11C0h+var_1170], rax
0x18002bb0d  lea     rax, [rbp+10C0h+var_1140]
0x18002bb11  mov     [rsp+11C0h+var_1170+8], rax
0x18002bb16  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002bb1d  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x18002bb21  mov     r9d, ebx; cchBufferMax
0x18002bb24  call    cs:__imp_LoadStringW
0x18002bb2b  nop     dword ptr [rax+rax+00h]
0x18002bb30  test    eax, eax
0x18002bb32  jz      short loc_18002BBA8
0x18002bb34  lea     rax, [rsp+11C0h+var_1170]
0x18002bb39  xor     r9d, r9d; dwLanguageId
0x18002bb3c  mov     [rsp+11C0h+Arguments], rax; Arguments
0x18002bb41  lea     rdx, [rbp+10C0h+Source]; lpSource
0x18002bb45  lea     rax, [rbp+10C0h+var_EC0]
0x18002bb4c  mov     [rsp+11C0h+nSize], 100h; nSize
0x18002bb54  xor     r8d, r8d; dwMessageId
0x18002bb57  mov     [rsp+11C0h+lpBuffer], rax; lpBuffer
0x18002bb5c  mov     ecx, 2400h; dwFlags
0x18002bb61  call    cs:__imp_FormatMessageW
0x18002bb68  nop     dword ptr [rax+rax+00h]
0x18002bb6d  test    eax, eax
0x18002bb6f  jnz     loc_18002B980
0x18002bb75  jmp     short loc_18002BBA8
0x18002bb77  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002bb7e  cmp     [rsi+24h], r8w
0x18002bb83  jnz     short loc_18002BBC9
0x18002bb85  mov     r9d, r14d; cchBufferMax
0x18002bb88  lea     r8, [rbp+10C0h+var_EC0]; lpBuffer
0x18002bb8f  mov     edx, 458h; uID
0x18002bb94  call    cs:__imp_LoadStringW
0x18002bb9b  nop     dword ptr [rax+rax+00h]
0x18002bba0  test    eax, eax
0x18002bba2  jnz     loc_18002B97A
0x18002bba8  call    cs:__imp_GetLastError
  ... truncated ...
```
