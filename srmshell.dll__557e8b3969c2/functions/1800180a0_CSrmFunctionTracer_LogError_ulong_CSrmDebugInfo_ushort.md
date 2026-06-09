# CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)

- ea: `0x1800180a0`
- end: `0x18001871b`
- name: `?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z`
- size: `1659`
- prototype: `void __fastcall(__int64, DWORD, __int64, WORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018724`
- `0x1800198e0`

## callees

- `0x1800161e8`
- `0x18001623c`
- `0x180016518`
- `0x180016564`
- `0x180016a1c`
- `0x180017158`
- `0x180017820`
- `0x1800180a0`
- `0x180018e28`
- `0x1800191ec`
- `0x1800193ec`
- `0x1800196f0`
- `0x18001b3ee`
- `0x18001b420`
- `0x18001b4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001862a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001862a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800185be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800185be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018272`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018272`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001826a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001826a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001824e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180018257`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001824e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180018257`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x1800185a8`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x1800185a8`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180018455`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180018455`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x1800184a7`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x1800184a7`

## pseudocode

```c
void __fastcall CSrmFunctionTracer::LogError(__int64 a1, DWORD a2, __int64 a3, WORD a4)
{
  const struct CSrmDebugInfo *v6; // rax
  CSrmFunctionTracerBase *v7; // rcx
  __int64 dwDataSize; // rsi
  __int64 v9; // rax
  int v10; // r15d
  const wchar_t *CommandLineW; // r12
  LPWSTR v12; // rax
  __int64 v13; // r14
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  unsigned __int16 v16; // r14
  unsigned __int16 i; // bx
  const WCHAR *v18; // r10
  unsigned __int16 j; // cx
  __int64 v20; // rax
  unsigned int v21; // r11d
  __int64 v22; // r10
  HANDLE v23; // rbx
  unsigned __int16 k; // cx
  __int64 v25; // rax
  unsigned int v26; // r10d
  DWORD LastError; // ebx
  struct CSrmDebugInfo *v28; // rax
  __int64 v29; // rax
  DWORD v30; // ebx
  struct CSrmDebugInfo *v31; // rax
  __int64 v32; // rax
  PSID lpUserSid; // [rsp+20h] [rbp-1BB8h]
  PSID lpUserSida; // [rsp+20h] [rbp-1BB8h]
  LPVOID pv[2]; // [rsp+80h] [rbp-1B58h] BYREF
  const unsigned __int16 **v37; // [rsp+90h] [rbp-1B48h]
  DWORD dwEventID; // [rsp+98h] [rbp-1B40h]
  const unsigned __int16 *v39; // [rsp+A0h] [rbp-1B38h] BYREF
  const unsigned __int16 *v40; // [rsp+A8h] [rbp-1B30h]
  const unsigned __int16 *v41; // [rsp+B0h] [rbp-1B28h]
  int v42; // [rsp+B8h] [rbp-1B20h]
  int v43; // [rsp+BCh] [rbp-1B1Ch]
  int v44; // [rsp+C0h] [rbp-1B18h]
  _QWORD v45[12]; // [rsp+C8h] [rbp-1B10h] BYREF
  int v46; // [rsp+128h] [rbp-1AB0h]
  _QWORD v47[3]; // [rsp+140h] [rbp-1A98h] BYREF
  int v48; // [rsp+158h] [rbp-1A80h]
  int v49; // [rsp+15Ch] [rbp-1A7Ch]
  int v50; // [rsp+160h] [rbp-1A78h]
  _QWORD v51[12]; // [rsp+168h] [rbp-1A70h]
  __int16 v52; // [rsp+1C8h] [rbp-1A10h]
  char v53; // [rsp+1CAh] [rbp-1A0Eh]
  char v54; // [rsp+1CBh] [rbp-1A0Dh]
  _BYTE v55[144]; // [rsp+1D0h] [rbp-1A08h] BYREF
  _QWORD v56[22]; // [rsp+260h] [rbp-1978h] BYREF
  LPCWSTR Strings[14]; // [rsp+310h] [rbp-18C8h] BYREF
  unsigned __int16 v58; // [rsp+380h] [rbp-1858h] BYREF
  _BYTE v59[2046]; // [rsp+382h] [rbp-1856h] BYREF
  char RawData[4112]; // [rsp+B80h] [rbp-1058h] BYREF

  dwEventID = a2;
  pv[1] = (LPVOID)a3;
  v37 = (const unsigned __int16 **)v55;
  v39 = L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp";
  v40 = L"CSrmFunctionTracer::LogError";
  v41 = L"TRCTRCC";
  v42 = 2794;
  v43 = 17;
  v44 = 255;
  v46 = 0x1000000;
  memset_0(v45, 0, sizeof(v45));
  v6 = (const struct CSrmDebugInfo *)CSrmDebugInfo::operator()((struct CSrmDebugInfo *)&v39, (CSrmDebugInfo *)v55);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v56, v6, 0);
  CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v39);
  memset_0(Strings, 0, 0x68u);
  memset_0(RawData, 0, 0x1001u);
  if ( (unsigned int)*(unsigned __int16 *)(a3 + 136) + 1 < 0xC )
  {
    v58 = 0;
    memset_0(v59, 0, sizeof(v59));
    CSrmFunctionTracerBase::GetCurrentUserName(v7, &v58);
    dwDataSize = -1;
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&v59[2 * v9 - 2] );
    v10 = (((((int)v9 + 7) >> 31) & 7) + v9 + 7) & 0xFFFFFFF8;
    CommandLineW = GetCommandLineW();
    v12 = GetCommandLineW();
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    StringCchPrintfA(
      RawData,
      0x1000u,
      "- Code: %8ls%08lu- Call: %8ls%08lu- PID:  %08lu- TID:  %08lu- CMD:  %-*ls- User: %-*ls",
      *(const wchar_t **)(a3 + 16),
      *(_DWORD *)(a3 + 24),
      *(const wchar_t **)(a1 + 32),
      *(_DWORD *)(a1 + 40),
      CurrentProcessId,
      CurrentThreadId,
      (((((int)v13 + 7) >> 31) & 7) + v13 + 7) & 0xFFFFFFF8,
      CommandLineW,
      v10,
      &v58);
    do
      ++dwDataSize;
    while ( RawData[dwDataSize] );
    v16 = *(_WORD *)(a3 + 136);
    for ( i = 0; i < v16; ++i )
      Strings[i] = *(LPCWSTR *)(a3 + 8LL * i + 40);
    pv[0] = 0;
    CSrmFunctionTracerBase::GetCurrentContexts((CSrmFunctionTracerBase *)a1, pv);
    v18 = (const WCHAR *)&qword_180023088;
    if ( pv[0] )
      v18 = (const WCHAR *)pv[0];
    Strings[i] = v18;
    v37 = (const unsigned __int16 **)v47;
    v39 = L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp";
    v40 = L"CSrmFunctionTracer::LogError";
    v41 = L"TRCTRCC";
    v42 = 2859;
    v43 = 17;
    v44 = 255;
    v46 = 0x1000000;
    for ( j = 0; j < 0xCu; ++j )
      v45[j] = 0;
    v20 = CSrmDebugInfo::operator()((struct CSrmDebugInfo *)&v39, (CSrmDebugInfo *)v47);
    CSrmFunctionTracerBase::TraceInternalWithFormat(a1, v20, L"CONTEXT", v21, L"Current context: '%s'", v22);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v39);
    v23 = RegisterEventSourceW(0, L"SRMSVC");
    if ( !v23 )
    {
      LastError = GetLastError();
      v37 = (const unsigned __int16 **)v47;
      v28 = (struct CSrmDebugInfo *)CSrmDebugInfo::CSrmDebugInfo(
                                      (__int64)&v39,
                                      (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
                                      (__int64)L"TRCTRCC",
                                      (__int64)L"CSrmFunctionTracer::LogError",
                                      2873,
                                      17);
      v29 = CSrmDebugInfo::operator()(v28, (CSrmDebugInfo *)v47);
      LODWORD(lpUserSid) = LastError;
      CSrmFunctionTracer::Throw(v56, v29, 2147549183LL, L"Error on RegisterEventSourceW 0x%08lx", lpUserSid);
    }
    if ( !ReportEventW(v23, a4, 0, dwEventID, 0, v16 + 1, dwDataSize, Strings, RawData) )
    {
      GetLastError();
      v37 = &v39;
      v47[0] = L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp";
      v47[1] = L"CSrmFunctionTracer::LogError";
      v47[2] = L"TRCTRCC";
      v48 = 2888;
      v49 = 17;
      v50 = 255;
      v52 = 0;
      v53 = 0;
      v54 = 1;
      for ( k = 0; k < 0xCu; ++k )
        v51[k] = 0;
      v25 = CSrmDebugInfo::operator()((struct CSrmDebugInfo *)v47, (CSrmDebugInfo *)&v39);
      CSrmFunctionTracer::Trace(v56, v25, L"Error on ReportEventW 0x%08lx", v26);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v47);
    }
    if ( !DeregisterEventSource(v23) )
    {
      v30 = GetLastError();
      v37 = (const unsigned __int16 **)v47;
      v31 = (struct CSrmDebugInfo *)CSrmDebugInfo::CSrmDebugInfo(
                                      (__int64)&v39,
                                      (__int64)L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
                                      (__int64)L"TRCTRCC",
                                      (__int64)L"CSrmFunctionTracer::LogError",
                                      2893,
                                      17);
      v32 = CSrmDebugInfo::operator()(v31, (CSrmDebugInfo *)v47);
      LODWORD(lpUserSida) = v30;
      CSrmFunctionTracer::Throw(v56, v32, 2147549183LL, L"Error on DeregisterEventSource 0x%08lx", lpUserSida);
    }
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    v56[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v56);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)a3);
  }
  else
  {
    v56[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v56);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)a3);
  }
}

```

## disassembly

```asm
0x1800180a0  push    rbx
0x1800180a2  push    rsi
0x1800180a3  push    rdi
0x1800180a4  push    r12
0x1800180a6  push    r13
0x1800180a8  push    r14
0x1800180aa  push    r15
0x1800180ac  mov     eax, 1BA0h
0x1800180b1  call    _alloca_probe
0x1800180b6  sub     rsp, rax
0x1800180b9  mov     rax, cs:__security_cookie
0x1800180c0  xor     rax, rsp
0x1800180c3  mov     [rsp+1BD8h+var_48], rax
0x1800180cb  mov     [rsp+1BD8h+var_1B60], r9w
0x1800180d1  mov     rdi, r8
0x1800180d4  mov     [rsp+1BD8h+dwEventID], edx
0x1800180db  mov     r13, rcx
0x1800180de  mov     [rsp+1BD8h+var_1B50], r8
0x1800180e6  lea     rax, [rsp+1BD8h+var_1A08]
0x1800180ee  mov     [rsp+1BD8h+var_1B48], rax
0x1800180f6  lea     rax, aBaseFsFsrmUtil_1; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x1800180fd  mov     [rsp+1BD8h+var_1B38], rax
0x180018105  lea     rax, aCsrmfunctiontr_0; "CSrmFunctionTracer::LogError"
0x18001810c  mov     [rsp+1BD8h+var_1B30], rax
0x180018114  lea     rax, aTrctrcc; "TRCTRCC"
0x18001811b  mov     [rsp+1BD8h+var_1B28], rax
0x180018123  mov     [rsp+1BD8h+var_1B20], 0AEAh
0x18001812e  mov     [rsp+1BD8h+var_1B1C], 11h
0x180018139  mov     [rsp+1BD8h+var_1B18], 0FFh
0x180018144  xor     ebx, ebx
0x180018146  mov     [rsp+1BD8h+var_1AB0], 1000000h
0x180018151  xor     edx, edx; Val
0x180018153  lea     r8d, [rbx+60h]; Size
0x180018157  lea     rcx, [rsp+1BD8h+var_1B10]; void *
0x18001815f  call    memset_0
0x180018164  nop
0x180018165  lea     rdx, [rsp+1BD8h+var_1A08]; this
0x18001816d  lea     rcx, [rsp+1BD8h+var_1B38]; struct CSrmDebugInfo *
0x180018175  call    ??RCSrmDebugInfo@@QEAA?AU0@W4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::operator()(_SRMDBG_SEV_ENUM)
0x18001817a  nop
0x18001817b  xor     r8d, r8d
0x18001817e  mov     rdx, rax
0x180018181  lea     rcx, [rsp+1BD8h+var_1978]
0x180018189  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001818e  nop
0x18001818f  lea     rcx, [rsp+1BD8h+var_1B38]; this
0x180018197  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18001819c  nop
0x18001819d  xor     edx, edx; Val
0x18001819f  lea     r8d, [rbx+68h]; Size
0x1800181a3  lea     rcx, [rsp+1BD8h+Strings]; void *
0x1800181ab  call    memset_0
0x1800181b0  xor     edx, edx; Val
0x1800181b2  mov     r8d, 1001h; Size
0x1800181b8  lea     rcx, [rsp+1BD8h+RawData]; void *
0x1800181c0  call    memset_0
0x1800181c5  movzx   eax, word ptr [rdi+88h]
0x1800181cc  inc     eax
0x1800181ce  cmp     eax, 0Ch
0x1800181d1  jb      short loc_1800181FD
0x1800181d3  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800181da  mov     [rsp+1BD8h+var_1978], rax
0x1800181e2  lea     rcx, [rsp+1BD8h+var_1978]; this
0x1800181ea  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800181ef  nop
0x1800181f0  mov     rcx, rdi; this
0x1800181f3  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x1800181f8  jmp     loc_180018603
0x1800181fd  mov     [rsp+1BD8h+var_1858], bx
0x180018205  xor     edx, edx; Val
0x180018207  mov     r8d, 7FEh; Size
0x18001820d  lea     rcx, [rsp+1BD8h+var_1856]; void *
0x180018215  call    memset_0
0x18001821a  lea     rdx, [rsp+1BD8h+var_1858]; unsigned __int16 *
0x180018222  call    ?GetCurrentUserName@CSrmFunctionTracerBase@@QEAAXPEAGK@Z; CSrmFunctionTracerBase::GetCurrentUserName(ushort *,ulong)
0x180018227  lea     rcx, [rsp+1BD8h+var_1858]
0x18001822f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180018233  mov     rax, rsi
0x180018236  inc     rax
0x180018239  cmp     [rcx+rax*2], bx
0x18001823d  jnz     short loc_180018236
0x18001823f  add     eax, 7
0x180018242  cdq
0x180018243  and     edx, 7
0x180018246  lea     r15d, [rdx+rax]
0x18001824a  and     r15d, 0FFFFFFF8h
0x18001824e  call    cs:__imp_GetCommandLineW
0x180018254  mov     r12, rax
0x180018257  call    cs:__imp_GetCommandLineW
0x18001825d  mov     r14, rsi
0x180018260  inc     r14
0x180018263  cmp     [rax+r14*2], bx
0x180018268  jnz     short loc_180018260
0x18001826a  call    cs:__imp_GetCurrentThreadId
0x180018270  mov     ebx, eax
0x180018272  call    cs:__imp_GetCurrentProcessId
0x180018278  mov     ecx, eax
0x18001827a  lea     eax, [r14+7]
0x18001827e  cdq
0x18001827f  and     edx, 7
0x180018282  add     eax, edx
0x180018284  and     eax, 0FFFFFFF8h
0x180018287  lea     rdx, [rsp+1BD8h+var_1858]
0x18001828f  mov     [rsp+1BD8h+var_1B78], rdx
0x180018294  mov     [rsp+1BD8h+var_1B80], r15d
0x180018299  mov     [rsp+1BD8h+var_1B88], r12
0x18001829e  mov     [rsp+1BD8h+var_1B90], eax
0x1800182a2  mov     dword ptr [rsp+1BD8h+lpRawData], ebx
0x1800182a6  mov     dword ptr [rsp+1BD8h+lpStrings], ecx
0x1800182aa  mov     eax, [r13+28h]
0x1800182ae  mov     [rsp+1BD8h+dwDataSize], eax
0x1800182b2  mov     rax, [r13+20h]
0x1800182b6  mov     qword ptr [rsp+1BD8h+wNumStrings], rax
0x1800182bb  mov     eax, [rdi+18h]
0x1800182be  mov     dword ptr [rsp+1BD8h+lpUserSid], eax
0x1800182c2  mov     r9, [rdi+10h]
0x1800182c6  lea     r8, aCode8ls08luCal; "- Code: %8ls%08lu- Call: %8ls%08lu- PID"...
0x1800182cd  mov     edx, 1000h; unsigned __int64
0x1800182d2  lea     rcx, [rsp+1BD8h+RawData]; char *
0x1800182da  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800182df  lea     rax, [rsp+1BD8h+RawData]
0x1800182e7  xor     r15d, r15d
0x1800182ea  inc     rsi
0x1800182ed  cmp     [rax+rsi], r15b
0x1800182f1  jnz     short loc_1800182EA
0x1800182f3  movzx   r14d, word ptr [rdi+88h]
0x1800182fb  mov     ebx, r15d
0x1800182fe  mov     r12d, 1
0x180018304  mov     [rsp+1BD8h+var_1B68], bx
0x180018309  cmp     bx, r14w
0x18001830d  jnb     short loc_180018325
0x18001830f  movzx   ecx, bx
0x180018312  mov     rax, [rdi+rcx*8+28h]
0x180018317  mov     [rsp+rcx*8+1BD8h+Strings], rax
0x18001831f  add     bx, r12w
0x180018323  jmp     short loc_180018304
0x180018325  mov     [rsp+1BD8h+pv], r15
0x18001832d  lea     rdx, [rsp+1BD8h+pv]; struct CSrmAutoPWSZ *
0x180018335  mov     rcx, r13; this
0x180018338  call    ?GetCurrentContexts@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z; CSrmFunctionTracerBase::GetCurrentContexts(CSrmAutoPWSZ &)
0x18001833d  mov     rax, [rsp+1BD8h+pv]
0x180018345  lea     r10, qword_180023088
0x18001834c  test    rax, rax
0x18001834f  cmovnz  r10, rax
0x180018353  movzx   eax, bx
0x180018356  mov     [rsp+rax*8+1BD8h+Strings], r10
0x18001835e  mov     ecx, 0FFh
0x180018363  mov     r11d, 64h ; 'd'
0x180018369  cmp     [rdi+20h], ecx
0x18001836c  cmovnz  r11d, [rdi+20h]
0x180018371  lea     r8, [rsp+1BD8h+var_1A98]
0x180018379  mov     [rsp+1BD8h+var_1B48], r8
0x180018381  lea     rax, aBaseFsFsrmUtil_1; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x180018388  mov     [rsp+1BD8h+var_1B38], rax
0x180018390  lea     rax, aCsrmfunctiontr_0; "CSrmFunctionTracer::LogError"
0x180018397  mov     [rsp+1BD8h+var_1B30], rax
0x18001839f  lea     rax, aTrctrcc; "TRCTRCC"
0x1800183a6  mov     [rsp+1BD8h+var_1B28], rax
0x1800183ae  mov     [rsp+1BD8h+var_1B20], 0B2Bh
0x1800183b9  mov     [rsp+1BD8h+var_1B1C], 11h
0x1800183c4  mov     [rsp+1BD8h+var_1B18], ecx
0x1800183cb  mov     word ptr [rsp+1BD8h+var_1AB0], r15w
0x1800183d4  mov     byte ptr [rsp+1BD8h+var_1AB0+2], r15b
0x1800183dc  mov     byte ptr [rsp+1BD8h+var_1AB0+3], r12b
0x1800183e4  mov     ecx, r15d
0x1800183e7  mov     edx, 0Ch
0x1800183ec  mov     [rsp+1BD8h+var_1B64], cx
0x1800183f1  cmp     cx, dx
0x1800183f4  jnb     short loc_180018407
0x1800183f6  movzx   eax, cx
0x1800183f9  mov     [rsp+rax*8+1BD8h+var_1B10], r15
0x180018401  add     cx, r12w
0x180018405  jmp     short loc_1800183EC
0x180018407  mov     rdx, r8; this
0x18001840a  lea     rcx, [rsp+1BD8h+var_1B38]; struct CSrmDebugInfo *
0x180018412  call    ??RCSrmDebugInfo@@QEAA?AU0@W4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::operator()(_SRMDBG_SEV_ENUM)
0x180018417  nop
0x180018418  mov     qword ptr [rsp+1BD8h+wNumStrings], r10
0x18001841d  lea     rcx, aCurrentContext; "Current context: '%s'"
0x180018424  mov     [rsp+1BD8h+lpUserSid], rcx
0x180018429  mov     r9d, r11d
0x18001842c  lea     r8, aContext; "CONTEXT"
0x180018433  mov     rdx, rax
0x180018436  mov     rcx, r13
0x180018439  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(CSrmDebugInfo,ushort const *,ulong,ushort const *,...)
0x18001843e  nop
0x18001843f  lea     rcx, [rsp+1BD8h+var_1B38]; this
0x180018447  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18001844c  lea     rdx, SourceName; "SRMSVC"
0x180018453  xor     ecx, ecx; lpUNCServerName
0x180018455  call    cs:__imp_RegisterEventSourceW
0x18001845b  mov     rbx, rax
0x18001845e  test    rax, rax
0x180018461  jz      loc_18001862A
0x180018467  add     r14w, r12w
0x18001846b  xor     r8d, r8d; wCategory
0x18001846e  lea     rax, [rsp+1BD8h+RawData]
0x180018476  mov     [rsp+1BD8h+lpRawData], rax; lpRawData
0x18001847b  lea     rax, [rsp+1BD8h+Strings]
0x180018483  mov     [rsp+1BD8h+lpStrings], rax; lpStrings
0x180018488  mov     [rsp+1BD8h+dwDataSize], esi; dwDataSize
0x18001848c  mov     [rsp+1BD8h+wNumStrings], r14w; wNumStrings
0x180018492  mov     [rsp+1BD8h+lpUserSid], r15; lpUserSid
0x180018497  mov     r9d, [rsp+1BD8h+dwEventID]; dwEventID
0x18001849f  movzx   edx, [rsp+1BD8h+var_1B60]; wType
0x1800184a4  mov     rcx, rbx; hEventLog
0x1800184a7  call    cs:__imp_ReportEventW
0x1800184ad  test    eax, eax
0x1800184af  jnz     loc_180018590
0x1800184b5  call    cs:__imp_GetLastError
0x1800184bb  mov     r10d, eax
0x1800184be  lea     rdx, [rsp+1BD8h+var_1B38]; this
0x1800184c6  mov     [rsp+1BD8h+var_1B48], rdx
0x1800184ce  lea     rsi, aBaseFsFsrmUtil_1; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x1800184d5  mov     [rsp+1BD8h+var_1A98], rsi
0x1800184dd  lea     r14, aCsrmfunctiontr_0; "CSrmFunctionTracer::LogError"
0x1800184e4  mov     [rsp+1BD8h+var_1A90], r14
0x1800184ec  lea     r13, aTrctrcc; "TRCTRCC"
0x1800184f3  mov     [rsp+1BD8h+var_1A88], r13
0x1800184fb  mov     [rsp+1BD8h+var_1A80], 0B48h
0x180018506  mov     [rsp+1BD8h+var_1A7C], 11h
0x180018511  mov     [rsp+1BD8h+var_1A78], 0FFh
0x18001851c  mov     [rsp+1BD8h+var_1A10], r15w
0x180018525  mov     [rsp+1BD8h+var_1A0E], r15b
0x18001852d  mov     [rsp+1BD8h+var_1A0D], r12b
0x180018535  mov     ecx, r15d
0x180018538  mov     [rsp+1BD8h+var_1B5C], cx
0x18001853d  mov     eax, 0Ch
0x180018542  cmp     cx, ax
0x180018545  jnb     short loc_180018558
0x180018547  movzx   eax, cx
0x18001854a  mov     [rsp+rax*8+1BD8h+var_1A70], r15
0x180018552  add     cx, r12w
0x180018556  jmp     short loc_180018538
0x180018558  lea     rcx, [rsp+1BD8h+var_1A98]; struct CSrmDebugInfo *
0x180018560  call    ??RCSrmDebugInfo@@QEAA?AU0@W4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::operator()(_SRMDBG_SEV_ENUM)
0x180018565  nop
0x180018566  mov     r9d, r10d
0x180018569  lea     r8, aErrorOnReporte; "Error on ReportEventW 0x%08lx"
0x180018570  mov     rdx, rax
0x180018573  lea     rcx, [rsp+1BD8h+var_1978]
0x18001857b  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180018580  nop
0x180018581  lea     rcx, [rsp+1BD8h+var_1A98]; this
0x180018589  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18001858e  jmp     short loc_1800185A5
0x180018590  lea     rsi, aBaseFsFsrmUtil_1; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x180018597  lea     r14, aCsrmfunctiontr_0; "CSrmFunctionTracer::LogError"
0x18001859e  lea     r13, aTrctrcc; "TRCTRCC"
0x1800185a5  mov     rcx, rbx; hEventLog
0x1800185a8  call    cs:__imp_DeregisterEventSource
0x1800185ae  test    eax, eax
0x1800185b0  jz      loc_1800186A8
0x1800185b6  mov     rcx, [rsp+1BD8h+pv]; pv
0x1800185be  call    cs:__imp_CoTaskMemFree
0x1800185c4  mov     [rsp+1BD8h+pv], r15
0x1800185cc  mov     [rsp+1BD8h+pv], r15
0x1800185d4  jmp     short loc_1800185DE
0x1800185d6  mov     rdi, [rsp+1BD8h+var_1B50]
0x1800185de  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800185e5  mov     [rsp+1BD8h+var_1978], rax
0x1800185ed  lea     rcx, [rsp+1BD8h+var_1978]; this
0x1800185f5  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800185fa  nop
0x1800185fb  mov     rcx, rdi; this
0x1800185fe  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180018603  mov     rcx, [rsp+1BD8h+var_48]
0x18001860b  xor     rcx, rsp; StackCookie
0x18001860e  call    __security_check_cookie
0x180018613  add     rsp, 1BA0h
0x18001861a  pop     r15
0x18001861c  pop     r14
0x18001861e  pop     r13
0x180018620  pop     r12
0x180018622  pop     rdi
0x180018623  pop     rsi
0x180018624  pop     rbx
0x180018625  retn
0x180018626  jmp     short loc_1800185D6
0x180018628  jmp     short loc_1800185D6
0x18001862a  call    cs:__imp_GetLastError
0x180018630  mov     ebx, eax
0x180018632  lea     rax, [rsp+1BD8h+var_1A98]
0x18001863a  mov     [rsp+1BD8h+var_1B48], rax
0x180018642  mov     dword ptr [rsp+1BD8h+wNumStrings], 11h
0x18001864a  mov     dword ptr [rsp+1BD8h+lpUserSid], 0B39h
0x180018652  lea     r9, aCsrmfunctiontr_0; "CSrmFunctionTracer::LogError"
0x180018659  lea     r8, aTrctrcc; "TRCTRCC"
0x180018660  lea     rdx, aBaseFsFsrmUtil_1; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x180018667  lea     rcx, [rsp+1BD8h+var_1B38]
0x18001866f  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180018674  nop
0x180018675  lea     rdx, [rsp+1BD8h+var_1A98]; this
0x18001867d  mov     rcx, rax; struct CSrmDebugInfo *
0x180018680  call    ??RCSrmDebugInfo@@QEAA?AU0@W4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::operator()(_SRMDBG_SEV_ENUM)
0x180018685  nop
0x180018686  mov     dword ptr [rsp+1BD8h+lpUserSid], ebx
0x18001868a  lea     r9, aErrorOnRegiste; "Error on RegisterEventSourceW 0x%08lx"
0x180018691  mov     r8d, 8000FFFFh
0x180018697  mov     rdx, rax
  ... truncated ...
```
