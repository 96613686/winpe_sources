# InternetQueryOptionA

- ea: `0x180003c40`
- end: `0x1800062b8`
- name: `InternetQueryOptionA`
- size: `9848`
- prototype: `BOOL __stdcall(HINTERNET hInternet, DWORD dwOption, LPVOID lpBuffer, LPDWORD lpdwBufferLength)`
- caller_count: `4`
- callee_count: `46`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003110`
- `0x1800d6f14`
- `0x180174810`
- `0x180188150`

## callees

- `0x180003074`
- `0x180003c40`
- `0x1800062c0`
- `0x180009cf0`
- `0x180035fcc`
- `0x18003a870`
- `0x18004e0f0`
- `0x180060d30`
- `0x180060f00`
- `0x1800641c0`
- `0x180064560`
- `0x18007ad20`
- `0x1800c13c0`
- `0x1800c2d90`
- `0x1800c9f5c`
- `0x1800d2e04`
- `0x1800e08a0`
- `0x1800f4ac8`
- `0x180103b58`
- `0x18010bd8c`
- `0x180116a98`
- `0x18011cd4c`
- `0x180122d98`
- `0x180125474`
- `0x180133504`
- `0x180135214`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x180154882`
- `0x18015c52c`
- `0x18015cb4c`
- `0x180166d0c`
- `0x180166de4`
- `0x180166e10`
- `0x18017afac`
- `0x18017b730`
- `0x18017c250`
- `0x18017c504`
- `0x18017cf48`
- `0x180190c1c`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e490c`
- `0x1801ea568`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000444e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000444e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004926`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000424b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000424b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004372`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ed3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004372`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ed3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000400a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004332`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000400a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004332`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000404a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000404a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004052`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004052`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c28`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003d43`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003d43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800054f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005509`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000551b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800054f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005509`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000551b`
- `ntdll!EtwEventActivityIdControl` at `0x180003e66`
- `ntdll!EtwEventActivityIdControl` at `0x180003ea6`
- `ntdll!EtwEventActivityIdControl` at `0x180004294`
- `ntdll!EtwEventActivityIdControl` at `0x180003e66`
- `ntdll!EtwEventActivityIdControl` at `0x180003ea6`
- `ntdll!EtwEventActivityIdControl` at `0x180004294`
- `ntdll!RtlGetLastNtStatus` at `0x18000401b`
- `ntdll!RtlGetLastNtStatus` at `0x180004343`
- `ntdll!RtlGetLastNtStatus` at `0x18000401b`
- `ntdll!RtlGetLastNtStatus` at `0x180004343`
- `CRYPT32!CertFreeCertificateContext` at `0x180005450`
- `CRYPT32!CertFreeCertificateContext` at `0x180005655`
- `CRYPT32!CertFreeCertificateContext` at `0x1800056e9`
- `CRYPT32!CertFreeCertificateContext` at `0x180005774`
- `CRYPT32!CertFreeCertificateContext` at `0x180005450`
- `CRYPT32!CertFreeCertificateContext` at `0x180005655`
- `CRYPT32!CertFreeCertificateContext` at `0x1800056e9`
- `CRYPT32!CertFreeCertificateContext` at `0x180005774`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall InternetQueryOptionA(HINTERNET hInternet, DWORD dwOption, LPVOID lpBuffer, LPDWORD lpdwBufferLength)
{
  LPVOID v4; // rsi
  LPDWORD v5; // rbx
  DWORD v6; // r14d
  HINTERNET v7; // r9
  DWORD LastError; // eax
  DWORD v9; // edi
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 *p_TimeoutValue; // rdi
  __int64 v13; // rdx
  HTTP_REQUEST_HANDLE_OBJECT *v14; // rbx
  DWORD v15; // eax
  HTTP_REQUEST_HANDLE_OBJECT *v16; // r13
  DWORD IsValid; // esi
  char *v18; // rbx
  __int64 v19; // rcx
  __int128 *v20; // rax
  __int128 *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int128 *v24; // rax
  int v25; // eax
  bool v26; // sf
  int v27; // eax
  bool v28; // sf
  HTTP_REQUEST_HANDLE_OBJECT *v29; // rbx
  BOOL v30; // r15d
  int v31; // r12d
  __int64 v32; // rbx
  signed __int32 v33; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  LPDWORD v36; // rax
  DWORD v37; // ebx
  int v38; // eax
  unsigned int v39; // ebx
  __int64 v40; // r8
  __int64 v41; // r9
  unsigned int v42; // r14d
  DWORD v43; // eax
  DWORD v44; // edi
  int v45; // eax
  bool v46; // sf
  __int64 v48; // rbx
  __int64 v49; // rbx
  int v50; // r14d
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rcx
  signed int v54; // eax
  bool v55; // sf
  SECURITY_CACHE_LIST_ENTRY *v56; // rcx
  const struct _CERT_CHAIN_CONTEXT *v57; // rcx
  __int64 v58; // rax
  LPVOID v59; // rdx
  char *v60; // r8
  DWORD v61; // ecx
  int v62; // eax
  HTTP_REQUEST_HANDLE_OBJECT **v63; // rax
  __int64 v64; // rax
  int v65; // ecx
  __int64 v66; // r9
  DWORD CurrentThreadId; // eax
  __int64 v68; // rax
  unsigned int v69; // eax
  __int64 v70; // rax
  unsigned int v71; // ecx
  __int64 v72; // rax
  __int64 *v73; // rcx
  const char *v74; // rax
  int v75; // ecx
  int v76; // r8d
  int v77; // r9d
  __int64 ThreadInfo; // rax
  int v79; // edx
  int v80; // edx
  int v81; // edx
  bool v82; // zf
  int v83; // edx
  int v84; // edx
  int v85; // esi
  int v86; // r8d
  __int64 v87; // rax
  unsigned __int64 v88; // rdx
  __int64 v89; // rax
  __int64 *v90; // rcx
  __int64 v91; // rbx
  unsigned int SecurityInfo; // eax
  __int64 v93; // rdx
  __int128 v94; // xmm0
  __int128 v95; // xmm1
  char *v96; // rcx
  SecPkgContext_CipherInfo *p_cipherInfo; // rax
  __int128 v98; // xmm0
  __int128 v99; // xmm1
  __int128 v100; // xmm0
  __int128 v101; // xmm1
  __int128 v102; // xmm0
  __int128 v103; // xmm1
  __int128 v104; // xmm0
  __int128 v105; // xmm1
  __int128 v106; // xmm0
  __int128 v107; // xmm1
  __int64 v108; // rax
  _DWORD *v109; // r10
  struct IProxyResolver *v110; // rcx
  int SessionProxySettings; // eax
  __int64 v112; // rcx
  int v113; // eax
  __int64 v114; // rcx
  int v115; // eax
  __int64 v116; // rcx
  _BOOL8 v117; // r14
  int v118; // r8d
  BOOL v119; // edx
  int v120; // edx
  int v121; // edx
  int v122; // edx
  int v123; // edx
  int v124; // edx
  int v125; // edx
  int v126; // edx
  int v127; // edx
  int v128; // edx
  int v129; // edx
  int v130; // r10d
  __int64 v131; // r11
  __int64 v132; // rcx
  __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rax
  DWORD Size; // [rsp+58h] [rbp-B0h]
  int Sizea; // [rsp+58h] [rbp-B0h]
  LPVOID lpMem[13]; // [rsp+70h] [rbp-98h] BYREF
  struct INTERNET_SECURITY_INFO v141; // [rsp+D8h] [rbp-30h] BYREF
  HTTP_REQUEST_HANDLE_OBJECT *v142; // [rsp+3D8h] [rbp+2D0h] BYREF
  __int64 v143; // [rsp+3E0h] [rbp+2D8h] BYREF
  _BYTE v144[16]; // [rsp+3E8h] [rbp+2E0h] BYREF
  HLOCAL hMem; // [rsp+3F8h] [rbp+2F0h]
  HLOCAL v146; // [rsp+400h] [rbp+2F8h]
  unsigned int TimeoutValue; // [rsp+428h] [rbp+320h] BYREF
  int IsPartialResponseCacheable; // [rsp+42Ch] [rbp+324h] BYREF
  unsigned int v149; // [rsp+430h] [rbp+328h] BYREF
  unsigned __int16 v150[2]; // [rsp+434h] [rbp+32Ch] BYREF
  char *v151[2]; // [rsp+438h] [rbp+330h] BYREF
  const struct _CERT_CHAIN_CONTEXT *v152; // [rsp+448h] [rbp+340h] BYREF
  int v153[2]; // [rsp+450h] [rbp+348h] BYREF
  int v154; // [rsp+458h] [rbp+350h] BYREF
  int v155[2]; // [rsp+460h] [rbp+358h] BYREF
  __int128 v156; // [rsp+468h] [rbp+360h] BYREF
  int v157; // [rsp+478h] [rbp+370h]
  __int64 v158; // [rsp+480h] [rbp+378h] BYREF
  __int128 v159; // [rsp+488h] [rbp+380h] BYREF
  __int128 v160; // [rsp+498h] [rbp+390h] BYREF
  __int64 v161; // [rsp+4A8h] [rbp+3A0h]
  __int128 v162; // [rsp+4B8h] [rbp+3B0h] BYREF
  _UNKNOWN *retaddr; // [rsp+520h] [rbp+418h]

  v4 = lpBuffer;
  v5 = lpdwBufferLength;
  v6 = dwOption;
  v7 = hInternet;
  *(_DWORD *)v150 = dwOption;
  v142 = (HTTP_REQUEST_HANDLE_OBJECT *)hInternet;
  if ( (xmmword_180266B60 & 4) != 0 )
  {
    v74 = InternetMapOption(dwOption);
    WPP_SF_qsdqqd(v75, 10, v76, v77, (__int64)v74, v6, (__int64)v4, (__int64)v5, v76);
  }
  Size = 0;
  TimeoutValue = 0;
  v161 = 0;
  v157 = 0;
  v160 = 0;
  v158 = 0;
  v156 = 0;
  IsPartialResponseCacheable = 0;
  v152 = 0;
  v143 = 0;
  memset(lpMem, 0, sizeof(lpMem));
  InternetSaveThreadInfo(&lpMem[1], *(_QWORD *)&dwOption, lpBuffer, v7);
  if ( !GlobalDataInitialized )
  {
    IsValid = GlobalDataInitialize();
    if ( IsValid )
      goto LABEL_86;
    v4 = lpBuffer;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( qword_180269EA8 && LastError && LastError != 997 && LastError != 12150 && LastError != 12028 && LastError != 122 )
  {
    v32 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
    GetSystemTimeAsFileTime((LPFILETIME)(v32 + qword_180269EA8));
    *(_DWORD *)(v32 + qword_180269EA8 + 8) = v9;
    *(_DWORD *)(v32 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
    v5 = lpdwBufferLength;
  }
  *(_QWORD *)v153 = TlsGetValue(InternetTlsIndex);
  if ( !*(_QWORD *)v153 )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(1037, 22, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, CurrentThreadId);
    }
    *(_QWORD *)v153 = InternetCreateThreadInfo(1);
    if ( !*(_QWORD *)v153 && (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      WPP_SF_(1037, 23, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids);
      SetLastError(v9);
      goto LABEL_196;
    }
  }
  SetLastError(v9);
  v11 = *(_QWORD *)v153;
  if ( *(_QWORD *)v153 )
  {
    p_TimeoutValue = 0;
    if ( !v5 )
    {
      IsValid = 87;
      goto LABEL_86;
    }
    v13 = 0;
    v149 = 0;
    if ( !v4 )
      *v5 = 0;
    v14 = v142;
    *(_QWORD *)v155 = v142;
    if ( v142 )
    {
      v15 = MapHandleToAddress(v142, &v142, 0);
      v16 = v142;
      IsValid = v15;
      if ( v15 )
        goto LABEL_48;
      v18 = (char *)v142 + 164;
      v19 = 16;
      v20 = &v156;
      do
      {
        *(_BYTE *)v20 = 0;
        v20 = (__int128 *)((char *)v20 + 1);
        --v19;
      }
      while ( v19 );
      v157 = 0;
      v21 = &v156;
      v159 = 0;
      v22 = 16;
      v162 = 0;
      do
      {
        *(_BYTE *)v21 = 0;
        v21 = (__int128 *)((char *)v21 + 1);
        --v22;
      }
      while ( v22 );
      *(_OWORD *)v151 = 0;
      v23 = 16;
      v24 = &v162;
      do
      {
        *(_BYTE *)v24 = 0;
        v24 = (__int128 *)((char *)v24 + 1);
        --v23;
      }
      while ( v23 );
      v25 = EtwEventActivityIdControl(1, v151);
      v26 = v25 < 0;
      if ( v25 > 0 )
        v26 = 1;
      if ( v26 )
        HIDWORD(v151[0]) = 128;
      else
        v162 = *(_OWORD *)v151;
      if ( v16 == (HTTP_REQUEST_HANDLE_OBJECT *)-164LL )
      {
        v33 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
        TickCount = GetTickCount();
        CurrentProcessId = GetCurrentProcessId();
        *(_QWORD *)&v159 = __PAIR64__(v33, (unsigned int)retaddr);
        p_TimeoutValue = 0;
        *((_QWORD *)&v159 + 1) = __PAIR64__(CurrentProcessId, TickCount);
        v18 = (char *)&v159;
      }
      HIDWORD(v151[0]) = 0;
      v27 = EtwEventActivityIdControl(2, v18);
      v28 = v27 < 0;
      if ( v27 > 0 )
        v28 = 1;
      if ( v28 )
        HIDWORD(v151[0]) = 144;
      v29 = v142;
      v156 = v162;
      v157 = 1;
      IsValid = HANDLE_OBJECT::IsValid(v142, 1684826455);
      v13 = IsValid ? v149 : (*(unsigned int (__fastcall **)(HTTP_REQUEST_HANDLE_OBJECT *))(*(_QWORD *)v29 + 32LL))(v29);
      if ( IsValid )
        goto LABEL_48;
      v14 = v142;
      v11 = *(_QWORD *)v153;
    }
    else
    {
      v16 = 0;
      if ( v6 != 24 && v6 != 15 && !(unsigned int)IsPerProcessOption(v6) )
      {
        if ( v6 - 1 > 0xC0 )
          IsValid = 12009;
        else
          IsValid = 12018;
        *lpdwBufferLength = 0;
        goto LABEL_86;
      }
      IsValid = 0;
    }
    if ( v6 != 75 )
    {
      v30 = 0;
      v31 = 0;
      switch ( v6 )
      {
        case 0x3Bu:
          p_TimeoutValue = &HttpVersionInfo;
LABEL_116:
          Size = 8;
          break;
        case 0x17u:
          Size = 4;
          if ( (_DWORD)v13 == 1852785480
            || (_DWORD)v13 == 1852785478
            || (_DWORD)v13 == 1952804425
            || (_DWORD)v13 == 1718374984 )
          {
            goto LABEL_175;
          }
          TimeoutValue = 0;
          v38 = 0;
          if ( *((_DWORD *)v16 + 198) )
          {
            v38 = 1;
            TimeoutValue = 1;
            if ( *((_DWORD *)v16 + 241) )
            {
              v38 = 129;
              TimeoutValue = 129;
            }
          }
          if ( (_DWORD)v13 == 1902465608 && *((_DWORD *)v16 + 198) && *((_DWORD *)v16 + 1259) )
          {
            v38 |= 0x100u;
            TimeoutValue = v38;
          }
          if ( *((_DWORD *)v16 + 239) )
          {
            v38 |= 4u;
            TimeoutValue = v38;
          }
          if ( *((_DWORD *)v16 + 240) )
          {
            v38 |= 8u;
            TimeoutValue = v38;
          }
          if ( *((_DWORD *)v16 + 199) )
            TimeoutValue = v38 | 0x40;
          p_TimeoutValue = (__int64 *)&TimeoutValue;
          break;
        case 0x9Cu:
          Size = 256;
          if ( *lpdwBufferLength >= 0x100 )
          {
            IsValid = 12018;
            if ( (_DWORD)v13 == 1852785480 )
            {
              v49 = *((_QWORD *)v16 + 122);
              if ( v49 )
              {
                v50 = 0;
                if ( v49 != -440 )
                {
                  EnterCriticalSection((LPCRITICAL_SECTION)(v49 + 440));
                  v50 = 1;
                }
                v51 = *(_QWORD *)(v49 + 536);
                if ( v51 && *(int *)(v49 + 504) > 0 )
                {
                  IsValid = 0;
                  memcpy_0(
                    lpBuffer,
                    *(const void **)(v51 + 48LL * *(int *)(v49 + 500)),
                    *(int *)(v51 + 48LL * *(int *)(v49 + 500) + 8));
                  memcpy_0(
                    (char *)lpBuffer + 128,
                    *(const void **)(*(_QWORD *)(v49 + 536) + 48LL * *(int *)(v49 + 500) + 16),
                    *(int *)(*(_QWORD *)(v49 + 536) + 48LL * *(int *)(v49 + 500) + 24));
                }
                else
                {
                  IsValid = 12007;
                }
                if ( v50 && v49 != -440 )
                  LeaveCriticalSection((LPCRITICAL_SECTION)(v49 + 440));
                v36 = lpdwBufferLength;
                LODWORD(p_TimeoutValue) = 0;
                v37 = 256;
              }
              else
              {
                v36 = lpdwBufferLength;
                IsValid = 12016;
                v37 = 256;
              }
            }
            else
            {
LABEL_160:
              v36 = lpdwBufferLength;
              v37 = Size;
            }
            goto LABEL_70;
          }
          IsValid = 12010;
          goto LABEL_133;
        case 0x78u:
          Size = 256;
          if ( *lpdwBufferLength < 0x100 )
          {
            v36 = lpdwBufferLength;
            IsValid = 12010;
            v37 = 256;
            goto LABEL_70;
          }
          if ( (_DWORD)v13 == 1902465608 )
          {
            v52 = *((_QWORD *)v16 + 150);
            if ( !v52 )
            {
              IsValid = 12019;
LABEL_133:
              v36 = lpdwBufferLength;
              v37 = 256;
              goto LABEL_70;
            }
            v59 = lpBuffer;
            v60 = (char *)lpBuffer + 128;
LABEL_157:
            IsValid = (*(__int64 (__fastcall **)(__int64, LPVOID, char *))(*(_QWORD *)v52 + 184LL))(v52, v59, v60);
            goto LABEL_133;
          }
          if ( (_DWORD)v13 == 1852330839 )
          {
            v52 = *((_QWORD *)v16 + 128);
            if ( !v52 )
            {
              IsValid = 12019;
              goto LABEL_133;
            }
            v59 = lpBuffer;
            v60 = (char *)lpBuffer + 128;
            goto LABEL_157;
          }
LABEL_175:
          v36 = lpdwBufferLength;
          IsValid = 12018;
          v37 = Size;
LABEL_70:
          *v36 = v37;
          if ( v16 )
          {
LABEL_71:
            if ( (BYTE2(xmmword_180266B60) & 2) != 0 )
              WPP_SF_q(1041, 30, WPP_dddf2698fa6139794d752a52a3642573_Traceguids, v16);
            v39 = HANDLE_OBJECT::IsValid(v16, 1684826455);
            if ( !v39 )
            {
              if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
                WPP_SF_q(1032, 24, WPP_a85fccec657a30c16cbc767298893445_Traceguids, *((_QWORD *)v16 + 16));
              v41 = *((_QWORD *)v16 + 16);
              LOBYTE(p_TimeoutValue) = _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 35, 0xFFFFFFFF) == 1;
              if ( (BYTE2(xmmword_180266B60) & 0x20) != 0 )
                WPP_SF_qqD(1045, 25, (unsigned int)WPP_a85fccec657a30c16cbc767298893445_Traceguids, v41, (__int64)v16);
              if ( (_DWORD)p_TimeoutValue )
                (*(void (__fastcall **)(HTTP_REQUEST_HANDLE_OBJECT *, __int64, __int64, __int64))(*(_QWORD *)v16 + 8LL))(
                  v16,
                  1,
                  v40,
                  v41);
              if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
                WPP_SF_d(1032, 26, WPP_a85fccec657a30c16cbc767298893445_Traceguids, (unsigned int)p_TimeoutValue);
              if ( !(_DWORD)p_TimeoutValue )
                v39 = 12036;
            }
            if ( (BYTE2(xmmword_180266B60) & 2) != 0 )
              WPP_SF_d(1041, 31, WPP_dddf2698fa6139794d752a52a3642573_Traceguids, v39);
          }
          goto LABEL_86;
        default:
          switch ( v6 )
          {
            case 1u:
              Size = 8;
              if ( v14 )
              {
                p_TimeoutValue = (__int64 *)&v152;
                v152 = (const struct _CERT_CHAIN_CONTEXT *)*((_QWORD *)v14 + 68);
                IsValid = 0;
                goto LABEL_63;
              }
              IsValid = 6;
              goto LABEL_180;
            case 2u:
            case 3u:
            case 4u:
            case 5u:
            case 6u:
            case 7u:
            case 8u:
            case 0x3Fu:
              Size = 4;
              ThreadInfo = InternetGetThreadInfo(v10, v13, v11);
              if ( ThreadInfo )
                InternetSetObjectHandle(ThreadInfo, *(_QWORD *)v155, v14);
              TimeoutValue = GetTimeoutValue(v6);
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              goto LABEL_63;
            case 9u:
              Size = 4;
              if ( (int)v13 <= 1818838598 )
              {
                switch ( (_DWORD)v13 )
                {
                  case 0x6C694646:
                    TimeoutValue = 7;
                    goto LABEL_332;
                  case 0x486C4646:
                    TimeoutValue = 8;
                    goto LABEL_332;
                  case 0x486E4646:
                    TimeoutValue = 6;
                    goto LABEL_332;
                  case 0x646E4646:
                    TimeoutValue = 5;
                    goto LABEL_332;
                  case 0x666C5248:
                    TimeoutValue = 14;
                    goto LABEL_332;
                }
LABEL_328:
                IsValid = 12004;
                goto LABEL_332;
              }
              v79 = v13 - 1852785478;
              if ( v79 )
              {
                v80 = v79 - 2;
                if ( v80 )
                {
                  v81 = v80 - 49680128;
                  if ( v81 )
                  {
                    if ( v81 == 50338817 )
                    {
                      TimeoutValue = 1;
                      goto LABEL_332;
                    }
                    goto LABEL_328;
                  }
                  TimeoutValue = 13;
                }
                else
                {
                  TimeoutValue = 4;
                }
              }
              else
              {
                TimeoutValue = 2;
              }
LABEL_332:
              p_TimeoutValue = (__int64 *)&TimeoutValue;
LABEL_179:
              if ( IsValid )
                goto LABEL_180;
              if ( v30 )
              {
LABEL_276:
                if ( p_TimeoutValue )
                {
LABEL_272:
                  v68 = -1;
                  do
                    ++v68;
                  while ( *((_BYTE *)p_TimeoutValue + v68) );
                  Size = v68 + 1;
                }
                else
                {
                  p_TimeoutValue = (__int64 *)qword_180222338;
                  Size = 1;
                }
              }
              goto LABEL_63;
            case 0xAu:
            case 0x2Du:
              Size = 8;
              v62 = RGetContext(v14, &v152, v11);
              p_TimeoutValue = (__int64 *)&v152;
              goto LABEL_178;
            case 0xBu:
            case 0xEu:
            case 0x11u:
            case 0x12u:
            case 0x13u:
            case 0x14u:
            case 0x17u:
            case 0x19u:
            case 0x25u:
            case 0x27u:
            case 0x2Au:
            case 0x2Eu:
            case 0x2Fu:
            case 0x30u:
            case 0x31u:
            case 0x3Bu:
            case 0x3Cu:
            case 0x3Eu:
            case 0x48u:
            case 0x4Bu:
            case 0x4Cu:
            case 0x4Du:
            case 0x4Fu:
            case 0x50u:
            case 0x51u:
            case 0x54u:
            case 0x55u:
            case 0x57u:
            case 0x58u:
            case 0x59u:
            case 0x5Au:
            case 0x5Bu:
            case 0x5Cu:
            case 0x5Du:
            case 0x5Fu:
            case 0x60u:
            case 0x63u:
            case 0x68u:
            case 0x6Au:
            case 0x6Bu:
            case 0x6Cu:
            case 0x6Fu:
            case 0x70u:
            case 0x71u:
            case 0x72u:
            case 0x73u:
            case 0x74u:
            case 0x76u:
            case 0x77u:
            case 0x78u:
            case 0x79u:
            case 0x7Au:
            case 0x7Bu:
            case 0x7Cu:
            case 0x7Du:
            case 0x7Eu:
            case 0x7Fu:
            case 0x80u:
            case 0x82u:
            case 0x83u:
            case 0x84u:
            case 0x85u:
            case 0x86u:
            case 0x87u:
            case 0x88u:
            case 0x89u:
            case 0x8Au:
            case 0x8Cu:
            case 0x8Du:
            case 0x8Eu:
            case 0x91u:
            case 0x92u:
            case 0x94u:
            case 0x96u:
            case 0x98u:
            case 0x9Au:
            case 0x9Cu:
            case 0x9Eu:
            case 0x9Fu:
            case 0xA0u:
            case 0xA1u:
            case 0xA2u:
            case 0xA3u:
            case 0xA4u:
            case 0xA5u:
            case 0xA6u:
            case 0xA7u:
            case 0xA8u:
            case 0xA9u:
            case 0xAAu:
            case 0xABu:
            case 0xACu:
            case 0xADu:
            case 0xAEu:
            case 0xAFu:
            case 0xB0u:
            case 0xB1u:
            case 0xB2u:
            case 0xB3u:
            case 0xB4u:
            case 0xB6u:
            case 0xB8u:
            case 0xB9u:
            case 0xBBu:
            case 0xBCu:
            case 0xBDu:
            case 0xBEu:
              LODWORD(p_TimeoutValue) = 0;
              goto LABEL_580;
            case 0xCu:
            case 0xDu:
              if ( (_DWORD)v13 == 1852330839 )
                goto LABEL_177;
              if ( (int)v13 > 1818838598 )
              {
                v83 = v13 - 1852785478;
                if ( !v83 )
                  goto LABEL_177;
                v84 = v83 - 2;
                if ( !v84 )
                  goto LABEL_177;
                v82 = v84 == 49680128;
              }
              else
              {
                if ( (_DWORD)v13 == 1818838598 || (_DWORD)v13 == 1215055430 || (_DWORD)v13 == 1215186502 )
                  goto LABEL_177;
                v82 = (_DWORD)v13 == 1684948550;
              }
              if ( !v82 )
                goto LABEL_183;
LABEL_177:
              Size = 4;
              v62 = RGetBufferSize(v14, v6, &TimeoutValue);
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              goto LABEL_178;
            case 0xFu:
            case 0x10u:
            case 0x1Au:
            case 0x1Eu:
            case 0x4Eu:
              IsValid = 120;
              goto LABEL_180;
            case 0x15u:
              v63 = (HTTP_REQUEST_HANDLE_OBJECT **)*((_QWORD *)v14 + 14);
              v142 = (HTTP_REQUEST_HANDLE_OBJECT *)v63;
              if ( v63 )
                v142 = v63[16];
              p_TimeoutValue = (__int64 *)&v142;
              Size = 8;
              goto LABEL_63;
            case 0x16u:
              if ( (_DWORD)v13 == 1852785480 )
                Size = 4;
              else
                IsValid = 12018;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              if ( (_DWORD)v13 != 1852785480 )
                p_TimeoutValue = 0;
              goto LABEL_179;
            case 0x18u:
              p_TimeoutValue = (__int64 *)(v11 + 76);
              Size = 4;
              goto LABEL_63;
            case 0x1Bu:
              Size = 8;
              if ( !(unsigned int)FValidCacheHandleType((unsigned int)v13) )
                goto LABEL_183;
              p_TimeoutValue = &v143;
              IsValid = 122;
              if ( !*((_DWORD *)v16 + 178) )
                IsValid = 1;
              goto LABEL_179;
            case 0x1Cu:
              v31 = 1;
              LODWORD(p_TimeoutValue) = 0;
              v85 = 1;
              v86 = 0;
              goto LABEL_366;
            case 0x1Du:
              LODWORD(p_TimeoutValue) = 0;
              v31 = 1;
              v86 = 0;
              goto LABEL_365;
            case 0x1Fu:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              TimeoutValue = 0;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              v66 = *((_QWORD *)v14 + 666);
              Size = 4;
              if ( v66 )
                v66 = *(unsigned int *)(v66 + 824);
              TimeoutValue = v66;
              if ( (xmmword_180266B60 & 0x40) != 0 )
                WPP_SF_d(1030, 12, WPP_707ecc95fad83ef15080a28830e142a1_Traceguids, v66);
              IsValid = 0;
              goto LABEL_63;
            case 0x20u:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              memset_0(&v141, 0, sizeof(v141));
              Size = 64;
              if ( HTTP_REQUEST_HANDLE_OBJECT::GetSecurityInfo(v14, &v141) )
                goto LABEL_420;
              IsValid = ConvertSecurityInfoIntoCertInfoStruct(&v141, lpBuffer, lpdwBufferLength);
              if ( v141.pCertificate )
                CertFreeCertificateContext(v141.pCertificate);
              goto LABEL_180;
            case 0x21u:
              if ( (_DWORD)v13 == 1902465608
                || (_DWORD)v13 == 1684948550
                || (_DWORD)v13 == 1215186502
                || (_DWORD)v13 == 1818838598
                || (_DWORD)v13 == 1215055430 )
              {
                IsValid = INTERNET_CONNECT_HANDLE_OBJECT::GetDataFileNameA(v16, (char **)lpMem);
                if ( IsValid )
                  goto LABEL_180;
                p_TimeoutValue = (__int64 *)lpMem[0];
              }
              else
              {
                if ( (_DWORD)v13 != 1718374984 )
                  goto LABEL_183;
                p_TimeoutValue = (__int64 *)*((_QWORD *)v16 + 80);
              }
              if ( !p_TimeoutValue )
              {
                IsValid = 12028;
                goto LABEL_180;
              }
              v30 = 1;
              goto LABEL_272;
            case 0x22u:
              if ( (_DWORD)v13 != 1902465608
                && (_DWORD)v13 != 1684948550
                && (_DWORD)v13 != 1215186502
                && (_DWORD)v13 != 1818838598
                && (_DWORD)v13 != 1215055430 )
              {
                goto LABEL_183;
              }
              v87 = 680;
              if ( !*((_QWORD *)v16 + 86) )
                v87 = 672;
              p_TimeoutValue = *(__int64 **)((char *)v16 + v87);
              v30 = 1;
              goto LABEL_276;
            case 0x23u:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              memset_0(&v141, 0, sizeof(v141));
              memset_0(v144, 0, 0x40u);
              v149 = 64;
              if ( HTTP_REQUEST_HANDLE_OBJECT::GetSecurityInfo(v14, &v141) )
                goto LABEL_420;
              IsValid = ConvertSecurityInfoIntoCertInfoStruct(&v141, v144, &v149);
              if ( v141.pCertificate )
                CertFreeCertificateContext(v141.pCertificate);
              if ( IsValid )
                goto LABEL_180;
              p_TimeoutValue = (__int64 *)FormatCertInfo(v144);
              if ( !p_TimeoutValue )
              {
                Sizea = 0;
                IsValid = 12016;
                goto LABEL_411;
              }
              v88 = *lpdwBufferLength;
              if ( v88 > 0x7FFFFFFF )
                goto LABEL_418;
              v89 = (unsigned int)v88;
              v90 = p_TimeoutValue;
              if ( !*lpdwBufferLength )
                goto LABEL_405;
              while ( *(_BYTE *)v90 )
              {
                v90 = (__int64 *)((char *)v90 + 1);
                if ( !--v89 )
                {
LABEL_405:
                  v91 = 0;
                  goto LABEL_406;
                }
              }
              v91 = (unsigned int)v88 - v89;
LABEL_406:
              if ( v89 )
              {
                Sizea = v91 + 1;
                if ( v88 >= v91 + 1 )
                {
                  if ( lpBuffer )
                  {
                    memcpy_0(lpBuffer, p_TimeoutValue, v91 + 1);
                    Sizea = v91;
                  }
LABEL_410:
                  LocalFree(p_TimeoutValue);
                  LODWORD(p_TimeoutValue) = 0;
LABEL_411:
                  if ( hMem )
                    LocalFree(hMem);
                  if ( v146 )
                    LocalFree(v146);
                  v36 = lpdwBufferLength;
                  v37 = Sizea;
                  goto LABEL_70;
                }
                Sizea = v91 + 1;
              }
              else
              {
LABEL_418:
                Sizea = 1;
              }
              IsValid = 122;
              goto LABEL_410;
            case 0x24u:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              memset_0(&v141, 0, sizeof(v141));
              LODWORD(p_TimeoutValue) = 0;
              Size = 4;
              TimeoutValue = 0;
              if ( HTTP_REQUEST_HANDLE_OBJECT::GetSecurityInfo(v14, &v141) )
                goto LABEL_159;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              TimeoutValue = v141.connectionInfo.dwCipherStrength;
              CertFreeCertificateContext(v141.pCertificate);
              if ( (xmmword_180266B60 & 0x40) != 0 )
                WPP_SF_d(1030, 13, WPP_707ecc95fad83ef15080a28830e142a1_Traceguids, TimeoutValue);
              goto LABEL_63;
            case 0x26u:
              LODWORD(p_TimeoutValue) = 0;
              IsValid = 0;
              if ( v14 )
              {
                if ( (_DWORD)v13 != 1952804425 )
                  goto LABEL_175;
                SessionProxySettings = INTERNET_HANDLE_OBJECT::LegacyGetSessionProxySettings(
                                         v14,
                                         lpBuffer,
                                         lpdwBufferLength);
              }
              else
              {
                v110 = GlobalProxyInfo;
                if ( GlobalProxyInfo )
                {
                  FixProxySettingsForCurrentConnection(0, 0);
                  v110 = GlobalProxyInfo;
                }
                SessionProxySettings = LegacyGetProxySettings(v110, lpBuffer, lpdwBufferLength);
              }
              if ( SessionProxySettings < 0 )
                IsValid = WX_WIN32_FROM_HR((unsigned int)SessionProxySettings);
LABEL_168:
              v36 = lpdwBufferLength;
              v37 = *lpdwBufferLength;
              goto LABEL_70;
            case 0x28u:
              p_TimeoutValue = &InternetVersionInfo;
              goto LABEL_116;
            case 0x29u:
              if ( (_DWORD)v13 != 1952804425 )
                goto LABEL_183;
              if ( *((_DWORD *)v14 + 70) )
                p_TimeoutValue = (__int64 *)*((_QWORD *)v14 + 34);
              else
                p_TimeoutValue = 0;
              v30 = 1;
              goto LABEL_276;
            case 0x2Bu:
              v31 = 1;
              LODWORD(p_TimeoutValue) = 0;
              v85 = 1;
              v86 = 1;
              goto LABEL_366;
            case 0x2Cu:
              v31 = 1;
              LODWORD(p_TimeoutValue) = 0;
              v86 = 1;
LABEL_365:
              v85 = 0;
LABEL_366:
              if ( !v14 || (_DWORD)v13 == 1952804425 || (_DWORD)v13 == 1718374984 )
              {
                v36 = lpdwBufferLength;
                IsValid = 12018;
                v37 = 0;
                goto LABEL_70;
              }
              p_TimeoutValue = (__int64 *)INTERNET_CONNECT_HANDLE_OBJECT::GetUserOrPass(v16, v85, v86);
              v30 = 1;
              if ( !p_TimeoutValue || v85 )
                v31 = 0;
              IsValid = 0;
              goto LABEL_276;
            case 0x32u:
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              TimeoutValue = 1;
              goto LABEL_63;
            case 0x33u:
              TimeoutValue = 0;
              Size = 4;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              goto LABEL_63;
            case 0x34u:
              TimeoutValue = 0;
              Size = 4;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              goto LABEL_63;
            case 0x35u:
              if ( (_DWORD)v13 == 1902465608 )
                p_TimeoutValue = (__int64 *)*((_QWORD *)v14 + 86);
              else
                IsValid = 12018;
              v30 = v13 == 1902465608;
              goto LABEL_179;
            case 0x36u:
            case 0x37u:
            case 0x38u:
            case 0x39u:
            case 0x46u:
              IsValid = 50;
              goto LABEL_180;
            case 0x3Au:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              TimeoutValue = *((_DWORD *)v14 + 286);
              goto LABEL_63;
            case 0x3Du:
              goto LABEL_63;
            case 0x40u:
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              TimeoutValue = GlobalBypassEditedEntry;
              goto LABEL_63;
            case 0x41u:
              if ( !v14 || (_DWORD)v13 != 1902465608 && (_DWORD)v13 != 1852785480 && (_DWORD)v13 != 1952804425 )
                goto LABEL_183;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              TimeoutValue = *((_DWORD *)v14 + 135);
              goto LABEL_63;
            case 0x42u:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              if ( *lpdwBufferLength < 0x2CC )
              {
                Size = 716;
                IsValid = 122;
                goto LABEL_180;
              }
              memset_0(&v141, 0, sizeof(v141));
              SecurityInfo = HTTP_REQUEST_HANDLE_OBJECT::GetSecurityInfo(v14, &v141);
              IsValid = SecurityInfo;
              if ( SecurityInfo )
              {
                v109 = lpBuffer;
                LODWORD(p_TimeoutValue) = 0;
                if ( SecurityInfo == 12004 )
                {
                  IsValid = 0;
                  *((_DWORD *)lpBuffer + 1) = 0;
                }
              }
              else
              {
                v93 = 5;
                v94 = *(_OWORD *)&v141.connectionInfo.dwProtocol;
                v95 = *(_OWORD *)&v141.connectionInfo.aiHash;
                *((_DWORD *)lpBuffer + 1) = 1;
                v96 = (char *)lpBuffer + 36;
                *(_OWORD *)((char *)lpBuffer + 8) = v94;
                *(_OWORD *)((char *)lpBuffer + 20) = v95;
                p_cipherInfo = &v141.cipherInfo;
                do
                {
                  v96 += 128;
                  v98 = *(_OWORD *)&p_cipherInfo->dwVersion;
                  v99 = *(_OWORD *)p_cipherInfo->szCipherSuite;
                  p_cipherInfo = (SecPkgContext_CipherInfo *)((char *)p_cipherInfo + 128);
                  *((_OWORD *)v96 - 8) = v98;
                  v100 = *(_OWORD *)&p_cipherInfo[-1].szCertificate[18];
                  *((_OWORD *)v96 - 7) = v99;
                  v101 = *(_OWORD *)&p_cipherInfo[-1].szCertificate[26];
                  *((_OWORD *)v96 - 6) = v100;
                  v102 = *(_OWORD *)&p_cipherInfo[-1].szCertificate[34];
                  *((_OWORD *)v96 - 5) = v101;
                  v103 = *(_OWORD *)&p_cipherInfo[-1].szCertificate[42];
                  *((_OWORD *)v96 - 4) = v102;
                  v104 = *(_OWORD *)&p_cipherInfo[-1].szCertificate[50];
                  *((_OWORD *)v96 - 3) = v103;
                  v105 = *(_OWORD *)&p_cipherInfo[-1].szCertificate[58];
                  *((_OWORD *)v96 - 2) = v104;
                  *((_OWORD *)v96 - 1) = v105;
                  --v93;
                }
                while ( v93 );
                v106 = *(_OWORD *)&p_cipherInfo->dwVersion;
                v107 = *(_OWORD *)p_cipherInfo->szCipherSuite;
                v108 = *(_QWORD *)&p_cipherInfo->szCipherSuite[8];
                *(_OWORD *)v96 = v106;
                *((_OWORD *)v96 + 1) = v107;
                *((_QWORD *)v96 + 4) = v108;
                if ( v141.pCertificate )
                  CertFreeCertificateContext(v141.pCertificate);
                v109 = lpBuffer;
                LODWORD(p_TimeoutValue) = 0;
              }
              v36 = lpdwBufferLength;
              v37 = 716;
              *v109 = 716;
              goto LABEL_70;
            case 0x43u:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              Size = 24;
              p_TimeoutValue = (__int64 *)&v160;
              *(_QWORD *)&v160 = HTTP_REQUEST_HANDLE_OBJECT::GetSocket(v14);
              v112 = *((_QWORD *)v14 + 150);
              if ( v112 )
                v113 = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)v112 + 176LL))(v112);
              else
                v113 = 0;
              DWORD2(v160) = v113;
              v114 = *((_QWORD *)v14 + 150);
              if ( v114 )
                v115 = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)v114 + 168LL))(v114);
              else
                v115 = 0;
              HIDWORD(v160) = v115;
              v116 = *((_QWORD *)v14 + 150);
              v117 = *((_DWORD *)v14 + 304) != 0;
              if ( v116 )
                v118 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v116 + 152LL))(v116);
              else
                v118 = 0;
              v119 = v117
                   | (v118 != 0 ? 2 : 0)
                   | (*((_DWORD *)v14 + 1288) != 0 ? 4 : 0)
                   | (*((_DWORD *)v14 + 1319) >> 6) & 8;
              v6 = *(_DWORD *)v150;
              LODWORD(v161) = v119;
              goto LABEL_63;
            case 0x44u:
              if ( (_DWORD)v13 == 1852330839 || (_DWORD)v13 == 1952804425 )
                goto LABEL_293;
              if ( (int)v13 <= 1818838598 )
              {
                if ( (_DWORD)v13 != 1818838598
                  && (_DWORD)v13 != 1215055430
                  && (_DWORD)v13 != 1215186502
                  && (_DWORD)v13 != 1684948550 )
                {
                  goto LABEL_183;
                }
LABEL_293:
                v69 = *((_DWORD *)v14 + 102);
                goto LABEL_280;
              }
              v120 = v13 - 1852785478;
              if ( !v120 )
                goto LABEL_293;
              v121 = v120 - 2;
              if ( !v121 || v121 == 49680128 )
                goto LABEL_293;
              goto LABEL_183;
            case 0x45u:
              v36 = lpdwBufferLength;
              LODWORD(p_TimeoutValue) = 0;
              if ( (_DWORD)v13 == 1902465608 )
              {
                if ( *lpdwBufferLength == 16 )
                {
                  v153[0] = 0;
                  v155[0] = 0;
                  v154 = 0;
                  HTTP_REQUEST_HANDLE_OBJECT::GetTimeStampsForCache(
                    v14,
                    (struct _FILETIME *)lpBuffer,
                    (struct _FILETIME *)lpBuffer + 1,
                    v153,
                    v155,
                    &v154);
                  v36 = lpdwBufferLength;
                  v37 = 0;
                }
                else
                {
                  v37 = 0;
                  IsValid = 12010;
                }
              }
              else
              {
                v37 = 0;
                IsValid = 12018;
              }
              goto LABEL_70;
            case 0x47u:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              TimeoutValue = AuthSuppressRequestEntity(v14) == 0;
              goto LABEL_63;
            case 0x49u:
              TimeoutValue = 0;
              Size = 4;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              if ( !v14 )
              {
                TimeoutValue = GlobalMaxConnectionsPerServer;
                goto LABEL_63;
              }
              if ( (_DWORD)v13 == 1852785480 )
              {
                v58 = *((_QWORD *)v14 + 122);
                if ( v58 )
                {
                  TimeoutValue = *(_DWORD *)(v58 + 384);
                  goto LABEL_63;
                }
              }
LABEL_420:
              IsValid = 12016;
              goto LABEL_180;
            case 0x4Au:
              if ( v14 )
                goto LABEL_420;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              TimeoutValue = GlobalMaxConnectionsPer1_0Server;
              goto LABEL_63;
            case 0x52u:
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              TimeoutValue = 1;
              goto LABEL_63;
            case 0x53u:
              if ( lpBuffer && *lpdwBufferLength )
                *(_BYTE *)lpBuffer = 0;
              IsValid = 0;
              v30 = 1;
              p_TimeoutValue = (__int64 *)lpBuffer;
              goto LABEL_276;
            case 0x56u:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              TimeoutValue = *((_DWORD *)v14 + 1336);
              goto LABEL_63;
            case 0x5Eu:
              Size = 4;
              if ( *lpdwBufferLength < 4 )
              {
                IsValid = 12010;
                goto LABEL_180;
              }
              if ( (_DWORD)v13 != 1852330839 )
                goto LABEL_183;
              v133 = *((_QWORD *)v16 + 128);
              if ( v133 )
                IsValid = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID))(*(_QWORD *)v133 + 592LL))(
                            v133,
                            4097,
                            lpBuffer);
              else
                IsValid = 12019;
              goto LABEL_180;
            case 0x61u:
              if ( (((_DWORD)v13 - 1852785478) & 0xFFFFFFFD) != 0 )
                goto LABEL_183;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              TimeoutValue = *((_DWORD *)v14 + 117);
              goto LABEL_63;
            case 0x62u:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              Size = 4;
              v70 = *((_QWORD *)v16 + 666);
              if ( v70 )
                v71 = *(_DWORD *)(v70 + 824);
              else
                v71 = 0;
              TimeoutValue = v71;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              goto LABEL_63;
            case 0x64u:
              if ( (_DWORD)v13 == 1852330839 || (_DWORD)v13 == 1952804425 )
                goto LABEL_279;
              if ( (int)v13 <= 1818838598 )
              {
                if ( (_DWORD)v13 != 1818838598
                  && (_DWORD)v13 != 1215055430
                  && (_DWORD)v13 != 1215186502
                  && (_DWORD)v13 != 1684948550 )
                {
                  goto LABEL_183;
                }
LABEL_279:
                v69 = *((_DWORD *)v14 + 103);
                goto LABEL_280;
              }
              v122 = v13 - 1852785478;
              if ( !v122 )
                goto LABEL_279;
              v123 = v122 - 2;
              if ( !v123 || v123 == 49680128 )
                goto LABEL_279;
              goto LABEL_183;
            case 0x65u:
              if ( (_DWORD)v13 == 1852330839 || (_DWORD)v13 == 1952804425 )
                goto LABEL_295;
              if ( (int)v13 <= 1818838598 )
              {
                if ( (_DWORD)v13 != 1818838598
                  && (_DWORD)v13 != 1215055430
                  && (_DWORD)v13 != 1215186502
                  && (_DWORD)v13 != 1684948550 )
                {
                  goto LABEL_183;
                }
LABEL_295:
                v69 = *((_DWORD *)v14 + 104);
                goto LABEL_280;
              }
              v124 = v13 - 1852785478;
              if ( !v124 )
                goto LABEL_295;
              v125 = v124 - 2;
              if ( !v125 || v125 == 49680128 )
                goto LABEL_295;
              goto LABEL_183;
            case 0x66u:
              if ( (_DWORD)v13 == 1852330839 || (_DWORD)v13 == 1952804425 )
                goto LABEL_299;
              if ( (int)v13 > 1818838598 )
              {
                v128 = v13 - 1852785478;
                if ( v128 )
                {
                  v129 = v128 - 2;
                  if ( v129 )
                  {
                    if ( v129 != 49680128 )
                      goto LABEL_183;
                  }
                }
              }
              else if ( (_DWORD)v13 != 1818838598
                     && (_DWORD)v13 != 1215055430
                     && (_DWORD)v13 != 1215186502
                     && (_DWORD)v13 != 1684948550 )
              {
                goto LABEL_183;
              }
LABEL_299:
              v69 = *((_DWORD *)v14 + 106);
LABEL_280:
              TimeoutValue = v69;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              Size = 4;
              goto LABEL_63;
            case 0x67u:
              LODWORD(p_TimeoutValue) = 0;
              Size = 4;
              TimeoutValue = 0;
              if ( v14 )
              {
LABEL_159:
                IsValid = 12016;
                goto LABEL_160;
              }
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              TimeoutValue = GlobalMaxConnectionsPerProxy;
              goto LABEL_63;
            case 0x69u:
              Size = 8;
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              if ( *lpdwBufferLength < 8 )
              {
                IsValid = 122;
                goto LABEL_180;
              }
              v56 = (SECURITY_CACHE_LIST_ENTRY *)*((_QWORD *)v14 + 666);
              LODWORD(p_TimeoutValue) = 0;
              if ( !v56 )
                goto LABEL_201;
              IsValid = 0;
              v57 = SECURITY_CACHE_LIST_ENTRY::DuplicateCertChain(v56);
              if ( !v57 )
              {
                v57 = SECURITY_CACHE_LIST_ENTRY::DuplicateUnverifiedCertChain(*((SECURITY_CACHE_LIST_ENTRY **)v14 + 666));
                if ( !v57 )
                  IsValid = 12019;
              }
              if ( !IsValid )
              {
                v152 = v57;
                p_TimeoutValue = (__int64 *)&v152;
                goto LABEL_63;
              }
              goto LABEL_160;
            case 0x6Du:
              v36 = lpdwBufferLength;
              Size = 104;
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_518;
              if ( *lpdwBufferLength < 0x68 )
              {
LABEL_564:
                IsValid = 12010;
                goto LABEL_181;
              }
              if ( !*((_DWORD *)v16 + 239) )
              {
                v37 = 104;
                IsValid = 12028;
                goto LABEL_69;
              }
              v151[0] = 0;
              v150[0] = 0;
              v149 = -1;
              HTTP_REQUEST_HANDLE_OBJECT::GetProxyName(v14, (const char **)v151, v150, (enum ProxyResolveScheme *)&v149);
              if ( !v151[0] || !*v151[0] || !v150[0] || !lpBuffer || *(_DWORD *)lpBuffer < 0x68u )
              {
                IsValid = 4317;
                goto LABEL_180;
              }
              v130 = StringCchCopyA(*((char **)lpBuffer + 3), *((unsigned int *)lpBuffer + 8), v151[0]);
              if ( v130 >= 0 )
              {
                *(_WORD *)(v131 + 36) = v150[0];
                *(_DWORD *)(v131 + 20) = v149;
                goto LABEL_180;
              }
              v62 = 122;
              if ( v130 != -2147024774 )
                v62 = 87;
LABEL_178:
              IsValid = v62;
              goto LABEL_179;
            case 0x6Eu:
              Size = 4;
              v36 = lpdwBufferLength;
              if ( *lpdwBufferLength < 4 )
                goto LABEL_564;
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_518;
              p_TimeoutValue = (__int64 *)&IsPartialResponseCacheable;
              IsPartialResponseCacheable = *((_DWORD *)v16 + 1361);
              goto LABEL_63;
            case 0x75u:
              Size = 4;
              v36 = lpdwBufferLength;
              if ( *lpdwBufferLength < 4 )
                goto LABEL_564;
              if ( (_DWORD)v13 != 1902465608 )
              {
LABEL_518:
                IsValid = 12018;
                goto LABEL_181;
              }
              if ( !*((_DWORD *)v16 + 1224) )
              {
                v37 = 4;
                IsValid = 12019;
                goto LABEL_69;
              }
              IsPartialResponseCacheable = HTTP_REQUEST_HANDLE_OBJECT::IsPartialResponseCacheable(v16);
              p_TimeoutValue = (__int64 *)&IsPartialResponseCacheable;
              goto LABEL_63;
            case 0x81u:
              Size = 4;
              if ( *lpdwBufferLength < 4 )
              {
                IsValid = 12010;
                goto LABEL_180;
              }
              if ( (_DWORD)v13 != 1852330839 )
                goto LABEL_183;
              v132 = *((_QWORD *)v16 + 128);
              if ( v132 )
                IsValid = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64))(*(_QWORD *)v132 + 568LL))(
                            v132,
                            lpBuffer,
                            v11);
              else
                IsValid = 12019;
              goto LABEL_180;
            case 0x8Bu:
              LODWORD(p_TimeoutValue) = 0;
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_175;
              v61 = 0;
              if ( *((_DWORD *)v16 + 1248) && *((_QWORD *)v16 + 625) && *((_DWORD *)v16 + 178) )
                v61 = *((_DWORD *)v16 + 1248);
              if ( lpBuffer && *lpdwBufferLength >= v61 )
              {
                IsValid = 0;
                *lpdwBufferLength = v61;
                memcpy_0(lpBuffer, *((const void **)v16 + 625), v61);
              }
              else
              {
                *lpdwBufferLength = v61;
                IsValid = 122;
              }
              goto LABEL_168;
            case 0x8Fu:
            case 0x90u:
              LODWORD(p_TimeoutValue) = 0;
              TimeoutValue = 0;
              if ( (_DWORD)v13 != 1902465608 )
              {
                v36 = lpdwBufferLength;
                IsValid = 12018;
                v37 = 0;
                goto LABEL_70;
              }
              TimeoutValue = 6;
              v134 = 5224;
              if ( v6 != 144 )
                v134 = 5232;
              v135 = *(_QWORD *)((char *)v16 + v134);
              if ( !v135 )
              {
LABEL_201:
                v36 = lpdwBufferLength;
                IsValid = 12019;
                v37 = Size;
                goto LABEL_70;
              }
              TimeoutValue = *(_DWORD *)(*(_QWORD *)(v135 + 24) + 24LL);
              IsValid = 0;
              Size = 4;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              goto LABEL_63;
            case 0x93u:
              Size = 8;
              IsValid = 12018;
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_180;
              if ( (*((_DWORD *)v16 + 1291) & 0x4000) == 0 )
                goto LABEL_180;
              v158 = *((_QWORD *)v16 + 618);
              if ( !v158 )
                goto LABEL_180;
              p_TimeoutValue = &v158;
              IsValid = 0;
              goto LABEL_63;
            case 0x95u:
              Size = 4;
              if ( *lpdwBufferLength < 4 )
              {
                v36 = lpdwBufferLength;
                IsValid = 12010;
                v37 = 4;
                goto LABEL_69;
              }
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              TimeoutValue = *((_DWORD *)v16 + 1432);
              IsValid = 0;
              goto LABEL_63;
            case 0x97u:
              Size = 4;
              if ( *lpdwBufferLength < 4 )
              {
                IsValid = 12010;
                goto LABEL_180;
              }
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              v64 = *((_QWORD *)v16 + 666);
              v65 = 0;
              if ( v64 )
                v65 = *(_DWORD *)(v64 + 828);
              IsPartialResponseCacheable = v65;
              p_TimeoutValue = (__int64 *)&IsPartialResponseCacheable;
              IsValid = 0;
              goto LABEL_63;
            case 0x99u:
              Size = 8;
              if ( *lpdwBufferLength < 8 )
              {
                IsValid = 12010;
                goto LABEL_180;
              }
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              IsValid = HTTP_REQUEST_HANDLE_OBJECT::GetIssuerListCopy(
                          v16,
                          (struct _SecPkgContext_IssuerListInfoEx **)lpBuffer);
              goto LABEL_180;
            case 0x9Bu:
              if ( (_DWORD)v13 == 1852330839 || (_DWORD)v13 == 1952804425 )
                goto LABEL_297;
              if ( (int)v13 > 1818838598 )
              {
                v126 = v13 - 1852785478;
                if ( v126 )
                {
                  v127 = v126 - 2;
                  if ( v127 )
                  {
                    if ( v127 != 49680128 )
                    {
LABEL_183:
                      IsValid = 12018;
LABEL_180:
                      v36 = lpdwBufferLength;
LABEL_181:
                      v37 = Size;
                      goto LABEL_69;
                    }
                  }
                }
              }
              else if ( (_DWORD)v13 != 1818838598
                     && (_DWORD)v13 != 1215055430
                     && (_DWORD)v13 != 1215186502
                     && (_DWORD)v13 != 1684948550 )
              {
                goto LABEL_183;
              }
LABEL_297:
              p_TimeoutValue = (__int64 *)&IsPartialResponseCacheable;
              IsPartialResponseCacheable = *((_DWORD *)v14 + 105);
              Size = 4;
              goto LABEL_63;
            case 0x9Du:
              Size = 4;
              v36 = lpdwBufferLength;
              if ( *lpdwBufferLength < 4 )
                goto LABEL_564;
              if ( (_DWORD)v13 != 1952804425 && (_DWORD)v13 != 1852785480 && (_DWORD)v13 != 1902465608 )
              {
                IsValid = 12018;
                goto LABEL_181;
              }
              TimeoutValue = (*(__int64 (__fastcall **)(HTTP_REQUEST_HANDLE_OBJECT *, __int64, __int64))(*(_QWORD *)v16 + 176LL))(
                               v16,
                               v13,
                               v11);
              p_TimeoutValue = (__int64 *)&TimeoutValue;
              goto LABEL_63;
            case 0xB5u:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              LODWORD(p_TimeoutValue) = 0;
              if ( !v16 )
              {
                IsValid = 12016;
                *lpdwBufferLength = 0;
                goto LABEL_86;
              }
              v53 = *((_QWORD *)v16 + 150);
              HIDWORD(v151[0]) = 0;
              if ( v53 )
              {
                v54 = (*(__int64 (__fastcall **)(__int64, LPVOID, LPDWORD))(*(_QWORD *)v53 + 328LL))(
                        v53,
                        lpBuffer,
                        lpdwBufferLength);
                v55 = v54 < 0;
                if ( v54 > 0 )
                {
                  v54 = (unsigned __int16)v54 | 0x80070000;
                  v55 = v54 < 0;
                }
                if ( v55 )
                  HIDWORD(v151[0]) = 1352;
              }
              else
              {
                v54 = -2147012880;
                HIDWORD(v151[0]) = 1351;
              }
              IsValid = WX_WIN32_FROM_HR((unsigned int)v54);
              *lpdwBufferLength = *lpdwBufferLength;
              goto LABEL_71;
            case 0xB7u:
              Size = 4;
              if ( *lpdwBufferLength < 4 )
              {
                IsValid = 12010;
                goto LABEL_180;
              }
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              IsValid = HTTP_REQUEST_HANDLE_OBJECT::GetSelectedAuthScheme(v16, (unsigned int *)lpBuffer);
              goto LABEL_180;
            case 0xBAu:
              if ( (_DWORD)v13 != 1902465608 )
                goto LABEL_183;
              IsValid = HTTP_REQUEST_HANDLE_OBJECT::GetRequestTimes(v16, lpBuffer, lpdwBufferLength);
              v36 = lpdwBufferLength;
              v37 = *lpdwBufferLength;
              goto LABEL_69;
            case 0xBFu:
              Size = 4;
              v36 = lpdwBufferLength;
              if ( *lpdwBufferLength >= 4 )
              {
                if ( (_DWORD)v13 == 1902465608 )
                  HTTP_REQUEST_HANDLE_OBJECT::IsHttp09(v16, (int *)lpBuffer);
                else
                  IsValid = 12018;
              }
              else
              {
                IsValid = 12010;
              }
              goto LABEL_181;
            case 0xC0u:
              Size = 8;
              if ( *lpdwBufferLength < 8 )
              {
                v36 = lpdwBufferLength;
                IsValid = 12010;
                v37 = 8;
                goto LABEL_69;
              }
              if ( (_DWORD)v13 != 1902465608 && (_DWORD)v13 != 1952804425 && (_DWORD)v13 != 1852785480 )
                goto LABEL_183;
              LODWORD(p_TimeoutValue) = 0;
              IsValid = 0;
              v37 = 8;
              *(_QWORD *)lpBuffer = *((_QWORD *)v16 + 77);
              v36 = lpdwBufferLength;
              goto LABEL_70;
            default:
LABEL_580:
              v36 = lpdwBufferLength;
              IsValid = 87;
              v37 = 0;
              goto LABEL_70;
          }
      }
LABEL_63:
      v36 = lpdwBufferLength;
      v37 = Size;
      if ( *lpdwBufferLength >= Size && lpBuffer )
      {
        memcpy_0(lpBuffer, p_TimeoutValue, Size);
        v36 = lpdwBufferLength;
        if ( v30 )
          v37 = Size - 1;
      }
      else
      {
        IsValid = 122;
      }
      if ( (v6 == 29 || v6 == 44) && v31 )
      {
        v72 = v37;
        v73 = p_TimeoutValue;
        if ( v37 )
        {
          do
          {
            *(_BYTE *)v73 = 0;
            v73 = (__int64 *)((char *)v73 + 1);
            --v72;
          }
          while ( v72 );
        }
        HeapFree(g_hWxProcessHeap, 0, p_TimeoutValue);
        v36 = lpdwBufferLength;
      }
LABEL_69:
      LODWORD(p_TimeoutValue) = 0;
      goto LABEL_70;
    }
    if ( lpBuffer )
    {
      if ( *lpdwBufferLength < 0x20 )
      {
        v36 = lpdwBufferLength;
        IsValid = 12010;
        v37 = 0;
      }
      else
      {
        if ( (_DWORD)v13 != 1952804425 )
        {
          v14 = 0;
          v142 = 0;
        }
        IsValid = QueryPerConnOptions(v14, (struct INTERNET_PER_CONN_OPTION_LISTA *)lpBuffer);
        v36 = lpdwBufferLength;
        v37 = *lpdwBufferLength;
      }
      goto LABEL_70;
    }
    IsValid = 87;
LABEL_48:
    v36 = lpdwBufferLength;
    v37 = 0;
    goto LABEL_70;
  }
LABEL_196:
  if ( (xmmword_180266B50 & 0x40) != 0 )
    WPP_SF_(518, 11, WPP_707ecc95fad83ef15080a28830e142a1_Traceguids);
  IsValid = 12004;
LABEL_86:
  if ( lpMem[0] )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(lpMem[0]);
    else
      HeapFree(g_hWxProcessHeap, 0, lpMem[0]);
  }
  if ( IsValid )
  {
    if ( (xmmword_180266B50 & 4) != 0 )
      WPP_SF_d(514, 16, WPP_707ecc95fad83ef15080a28830e142a1_Traceguids, IsValid);
    v42 = 0;
  }
  else
  {
    v42 = 1;
  }
  if ( (xmmword_180266B60 & 4) != 0 )
    WPP_SF_d(1026, 18, WPP_707ecc95fad83ef15080a28830e142a1_Traceguids, v42);
  v43 = GetLastError();
  v44 = v43;
  if ( qword_180269EA8 && v43 && v43 != 997 && v43 != 12150 && v43 != 12028 && v43 != 122 )
  {
    v48 = 16LL * (unsigned __int8)_InterlockedIncrement(&dword_180269EA4);
    GetSystemTimeAsFileTime((LPFILETIME)(v48 + qword_180269EA8));
    *(_DWORD *)(v48 + qword_180269EA8 + 8) = v44;
    *(_DWORD *)(v48 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
  }
  if ( v157 )
  {
    HIDWORD(v151[0]) = 0;
    v45 = EtwEventActivityIdControl(2, &v156);
    v46 = v45 < 0;
    if ( v45 > 0 )
      v46 = 1;
    if ( v46 )
      HIDWORD(v151[0]) = 144;
  }
  SetLastError(v44);
  InternetRestoreThreadInfo(&lpMem[1]);
  SetLastError(IsValid);
  return v42;
}

```

## disassembly

```asm
0x180003c40  mov     r11, rsp
0x180003c43  push    rbp
0x180003c44  push    rsi
0x180003c45  push    rdi
0x180003c46  push    r14
0x180003c48  lea     rbp, [r11-418h]
0x180003c4f  sub     rsp, 4F8h
0x180003c56  mov     rax, cs:__security_cookie
0x180003c5d  xor     rax, rsp
0x180003c60  mov     [rbp+410h+var_50], rax
0x180003c67  mov     [r11-28h], rbx
0x180003c6b  mov     rsi, r8
0x180003c6e  mov     rbx, r9
0x180003c71  mov     [r11-30h], r12
0x180003c75  mov     [rsp+510h+var_4B8], rbx
0x180003c7a  mov     r14d, edx
0x180003c7d  mov     [rsp+510h+var_4B0], r8
0x180003c82  mov     r9, rcx
0x180003c85  mov     dword ptr [rbp+410h+var_E4], edx
0x180003c8b  mov     [rbp+410h+var_140], rcx
0x180003c92  xor     edi, edi
0x180003c94  test    byte ptr cs:xmmword_180266B60, 4
0x180003c9b  jnz     loc_180004F56
0x180003ca1  xorps   xmm0, xmm0
0x180003ca4  mov     dword ptr [rsp+510h+Size], edi
0x180003ca8  xor     eax, eax
0x180003caa  mov     [rbp+410h+var_F0], edi
0x180003cb0  xorps   xmm1, xmm1
0x180003cb3  mov     [rbp+410h+var_70], rax
0x180003cba  lea     rcx, [rsp+510h+lpMem+8]
0x180003cbf  mov     [rbp+410h+var_A0], eax
0x180003cc5  movups  [rbp+410h+var_80], xmm0
0x180003ccc  mov     [rbp+410h+var_98], rdi
0x180003cd3  movups  [rbp+410h+var_B0], xmm1
0x180003cda  mov     [rbp+410h+var_EC], edi
0x180003ce0  movups  xmmword ptr [rsp+510h+lpMem+8], xmm0
0x180003ce5  mov     [rbp+410h+var_D0], rdi
0x180003cec  movups  [rbp+410h+var_490], xmm0
0x180003cf0  mov     [rbp+410h+var_138], rdi
0x180003cf7  movups  [rbp+410h+var_480], xmm0
0x180003cfb  mov     [rsp+510h+lpMem], rdi
0x180003d00  movups  [rbp+410h+var_470], xmm0
0x180003d04  movups  [rbp+410h+var_460], xmm0
0x180003d08  movups  [rbp+410h+var_450], xmm0
0x180003d0c  call    InternetSaveThreadInfo
0x180003d11  cmp     cs:GlobalDataInitialized, edi
0x180003d17  mov     r12d, 1
0x180003d1d  jz      loc_180004995
0x180003d23  call    cs:__imp_GetLastError
0x180003d29  cmp     cs:qword_180269EA8, 0
0x180003d31  mov     edi, eax
0x180003d33  jz      short loc_180003D3D
0x180003d35  test    eax, eax
0x180003d37  jnz     loc_180003FBF
0x180003d3d  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x180003d43  call    cs:__imp_TlsGetValue
0x180003d49  mov     qword ptr [rbp+410h+var_C8], rax
0x180003d50  test    rax, rax
0x180003d53  jz      loc_1800048DC
0x180003d59  mov     ecx, edi; dwErrCode
0x180003d5b  call    cs:__imp_SetLastError
0x180003d61  mov     r8, qword ptr [rbp+410h+var_C8]
0x180003d68  test    r8, r8
0x180003d6b  jz      loc_18000492C
0x180003d71  xor     edi, edi
0x180003d73  test    rbx, rbx
0x180003d76  jz      loc_180004B99
0x180003d7c  mov     [rsp+510h+var_38], r15
0x180003d84  mov     edx, edi
0x180003d86  mov     [rbp+410h+var_E8], edx
0x180003d8c  test    rsi, rsi
0x180003d8f  jnz     short loc_180003D93
0x180003d91  mov     [rbx], edi
0x180003d93  mov     rbx, [rbp+410h+var_140]
0x180003d9a  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180003da1  mov     [rsp+510h+var_30], r13
0x180003da9  mov     qword ptr [rbp+410h+var_B8], rbx
0x180003db0  test    rbx, rbx
0x180003db3  jz      loc_1800043C4
0x180003db9  xor     r8d, r8d
0x180003dbc  lea     rdx, [rbp+410h+var_140]
0x180003dc3  mov     rcx, rbx
0x180003dc6  call    MapHandleToAddress
0x180003dcb  mov     r13, [rbp+410h+var_140]
0x180003dd2  mov     esi, eax
0x180003dd4  test    eax, eax
0x180003dd6  jnz     loc_180004083
0x180003ddc  lea     rbx, [r13+0A4h]
0x180003de3  mov     ecx, 10h
0x180003de8  lea     rax, [rbp+410h+var_B0]
0x180003def  nop
0x180003df0  mov     [rax], dil
0x180003df3  lea     rax, [rax+1]
0x180003df7  sub     rcx, r12
0x180003dfa  jnz     short loc_180003DF0
0x180003dfc  xorps   xmm0, xmm0
0x180003dff  mov     [rbp+410h+var_A0], edi
0x180003e05  xorps   xmm1, xmm1
0x180003e08  lea     rax, [rbp+410h+var_B0]
0x180003e0f  movups  [rbp+410h+var_90], xmm0
0x180003e16  mov     ecx, 10h
0x180003e1b  movups  [rbp+410h+var_60], xmm1
0x180003e22  mov     [rax], dil
0x180003e25  lea     rax, [rax+1]
0x180003e29  sub     rcx, r12
0x180003e2c  jnz     short loc_180003E22
0x180003e2e  xorps   xmm0, xmm0
0x180003e31  mov     dword ptr [rbp+410h+var_E0+4], edi
0x180003e37  movups  xmmword ptr [rbp+330h], xmm0
0x180003e3e  mov     ecx, 10h
0x180003e43  lea     rax, [rbp+410h+var_60]
0x180003e4a  nop     word ptr [rax+rax+00h]
0x180003e50  mov     [rax], dil
0x180003e53  lea     rax, [rax+1]
0x180003e57  sub     rcx, r12
0x180003e5a  jnz     short loc_180003E50
0x180003e5c  lea     rdx, [rbp+410h+var_E0]
0x180003e63  mov     ecx, r12d
0x180003e66  call    cs:__imp_EtwEventActivityIdControl
0x180003e6c  test    eax, eax
0x180003e6e  jle     short loc_180003E7A
0x180003e70  movzx   eax, ax
0x180003e73  or      eax, 80070000h
0x180003e78  test    eax, eax
0x180003e7a  js      loc_180004F93
0x180003e80  movaps  xmm0, xmmword ptr [rbp+410h+var_E0]
0x180003e87  movdqa  [rbp+410h+var_60], xmm0
0x180003e8f  test    rbx, rbx
0x180003e92  jz      loc_180004036
0x180003e98  mov     rdx, rbx
0x180003e9b  mov     dword ptr [rbp+410h+var_E0+4], edi
0x180003ea1  mov     ecx, 2
0x180003ea6  call    cs:__imp_EtwEventActivityIdControl
0x180003eac  test    eax, eax
0x180003eae  jle     short loc_180003EBA
0x180003eb0  movzx   eax, ax
0x180003eb3  or      eax, 80070000h
0x180003eb8  test    eax, eax
0x180003eba  js      loc_180004FA2
0x180003ec0  mov     rbx, [rbp+410h+var_140]
0x180003ec7  mov     edx, 646C6957h
0x180003ecc  movaps  xmm0, [rbp+410h+var_60]
0x180003ed3  mov     rcx, rbx
0x180003ed6  movups  [rbp+410h+var_B0], xmm0
0x180003edd  mov     [rbp+410h+var_A0], r12d
0x180003ee4  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x180003ee9  mov     esi, eax
0x180003eeb  test    eax, eax
0x180003eed  jnz     loc_180004FB1
0x180003ef3  mov     rax, [rbx]
0x180003ef6  mov     rcx, rbx
0x180003ef9  mov     rax, [rax+20h]
0x180003efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f02  mov     edx, eax
0x180003f04  test    esi, esi
0x180003f06  jnz     loc_180004083
0x180003f0c  mov     rbx, [rbp+410h+var_140]
0x180003f13  mov     r8, qword ptr [rbp+410h+var_C8]
0x180003f1a  cmp     r14d, 4Bh ; 'K'
0x180003f1e  jz      loc_18000437D
0x180003f24  mov     r15d, edi
0x180003f27  mov     r12d, edi
0x180003f2a  cmp     r14d, 3Bh ; ';'
0x180003f2e  jz      loc_1800043EA
0x180003f34  cmp     r14d, 17h
0x180003f38  jz      loc_180004092
0x180003f3e  cmp     r14d, 9Ch
0x180003f45  jz      loc_1800043FE
0x180003f4b  cmp     r14d, 78h ; 'x'
0x180003f4f  jz      loc_1800044EF
0x180003f55  lea     eax, [r14-1]; switch 192 cases
0x180003f59  cmp     eax, 0BFh
0x180003f5e  ja      def_180003F7F; jumptable 0000000180003F7F default case
0x180003f64  lea     r9, __ImageBase
0x180003f6b  movzx   eax, ds:(byte_1800061F8 - 180000000h)[r9+rax]
0x180003f74  mov     ecx, ds:(jpt_180003F7F - 180000000h)[r9+rax*4]
0x180003f7c  add     rcx, r9
0x180003f7f  jmp     rcx; switch jump
0x180003f81  mov     rsi, [rsp+510h+var_4B8]; jumptable 0000000180003F7F case 149
0x180003f86  mov     eax, 4
0x180003f8b  mov     [rsp+510h+Size], rax
0x180003f90  cmp     [rsi], eax
0x180003f92  jb      loc_180004881
0x180003f98  cmp     edx, 71655248h
0x180003f9e  jnz     loc_18000485D
0x180003fa4  mov     eax, [r13+1660h]
0x180003fab  lea     rdi, [rbp+410h+var_F0]
0x180003fb2  mov     [rbp+410h+var_F0], eax
0x180003fb8  xor     esi, esi
0x180003fba  jmp     loc_18000412E; jumptable 0000000180003F7F case 61
0x180003fbf  cmp     edi, 3E5h
0x180003fc5  jz      loc_180003D3D
0x180003fcb  cmp     edi, 2F76h
0x180003fd1  jz      loc_180003D3D
0x180003fd7  cmp     edi, 2EFCh
0x180003fdd  jz      loc_180003D3D
0x180003fe3  cmp     edi, 7Ah ; 'z'
0x180003fe6  jz      loc_180003D3D
0x180003fec  mov     eax, r12d
0x180003fef  lock xadd cs:dword_180269EA4, eax
0x180003ff7  mov     rcx, cs:qword_180269EA8
0x180003ffe  inc     eax
0x180004000  movzx   ebx, al
0x180004003  shl     rbx, 4
0x180004007  add     rcx, rbx; lpSystemTimeAsFileTime
0x18000400a  call    cs:__imp_GetSystemTimeAsFileTime
0x180004010  mov     rax, cs:qword_180269EA8
0x180004017  mov     [rbx+rax+8], edi
0x18000401b  call    cs:__imp_RtlGetLastNtStatus
0x180004021  mov     rcx, cs:qword_180269EA8
0x180004028  mov     [rbx+rcx+0Ch], eax
0x18000402c  mov     rbx, [rsp+510h+var_4B8]
0x180004031  jmp     loc_180003D3D
0x180004036  mov     rdi, [rbp+418h]
0x18000403d  mov     esi, r12d
0x180004040  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x180004048  inc     esi
0x18000404a  call    cs:__imp_GetTickCount
0x180004050  mov     ebx, eax
0x180004052  call    cs:__imp_GetCurrentProcessId
0x180004058  mov     dword ptr [rbp+410h+var_90], edi
0x18000405e  xor     edi, edi
0x180004060  mov     dword ptr [rbp+410h+var_90+8], ebx
0x180004066  lea     rbx, [rbp+410h+var_90]
0x18000406d  mov     dword ptr [rbp+410h+var_90+0Ch], eax
0x180004073  mov     dword ptr [rbp+410h+var_90+4], esi
0x180004079  jmp     loc_180003E98
0x18000407e  mov     esi, 57h ; 'W'
0x180004083  mov     rax, [rsp+510h+var_4B8]
0x180004088  mov     rbx, [rsp+510h+Size]
0x18000408d  jmp     loc_18000418A
0x180004092  mov     eax, 4
0x180004097  mov     [rsp+510h+Size], rax
0x18000409c  cmp     edx, 6E6F4348h
0x1800040a2  jz      loc_1800047E1
0x1800040a8  cmp     edx, 6E6F4346h
0x1800040ae  jz      loc_1800047E1
0x1800040b4  cmp     edx, 74656E49h
0x1800040ba  jz      loc_1800047E1
0x1800040c0  cmp     edx, 666C5248h
0x1800040c6  jz      loc_1800047E1
0x1800040cc  mov     [rbp+410h+var_F0], edi
0x1800040d2  mov     eax, edi
0x1800040d4  cmp     dword ptr [r13+318h], 0
0x1800040dc  jnz     loc_1800048B3
0x1800040e2  cmp     edx, 71655248h
0x1800040e8  jnz     short loc_1800040F8
0x1800040ea  cmp     dword ptr [r13+318h], 0
0x1800040f2  jnz     loc_180004864
0x1800040f8  cmp     dword ptr [r13+3BCh], 0
0x180004100  jnz     loc_180004B49
0x180004106  cmp     dword ptr [r13+3C0h], 0
0x18000410e  jnz     loc_180006073
0x180004114  cmp     dword ptr [r13+31Ch], 0
0x18000411c  jz      short loc_180004127
0x18000411e  or      eax, 40h
0x180004121  mov     [rbp+410h+var_F0], eax
0x180004127  lea     rdi, [rbp+410h+var_F0]
0x18000412e  mov     rax, [rsp+510h+var_4B8]; jumptable 0000000180003F7F case 61
0x180004133  mov     rbx, [rsp+510h+Size]
0x180004138  cmp     [rax], ebx
0x18000413a  jb      loc_180004538
0x180004140  mov     rcx, [rsp+510h+var_4B0]; void *
0x180004145  test    rcx, rcx
0x180004148  jz      loc_180004538
0x18000414e  mov     r8d, ebx; Size
0x180004151  mov     rdx, rdi; Src
0x180004154  call    memcpy_0
0x180004159  mov     rax, [rsp+510h+var_4B8]
0x18000415e  test    r15d, r15d
0x180004161  jnz     loc_180006081
0x180004167  cmp     r14d, 1Dh
0x18000416b  jz      loc_18000608F
0x180004171  cmp     r14d, 2Ch ; ','
0x180004175  jz      loc_18000608F
0x18000417b  xor     edi, edi
0x18000417d  mov     r12d, 1
0x180004183  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000418a  mov     [rax], ebx
0x18000418c  test    r13, r13
0x18000418f  jz      loc_180004215
0x180004195  test    byte ptr cs:xmmword_180266B60+2, 2
0x18000419c  jnz     loc_180004BEC
0x1800041a2  mov     edx, 646C6957h
0x1800041a7  mov     rcx, r13
0x1800041aa  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x1800041af  mov     ebx, eax
0x1800041b1  test    eax, eax
0x1800041b3  jnz     short loc_180004206
0x1800041b5  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800041bc  jnz     loc_180004C4C
0x1800041c2  mov     r9, [r13+80h]
0x1800041c9  lock xadd [r13+8Ch], r15d
0x1800041d2  add     r15d, 0FFFFFFFFh
0x1800041d6  setz    dil
0x1800041da  test    byte ptr cs:xmmword_180266B60+2, 20h
0x1800041e1  jnz     loc_180004C6E
0x1800041e7  test    edi, edi
0x1800041e9  jnz     loc_180004688
0x1800041ef  test    byte ptr cs:xmmword_180266B60+1, 1
  ... truncated ...
```
