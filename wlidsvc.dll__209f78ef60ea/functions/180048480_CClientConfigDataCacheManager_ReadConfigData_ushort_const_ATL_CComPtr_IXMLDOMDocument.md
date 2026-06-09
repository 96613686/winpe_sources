# CClientConfigDataCacheManager::ReadConfigData(ushort const *,ATL::CComPtr<IXMLDOMDocument> &)

- ea: `0x180048480`
- end: `0x18004875b`
- name: `?ReadConfigData@CClientConfigDataCacheManager@@AEAAJPEBGAEAV?$CComPtr@UIXMLDOMDocument@@@ATL@@@Z`
- size: `731`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, struct IXMLDOMDocument **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180048384`

## callees

- `0x18000c050`
- `0x1800151c4`
- `0x18001a530`
- `0x18001a9c0`
- `0x1800204ac`
- `0x18003c3c0`
- `0x180040f70`
- `0x180048480`
- `0x18007cdf8`
- `0x1800f4624`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004861f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004861f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048693`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004865e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004865e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048734`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048734`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004860e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004860e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180048684`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180048684`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800485d7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800485d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004857f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004857f`

## string_xrefs

- `0x1800484ed`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800484d7`: `CClientConfigDataCacheManager::ReadConfigData`
- `0x18004864a`: `CClientConfigDataCacheManager::ReadConfigData`
- `0x1800486c1`: `CClientConfigDataCacheManager::ReadConfigData`
- `0x18004870a`: `CClientConfigDataCacheManager::ReadConfigData`
- `0x1800486f5`: `hr = WlidsvcUtil::LoadXMLFromString(resourceXML, &rpXMLConfigData)`

## pseudocode

```c
__int64 __fastcall CClientConfigDataCacheManager::ReadConfigData(
        __int64 a1,
        const WCHAR *a2,
        struct IXMLDOMDocument **a3)
{
  int v5; // r9d
  unsigned int v6; // r8d
  unsigned int v7; // ebx
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v11; // eax
  bool v12; // sf
  HANDLE ProcessHeap; // r14
  SIZE_T LowPart; // rdi
  signed int v15; // eax
  void *v16; // rbx
  signed int v17; // eax
  int XMLFromString; // eax
  const char *v19; // r9
  const char *dwCreationDisposition; // [rsp+20h] [rbp-60h]
  char *v21; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v23[32]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v25; // [rsp+C0h] [rbp+40h] BYREF
  int v26; // [rsp+C4h] [rbp+44h]
  DWORD NumberOfBytesRead; // [rsp+C8h] [rbp+48h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+D8h] [rbp+58h] BYREF

  v26 = HIDWORD(a1);
  v25 = 0;
  FileSize.QuadPart = 0;
  memset(v22, 0, sizeof(v22));
  CTraceFuncW<long>::CTraceFuncW<long>(
    v23,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    1964,
    &v25,
    "CClientConfigDataCacheManager::ReadConfigData",
    L"szFileName=%ls",
    a2);
  if ( !a2 )
  {
    v5 = -2147024809;
    v25 = -2147024809;
    dwCreationDisposition = "szFileName != nullptr";
    v6 = 1966;
LABEL_3:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "CClientConfigDataCacheManager::ReadConfigData",
      v6,
      v5,
      dwCreationDisposition);
    goto LABEL_4;
  }
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  Auto<void *,HandleFunctor,IWinApiLite>::Clear(v22);
  v22[0] = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v25 = LastError;
    if ( LastError < 0 )
    {
      dwCreationDisposition = "hr = HRESULT_FROM_WIN32(GetLastError())";
      v5 = LastError;
      v6 = 1979;
      goto LABEL_3;
    }
  }
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v11 = GetLastError();
    v12 = v11 < 0;
    if ( v11 > 0 )
    {
      v11 = (unsigned __int16)v11 | 0x80070000;
      v12 = v11 < 0;
    }
    if ( v12 )
    {
      dwCreationDisposition = "HRESULT_FROM_WIN32(GetLastError())";
      v5 = v11;
      v6 = 1988;
      goto LABEL_3;
    }
  }
  ProcessHeap = GetProcessHeap();
  LowPart = FileSize.LowPart;
  if ( ProcessHeap )
    goto LABEL_21;
  v15 = GetLastError();
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  v25 = v15;
  if ( v15 >= 0 )
  {
LABEL_21:
    v16 = HeapAlloc(ProcessHeap, 0, LowPart);
    NumberOfBytesRead = 0;
    if ( ReadFile(FileW, v16, LowPart, &NumberOfBytesRead, 0) && NumberOfBytesRead == (_DWORD)LowPart )
      goto LABEL_27;
    v17 = GetLastError();
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    v25 = v17;
    if ( v17 >= 0 )
    {
LABEL_27:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
        &v21,
        v16,
        (unsigned int)LowPart);
      XMLFromString = WlidsvcUtil::LoadXMLFromString(v21, a3);
      v25 = XMLFromString;
      if ( XMLFromString < 0 )
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
          "CClientConfigDataCacheManager::ReadConfigData",
          0x7E3u,
          XMLFromString,
          "hr = WlidsvcUtil::LoadXMLFromString(resourceXML, &rpXMLConfigData)");
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v21);
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        "CClientConfigDataCacheManager::ReadConfigData",
        0x7DCu,
        v17,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
    }
    if ( v16 && !HeapFree(ProcessHeap, 0, v16) )
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x7E9,
             (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
             v19);
      goto LABEL_5;
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "CClientConfigDataCacheManager::ReadConfigData",
      0x7CCu,
      v15,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
LABEL_4:
  v7 = v25;
LABEL_5:
  CTraceFuncW<long>::~CTraceFuncW<long>(v23);
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(v22);
  return v7;
}

```

## disassembly

```asm
0x180048480  mov     [rsp-38h+arg_0], rcx
0x180048485  push    rbp
0x180048486  push    rbx
0x180048487  push    rsi
0x180048488  push    rdi
0x180048489  push    r13
0x18004848b  push    r14
0x18004848d  push    r15
0x18004848f  mov     rbp, rsp
0x180048492  sub     rsp, 80h
0x180048499  mov     r15, r8
0x18004849c  mov     rbx, rdx
0x18004849f  mov     dword ptr [rbp+arg_0], 0
0x1800484a6  mov     qword ptr [rbp+FileSize], 0
0x1800484ae  mov     [rbp+var_38], 0
0x1800484b6  mov     [rbp+var_28], 0
0x1800484be  mov     [rbp+var_30], 0
0x1800484c6  mov     [rsp+80h+hTemplateFile], rdx
0x1800484cb  lea     rax, aSzfilenameLs; "szFileName=%ls"
0x1800484d2  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rax
0x1800484d7  lea     rdi, aCclientconfigd_15; "CClientConfigDataCacheManager::ReadConf"...
0x1800484de  mov     qword ptr [rsp+80h+dwCreationDisposition], rdi
0x1800484e3  lea     r9, [rbp+arg_0]
0x1800484e7  mov     r8d, 7ACh
0x1800484ed  lea     r13, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800484f4  mov     rdx, r13
0x1800484f7  lea     rcx, [rbp+var_20]
0x1800484fb  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x180048500  nop
0x180048501  test    rbx, rbx
0x180048504  jnz     short loc_180048557
0x180048506  mov     r9d, 80070057h; int
0x18004850c  mov     dword ptr [rbp+arg_0], r9d
0x180048510  lea     rax, aSzfilenameNull; "szFileName != nullptr"
0x180048517  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; char *
0x18004851c  mov     r8d, 7AEh; unsigned int
0x180048522  mov     rdx, rdi; char *
0x180048525  mov     rcx, r13; char *
0x180048528  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18004852d  mov     ebx, dword ptr [rbp+arg_0]
0x180048530  lea     rcx, [rbp+var_20]
0x180048534  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180048539  nop
0x18004853a  lea     rcx, [rbp+var_38]
0x18004853e  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x180048543  mov     eax, ebx
0x180048545  add     rsp, 80h
0x18004854c  pop     r15
0x18004854e  pop     r14
0x180048550  pop     r13
0x180048552  pop     rdi
0x180048553  pop     rsi
0x180048554  pop     rbx
0x180048555  pop     rbp
0x180048556  retn
0x180048557  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180048560  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180048568  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180048570  xor     r9d, r9d; lpSecurityAttributes
0x180048573  mov     edx, 80000000h; dwDesiredAccess
0x180048578  lea     r8d, [r9+1]; dwShareMode
0x18004857c  mov     rcx, rbx; lpFileName
0x18004857f  call    cs:__imp_CreateFileW
0x180048585  mov     rsi, rax
0x180048588  lea     rcx, [rbp+var_38]
0x18004858c  call    ?Clear@?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAAXXZ; Auto<void *,HandleFunctor,IWinApiLite>::Clear(void)
0x180048591  mov     [rbp+var_38], rsi
0x180048595  mov     ebx, 80070000h
0x18004859a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004859e  jnz     short loc_1800485D0
0x1800485a0  call    cs:__imp_GetLastError
0x1800485a6  test    eax, eax
0x1800485a8  jle     short loc_1800485AF
0x1800485aa  movzx   eax, ax
0x1800485ad  or      eax, ebx
0x1800485af  mov     dword ptr [rbp+arg_0], eax
0x1800485b2  test    eax, eax
0x1800485b4  jns     short loc_1800485D0
0x1800485b6  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800485bd  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x1800485c2  mov     r9d, eax
0x1800485c5  mov     r8d, 7BBh
0x1800485cb  jmp     loc_180048522
0x1800485d0  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800485d4  mov     rcx, rsi; hFile
0x1800485d7  call    cs:__imp_GetFileSizeEx
0x1800485dd  test    eax, eax
0x1800485df  jnz     short loc_18004860E
0x1800485e1  call    cs:__imp_GetLastError
0x1800485e7  test    eax, eax
0x1800485e9  jle     short loc_1800485F2
0x1800485eb  movzx   eax, ax
0x1800485ee  or      eax, ebx
0x1800485f0  test    eax, eax
0x1800485f2  jns     short loc_18004860E
0x1800485f4  lea     rcx, aHresultFromWin; "HRESULT_FROM_WIN32(GetLastError())"
0x1800485fb  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x180048600  mov     r9d, eax
0x180048603  mov     r8d, 7C4h
0x180048609  jmp     loc_180048522
0x18004860e  call    cs:__imp_GetProcessHeap
0x180048614  mov     r14, rax
0x180048617  mov     edi, dword ptr [rbp+FileSize]
0x18004861a  test    rax, rax
0x18004861d  jnz     short loc_180048656
0x18004861f  call    cs:__imp_GetLastError
0x180048625  test    eax, eax
0x180048627  jle     short loc_18004862E
0x180048629  movzx   eax, ax
0x18004862c  or      eax, ebx
0x18004862e  mov     dword ptr [rbp+arg_0], eax
0x180048631  test    eax, eax
0x180048633  jns     short loc_180048656
0x180048635  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18004863c  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx
0x180048641  mov     r9d, eax
0x180048644  mov     r8d, 7CCh
0x18004864a  lea     rdx, aCclientconfigd_15; "CClientConfigDataCacheManager::ReadConf"...
0x180048651  jmp     loc_180048525
0x180048656  mov     r8, rdi; dwBytes
0x180048659  xor     edx, edx; dwFlags
0x18004865b  mov     rcx, r14; hHeap
0x18004865e  call    cs:__imp_HeapAlloc
0x180048664  mov     rbx, rax
0x180048667  mov     [rbp+NumberOfBytesRead], 0
0x18004866e  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOverlapped
0x180048677  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004867b  mov     r8d, edi; nNumberOfBytesToRead
0x18004867e  mov     rdx, rax; lpBuffer
0x180048681  mov     rcx, rsi; hFile
0x180048684  call    cs:__imp_ReadFile
0x18004868a  test    eax, eax
0x18004868c  jz      short loc_180048693
0x18004868e  cmp     [rbp+NumberOfBytesRead], edi
0x180048691  jz      short loc_1800486D2
0x180048693  call    cs:__imp_GetLastError
0x180048699  test    eax, eax
0x18004869b  jle     short loc_1800486A5
0x18004869d  movzx   eax, ax
0x1800486a0  or      eax, 80070000h
0x1800486a5  mov     dword ptr [rbp+arg_0], eax
0x1800486a8  test    eax, eax
0x1800486aa  jns     short loc_1800486D2
0x1800486ac  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800486b3  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx; char *
0x1800486b8  mov     r9d, eax; int
0x1800486bb  mov     r8d, 7DCh; unsigned int
0x1800486c1  lea     rdx, aCclientconfigd_15; "CClientConfigDataCacheManager::ReadConf"...
0x1800486c8  mov     rcx, r13; char *
0x1800486cb  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800486d0  jmp     short loc_180048723
0x1800486d2  mov     r8d, edi
0x1800486d5  mov     rdx, rbx
0x1800486d8  lea     rcx, [rbp+var_40]
0x1800486dc  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBDH@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(char const *,int)
0x1800486e1  nop
0x1800486e2  mov     rdx, r15; struct IXMLDOMDocument **
0x1800486e5  mov     rcx, [rbp+var_40]; char *
0x1800486e9  call    ?LoadXMLFromString@WlidsvcUtil@@SAJQEBDPEAPEAUIXMLDOMDocument@@@Z; WlidsvcUtil::LoadXMLFromString(char const * const,IXMLDOMDocument * *)
0x1800486ee  mov     dword ptr [rbp+arg_0], eax
0x1800486f1  test    eax, eax
0x1800486f3  jns     short loc_18004871A
0x1800486f5  lea     rcx, aHrWlidsvcutilL_0; "hr = WlidsvcUtil::LoadXMLFromString(res"...
0x1800486fc  mov     qword ptr [rsp+80h+dwCreationDisposition], rcx; char *
0x180048701  mov     r9d, eax; int
0x180048704  mov     r8d, 7E3h; unsigned int
0x18004870a  lea     rdx, aCclientconfigd_15; "CClientConfigDataCacheManager::ReadConf"...
0x180048711  mov     rcx, r13; char *
0x180048714  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180048719  nop
0x18004871a  lea     rcx, [rbp+var_40]
0x18004871e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180048723  test    rbx, rbx
0x180048726  jz      loc_18004852D
0x18004872c  mov     r8, rbx; lpMem
0x18004872f  xor     edx, edx; dwFlags
0x180048731  mov     rcx, r14; hHeap
0x180048734  call    cs:__imp_HeapFree
0x18004873a  test    eax, eax
0x18004873c  jnz     loc_18004852D
0x180048742  mov     rcx, [rbp+38h]; this
0x180048746  mov     r8, r13; unsigned int
0x180048749  mov     edx, 7E9h; void *
0x18004874e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180048753  mov     ebx, eax
0x180048755  jmp     loc_180048530
```
