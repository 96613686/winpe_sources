# CTftpServer::CreateDataPortPool(void)

- ea: `0x180002544`
- end: `0x18000277c`
- name: `?CreateDataPortPool@CTftpServer@@AEAAKXZ`
- size: `568`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800012e0`
- `0x180002ad0`

## callees

- `0x180002544`
- `0x180003170`
- `0x180003cb4`
- `0x18003c514`
- `0x18003ce78`
- `0x180060e70`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180002701`
- `KERNEL32!ReleaseSemaphore` at `0x18000272d`
- `KERNEL32!ReleaseSemaphore` at `0x180002701`
- `KERNEL32!ReleaseSemaphore` at `0x18000272d`
- `KERNEL32!GetCurrentThreadId` at `0x180002669`
- `KERNEL32!GetCurrentThreadId` at `0x180002669`
- `KERNEL32!EnterCriticalSection` at `0x18000265d`
- `KERNEL32!EnterCriticalSection` at `0x18000265d`
- `KERNEL32!LeaveCriticalSection` at `0x180002759`
- `KERNEL32!LeaveCriticalSection` at `0x180002759`

## string_xrefs

- `0x180002579`: `-> CTftpServer::CreateDataPortPool`
- `0x1800025f1`: `CTftpServer::CreateDataPortPool: Data port pool initialized with %u ports (%u configured).`
- `0x18000260d`: `CTftpServer::CreateDataPortPool: Unable to initialize data port pool (0x%08x).`
- `0x18000262e`: `<- CTftpServer::CreateDataPortPool=%x`
- `0x180002675`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180002686`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x1800026b6`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x1800026dc`: `m_uActiveReaders == 0`
- `0x180002711`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x18000273d`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

## pseudocode

```c
__int64 __fastcall CTftpServer::CreateDataPortPool(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v2; // edi
  void (*v3)(unsigned int, const unsigned __int16 *, ...); // rax
  __int64 OwningThread_high; // r8
  unsigned int v5; // ecx
  __int64 v6; // rsi
  const char *v7; // rdx
  LPCRITICAL_SECTION v8; // rbx
  int v9; // r9d
  int DebugInfo; // eax
  int v11; // r9d
  const char *v12; // r8
  unsigned int v13; // edx
  LONG LockSemaphore_high; // edx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-18h] BYREF
  int v17; // [rsp+38h] [rbp-10h]

  lpCriticalSection = this;
  v2 = 0;
  v17 = 0;
  CAutoWriterLock::Lock((CAutoWriterLock *)&lpCriticalSection);
  v3 = g_ErrLibTraceFunctionEx;
  if ( g_ErrLibTraceFunctionEx )
  {
    g_ErrLibTraceFunctionEx(0x10000u, L"-> CTftpServer::CreateDataPortPool");
    v3 = g_ErrLibTraceFunctionEx;
  }
  OwningThread_high = HIDWORD(this[12].OwningThread);
  v5 = HIDWORD(this[13].LockSemaphore) - OwningThread_high;
  if ( v5 )
  {
    v6 = v5;
    do
    {
      v2 = CClientContext::AddNewEndpoint((CClientContext *)&this[8], 0);
      ElValidateWin32(v2, v7, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x3C6u);
      --v6;
    }
    while ( v6 );
    OwningThread_high = HIDWORD(this[12].OwningThread);
    v3 = g_ErrLibTraceFunctionEx;
  }
  if ( (_DWORD)OwningThread_high )
  {
    v2 = 0;
    if ( !v3 )
      goto LABEL_14;
    v3(
      0x20000u,
      L"CTftpServer::CreateDataPortPool: Data port pool initialized with %u ports (%u configured).",
      OwningThread_high,
      HIDWORD(this[13].LockSemaphore));
  }
  else
  {
    if ( !v3 )
      goto LABEL_14;
    v3(0x80000u, L"CTftpServer::CreateDataPortPool: Unable to initialize data port pool (0x%08x).", v2);
  }
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(0x10000u, L"<- CTftpServer::CreateDataPortPool=%x", v2);
LABEL_14:
  if ( v17 == 1 )
  {
    v8 = lpCriticalSection;
    EnterCriticalSection(lpCriticalSection);
    if ( LODWORD(v8[1].SpinCount) != GetCurrentThreadId() )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x195u,
        "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
        v9,
        0);
    DebugInfo = (int)v8[2].DebugInfo;
    if ( DebugInfo )
    {
      LODWORD(v8[2].DebugInfo) = DebugInfo - 1;
LABEL_30:
      LeaveCriticalSection(v8);
      return v2;
    }
    if ( HIDWORD(v8[1].SpinCount) )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x1A1u,
        "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
        v9,
        0);
    v8[1].SpinCount = 0;
    LODWORD(v8[2].DebugInfo) = 0;
    if ( LODWORD(v8[2].LockSemaphore) )
      WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", v9, 0);
    if ( LODWORD(v8[2].SpinCount) )
    {
      if ( ReleaseSemaphore(v8[1].OwningThread, 1, 0) )
        goto LABEL_30;
      v12 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
      v13 = 431;
    }
    else
    {
      LockSemaphore_high = HIDWORD(v8[2].LockSemaphore);
      if ( !LockSemaphore_high || ReleaseSemaphore(*(HANDLE *)&v8[1].LockCount, LockSemaphore_high, 0) )
        goto LABEL_30;
      v12 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
      v13 = 440;
    }
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v13, v12, v11, 0);
    goto LABEL_30;
  }
  return v2;
}

```

## disassembly

```asm
0x180002544  mov     rax, rsp
0x180002547  mov     [rax+8], rbx
0x18000254b  mov     [rax+10h], rbp
0x18000254f  mov     [rax+18h], rsi
0x180002553  push    rdi
0x180002554  sub     rsp, 40h
0x180002558  mov     rbx, rcx
0x18000255b  mov     [rax-18h], rcx
0x18000255f  xor     edi, edi
0x180002561  lea     rcx, [rax-18h]; this
0x180002565  and     [rax-10h], edi
0x180002568  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x18000256d  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180002574  test    rax, rax
0x180002577  jz      short loc_180002592
0x180002579  lea     rdx, aCtftpserverCre; "-> CTftpServer::CreateDataPortPool"
0x180002580  mov     ecx, 10000h
0x180002585  call    cs:__guard_dispatch_icall_fptr
0x18000258b  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180002592  mov     ecx, [rbx+224h]
0x180002598  mov     r8d, [rbx+1F4h]
0x18000259f  sub     ecx, r8d
0x1800025a2  jz      short loc_1800025DE
0x1800025a4  mov     esi, ecx
0x1800025a6  xor     edx, edx; unsigned int *
0x1800025a8  lea     rcx, [rbx+140h]; this
0x1800025af  call    ?AddNewEndpoint@CClientContext@@QEAAKPEAK@Z; CClientContext::AddNewEndpoint(ulong *)
0x1800025b4  mov     r9d, 3C6h; unsigned int
0x1800025ba  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800025c1  mov     ecx, eax; unsigned int
0x1800025c3  mov     edi, eax
0x1800025c5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800025ca  sub     rsi, 1
0x1800025ce  jnz     short loc_1800025A6
0x1800025d0  mov     r8d, [rbx+1F4h]
0x1800025d7  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800025de  test    r8d, r8d
0x1800025e1  jz      short loc_180002605
0x1800025e3  xor     edi, edi
0x1800025e5  test    rax, rax
0x1800025e8  jz      short loc_180002640
0x1800025ea  mov     r9d, [rbx+224h]
0x1800025f1  lea     rdx, aCtftpserverCre_2; "CTftpServer::CreateDataPortPool: Data p"...
0x1800025f8  mov     ecx, 20000h
0x1800025fd  call    cs:__guard_dispatch_icall_fptr
0x180002603  jmp     short loc_18000261F
0x180002605  test    rax, rax
0x180002608  jz      short loc_180002640
0x18000260a  mov     r8d, edi
0x18000260d  lea     rdx, aCtftpserverCre_1; "CTftpServer::CreateDataPortPool: Unable"...
0x180002614  mov     ecx, 80000h
0x180002619  call    cs:__guard_dispatch_icall_fptr
0x18000261f  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180002626  test    rax, rax
0x180002629  jz      short loc_180002640
0x18000262b  mov     r8d, edi
0x18000262e  lea     rdx, aCtftpserverCre_0; "<- CTftpServer::CreateDataPortPool=%x"
0x180002635  mov     ecx, 10000h
0x18000263a  call    cs:__guard_dispatch_icall_fptr
0x180002640  mov     eax, [rsp+48h+var_10]
0x180002644  test    eax, eax
0x180002646  jz      loc_180002765
0x18000264c  cmp     eax, 1
0x18000264f  jnz     loc_180002765
0x180002655  mov     rbx, [rsp+48h+lpCriticalSection]
0x18000265a  mov     rcx, rbx; lpCriticalSection
0x18000265d  call    cs:__imp_EnterCriticalSection
0x180002664  nop     dword ptr [rax+rax+00h]
0x180002669  call    cs:__imp_GetCurrentThreadId
0x180002670  nop     dword ptr [rax+rax+00h]
0x180002675  lea     rsi, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000267c  cmp     [rbx+48h], eax
0x18000267f  jz      short loc_18000269A
0x180002681  and     [rsp+48h+var_28], 0
0x180002686  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x18000268d  mov     edx, 195h; unsigned int
0x180002692  mov     rcx, rsi; char *
0x180002695  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000269a  mov     eax, [rbx+50h]
0x18000269d  test    eax, eax
0x18000269f  jz      short loc_1800026AB
0x1800026a1  dec     eax
0x1800026a3  mov     [rbx+50h], eax
0x1800026a6  jmp     loc_180002756
0x1800026ab  cmp     dword ptr [rbx+4Ch], 0
0x1800026af  jz      short loc_1800026CA
0x1800026b1  and     [rsp+48h+var_28], 0
0x1800026b6  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x1800026bd  mov     edx, 1A1h; unsigned int
0x1800026c2  mov     rcx, rsi; char *
0x1800026c5  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800026ca  xor     eax, eax
0x1800026cc  mov     [rbx+48h], rax
0x1800026d0  mov     [rbx+50h], eax
0x1800026d3  cmp     [rbx+68h], eax
0x1800026d6  jz      short loc_1800026F0
0x1800026d8  and     [rsp+48h+var_28], eax
0x1800026dc  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x1800026e3  mov     edx, 1A4h; unsigned int
0x1800026e8  mov     rcx, rsi; char *
0x1800026eb  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800026f0  cmp     dword ptr [rbx+70h], 0
0x1800026f4  jz      short loc_18000271F
0x1800026f6  mov     rcx, [rbx+38h]; hSemaphore
0x1800026fa  xor     r8d, r8d; lpPreviousCount
0x1800026fd  lea     edx, [r8+1]; lReleaseCount
0x180002701  call    cs:__imp_ReleaseSemaphore
0x180002708  nop     dword ptr [rax+rax+00h]
0x18000270d  test    eax, eax
0x18000270f  jnz     short loc_180002756
0x180002711  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180002718  mov     edx, 1AFh
0x18000271d  jmp     short loc_180002749
0x18000271f  mov     edx, [rbx+6Ch]; lReleaseCount
0x180002722  test    edx, edx
0x180002724  jz      short loc_180002756
0x180002726  mov     rcx, [rbx+30h]; hSemaphore
0x18000272a  xor     r8d, r8d; lpPreviousCount
0x18000272d  call    cs:__imp_ReleaseSemaphore
0x180002734  nop     dword ptr [rax+rax+00h]
0x180002739  test    eax, eax
0x18000273b  jnz     short loc_180002756
0x18000273d  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x180002744  mov     edx, 1B8h; unsigned int
0x180002749  and     [rsp+48h+var_28], 0
0x18000274e  mov     rcx, rsi; char *
0x180002751  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180002756  mov     rcx, rbx; lpCriticalSection
0x180002759  call    cs:__imp_LeaveCriticalSection
0x180002760  nop     dword ptr [rax+rax+00h]
0x180002765  mov     rbx, [rsp+48h+arg_0]
0x18000276a  mov     eax, edi
0x18000276c  mov     rbp, [rsp+48h+arg_8]
0x180002771  mov     rsi, [rsp+48h+arg_10]
0x180002776  add     rsp, 40h
0x18000277a  pop     rdi
0x18000277b  retn
```
