# CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)

- ea: `0x1400330fc`
- end: `0x140033746`
- name: `?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z`
- size: `1610`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `75`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140009ea0`
- `0x14000c84c`
- `0x14000f1d0`
- `0x14000fba0`
- `0x14001f070`
- `0x14001f334`
- `0x140024500`
- `0x1400281a0`
- `0x140028888`
- `0x140028b48`
- `0x140028d60`
- `0x14002a724`
- `0x14002a8ac`
- `0x14002b160`
- `0x14002f438`
- `0x14002fde0`
- `0x140030790`
- `0x140031cd0`
- `0x140032990`
- `0x140033e1c`
- `0x14003d180`
- `0x14003de10`
- `0x140040c48`
- `0x140042688`
- `0x140042acc`
- `0x1400437e0`
- `0x140044014`
- `0x1400445c0`
- `0x140044780`
- `0x14004498c`
- `0x140049ec4`
- `0x14004a0c8`
- `0x14004d814`
- `0x14004f3e0`
- `0x140052640`
- `0x140054608`
- `0x1400588b4`
- `0x14005b2a0`
- `0x14005e024`
- `0x140063078`
- `0x140063f60`
- `0x140067464`
- `0x140067af4`
- `0x14006d260`
- `0x14006f180`
- `0x140070a00`
- `0x140070fcc`
- `0x14007c240`
- `0x14007d6fc`
- `0x14007e6c4`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x1400144d0`
- `0x140019e30`
- `0x1400330fc`
- `0x14004073c`
- `0x140040a80`
- `0x140046cb4`
- `0x140091560`
- `0x1400921dc`
- `0x1400cd8f8`
- `0x1400da290`
- `0x1400da314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003346d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003346d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033648`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033288`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033288`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140033290`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140033290`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14003326d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140033276`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14003326d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140033276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400336f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400336f8`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x14003363a`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x14003363a`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x140033458`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x140033458`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x140033564`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x140033564`

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
  int v39; // [rsp+140h] [rbp-1A48h] BYREF
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
      v20 = &byte_1400F9C88;
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
0x1400330fc  push    rbx
0x1400330fe  push    rsi
0x1400330ff  push    rdi
0x140033100  push    r12
0x140033102  push    r13
0x140033104  push    r14
0x140033106  push    r15
0x140033108  mov     eax, 1B50h
0x14003310d  call    _alloca_probe
0x140033112  sub     rsp, rax
0x140033115  mov     rax, cs:__security_cookie
0x14003311c  xor     rax, rsp
0x14003311f  mov     [rsp+1B88h+var_48], rax
0x140033127  mov     [rsp+1B88h+var_1B18], r9w
0x14003312d  mov     r14, r8
0x140033130  mov     [rsp+1B88h+dwEventID], edx
0x140033137  mov     r13, rcx
0x14003313a  mov     [rsp+1B88h+var_1B10], r8
0x14003313f  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x140033146  mov     [rsp+1B88h+Strings], rax
0x14003314e  lea     rax, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x140033155  mov     [rsp+1B88h+var_1900], rax
0x14003315d  lea     rax, aTrctrcc; "TRCTRCC"
0x140033164  mov     [rsp+1B88h+var_18F8], rax
0x14003316c  mov     [rsp+1B88h+var_18F0], 8C1h
0x140033177  mov     [rsp+1B88h+var_18EC], 0Bh
0x140033182  mov     [rsp+1B88h+var_18E8], 0FFh
0x14003318d  xor     ebx, ebx
0x14003318f  mov     [rsp+1B88h+var_1868], 1000000h
0x14003319a  lea     edi, [rbx+1]
0x14003319d  xor     edx, edx; Val
0x14003319f  lea     r8d, [rbx+78h]; Size
0x1400331a3  lea     rcx, [rsp+1B88h+var_18E0]; void *
0x1400331ab  call    memset_0
0x1400331b0  xor     r8d, r8d
0x1400331b3  lea     rdx, [rsp+1B88h+Strings]
0x1400331bb  lea     rcx, [rsp+1B88h+var_1A38]
0x1400331c3  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400331c8  nop
0x1400331c9  xor     edx, edx; Val
0x1400331cb  lea     r8d, [rdi+7Fh]; Size
0x1400331cf  lea     rcx, [rsp+1B88h+Strings]; void *
0x1400331d7  call    memset_0
0x1400331dc  xor     edx, edx; Val
0x1400331de  mov     r8d, 1001h; Size
0x1400331e4  lea     rcx, [rsp+1B88h+RawData]; void *
0x1400331ec  call    memset_0
0x1400331f1  movzx   eax, word ptr [r14+0A0h]
0x1400331f9  add     eax, edi
0x1400331fb  cmp     eax, 0Fh
0x1400331fe  jb      short loc_14003321B
0x140033200  lea     rcx, [rsp+1B88h+var_1A38]; this
0x140033208  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003320d  nop
0x14003320e  mov     rcx, r14; this
0x140033211  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140033216  jmp     loc_140033723
0x14003321b  mov     [rsp+1B88h+var_1858], bx
0x140033223  xor     edx, edx; Val
0x140033225  mov     r8d, 7FEh; Size
0x14003322b  lea     rcx, [rsp+1B88h+var_1856]; void *
0x140033233  call    memset_0
0x140033238  lea     rdx, [rsp+1B88h+var_1858]; unsigned __int16 *
0x140033240  call    ?GetCurrentUserName@CVssFunctionTracer@@QEAAXPEAGK@Z; CVssFunctionTracer::GetCurrentUserName(ushort *,ulong)
0x140033245  lea     rcx, [rsp+1B88h+var_1858]
0x14003324d  or      r15, 0FFFFFFFFFFFFFFFFh
0x140033251  mov     rax, r15
0x140033254  inc     rax
0x140033257  cmp     [rcx+rax*2], bx
0x14003325b  jnz     short loc_140033254
0x14003325d  add     eax, 7
0x140033260  cdq
0x140033261  mov     ecx, 8
0x140033266  idiv    ecx
0x140033268  mov     esi, eax
0x14003326a  shl     esi, 3
0x14003326d  call    cs:__imp_GetCommandLineW
0x140033273  mov     r12, rax
0x140033276  call    cs:__imp_GetCommandLineW
0x14003327c  mov     rdi, r15
0x14003327f  inc     rdi
0x140033282  cmp     [rax+rdi*2], bx
0x140033286  jnz     short loc_14003327F
0x140033288  call    cs:__imp_GetCurrentThreadId
0x14003328e  mov     ebx, eax
0x140033290  call    cs:__imp_GetCurrentProcessId
0x140033296  mov     ecx, eax
0x140033298  lea     eax, [rdi+7]
0x14003329b  cdq
0x14003329c  mov     r8d, 8
0x1400332a2  idiv    r8d
0x1400332a5  shl     eax, 3
0x1400332a8  lea     rdx, [rsp+1B88h+var_1858]
0x1400332b0  mov     [rsp+1B88h+var_1B28], rdx
0x1400332b5  mov     [rsp+1B88h+var_1B30], esi
0x1400332b9  mov     [rsp+1B88h+var_1B38], r12
0x1400332be  mov     [rsp+1B88h+var_1B40], eax
0x1400332c2  mov     dword ptr [rsp+1B88h+lpRawData], ebx
0x1400332c6  mov     dword ptr [rsp+1B88h+lpStrings], ecx
0x1400332ca  mov     eax, [r13+20h]
0x1400332ce  mov     [rsp+1B88h+dwDataSize], eax
0x1400332d2  mov     rax, [r13+18h]
0x1400332d6  mov     qword ptr [rsp+1B88h+wNumStrings], rax
0x1400332db  mov     eax, [r14+18h]
0x1400332df  mov     dword ptr [rsp+1B88h+lpUserSid], eax
0x1400332e3  mov     r9, [r14+10h]
0x1400332e7  lea     r8, aCode8ls08luCal; "- Code: %8ls%08lu- Call: %8ls%08lu- PID"...
0x1400332ee  mov     edx, 1000h; unsigned __int64
0x1400332f3  lea     rcx, [rsp+1B88h+RawData]; char *
0x1400332fb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140033300  lea     rax, [rsp+1B88h+RawData]
0x140033308  inc     r15
0x14003330b  cmp     byte ptr [rax+r15], 0
0x140033310  jnz     short loc_140033308
0x140033312  movzx   ebx, word ptr [r14+0A0h]
0x14003331a  mov     esi, 1
0x14003331f  lea     r12d, [rsi+rbx]
0x140033323  xor     edi, edi
0x140033325  xor     eax, eax
0x140033327  cmp     ax, bx
0x14003332a  jnb     short loc_14003334C
0x14003332c  mov     r8d, ebx
0x14003332f  shl     r8, 3; Size
0x140033333  lea     rdx, [r14+28h]; Src
0x140033337  lea     rcx, [rsp+1B88h+Strings]; void *
0x14003333f  call    memcpy_0
0x140033344  add     di, si
0x140033347  cmp     di, bx
0x14003334a  jb      short loc_140033344
0x14003334c  mov     [rsp+1B88h+var_1AF8], 0
0x140033358  mov     rcx, r13; this
0x14003335b  call    ?GetCurrentContexts@CVssFunctionTracer@@QEAAPEAGXZ; CVssFunctionTracer::GetCurrentContexts(void)
0x140033360  mov     rbx, rax
0x140033363  mov     [rsp+1B88h+var_1AF8], rax
0x14003336b  lea     rsi, byte_1400F9C88
0x140033372  test    rax, rax
0x140033375  cmovnz  rsi, rax
0x140033379  movzx   eax, di
0x14003337c  mov     [rsp+rax*8+1B88h+Strings], rsi
0x140033384  mov     edi, 64h ; 'd'
0x140033389  cmp     dword ptr [r14+20h], 0FFh
0x140033391  cmovnz  edi, [r14+20h]
0x140033396  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x14003339d  mov     [rsp+1B88h+var_1AF0], rax
0x1400333a5  lea     rax, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x1400333ac  mov     [rsp+1B88h+var_1AE8], rax
0x1400333b4  lea     rax, aTrctrcc; "TRCTRCC"
0x1400333bb  mov     [rsp+1B88h+var_1AE0], rax
0x1400333c3  mov     [rsp+1B88h+var_1AD8], 902h
0x1400333ce  mov     [rsp+1B88h+var_1AD4], 0Bh
0x1400333d9  mov     [rsp+1B88h+var_1A50], 1000000h
0x1400333e4  xor     edx, edx; Val
0x1400333e6  lea     r8d, [rdx+78h]; Size
0x1400333ea  lea     rcx, [rsp+1B88h+var_1AC8]; void *
0x1400333f2  call    memset_0
0x1400333f7  mov     [rsp+1B88h+var_1AD0], 64h ; 'd'
0x140033402  lea     rdx, [rsp+1B88h+var_1AF0]; struct CVssDebugInfo *
0x14003340a  lea     rcx, [rsp+1B88h+var_19B8]; this
0x140033412  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x140033417  mov     qword ptr [rsp+1B88h+wNumStrings], rsi
0x14003341c  lea     rax, aCurrentContext; "Current context: '%s'"
0x140033423  mov     [rsp+1B88h+lpUserSid], rax
0x140033428  mov     r9d, edi
0x14003342b  lea     r8, aContext; "CONTEXT"
0x140033432  lea     rdx, [rsp+1B88h+var_19B8]
0x14003343a  mov     rcx, r13
0x14003343d  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1ZZ; CVssFunctionTracer::TraceInternalWithFormat(CVssDebugInfo,ushort const *,ulong,ushort const *,...)
0x140033442  lea     rcx, [rsp+1B88h+var_1AF0]; this
0x14003344a  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003344f  lea     rdx, SourceName; "VSS"
0x140033456  xor     ecx, ecx; lpUNCServerName
0x140033458  call    cs:__imp_RegisterEventSourceW
0x14003345e  mov     rsi, rax
0x140033461  xor     r13d, r13d
0x140033464  test    rax, rax
0x140033467  jnz     loc_140033527
0x14003346d  call    cs:__imp_GetLastError
0x140033473  mov     ebx, eax
0x140033475  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x14003347c  mov     [rsp+1B88h+var_1AF0], rax
0x140033484  lea     rax, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x14003348b  mov     [rsp+1B88h+var_1AE8], rax
0x140033493  lea     rax, aTrctrcc; "TRCTRCC"
0x14003349a  mov     [rsp+1B88h+var_1AE0], rax
0x1400334a2  mov     [rsp+1B88h+var_1AD8], 912h
0x1400334ad  mov     [rsp+1B88h+var_1AD4], 0Bh
0x1400334b8  mov     [rsp+1B88h+var_1A50], 1000000h
0x1400334c3  xor     edx, edx; Val
0x1400334c5  lea     r8d, [rsi+78h]; Size
0x1400334c9  lea     rcx, [rsp+1B88h+var_1AC8]; void *
0x1400334d1  call    memset_0
0x1400334d6  mov     [rsp+1B88h+var_1AD0], 64h ; 'd'
0x1400334e1  lea     rdx, [rsp+1B88h+var_1AF0]; struct CVssDebugInfo *
0x1400334e9  lea     rcx, [rsp+1B88h+var_19B8]; this
0x1400334f1  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x1400334f6  mov     r9d, ebx
0x1400334f9  lea     r8, aErrorOnRegiste; "Error on RegisterEventSourceW 0x%08lx"
0x140033500  lea     rdx, [rsp+1B88h+var_19B8]
0x140033508  lea     rcx, [rsp+1B88h+var_1A38]
0x140033510  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140033515  lea     rcx, [rsp+1B88h+var_1AF0]; this
0x14003351d  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140033522  call    ?InternalThrow@@YAXJ@Z; InternalThrow(long)
0x140033527  xor     r8d, r8d; wCategory
0x14003352a  lea     rax, [rsp+1B88h+RawData]
0x140033532  mov     [rsp+1B88h+lpRawData], rax; lpRawData
0x140033537  lea     rax, [rsp+1B88h+Strings]
0x14003353f  mov     [rsp+1B88h+lpStrings], rax; lpStrings
0x140033544  mov     [rsp+1B88h+dwDataSize], r15d; dwDataSize
0x140033549  mov     [rsp+1B88h+wNumStrings], r12w; wNumStrings
0x14003354f  mov     [rsp+1B88h+lpUserSid], r13; lpUserSid
0x140033554  mov     r9d, [rsp+1B88h+dwEventID]; dwEventID
0x14003355c  movzx   edx, [rsp+1B88h+var_1B18]; wType
0x140033561  mov     rcx, rsi; hEventLog
0x140033564  call    cs:__imp_ReportEventW
0x14003356a  test    eax, eax
0x14003356c  jnz     loc_140033629
0x140033572  call    cs:__imp_GetLastError
0x140033578  mov     edi, eax
0x14003357a  lea     r15, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x140033581  mov     [rsp+1B88h+var_1AF0], r15
0x140033589  lea     r12, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x140033590  mov     [rsp+1B88h+var_1AE8], r12
0x140033598  lea     rax, aTrctrcc; "TRCTRCC"
0x14003359f  mov     [rsp+1B88h+var_1AE0], rax
0x1400335a7  mov     [rsp+1B88h+var_1AD8], 923h
0x1400335b2  mov     [rsp+1B88h+var_1AD4], 0Bh
0x1400335bd  mov     [rsp+1B88h+var_1A50], 1000000h
0x1400335c8  xor     edx, edx; Val
0x1400335ca  lea     r8d, [rdx+78h]; Size
0x1400335ce  lea     rcx, [rsp+1B88h+var_1AC8]; void *
0x1400335d6  call    memset_0
0x1400335db  mov     [rsp+1B88h+var_1AD0], 64h ; 'd'
0x1400335e6  lea     rdx, [rsp+1B88h+var_1AF0]; struct CVssDebugInfo *
0x1400335ee  lea     rcx, [rsp+1B88h+var_19B8]; this
0x1400335f6  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x1400335fb  mov     r9d, edi
0x1400335fe  lea     r8, aErrorOnReporte; "Error on ReportEventW 0x%08lx"
0x140033605  lea     rdx, [rsp+1B88h+var_19B8]
0x14003360d  lea     rcx, [rsp+1B88h+var_1A38]
0x140033615  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003361a  lea     rcx, [rsp+1B88h+var_1AF0]; this
0x140033622  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140033627  jmp     short loc_140033637
0x140033629  lea     r15, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x140033630  lea     r12, aCvssfunctiontr_1; "CVssFunctionTracer::LogError"
0x140033637  mov     rcx, rsi; hEventLog
0x14003363a  call    cs:__imp_DeregisterEventSource
0x140033640  test    eax, eax
0x140033642  jnz     loc_1400336F5
0x140033648  call    cs:__imp_GetLastError
0x14003364e  mov     ebx, eax
0x140033650  mov     [rsp+1B88h+var_1AF0], r15
0x140033658  mov     [rsp+1B88h+var_1AE8], r12
0x140033660  lea     rax, aTrctrcc; "TRCTRCC"
0x140033667  mov     [rsp+1B88h+var_1AE0], rax
0x14003366f  mov     [rsp+1B88h+var_1AD8], 92Ah
0x14003367a  mov     [rsp+1B88h+var_1AD4], 0Bh
0x140033685  mov     [rsp+1B88h+var_1A50], 1000000h
0x140033690  xor     edx, edx; Val
0x140033692  lea     r8d, [rdx+78h]; Size
0x140033696  lea     rcx, [rsp+1B88h+var_1AC8]; void *
0x14003369e  call    memset_0
0x1400336a3  mov     [rsp+1B88h+var_1AD0], 64h ; 'd'
0x1400336ae  lea     rdx, [rsp+1B88h+var_1AF0]; struct CVssDebugInfo *
0x1400336b6  lea     rcx, [rsp+1B88h+var_19B8]; this
0x1400336be  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x1400336c3  mov     r9d, ebx
0x1400336c6  lea     r8, aErrorOnDeregis; "Error on DeregisterEventSource 0x%08lx"
0x1400336cd  lea     rdx, [rsp+1B88h+var_19B8]
0x1400336d5  lea     rcx, [rsp+1B88h+var_1A38]
0x1400336dd  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400336e2  lea     rcx, [rsp+1B88h+var_1AF0]; this
0x1400336ea  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x1400336ef  call    ?InternalThrow@@YAXJ@Z; InternalThrow(long)
0x1400336f5  mov     rcx, rbx; pv
0x1400336f8  call    cs:__imp_CoTaskMemFree
0x1400336fe  nop
0x1400336ff  jmp     short loc_14003370C
0x140033701  jmp     short loc_140033707
0x140033703  jmp     short loc_140033707
0x140033705  jmp     short $+2
0x140033707  mov     r14, [rsp+1B88h+var_1B10]
0x14003370c  lea     rcx, [rsp+1B88h+var_1A38]; this
0x140033714  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140033719  nop
0x14003371a  mov     rcx, r14; this
0x14003371d  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140033722  nop
0x140033723  mov     rcx, [rsp+1B88h+var_48]
0x14003372b  xor     rcx, rsp; StackCookie
0x14003372e  call    __security_check_cookie
0x140033733  add     rsp, 1B50h
0x14003373a  pop     r15
0x14003373c  pop     r14
0x14003373e  pop     r13
0x140033740  pop     r12
0x140033742  pop     rdi
0x140033743  pop     rsi
0x140033744  pop     rbx
  ... truncated ...
```
