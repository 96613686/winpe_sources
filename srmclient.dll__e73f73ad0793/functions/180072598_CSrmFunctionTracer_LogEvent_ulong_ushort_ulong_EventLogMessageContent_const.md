# CSrmFunctionTracer::LogEvent(ulong,ushort,ulong,EventLogMessageContent const &)

- ea: `0x180072598`
- end: `0x1800728cf`
- name: `?LogEvent@CSrmFunctionTracer@@QEAAXKGKAEBUEventLogMessageContent@@@Z`
- size: `823`
- prototype: `void __fastcall(CSrmFunctionTracer *__hidden this, unsigned int, unsigned __int16, unsigned int, const struct EventLogMessageContent *)`
- caller_count: `9`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800125c0`
- `0x18001671c`
- `0x180017210`
- `0x180018064`
- `0x180018b04`
- `0x180027ac8`
- `0x18006d8e0`
- `0x18009cf88`
- `0x1800a2560`

## callees

- `0x18006febc`
- `0x1800700b8`
- `0x18007120c`
- `0x1800716ec`
- `0x180072598`
- `0x180073940`
- `0x180073f54`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800b0890`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180072879`
- `ole32!CoTaskMemFree` at `0x180072879`
- `KERNEL32!GetCurrentProcessId` at `0x1800726f9`
- `KERNEL32!GetCurrentProcessId` at `0x1800726f9`
- `KERNEL32!GetCurrentThreadId` at `0x1800726f1`
- `KERNEL32!GetCurrentThreadId` at `0x1800726f1`
- `KERNEL32!GetLastError` at `0x180072816`
- `KERNEL32!GetLastError` at `0x18007284a`
- `KERNEL32!GetLastError` at `0x180072816`
- `KERNEL32!GetLastError` at `0x18007284a`
- `ADVAPI32!DeregisterEventSource` at `0x180072842`
- `ADVAPI32!DeregisterEventSource` at `0x180072842`
- `ADVAPI32!RegisterEventSourceW` at `0x1800727b3`
- `ADVAPI32!RegisterEventSourceW` at `0x1800727b3`
- `ADVAPI32!ReportEventW` at `0x18007280c`
- `ADVAPI32!ReportEventW` at `0x18007280c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CSrmFunctionTracer::LogEvent(
        CSrmFunctionTracer *this,
        int a2,
        WORD a3,
        __int64 a4,
        const struct EventLogMessageContent *a5)
{
  CSrmFunctionTracerBase *v7; // rcx
  __int64 v8; // r14
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  int i; // ecx
  const WCHAR *v12; // rdx
  unsigned __int16 v13; // di
  const WCHAR *v14; // rcx
  WORD wNumStrings; // di
  HANDLE v16; // rbx
  __int64 dwDataSize; // rsi
  PSID lpUserSid; // [rsp+20h] [rbp-1A58h]
  PSID lpUserSida; // [rsp+20h] [rbp-1A58h]
  LPVOID pv; // [rsp+58h] [rbp-1A20h] BYREF
  int v22; // [rsp+60h] [rbp-1A18h]
  int v23; // [rsp+64h] [rbp-1A14h] BYREF
  _QWORD *v24; // [rsp+68h] [rbp-1A10h]
  _com_error *v25; // [rsp+70h] [rbp-1A08h] BYREF
  const exception *v26; // [rsp+78h] [rbp-1A00h] BYREF
  _QWORD v27[3]; // [rsp+80h] [rbp-19F8h] BYREF
  int v28; // [rsp+98h] [rbp-19E0h]
  int v29; // [rsp+9Ch] [rbp-19DCh]
  int v30; // [rsp+A0h] [rbp-19D8h]
  _BYTE v31[96]; // [rsp+A8h] [rbp-19D0h] BYREF
  int v32; // [rsp+108h] [rbp-1970h]
  _QWORD v33[5]; // [rsp+110h] [rbp-1968h] BYREF
  unsigned int v34; // [rsp+13Ch] [rbp-193Ch]
  LPCWSTR Strings[12]; // [rsp+1C0h] [rbp-18B8h] BYREF
  unsigned __int16 v36; // [rsp+220h] [rbp-1858h] BYREF
  _BYTE v37[2046]; // [rsp+222h] [rbp-1856h] BYREF
  char RawData[4112]; // [rsp+A20h] [rbp-1058h] BYREF

  v24 = v27;
  v27[0] = L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp";
  v27[1] = L"CSrmFunctionTracer::LogEvent";
  v27[2] = L"TRCTRCC";
  v28 = 2705;
  v29 = 17;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v33, (const struct CSrmDebugInfo *)v27, 0);
  try
  {
    pv = 0;
    v13 = 0;
    memset_0(Strings, 0, sizeof(Strings));
    memset_0(RawData, 0, 0x1001u);
    v36 = 0;
    memset_0(v37, 0, sizeof(v37));
    CSrmFunctionTracerBase::GetCurrentContexts(this, (struct CSrmAutoPWSZ *)&pv);
    CSrmFunctionTracerBase::GetCurrentUserName(v7, &v36);
    dwDataSize = -1;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v37[2 * v8 - 2] );
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    StringCchPrintfA(
      RawData,
      0x1000u,
      "- Call: %8ls%08lu- PID:  %08lu- TID:  %08lu- User: %-*ls",
      *((const wchar_t **)this + 4),
      a2,
      CurrentProcessId,
      CurrentThreadId,
      (((((int)v8 + 7) >> 31) & 7) + v8 + 7) & 0xFFFFFFF8,
      &v36);
    for ( i = 0; ; ++i )
    {
      v22 = i;
      if ( (unsigned __int64)i >= 9 )
        break;
      v12 = (const WCHAR *)*((_QWORD *)a5 + i + 1);
      if ( v12 )
        Strings[v13++] = v12;
    }
    v14 = &dword_1800DC394;
    if ( pv )
      v14 = (const WCHAR *)pv;
    Strings[v13] = v14;
    wNumStrings = v13 + 1;
    v16 = RegisterEventSourceW(0, L"SRMSVC");
    if ( v16 )
    {
      do
        ++dwDataSize;
      while ( RawData[dwDataSize] );
      if ( !ReportEventW(v16, a3, 0, *(_DWORD *)a5, 0, wNumStrings, dwDataSize, Strings, RawData) )
      {
        LODWORD(lpUserSida) = GetLastError();
        CSrmFunctionTracer::Trace(
          (CSrmFunctionTracer *)v33,
          0x8Cu,
          0xAD3u,
          L"Error on ReportEventW 0x%08lx",
          lpUserSida);
      }
      DeregisterEventSource(v16);
    }
    else
    {
      LODWORD(lpUserSid) = GetLastError();
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)v33,
        0x8Cu,
        0xADCu,
        L"Error on RegisterEventSourceW 0x%08lx",
        lpUserSid);
    }
    CoTaskMemFree(pv);
    pv = 0;
  }
  catch ( long v23 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)v33,
      v23,
      L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
      L"TRCTRCC",
      L"CSrmFunctionTracer::LogEvent",
      0xADFu,
      v34);
  }
  catch ( _com_error *v25 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)v33,
      v25,
      L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
      L"TRCTRCC",
      L"CSrmFunctionTracer::LogEvent",
      0xADFu,
      v34);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)v33,
      L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
      L"TRCTRCC",
      L"CSrmFunctionTracer::LogEvent",
      0xADFu,
      v34);
  }
  catch ( const exception *v26 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)v33,
      v26,
      L"base\\fs\\fsrm\\utilities\\functracer\\functiontracer.cpp",
      L"TRCTRCC",
      L"CSrmFunctionTracer::LogEvent",
      0xADFu,
      v34);
  }
  v33[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v33);
}

```

## disassembly

```asm
0x180072598  push    rbx
0x18007259a  push    rsi
0x18007259b  push    rdi
0x18007259c  push    r12
0x18007259e  push    r13
0x1800725a0  push    r14
0x1800725a2  push    r15
0x1800725a4  mov     eax, 1A40h
0x1800725a9  call    _alloca_probe
0x1800725ae  sub     rsp, rax
0x1800725b1  mov     rax, cs:__security_cookie
0x1800725b8  xor     rax, rsp
0x1800725bb  mov     [rsp+1A78h+var_48], rax
0x1800725c3  mov     [rsp+1A78h+var_1A24], r8w
0x1800725c9  mov     r12d, edx
0x1800725cc  mov     r13, rcx
0x1800725cf  mov     r15, [rsp+1A78h+arg_20]
0x1800725d7  lea     rax, [rsp+1A78h+var_19F8]
0x1800725df  mov     [rsp+1A78h+var_1A10], rax
0x1800725e4  lea     rax, aBaseFsFsrmUtil_9; "base\\fs\\fsrm\\utilities\\functracer\\"...
0x1800725eb  mov     [rsp+1A78h+var_19F8], rax
0x1800725f3  lea     rax, aCsrmfunctiontr; "CSrmFunctionTracer::LogEvent"
0x1800725fa  mov     [rsp+1A78h+var_19F0], rax
0x180072602  lea     rax, aTrctrcc; "TRCTRCC"
0x180072609  mov     [rsp+1A78h+var_19E8], rax
0x180072611  mov     [rsp+1A78h+var_19E0], 0A91h
0x18007261c  mov     [rsp+1A78h+var_19DC], 11h
0x180072627  mov     [rsp+1A78h+var_19D8], 0FFh
0x180072632  xor     ebx, ebx
0x180072634  mov     [rsp+1A78h+var_1970], 1000000h
0x18007263f  lea     esi, [rbx+60h]
0x180072642  mov     r8d, esi; Size
0x180072645  xor     edx, edx; Val
0x180072647  lea     rcx, [rsp+1A78h+var_19D0]; void *
0x18007264f  call    memset_0
0x180072654  nop
0x180072655  xor     r8d, r8d
0x180072658  lea     rdx, [rsp+1A78h+var_19F8]
0x180072660  lea     rcx, [rsp+1A78h+var_1968]
0x180072668  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007266d  nop
0x18007266e  mov     [rsp+1A78h+pv], rbx
0x180072673  mov     edi, ebx
0x180072675  mov     [rsp+1A78h+var_1A28], bx
0x18007267a  mov     r8d, esi; Size
0x18007267d  xor     edx, edx; Val
0x18007267f  lea     rcx, [rsp+1A78h+Strings]; void *
0x180072687  call    memset_0
0x18007268c  xor     edx, edx; Val
0x18007268e  mov     r8d, 1001h; Size
0x180072694  lea     rcx, [rsp+1A78h+RawData]; void *
0x18007269c  call    memset_0
0x1800726a1  mov     [rsp+1A78h+var_1858], bx
0x1800726a9  xor     edx, edx; Val
0x1800726ab  mov     r8d, 7FEh; Size
0x1800726b1  lea     rcx, [rsp+1A78h+var_1856]; void *
0x1800726b9  call    memset_0
0x1800726be  lea     rdx, [rsp+1A78h+pv]; struct CSrmAutoPWSZ *
0x1800726c3  mov     rcx, r13; this
0x1800726c6  call    ?GetCurrentContexts@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z; CSrmFunctionTracerBase::GetCurrentContexts(CSrmAutoPWSZ &)
0x1800726cb  lea     rdx, [rsp+1A78h+var_1858]; unsigned __int16 *
0x1800726d3  call    ?GetCurrentUserName@CSrmFunctionTracerBase@@QEAAXPEAGK@Z; CSrmFunctionTracerBase::GetCurrentUserName(ushort *,ulong)
0x1800726d8  lea     rax, [rsp+1A78h+var_1858]
0x1800726e0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800726e4  mov     r14, rsi
0x1800726e7  inc     r14
0x1800726ea  cmp     [rax+r14*2], bx
0x1800726ef  jnz     short loc_1800726E7
0x1800726f1  call    cs:__imp_GetCurrentThreadId
0x1800726f7  mov     ebx, eax
0x1800726f9  call    cs:__imp_GetCurrentProcessId
0x1800726ff  mov     ecx, eax
0x180072701  lea     eax, [r14+7]
0x180072705  cdq
0x180072706  and     edx, 7
0x180072709  add     eax, edx
0x18007270b  and     eax, 0FFFFFFF8h
0x18007270e  lea     rdx, [rsp+1A78h+var_1858]
0x180072716  mov     [rsp+1A78h+lpRawData], rdx
0x18007271b  mov     dword ptr [rsp+1A78h+lpStrings], eax
0x18007271f  mov     [rsp+1A78h+dwDataSize], ebx
0x180072723  mov     dword ptr [rsp+1A78h+wNumStrings], ecx
0x180072727  mov     dword ptr [rsp+1A78h+lpUserSid], r12d
0x18007272c  mov     r9, [r13+20h]
0x180072730  lea     r8, aCall8ls08luPid; "- Call: %8ls%08lu- PID:  %08lu- TID:  %"...
0x180072737  mov     edx, 1000h; unsigned __int64
0x18007273c  lea     rcx, [rsp+1A78h+RawData]; char *
0x180072744  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180072749  xor     r14d, r14d
0x18007274c  mov     ecx, r14d
0x18007274f  lea     r8d, [r14+1]
0x180072753  mov     [rsp+1A78h+var_1A18], ecx
0x180072757  movsxd  rax, ecx
0x18007275a  cmp     rax, 9
0x18007275e  jnb     short loc_180072783
0x180072760  mov     rdx, [r15+rax*8+8]
0x180072765  test    rdx, rdx
0x180072768  jz      short loc_18007277E
0x18007276a  movzx   eax, di
0x18007276d  mov     [rsp+rax*8+1A78h+Strings], rdx
0x180072775  add     di, r8w
0x180072779  mov     [rsp+1A78h+var_1A28], di
0x18007277e  add     ecx, r8d
0x180072781  jmp     short loc_180072753
0x180072783  lea     rcx, dword_1800DC394
0x18007278a  mov     rax, [rsp+1A78h+pv]
0x18007278f  test    rax, rax
0x180072792  cmovnz  rcx, rax
0x180072796  movzx   eax, di
0x180072799  mov     [rsp+rax*8+1A78h+Strings], rcx
0x1800727a1  add     di, r8w
0x1800727a5  mov     [rsp+1A78h+var_1A28], di
0x1800727aa  lea     rdx, SourceName; "SRMSVC"
0x1800727b1  xor     ecx, ecx; lpUNCServerName
0x1800727b3  call    cs:__imp_RegisterEventSourceW
0x1800727b9  mov     rbx, rax
0x1800727bc  test    rax, rax
0x1800727bf  jz      loc_18007284A
0x1800727c5  lea     rax, [rsp+1A78h+RawData]
0x1800727cd  inc     rsi
0x1800727d0  cmp     [rax+rsi], r14b
0x1800727d4  jnz     short loc_1800727CD
0x1800727d6  xor     r8d, r8d; wCategory
0x1800727d9  lea     rax, [rsp+1A78h+RawData]
0x1800727e1  mov     [rsp+1A78h+lpRawData], rax; lpRawData
0x1800727e6  lea     rax, [rsp+1A78h+Strings]
0x1800727ee  mov     [rsp+1A78h+lpStrings], rax; lpStrings
0x1800727f3  mov     [rsp+1A78h+dwDataSize], esi; dwDataSize
0x1800727f7  mov     [rsp+1A78h+wNumStrings], di; wNumStrings
0x1800727fc  mov     [rsp+1A78h+lpUserSid], r14; lpUserSid
0x180072801  mov     r9d, [r15]; dwEventID
0x180072804  movzx   edx, [rsp+1A78h+var_1A24]; wType
0x180072809  mov     rcx, rbx; hEventLog
0x18007280c  call    cs:__imp_ReportEventW
0x180072812  test    eax, eax
0x180072814  jnz     short loc_18007283F
0x180072816  call    cs:__imp_GetLastError
0x18007281c  mov     dword ptr [rsp+1A78h+lpUserSid], eax
0x180072820  lea     r9, aErrorOnReporte; "Error on ReportEventW 0x%08lx"
0x180072827  mov     edx, 8Ch; unsigned int
0x18007282c  mov     r8d, 0AD3h; unsigned int
0x180072832  lea     rcx, [rsp+1A78h+var_1968]; this
0x18007283a  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18007283f  mov     rcx, rbx; hEventLog
0x180072842  call    cs:__imp_DeregisterEventSource
0x180072848  jmp     short loc_180072874
0x18007284a  call    cs:__imp_GetLastError
0x180072850  mov     dword ptr [rsp+1A78h+lpUserSid], eax
0x180072854  lea     r9, aErrorOnRegiste; "Error on RegisterEventSourceW 0x%08lx"
0x18007285b  mov     edx, 8Ch; unsigned int
0x180072860  mov     r8d, 0ADCh; unsigned int
0x180072866  lea     rcx, [rsp+1A78h+var_1968]; this
0x18007286e  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180072873  nop
0x180072874  mov     rcx, [rsp+1A78h+pv]; pv
0x180072879  call    cs:__imp_CoTaskMemFree
0x18007287f  mov     [rsp+1A78h+pv], r14
0x180072884  mov     [rsp+1A78h+pv], r14
0x180072889  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180072890  mov     [rsp+1A78h+var_1968], rax
0x180072898  lea     rcx, [rsp+1A78h+var_1968]; this
0x1800728a0  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800728a5  mov     rcx, [rsp+1A78h+var_48]
0x1800728ad  xor     rcx, rsp; StackCookie
0x1800728b0  call    __security_check_cookie
0x1800728b5  add     rsp, 1A40h
0x1800728bc  pop     r15
0x1800728be  pop     r14
0x1800728c0  pop     r13
0x1800728c2  pop     r12
0x1800728c4  pop     rdi
0x1800728c5  pop     rsi
0x1800728c6  pop     rbx
0x1800728c7  retn
0x1800728c8  jmp     short loc_180072889
0x1800728ca  jmp     short loc_180072889
0x1800728cc  jmp     short loc_180072889
```
