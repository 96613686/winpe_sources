# InitPrefBinWorker(void)

- ea: `0x1800372d0`
- end: `0x180037481`
- name: `?InitPrefBinWorker@@YAJXZ`
- size: `433`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016c74`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x1800372d0`
- `0x1800530e4`
- `0x180053d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037353`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800373a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800373e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037353`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800373a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800373e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037435`

## string_xrefs

- `0x180037322`: `PrefBin already Initialized`
- `0x180037377`: `Could not create stop event, will fall back to sync SetPrefBinCookie. 0x%x`
- `0x1800373ca`: `Could not create set cookie event, will fall back to sync SetPrefBinCookie. 0x%x`
- `0x180037409`: `Could not create reset cookie event, will fall back to sync SetPrefBinCookie. 0x%x`
- `0x180037447`: `Could not create prefbin thread, will fall back to sync SetPrefBinCookie. 0x%x`

## pseudocode

```c
__int64 InitPrefBinWorker(void)
{
  unsigned int v0; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v2; // r9
  unsigned int v3; // r8d
  int v4; // r8d
  const unsigned __int16 *v6; // [rsp+20h] [rbp-30h]
  __int64 v7; // [rsp+20h] [rbp-30h]
  _QWORD v8[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+10h] BYREF

  v0 = 0;
  v9 = 0;
  v8[0] = "InitPrefBinWorker";
  v8[1] = &v9;
  v8[2] = 0;
  v8[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\prefbinasync.cpp",
    "InitPrefBinWorker",
    (const char *)0x125,
    0,
    v6);
  if ( g_fInitialized )
  {
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\prefbinasync.cpp",
      0x12Eu,
      L"PrefBin already Initialized");
    v0 = -2147418113;
  }
  else
  {
    g_hStopPrefLoop = CreateEventW(0, 1, 0, 0);
    if ( g_hStopPrefLoop )
    {
      g_hSetCookie = CreateEventW(0, 1, 0, 0);
      if ( g_hSetCookie )
      {
        g_hResetCookie = CreateEventW(0, 1, 0, 0);
        if ( g_hResetCookie )
        {
          g_hPrefBinThread = IDCRLCreateThread((LPTHREAD_START_ROUTINE)SetPrefBinLoop, 0, v4);
          if ( g_hPrefBinThread )
          {
            v0 = v9;
            g_fInitialized = 1;
            goto LABEL_22;
          }
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v2 = L"Could not create prefbin thread, will fall back to sync SetPrefBinCookie. 0x%x";
          v3 = 341;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v2 = L"Could not create reset cookie event, will fall back to sync SetPrefBinCookie. 0x%x";
          v3 = 332;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v2 = L"Could not create set cookie event, will fall back to sync SetPrefBinCookie. 0x%x";
        v3 = 322;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v2 = L"Could not create stop event, will fall back to sync SetPrefBinCookie. 0x%x";
      v3 = 312;
    }
    LODWORD(v7) = LastError;
    v9 = LastError;
    TracePrintW(2u, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\prefbinasync.cpp", v3, v2, v7);
  }
  v9 = v0;
LABEL_22:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v8);
  return v0;
}

```

## disassembly

```asm
0x1800372d0  mov     [rsp-8+arg_8], rbx
0x1800372d5  mov     [rsp-8+arg_10], rsi
0x1800372da  push    rbp
0x1800372db  mov     rbp, rsp
0x1800372de  sub     rsp, 50h
0x1800372e2  xor     ebx, ebx
0x1800372e4  lea     rdx, aInitprefbinwor; "InitPrefBinWorker"
0x1800372eb  lea     rax, [rbp+arg_0]
0x1800372ef  mov     [rbp+arg_0], ebx
0x1800372f2  lea     rsi, aClientcoreDsEx_0; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x1800372f9  mov     [rbp+var_20], rdx
0x1800372fd  mov     rcx, rsi; this
0x180037300  mov     [rbp+var_18], rax
0x180037304  xor     r9d, r9d; unsigned int
0x180037307  mov     [rbp+var_10], rbx
0x18003730b  mov     r8d, 125h; char *
0x180037311  mov     [rbp+var_8], rbx
0x180037315  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003731a  cmp     cs:?g_fInitialized@@3HA, ebx; int g_fInitialized
0x180037320  jz      short loc_180037347
0x180037322  lea     r9, aPrefbinAlready; "PrefBin already Initialized"
0x180037329  mov     r8d, 12Eh; unsigned int
0x18003732f  mov     rdx, rsi; char *
0x180037332  lea     ecx, [rbx+2]; unsigned __int8
0x180037335  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003733a  mov     ebx, 8000FFFFh
0x18003733f  mov     [rbp+arg_0], ebx
0x180037342  jmp     loc_180037466
0x180037347  xor     r9d, r9d; lpName
0x18003734a  xor     r8d, r8d; bInitialState
0x18003734d  xor     ecx, ecx; lpEventAttributes
0x18003734f  lea     edx, [r9+1]; bManualReset
0x180037353  call    cs:__imp_CreateEventW
0x180037359  mov     cs:?g_hStopPrefLoop@@3PEAXEA, rax; void * g_hStopPrefLoop
0x180037360  test    rax, rax
0x180037363  jnz     short loc_18003739A
0x180037365  call    cs:__imp_GetLastError
0x18003736b  test    eax, eax
0x18003736d  jle     short loc_180037377
0x18003736f  movzx   eax, ax
0x180037372  or      eax, 80070000h
0x180037377  lea     r9, aCouldNotCreate; "Could not create stop event, will fall "...
0x18003737e  mov     r8d, 138h; unsigned int
0x180037384  mov     rdx, rsi; char *
0x180037387  mov     [rsp+50h+var_30], eax
0x18003738b  mov     ecx, 2; unsigned __int8
0x180037390  mov     [rbp+arg_0], eax
0x180037393  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180037398  jmp     short loc_18003733F
0x18003739a  xor     r9d, r9d; lpName
0x18003739d  xor     r8d, r8d; bInitialState
0x1800373a0  xor     ecx, ecx; lpEventAttributes
0x1800373a2  lea     edx, [r9+1]; bManualReset
0x1800373a6  call    cs:__imp_CreateEventW
0x1800373ac  mov     cs:?g_hSetCookie@@3PEAXEA, rax; void * g_hSetCookie
0x1800373b3  test    rax, rax
0x1800373b6  jnz     short loc_1800373D9
0x1800373b8  call    cs:__imp_GetLastError
0x1800373be  test    eax, eax
0x1800373c0  jle     short loc_1800373CA
0x1800373c2  movzx   eax, ax
0x1800373c5  or      eax, 80070000h
0x1800373ca  lea     r9, aCouldNotCreate_0; "Could not create set cookie event, will"...
0x1800373d1  mov     r8d, 142h
0x1800373d7  jmp     short loc_180037384
0x1800373d9  xor     r9d, r9d; lpName
0x1800373dc  xor     r8d, r8d; bInitialState
0x1800373df  xor     ecx, ecx; lpEventAttributes
0x1800373e1  lea     edx, [r9+1]; bManualReset
0x1800373e5  call    cs:__imp_CreateEventW
0x1800373eb  mov     cs:?g_hResetCookie@@3PEAXEA, rax; void * g_hResetCookie
0x1800373f2  test    rax, rax
0x1800373f5  jnz     short loc_18003741B
0x1800373f7  call    cs:__imp_GetLastError
0x1800373fd  test    eax, eax
0x1800373ff  jle     short loc_180037409
0x180037401  movzx   eax, ax
0x180037404  or      eax, 80070000h
0x180037409  lea     r9, aCouldNotCreate_2; "Could not create reset cookie event, wi"...
0x180037410  mov     r8d, 14Ch
0x180037416  jmp     loc_180037384
0x18003741b  xor     edx, edx; lpParameter
0x18003741d  lea     rcx, ?SetPrefBinLoop@@YAKPEAX@Z; lpStartAddress
0x180037424  call    ?IDCRLCreateThread@@YAPEAXP6AKPEAX@Z0H@Z; IDCRLCreateThread(ulong (*)(void *),void *,int)
0x180037429  mov     cs:?g_hPrefBinThread@@3PEAXEA, rax; void * g_hPrefBinThread
0x180037430  test    rax, rax
0x180037433  jnz     short loc_180037459
0x180037435  call    cs:__imp_GetLastError
0x18003743b  test    eax, eax
0x18003743d  jle     short loc_180037447
0x18003743f  movzx   eax, ax
0x180037442  or      eax, 80070000h
0x180037447  lea     r9, aCouldNotCreate_1; "Could not create prefbin thread, will f"...
0x18003744e  mov     r8d, 155h
0x180037454  jmp     loc_180037384
0x180037459  mov     ebx, [rbp+arg_0]
0x18003745c  mov     cs:?g_fInitialized@@3HA, 1; int g_fInitialized
0x180037466  lea     rcx, [rbp+var_20]
0x18003746a  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003746f  mov     rsi, [rsp+50h+arg_10]
0x180037474  mov     eax, ebx
0x180037476  mov     rbx, [rsp+50h+arg_8]
0x18003747b  add     rsp, 50h
0x18003747f  pop     rbp
0x180037480  retn
```
