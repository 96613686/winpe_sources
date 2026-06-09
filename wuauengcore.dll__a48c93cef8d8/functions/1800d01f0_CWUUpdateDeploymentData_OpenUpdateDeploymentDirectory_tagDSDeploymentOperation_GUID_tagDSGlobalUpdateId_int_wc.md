# CWUUpdateDeploymentData::OpenUpdateDeploymentDirectory(tagDSDeploymentOperation,_GUID,tagDSGlobalUpdateId,int,wchar_t * *,wchar_t const *)

- ea: `0x1800d01f0`
- end: `0x1800d068b`
- name: `?OpenUpdateDeploymentDirectory@CWUUpdateDeploymentData@@UEAAJW4tagDSDeploymentOperation@@U_GUID@@UtagDSGlobalUpdateId@@HPEAPEA_WPEB_W@Z`
- size: `1179`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x18003baf4`
- `0x18009df14`
- `0x1800aa468`
- `0x1800cf4a4`
- `0x1800d01f0`
- `0x1801345ec`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d05e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d05e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d02cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d03a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d02cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d03a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0307`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0389`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d062e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0642`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0307`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0389`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d062e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0642`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d0579`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800d0579`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800d0427`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800d0427`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d058b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d05dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d058b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d05dc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d0481`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d0481`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800d03d2`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800d046c`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800d04b7`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800d04db`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800d03d2`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800d046c`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800d04b7`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800d04db`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800d0417`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800d0417`

## string_xrefs

- `0x1800d0260`: `C:\__w\1\s\src\Client\Engine\Agent\WUUpdateDeploymentDataImpl.cpp`
- `0x1800d0371`: `C:\__w\1\s\src\Client\Engine\Agent\WUUpdateDeploymentDataImpl.cpp`
- `0x1800d05a1`: `C:\__w\1\s\src\Client\Engine\Agent\WUUpdateDeploymentDataImpl.cpp`
- `0x1800d05c5`: `C:\__w\1\s\src\Client\Engine\Agent\WUUpdateDeploymentDataImpl.cpp`
- `0x1800d05f9`: `C:\__w\1\s\src\Client\Engine\Agent\WUUpdateDeploymentDataImpl.cpp`
- `0x1800d03ec`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x1800d044b`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x1800d0496`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall CWUUpdateDeploymentData::OpenUpdateDeploymentDirectory(
        __int64 a1,
        unsigned int a2,
        const struct _GUID *a3,
        const struct tagDSGlobalUpdateId *a4,
        int a5,
        wchar_t **a6,
        wchar_t *a7)
{
  int IsPatchUpdate; // ebx
  __int64 v11; // rdx
  CAgentDownloadManager *v13; // rcx
  const struct _GUID *v14; // r8
  unsigned int v15; // r9d
  unsigned int v16; // edx
  __int64 v17; // r8
  void (__fastcall ***v18)(_QWORD, __int64); // rdi
  HANDLE v19; // rsi
  HRESULT v20; // eax
  RPC_STATUS v21; // eax
  signed int LastError; // r14d
  DWORD CurrentProcessId; // eax
  const char *v24; // r9
  __int64 v25; // rdx
  int Instance; // eax
  HANDLE Thread; // rax
  const char *v28; // r9
  void *v29; // rcx
  HANDLE v30; // r14
  const char *v31; // r9
  HANDLE *dwCreationFlags; // [rsp+20h] [rbp-E0h]
  bool v33; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-BCh]
  void (__fastcall ***v35)(_QWORD, __int64); // [rsp+48h] [rbp-B8h]
  const struct _GUID *v36; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v37; // [rsp+58h] [rbp-A8h]
  wchar_t **v38; // [rsp+60h] [rbp-A0h]
  _DWORD RpcCallAttributes[32]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v40; // [rsp+F0h] [rbp-10h] BYREF
  IUnknown *ppOldObject; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t v42[264]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v36 = a3;
  v34 = a2;
  v38 = a6;
  v37 = a7;
  if ( !a6 )
  {
    IsPatchUpdate = -2147467261;
    v11 = 363;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\WUUpdateDeploymentDataImpl.cpp",
      (const char *)(unsigned int)IsPatchUpdate,
      (int)dwCreationFlags);
    return (unsigned int)IsPatchUpdate;
  }
  memset(v42, 0, 0x208u);
  v13 = (CAgentDownloadManager *)(*(_QWORD *)(a1 + 136) + 160LL);
  v33 = 0;
  IsPatchUpdate = CAgentDownloadManager::IsPatchUpdate(v13, a4, v14, &v33);
  if ( IsPatchUpdate < 0 )
  {
    v11 = 368;
    goto LABEL_3;
  }
  if ( !v33 )
  {
    if ( a1 != -8 )
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    v15 = *(_DWORD *)(a1 + 124);
    v16 = 0;
    if ( v15 )
    {
      v17 = 0;
      while ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 112) + v17) + 64LL) )
      {
        ++v16;
        v17 += 8;
        if ( v16 >= v15 )
          goto LABEL_13;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17C,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\WUUpdateDeploymentDataImpl.cpp",
        (const char *)0x80240016LL,
        (int)dwCreationFlags);
      if ( a1 != -8 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      return 2149842966LL;
    }
LABEL_13:
    if ( a1 != -8 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
  IsPatchUpdate = CAgentDownloadManager::OpenUpdateInstallDirectory(
                    (CAgentDownloadManager *)(*(_QWORD *)(a1 + 136) + 160LL),
                    a3,
                    a4,
                    a7,
                    v42,
                    0x104u,
                    a5);
  if ( IsPatchUpdate < 0 )
  {
    v11 = 390;
    goto LABEL_3;
  }
  if ( a1 != -8 )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v35 = 0;
  v18 = 0;
  memset(&RpcCallAttributes[2], 0, 0x70u);
  v40 = 0;
  ppOldObject = 0;
  v19 = 0;
  v20 = CoSwitchCallContext(0, &ppOldObject);
  if ( v20 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)(unsigned int)v20,
      (int)dwCreationFlags);
  else
    LODWORD(v40) = 1;
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 112;
  v21 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  LastError = v21;
  if ( v21 == 1725 )
  {
    CurrentProcessId = GetCurrentProcessId();
  }
  else
  {
    if ( v21 >= 1 )
      LastError = (unsigned __int16)v21 | 0x80010000;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
        (const char *)(unsigned int)LastError,
        (int)dwCreationFlags);
      if ( (_DWORD)v40 )
        CoSwitchCallContext(ppOldObject, &ppOldObject);
      goto LABEL_37;
    }
    CurrentProcessId = RpcCallAttributes[16];
  }
  v19 = OpenProcess(0x100400u, 0, CurrentProcessId);
  if ( v19 )
  {
    if ( (_DWORD)v40 )
      CoSwitchCallContext(ppOldObject, &ppOldObject);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD2,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                  v24);
    if ( (_DWORD)v40 )
      CoSwitchCallContext(ppOldObject, &ppOldObject);
    v19 = 0;
    if ( LastError < 0 )
    {
LABEL_37:
      v25 = 399;
      goto LABEL_50;
    }
  }
  dwCreationFlags = &v40;
  v40 = v19;
  Instance = CWUDeploymentDirectoryInfo::CreateInstance(v34, a4, v36, v37);
  v18 = v35;
  LastError = Instance;
  if ( Instance < 0 )
  {
    v25 = 408;
    goto LABEL_50;
  }
  v36 = (const struct _GUID *)v35;
  v19 = 0;
  LastError = (*(__int64 (__fastcall **)(__int64, const struct _GUID **, _QWORD))(*(_QWORD *)(a1 + 104) + 8LL))(
                a1 + 104,
                &v36,
                0);
  if ( LastError < 0 )
  {
    v25 = 412;
    goto LABEL_50;
  }
  v18 = 0;
  if ( !*(_QWORD *)(a1 + 88) )
  {
    Thread = CreateThread(0, 0, CWUUpdateDeploymentData::DeploymentDirectoryMonitorThread, (LPVOID)a1, 0, 0);
    v29 = *(void **)(a1 + 88);
    v30 = Thread;
    if ( v29 )
      CloseHandle(v29);
    *(_QWORD *)(a1 + 88) = v30;
    if ( !v30 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x106,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\WUUpdateDeploymentDataImpl.cpp",
                    v28);
      if ( LastError < 0 )
      {
        v25 = 414;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\WUUpdateDeploymentDataImpl.cpp",
          (const char *)(unsigned int)LastError,
          (int)dwCreationFlags);
        if ( v19 )
          CloseHandle(v19);
        goto LABEL_54;
      }
    }
  }
  if ( !SetEvent(*(HANDLE *)(a1 + 72)) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x19F,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\WUUpdateDeploymentDataImpl.cpp",
                  v31);
LABEL_54:
    if ( v18 )
      (**v18)(v18, 1);
    if ( a1 != -8 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    return (unsigned int)LastError;
  }
  if ( a1 != -8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  IsPatchUpdate = DSCopyString(v38, v42);
  if ( IsPatchUpdate < 0 )
  {
    v11 = 418;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800d01f0  push    rbp
0x1800d01f2  push    rbx
0x1800d01f3  push    rsi
0x1800d01f4  push    rdi
0x1800d01f5  push    r12
0x1800d01f7  push    r13
0x1800d01f9  push    r14
0x1800d01fb  push    r15
0x1800d01fd  lea     rbp, [rsp-228h]
0x1800d0205  sub     rsp, 328h
0x1800d020c  mov     rax, cs:__security_cookie
0x1800d0213  xor     rax, rsp
0x1800d0216  mov     [rbp+260h+var_50], rax
0x1800d021d  mov     rax, [rbp+260h+arg_28]
0x1800d0224  xor     r14d, r14d
0x1800d0227  mov     rsi, [rbp+260h+arg_30]
0x1800d022e  mov     r13, r9
0x1800d0231  mov     [rsp+360h+var_310], r8
0x1800d0236  mov     rdi, r8
0x1800d0239  mov     [rsp+360h+var_31C], edx
0x1800d023d  mov     r15, rcx
0x1800d0240  mov     [rsp+360h+var_300], rax
0x1800d0245  mov     [rsp+360h+var_308], rsi
0x1800d024a  test    rax, rax
0x1800d024d  jnz     short loc_1800D0276
0x1800d024f  mov     ebx, 80004003h
0x1800d0254  mov     edx, 16Bh; void *
0x1800d0259  mov     rcx, [rbp+268h]; this
0x1800d0260  lea     r8, aCW1SSrcClientE_68; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800d0267  mov     r9d, ebx; char *
0x1800d026a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d026f  mov     eax, ebx
0x1800d0271  jmp     loc_1800D0668
0x1800d0276  xor     edx, edx; Val
0x1800d0278  lea     rcx, [rbp+260h+var_260]; void *
0x1800d027c  mov     r8d, 208h; Size
0x1800d0282  call    memset
0x1800d0287  mov     rcx, [r15+88h]
0x1800d028e  lea     r9, [rsp+360h+var_320]; bool *
0x1800d0293  add     rcx, 0A0h; this
0x1800d029a  mov     [rsp+360h+var_320], r14b
0x1800d029f  mov     rdx, r13; struct tagDSGlobalUpdateId *
0x1800d02a2  call    ?IsPatchUpdate@CAgentDownloadManager@@QEAAJAEBUtagDSGlobalUpdateId@@AEBU_GUID@@PEA_N@Z; CAgentDownloadManager::IsPatchUpdate(tagDSGlobalUpdateId const &,_GUID const &,bool *)
0x1800d02a7  mov     ebx, eax
0x1800d02a9  test    eax, eax
0x1800d02ab  jns     short loc_1800D02B4
0x1800d02ad  mov     edx, 170h
0x1800d02b2  jmp     short loc_1800D0259
0x1800d02b4  mov     r12b, [rsp+360h+var_320]
0x1800d02b9  test    r12b, r12b
0x1800d02bc  jnz     short loc_1800D030D
0x1800d02be  lea     rbx, [r15+8]
0x1800d02c2  test    rbx, rbx
0x1800d02c5  jz      short loc_1800D02D1
0x1800d02c7  lea     rcx, [rbx+8]; lpCriticalSection
0x1800d02cb  call    cs:__imp_EnterCriticalSection
0x1800d02d1  mov     r9d, [r15+7Ch]
0x1800d02d5  mov     edx, r14d
0x1800d02d8  test    r9d, r9d
0x1800d02db  jz      short loc_1800D02FE
0x1800d02dd  mov     r8, r14
0x1800d02e0  cmp     edx, r9d
0x1800d02e3  jnb     short loc_1800D0360
0x1800d02e5  mov     rax, [r15+70h]
0x1800d02e9  mov     rcx, [rax+r8]
0x1800d02ed  cmp     [rcx+40h], r14b
0x1800d02f1  jz      short loc_1800D0354
0x1800d02f3  inc     edx
0x1800d02f5  add     r8, 8
0x1800d02f9  cmp     edx, r9d
0x1800d02fc  jb      short loc_1800D02E5
0x1800d02fe  test    rbx, rbx
0x1800d0301  jz      short loc_1800D030D
0x1800d0303  lea     rcx, [rbx+8]; lpCriticalSection
0x1800d0307  call    cs:__imp_LeaveCriticalSection
0x1800d030d  mov     eax, [rbp+260h+arg_20]
0x1800d0313  mov     r9, rsi; wchar_t *
0x1800d0316  mov     rcx, [r15+88h]
0x1800d031d  mov     r8, r13; struct tagDSGlobalUpdateId *
0x1800d0320  mov     [rsp+360h+var_330], eax; int
0x1800d0324  add     rcx, 0A0h; this
0x1800d032b  lea     rax, [rbp+260h+var_260]
0x1800d032f  mov     dword ptr [rsp+360h+lpThreadId], 104h; unsigned int
0x1800d0337  mov     rdx, rdi; struct _GUID *
0x1800d033a  mov     qword ptr [rsp+360h+dwCreationFlags], rax; int
0x1800d033f  call    ?OpenUpdateInstallDirectory@CAgentDownloadManager@@QEAAJAEBU_GUID@@AEBUtagDSGlobalUpdateId@@PEB_WPEA_WKH@Z; CAgentDownloadManager::OpenUpdateInstallDirectory(_GUID const &,tagDSGlobalUpdateId const &,wchar_t const *,wchar_t *,ulong,int)
0x1800d0344  mov     ebx, eax
0x1800d0346  test    eax, eax
0x1800d0348  jns     short loc_1800D0396
0x1800d034a  mov     edx, 186h
0x1800d034f  jmp     loc_1800D0259
0x1800d0354  mov     edi, 80240016h
0x1800d0359  mov     edx, 17Ch
0x1800d035e  jmp     short loc_1800D036A
0x1800d0360  mov     edi, 80240007h
0x1800d0365  mov     edx, 17Bh; void *
0x1800d036a  mov     rcx, [rbp+268h]; this
0x1800d0371  lea     r8, aCW1SSrcClientE_68; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800d0378  mov     r9d, edi; char *
0x1800d037b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0380  test    rbx, rbx
0x1800d0383  jz      short loc_1800D038F
0x1800d0385  lea     rcx, [rbx+8]; lpCriticalSection
0x1800d0389  call    cs:__imp_LeaveCriticalSection
0x1800d038f  mov     eax, edi
0x1800d0391  jmp     loc_1800D0668
0x1800d0396  lea     rbx, [r15+8]
0x1800d039a  test    rbx, rbx
0x1800d039d  jz      short loc_1800D03A9
0x1800d039f  lea     rcx, [rbx+8]; lpCriticalSection
0x1800d03a3  call    cs:__imp_EnterCriticalSection
0x1800d03a9  xor     edx, edx; Val
0x1800d03ab  mov     [rsp+360h+var_318], r14
0x1800d03b0  lea     rcx, [rsp+360h+var_2E8]; void *
0x1800d03b5  mov     rdi, r14
0x1800d03b8  lea     r8d, [rdx+70h]; Size
0x1800d03bc  call    memset
0x1800d03c1  lea     rdx, [rbp+260h+ppOldObject]; ppOldObject
0x1800d03c5  mov     [rbp+260h+var_270], r14
0x1800d03c9  xor     ecx, ecx; pNewObject
0x1800d03cb  mov     [rbp+260h+ppOldObject], r14
0x1800d03cf  mov     rsi, r14
0x1800d03d2  call    cs:__imp_CoSwitchCallContext
0x1800d03d8  test    eax, eax
0x1800d03da  js      short loc_1800D03E5
0x1800d03dc  mov     dword ptr [rbp+260h+var_270], 1
0x1800d03e3  jmp     short loc_1800D0400
0x1800d03e5  mov     rcx, [rbp+268h]; this
0x1800d03ec  lea     r8, aCW1SSrcClientL_45; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800d03f3  mov     r9d, eax; char *
0x1800d03f6  mov     edx, 0BFh; void *
0x1800d03fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d0400  lea     rdx, [rsp+360h+RpcCallAttributes]; RpcCallAttributes
0x1800d0405  mov     [rsp+360h+RpcCallAttributes], 3
0x1800d040d  xor     ecx, ecx; ClientBinding
0x1800d040f  mov     [rsp+360h+var_2EC], 70h ; 'p'
0x1800d0417  call    cs:__imp_RpcServerInqCallAttributesW
0x1800d041d  mov     r14d, eax
0x1800d0420  cmp     eax, 6BDh
0x1800d0425  jnz     short loc_1800D042F
0x1800d0427  call    cs:__imp_GetCurrentProcessId
0x1800d042d  jmp     short loc_1800D0477
0x1800d042f  cmp     eax, 1
0x1800d0432  jl      short loc_1800D043F
0x1800d0434  movzx   r14d, ax
0x1800d0438  or      r14d, 80010000h
0x1800d043f  test    r14d, r14d
0x1800d0442  jns     short loc_1800D0474
0x1800d0444  mov     rcx, [rbp+268h]; this
0x1800d044b  lea     r8, aCW1SSrcClientL_45; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800d0452  mov     r9d, r14d; char *
0x1800d0455  mov     edx, 0CDh; void *
0x1800d045a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d045f  cmp     dword ptr [rbp+260h+var_270], esi
0x1800d0462  jz      short loc_1800D04C4
0x1800d0464  mov     rcx, [rbp+260h+ppOldObject]; pNewObject
0x1800d0468  lea     rdx, [rbp+260h+ppOldObject]; ppOldObject
0x1800d046c  call    cs:__imp_CoSwitchCallContext
0x1800d0472  jmp     short loc_1800D04C4
0x1800d0474  mov     eax, [rbp+260h+var_2B0]
0x1800d0477  mov     r8d, eax; dwProcessId
0x1800d047a  xor     edx, edx; bInheritHandle
0x1800d047c  mov     ecx, 100400h; dwDesiredAccess
0x1800d0481  call    cs:__imp_OpenProcess
0x1800d0487  mov     rsi, rax
0x1800d048a  test    rax, rax
0x1800d048d  jnz     short loc_1800D04CE
0x1800d048f  mov     rcx, [rbp+268h]; this
0x1800d0496  lea     r8, aCW1SSrcClientL_45; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800d049d  mov     edx, 0D2h; void *
0x1800d04a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d04a7  mov     r14d, eax
0x1800d04aa  cmp     dword ptr [rbp+260h+var_270], edi
0x1800d04ad  jz      short loc_1800D04BD
0x1800d04af  mov     rcx, [rbp+260h+ppOldObject]; pNewObject
0x1800d04b3  lea     rdx, [rbp+260h+ppOldObject]; ppOldObject
0x1800d04b7  call    cs:__imp_CoSwitchCallContext
0x1800d04bd  xor     esi, esi
0x1800d04bf  test    r14d, r14d
0x1800d04c2  jns     short loc_1800D04E1
0x1800d04c4  mov     edx, 18Fh
0x1800d04c9  jmp     loc_1800D05BE
0x1800d04ce  cmp     dword ptr [rbp+260h+var_270], edi
0x1800d04d1  jz      short loc_1800D04E1
0x1800d04d3  mov     rcx, [rbp+260h+ppOldObject]; pNewObject
0x1800d04d7  lea     rdx, [rbp+260h+ppOldObject]; ppOldObject
0x1800d04db  call    cs:__imp_CoSwitchCallContext
0x1800d04e1  mov     r9, [rsp+360h+var_308]
0x1800d04e6  lea     rax, [rsp+360h+var_318]
0x1800d04eb  mov     r8, [rsp+360h+var_310]
0x1800d04f0  mov     rdx, r13
0x1800d04f3  mov     ecx, [rsp+360h+var_31C]
0x1800d04f7  mov     qword ptr [rsp+360h+var_330], rax
0x1800d04fc  lea     rax, [rbp+260h+var_270]
0x1800d0500  mov     byte ptr [rsp+360h+lpThreadId], r12b
0x1800d0505  mov     qword ptr [rsp+360h+dwCreationFlags], rax
0x1800d050a  mov     [rbp+260h+var_270], rsi
0x1800d050e  call    ?CreateInstance@CWUDeploymentDirectoryInfo@@SAJW4tagDSDeploymentOperation@@AEBUtagDSGlobalUpdateId@@AEBU_GUID@@PEB_WAEBQEAX_NPEAPEAV1@@Z; CWUDeploymentDirectoryInfo::CreateInstance(tagDSDeploymentOperation,tagDSGlobalUpdateId const &,_GUID const &,wchar_t const *,void * const &,bool,CWUDeploymentDirectoryInfo * *)
0x1800d0513  mov     rdi, [rsp+360h+var_318]
0x1800d0518  mov     r14d, eax
0x1800d051b  test    eax, eax
0x1800d051d  jns     short loc_1800D0529
0x1800d051f  mov     edx, 198h
0x1800d0524  jmp     loc_1800D05BE
0x1800d0529  lea     rcx, [r15+68h]
0x1800d052d  mov     [rsp+360h+var_310], rdi
0x1800d0532  mov     rax, [rcx]
0x1800d0535  lea     rdx, [rsp+360h+var_310]
0x1800d053a  xor     r8d, r8d
0x1800d053d  xor     esi, esi
0x1800d053f  mov     rax, [rax+8]
0x1800d0543  call    _guard_dispatch_icall
0x1800d0548  mov     r14d, eax
0x1800d054b  test    eax, eax
0x1800d054d  jns     short loc_1800D0556
0x1800d054f  mov     edx, 19Ch
0x1800d0554  jmp     short loc_1800D05BE
0x1800d0556  xor     edi, edi
0x1800d0558  cmp     [r15+58h], rsi
0x1800d055c  jnz     loc_1800D05E4
0x1800d0562  mov     [rsp+360h+lpThreadId], rsi; lpThreadId
0x1800d0567  lea     r8, ?DeploymentDirectoryMonitorThread@CWUUpdateDeploymentData@@CAKPEAX@Z; lpStartAddress
0x1800d056e  mov     r9, r15; lpParameter
0x1800d0571  mov     [rsp+360h+dwCreationFlags], esi; int
0x1800d0575  xor     edx, edx; dwStackSize
0x1800d0577  xor     ecx, ecx; lpThreadAttributes
0x1800d0579  call    cs:__imp_CreateThread
0x1800d057f  mov     rcx, [r15+58h]; hObject
0x1800d0583  mov     r14, rax
0x1800d0586  test    rcx, rcx
0x1800d0589  jz      short loc_1800D0591
0x1800d058b  call    cs:__imp_CloseHandle
0x1800d0591  mov     [r15+58h], r14
0x1800d0595  test    r14, r14
0x1800d0598  jnz     short loc_1800D05E4
0x1800d059a  mov     rcx, [rbp+268h]; this
0x1800d05a1  lea     r8, aCW1SSrcClientE_68; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800d05a8  mov     edx, 106h; void *
0x1800d05ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d05b2  mov     r14d, eax
0x1800d05b5  test    eax, eax
0x1800d05b7  jns     short loc_1800D05E4
0x1800d05b9  mov     edx, 19Eh; void *
0x1800d05be  mov     rcx, [rbp+268h]; this
0x1800d05c5  lea     r8, aCW1SSrcClientE_68; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800d05cc  mov     r9d, r14d; char *
0x1800d05cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d05d4  test    rsi, rsi
0x1800d05d7  jz      short loc_1800D060D
0x1800d05d9  mov     rcx, rsi; hObject
0x1800d05dc  call    cs:__imp_CloseHandle
0x1800d05e2  jmp     short loc_1800D060D
0x1800d05e4  mov     rcx, [r15+48h]; hEvent
0x1800d05e8  call    cs:__imp_SetEvent
0x1800d05ee  test    eax, eax
0x1800d05f0  jnz     short loc_1800D0639
0x1800d05f2  mov     rcx, [rbp+268h]; this
0x1800d05f9  lea     r8, aCW1SSrcClientE_68; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800d0600  mov     edx, 19Fh; void *
0x1800d0605  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d060a  mov     r14d, eax
0x1800d060d  test    rdi, rdi
0x1800d0610  jz      short loc_1800D0625
0x1800d0612  mov     rcx, [rdi]
0x1800d0615  mov     edx, 1
0x1800d061a  mov     rax, [rcx]
0x1800d061d  mov     rcx, rdi
0x1800d0620  call    _guard_dispatch_icall
0x1800d0625  test    rbx, rbx
0x1800d0628  jz      short loc_1800D0634
0x1800d062a  lea     rcx, [rbx+8]; lpCriticalSection
0x1800d062e  call    cs:__imp_LeaveCriticalSection
0x1800d0634  mov     eax, r14d
0x1800d0637  jmp     short loc_1800D0668
0x1800d0639  test    rbx, rbx
0x1800d063c  jz      short loc_1800D0648
0x1800d063e  lea     rcx, [rbx+8]; lpCriticalSection
0x1800d0642  call    cs:__imp_LeaveCriticalSection
0x1800d0648  mov     rcx, [rsp+360h+var_300]; wchar_t **
0x1800d064d  lea     rdx, [rbp+260h+var_260]; wchar_t *
0x1800d0651  call    ?DSCopyString@@YAJPEAPEA_WPEB_W@Z; DSCopyString(wchar_t * *,wchar_t const *)
0x1800d0656  mov     ebx, eax
0x1800d0658  test    eax, eax
0x1800d065a  jns     short loc_1800D0666
0x1800d065c  mov     edx, 1A2h
0x1800d0661  jmp     loc_1800D0259
0x1800d0666  xor     eax, eax
0x1800d0668  mov     rcx, [rbp+260h+var_50]
0x1800d066f  xor     rcx, rsp; StackCookie
0x1800d0672  call    __security_check_cookie
0x1800d0677  add     rsp, 328h
0x1800d067e  pop     r15
0x1800d0680  pop     r14
0x1800d0682  pop     r13
0x1800d0684  pop     r12
0x1800d0686  pop     rdi
0x1800d0687  pop     rsi
0x1800d0688  pop     rbx
0x1800d0689  pop     rbp
0x1800d068a  retn
  ... truncated ...
```
