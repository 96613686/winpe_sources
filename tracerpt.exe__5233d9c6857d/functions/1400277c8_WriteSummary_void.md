# WriteSummary(void)

- ea: `0x1400277c8`
- end: `0x140027ddc`
- name: `?WriteSummary@@YAXXZ`
- size: `1556`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140016ae0`

## callees

- `0x14002130c`
- `0x1400273e0`
- `0x1400277c8`
- `0x140032488`
- `0x1400400d6`
- `0x140040130`
- `0x1400401c0`

## import_xrefs

- `msvcrt!_wfopen` at `0x140027848`
- `msvcrt!_wfopen` at `0x140027848`
- `msvcrt!fwprintf` at `0x140027864`
- `msvcrt!fwprintf` at `0x14002788c`
- `msvcrt!fwprintf` at `0x14002795c`
- `msvcrt!fwprintf` at `0x140027970`
- `msvcrt!fwprintf` at `0x140027a46`
- `msvcrt!fwprintf` at `0x140027a94`
- `msvcrt!fwprintf` at `0x140027bfe`
- `msvcrt!fwprintf` at `0x140027c3f`
- `msvcrt!fwprintf` at `0x140027d4a`
- `msvcrt!fwprintf` at `0x140027d8a`
- `msvcrt!fwprintf` at `0x140027daa`
- `msvcrt!fwprintf` at `0x140027864`
- `msvcrt!fwprintf` at `0x14002788c`
- `msvcrt!fwprintf` at `0x14002795c`
- `msvcrt!fwprintf` at `0x140027970`
- `msvcrt!fwprintf` at `0x140027a46`
- `msvcrt!fwprintf` at `0x140027a94`
- `msvcrt!fwprintf` at `0x140027bfe`
- `msvcrt!fwprintf` at `0x140027c3f`
- `msvcrt!fwprintf` at `0x140027d4a`
- `msvcrt!fwprintf` at `0x140027d8a`
- `msvcrt!fwprintf` at `0x140027daa`
- `msvcrt!fclose` at `0x140027db3`
- `msvcrt!fclose` at `0x140027db3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400278c0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x140027996`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400278c0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x140027996`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1400278e1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1400279b3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1400278e1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1400279b3`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x140027914`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x1400279e6`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x140027914`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x1400279e6`

## pseudocode

```c
void WriteSummary(void)
{
  const wchar_t *v0; // rcx
  FILE *v1; // rax
  FILE *v2; // rbx
  _QWORD *v3; // rax
  unsigned int i; // edi
  LPVOID *v5; // r12
  LPVOID *v6; // rsi
  LPVOID *v7; // rdi
  _WORD *v8; // rcx
  __int64 v9; // r9
  int *v10; // rdx
  __int64 v11; // r8
  int *v12; // rcx
  LPVOID *v13; // r15
  int v14; // ecx
  LPVOID *v15; // r14
  LPVOID *v16; // rsi
  LPVOID *v17; // rdx
  LPVOID *v18; // r15
  LPVOID *v19; // rsi
  _QWORD *v20; // rdi
  unsigned __int16 *v21; // rax
  _WORD *v22; // rcx
  unsigned __int16 *v23; // r13
  __int64 v24; // r9
  int *v25; // rdx
  __int64 v26; // r8
  int *v27; // rcx
  _QWORD *v28; // r12
  _QWORD *v29; // rsi
  __int64 v30; // r8
  _QWORD *v31; // r14
  _QWORD *v32; // rax
  LPWSTR lpDateStr; // [rsp+20h] [rbp-E0h]
  LPWSTR lpDateStra; // [rsp+20h] [rbp-E0h]
  int cchDate[2]; // [rsp+28h] [rbp-D8h]
  FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+58h] [rbp-A8h] BYREF
  SYSTEMTIME Date; // [rsp+68h] [rbp-98h] BYREF
  SYSTEMTIME UniversalTime; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v41[64]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR DateStr[1024]; // [rsp+110h] [rbp+10h] BYREF
  int v43[512]; // [rsp+910h] [rbp+810h] BYREF

  FileTime = 0;
  SystemTime = 0;
  v0 = (const wchar_t *)*((_QWORD *)g_TraceContext + 779);
  LocalTime = 0;
  UniversalTime = 0;
  Date = 0;
  if ( !v0 )
    return;
  if ( !TotalEventCount )
    return;
  v1 = _wfopen(v0, L"w");
  v2 = v1;
  if ( !v1 )
    return;
  fwprintf(v1, L"Files Processed:\n");
  v3 = g_TraceContext;
  for ( i = 0; i < *((_DWORD *)g_TraceContext + 2); ++i )
  {
    fwprintf(v2, L"\t%s\n", v3[i + 3]);
    v3 = g_TraceContext;
  }
  FileTime = CurrentSystem;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) || SystemTime.wMonth > 0xCu )
  {
    SystemTime = 0;
    goto LABEL_13;
  }
  if ( !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) || LocalTime.wMonth > 0xCu )
  {
    LocalTime = 0;
LABEL_13:
    DateStr[0] = 0;
    goto LABEL_14;
  }
  GetDateFormatW(0x400u, 2u, &LocalTime, 0, DateStr, 1024);
LABEL_14:
  LODWORD(lpDateStr) = TotalEventsLost;
  fwprintf(
    v2,
    L"Total Buffers Processed %d\nTotal Events  Processed %d\nTotal Events  Lost      %d\n",
    TotalBuffersRead,
    TotalEventCount + TotalEventSkipped,
    lpDateStr);
  fwprintf(v2, L"Start Time              %ws\n", DateStr);
  FileTime = SystemTimeAsFileTime;
  if ( !FileTimeToSystemTime(&FileTime, &UniversalTime) || SystemTime.wMonth > 0xCu )
  {
    UniversalTime = 0;
    goto LABEL_21;
  }
  if ( !SystemTimeToTzSpecificLocalTime(0, &UniversalTime, &Date) || Date.wMonth > 0xCu )
  {
    Date = 0;
LABEL_21:
    DateStr[0] = 0;
    goto LABEL_22;
  }
  GetDateFormatW(0x400u, 2u, &Date, 0, DateStr, 1024);
LABEL_22:
  g_ElapseTime = *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CurrentSystem;
  fwprintf(
    v2,
    L"End Time                %ws\nElapsed Time            %I64d sec\n",
    DateStr,
    (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CurrentSystem) / 10000000LL
  + *(_QWORD *)&SystemTimeAsFileTime
  - *(_QWORD *)&CurrentSystem);
  fwprintf(
    v2,
    L"+-------------------------------------------------------------------------------------------------------------------"
     "------+\n"
     "|%10s   %-20s %-15s %-15s %-15s %-38s|\n"
     "+-------------------------------------------------------------------------------------------------------------------------+\n",
    L"Event Count",
    L"Event Name",
    L"Task",
    L"Opcode",
    L"Version",
    L"Guid");
  v5 = (LPVOID *)qword_140082180;
  if ( &qword_140082180 != qword_140082180 )
  {
    while ( 1 )
    {
      memset_0(v43, 0, sizeof(v43));
      v6 = v5;
      v5 = (LPVOID *)*v5;
      if ( *((_DWORD *)v6 + 10) )
      {
        v7 = 0;
        CpdiGuidToString(v41, 0x40u, (struct _GUID *)v6 + 3);
        v8 = v6[4];
        if ( v8 )
        {
          v9 = 2147483646;
          v10 = v43;
          v11 = 1024;
          do
          {
            if ( !v9 )
              break;
            if ( !*v8 )
              break;
            *(_WORD *)v10 = *v8++;
            v10 = (int *)((char *)v10 + 2);
            --v9;
            --v11;
          }
          while ( v11 );
          v12 = (int *)((char *)v10 - 2);
          if ( v11 )
            v12 = v10;
          *(_WORD *)v12 = 0;
        }
        v13 = v6 + 520;
        v14 = 0;
        v15 = (LPVOID *)v6[520];
        if ( v6 + 520 != v15 )
          break;
      }
LABEL_43:
      if ( &qword_140082180 == v5 )
        goto LABEL_44;
    }
    while ( 1 )
    {
      v16 = v15;
      v17 = v15;
      v15 = (LPVOID *)*v15;
      if ( !v7 )
        goto LABEL_39;
      if ( *((_WORD *)v7 + 15) != *((_WORD *)v17 + 15)
        || *((_BYTE *)v7 + 29) != *((_BYTE *)v17 + 29)
        || *((_BYTE *)v7 + 26) != *((_BYTE *)v17 + 26) )
      {
        break;
      }
      v14 += *((_DWORD *)v17 + 4);
LABEL_40:
      if ( v13 == v15 )
      {
        if ( v7 )
          PrintTaskOpcodeVersionSummary(v2, (int)v7, (int)v43);
        goto LABEL_43;
      }
    }
    PrintTaskOpcodeVersionSummary(v2, (int)v7, (int)v43);
LABEL_39:
    v14 = *((_DWORD *)v16 + 4);
    v7 = v16;
    goto LABEL_40;
  }
LABEL_44:
  fwprintf(
    v2,
    L"+-------------------------------------------------------------------------------------------------------------------------+\n");
  if ( byte_1400820CB )
  {
    fwprintf(
      v2,
      L"+---------------------------------------------------------------------------------------------------------+\n"
       "|%10s   %-20s %-15s %-15s %-38s|\n"
       "+---------------------------------------------------------------------------------------------------------+\n",
      L"Event Count",
      L"Event Name",
      L"Event ID",
      L"Version",
      L"Guid");
    v18 = (LPVOID *)qword_140082180;
    if ( &qword_140082180 != qword_140082180 )
    {
      while ( 1 )
      {
        memset_0(v43, 0, sizeof(v43));
        v19 = v18;
        v18 = (LPVOID *)*v18;
        if ( *((_DWORD *)v19 + 10) )
        {
          v20 = 0;
          v21 = CpdiGuidToString(v41, 0x40u, (struct _GUID *)v19 + 3);
          v22 = v19[4];
          v23 = v21;
          if ( v22 )
          {
            v24 = 2147483646;
            v25 = v43;
            v26 = 1024;
            do
            {
              if ( !v24 )
                break;
              if ( !*v22 )
                break;
              *(_WORD *)v25 = *v22++;
              v25 = (int *)((char *)v25 + 2);
              --v24;
              --v26;
            }
            while ( v26 );
            v27 = (int *)((char *)v25 - 2);
            if ( v26 )
              v27 = v25;
            *(_WORD *)v27 = 0;
          }
          v28 = v19 + 520;
          SortMofCountList(v19 + 520, *((unsigned int *)v19 + 1044));
          v29 = v19[520];
          v30 = 0;
          if ( v28 != (_QWORD *)*v28 )
            break;
        }
LABEL_65:
        if ( &qword_140082180 == v18 )
          goto LABEL_66;
      }
      while ( 1 )
      {
        v31 = v29;
        v32 = v29;
        v29 = (_QWORD *)*v29;
        if ( !v20 )
          goto LABEL_61;
        if ( *((_WORD *)v20 + 12) != *((_WORD *)v32 + 12) || *((_BYTE *)v20 + 26) != *((_BYTE *)v32 + 26) )
          break;
        v30 = (unsigned int)(*((_DWORD *)v31 + 4) + v30);
LABEL_62:
        if ( v28 == v29 )
        {
          if ( v20 )
          {
            cchDate[0] = *((unsigned __int8 *)v20 + 26);
            LODWORD(lpDateStra) = *((unsigned __int16 *)v20 + 12);
            fwprintf(v2, L"| %10d   %-20s %-15d %-15d %38s|\n", v30, v43, lpDateStra, *(_QWORD *)cchDate, v23);
          }
          goto LABEL_65;
        }
      }
      cchDate[0] = *((unsigned __int8 *)v20 + 26);
      LODWORD(lpDateStra) = *((unsigned __int16 *)v20 + 12);
      fwprintf(v2, L"| %10d   %-20s %-15d %-15d %38s|\n", v30, v43, lpDateStra, *(_QWORD *)cchDate, v23);
LABEL_61:
      v30 = *((unsigned int *)v31 + 4);
      v20 = v31;
      goto LABEL_62;
    }
LABEL_66:
    fwprintf(
      v2,
      L"+---------------------------------------------------------------------------------------------------------+\n");
  }
  fclose(v2);
}

```

## disassembly

```asm
0x1400277c8  push    rbp
0x1400277ca  push    rbx
0x1400277cb  push    rsi
0x1400277cc  push    rdi
0x1400277cd  push    r12
0x1400277cf  push    r13
0x1400277d1  push    r14
0x1400277d3  push    r15
0x1400277d5  lea     rbp, [rsp-1028h]
0x1400277dd  mov     eax, 1128h
0x1400277e2  call    _alloca_probe
0x1400277e7  sub     rsp, rax
0x1400277ea  mov     rax, cs:__security_cookie
0x1400277f1  xor     rax, rsp
0x1400277f4  mov     [rbp+1060h+var_50], rax
0x1400277fb  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140027802  xor     r14d, r14d
0x140027805  xorps   xmm0, xmm0
0x140027808  mov     qword ptr [rsp+1160h+FileTime.dwLowDateTime], r14
0x14002780d  xorps   xmm1, xmm1
0x140027810  movups  xmmword ptr [rsp+1160h+SystemTime.wYear], xmm0
0x140027815  mov     rcx, [rax+1858h]; FileName
0x14002781c  movups  xmmword ptr [rsp+1160h+LocalTime.wYear], xmm1
0x140027821  movups  xmmword ptr [rsp+1160h+UniversalTime.wYear], xmm0
0x140027826  movups  xmmword ptr [rsp+1160h+Date.wYear], xmm1
0x14002782b  test    rcx, rcx
0x14002782e  jz      loc_140027DB9
0x140027834  cmp     cs:?TotalEventCount@@3KA, r14d; ulong TotalEventCount
0x14002783b  jz      loc_140027DB9
0x140027841  lea     rdx, aW_0; "w"
0x140027848  call    cs:__imp__wfopen
0x14002784e  mov     rbx, rax
0x140027851  test    rax, rax
0x140027854  jz      loc_140027DB9
0x14002785a  lea     rdx, aFilesProcessed; "Files Processed:\n"
0x140027861  mov     rcx, rax; Stream
0x140027864  call    cs:__imp_fwprintf
0x14002786a  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140027871  mov     edi, r14d
0x140027874  cmp     [rax+8], r14d
0x140027878  jbe     short loc_1400278A0
0x14002787a  mov     r8d, edi
0x14002787d  lea     rdx, aS_1; "\t%s\n"
0x140027884  mov     rcx, rbx; Stream
0x140027887  mov     r8, [rax+r8*8+18h]
0x14002788c  call    cs:__imp_fwprintf
0x140027892  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140027899  inc     edi
0x14002789b  cmp     edi, [rax+8]
0x14002789e  jb      short loc_14002787A
0x1400278a0  mov     rax, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x1400278a7  lea     rdx, [rsp+1160h+SystemTime]; lpSystemTime
0x1400278ac  mov     rcx, rax
0x1400278af  mov     [rsp+1160h+FileTime.dwLowDateTime], eax
0x1400278b3  shr     rcx, 20h
0x1400278b7  mov     [rsp+1160h+FileTime.dwHighDateTime], ecx
0x1400278bb  lea     rcx, [rsp+1160h+FileTime]; lpFileTime
0x1400278c0  call    cs:__imp_FileTimeToSystemTime
0x1400278c6  mov     di, 0Ch
0x1400278ca  test    eax, eax
0x1400278cc  jz      short loc_140027926
0x1400278ce  cmp     [rsp+1160h+SystemTime.wMonth], di
0x1400278d3  ja      short loc_140027926
0x1400278d5  lea     r8, [rsp+1160h+LocalTime]; lpLocalTime
0x1400278da  xor     ecx, ecx; lpTimeZoneInformation
0x1400278dc  lea     rdx, [rsp+1160h+SystemTime]; lpUniversalTime
0x1400278e1  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x1400278e7  test    eax, eax
0x1400278e9  jz      short loc_14002791C
0x1400278eb  cmp     [rsp+1160h+LocalTime.wMonth], di
0x1400278f0  ja      short loc_14002791C
0x1400278f2  xor     r9d, r9d; lpFormat
0x1400278f5  mov     [rsp+1160h+cchDate], 400h; cchDate
0x1400278fd  lea     rax, [rbp+1060h+DateStr]
0x140027901  mov     ecx, 400h; Locale
0x140027906  lea     r8, [rsp+1160h+LocalTime]; lpDate
0x14002790b  mov     [rsp+1160h+lpDateStr], rax; lpDateStr
0x140027910  lea     edx, [r9+2]; dwFlags
0x140027914  call    cs:__imp_GetDateFormatW
0x14002791a  jmp     short loc_140027933
0x14002791c  xorps   xmm0, xmm0
0x14002791f  movups  xmmword ptr [rsp+1160h+LocalTime.wYear], xmm0
0x140027924  jmp     short loc_14002792E
0x140027926  xorps   xmm0, xmm0
0x140027929  movups  xmmword ptr [rsp+1160h+SystemTime.wYear], xmm0
0x14002792e  mov     [rbp+1060h+DateStr], r14w
0x140027933  mov     r9d, cs:?TotalEventSkipped@@3KA; ulong TotalEventSkipped
0x14002793a  lea     rdx, aTotalBuffersPr; "Total Buffers Processed %d\nTotal Event"...
0x140027941  mov     eax, cs:?TotalEventsLost@@3KA; ulong TotalEventsLost
0x140027947  mov     rcx, rbx; Stream
0x14002794a  add     r9d, cs:?TotalEventCount@@3KA; ulong TotalEventCount
0x140027951  mov     r8d, cs:?TotalBuffersRead@@3KA; ulong TotalBuffersRead
0x140027958  mov     dword ptr [rsp+1160h+lpDateStr], eax
0x14002795c  call    cs:__imp_fwprintf
0x140027962  lea     r8, [rbp+1060h+DateStr]
0x140027966  mov     rcx, rbx; Stream
0x140027969  lea     rdx, aStartTimeWs; "Start Time              %ws\n"
0x140027970  call    cs:__imp_fwprintf
0x140027976  mov     rax, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x14002797d  lea     rdx, [rsp+1160h+UniversalTime]; lpSystemTime
0x140027982  mov     rcx, rax
0x140027985  mov     [rsp+1160h+FileTime.dwLowDateTime], eax
0x140027989  shr     rcx, 20h
0x14002798d  mov     [rsp+1160h+FileTime.dwHighDateTime], ecx
0x140027991  lea     rcx, [rsp+1160h+FileTime]; lpFileTime
0x140027996  call    cs:__imp_FileTimeToSystemTime
0x14002799c  test    eax, eax
0x14002799e  jz      short loc_1400279F8
0x1400279a0  cmp     [rsp+1160h+SystemTime.wMonth], di
0x1400279a5  ja      short loc_1400279F8
0x1400279a7  lea     r8, [rsp+1160h+Date]; lpLocalTime
0x1400279ac  xor     ecx, ecx; lpTimeZoneInformation
0x1400279ae  lea     rdx, [rsp+1160h+UniversalTime]; lpUniversalTime
0x1400279b3  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x1400279b9  test    eax, eax
0x1400279bb  jz      short loc_1400279EE
0x1400279bd  cmp     [rsp+1160h+Date.wMonth], di
0x1400279c2  ja      short loc_1400279EE
0x1400279c4  xor     r9d, r9d; lpFormat
0x1400279c7  mov     [rsp+1160h+cchDate], 400h; cchDate
0x1400279cf  lea     rax, [rbp+1060h+DateStr]
0x1400279d3  mov     ecx, 400h; Locale
0x1400279d8  lea     r8, [rsp+1160h+Date]; lpDate
0x1400279dd  mov     [rsp+1160h+lpDateStr], rax; lpDateStr
0x1400279e2  lea     edx, [r9+2]; dwFlags
0x1400279e6  call    cs:__imp_GetDateFormatW
0x1400279ec  jmp     short loc_140027A05
0x1400279ee  xorps   xmm0, xmm0
0x1400279f1  movups  xmmword ptr [rsp+1160h+Date.wYear], xmm0
0x1400279f6  jmp     short loc_140027A00
0x1400279f8  xorps   xmm0, xmm0
0x1400279fb  movups  xmmword ptr [rsp+1160h+UniversalTime.wYear], xmm0
0x140027a00  mov     [rbp+1060h+DateStr], r14w
0x140027a05  mov     rcx, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x140027a0c  lea     r8, [rbp+1060h+DateStr]
0x140027a10  sub     rcx, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x140027a17  mov     rax, 0D6BF94D5E57A42BDh
0x140027a21  imul    rcx
0x140027a24  mov     cs:?g_ElapseTime@@3_JA, rcx; __int64 g_ElapseTime
0x140027a2b  add     rdx, rcx
0x140027a2e  mov     rcx, rbx; Stream
0x140027a31  sar     rdx, 17h
0x140027a35  mov     r9, rdx
0x140027a38  shr     r9, 3Fh
0x140027a3c  add     r9, rdx
0x140027a3f  lea     rdx, aEndTimeWsElaps; "End Time                %ws\nElapsed Ti"...
0x140027a46  call    cs:__imp_fwprintf
0x140027a4c  lea     rax, aOpcode; "Opcode"
0x140027a53  mov     rcx, rbx; Stream
0x140027a56  lea     rdi, aGuid; "Guid"
0x140027a5d  mov     [rsp+1160h+var_1128], rdi
0x140027a62  lea     r15, aVersion_1; "Version"
0x140027a69  mov     [rsp+1160h+var_1130], r15
0x140027a6e  lea     r9, aEventName_0; "Event Name"
0x140027a75  mov     qword ptr [rsp+1160h+cchDate], rax
0x140027a7a  lea     r8, aEventCount; "Event Count"
0x140027a81  lea     rax, aTask_2; "Task"
0x140027a88  lea     rdx, asc_140058160; "+--------------------------------------"...
0x140027a8f  mov     [rsp+1160h+lpDateStr], rax
0x140027a94  call    cs:__imp_fwprintf
0x140027a9a  mov     r12, cs:qword_140082180
0x140027aa1  lea     rsi, qword_140082180
0x140027aa8  cmp     rsi, r12
0x140027aab  jz      loc_140027BF4
0x140027ab1  xor     edx, edx; Val
0x140027ab3  lea     rcx, [rbp+1060h+var_850]; void *
0x140027aba  mov     r8d, 800h; Size
0x140027ac0  call    memset_0
0x140027ac5  lea     rsi, [r12]
0x140027ac9  mov     r12, [r12]
0x140027acd  cmp     [rsi+28h], r14d
0x140027ad1  jbe     loc_140027BD6
0x140027ad7  lea     r8, [rsi+30h]; struct _GUID *
0x140027adb  mov     edx, 40h ; '@'; unsigned int
0x140027ae0  lea     rcx, [rbp+1060h+var_10D0]; unsigned __int16 *
0x140027ae4  mov     rdi, r14
0x140027ae7  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x140027aec  mov     rcx, [rsi+20h]
0x140027af0  mov     r13, rax
0x140027af3  test    rcx, rcx
0x140027af6  jz      short loc_140027B3B
0x140027af8  mov     r9d, 7FFFFFFEh
0x140027afe  lea     rdx, [rbp+1060h+var_850]
0x140027b05  mov     r8d, 400h
0x140027b0b  test    r9, r9
0x140027b0e  jz      short loc_140027B2C
0x140027b10  movzx   eax, word ptr [rcx]
0x140027b13  test    ax, ax
0x140027b16  jz      short loc_140027B2C
0x140027b18  mov     [rdx], ax
0x140027b1b  add     rcx, 2
0x140027b1f  add     rdx, 2
0x140027b23  dec     r9
0x140027b26  sub     r8, 1
0x140027b2a  jnz     short loc_140027B0B
0x140027b2c  test    r8, r8
0x140027b2f  lea     rcx, [rdx-2]
0x140027b33  cmovnz  rcx, rdx
0x140027b37  mov     [rcx], r14w
0x140027b3b  lea     r15, [rsi+1040h]
0x140027b42  mov     ecx, r14d
0x140027b45  mov     r14, [r15]
0x140027b48  cmp     r15, r14
0x140027b4b  jz      loc_140027BD3
0x140027b51  mov     rsi, r14
0x140027b54  mov     rdx, r14
0x140027b57  mov     r14, [r14]
0x140027b5a  test    rdi, rdi
0x140027b5d  jz      short loc_140027B9E
0x140027b5f  movzx   eax, word ptr [rdx+1Eh]
0x140027b63  cmp     [rdi+1Eh], ax
0x140027b67  jnz     short loc_140027B7E
0x140027b69  mov     al, [rdx+1Dh]
0x140027b6c  cmp     [rdi+1Dh], al
0x140027b6f  jnz     short loc_140027B7E
0x140027b71  mov     al, [rdx+1Ah]
0x140027b74  cmp     [rdi+1Ah], al
0x140027b77  jnz     short loc_140027B7E
0x140027b79  add     ecx, [rdx+10h]
0x140027b7c  jmp     short loc_140027BA4
0x140027b7e  mov     eax, [rsi+30h]
0x140027b81  lea     r8, [rbp+1060h+var_850]; int
0x140027b88  mov     [rsp+1160h+cchDate], eax
0x140027b8c  mov     r9, r13
0x140027b8f  mov     dword ptr [rsp+1160h+lpDateStr], ecx
0x140027b93  mov     rdx, rdi; int
0x140027b96  mov     rcx, rbx; Stream
0x140027b99  call    PrintTaskOpcodeVersionSummary
0x140027b9e  mov     ecx, [rsi+10h]
0x140027ba1  mov     rdi, rsi
0x140027ba4  cmp     r15, r14
0x140027ba7  jnz     short loc_140027B51
0x140027ba9  xor     r14d, r14d
0x140027bac  test    rdi, rdi
0x140027baf  jz      short loc_140027BD6
0x140027bb1  mov     eax, [rsi+30h]
0x140027bb4  lea     r8, [rbp+1060h+var_850]; int
0x140027bbb  mov     [rsp+1160h+cchDate], eax
0x140027bbf  mov     r9, r13
0x140027bc2  mov     dword ptr [rsp+1160h+lpDateStr], ecx
0x140027bc6  mov     rdx, rdi; int
0x140027bc9  mov     rcx, rbx; Stream
0x140027bcc  call    PrintTaskOpcodeVersionSummary
0x140027bd1  jmp     short loc_140027BD6
0x140027bd3  xor     r14d, r14d
0x140027bd6  lea     rsi, qword_140082180
0x140027bdd  cmp     rsi, r12
0x140027be0  jnz     loc_140027AB1
0x140027be6  lea     rdi, aGuid; "Guid"
0x140027bed  lea     r15, aVersion_1; "Version"
0x140027bf4  lea     rdx, asc_1400583A0; "+--------------------------------------"...
0x140027bfb  mov     rcx, rbx; Stream
0x140027bfe  call    cs:__imp_fwprintf
0x140027c04  cmp     cs:byte_1400820CB, r14b
0x140027c0b  jz      loc_140027DB0
0x140027c11  mov     [rsp+1160h+var_1130], rdi
0x140027c16  lea     rax, aEventId_0; "Event ID"
0x140027c1d  mov     qword ptr [rsp+1160h+cchDate], r15
0x140027c22  lea     r9, aEventName_0; "Event Name"
0x140027c29  lea     r8, aEventCount; "Event Count"
0x140027c30  mov     [rsp+1160h+lpDateStr], rax
0x140027c35  lea     rdx, asc_1400584C0; "+--------------------------------------"...
0x140027c3c  mov     rcx, rbx; Stream
0x140027c3f  call    cs:__imp_fwprintf
0x140027c45  mov     r15, cs:qword_140082180
0x140027c4c  cmp     rsi, r15
0x140027c4f  jz      loc_140027DA0
0x140027c55  xor     edx, edx; Val
0x140027c57  lea     rcx, [rbp+1060h+var_850]; void *
0x140027c5e  mov     r8d, 800h; Size
0x140027c64  call    memset_0
0x140027c69  lea     rsi, [r15]
0x140027c6c  mov     r15, [r15]
0x140027c6f  cmp     [rsi+28h], r14d
0x140027c73  jbe     loc_140027D90
0x140027c79  lea     r8, [rsi+30h]; struct _GUID *
0x140027c7d  mov     edx, 40h ; '@'; unsigned int
0x140027c82  lea     rcx, [rbp+1060h+var_10D0]; unsigned __int16 *
0x140027c86  mov     rdi, r14
0x140027c89  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x140027c8e  mov     rcx, [rsi+20h]
0x140027c92  mov     r13, rax
0x140027c95  test    rcx, rcx
0x140027c98  jz      short loc_140027CDD
0x140027c9a  mov     r9d, 7FFFFFFEh
0x140027ca0  lea     rdx, [rbp+1060h+var_850]
0x140027ca7  mov     r8d, 400h
0x140027cad  test    r9, r9
0x140027cb0  jz      short loc_140027CCE
0x140027cb2  movzx   eax, word ptr [rcx]
0x140027cb5  test    ax, ax
0x140027cb8  jz      short loc_140027CCE
0x140027cba  mov     [rdx], ax
0x140027cbd  add     rcx, 2
0x140027cc1  add     rdx, 2
0x140027cc5  dec     r9
0x140027cc8  sub     r8, 1
0x140027ccc  jnz     short loc_140027CAD
0x140027cce  test    r8, r8
0x140027cd1  lea     rcx, [rdx-2]
  ... truncated ...
```
