# CSetupFilesCleanup::CleanVolume(_SETUPCLN_PARAMS *)

- ea: `0x1800040c0`
- end: `0x1800047a5`
- name: `?CleanVolume@CSetupFilesCleanup@@QEAAJPEAU_SETUPCLN_PARAMS@@@Z`
- size: `1765`
- prototype: `__int64 __fastcall(CSetupFilesCleanup *__hidden this, struct _SETUPCLN_PARAMS *)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004c70`
- `0x180005080`
- `0x180005c30`

## callees

- `0x180002fe8`
- `0x1800036e8`
- `0x1800040c0`
- `0x1800047ac`
- `0x180006518`
- `0x180006868`
- `0x180007f88`
- `0x18000802c`
- `0x180009528`
- `0x18000a780`
- `0x18000b044`
- `0x18000bb18`
- `0x1800131a2`
- `0x1800131e0`
- `0x180014010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800042ce`
- `msvcrt!wcschr` at `0x1800042ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000422c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000450e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000422c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000450e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004704`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004494`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004588`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004494`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004588`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004596`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004596`
- `WDSCORE!CurrentIP` at `0x1800041a2`
- `WDSCORE!CurrentIP` at `0x180004234`
- `WDSCORE!CurrentIP` at `0x180004348`
- `WDSCORE!CurrentIP` at `0x1800043d1`
- `WDSCORE!CurrentIP` at `0x180004516`
- `WDSCORE!CurrentIP` at `0x1800045f9`
- `WDSCORE!CurrentIP` at `0x180004668`
- `WDSCORE!CurrentIP` at `0x18000470c`
- `WDSCORE!CurrentIP` at `0x1800041a2`
- `WDSCORE!CurrentIP` at `0x180004234`
- `WDSCORE!CurrentIP` at `0x180004348`
- `WDSCORE!CurrentIP` at `0x1800043d1`
- `WDSCORE!CurrentIP` at `0x180004516`
- `WDSCORE!CurrentIP` at `0x1800045f9`
- `WDSCORE!CurrentIP` at `0x180004668`
- `WDSCORE!CurrentIP` at `0x18000470c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004208`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004293`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800043a8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000443a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004576`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800046c7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000476b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004208`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004293`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800043a8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000443a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004576`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800046c7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000476b`
- `ServicingCommon!GetUpdateReserveManagerLoader` at `0x18000418c`
- `ServicingCommon!GetUpdateReserveManagerLoader` at `0x18000421f`
- `ServicingCommon!GetUpdateReserveManagerLoader` at `0x18000418c`
- `ServicingCommon!GetUpdateReserveManagerLoader` at `0x18000421f`

## string_xrefs

- `0x180004162`: `SetupclnPlugin::%s`
- `0x180004216`: `SetupclnPlugin`
- `0x18000423d`: `CSetupFilesCleanup::CleanVolume: Failed to get UpdateReserveManagerLoader from online OS. status: %x`
- `0x1800043dc`: `CSetupFilesCleanup::CleanVolume - Plugin %s not found because well-known directory %s doesn't exist`
- `0x1800044f3`: `Windows.old`
- `0x180004520`: `CSetupFilesCleanup::CleanVolume - Plugin %s not found because Windows.old doesn't exist`

## pseudocode

```c
__int64 __fastcall CSetupFilesCleanup::CleanVolume(CSetupFilesCleanup *this, struct _SETUPCLN_PARAMS *a2)
{
  CSetupFilesCleanup *v3; // r13
  char *v4; // r12
  volatile signed __int64 *v5; // rcx
  int v6; // r14d
  char *v7; // r15
  int v8; // r12d
  int UpdateReserveManagerLoader; // eax
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  int v13; // r15d
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  const wchar_t *v17; // r15
  wchar_t *v18; // rax
  __int64 v19; // r8
  int v20; // r13d
  __int64 v21; // rax
  int v22; // eax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  DWORD v26; // edi
  __int64 v27; // rax
  __int64 v28; // rbx
  struct tagLOG_PARTIAL_MSG *v29; // rax
  __int64 v30; // rax
  void *v31; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v33; // rax
  const wchar_t *v34; // rcx
  void *v35; // r15
  DWORD v36; // edi
  __int64 v37; // rbx
  struct tagLOG_PARTIAL_MSG *v38; // rax
  HANDLE v39; // rax
  int v40; // eax
  int v41; // eax
  __int64 v42; // rax
  DWORD v43; // edi
  __int64 v44; // rbx
  struct tagLOG_PARTIAL_MSG *v45; // rax
  int v46; // r15d
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  int v50; // eax
  DWORD v51; // edi
  __int64 v52; // rbx
  struct tagLOG_PARTIAL_MSG *v53; // rax
  __int64 v55; // [rsp+60h] [rbp-A0h] BYREF
  CSetupFilesCleanup *v56; // [rsp+68h] [rbp-98h]
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  char *v58; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v59; // [rsp+80h] [rbp-80h]
  char v60[144]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v61[264]; // [rsp+120h] [rbp+20h] BYREF

  v56 = this;
  v3 = this;
  memset_0(v61, 0, 0x208u);
  v4 = 0;
  if ( !a2 || !*((_QWORD *)a2 + 2) )
    return 2147942487LL;
  v5 = (volatile signed __int64 *)*((_QWORD *)a2 + 8);
  v6 = 0;
  v7 = 0;
  if ( v5 )
  {
    v7 = v60;
    if ( !TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v5,
            _InterlockedExchangeAdd64(v5 + 17, 0),
            v60) )
      v7 = 0;
  }
  v55 = 0;
  if ( *(_DWORD *)a2 )
  {
    v8 = StringCchPrintfW(v61, 0x104u, L"SetupclnPlugin::%s", *((_QWORD *)v3 + 9));
    if ( v8 < 0 )
    {
      LastError = GetLastError();
      v11 = CurrentIP();
      v12 = ConstructPartialMsgW(
              0x3000000u,
              "CSetupFilesCleanup::CleanVolume: Failed to construct client ID for [%s]. status: %x",
              *((const char **)v3 + 9),
              v8);
      v4 = 0;
      WdsSetupLogMessageW(
        v12,
        0,
        L"D",
        0,
        799,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"CSetupFilesCleanup::CleanVolume",
        v11,
        LastError,
        0,
        0);
      UpdateReserveManagerLoader = GetUpdateReserveManagerLoader(0, L"SetupclnPlugin", v7, &v55);
    }
    else
    {
      UpdateReserveManagerLoader = GetUpdateReserveManagerLoader(0, v61, v7, &v55);
      v4 = 0;
    }
    v13 = UpdateReserveManagerLoader;
    if ( UpdateReserveManagerLoader < 0 )
    {
      v14 = GetLastError();
      v15 = CurrentIP();
      v16 = ConstructPartialMsgW(
              0x3000000u,
              "CSetupFilesCleanup::CleanVolume: Failed to get UpdateReserveManagerLoader from online OS. status: %x",
              v13);
      WdsSetupLogMessageW(
        v16,
        0,
        L"D",
        0,
        805,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"CSetupFilesCleanup::CleanVolume",
        v15,
        v14,
        0,
        0);
      v55 = 0;
    }
  }
  *((_QWORD *)a2 + 9) = v55;
  v17 = (const wchar_t *)*((_QWORD *)v3 + 4);
  if ( v17 )
  {
    while ( *v17 && !**((_DWORD **)a2 + 2) )
    {
      v18 = wcschr(v17, 0x3Bu);
      lpMem = 0;
      v59 = v18;
      v58 = 0;
      if ( v18 )
      {
        v19 = v18 - v17;
      }
      else
      {
        v19 = -1;
        do
          ++v19;
        while ( v17[v19] );
      }
      v20 = StrSubstring(v17, 0, v19, &lpMem);
      if ( v20 >= 0 )
      {
        v21 = BuildPath(*((STRSAFE_PCNZWCH *)v56 + 2), (STRSAFE_PCNZWCH)lpMem);
        v22 = HrPtr<unsigned short>(v21, &v58);
        v4 = v58;
        v20 = v22;
      }
      v23 = GetLastError();
      v24 = CurrentIP();
      v25 = ConstructPartialMsgW(0x4000000u, "CSetupFilesCleanup::CleanVolume - Iterating on: %s", v4);
      WdsSetupLogMessageW(
        v25,
        0,
        L"D",
        0,
        830,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"CSetupFilesCleanup::CleanVolume",
        v24,
        v23,
        0,
        0);
      if ( *((_DWORD *)a2 + 1) )
      {
        if ( !(unsigned int)DirectoryExists(v4) )
        {
          v26 = GetLastError();
          v27 = CurrentIP();
          v3 = v56;
          v28 = v27;
          v29 = ConstructPartialMsgW(
                  0x4000000u,
                  "CSetupFilesCleanup::CleanVolume - Plugin %s not found because well-known directory %s doesn't exist",
                  *((const char **)v56 + 9),
                  v4);
          WdsSetupLogMessageW(
            v29,
            0,
            L"D",
            0,
            840,
            L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
            L"CSetupFilesCleanup::CleanVolume",
            v28,
            v26,
            0,
            0);
          **((_DWORD **)a2 + 1) = 0;
          goto LABEL_29;
        }
      }
      else
      {
        if ( v20 >= 0 )
          v20 = SetupClnEnum(a2, v4);
        if ( v6 >= 0 )
          v6 = v20;
      }
      v3 = v56;
LABEL_29:
      if ( v59 )
      {
        v17 = v59 + 1;
      }
      else
      {
        v30 = -1;
        do
          ++v30;
        while ( v17[v30] );
        v17 += v30;
      }
      v31 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v31);
      }
      if ( v4 )
      {
        v33 = GetProcessHeap();
        HeapFree(v33, 0, v4);
      }
      v4 = 0;
    }
  }
  if ( !**((_DWORD **)a2 + 2) && *((_DWORD *)v3 + 6) )
  {
    v34 = (const wchar_t *)*((_QWORD *)v3 + 2);
    if ( *((_DWORD *)a2 + 1) )
    {
      v35 = (void *)BuildPath(v34, L"Windows.old");
      if ( !(unsigned int)DirectoryExists(v35) )
      {
        v36 = GetLastError();
        v37 = CurrentIP();
        v38 = ConstructPartialMsgW(
                0x4000000u,
                "CSetupFilesCleanup::CleanVolume - Plugin %s not found because Windows.old doesn't exist",
                *((const char **)v3 + 9));
        WdsSetupLogMessageW(
          v38,
          0,
          L"D",
          0,
          870,
          L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
          L"CSetupFilesCleanup::CleanVolume",
          v37,
          v36,
          0,
          0);
        **((_DWORD **)a2 + 1) = 0;
      }
      if ( v35 )
      {
        v39 = GetProcessHeap();
        HeapFree(v39, 0, v35);
      }
    }
    else
    {
      v40 = EnumeratePathEx(v34, 1);
      v41 = HrBool(v40);
      if ( v6 >= 0 )
        v6 = v41;
    }
  }
  if ( v55 )
  {
    if ( *(_DWORD *)a2 )
    {
      v42 = (*(__int64 (**)(void))(*(_QWORD *)v55 + 8LL))();
      if ( v42 )
      {
        v46 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2);
        if ( v46 < 0 )
        {
          v47 = GetLastError();
          v48 = CurrentIP();
          v49 = ConstructPartialMsgW(
                  0x3000000u,
                  "CSetupFilesCleanup::CleanVolume: Failed to Initialize Reserves. status: %x",
                  v46);
          WdsSetupLogMessageW(
            v49,
            0,
            L"D",
            0,
            903,
            L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
            L"CSetupFilesCleanup::CleanVolume",
            v48,
            v47,
            0,
            0);
        }
      }
      else
      {
        v43 = GetLastError();
        v44 = CurrentIP();
        v45 = ConstructPartialMsgW(
                0x3000000u,
                "CSetupFilesCleanup::CleanVolume: Failed to get reserve manager to re-initialize Reserves");
        WdsSetupLogMessageW(
          v45,
          0,
          L"D",
          0,
          896,
          L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
          L"CSetupFilesCleanup::CleanVolume",
          v44,
          v43,
          0,
          0);
      }
    }
    (**(void (__fastcall ***)(__int64))v55)(v55);
    v55 = 0;
    *((_QWORD *)a2 + 9) = 0;
  }
  if ( !**((_DWORD **)a2 + 2) && *((_DWORD *)v3 + 22) )
  {
    v50 = SetupClnDeleteResetLogs(a2);
    if ( v6 >= 0 )
      v6 = v50;
  }
  v51 = GetLastError();
  v52 = CurrentIP();
  v53 = ConstructPartialMsgW(0x4000000u, "CSetupFilesCleanup::CleanVolume - Return status: %x", v6);
  WdsSetupLogMessageW(
    v53,
    0,
    L"D",
    0,
    924,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::CleanVolume",
    v52,
    v51,
    0,
    0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800040c0  mov     [rsp-8+arg_10], rbx
0x1800040c5  push    rbp
0x1800040c6  push    rsi
0x1800040c7  push    rdi
0x1800040c8  push    r12
0x1800040ca  push    r13
0x1800040cc  push    r14
0x1800040ce  push    r15
0x1800040d0  lea     rbp, [rsp-240h]
0x1800040d8  sub     rsp, 340h
0x1800040df  mov     rax, cs:__security_cookie
0x1800040e6  xor     rax, rsp
0x1800040e9  mov     [rbp+270h+var_40], rax
0x1800040f0  mov     rsi, rdx
0x1800040f3  mov     [rsp+370h+var_308], rcx
0x1800040f8  mov     r13, rcx
0x1800040fb  xor     edx, edx; Val
0x1800040fd  lea     rcx, [rbp+270h+var_250]; void *
0x180004101  mov     r8d, 208h; Size
0x180004107  call    memset_0
0x18000410c  xor     r12d, r12d
0x18000410f  test    rsi, rsi
0x180004112  jz      loc_180004776
0x180004118  cmp     [rsi+10h], r12
0x18000411c  jz      loc_180004776
0x180004122  mov     rcx, [rsi+40h]; this
0x180004126  mov     r14d, r12d
0x180004129  mov     r15d, r12d
0x18000412c  test    rcx, rcx
0x18000412f  jz      short loc_180004150
0x180004131  mov     edx, r12d
0x180004134  lock xadd [rcx+88h], rdx; unsigned __int64
0x18000413d  lea     r8, [rbp+270h+var_2E0]; char *
0x180004141  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180004146  test    al, al
0x180004148  lea     r15, [rbp+270h+var_2E0]
0x18000414c  cmovz   r15, r12
0x180004150  mov     [rsp+370h+var_310], r12
0x180004155  cmp     [rsi], r12d
0x180004158  jz      loc_18000429E
0x18000415e  mov     r9, [r13+48h]
0x180004162  lea     r8, aSetupclnplugin; "SetupclnPlugin::%s"
0x180004169  mov     edx, 104h; unsigned __int64
0x18000416e  lea     rcx, [rbp+270h+var_250]; unsigned __int16 *
0x180004172  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004177  xor     ecx, ecx
0x180004179  mov     r12d, eax
0x18000417c  test    eax, eax
0x18000417e  js      short loc_18000419A
0x180004180  lea     r9, [rsp+370h+var_310]
0x180004185  mov     r8, r15
0x180004188  lea     rdx, [rbp+270h+var_250]
0x18000418c  call    cs:__imp_GetUpdateReserveManagerLoader
0x180004192  xor     r12d, r12d
0x180004195  jmp     loc_180004225
0x18000419a  call    cs:__imp_GetLastError
0x1800041a0  mov     edi, eax
0x1800041a2  call    cs:__imp_CurrentIP
0x1800041a8  mov     r8, [r13+48h]
0x1800041ac  lea     rdx, aCsetupfilescle_20; "CSetupFilesCleanup::CleanVolume: Failed"...
0x1800041b3  mov     r9d, r12d
0x1800041b6  mov     ecx, 3000000h; unsigned int
0x1800041bb  mov     rbx, rax
0x1800041be  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800041c3  xor     r12d, r12d
0x1800041c6  lea     rcx, aCsetupfilescle_21; "CSetupFilesCleanup::CleanVolume"
0x1800041cd  mov     [rsp+370h+var_320], r12d
0x1800041d2  lea     r8, aD; "D"
0x1800041d9  mov     [rsp+370h+var_328], r12
0x1800041de  xor     r9d, r9d
0x1800041e1  mov     [rsp+370h+var_330], edi
0x1800041e5  xor     edx, edx
0x1800041e7  mov     [rsp+370h+var_338], rbx
0x1800041ec  mov     [rsp+370h+var_340], rcx
0x1800041f1  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x1800041f8  mov     [rsp+370h+var_348], rcx
0x1800041fd  mov     rcx, rax
0x180004200  mov     [rsp+370h+var_350], 31Fh
0x180004208  call    cs:__imp_WdsSetupLogMessageW
0x18000420e  lea     r9, [rsp+370h+var_310]
0x180004213  mov     r8, r15
0x180004216  lea     rdx, aSetupclnplugin_0; "SetupclnPlugin"
0x18000421d  xor     ecx, ecx
0x18000421f  call    cs:__imp_GetUpdateReserveManagerLoader
0x180004225  mov     r15d, eax
0x180004228  test    eax, eax
0x18000422a  jns     short loc_18000429E
0x18000422c  call    cs:__imp_GetLastError
0x180004232  mov     edi, eax
0x180004234  call    cs:__imp_CurrentIP
0x18000423a  mov     r8d, r15d
0x18000423d  lea     rdx, aCsetupfilescle_11; "CSetupFilesCleanup::CleanVolume: Failed"...
0x180004244  mov     ecx, 3000000h; unsigned int
0x180004249  mov     rbx, rax
0x18000424c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004251  mov     [rsp+370h+var_320], r12d
0x180004256  lea     rcx, aCsetupfilescle_21; "CSetupFilesCleanup::CleanVolume"
0x18000425d  mov     [rsp+370h+var_328], r12
0x180004262  lea     r8, aD; "D"
0x180004269  mov     [rsp+370h+var_330], edi
0x18000426d  xor     r9d, r9d
0x180004270  mov     [rsp+370h+var_338], rbx
0x180004275  xor     edx, edx
0x180004277  mov     [rsp+370h+var_340], rcx
0x18000427c  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180004283  mov     [rsp+370h+var_348], rcx
0x180004288  mov     rcx, rax
0x18000428b  mov     [rsp+370h+var_350], 325h
0x180004293  call    cs:__imp_WdsSetupLogMessageW
0x180004299  mov     [rsp+370h+var_310], r12
0x18000429e  mov     rax, [rsp+370h+var_310]
0x1800042a3  mov     [rsi+48h], rax
0x1800042a7  mov     r15, [r13+20h]
0x1800042ab  test    r15, r15
0x1800042ae  jz      loc_1800044CE
0x1800042b4  jmp     loc_1800044C4
0x1800042b9  mov     rax, [rsi+10h]
0x1800042bd  cmp     [rax], r12d
0x1800042c0  jnz     loc_1800044CE
0x1800042c6  mov     edx, 3Bh ; ';'; Ch
0x1800042cb  mov     rcx, r15; Str
0x1800042ce  call    cs:__imp_wcschr
0x1800042d4  xor     ebx, ebx
0x1800042d6  mov     [rsp+370h+lpMem], r12
0x1800042db  mov     [rbp+270h+var_2F0], rax
0x1800042df  mov     [rsp+370h+var_2F8], r12
0x1800042e4  test    rax, rax
0x1800042e7  jz      short loc_1800042F4
0x1800042e9  mov     r8, rax
0x1800042ec  sub     r8, r15
0x1800042ef  sar     r8, 1
0x1800042f2  jmp     short loc_180004302
0x1800042f4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800042f8  inc     r8
0x1800042fb  cmp     [r15+r8*2], bx
0x180004300  jnz     short loc_1800042F8
0x180004302  lea     r9, [rsp+370h+lpMem]
0x180004307  xor     edx, edx
0x180004309  mov     rcx, r15
0x18000430c  call    StrSubstring
0x180004311  mov     r13d, eax
0x180004314  test    eax, eax
0x180004316  js      short loc_180004340
0x180004318  mov     rcx, [rsp+370h+var_308]
0x18000431d  mov     rdx, [rsp+370h+lpMem]; STRSAFE_PCNZWCH
0x180004322  mov     rcx, [rcx+10h]; pszSrc
0x180004326  call    BuildPath
0x18000432b  mov     rcx, rax
0x18000432e  lea     rdx, [rsp+370h+var_2F8]
0x180004333  call    ??$HrPtr@G@@YAJPEAGAEAPEAG@Z; HrPtr<ushort>(ushort *,ushort * &)
0x180004338  mov     r12, [rsp+370h+var_2F8]
0x18000433d  mov     r13d, eax
0x180004340  call    cs:__imp_GetLastError
0x180004346  mov     edi, eax
0x180004348  call    cs:__imp_CurrentIP
0x18000434e  mov     r8, r12
0x180004351  lea     rdx, aCsetupfilescle_15; "CSetupFilesCleanup::CleanVolume - Itera"...
0x180004358  mov     ecx, 4000000h; unsigned int
0x18000435d  mov     rbx, rax
0x180004360  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004365  xor     ecx, ecx
0x180004367  lea     r8, aD; "D"
0x18000436e  mov     [rsp+370h+var_320], ecx
0x180004372  xor     r9d, r9d
0x180004375  mov     [rsp+370h+var_328], rcx
0x18000437a  xor     edx, edx
0x18000437c  mov     [rsp+370h+var_330], edi
0x180004380  lea     rcx, aCsetupfilescle_21; "CSetupFilesCleanup::CleanVolume"
0x180004387  mov     [rsp+370h+var_338], rbx
0x18000438c  mov     [rsp+370h+var_340], rcx
0x180004391  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180004398  mov     [rsp+370h+var_348], rcx
0x18000439d  mov     rcx, rax
0x1800043a0  mov     [rsp+370h+var_350], 33Eh
0x1800043a8  call    cs:__imp_WdsSetupLogMessageW
0x1800043ae  xor     edi, edi
0x1800043b0  cmp     [rsi+4], edi
0x1800043b3  jz      loc_18000444A
0x1800043b9  mov     rcx, r12
0x1800043bc  call    DirectoryExists
0x1800043c1  test    eax, eax
0x1800043c3  jnz     loc_180004464
0x1800043c9  call    cs:__imp_GetLastError
0x1800043cf  mov     edi, eax
0x1800043d1  call    cs:__imp_CurrentIP
0x1800043d7  mov     r13, [rsp+370h+var_308]
0x1800043dc  lea     rdx, aCsetupfilescle_19; "CSetupFilesCleanup::CleanVolume - Plugi"...
0x1800043e3  mov     r9, r12
0x1800043e6  mov     ecx, 4000000h; unsigned int
0x1800043eb  mov     rbx, rax
0x1800043ee  mov     r8, [r13+48h]
0x1800043f2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800043f7  xor     ecx, ecx
0x1800043f9  lea     r8, aD; "D"
0x180004400  mov     [rsp+370h+var_320], ecx
0x180004404  xor     r9d, r9d
0x180004407  mov     [rsp+370h+var_328], rcx
0x18000440c  xor     edx, edx
0x18000440e  mov     [rsp+370h+var_330], edi
0x180004412  lea     rcx, aCsetupfilescle_21; "CSetupFilesCleanup::CleanVolume"
0x180004419  mov     [rsp+370h+var_338], rbx
0x18000441e  mov     [rsp+370h+var_340], rcx
0x180004423  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x18000442a  mov     [rsp+370h+var_348], rcx
0x18000442f  mov     rcx, rax
0x180004432  mov     [rsp+370h+var_350], 348h
0x18000443a  call    cs:__imp_WdsSetupLogMessageW
0x180004440  mov     rax, [rsi+8]
0x180004444  xor     edi, edi
0x180004446  mov     [rax], edi
0x180004448  jmp     short loc_180004469
0x18000444a  test    r13d, r13d
0x18000444d  js      short loc_18000445D
0x18000444f  mov     rdx, r12
0x180004452  mov     rcx, rsi
0x180004455  call    SetupClnEnum
0x18000445a  mov     r13d, eax
0x18000445d  test    r14d, r14d
0x180004460  cmovns  r14d, r13d
0x180004464  mov     r13, [rsp+370h+var_308]
0x180004469  mov     rax, [rbp+270h+var_2F0]
0x18000446d  test    rax, rax
0x180004470  jnz     short loc_180004486
0x180004472  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004476  inc     rax
0x180004479  cmp     [r15+rax*2], di
0x18000447e  jnz     short loc_180004476
0x180004480  lea     r15, [r15+rax*2]
0x180004484  jmp     short loc_18000448A
0x180004486  lea     r15, [rax+2]
0x18000448a  mov     rbx, [rsp+370h+lpMem]
0x18000448f  test    rbx, rbx
0x180004492  jz      short loc_1800044A8
0x180004494  call    cs:__imp_GetProcessHeap
0x18000449a  mov     r8, rbx; lpMem
0x18000449d  xor     edx, edx; dwFlags
0x18000449f  mov     rcx, rax; hHeap
0x1800044a2  call    cs:__imp_HeapFree
0x1800044a8  test    r12, r12
0x1800044ab  jz      short loc_1800044C1
0x1800044ad  call    cs:__imp_GetProcessHeap
0x1800044b3  mov     r8, r12; lpMem
0x1800044b6  xor     edx, edx; dwFlags
0x1800044b8  mov     rcx, rax; hHeap
0x1800044bb  call    cs:__imp_HeapFree
0x1800044c1  xor     r12d, r12d
0x1800044c4  cmp     r12w, [r15]
0x1800044c8  jnz     loc_1800042B9
0x1800044ce  mov     rax, [rsi+10h]
0x1800044d2  cmp     [rax], r12d
0x1800044d5  jnz     loc_1800045C6
0x1800044db  cmp     [r13+18h], r12d
0x1800044df  jz      loc_1800045C6
0x1800044e5  mov     rcx, [r13+10h]; lpFileName
0x1800044e9  cmp     [rsi+4], r12d
0x1800044ed  jz      loc_18000459E
0x1800044f3  lea     rdx, aWindowsOld_0; "Windows.old"
0x1800044fa  call    BuildPath
0x1800044ff  mov     rcx, rax
0x180004502  mov     r15, rax
0x180004505  call    DirectoryExists
0x18000450a  test    eax, eax
0x18000450c  jnz     short loc_180004583
0x18000450e  call    cs:__imp_GetLastError
0x180004514  mov     edi, eax
0x180004516  call    cs:__imp_CurrentIP
0x18000451c  mov     r8, [r13+48h]
0x180004520  lea     rdx, aCsetupfilescle_4; "CSetupFilesCleanup::CleanVolume - Plugi"...
0x180004527  mov     ecx, 4000000h; unsigned int
0x18000452c  mov     rbx, rax
0x18000452f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004534  mov     [rsp+370h+var_320], r12d
0x180004539  lea     rcx, aCsetupfilescle_21; "CSetupFilesCleanup::CleanVolume"
0x180004540  mov     [rsp+370h+var_328], r12
0x180004545  lea     r8, aD; "D"
0x18000454c  mov     [rsp+370h+var_330], edi
0x180004550  xor     r9d, r9d
0x180004553  mov     [rsp+370h+var_338], rbx
0x180004558  xor     edx, edx
0x18000455a  mov     [rsp+370h+var_340], rcx
0x18000455f  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180004566  mov     [rsp+370h+var_348], rcx
0x18000456b  mov     rcx, rax
0x18000456e  mov     [rsp+370h+var_350], 366h
0x180004576  call    cs:__imp_WdsSetupLogMessageW
0x18000457c  mov     rax, [rsi+8]
0x180004580  mov     [rax], r12d
0x180004583  test    r15, r15
0x180004586  jz      short loc_1800045C6
0x180004588  call    cs:__imp_GetProcessHeap
0x18000458e  mov     r8, r15; lpMem
0x180004591  xor     edx, edx; dwFlags
0x180004593  mov     rcx, rax; hHeap
0x180004596  call    cs:__imp_HeapFree
0x18000459c  jmp     short loc_1800045C6
0x18000459e  mov     r9, rsi
0x1800045a1  mov     [rsp+370h+var_350], 1; int
0x1800045a9  xor     r8d, r8d
0x1800045ac  lea     rdx, ?EnumVolumeSubdirs@CSetupFilesCleanup@@CAHPEAU_WDSLIB_FIND_DATA@@P6AH0PEAX@Z1@Z; CSetupFilesCleanup::EnumVolumeSubdirs(_WDSLIB_FIND_DATA *,int (*)(_WDSLIB_FIND_DATA *,void *),void *)
0x1800045b3  call    EnumeratePathEx
  ... truncated ...
```
