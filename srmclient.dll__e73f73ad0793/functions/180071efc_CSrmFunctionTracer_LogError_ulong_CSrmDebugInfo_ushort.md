# CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)

- ea: `0x180071efc`
- end: `0x180072592`
- name: `?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z`
- size: `1686`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `26`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180040f60`
- `0x1800417d0`
- `0x18005162c`
- `0x180059008`
- `0x180064400`
- `0x180069dc0`
- `0x180070d7c`
- `0x1800728d8`
- `0x1800745d0`
- `0x180074874`
- `0x180078a88`
- `0x180078f5c`
- `0x180079724`
- `0x180079b9c`
- `0x18007aa14`
- `0x18007fbd8`
- `0x180093344`
- `0x180093aa8`
- `0x18009887c`
- `0x18009a9a8`
- `0x18009f958`
- `0x1800a0428`
- `0x1800a5fb0`
- `0x1800a6f90`
- `0x1800a8500`
- `0x1800a9190`

## callees

- `0x18006fe68`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x1800705d4`
- `0x18007120c`
- `0x1800716ec`
- `0x180071efc`
- `0x180073940`
- `0x180073d04`
- `0x180074048`
- `0x18007434c`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800b0890`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180072429`
- `ole32!CoTaskMemFree` at `0x180072429`
- `KERNEL32!GetCurrentProcessId` at `0x1800720d2`
- `KERNEL32!GetCurrentProcessId` at `0x1800720d2`
- `KERNEL32!GetCurrentThreadId` at `0x1800720ca`
- `KERNEL32!GetCurrentThreadId` at `0x1800720ca`
- `KERNEL32!GetLastError` at `0x18007231a`
- `KERNEL32!GetLastError` at `0x180072495`
- `KERNEL32!GetLastError` at `0x180072519`
- `KERNEL32!GetLastError` at `0x18007231a`
- `KERNEL32!GetLastError` at `0x180072495`
- `KERNEL32!GetLastError` at `0x180072519`
- `KERNEL32!GetCommandLineW` at `0x1800720ae`
- `KERNEL32!GetCommandLineW` at `0x1800720b7`
- `KERNEL32!GetCommandLineW` at `0x1800720ae`
- `KERNEL32!GetCommandLineW` at `0x1800720b7`
- `ADVAPI32!DeregisterEventSource` at `0x180072413`
- `ADVAPI32!DeregisterEventSource` at `0x180072413`
- `ADVAPI32!RegisterEventSourceW` at `0x1800722ba`
- `ADVAPI32!RegisterEventSourceW` at `0x1800722ba`
- `ADVAPI32!ReportEventW` at `0x18007230c`
- `ADVAPI32!ReportEventW` at `0x18007230c`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
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
    CSrmFunctionTracerBase::GetCurrentContexts((CSrmFunctionTracerBase *)a1, (struct CSrmAutoPWSZ *)pv);
    v18 = &dword_1800DC394;
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
0x180071efc  push    rbx
0x180071efe  push    rsi
0x180071eff  push    rdi
0x180071f00  push    r12
0x180071f02  push    r13
0x180071f04  push    r14
0x180071f06  push    r15
0x180071f08  mov     eax, 1BA0h
0x180071f0d  call    _alloca_probe
0x180071f12  sub     rsp, rax
0x180071f15  mov     rax, cs:__security_cookie
0x180071f1c  xor     rax, rsp
0x180071f1f  mov     [rsp+1BD8h+var_48], rax
0x180071f27  mov     [rsp+1BD8h+var_1B60], r9w
0x180071f2d  mov     rdi, r8
0x180071f30  mov     [rsp+1BD8h+dwEventID], edx
0x180071f37  mov     r13, rcx
0x180071f3a  mov     [rsp+1BD8h+var_1B50], r8
0x180071f42  lea     rax, [rsp+1BD8h+var_1A08]
0x180071f4a  mov     [rsp+1BD8h+var_1B48], rax
0x180071f52  lea     rax, aBaseFsFsrmUtil_9; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x180071f59  mov     [rsp+1BD8h+var_1B38], rax
0x180071f61  lea     rax, aCsrmfunctiontr_3; "CSrmFunctionTracer::LogError"
0x180071f68  mov     [rsp+1BD8h+var_1B30], rax
0x180071f70  lea     rax, aTrctrcc; "TRCTRCC"
0x180071f77  mov     [rsp+1BD8h+var_1B28], rax
0x180071f7f  mov     [rsp+1BD8h+var_1B20], 0AEAh
0x180071f8a  mov     [rsp+1BD8h+var_1B1C], 11h
0x180071f95  mov     [rsp+1BD8h+var_1B18], 0FFh
0x180071fa0  xor     ebx, ebx
0x180071fa2  mov     [rsp+1BD8h+var_1AB0], 1000000h
0x180071fad  xor     edx, edx; Val
0x180071faf  lea     r8d, [rbx+60h]; Size
0x180071fb3  lea     rcx, [rsp+1BD8h+var_1B10]; void *
0x180071fbb  call    memset_0
0x180071fc0  nop
0x180071fc1  lea     r8d, [rbx+64h]
0x180071fc5  lea     rdx, [rsp+1BD8h+var_1A08]; this
0x180071fcd  lea     rcx, [rsp+1BD8h+var_1B38]; struct CSrmDebugInfo *
0x180071fd5  call    ??RCSrmDebugInfo@@QEAA?AU0@W4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::operator()(_SRMDBG_SEV_ENUM)
0x180071fda  nop
0x180071fdb  xor     r8d, r8d
0x180071fde  mov     rdx, rax
0x180071fe1  lea     rcx, [rsp+1BD8h+var_1978]
0x180071fe9  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180071fee  nop
0x180071fef  lea     rcx, [rsp+1BD8h+var_1B38]; this
0x180071ff7  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180071ffc  nop
0x180071ffd  xor     edx, edx; Val
0x180071fff  lea     r8d, [rbx+68h]; Size
0x180072003  lea     rcx, [rsp+1BD8h+Strings]; void *
0x18007200b  call    memset_0
0x180072010  xor     edx, edx; Val
0x180072012  mov     r8d, 1001h; Size
0x180072018  lea     rcx, [rsp+1BD8h+RawData]; void *
0x180072020  call    memset_0
0x180072025  movzx   eax, word ptr [rdi+88h]
0x18007202c  inc     eax
0x18007202e  cmp     eax, 0Ch
0x180072031  jb      short loc_18007205D
0x180072033  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007203a  mov     [rsp+1BD8h+var_1978], rax
0x180072042  lea     rcx, [rsp+1BD8h+var_1978]; this
0x18007204a  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007204f  nop
0x180072050  mov     rcx, rdi; this
0x180072053  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180072058  jmp     loc_18007246E
0x18007205d  mov     [rsp+1BD8h+var_1858], bx
0x180072065  xor     edx, edx; Val
0x180072067  mov     r8d, 7FEh; Size
0x18007206d  lea     rcx, [rsp+1BD8h+var_1856]; void *
0x180072075  call    memset_0
0x18007207a  lea     rdx, [rsp+1BD8h+var_1858]; unsigned __int16 *
0x180072082  call    ?GetCurrentUserName@CSrmFunctionTracerBase@@QEAAXPEAGK@Z; CSrmFunctionTracerBase::GetCurrentUserName(ushort *,ulong)
0x180072087  lea     rcx, [rsp+1BD8h+var_1858]
0x18007208f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180072093  mov     rax, rsi
0x180072096  inc     rax
0x180072099  cmp     [rcx+rax*2], bx
0x18007209d  jnz     short loc_180072096
0x18007209f  add     eax, 7
0x1800720a2  cdq
0x1800720a3  and     edx, 7
0x1800720a6  lea     r15d, [rdx+rax]
0x1800720aa  and     r15d, 0FFFFFFF8h
0x1800720ae  call    cs:__imp_GetCommandLineW
0x1800720b4  mov     r12, rax
0x1800720b7  call    cs:__imp_GetCommandLineW
0x1800720bd  mov     r14, rsi
0x1800720c0  inc     r14
0x1800720c3  cmp     [rax+r14*2], bx
0x1800720c8  jnz     short loc_1800720C0
0x1800720ca  call    cs:__imp_GetCurrentThreadId
0x1800720d0  mov     ebx, eax
0x1800720d2  call    cs:__imp_GetCurrentProcessId
0x1800720d8  mov     ecx, eax
0x1800720da  lea     eax, [r14+7]
0x1800720de  cdq
0x1800720df  and     edx, 7
0x1800720e2  add     eax, edx
0x1800720e4  and     eax, 0FFFFFFF8h
0x1800720e7  lea     rdx, [rsp+1BD8h+var_1858]
0x1800720ef  mov     [rsp+1BD8h+var_1B78], rdx
0x1800720f4  mov     [rsp+1BD8h+var_1B80], r15d
0x1800720f9  mov     [rsp+1BD8h+var_1B88], r12
0x1800720fe  mov     [rsp+1BD8h+var_1B90], eax
0x180072102  mov     dword ptr [rsp+1BD8h+lpRawData], ebx
0x180072106  mov     dword ptr [rsp+1BD8h+lpStrings], ecx
0x18007210a  mov     eax, [r13+28h]
0x18007210e  mov     [rsp+1BD8h+dwDataSize], eax
0x180072112  mov     rax, [r13+20h]
0x180072116  mov     qword ptr [rsp+1BD8h+wNumStrings], rax
0x18007211b  mov     eax, [rdi+18h]
0x18007211e  mov     dword ptr [rsp+1BD8h+lpUserSid], eax
0x180072122  mov     r9, [rdi+10h]
0x180072126  lea     r8, aCode8ls08luCal; "- Code: %8ls%08lu- Call: %8ls%08lu- PID"...
0x18007212d  mov     edx, 1000h; unsigned __int64
0x180072132  lea     rcx, [rsp+1BD8h+RawData]; char *
0x18007213a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18007213f  lea     rax, [rsp+1BD8h+RawData]
0x180072147  xor     r15d, r15d
0x18007214a  inc     rsi
0x18007214d  cmp     [rax+rsi], r15b
0x180072151  jnz     short loc_18007214A
0x180072153  movzx   r14d, word ptr [rdi+88h]
0x18007215b  mov     ebx, r15d
0x18007215e  mov     r12d, 1
0x180072164  mov     [rsp+1BD8h+var_1B68], bx
0x180072169  cmp     bx, r14w
0x18007216d  jnb     short loc_180072185
0x18007216f  movzx   ecx, bx
0x180072172  mov     rax, [rdi+rcx*8+28h]
0x180072177  mov     [rsp+rcx*8+1BD8h+Strings], rax
0x18007217f  add     bx, r12w
0x180072183  jmp     short loc_180072164
0x180072185  mov     [rsp+1BD8h+pv], r15
0x18007218d  lea     rdx, [rsp+1BD8h+pv]; struct CSrmAutoPWSZ *
0x180072195  mov     rcx, r13; this
0x180072198  call    ?GetCurrentContexts@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z; CSrmFunctionTracerBase::GetCurrentContexts(CSrmAutoPWSZ &)
0x18007219d  mov     rax, [rsp+1BD8h+pv]
0x1800721a5  lea     r10, dword_1800DC394
0x1800721ac  test    rax, rax
0x1800721af  cmovnz  r10, rax
0x1800721b3  movzx   eax, bx
0x1800721b6  mov     [rsp+rax*8+1BD8h+Strings], r10
0x1800721be  mov     edx, 64h ; 'd'
0x1800721c3  mov     r11d, edx
0x1800721c6  mov     ecx, 0FFh
0x1800721cb  cmp     [rdi+20h], ecx
0x1800721ce  cmovnz  r11d, [rdi+20h]
0x1800721d3  lea     r9, [rsp+1BD8h+var_1A98]
0x1800721db  mov     [rsp+1BD8h+var_1B48], r9
0x1800721e3  lea     rax, aBaseFsFsrmUtil_9; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x1800721ea  mov     [rsp+1BD8h+var_1B38], rax
0x1800721f2  lea     rax, aCsrmfunctiontr_3; "CSrmFunctionTracer::LogError"
0x1800721f9  mov     [rsp+1BD8h+var_1B30], rax
0x180072201  lea     rax, aTrctrcc; "TRCTRCC"
0x180072208  mov     [rsp+1BD8h+var_1B28], rax
0x180072210  mov     [rsp+1BD8h+var_1B20], 0B2Bh
0x18007221b  mov     [rsp+1BD8h+var_1B1C], 11h
0x180072226  mov     [rsp+1BD8h+var_1B18], ecx
0x18007222d  mov     word ptr [rsp+1BD8h+var_1AB0], r15w
0x180072236  mov     byte ptr [rsp+1BD8h+var_1AB0+2], r15b
0x18007223e  mov     byte ptr [rsp+1BD8h+var_1AB0+3], r12b
0x180072246  mov     ecx, r15d
0x180072249  lea     r8d, [rdx-58h]
0x18007224d  mov     [rsp+1BD8h+var_1B64], cx
0x180072252  cmp     cx, r8w
0x180072256  jnb     short loc_180072269
0x180072258  movzx   eax, cx
0x18007225b  mov     [rsp+rax*8+1BD8h+var_1B10], r15
0x180072263  add     cx, r12w
0x180072267  jmp     short loc_18007224D
0x180072269  mov     r8d, edx
0x18007226c  mov     rdx, r9; this
0x18007226f  lea     rcx, [rsp+1BD8h+var_1B38]; struct CSrmDebugInfo *
0x180072277  call    ??RCSrmDebugInfo@@QEAA?AU0@W4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::operator()(_SRMDBG_SEV_ENUM)
0x18007227c  nop
0x18007227d  mov     qword ptr [rsp+1BD8h+wNumStrings], r10
0x180072282  lea     rcx, aCurrentContext; "Current context: '%s'"
0x180072289  mov     [rsp+1BD8h+lpUserSid], rcx
0x18007228e  mov     r9d, r11d
0x180072291  lea     r8, aContext; "CONTEXT"
0x180072298  mov     rdx, rax
0x18007229b  mov     rcx, r13
0x18007229e  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXUCSrmDebugInfo@@PEBGK1ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(CSrmDebugInfo,ushort const *,ulong,ushort const *,...)
0x1800722a3  nop
0x1800722a4  lea     rcx, [rsp+1BD8h+var_1B38]; this
0x1800722ac  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x1800722b1  lea     rdx, SourceName; "SRMSVC"
0x1800722b8  xor     ecx, ecx; lpUNCServerName
0x1800722ba  call    cs:__imp_RegisterEventSourceW
0x1800722c0  mov     rbx, rax
0x1800722c3  test    rax, rax
0x1800722c6  jz      loc_180072495
0x1800722cc  add     r14w, r12w
0x1800722d0  xor     r8d, r8d; wCategory
0x1800722d3  lea     rax, [rsp+1BD8h+RawData]
0x1800722db  mov     [rsp+1BD8h+lpRawData], rax; lpRawData
0x1800722e0  lea     rax, [rsp+1BD8h+Strings]
0x1800722e8  mov     [rsp+1BD8h+lpStrings], rax; lpStrings
0x1800722ed  mov     [rsp+1BD8h+dwDataSize], esi; dwDataSize
0x1800722f1  mov     [rsp+1BD8h+wNumStrings], r14w; wNumStrings
0x1800722f7  mov     [rsp+1BD8h+lpUserSid], r15; lpUserSid
0x1800722fc  mov     r9d, [rsp+1BD8h+dwEventID]; dwEventID
0x180072304  movzx   edx, [rsp+1BD8h+var_1B60]; wType
0x180072309  mov     rcx, rbx; hEventLog
0x18007230c  call    cs:__imp_ReportEventW
0x180072312  test    eax, eax
0x180072314  jnz     loc_1800723FB
0x18007231a  call    cs:__imp_GetLastError
0x180072320  mov     r10d, eax
0x180072323  lea     rdx, [rsp+1BD8h+var_1B38]; this
0x18007232b  mov     [rsp+1BD8h+var_1B48], rdx
0x180072333  lea     rsi, aBaseFsFsrmUtil_9; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x18007233a  mov     [rsp+1BD8h+var_1A98], rsi
0x180072342  lea     r14, aCsrmfunctiontr_3; "CSrmFunctionTracer::LogError"
0x180072349  mov     [rsp+1BD8h+var_1A90], r14
0x180072351  lea     r13, aTrctrcc; "TRCTRCC"
0x180072358  mov     [rsp+1BD8h+var_1A88], r13
0x180072360  mov     [rsp+1BD8h+var_1A80], 0B48h
0x18007236b  mov     [rsp+1BD8h+var_1A7C], 11h
0x180072376  mov     [rsp+1BD8h+var_1A78], 0FFh
0x180072381  mov     [rsp+1BD8h+var_1A10], r15w
0x18007238a  mov     [rsp+1BD8h+var_1A0E], r15b
0x180072392  mov     [rsp+1BD8h+var_1A0D], r12b
0x18007239a  mov     ecx, r15d
0x18007239d  mov     [rsp+1BD8h+var_1B5C], cx
0x1800723a2  mov     eax, 0Ch
0x1800723a7  cmp     cx, ax
0x1800723aa  jnb     short loc_1800723BD
0x1800723ac  movzx   eax, cx
0x1800723af  mov     [rsp+rax*8+1BD8h+var_1A70], r15
0x1800723b7  add     cx, r12w
0x1800723bb  jmp     short loc_18007239D
0x1800723bd  mov     r8d, 64h ; 'd'
0x1800723c3  lea     rcx, [rsp+1BD8h+var_1A98]; struct CSrmDebugInfo *
0x1800723cb  call    ??RCSrmDebugInfo@@QEAA?AU0@W4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::operator()(_SRMDBG_SEV_ENUM)
0x1800723d0  nop
0x1800723d1  mov     r9d, r10d
0x1800723d4  lea     r8, aErrorOnReporte; "Error on ReportEventW 0x%08lx"
0x1800723db  mov     rdx, rax
0x1800723de  lea     rcx, [rsp+1BD8h+var_1978]
0x1800723e6  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800723eb  nop
0x1800723ec  lea     rcx, [rsp+1BD8h+var_1A98]; this
0x1800723f4  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x1800723f9  jmp     short loc_180072410
0x1800723fb  lea     rsi, aBaseFsFsrmUtil_9; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x180072402  lea     r14, aCsrmfunctiontr_3; "CSrmFunctionTracer::LogError"
0x180072409  lea     r13, aTrctrcc; "TRCTRCC"
0x180072410  mov     rcx, rbx; hEventLog
0x180072413  call    cs:__imp_DeregisterEventSource
0x180072419  test    eax, eax
0x18007241b  jz      loc_180072519
0x180072421  mov     rcx, [rsp+1BD8h+pv]; pv
0x180072429  call    cs:__imp_CoTaskMemFree
0x18007242f  mov     [rsp+1BD8h+pv], r15
0x180072437  mov     [rsp+1BD8h+pv], r15
0x18007243f  jmp     short loc_180072449
0x180072441  mov     rdi, [rsp+1BD8h+var_1B50]
0x180072449  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180072450  mov     [rsp+1BD8h+var_1978], rax
0x180072458  lea     rcx, [rsp+1BD8h+var_1978]; this
0x180072460  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180072465  nop
0x180072466  mov     rcx, rdi; this
0x180072469  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18007246e  mov     rcx, [rsp+1BD8h+var_48]
0x180072476  xor     rcx, rsp; StackCookie
0x180072479  call    __security_check_cookie
0x18007247e  add     rsp, 1BA0h
0x180072485  pop     r15
0x180072487  pop     r14
0x180072489  pop     r13
0x18007248b  pop     r12
0x18007248d  pop     rdi
0x18007248e  pop     rsi
0x18007248f  pop     rbx
0x180072490  retn
0x180072491  jmp     short loc_180072441
0x180072493  jmp     short loc_180072441
0x180072495  call    cs:__imp_GetLastError
0x18007249b  mov     ebx, eax
0x18007249d  lea     rax, [rsp+1BD8h+var_1A98]
0x1800724a5  mov     [rsp+1BD8h+var_1B48], rax
0x1800724ad  mov     dword ptr [rsp+1BD8h+wNumStrings], 11h
0x1800724b5  mov     dword ptr [rsp+1BD8h+lpUserSid], 0B39h
0x1800724bd  lea     r9, aCsrmfunctiontr_3; "CSrmFunctionTracer::LogError"
0x1800724c4  lea     r8, aTrctrcc; "TRCTRCC"
0x1800724cb  lea     rdx, aBaseFsFsrmUtil_9; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x1800724d2  lea     rcx, [rsp+1BD8h+var_1B38]
0x1800724da  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800724df  nop
0x1800724e0  mov     r8d, 64h ; 'd'
0x1800724e6  lea     rdx, [rsp+1BD8h+var_1A98]; this
0x1800724ee  mov     rcx, rax; struct CSrmDebugInfo *
0x1800724f1  call    ??RCSrmDebugInfo@@QEAA?AU0@W4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::operator()(_SRMDBG_SEV_ENUM)
  ... truncated ...
```
