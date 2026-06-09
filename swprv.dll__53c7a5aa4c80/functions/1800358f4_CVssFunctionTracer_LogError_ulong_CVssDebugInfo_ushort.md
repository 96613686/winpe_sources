# CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)

- ea: `0x1800358f4`
- end: `0x180035f3e`
- name: `?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z`
- size: `1610`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006910`
- `0x180009db0`
- `0x180011178`
- `0x18001b130`
- `0x18001f47c`
- `0x180020c6c`
- `0x180021bc4`
- `0x180034cfc`
- `0x180035f44`
- `0x180036c10`
- `0x180036f10`
- `0x180037080`
- `0x1800372e8`
- `0x18003750c`
- `0x1800377c4`
- `0x18003ced0`
- `0x18003e960`
- `0x1800402e4`
- `0x180040cb0`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800339c0`
- `0x180033a8c`
- `0x180033c2c`
- `0x180033c78`
- `0x180034f3c`
- `0x180035198`
- `0x180035680`
- `0x1800358f4`
- `0x180036360`
- `0x1800367b8`
- `0x180036af8`
- `0x180041990`
- `0x180041a08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035a88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035a88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035a80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e40`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180035a65`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180035a6e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180035a65`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180035a6e`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180035e32`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180035e32`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180035c50`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180035c50`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180035d5c`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180035d5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ef0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ef0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssFunctionTracer::LogError(__int64 a1, DWORD a2, __int64 a3, WORD a4)
{
  __int64 v4; // r14
  CVssFunctionTracer *v6; // rcx
  __int64 dwDataSize; // r15
  __int64 v8; // rax
  int v9; // esi
  const wchar_t *CommandLineW; // r12
  LPWSTR v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  unsigned __int16 v15; // bx
  WORD wNumStrings; // r12
  unsigned __int16 v17; // di
  unsigned __int16 *CurrentContexts; // rax
  unsigned __int16 *v19; // rbx
  const WCHAR *v20; // rsi
  unsigned int v21; // edi
  HANDLE v22; // rsi
  DWORD LastError; // ebx
  int v24; // ecx
  DWORD v25; // edi
  DWORD v26; // ebx
  int v27; // ecx
  const unsigned __int16 *v31; // [rsp+98h] [rbp-1AF0h] BYREF
  const unsigned __int16 *v32; // [rsp+A0h] [rbp-1AE8h]
  const unsigned __int16 *v33; // [rsp+A8h] [rbp-1AE0h]
  int v34; // [rsp+B0h] [rbp-1AD8h]
  int v35; // [rsp+B4h] [rbp-1AD4h]
  int v36; // [rsp+B8h] [rbp-1AD0h]
  _BYTE v37[120]; // [rsp+C0h] [rbp-1AC8h] BYREF
  int v38; // [rsp+138h] [rbp-1A50h]
  unsigned int v39; // [rsp+140h] [rbp-1A48h] BYREF
  LPVOID v40[4]; // [rsp+150h] [rbp-1A38h] BYREF
  unsigned int v41; // [rsp+174h] [rbp-1A14h]
  _com_error *v42; // [rsp+1C0h] [rbp-19C8h] BYREF
  const std::exception *v43; // [rsp+1C8h] [rbp-19C0h] BYREF
  _BYTE v44[176]; // [rsp+1D0h] [rbp-19B8h] BYREF
  LPCWSTR Strings[3]; // [rsp+280h] [rbp-1908h] BYREF
  int v46; // [rsp+298h] [rbp-18F0h]
  int v47; // [rsp+29Ch] [rbp-18ECh]
  int v48; // [rsp+2A0h] [rbp-18E8h]
  _BYTE v49[120]; // [rsp+2A8h] [rbp-18E0h] BYREF
  int v50; // [rsp+320h] [rbp-1868h]
  unsigned __int16 v51; // [rsp+330h] [rbp-1858h] BYREF
  _BYTE v52[2046]; // [rsp+332h] [rbp-1856h] BYREF
  char RawData[4112]; // [rsp+B30h] [rbp-1058h] BYREF

  v4 = a3;
  Strings[0] = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
  Strings[1] = L"CVssFunctionTracer::LogError";
  Strings[2] = L"TRCTRCC";
  v46 = 2241;
  v47 = 11;
  v48 = 255;
  v50 = 0x1000000;
  memset_0(v49, 0, sizeof(v49));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v40, (__int64)Strings, 0);
  memset_0(Strings, 0, 0x80u);
  memset_0(RawData, 0, 0x1001u);
  if ( (unsigned int)*(unsigned __int16 *)(v4 + 160) + 1 < 0xF )
  {
    v51 = 0;
    memset_0(v52, 0, sizeof(v52));
    CVssFunctionTracer::GetCurrentUserName(v6, &v51);
    dwDataSize = -1;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v52[2 * v8 - 2] );
    v9 = 8 * (((int)v8 + 7) / 8);
    CommandLineW = GetCommandLineW();
    v11 = GetCommandLineW();
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    StringCchPrintfA(
      RawData,
      0x1000u,
      "- Code: %8ls%08lu- Call: %8ls%08lu- PID:  %08lu- TID:  %08lu- CMD:  %-*ls- User: %-*ls",
      *(const wchar_t **)(v4 + 16),
      *(_DWORD *)(v4 + 24),
      *(const wchar_t **)(a1 + 24),
      *(_DWORD *)(a1 + 32),
      CurrentProcessId,
      CurrentThreadId,
      8 * (((int)v12 + 7) / 8),
      CommandLineW,
      v9,
      &v51);
    do
      ++dwDataSize;
    while ( RawData[dwDataSize] );
    v15 = *(_WORD *)(v4 + 160);
    wNumStrings = v15 + 1;
    v17 = 0;
    if ( v15 )
    {
      memcpy_0(Strings, (const void *)(v4 + 40), 8LL * *(unsigned __int16 *)(v4 + 160));
      do
        ++v17;
      while ( v17 < v15 );
    }
    try
    {
      CurrentContexts = CVssFunctionTracer::GetCurrentContexts((CVssFunctionTracer *)a1);
      v19 = CurrentContexts;
      v20 = &qword_180050E70;
      if ( CurrentContexts )
        v20 = CurrentContexts;
      Strings[v17] = v20;
      v21 = 100;
      if ( *(_DWORD *)(v4 + 32) != 255 )
        v21 = *(_DWORD *)(v4 + 32);
      v31 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
      v32 = L"CVssFunctionTracer::LogError";
      v33 = L"TRCTRCC";
      v34 = 2306;
      v35 = 11;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      v36 = 100;
      CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v44, (const struct CVssDebugInfo *)&v31);
      CVssFunctionTracer::TraceInternalWithFormat(a1, v44, L"CONTEXT", v21, L"Current context: '%s'", v20);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v31);
      v22 = RegisterEventSourceW(0, L"VSS");
      if ( !v22 )
      {
        LastError = GetLastError();
        v31 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
        v32 = L"CVssFunctionTracer::LogError";
        v33 = L"TRCTRCC";
        v34 = 2322;
        v35 = 11;
        v38 = 0x1000000;
        memset_0(v37, 0, sizeof(v37));
        v36 = 100;
        CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v44, (const struct CVssDebugInfo *)&v31);
        CVssFunctionTracer::Trace(v40, v44, L"Error on RegisterEventSourceW 0x%08lx", LastError);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v31);
        InternalThrow(v24);
      }
      if ( !ReportEventW(v22, a4, 0, a2, 0, wNumStrings, dwDataSize, Strings, RawData) )
      {
        v25 = GetLastError();
        v31 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
        v32 = L"CVssFunctionTracer::LogError";
        v33 = L"TRCTRCC";
        v34 = 2339;
        v35 = 11;
        v38 = 0x1000000;
        memset_0(v37, 0, sizeof(v37));
        v36 = 100;
        CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v44, (const struct CVssDebugInfo *)&v31);
        CVssFunctionTracer::Trace(v40, v44, L"Error on ReportEventW 0x%08lx", v25);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v31);
      }
      if ( !DeregisterEventSource(v22) )
      {
        v26 = GetLastError();
        v31 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
        v32 = L"CVssFunctionTracer::LogError";
        v33 = L"TRCTRCC";
        v34 = 2346;
        v35 = 11;
        v38 = 0x1000000;
        memset_0(v37, 0, sizeof(v37));
        v36 = 100;
        CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v44, (const struct CVssDebugInfo *)&v31);
        CVssFunctionTracer::Trace(v40, v44, L"Error on DeregisterEventSource 0x%08lx", v26);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v31);
        InternalThrow(v27);
      }
      CoTaskMemFree(v19);
    }
    catch ( long v39 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)v40,
        v39,
        L"base\\stor\\vss\\modules\\trace\\fntracer.cpp",
        L"TRCTRCC",
        L"CVssFunctionTracer::LogError",
        0x92Eu,
        v41);
      v4 = a3;
    }
    catch ( _com_error *v42 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)v40,
        v42,
        L"base\\stor\\vss\\modules\\trace\\fntracer.cpp",
        L"TRCTRCC",
        L"CVssFunctionTracer::LogError",
        0x92Eu,
        v41);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)v40,
        L"base\\stor\\vss\\modules\\trace\\fntracer.cpp",
        L"TRCTRCC",
        L"CVssFunctionTracer::LogError",
        0x92Eu,
        v41);
      v4 = a3;
    }
    catch ( const std::exception *v43 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)v40,
        v43,
        L"base\\stor\\vss\\modules\\trace\\fntracer.cpp",
        L"TRCTRCC",
        L"CVssFunctionTracer::LogError",
        0x92Eu,
        v41);
    }
    CVssFunctionTracer::~CVssFunctionTracer(v40);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v4);
  }
  else
  {
    CVssFunctionTracer::~CVssFunctionTracer(v40);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v4);
  }
}

```

## disassembly

```asm
0x1800358f4  push    rbx
0x1800358f6  push    rsi
0x1800358f7  push    rdi
0x1800358f8  push    r12
0x1800358fa  push    r13
0x1800358fc  push    r14
0x1800358fe  push    r15
0x180035900  mov     eax, 1B50h
0x180035905  call    _alloca_probe
0x18003590a  sub     rsp, rax
0x18003590d  mov     rax, cs:__security_cookie
0x180035914  xor     rax, rsp
0x180035917  mov     [rsp+1B88h+var_48], rax
0x18003591f  mov     [rsp+1B88h+var_1B18], r9w
0x180035925  mov     r14, r8
0x180035928  mov     [rsp+1B88h+dwEventID], edx
0x18003592f  mov     r13, rcx
0x180035932  mov     [rsp+1B88h+var_1B10], r8
0x180035937  lea     rax, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x18003593e  mov     [rsp+1B88h+Strings], rax
0x180035946  lea     rax, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x18003594d  mov     [rsp+1B88h+var_1900], rax
0x180035955  lea     rax, aTrctrcc; "TRCTRCC"
0x18003595c  mov     [rsp+1B88h+var_18F8], rax
0x180035964  mov     [rsp+1B88h+var_18F0], 8C1h
0x18003596f  mov     [rsp+1B88h+var_18EC], 0Bh
0x18003597a  mov     [rsp+1B88h+var_18E8], 0FFh
0x180035985  xor     ebx, ebx
0x180035987  mov     [rsp+1B88h+var_1868], 1000000h
0x180035992  lea     edi, [rbx+1]
0x180035995  xor     edx, edx; Val
0x180035997  lea     r8d, [rbx+78h]; Size
0x18003599b  lea     rcx, [rsp+1B88h+var_18E0]; void *
0x1800359a3  call    memset_0
0x1800359a8  xor     r8d, r8d
0x1800359ab  lea     rdx, [rsp+1B88h+Strings]
0x1800359b3  lea     rcx, [rsp+1B88h+var_1A38]
0x1800359bb  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800359c0  nop
0x1800359c1  xor     edx, edx; Val
0x1800359c3  lea     r8d, [rdi+7Fh]; Size
0x1800359c7  lea     rcx, [rsp+1B88h+Strings]; void *
0x1800359cf  call    memset_0
0x1800359d4  xor     edx, edx; Val
0x1800359d6  mov     r8d, 1001h; Size
0x1800359dc  lea     rcx, [rsp+1B88h+RawData]; void *
0x1800359e4  call    memset_0
0x1800359e9  movzx   eax, word ptr [r14+0A0h]
0x1800359f1  add     eax, edi
0x1800359f3  cmp     eax, 0Fh
0x1800359f6  jb      short loc_180035A13
0x1800359f8  lea     rcx, [rsp+1B88h+var_1A38]; this
0x180035a00  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180035a05  nop
0x180035a06  mov     rcx, r14; this
0x180035a09  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180035a0e  jmp     loc_180035F1B
0x180035a13  mov     [rsp+1B88h+var_1858], bx
0x180035a1b  xor     edx, edx; Val
0x180035a1d  mov     r8d, 7FEh; Size
0x180035a23  lea     rcx, [rsp+1B88h+var_1856]; void *
0x180035a2b  call    memset_0
0x180035a30  lea     rdx, [rsp+1B88h+var_1858]; unsigned __int16 *
0x180035a38  call    ?GetCurrentUserName@CVssFunctionTracer@@QEAAXPEAGK@Z; CVssFunctionTracer::GetCurrentUserName(ushort *,ulong)
0x180035a3d  lea     rcx, [rsp+1B88h+var_1858]
0x180035a45  or      r15, 0FFFFFFFFFFFFFFFFh
0x180035a49  mov     rax, r15
0x180035a4c  inc     rax
0x180035a4f  cmp     [rcx+rax*2], bx
0x180035a53  jnz     short loc_180035A4C
0x180035a55  add     eax, 7
0x180035a58  cdq
0x180035a59  mov     ecx, 8
0x180035a5e  idiv    ecx
0x180035a60  mov     esi, eax
0x180035a62  shl     esi, 3
0x180035a65  call    cs:__imp_GetCommandLineW
0x180035a6b  mov     r12, rax
0x180035a6e  call    cs:__imp_GetCommandLineW
0x180035a74  mov     rdi, r15
0x180035a77  inc     rdi
0x180035a7a  cmp     [rax+rdi*2], bx
0x180035a7e  jnz     short loc_180035A77
0x180035a80  call    cs:__imp_GetCurrentThreadId
0x180035a86  mov     ebx, eax
0x180035a88  call    cs:__imp_GetCurrentProcessId
0x180035a8e  mov     ecx, eax
0x180035a90  lea     eax, [rdi+7]
0x180035a93  cdq
0x180035a94  mov     r8d, 8
0x180035a9a  idiv    r8d
0x180035a9d  shl     eax, 3
0x180035aa0  lea     rdx, [rsp+1B88h+var_1858]
0x180035aa8  mov     [rsp+1B88h+var_1B28], rdx
0x180035aad  mov     [rsp+1B88h+var_1B30], esi
0x180035ab1  mov     [rsp+1B88h+var_1B38], r12
0x180035ab6  mov     [rsp+1B88h+var_1B40], eax
0x180035aba  mov     dword ptr [rsp+1B88h+lpRawData], ebx
0x180035abe  mov     dword ptr [rsp+1B88h+lpStrings], ecx
0x180035ac2  mov     eax, [r13+20h]
0x180035ac6  mov     [rsp+1B88h+dwDataSize], eax
0x180035aca  mov     rax, [r13+18h]
0x180035ace  mov     qword ptr [rsp+1B88h+wNumStrings], rax
0x180035ad3  mov     eax, [r14+18h]
0x180035ad7  mov     dword ptr [rsp+1B88h+lpUserSid], eax
0x180035adb  mov     r9, [r14+10h]
0x180035adf  lea     r8, aCode8ls08luCal; "- Code: %8ls%08lu- Call: %8ls%08lu- PID"...
0x180035ae6  mov     edx, 1000h; unsigned __int64
0x180035aeb  lea     rcx, [rsp+1B88h+RawData]; char *
0x180035af3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180035af8  lea     rax, [rsp+1B88h+RawData]
0x180035b00  inc     r15
0x180035b03  cmp     byte ptr [rax+r15], 0
0x180035b08  jnz     short loc_180035B00
0x180035b0a  movzx   ebx, word ptr [r14+0A0h]
0x180035b12  mov     esi, 1
0x180035b17  lea     r12d, [rsi+rbx]
0x180035b1b  xor     edi, edi
0x180035b1d  xor     eax, eax
0x180035b1f  cmp     ax, bx
0x180035b22  jnb     short loc_180035B44
0x180035b24  mov     r8d, ebx
0x180035b27  shl     r8, 3; Size
0x180035b2b  lea     rdx, [r14+28h]; Src
0x180035b2f  lea     rcx, [rsp+1B88h+Strings]; void *
0x180035b37  call    memcpy_0
0x180035b3c  add     di, si
0x180035b3f  cmp     di, bx
0x180035b42  jb      short loc_180035B3C
0x180035b44  mov     [rsp+1B88h+var_1AF8], 0
0x180035b50  mov     rcx, r13; this
0x180035b53  call    ?GetCurrentContexts@CVssFunctionTracer@@QEAAPEAGXZ; CVssFunctionTracer::GetCurrentContexts(void)
0x180035b58  mov     rbx, rax
0x180035b5b  mov     [rsp+1B88h+var_1AF8], rax
0x180035b63  lea     rsi, qword_180050E70
0x180035b6a  test    rax, rax
0x180035b6d  cmovnz  rsi, rax
0x180035b71  movzx   eax, di
0x180035b74  mov     [rsp+rax*8+1B88h+Strings], rsi
0x180035b7c  mov     edi, 64h ; 'd'
0x180035b81  cmp     dword ptr [r14+20h], 0FFh
0x180035b89  cmovnz  edi, [r14+20h]
0x180035b8e  lea     rax, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x180035b95  mov     [rsp+1B88h+var_1AF0], rax
0x180035b9d  lea     rax, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x180035ba4  mov     [rsp+1B88h+var_1AE8], rax
0x180035bac  lea     rax, aTrctrcc; "TRCTRCC"
0x180035bb3  mov     [rsp+1B88h+var_1AE0], rax
0x180035bbb  mov     [rsp+1B88h+var_1AD8], 902h
0x180035bc6  mov     [rsp+1B88h+var_1AD4], 0Bh
0x180035bd1  mov     [rsp+1B88h+var_1A50], 1000000h
0x180035bdc  xor     edx, edx; Val
0x180035bde  lea     r8d, [rdx+78h]; Size
0x180035be2  lea     rcx, [rsp+1B88h+var_1AC8]; void *
0x180035bea  call    memset_0
0x180035bef  mov     [rsp+1B88h+var_1AD0], 64h ; 'd'
0x180035bfa  lea     rdx, [rsp+1B88h+var_1AF0]; struct CVssDebugInfo *
0x180035c02  lea     rcx, [rsp+1B88h+var_19B8]; this
0x180035c0a  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180035c0f  mov     qword ptr [rsp+1B88h+wNumStrings], rsi
0x180035c14  lea     rax, aCurrentContext; "Current context: '%s'"
0x180035c1b  mov     [rsp+1B88h+lpUserSid], rax
0x180035c20  mov     r9d, edi
0x180035c23  lea     r8, aContext; "CONTEXT"
0x180035c2a  lea     rdx, [rsp+1B88h+var_19B8]
0x180035c32  mov     rcx, r13
0x180035c35  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1ZZ; CVssFunctionTracer::TraceInternalWithFormat(CVssDebugInfo,ushort const *,ulong,ushort const *,...)
0x180035c3a  lea     rcx, [rsp+1B88h+var_1AF0]; this
0x180035c42  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180035c47  lea     rdx, SourceName; "VSS"
0x180035c4e  xor     ecx, ecx; lpUNCServerName
0x180035c50  call    cs:__imp_RegisterEventSourceW
0x180035c56  mov     rsi, rax
0x180035c59  xor     r13d, r13d
0x180035c5c  test    rax, rax
0x180035c5f  jnz     loc_180035D1F
0x180035c65  call    cs:__imp_GetLastError
0x180035c6b  mov     ebx, eax
0x180035c6d  lea     rax, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x180035c74  mov     [rsp+1B88h+var_1AF0], rax
0x180035c7c  lea     rax, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x180035c83  mov     [rsp+1B88h+var_1AE8], rax
0x180035c8b  lea     rax, aTrctrcc; "TRCTRCC"
0x180035c92  mov     [rsp+1B88h+var_1AE0], rax
0x180035c9a  mov     [rsp+1B88h+var_1AD8], 912h
0x180035ca5  mov     [rsp+1B88h+var_1AD4], 0Bh
0x180035cb0  mov     [rsp+1B88h+var_1A50], 1000000h
0x180035cbb  xor     edx, edx; Val
0x180035cbd  lea     r8d, [rsi+78h]; Size
0x180035cc1  lea     rcx, [rsp+1B88h+var_1AC8]; void *
0x180035cc9  call    memset_0
0x180035cce  mov     [rsp+1B88h+var_1AD0], 64h ; 'd'
0x180035cd9  lea     rdx, [rsp+1B88h+var_1AF0]; struct CVssDebugInfo *
0x180035ce1  lea     rcx, [rsp+1B88h+var_19B8]; this
0x180035ce9  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180035cee  mov     r9d, ebx
0x180035cf1  lea     r8, aErrorOnRegiste; "Error on RegisterEventSourceW 0x%08lx"
0x180035cf8  lea     rdx, [rsp+1B88h+var_19B8]
0x180035d00  lea     rcx, [rsp+1B88h+var_1A38]
0x180035d08  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180035d0d  lea     rcx, [rsp+1B88h+var_1AF0]; this
0x180035d15  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180035d1a  call    ?InternalThrow@@YAXJ@Z; InternalThrow(long)
0x180035d1f  xor     r8d, r8d; wCategory
0x180035d22  lea     rax, [rsp+1B88h+RawData]
0x180035d2a  mov     [rsp+1B88h+lpRawData], rax; lpRawData
0x180035d2f  lea     rax, [rsp+1B88h+Strings]
0x180035d37  mov     [rsp+1B88h+lpStrings], rax; lpStrings
0x180035d3c  mov     [rsp+1B88h+dwDataSize], r15d; dwDataSize
0x180035d41  mov     [rsp+1B88h+wNumStrings], r12w; wNumStrings
0x180035d47  mov     [rsp+1B88h+lpUserSid], r13; lpUserSid
0x180035d4c  mov     r9d, [rsp+1B88h+dwEventID]; dwEventID
0x180035d54  movzx   edx, [rsp+1B88h+var_1B18]; wType
0x180035d59  mov     rcx, rsi; hEventLog
0x180035d5c  call    cs:__imp_ReportEventW
0x180035d62  test    eax, eax
0x180035d64  jnz     loc_180035E21
0x180035d6a  call    cs:__imp_GetLastError
0x180035d70  mov     edi, eax
0x180035d72  lea     r15, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x180035d79  mov     [rsp+1B88h+var_1AF0], r15
0x180035d81  lea     r12, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x180035d88  mov     [rsp+1B88h+var_1AE8], r12
0x180035d90  lea     rax, aTrctrcc; "TRCTRCC"
0x180035d97  mov     [rsp+1B88h+var_1AE0], rax
0x180035d9f  mov     [rsp+1B88h+var_1AD8], 923h
0x180035daa  mov     [rsp+1B88h+var_1AD4], 0Bh
0x180035db5  mov     [rsp+1B88h+var_1A50], 1000000h
0x180035dc0  xor     edx, edx; Val
0x180035dc2  lea     r8d, [rdx+78h]; Size
0x180035dc6  lea     rcx, [rsp+1B88h+var_1AC8]; void *
0x180035dce  call    memset_0
0x180035dd3  mov     [rsp+1B88h+var_1AD0], 64h ; 'd'
0x180035dde  lea     rdx, [rsp+1B88h+var_1AF0]; struct CVssDebugInfo *
0x180035de6  lea     rcx, [rsp+1B88h+var_19B8]; this
0x180035dee  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180035df3  mov     r9d, edi
0x180035df6  lea     r8, aErrorOnReporte; "Error on ReportEventW 0x%08lx"
0x180035dfd  lea     rdx, [rsp+1B88h+var_19B8]
0x180035e05  lea     rcx, [rsp+1B88h+var_1A38]
0x180035e0d  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180035e12  lea     rcx, [rsp+1B88h+var_1AF0]; this
0x180035e1a  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180035e1f  jmp     short loc_180035E2F
0x180035e21  lea     r15, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x180035e28  lea     r12, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x180035e2f  mov     rcx, rsi; hEventLog
0x180035e32  call    cs:__imp_DeregisterEventSource
0x180035e38  test    eax, eax
0x180035e3a  jnz     loc_180035EED
0x180035e40  call    cs:__imp_GetLastError
0x180035e46  mov     ebx, eax
0x180035e48  mov     [rsp+1B88h+var_1AF0], r15
0x180035e50  mov     [rsp+1B88h+var_1AE8], r12
0x180035e58  lea     rax, aTrctrcc; "TRCTRCC"
0x180035e5f  mov     [rsp+1B88h+var_1AE0], rax
0x180035e67  mov     [rsp+1B88h+var_1AD8], 92Ah
0x180035e72  mov     [rsp+1B88h+var_1AD4], 0Bh
0x180035e7d  mov     [rsp+1B88h+var_1A50], 1000000h
0x180035e88  xor     edx, edx; Val
0x180035e8a  lea     r8d, [rdx+78h]; Size
0x180035e8e  lea     rcx, [rsp+1B88h+var_1AC8]; void *
0x180035e96  call    memset_0
0x180035e9b  mov     [rsp+1B88h+var_1AD0], 64h ; 'd'
0x180035ea6  lea     rdx, [rsp+1B88h+var_1AF0]; struct CVssDebugInfo *
0x180035eae  lea     rcx, [rsp+1B88h+var_19B8]; this
0x180035eb6  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180035ebb  mov     r9d, ebx
0x180035ebe  lea     r8, aErrorOnDeregis; "Error on DeregisterEventSource 0x%08lx"
0x180035ec5  lea     rdx, [rsp+1B88h+var_19B8]
0x180035ecd  lea     rcx, [rsp+1B88h+var_1A38]
0x180035ed5  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180035eda  lea     rcx, [rsp+1B88h+var_1AF0]; this
0x180035ee2  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180035ee7  call    ?InternalThrow@@YAXJ@Z; InternalThrow(long)
0x180035eed  mov     rcx, rbx; pv
0x180035ef0  call    cs:__imp_CoTaskMemFree
0x180035ef6  nop
0x180035ef7  jmp     short loc_180035F04
0x180035ef9  jmp     short loc_180035EFF
0x180035efb  jmp     short loc_180035EFF
0x180035efd  jmp     short $+2
0x180035eff  mov     r14, [rsp+1B88h+var_1B10]
0x180035f04  lea     rcx, [rsp+1B88h+var_1A38]; this
0x180035f0c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180035f11  nop
0x180035f12  mov     rcx, r14; this
0x180035f15  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180035f1a  nop
0x180035f1b  mov     rcx, [rsp+1B88h+var_48]
0x180035f23  xor     rcx, rsp; StackCookie
0x180035f26  call    __security_check_cookie
0x180035f2b  add     rsp, 1B50h
0x180035f32  pop     r15
0x180035f34  pop     r14
0x180035f36  pop     r13
0x180035f38  pop     r12
0x180035f3a  pop     rdi
0x180035f3b  pop     rsi
0x180035f3c  pop     rbx
  ... truncated ...
```
