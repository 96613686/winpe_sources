# WdsSetupLogMessageW

- ea: `0x18001dc70`
- end: `0x18001e0b0`
- name: `WdsSetupLogMessageW`
- size: `1088`
- prototype: `__int64 __fastcall(int, int, int, int, int, unsigned __int16 *, __int64, LPCWSTR lpModuleName, int, __int64, int)`
- caller_count: `74`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180001f24`
- `0x180002364`
- `0x180002958`
- `0x180002c4c`
- `0x180002d14`
- `0x180002f5c`
- `0x180003108`
- `0x180003680`
- `0x180003804`
- `0x180003bbc`
- `0x180003d18`
- `0x180004164`
- `0x1800044f0`
- `0x180004830`
- `0x180004bc4`
- `0x180004e6c`
- `0x18000525c`
- `0x180005760`
- `0x180005950`
- `0x180005eac`
- `0x180005ff0`
- `0x180006170`
- `0x180006398`
- `0x18000665c`
- `0x180006890`
- `0x180006a84`
- `0x180006d64`
- `0x18000720c`
- `0x180007330`
- `0x1800076a4`
- `0x180007c60`
- `0x180008380`
- `0x1800086c4`
- `0x1800087e0`
- `0x180008f30`
- `0x180009030`
- `0x1800096f8`
- `0x180009f2c`
- `0x18000a288`
- `0x18000a6b8`
- `0x18000a8f0`
- `0x18000ad30`
- `0x18000af7c`
- `0x18000b1f0`
- `0x18000b484`
- `0x18000b6c4`
- `0x18000b860`
- `0x18000bca4`
- `0x18000bd60`
- `0x18000bf40`

## callees

- `0x180005e18`
- `0x18001a3f4`
- `0x18001a85c`
- `0x18001abcc`
- `0x18001b348`
- `0x18001b990`
- `0x18001ba40`
- `0x18001ca90`
- `0x18001dc70`
- `0x180022e90`
- `0x1800274de`
- `0x180027510`
- `0x18002a010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001de37`
- `msvcrt!wcsrchr` at `0x18001de37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dd97`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dd97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001deff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e01c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001deff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e01c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dd83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001deeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dd83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001deeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e008`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e06d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e06d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e05a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e05a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001df21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001df21`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18001e034`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x18001e034`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001de1e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18001de1e`

## pseudocode

```c
__int64 __fastcall WdsSetupLogMessageW(
        int *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int16 *a6,
        const unsigned __int16 *a7,
        LPCWSTR lpModuleName,
        int a9,
        __int64 a10,
        int a11)
{
  const unsigned __int16 *v12; // r14
  DWORD LastError; // eax
  DWORD v16; // esi
  __int64 v17; // rax
  __int64 v18; // rsi
  unsigned int v19; // r14d
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // r12
  HMODULE v23; // rax
  wchar_t *v24; // rax
  int v25; // ecx
  unsigned int v26; // edx
  int v27; // eax
  char *v28; // rbx
  HANDLE v29; // rax
  __int64 (__fastcall *v30)(struct ILogManager *, __int64, __int64, _QWORD, __int64, __int64, unsigned int, _QWORD, const unsigned __int16 *, unsigned int, __int64, unsigned int, DWORD, unsigned __int16 *, wchar_t *, WCHAR *, int, __int64, int, _QWORD); // r15
  double CurrentDateTime; // xmm0_8
  DWORD CurrentThreadId; // eax
  unsigned int v33; // edi
  DWORD v34; // ebx
  __int64 v35; // rsi
  unsigned int v36; // ebp
  __int64 MinorTask; // r14
  __int64 MajorTask; // rax
  unsigned int v39; // ebx
  HANDLE v40; // rax
  DWORD dwErrCode; // [rsp+B0h] [rbp-298h]
  int v43; // [rsp+B4h] [rbp-294h]
  WCHAR *v44; // [rsp+B8h] [rbp-290h]
  unsigned __int16 *v45; // [rsp+C0h] [rbp-288h]
  WCHAR Filename[10]; // [rsp+E0h] [rbp-268h] BYREF
  _BYTE v48[508]; // [rsp+F4h] [rbp-254h] BYREF

  v12 = a7;
  LastError = GetLastError();
  wcscpy(Filename, L"<unknown>");
  v16 = LastError;
  dwErrCode = LastError;
  memset_0(v48, 0, 0x1F4u);
  if ( !g_pLogManager || !a1 )
    return 0;
  a1[1] |= a2;
  v44 = 0;
  v43 = 0;
  if ( !a4 )
  {
    v22 = 0;
LABEL_12:
    v45 = v22;
    goto LABEL_13;
  }
  v45 = 0;
  v17 = -1;
  do
    ++v17;
  while ( *(_BYTE *)(a4 + v17) );
  v18 = (unsigned int)(v17 + 1);
  v19 = v17 + 1;
  ProcessHeap = GetProcessHeap();
  v21 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v18);
  v22 = v21;
  if ( v21 )
  {
    if ( (int)StringCchPrintfW(v21, v19, L"%S", a4) < 0 )
      v22[(unsigned int)(v18 - 1)] = 0;
    v16 = dwErrCode;
    v12 = a7;
    goto LABEL_12;
  }
  v16 = dwErrCode;
  v12 = a7;
LABEL_13:
  if ( lpModuleName )
  {
    v23 = (HMODULE)pIPtoHModule(lpModuleName);
    if ( v23 && (GetModuleFileNameW(v23, Filename, 0x104u), (v24 = wcsrchr(Filename, 0x5Cu)) != 0) )
      v44 = v24 + 1;
    else
      v44 = Filename;
  }
  v25 = *a1;
  if ( *a1 == 1694498816 || !v25 )
  {
    v26 = g_dwPrevFlags;
    if ( (g_dwPrevFlags & 0x80000) != 0 )
    {
      v27 = 1795162112;
      if ( v25 != 1694498816 )
        v27 = 0x2000000;
      v25 = v27;
      *a1 = v27;
    }
    if ( (v26 & 0x40000) != 0 )
      v43 = 1;
  }
  if ( ((v25 - 0x1000000) & 0xFEFFFFFF) == 0 && (unsigned int)ShouldTelemetryAssert() )
  {
    v28 = BuildTelAssertReportW(*((const unsigned __int16 **)a1 + 1), v12, a6);
    MicrosoftTelemetryAssertTriggeredArgs(v28, a5, v16);
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
  }
  v30 = *(__int64 (__fastcall **)(struct ILogManager *, __int64, __int64, _QWORD, __int64, __int64, unsigned int, _QWORD, const unsigned __int16 *, unsigned int, __int64, unsigned int, DWORD, unsigned __int16 *, wchar_t *, WCHAR *, int, __int64, int, _QWORD))(*(_QWORD *)g_pLogManager + 40LL);
  CurrentDateTime = GetCurrentDateTime();
  CurrentThreadId = GetCurrentThreadId();
  v33 = g_ProcessID;
  v34 = CurrentThreadId;
  v35 = *((_QWORD *)a1 + 1);
  v36 = a1[1];
  MinorTask = GetMinorTask();
  MajorTask = GetMajorTask();
  v39 = v30(
          g_pLogManager,
          17,
          a3,
          (unsigned int)*a1,
          MajorTask,
          MinorTask,
          a5,
          0,
          a7,
          v36,
          v35,
          v33,
          v34,
          v45,
          g_ProcessExeW,
          v44,
          a9,
          a10,
          a11,
          *(_QWORD *)&CurrentDateTime);
  if ( v22 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v22);
  }
  if ( v39 == 4 )
  {
    WdsSetupLogDestroy();
    ExitProcess(0);
  }
  if ( v43 )
    RaiseException(0xC0000025, 1u, 0, 0);
  SetLastError(dwErrCode);
  return v39;
}

```

## disassembly

```asm
0x18001dc70  mov     rax, rsp
0x18001dc73  mov     [rax+10h], rbx
0x18001dc77  push    rbp
0x18001dc78  push    rsi
0x18001dc79  push    rdi
0x18001dc7a  push    r12
0x18001dc7c  push    r13
0x18001dc7e  push    r14
0x18001dc80  push    r15
0x18001dc82  sub     rsp, 310h
0x18001dc89  movaps  xmmword ptr [rax-48h], xmm6
0x18001dc8d  mov     rax, cs:__security_cookie
0x18001dc94  xor     rax, rsp
0x18001dc97  mov     [rsp+348h+var_58], rax
0x18001dc9f  mov     rax, [rsp+348h+arg_48]
0x18001dca7  mov     rdi, r9
0x18001dcaa  mov     r14, [rsp+348h+arg_30]
0x18001dcb2  mov     ebx, edx
0x18001dcb4  mov     r15, [rsp+348h+arg_28]
0x18001dcbc  mov     r13, rcx
0x18001dcbf  mov     rbp, [rsp+348h+lpModuleName]
0x18001dcc7  mov     [rsp+348h+var_280], r14
0x18001dccf  mov     [rsp+348h+var_278], rax
0x18001dcd7  mov     [rsp+348h+var_270], r8
0x18001dcdf  call    cs:__imp_GetLastError
0x18001dce6  nop     dword ptr [rax+rax+00h]
0x18001dceb  movups  xmm0, xmmword ptr cs:aUnknown; "<unknown>"
0x18001dcf2  mov     ecx, dword ptr cs:aUnknown+10h; ">"
0x18001dcf8  xor     edx, edx; Val
0x18001dcfa  mov     [rsp+348h+var_258], ecx
0x18001dd01  mov     r8d, 1F4h; Size
0x18001dd07  lea     rcx, [rsp+348h+var_254]; void *
0x18001dd0f  movaps  xmmword ptr [rsp+348h+Filename], xmm0
0x18001dd17  mov     esi, eax
0x18001dd19  mov     [rsp+348h+dwErrCode], eax
0x18001dd20  call    memset_0
0x18001dd25  cmp     cs:?g_pLogManager@@3PEAVILogManager@@EA, 0; ILogManager * g_pLogManager
0x18001dd2d  jz      loc_18001E07D
0x18001dd33  test    r13, r13
0x18001dd36  jz      loc_18001E07D
0x18001dd3c  or      [r13+4], ebx
0x18001dd40  mov     [rsp+348h+var_290], 0
0x18001dd4c  mov     [rsp+348h+var_294], 0
0x18001dd57  test    rdi, rdi
0x18001dd5a  jz      loc_18001DDF0
0x18001dd60  mov     [rsp+348h+var_288], 0
0x18001dd6c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001dd70  inc     rax
0x18001dd73  cmp     byte ptr [rdi+rax], 0
0x18001dd77  jnz     short loc_18001DD70
0x18001dd79  lea     esi, [rax+1]
0x18001dd7c  mov     r14d, esi
0x18001dd7f  lea     rbx, [rsi+rsi]
0x18001dd83  call    cs:__imp_GetProcessHeap
0x18001dd8a  nop     dword ptr [rax+rax+00h]
0x18001dd8f  mov     r8, rbx; dwBytes
0x18001dd92  xor     edx, edx; dwFlags
0x18001dd94  mov     rcx, rax; hHeap
0x18001dd97  call    cs:__imp_HeapAlloc
0x18001dd9e  nop     dword ptr [rax+rax+00h]
0x18001dda3  mov     r12, rax
0x18001dda6  test    rax, rax
0x18001dda9  jz      short loc_18001DDDF
0x18001ddab  mov     r9, rdi
0x18001ddae  lea     r8, aS_5; "%S"
0x18001ddb5  mov     edx, r14d; unsigned __int64
0x18001ddb8  mov     rcx, rax; unsigned __int16 *
0x18001ddbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ddc0  test    eax, eax
0x18001ddc2  jns     short loc_18001DDCE
0x18001ddc4  lea     ecx, [rsi-1]
0x18001ddc7  xor     eax, eax
0x18001ddc9  mov     [r12+rcx*2], ax
0x18001ddce  mov     esi, [rsp+348h+dwErrCode]
0x18001ddd5  mov     r14, [rsp+348h+var_280]
0x18001dddd  jmp     short loc_18001DDF3
0x18001dddf  mov     esi, [rsp+348h+dwErrCode]
0x18001dde6  mov     r14, [rsp+348h+var_280]
0x18001ddee  jmp     short loc_18001DDFB
0x18001ddf0  xor     r12d, r12d
0x18001ddf3  mov     [rsp+348h+var_288], r12
0x18001ddfb  test    rbp, rbp
0x18001ddfe  jz      short loc_18001DE69
0x18001de00  mov     rcx, rbp; lpModuleName
0x18001de03  call    pIPtoHModule
0x18001de08  test    rax, rax
0x18001de0b  jz      short loc_18001DE59
0x18001de0d  mov     r8d, 104h; nSize
0x18001de13  lea     rdx, [rsp+348h+Filename]; lpFilename
0x18001de1b  mov     rcx, rax; hModule
0x18001de1e  call    cs:__imp_GetModuleFileNameW
0x18001de25  nop     dword ptr [rax+rax+00h]
0x18001de2a  mov     edx, 5Ch ; '\'; Ch
0x18001de2f  lea     rcx, [rsp+348h+Filename]; Str
0x18001de37  call    cs:__imp_wcsrchr
0x18001de3e  nop     dword ptr [rax+rax+00h]
0x18001de43  mov     rdi, rax
0x18001de46  test    rax, rax
0x18001de49  jz      short loc_18001DE59
0x18001de4b  add     rdi, 2
0x18001de4f  mov     [rsp+348h+var_290], rdi
0x18001de57  jmp     short loc_18001DE69
0x18001de59  lea     rax, [rsp+348h+Filename]
0x18001de61  mov     [rsp+348h+var_290], rax
0x18001de69  mov     ecx, [r13+0]
0x18001de6d  mov     r9d, 65000000h
0x18001de73  cmp     ecx, r9d
0x18001de76  jz      short loc_18001DE7C
0x18001de78  test    ecx, ecx
0x18001de7a  jnz     short loc_18001DEB1
0x18001de7c  mov     edx, cs:?g_dwPrevFlags@@3KA; ulong g_dwPrevFlags
0x18001de82  bt      edx, 13h
0x18001de86  jnb     short loc_18001DEA0
0x18001de88  cmp     ecx, r9d
0x18001de8b  mov     eax, 6B000000h
0x18001de90  mov     r8d, 2000000h
0x18001de96  cmovnz  eax, r8d
0x18001de9a  mov     ecx, eax
0x18001de9c  mov     [r13+0], eax
0x18001dea0  bt      edx, 12h
0x18001dea4  jnb     short loc_18001DEB1
0x18001dea6  mov     [rsp+348h+var_294], 1
0x18001deb1  lea     eax, [rcx-1000000h]
0x18001deb7  test    eax, 0FEFFFFFFh
0x18001debc  jnz     short loc_18001DF0B
0x18001debe  call    ?ShouldTelemetryAssert@@YAHXZ; ShouldTelemetryAssert(void)
0x18001dec3  test    eax, eax
0x18001dec5  jz      short loc_18001DF0B
0x18001dec7  mov     rcx, [r13+8]; unsigned __int16 *
0x18001decb  mov     r8, r15; unsigned __int16 *
0x18001dece  mov     rdx, r14; unsigned __int16 *
0x18001ded1  call    ?BuildTelAssertReportW@@YAPEADPEBG00@Z; BuildTelAssertReportW(ushort const *,ushort const *,ushort const *)
0x18001ded6  mov     rbx, rax
0x18001ded9  mov     edx, [rsp+348h+arg_20]
0x18001dee0  mov     r8d, esi
0x18001dee3  mov     rcx, rax
0x18001dee6  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001deeb  call    cs:__imp_GetProcessHeap
0x18001def2  nop     dword ptr [rax+rax+00h]
0x18001def7  mov     r8, rbx; lpMem
0x18001defa  xor     edx, edx; dwFlags
0x18001defc  mov     rcx, rax; hHeap
0x18001deff  call    cs:__imp_HeapFree
0x18001df06  nop     dword ptr [rax+rax+00h]
0x18001df0b  mov     rax, cs:?g_pLogManager@@3PEAVILogManager@@EA; ILogManager * g_pLogManager
0x18001df12  mov     rcx, [rax]
0x18001df15  mov     r15, [rcx+28h]
0x18001df19  call    ?GetCurrentDateTime@@YANXZ; GetCurrentDateTime(void)
0x18001df1e  movaps  xmm6, xmm0
0x18001df21  call    cs:__imp_GetCurrentThreadId
0x18001df28  nop     dword ptr [rax+rax+00h]
0x18001df2d  mov     edi, cs:?g_ProcessID@@3KA; ulong g_ProcessID
0x18001df33  mov     ebx, eax
0x18001df35  mov     rsi, [r13+8]
0x18001df39  mov     ebp, [r13+4]
0x18001df3d  call    GetMinorTask
0x18001df42  mov     r14, rax
0x18001df45  call    GetMajorTask
0x18001df4a  mov     ecx, [rsp+348h+arg_50]
0x18001df51  mov     edx, 11h
0x18001df56  mov     r9d, [r13+0]
0x18001df5a  mov     r8, [rsp+348h+var_270]
0x18001df62  movsd   [rsp+348h+var_2B0], xmm6
0x18001df6b  mov     [rsp+348h+var_2B8], ecx
0x18001df72  mov     rcx, [rsp+348h+var_278]
0x18001df7a  mov     [rsp+348h+var_2C0], rcx
0x18001df82  mov     ecx, [rsp+348h+arg_40]
0x18001df89  mov     [rsp+348h+var_2C8], ecx
0x18001df90  mov     rcx, [rsp+348h+var_290]
0x18001df98  mov     [rsp+348h+var_2D0], rcx
0x18001df9d  lea     rcx, ?g_ProcessExeW@@3PAGA; "<unknown>"
0x18001dfa4  mov     [rsp+348h+var_2D8], rcx
0x18001dfa9  mov     rcx, [rsp+348h+var_288]
0x18001dfb1  mov     [rsp+348h+var_2E0], rcx
0x18001dfb6  mov     rcx, [rsp+348h+var_280]
0x18001dfbe  mov     [rsp+348h+var_2E8], ebx
0x18001dfc2  mov     [rsp+348h+var_2F0], edi
0x18001dfc6  mov     [rsp+348h+var_2F8], rsi
0x18001dfcb  mov     [rsp+348h+var_300], ebp
0x18001dfcf  mov     [rsp+348h+var_308], rcx
0x18001dfd4  mov     ecx, [rsp+348h+arg_20]
0x18001dfdb  mov     [rsp+348h+var_310], 0
0x18001dfe4  mov     [rsp+348h+var_318], ecx
0x18001dfe8  mov     rcx, cs:?g_pLogManager@@3PEAVILogManager@@EA; ILogManager * g_pLogManager
0x18001dfef  mov     [rsp+348h+var_320], r14
0x18001dff4  mov     [rsp+348h+var_328], rax
0x18001dff9  mov     rax, r15
0x18001dffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e001  mov     ebx, eax
0x18001e003  test    r12, r12
0x18001e006  jz      short loc_18001E028
0x18001e008  call    cs:__imp_GetProcessHeap
0x18001e00f  nop     dword ptr [rax+rax+00h]
0x18001e014  mov     r8, r12; lpMem
0x18001e017  xor     edx, edx; dwFlags
0x18001e019  mov     rcx, rax; hHeap
0x18001e01c  call    cs:__imp_HeapFree
0x18001e023  nop     dword ptr [rax+rax+00h]
0x18001e028  cmp     ebx, 4
0x18001e02b  jnz     short loc_18001E041
0x18001e02d  call    WdsSetupLogDestroy
0x18001e032  xor     ecx, ecx; uExitCode
0x18001e034  call    cs:__imp_ExitProcess
0x18001e041  cmp     [rsp+348h+var_294], 0
0x18001e049  jz      short loc_18001E066
0x18001e04b  xor     r9d, r9d; lpArguments
0x18001e04e  xor     r8d, r8d; nNumberOfArguments
0x18001e051  mov     ecx, 0C0000025h; dwExceptionCode
0x18001e056  lea     edx, [r9+1]; dwExceptionFlags
0x18001e05a  call    cs:__imp_RaiseException
0x18001e061  nop     dword ptr [rax+rax+00h]
0x18001e066  mov     ecx, [rsp+348h+dwErrCode]; dwErrCode
0x18001e06d  call    cs:__imp_SetLastError
0x18001e074  nop     dword ptr [rax+rax+00h]
0x18001e079  mov     eax, ebx
0x18001e07b  jmp     short loc_18001E07F
0x18001e07d  xor     eax, eax
0x18001e07f  mov     rcx, [rsp+348h+var_58]
0x18001e087  xor     rcx, rsp; StackCookie
0x18001e08a  call    __security_check_cookie
0x18001e08f  lea     r11, [rsp+348h+var_38]
0x18001e097  mov     rbx, [r11+48h]
0x18001e09b  movaps  xmm6, xmmword ptr [r11-10h]
0x18001e0a0  mov     rsp, r11
0x18001e0a3  pop     r15
0x18001e0a5  pop     r14
0x18001e0a7  pop     r13
0x18001e0a9  pop     r12
0x18001e0ab  pop     rdi
0x18001e0ac  pop     rsi
0x18001e0ad  pop     rbp
0x18001e0ae  retn
```
