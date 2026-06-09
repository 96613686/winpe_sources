# GetHardErrorText

- ea: `0x18000c050`
- end: `0x18000d029`
- name: `GetHardErrorText`
- size: `4057`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000dda0`

## callees

- `0x180004384`
- `0x18000c050`
- `0x18000daf0`
- `0x18000dbb4`
- `0x180011bd8`
- `0x1800138ad`
- `0x1800138b9`
- `0x1800138c5`
- `0x1800138d1`
- `0x1800138f0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18000c2f0`
- `KERNELBASE!LocalAlloc` at `0x18000c5ef`
- `KERNELBASE!LocalAlloc` at `0x18000c78c`
- `KERNELBASE!LocalAlloc` at `0x18000c874`
- `KERNELBASE!LocalAlloc` at `0x18000c908`
- `KERNELBASE!LocalAlloc` at `0x18000cd24`
- `KERNELBASE!LocalAlloc` at `0x18000c2f0`
- `KERNELBASE!LocalAlloc` at `0x18000c5ef`
- `KERNELBASE!LocalAlloc` at `0x18000c78c`
- `KERNELBASE!LocalAlloc` at `0x18000c874`
- `KERNELBASE!LocalAlloc` at `0x18000c908`
- `KERNELBASE!LocalAlloc` at `0x18000cd24`
- `ntdll!RtlFindMessage` at `0x18000c717`
- `ntdll!RtlFindMessage` at `0x18000c9fd`
- `ntdll!RtlFindMessage` at `0x18000c717`
- `ntdll!RtlFindMessage` at `0x18000c9fd`
- `ntdll!wcsrchr` at `0x18000c655`
- `ntdll!wcsrchr` at `0x18000c655`
- `ntdll!_strnicmp` at `0x18000c41f`
- `ntdll!_strnicmp` at `0x18000c41f`
- `ntdll!RtlFreeAnsiString` at `0x18000c3e8`
- `ntdll!RtlFreeAnsiString` at `0x18000c53c`
- `ntdll!RtlFreeAnsiString` at `0x18000c3e8`
- `ntdll!RtlFreeAnsiString` at `0x18000c53c`
- `ntdll!RtlCreateUnicodeString` at `0x18000c94b`
- `ntdll!RtlCreateUnicodeString` at `0x18000ca6f`
- `ntdll!RtlCreateUnicodeString` at `0x18000cd83`
- `ntdll!RtlCreateUnicodeString` at `0x18000ce15`
- `ntdll!RtlCreateUnicodeString` at `0x18000cf41`
- `ntdll!RtlCreateUnicodeString` at `0x18000c94b`
- `ntdll!RtlCreateUnicodeString` at `0x18000ca6f`
- `ntdll!RtlCreateUnicodeString` at `0x18000cd83`
- `ntdll!RtlCreateUnicodeString` at `0x18000ce15`
- `ntdll!RtlCreateUnicodeString` at `0x18000cf41`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000c3d0`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000c3d0`
- `ntdll!strstr` at `0x18000c399`
- `ntdll!strstr` at `0x18000c399`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000c37e`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000c37e`
- `ntdll!NtReadVirtualMemory` at `0x18000c2b5`
- `ntdll!NtReadVirtualMemory` at `0x18000c321`
- `ntdll!NtReadVirtualMemory` at `0x18000c2b5`
- `ntdll!NtReadVirtualMemory` at `0x18000c321`
- `ntdll!NtAlpcOpenSenderProcess` at `0x18000c228`
- `ntdll!NtAlpcOpenSenderProcess` at `0x18000c228`
- `ntdll!NtQueryInformationProcess` at `0x18000c61c`
- `ntdll!NtQueryInformationProcess` at `0x18000c61c`
- `ntdll!RtlFreeUnicodeString` at `0x18000c3f9`
- `ntdll!RtlFreeUnicodeString` at `0x18000c513`
- `ntdll!RtlFreeUnicodeString` at `0x18000c3f9`
- `ntdll!RtlFreeUnicodeString` at `0x18000c513`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c6ef`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c6ef`
- `ntdll!RtlInitUnicodeString` at `0x18000c108`
- `ntdll!RtlInitUnicodeString` at `0x18000c11a`
- `ntdll!RtlInitUnicodeString` at `0x18000c961`
- `ntdll!RtlInitUnicodeString` at `0x18000ca87`
- `ntdll!RtlInitUnicodeString` at `0x18000cd99`
- `ntdll!RtlInitUnicodeString` at `0x18000cf5b`
- `ntdll!RtlInitUnicodeString` at `0x18000cf80`
- `ntdll!RtlInitUnicodeString` at `0x18000cfa0`
- `ntdll!RtlInitUnicodeString` at `0x18000cff8`
- `ntdll!RtlInitUnicodeString` at `0x18000d018`
- `ntdll!RtlInitUnicodeString` at `0x18000c108`
- `ntdll!RtlInitUnicodeString` at `0x18000c11a`
- `ntdll!RtlInitUnicodeString` at `0x18000c961`
- `ntdll!RtlInitUnicodeString` at `0x18000ca87`
- `ntdll!RtlInitUnicodeString` at `0x18000cd99`
- `ntdll!RtlInitUnicodeString` at `0x18000cf5b`
- `ntdll!RtlInitUnicodeString` at `0x18000cf80`
- `ntdll!RtlInitUnicodeString` at `0x18000cfa0`
- `ntdll!RtlInitUnicodeString` at `0x18000cff8`
- `ntdll!RtlInitUnicodeString` at `0x18000d018`
- `ntdll!RtlEnterCriticalSection` at `0x18000c6b9`
- `ntdll!RtlEnterCriticalSection` at `0x18000c6b9`
- `ntdll!NtClose` at `0x18000caab`
- `ntdll!NtClose` at `0x18000caab`
- `ntdll!RtlFreeHeap` at `0x18000caed`
- `ntdll!RtlFreeHeap` at `0x18000caed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c63e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c98f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c9ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c9be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cda8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c63e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c98f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c9ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c9be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cda8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c6d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c6d5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c24f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c24f`
- `CSRSRV!CsrImpersonateClient` at `0x18000c196`
- `CSRSRV!CsrImpersonateClient` at `0x18000c196`
- `CSRSRV!CsrRevertToSelf` at `0x18000c56c`
- `CSRSRV!CsrRevertToSelf` at `0x18000c56c`
- `USER32!EnumThreadWindows` at `0x18000c83b`
- `USER32!EnumThreadWindows` at `0x18000c83b`
- `USER32!GetWindowTextLengthW` at `0x18000c850`
- `USER32!GetWindowTextLengthW` at `0x18000c850`
- `USER32!GetWindowTextW` at `0x18000c895`
- `USER32!GetWindowTextW` at `0x18000c895`

## string_xrefs

- `0x18000c6ce`: `ntdll`

## pseudocode

```c
__int64 __fastcall GetHardErrorText(__int64 a1)
{
  __int64 v1; // r12
  int v2; // r15d
  int v3; // r13d
  unsigned int *v4; // r14
  unsigned int v5; // ebx
  int v6; // esi
  unsigned int i; // ecx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rbx
  int v11; // ecx
  DWORD v12; // r8d
  HLOCAL v13; // rax
  int v14; // eax
  char *v15; // rax
  PCHAR v16; // rcx
  __int64 MaximumLength; // rdx
  PCHAR v18; // rcx
  __int64 v19; // rax
  PCHAR v20; // r8
  PCHAR v21; // rax
  unsigned __int64 v22; // rax
  _WORD *v23; // rdx
  __int64 v24; // rcx
  _WORD *v25; // r8
  _WORD *v26; // rcx
  int v27; // edi
  __int64 v28; // rcx
  HLOCAL v29; // r15
  unsigned __int64 v30; // rax
  const wchar_t **v31; // rax
  const wchar_t **v32; // r13
  wchar_t *v33; // rax
  __int64 v34; // r14
  const wchar_t *v35; // rsi
  BYTE *Text; // rbx
  unsigned int v37; // edi
  __int16 v38; // ax
  HLOCAL v39; // rax
  unsigned int v40; // eax
  HLOCAL v41; // rbx
  DWORD v42; // ecx
  unsigned int WindowTextLengthW; // eax
  __int64 v44; // rdi
  WCHAR *v45; // rax
  __int64 *v46; // r15
  __int64 v47; // rbx
  int v48; // edi
  HLOCAL v49; // rdx
  __int64 v50; // r12
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  unsigned int v54; // r14d
  wchar_t *v55; // rbx
  void *v56; // rcx
  __int64 v57; // rdi
  __int64 v58; // rcx
  void *StringOrError; // rbx
  BOOLEAN v60; // al
  int v61; // eax
  PWSTR v62; // r8
  struct _UNICODE_STRING v63; // xmm0
  __int64 result; // rax
  struct _UNICODE_STRING v65; // xmm1
  const wchar_t *v66; // rax
  __int64 v67; // rcx
  PMESSAGE_RESOURCE_ENTRY v68; // rbx
  wchar_t *p_Flags; // rbx
  wchar_t j; // ax
  int v71; // eax
  __int64 v72; // rcx
  _WORD *v73; // r15
  int v74; // esi
  __int64 v75; // rax
  int v76; // ecx
  __int64 v77; // rax
  __int64 v78; // rcx
  unsigned int v79; // r14d
  wchar_t *v80; // rdi
  __int64 *v81; // rax
  __int64 *v82; // rcx
  int v83; // r9d
  int v84; // r8d
  wchar_t v85; // ax
  wchar_t *v86; // rbx
  wchar_t *v87; // rdi
  bool v88; // zf
  __int64 v89; // rax
  unsigned __int64 v90; // rcx
  ULONG v91; // eax
  int v92; // [rsp+40h] [rbp-C0h]
  int v93; // [rsp+44h] [rbp-BCh]
  int v94; // [rsp+48h] [rbp-B8h]
  HANDLE ProcessHandle; // [rsp+50h] [rbp-B0h] BYREF
  int v96; // [rsp+58h] [rbp-A8h]
  int v97; // [rsp+5Ch] [rbp-A4h] BYREF
  HLOCAL v98; // [rsp+60h] [rbp-A0h]
  __int64 v99; // [rsp+68h] [rbp-98h]
  HLOCAL hMem[2]; // [rsp+70h] [rbp-90h] BYREF
  int v101; // [rsp+80h] [rbp-80h]
  int v102; // [rsp+84h] [rbp-7Ch]
  PMESSAGE_RESOURCE_ENTRY MessageResourceEntry; // [rsp+88h] [rbp-78h] BYREF
  _STRING SourceString; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v105; // [rsp+A0h] [rbp-60h] BYREF
  int v106; // [rsp+B0h] [rbp-50h]
  int v107; // [rsp+B4h] [rbp-4Ch]
  unsigned int v108; // [rsp+B8h] [rbp-48h]
  __int64 v109; // [rsp+C0h] [rbp-40h]
  LPARAM lParam; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int *v111; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  __m128i Buffer; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v114[48]; // [rsp+100h] [rbp+0h] BYREF
  ULONG MessageId[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v116; // [rsp+138h] [rbp+38h]
  const wchar_t *v117; // [rsp+140h] [rbp+40h]
  unsigned __int64 v118; // [rsp+148h] [rbp+48h]
  __int64 v119; // [rsp+150h] [rbp+50h]
  __int128 v120; // [rsp+158h] [rbp+58h]
  int v121; // [rsp+168h] [rbp+68h]
  __int128 v122; // [rsp+170h] [rbp+70h] BYREF
  int v123; // [rsp+180h] [rbp+80h]
  wchar_t pszDest[1032]; // [rsp+190h] [rbp+90h] BYREF

  v99 = a1;
  v1 = a1;
  v96 = 0;
  v102 = 0;
  lParam = 0;
  MessageResourceEntry = 0;
  v97 = 0;
  v2 = 0;
  SourceString = 0;
  Buffer = 0;
  *(_OWORD *)hMem = 0;
  v105 = 0;
  DestinationString = 0;
  memset(v114, 0, 44);
  memset_0(pszDest, 0, 0x802u);
  v92 = 0;
  v123 = 0;
  v121 = 0;
  v101 = 0;
  v122 = 0;
  v3 = 0;
  v120 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&v105, 0);
  v4 = (unsigned int *)(v1 + 24);
  ProcessHandle = 0;
  v5 = *(_DWORD *)(v1 + 88);
  v6 = -1;
  v94 = 0;
  v108 = -1;
  v111 = (unsigned int *)(v1 + 24);
  *(_DWORD *)(v1 + 84) = 1;
  memcpy_0(MessageId, (const void *)(v1 + 96), 8LL * v5);
  for ( i = 0; i < 5; ++i )
  {
    if ( i < v5 )
    {
      v8 = *(_DWORD *)(v1 + 92);
      if ( !_bittest(&v8, i) )
        continue;
    }
    *(_QWORD *)&MessageId[2 * i] = &qword_180017108;
    *((_DWORD *)&v120 + i) = 2;
  }
  v9 = *(_QWORD *)(v1 + 8);
  v10 = 0;
  if ( v9 )
  {
    if ( !(unsigned __int8)CsrImpersonateClient(v9) )
      goto LABEL_69;
    v2 = 1;
  }
  v11 = *(_DWORD *)(v1 + 64);
  if ( (unsigned int)(v11 + 1073741806) > 2 && (unsigned int)(v11 + 1073741662) > 1 && v11 != -1073741643 )
  {
    if ( *(_QWORD *)(v1 + 192) )
    {
      if ( WinStationApiPort )
      {
        *(_DWORD *)v114 = 48;
        memset(&v114[8], 0, 20);
        *(_OWORD *)&v114[32] = 0;
        if ( (int)NtAlpcOpenSenderProcess(&ProcessHandle, WinStationApiPort, v1 + 24, 0, 1040, v114) < 0 )
          ProcessHandle = 0;
      }
    }
    if ( ProcessHandle )
    {
LABEL_20:
      if ( !*(_DWORD *)(v1 + 92) || !*(_DWORD *)(v1 + 88) )
        goto LABEL_67;
      while ( 1 )
      {
        if ( ((1 << v10) & *(_DWORD *)(v1 + 92)) != 0
          && NtReadVirtualMemory(ProcessHandle, *(PVOID *)&v4[2 * (unsigned int)v10 + 18], &Buffer, 0x10u, 0) >= 0 )
        {
          *(__m128i *)hMem = Buffer;
          LOWORD(hMem[0]) = _mm_cvtsi128_si32(Buffer) & 0xFFFE;
          v13 = LocalAlloc(0x40u, LOWORD(hMem[0]) + 2LL);
          hMem[1] = v13;
          if ( v13 )
          {
            if ( NtReadVirtualMemory(ProcessHandle, (PVOID)Buffer.m128i_i64[1], v13, LOWORD(hMem[0]), 0) < 0
              || (WORD1(hMem[0]) = hMem[0], RtlUnicodeStringToAnsiString(&SourceString, (PCUNICODE_STRING)hMem, 1u) < 0) )
            {
              LocalFree(hMem[1]);
            }
            else
            {
              v15 = strstr(SourceString.Buffer, "\\Device");
              v16 = SourceString.Buffer;
              if ( v15 != SourceString.Buffer )
              {
                if ( SourceString.Length > 4u )
                {
                  if ( !_strnicmp(SourceString.Buffer, "\\??\\", 4u) )
                  {
                    MaximumLength = SourceString.MaximumLength;
                    if ( SourceString.MaximumLength )
                    {
                      v18 = SourceString.Buffer;
                      v19 = 2147483646;
                      v20 = SourceString.Buffer + 4;
                      do
                      {
                        if ( !v19 )
                          break;
                        if ( !*v20 )
                          break;
                        *v18++ = *v20++;
                        --v19;
                        --MaximumLength;
                      }
                      while ( MaximumLength );
                      v21 = v18 - 1;
                      if ( MaximumLength )
                        v21 = v18;
                      *v21 = 0;
                    }
                    SourceString.Length -= 4;
                    v22 = (unsigned __int64)WORD1(hMem[0]) >> 1;
                    if ( v22 )
                    {
                      v23 = hMem[1];
                      v24 = 2147483646;
                      v25 = (char *)hMem[1] + 8;
                      do
                      {
                        if ( !v24 )
                          break;
                        if ( !*v25 )
                          break;
                        *v23++ = *v25++;
                        --v24;
                        --v22;
                      }
                      while ( v22 );
                      v26 = v23 - 1;
                      if ( v22 )
                        v26 = v23;
                      *v26 = 0;
                    }
                    LOWORD(hMem[0]) -= 8;
                  }
LABEL_54:
                  v16 = SourceString.Buffer;
                }
                if ( *(_DWORD *)(v1 + 64) == 1073741848
                  || *(_DWORD *)(v1 + 64) == -1073741283
                  || *(_DWORD *)(v1 + 64) == -1073741103 )
                {
                  *(HLOCAL *)&MessageId[2 * (unsigned int)v10] = hMem[1];
                  if ( (unsigned int)v10 < 5 )
                    *((_DWORD *)&v120 + (unsigned int)v10) = 2;
                  RtlFreeAnsiString(&SourceString);
                }
                else
                {
                  *(_QWORD *)&MessageId[2 * (unsigned int)v10] = v16;
                  if ( (unsigned int)v10 < 5 )
                    *((_DWORD *)&v120 + (unsigned int)v10) = 1;
                  RtlFreeUnicodeString((PUNICODE_STRING)hMem);
                }
                v94 |= 1 << v10;
                goto LABEL_65;
              }
              if ( (int)SubstituteDeviceName((PCUNICODE_STRING)hMem) < 0
                || RtlAnsiStringToUnicodeString((PUNICODE_STRING)hMem, &SourceString, 0) >= 0 )
              {
                goto LABEL_54;
              }
              RtlFreeAnsiString(&SourceString);
              RtlFreeUnicodeString((PUNICODE_STRING)hMem);
            }
          }
        }
LABEL_65:
        LODWORD(v10) = v10 + 1;
        if ( (unsigned int)v10 >= *(_DWORD *)(v1 + 88) )
        {
          v1 = v99;
          v6 = -1;
          v3 = 0;
          v10 = 0;
          goto LABEL_67;
        }
      }
    }
    goto LABEL_17;
  }
  if ( !v2 )
  {
LABEL_17:
    v12 = *(_DWORD *)(v1 + 32);
    goto LABEL_18;
  }
  v14 = *(_DWORD *)(v1 + 88);
  if ( !v14 )
    goto LABEL_19;
  v12 = v4[2 * (v14 - 1) + 18];
LABEL_18:
  ProcessHandle = OpenProcess(0x410u, 0, v12);
LABEL_19:
  if ( ProcessHandle )
    goto LABEL_20;
LABEL_67:
  if ( v2 )
    CsrRevertToSelf();
LABEL_69:
  v27 = 0;
  if ( v4[16] > 4 && (v119 & 0x20000) != 0 )
    v27 = 0x20000;
  if ( v4[10] == -1073741283 )
  {
    v90 = (unsigned __int64)v117;
    v91 = MessageId[0];
    *(_DWORD *)(v1 + 136) |= 0x80u;
    *(_DWORD *)(v1 + 184) = v91;
    *(_DWORD *)(v1 + 188) = v116;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(v90 & -(__int64)(*(_WORD *)v90 != 0)));
    RtlInitUnicodeString(&v105, (PCWSTR)(v118 & -(__int64)(*(_WORD *)v118 != 0)));
  }
  else
  {
    if ( v4[10] != 1073741848 )
    {
      v28 = v4[14];
      v29 = 0;
      v30 = (unsigned __int64)v4[10] >> 30;
      v106 = 0;
      v98 = 0;
      v93 = wOptions[v28] | wIcons[v30] | v27;
      if ( ProcessHandle )
      {
        v31 = (const wchar_t **)LocalAlloc(0, 0x21Au);
        v32 = v31;
        if ( v31 )
        {
          if ( NtQueryInformationProcess(ProcessHandle, ProcessImageFileName, v31, 0x21Au, 0) >= 0 )
          {
            if ( *(_WORD *)v32 )
            {
              v33 = wcsrchr(v32[1], 0x5Cu);
              if ( v33 )
                v34 = (__int64)(v33 + 1);
              else
                v34 = (__int64)v32[1];
              v109 = v34;
              v101 = 1;
              v107 = 1;
              v92 = 0;
              if ( v34 )
              {
LABEL_88:
                RtlEnterCriticalSection(&gcsUserSrv);
                if ( !gNtDllHandle )
                  gNtDllHandle = GetModuleHandleW(L"ntdll");
                RtlLeaveCriticalSection(&gcsUserSrv);
                if ( RtlFindMessage(gNtDllHandle, 0xBu, 0, *(_DWORD *)(v1 + 64), &MessageResourceEntry) >= 0 )
                {
                  Text = MessageResourceEntry->Text;
                  if ( *(_WORD *)MessageResourceEntry->Text == 123 )
                  {
                    v37 = 0;
                    Text = (BYTE *)&MessageResourceEntry[1];
                    while ( 1 )
                    {
                      v38 = *(_WORD *)Text;
                      if ( !*(_WORD *)Text )
                        break;
                      Text += 2;
                      if ( v38 == 125 )
                        break;
                      ++v37;
                    }
                    while ( *(_WORD *)Text && *(_WORD *)Text <= 0x20u )
                      Text += 2;
                    if ( v37 - 1 <= 0x7FFFFFFC )
                    {
                      v39 = LocalAlloc(0x40u, 2LL * (v37 + 1));
                      v98 = v39;
                      v29 = v39;
                      if ( v39 )
                      {
                        v106 = 1;
                        memcpy_0(v39, &MessageResourceEntry[1], 2LL * v37);
                      }
                    }
                  }
                  v35 = aUnknownHardErr;
                  if ( *(_WORD *)Text )
                    v35 = (const wchar_t *)Text;
                  v10 = 0;
                  if ( v29 )
                    goto LABEL_116;
                }
                else
                {
                  v35 = aUnknownHardErr;
                }
                v40 = *(_DWORD *)(v1 + 64) & 0xC0000000;
                switch ( v40 )
                {
                  case 0u:
                    v98 = gpwszaSUCCESS;
                    break;
                  case 0x40000000u:
                    v41 = gpwszaSYSTEM_INFORMATION;
                    goto LABEL_114;
                  case 0x80000000:
                    v41 = gpwszaSYSTEM_WARNING;
                    goto LABEL_114;
                  case 0xC0000000:
                    v41 = gpwszaSYSTEM_ERROR;
LABEL_114:
                    v98 = v41;
                    v10 = 0;
                    break;
                }
LABEL_116:
                v42 = *(_DWORD *)(v1 + 40);
                lParam = 0;
                EnumThreadWindows(v42, FindWindowFromThread, (LPARAM)&lParam);
                if ( lParam
                  && (WindowTextLengthW = GetWindowTextLengthW((HWND)lParam),
                      v44 = WindowTextLengthW,
                      WindowTextLengthW - 1 <= 0x7FFFFFFB) )
                {
                  v45 = (WCHAR *)LocalAlloc(0x40u, 2LL * (WindowTextLengthW + 3));
                  v46 = (__int64 *)v45;
                  if ( v45 )
                  {
                    v47 = (unsigned int)(v44 + 1);
                    GetWindowTextW((HWND)lParam, v45, v44 + 1);
                    *((_WORD *)v46 + v44) = 58;
                    v48 = v44 + 2;
                    *((_WORD *)v46 + v47) = 32;
                    v10 = 0;
                  }
                  else
                  {
                    v48 = 0;
                  }
                  if ( v48 )
                    goto LABEL_125;
                }
                else
                {
                  v48 = 0;
                }
                v46 = &qword_180017108;
LABEL_125:
                v49 = v98;
                v50 = -1;
                v51 = -1;
                do
                  ++v51;
                while ( *((_WORD *)v98 + v51) );
                v52 = -1;
                do
                  ++v52;
                while ( *(_WORD *)(v34 + 2 * v52) );
                v53 = (unsigned int)(v48 + v52 + v51 + 4);
                if ( (unsigned int)v53 <= 0x7FFFFFFF )
                {
                  v54 = v53;
                  v55 = (wchar_t *)LocalAlloc(0x40u, 2 * v53);
                  if ( v55 )
                  {
                    StringCchPrintfW(v55, v54, L"%s%s - %s", v46, v109, v98);
                    if ( !RtlCreateUnicodeString(&DestinationString, v55) )
                      RtlInitUnicodeString(&DestinationString, 0);
                    LocalFree(v55);
                  }
                  v49 = v98;
                  v10 = 0;
                  v34 = v109;
                }
                if ( v106 )
                  LocalFree(v49);
                if ( v101 )
                {
                  v56 = v32;
                  if ( !v107 )
                    v56 = (void *)v34;
                  LocalFree(v56);
                }
                if ( v48 )
                  LocalFree(v46);
                v4 = v111;
                if ( v111[10] == -1073741500 )
                {
                  v57 = *(_QWORD *)MessageId;
                  if ( RtlFindMessage(gNtDllHandle, 0xBu, 0, MessageId[0], &MessageResourceEntry) < 0 )
                  {
                    StringOrError = (void *)RtlLoadStringOrError(v58, 4, aUnknownSoftwar);
                    StringCchPrintfW(pszDest, 0x401u, v35, StringOrError, v57, v116);
                    if ( v96 )
                      LocalFree(StringOrError);
                    v60 = RtlCreateUnicodeString(&v105, pszDest);
                    LODWORD(v10) = 0;
                    goto LABEL_148;
                  }
                  if ( (_DWORD)v57 == -1073741819 )
                  {
                    v66 = L"written";
                    if ( !v117 )
                      v66 = L"read";
                  }
                  else
                  {
                    if ( (_DWORD)v57 != -1073741818 )
                    {
                      v68 = MessageResourceEntry;
                      if ( !wcsncmp_0((const wchar_t *)MessageResourceEntry->Text, L"{EXCEPTION}", 0xBu) )
                      {
                        p_Flags = &v68[4].Flags;
                        for ( j = *p_Flags; *p_Flags; j = *p_Flags )
                        {
                          if ( j > 0x20u )
                            break;
                          ++p_Flags;
                        }
                      }
                      else
                      {
                        p_Flags = aUnknownSoftwar;
                      }
                      v71 = ValidateFormatStringW(v35, 3, &v122, &v97);
                      v67 = (unsigned int)v71;
                      if ( v71 >= 0 )
                      {
                        if ( v97 > 0 && (_DWORD)v122 != 2 )
                          v67 = 3221225485LL;
                        if ( v97 > 1 && DWORD1(v122) != (_DWORD)v120 )
                          v67 = 3221225485LL;
                        if ( (v97 <= 2 || DWORD2(v122) == DWORD1(v120)) && (int)v67 >= 0 )
                          StringCchPrintfW(pszDest, 0x401u, v35, p_Flags, v57, v116);
                      }
                      v10 = 0;
LABEL_190:
                      v73 = (_WORD *)RtlLoadStringOrError(v67, 1, L"Click on OK to terminate the application");
                      if ( v4[14] == 2 )
                      {
                        v10 = RtlLoadStringOrError(v72, 2, L"Click on CANCEL xx to debug the application");
                        if ( v10 )
                        {
                          v75 = -1;
                          do
                            ++v75;
                          while ( *(_WORD *)(v10 + 2 * v75) );
                          v74 = v102;
                          v76 = v75 + 1;
                          goto LABEL_198;
                        }
                        v74 = v102;
                      }
                      else
                      {
                        v74 = 0;
                      }
                      v76 = 0;
LABEL_198:
                      v77 = -1;
                      do
                        ++v77;
                      while ( pszDest[v77] );
                      do
                        ++v50;
                      while ( v73[v50] );
                      v78 = (unsigned int)(v50 + v77 + v76 + 2);
                      if ( (unsigned int)v78 <= 0x7FFFFFFF )
                      {
                        v79 = v78;
                        v80 = (wchar_t *)LocalAlloc(0x40u, 2 * v78);
                        if ( v80 )
                        {
                          v81 = &qword_180017108;
                          v82 = &qword_180017108;
                          if ( v10 )
                          {
                            v82 = (__int64 *)v10;
                            v81 = (__int64 *)L"\n";
                          }
                          StringCchPrintfW(v80, v79, L"%s\n%s%s%s", pszDest, v73, v81, v82);
                          if ( !RtlCreateUnicodeString(&v105, v80) )
                            RtlInitUnicodeString(&v105, 0);
                          LocalFree(v80);
                        }
                        v4 = v111;
                      }
                      if ( v96 )
                        LocalFree(v73);
                      if ( v74 )
                        LocalFree((HLOCAL)v10);
                      LODWORD(v10) = 0;
                      goto LABEL_150;
                    }
                    v66 = v117;
                  }
                  StringCchPrintfW(pszDest, 0x401u, (STRSAFE_LPCWSTR)MessageResourceEntry->Text, v116, v118, v66);
                  goto LABEL_190;
                }
                if ( v111[10] == -1073741103 )
                {
                  StringCchPrintfW(pszDest, 0x401u, v35, *(_QWORD *)MessageId);
                  v60 = RtlCreateUnicodeString(&v105, pszDest);
LABEL_148:
                  if ( !v60 )
                    RtlInitUnicodeString(&v105, 0);
LABEL_150:
                  v3 = v92;
LABEL_151:
                  v1 = v99;
                  v27 = v93;
                  goto LABEL_152;
                }
                v3 = v92;
                v83 = ValidateFormatStringW(v35, 5, &v122, &v97);
                if ( v83 < 0 )
                  goto LABEL_223;
                v84 = 0;
                if ( v97 <= 0 )
                  goto LABEL_222;
                do
                {
                  if ( *((_DWORD *)&v122 + v84) != *((_DWORD *)&v120 + v84) )
                    v83 = -1073741811;
                  ++v84;
                }
                while ( v84 < v97 );
                if ( v83 < 0 )
LABEL_223:
                  StringCchPrintfW(
                    pszDest,
                    0x401u,
                    L"Exception Processing Message 0x%x - Unexpected parameters",
                    v4[10]);
                else
LABEL_222:
                  StringCchPrintfW(pszDest, 0x401u, v35, *(_QWORD *)MessageId, v116, v117, v118);
                v85 = pszDest[0];
                if ( !pszDest[0] )
                {
LABEL_235:
                  if ( !RtlCreateUnicodeString(&v105, pszDest) )
                    RtlInitUnicodeString(&v105, 0);
                  goto LABEL_151;
                }
                v86 = pszDest;
                while ( 1 )
                {
                  v87 = v86 + 1;
                  if ( v85 != 13 )
                    goto LABEL_231;
                  v88 = *v87 == 10;
                  *v86 = 32;
                  if ( v88 )
                    break;
LABEL_233:
                  ++v86;
                  v85 = *v87;
                  if ( !*v87 )
                  {
                    v3 = v92;
                    LODWORD(v10) = 0;
                    goto LABEL_235;
                  }
                }
                v89 = -1;
                do
                  ++v89;
                while ( v87[v89] );
                memmove_0(v86, v86 + 1, (unsigned int)(2 * v89 + 2));
LABEL_231:
                if ( *v86 == 10 )
                  *v86 = 32;
                goto LABEL_233;
              }
LABEL_87:
              v34 = RtlLoadStringOrError(v28, 3, L"System Process");
              v109 = v34;
              goto LABEL_88;
            }
            v92 = 1;
          }
          LocalFree(v32);
        }
      }
      else
      {
        v32 = 0;
      }
      v107 = 0;
      goto LABEL_87;
    }
    RtlInitUnicodeString(&v105, (PCWSTR)(*(_QWORD *)MessageId & -(__int64)(**(_WORD **)MessageId != 0)));
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(v116 & -(__int64)(*(_WORD *)v116 != 0)));
    v27 = (unsigned int)v117 & 0xFFDFFFFF;
    if ( v4[16] == 4 )
      v6 = v118;
    v108 = v6;
  }
LABEL_152:
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  v61 = v94;
  if ( v94 && v4[16] )
  {
    do
    {
      if ( _bittest(&v61, v10) )
      {
        v62 = *(PWSTR *)&MessageId[2 * (unsigned int)v10];
        if ( v62 != v105.Buffer && v62 != DestinationString.Buffer )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v62);
        v61 = v94;
      }
      LODWORD(v10) = v10 + 1;
    }
    while ( (unsigned int)v10 < v4[16] );
  }
  if ( v3 )
    *(_DWORD *)(v1 + 136) |= 0x40u;
  v63 = v105;
  result = v108;
  v65 = DestinationString;
  *(_DWORD *)(v1 + 176) = v27;
  *(struct _UNICODE_STRING *)(v1 + 144) = v63;
  *(_DWORD *)(v1 + 180) = result;
  *(struct _UNICODE_STRING *)(v1 + 160) = v65;
  return result;
}

```

## disassembly

```asm
0x18000c050  push    rbp
0x18000c052  push    rbx
0x18000c053  push    rsi
0x18000c054  push    rdi
0x18000c055  push    r12
0x18000c057  push    r13
0x18000c059  push    r14
0x18000c05b  push    r15
0x18000c05d  lea     rbp, [rsp-8B8h]
0x18000c065  sub     rsp, 9B8h
0x18000c06c  mov     rax, cs:__security_cookie
0x18000c073  xor     rax, rsp
0x18000c076  mov     [rbp+8F0h+var_50], rax
0x18000c07d  xorps   xmm0, xmm0
0x18000c080  mov     [rsp+9F0h+var_988], rcx
0x18000c085  xor     edi, edi
0x18000c087  xorps   xmm1, xmm1
0x18000c08a  mov     r12, rcx
0x18000c08d  mov     [rsp+9F0h+var_998], edi
0x18000c091  movups  [rbp+8F0h+var_8E0], xmm0
0x18000c095  xor     eax, eax
0x18000c097  mov     [rbp+8F0h+var_96C], edi
0x18000c09a  xor     edx, edx; Val
0x18000c09c  mov     [rbp+8F0h+lParam], rdi
0x18000c0a0  mov     r8d, 802h; Size
0x18000c0a6  mov     [rbp+8F0h+MessageResourceEntry], rdi
0x18000c0aa  lea     rcx, [rbp+8F0h+pszDest]; void *
0x18000c0b1  mov     [rsp+9F0h+var_994], edi
0x18000c0b5  movups  [rbp+8F0h+var_8E0+0Ch], xmm0
0x18000c0b9  mov     r15d, edi
0x18000c0bc  movups  xmmword ptr [rbp+8F0h+SourceString.Length], xmm0
0x18000c0c0  movups  [rbp+8F0h+Buffer], xmm0
0x18000c0c4  movups  xmmword ptr [rsp+9F0h+hMem], xmm1
0x18000c0c9  movups  xmmword ptr [rbp+8F0h+var_950.Length], xmm0
0x18000c0cd  movups  xmmword ptr [rbp+8F0h+DestinationString.Length], xmm1
0x18000c0d1  movups  [rbp+8F0h+var_8F0], xmm0
0x18000c0d5  call    memset_0
0x18000c0da  xor     eax, eax
0x18000c0dc  mov     [rsp+9F0h+var_9B0], edi
0x18000c0e0  xorps   xmm0, xmm0
0x18000c0e3  mov     [rbp+8F0h+var_870], eax
0x18000c0e9  xorps   xmm1, xmm1
0x18000c0ec  mov     [rbp+8F0h+var_888], eax
0x18000c0ef  xor     edx, edx; SourceString
0x18000c0f1  mov     [rbp+8F0h+var_970], edi
0x18000c0f4  lea     rcx, [rbp+8F0h+DestinationString]; DestinationString
0x18000c0f8  mov     [rsp+9F0h+ProcessHandle], rdi
0x18000c0fd  movups  [rbp+8F0h+var_880], xmm0
0x18000c101  mov     r13d, edi
0x18000c104  movups  [rbp+8F0h+var_898], xmm1
0x18000c108  call    cs:__imp_RtlInitUnicodeString
0x18000c10f  nop     dword ptr [rax+rax+00h]
0x18000c114  xor     edx, edx; SourceString
0x18000c116  lea     rcx, [rbp+8F0h+var_950]; DestinationString
0x18000c11a  call    cs:__imp_RtlInitUnicodeString
0x18000c121  nop     dword ptr [rax+rax+00h]
0x18000c126  lea     r14, [r12+18h]
0x18000c12b  mov     [rsp+9F0h+ProcessHandle], rdi
0x18000c130  mov     ebx, [r14+40h]
0x18000c134  lea     rdx, [r14+48h]; Src
0x18000c138  or      esi, 0FFFFFFFFh
0x18000c13b  mov     [rsp+9F0h+var_9A8], edi
0x18000c13f  mov     r8d, ebx
0x18000c142  mov     [rbp+8F0h+var_938], esi
0x18000c145  shl     r8, 3; Size
0x18000c149  lea     rcx, [rbp+8F0h+MessageId]; void *
0x18000c14d  mov     [rbp+8F0h+var_920], r14
0x18000c151  mov     dword ptr [r14+3Ch], 1
0x18000c159  call    memcpy_0
0x18000c15e  mov     ecx, edi
0x18000c160  lea     rdx, qword_180017108
0x18000c167  cmp     ecx, ebx
0x18000c169  jnb     short loc_18000C174
0x18000c16b  mov     eax, [r14+44h]
0x18000c16f  bt      eax, ecx
0x18000c172  jnb     short loc_18000C183
0x18000c174  mov     eax, ecx
0x18000c176  mov     qword ptr [rbp+rax*8+8F0h+MessageId], rdx
0x18000c17b  mov     dword ptr [rbp+rax*4+8F0h+var_898], 2
0x18000c183  inc     ecx
0x18000c185  cmp     ecx, 5
0x18000c188  jb      short loc_18000C167
0x18000c18a  mov     rcx, [r12+8]
0x18000c18f  xor     ebx, ebx
0x18000c191  test    rcx, rcx
0x18000c194  jz      short loc_18000C1AE
0x18000c196  call    cs:__imp_CsrImpersonateClient
0x18000c19d  nop     dword ptr [rax+rax+00h]
0x18000c1a2  test    al, al
0x18000c1a4  jz      loc_18000C578
0x18000c1aa  lea     r15d, [rbx+1]
0x18000c1ae  mov     ecx, [r14+28h]
0x18000c1b2  lea     eax, [rcx+3FFFFFEEh]
0x18000c1b8  cmp     eax, 2
0x18000c1bb  jbe     loc_18000C347
0x18000c1c1  lea     eax, [rcx+3FFFFF5Eh]
0x18000c1c7  cmp     eax, 1
0x18000c1ca  jbe     loc_18000C347
0x18000c1d0  cmp     ecx, 0C00000B5h
0x18000c1d6  jz      loc_18000C347
0x18000c1dc  cmp     [r12+0C0h], rbx
0x18000c1e4  jz      short loc_18000C23D
0x18000c1e6  mov     rdx, cs:WinStationApiPort
0x18000c1ed  test    rdx, rdx
0x18000c1f0  jz      short loc_18000C23D
0x18000c1f2  lea     rax, [rbp+8F0h+var_8F0]
0x18000c1f6  mov     dword ptr [rbp+8F0h+var_8F0], 30h ; '0'
0x18000c1fd  xorps   xmm0, xmm0
0x18000c200  mov     [rsp+9F0h+var_9C8], rax
0x18000c205  xor     r9d, r9d
0x18000c208  mov     dword ptr [rsp+9F0h+NumberOfBytesRead], 410h
0x18000c210  mov     r8, r14
0x18000c213  mov     qword ptr [rbp+8F0h+var_8F0+8], rbx
0x18000c217  lea     rcx, [rsp+9F0h+ProcessHandle]
0x18000c21c  mov     dword ptr [rbp+8F0h+var_8E0+8], ebx
0x18000c21f  mov     qword ptr [rbp+8F0h+var_8E0], rbx
0x18000c223  movdqu  [rbp+8F0h+var_8D0], xmm0
0x18000c228  call    cs:__imp_NtAlpcOpenSenderProcess
0x18000c22f  nop     dword ptr [rax+rax+00h]
0x18000c234  test    eax, eax
0x18000c236  jns     short loc_18000C23D
0x18000c238  mov     [rsp+9F0h+ProcessHandle], rbx
0x18000c23d  cmp     [rsp+9F0h+ProcessHandle], rbx
0x18000c242  jnz     short loc_18000C26B
0x18000c244  mov     r8d, [r14+8]; dwProcessId
0x18000c248  xor     edx, edx; bInheritHandle
0x18000c24a  mov     ecx, 410h; dwDesiredAccess
0x18000c24f  call    cs:__imp_OpenProcess
0x18000c256  nop     dword ptr [rax+rax+00h]
0x18000c25b  mov     [rsp+9F0h+ProcessHandle], rax
0x18000c260  cmp     [rsp+9F0h+ProcessHandle], rbx
0x18000c265  jz      loc_18000C567
0x18000c26b  cmp     [r14+44h], ebx
0x18000c26f  jz      loc_18000C567
0x18000c275  cmp     [r14+40h], ebx
0x18000c279  jbe     loc_18000C567
0x18000c27f  xor     r12d, r12d
0x18000c282  lea     r13d, [r12+4]
0x18000c287  mov     ecx, ebx
0x18000c289  mov     esi, 1
0x18000c28e  shl     esi, cl
0x18000c290  test    [r14+44h], esi
0x18000c294  jz      loc_18000C54C
0x18000c29a  mov     rcx, [rsp+9F0h+ProcessHandle]; ProcessHandle
0x18000c29f  lea     r8, [rbp+8F0h+Buffer]; Buffer
0x18000c2a3  mov     edi, ebx
0x18000c2a5  mov     r9d, 10h; NumberOfBytesToRead
0x18000c2ab  mov     [rsp+9F0h+NumberOfBytesRead], r12; NumberOfBytesRead
0x18000c2b0  mov     rdx, [r14+rdi*8+48h]; BaseAddress
0x18000c2b5  call    cs:__imp_NtReadVirtualMemory
0x18000c2bc  nop     dword ptr [rax+rax+00h]
0x18000c2c1  test    eax, eax
0x18000c2c3  js      loc_18000C54C
0x18000c2c9  movaps  xmm0, [rbp+8F0h+Buffer]
0x18000c2cd  mov     ecx, 0FFFEh
0x18000c2d2  movd    eax, xmm0
0x18000c2d6  movdqa  xmmword ptr [rsp+9F0h+hMem], xmm0
0x18000c2dc  and     ax, cx
0x18000c2df  mov     ecx, 40h ; '@'; uFlags
0x18000c2e4  movzx   edx, ax
0x18000c2e7  mov     word ptr [rsp+9F0h+hMem], dx
0x18000c2ec  add     rdx, 2; uBytes
0x18000c2f0  call    cs:__imp_LocalAlloc
0x18000c2f7  nop     dword ptr [rax+rax+00h]
0x18000c2fc  mov     [rsp+9F0h+hMem+8], rax
0x18000c301  test    rax, rax
0x18000c304  jz      loc_18000C54C
0x18000c30a  movzx   r9d, word ptr [rsp+9F0h+hMem]; NumberOfBytesToRead
0x18000c310  mov     r8, rax; Buffer
0x18000c313  mov     rdx, qword ptr [rbp+8F0h+Buffer+8]; BaseAddress
0x18000c317  mov     rcx, [rsp+9F0h+ProcessHandle]; ProcessHandle
0x18000c31c  mov     [rsp+9F0h+NumberOfBytesRead], r12; NumberOfBytesRead
0x18000c321  call    cs:__imp_NtReadVirtualMemory
0x18000c328  nop     dword ptr [rax+rax+00h]
0x18000c32d  test    eax, eax
0x18000c32f  jns     short loc_18000C368
0x18000c331  mov     rcx, [rsp+9F0h+hMem+8]; hMem
0x18000c336  call    cs:__imp_LocalFree
0x18000c33d  nop     dword ptr [rax+rax+00h]
0x18000c342  jmp     loc_18000C54C
0x18000c347  test    r15d, r15d
0x18000c34a  jz      loc_18000C244
0x18000c350  mov     eax, [r14+40h]
0x18000c354  test    eax, eax
0x18000c356  jz      loc_18000C260
0x18000c35c  dec     eax
0x18000c35e  mov     r8d, [r14+rax*8+48h]
0x18000c363  jmp     loc_18000C248
0x18000c368  movzx   eax, word ptr [rsp+9F0h+hMem]
0x18000c36d  lea     rdx, [rsp+9F0h+hMem]; SourceString
0x18000c372  mov     r8b, 1; AllocateDestinationString
0x18000c375  mov     word ptr [rsp+9F0h+hMem+2], ax
0x18000c37a  lea     rcx, [rbp+8F0h+SourceString]; DestinationString
0x18000c37e  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18000c385  nop     dword ptr [rax+rax+00h]
0x18000c38a  test    eax, eax
0x18000c38c  js      short loc_18000C331
0x18000c38e  mov     rcx, [rbp+8F0h+SourceString.Buffer]; Str
0x18000c392  lea     rdx, SubStr; "\\Device"
0x18000c399  call    cs:__imp_strstr
0x18000c3a0  nop     dword ptr [rax+rax+00h]
0x18000c3a5  mov     rcx, [rbp+8F0h+SourceString.Buffer]; String1
0x18000c3a9  cmp     rax, rcx
0x18000c3ac  jnz     short loc_18000C40A
0x18000c3ae  lea     rdx, [rbp+8F0h+SourceString]
0x18000c3b2  lea     rcx, [rsp+9F0h+hMem]; String1
0x18000c3b7  call    SubstituteDeviceName
0x18000c3bc  test    eax, eax
0x18000c3be  js      loc_18000C4DA
0x18000c3c4  xor     r8d, r8d; AllocateDestinationString
0x18000c3c7  lea     rdx, [rbp+8F0h+SourceString]; SourceString
0x18000c3cb  lea     rcx, [rsp+9F0h+hMem]; DestinationString
0x18000c3d0  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000c3d7  nop     dword ptr [rax+rax+00h]
0x18000c3dc  test    eax, eax
0x18000c3de  jns     loc_18000C4DA
0x18000c3e4  lea     rcx, [rbp+8F0h+SourceString]; AnsiString
0x18000c3e8  call    cs:__imp_RtlFreeAnsiString
0x18000c3ef  nop     dword ptr [rax+rax+00h]
0x18000c3f4  lea     rcx, [rsp+9F0h+hMem]; UnicodeString
0x18000c3f9  call    cs:__imp_RtlFreeUnicodeString
0x18000c400  nop     dword ptr [rax+rax+00h]
0x18000c405  jmp     loc_18000C54C
0x18000c40a  cmp     [rbp+8F0h+SourceString.Length], r13w
0x18000c40f  jbe     loc_18000C4DE
0x18000c415  mov     r8, r13; MaxCount
0x18000c418  lea     rdx, asc_180017B78; "\\??\\"
0x18000c41f  call    cs:__imp__strnicmp
0x18000c426  nop     dword ptr [rax+rax+00h]
0x18000c42b  xor     r10d, r10d
0x18000c42e  test    eax, eax
0x18000c430  jnz     loc_18000C4D7
0x18000c436  movzx   edx, [rbp+8F0h+SourceString.MaximumLength]
0x18000c43a  test    rdx, rdx
0x18000c43d  jz      short loc_18000C479
0x18000c43f  mov     rcx, [rbp+8F0h+SourceString.Buffer]
0x18000c443  mov     eax, 7FFFFFFEh
0x18000c448  lea     r8, [rcx+4]
0x18000c44c  test    rax, rax
0x18000c44f  jz      short loc_18000C46B
0x18000c451  mov     r9b, [r8]
0x18000c454  test    r9b, r9b
0x18000c457  jz      short loc_18000C46B
0x18000c459  mov     [rcx], r9b
0x18000c45c  inc     r8
0x18000c45f  inc     rcx
0x18000c462  dec     rax
0x18000c465  sub     rdx, 1
0x18000c469  jnz     short loc_18000C44C
0x18000c46b  test    rdx, rdx
0x18000c46e  lea     rax, [rcx-1]
0x18000c472  cmovnz  rax, rcx
0x18000c476  mov     [rax], r10b
0x18000c479  mov     eax, 0FFFCh
0x18000c47e  add     [rbp+8F0h+SourceString.Length], ax
0x18000c482  movzx   eax, word ptr [rsp+9F0h+hMem+2]
0x18000c487  shr     rax, 1
0x18000c48a  jz      short loc_18000C4CD
0x18000c48c  mov     rdx, [rsp+9F0h+hMem+8]
0x18000c491  mov     ecx, 7FFFFFFEh
0x18000c496  lea     r8, [rdx+8]
0x18000c49a  test    rcx, rcx
0x18000c49d  jz      short loc_18000C4BE
0x18000c49f  movzx   r9d, word ptr [r8]
0x18000c4a3  test    r9w, r9w
0x18000c4a7  jz      short loc_18000C4BE
0x18000c4a9  mov     [rdx], r9w
0x18000c4ad  add     r8, 2
0x18000c4b1  add     rdx, 2
0x18000c4b5  dec     rcx
0x18000c4b8  sub     rax, 1
0x18000c4bc  jnz     short loc_18000C49A
0x18000c4be  test    rax, rax
0x18000c4c1  lea     rcx, [rdx-2]
0x18000c4c5  cmovnz  rcx, rdx
0x18000c4c9  mov     [rcx], r10w
0x18000c4cd  mov     eax, 0FFF8h
0x18000c4d2  add     word ptr [rsp+9F0h+hMem], ax
0x18000c4d7  xor     r12d, r12d
0x18000c4da  mov     rcx, [rbp+8F0h+SourceString.Buffer]
0x18000c4de  cmp     dword ptr [r14+28h], 40000018h
0x18000c4e6  jz      short loc_18000C521
0x18000c4e8  cmp     dword ptr [r14+28h], 0C000021Dh
0x18000c4f0  jz      short loc_18000C521
0x18000c4f2  cmp     dword ptr [r14+28h], 0C00002D1h
0x18000c4fa  jz      short loc_18000C521
0x18000c4fc  mov     qword ptr [rbp+rdi*8+8F0h+MessageId], rcx
0x18000c501  cmp     ebx, 5
0x18000c504  jnb     short loc_18000C50E
0x18000c506  mov     dword ptr [rbp+rdi*4+8F0h+var_898], 1
0x18000c50e  lea     rcx, [rsp+9F0h+hMem]; UnicodeString
0x18000c513  call    cs:__imp_RtlFreeUnicodeString
0x18000c51a  nop     dword ptr [rax+rax+00h]
0x18000c51f  jmp     short loc_18000C548
0x18000c521  mov     rax, [rsp+9F0h+hMem+8]
0x18000c526  mov     qword ptr [rbp+rdi*8+8F0h+MessageId], rax
0x18000c52b  cmp     ebx, 5
0x18000c52e  jnb     short loc_18000C538
0x18000c530  mov     dword ptr [rbp+rdi*4+8F0h+var_898], 2
0x18000c538  lea     rcx, [rbp+8F0h+SourceString]; AnsiString
  ... truncated ...
```
