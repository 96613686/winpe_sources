# CClientContext::CleanupSessions(void)

- ea: `0x180004604`
- end: `0x180004b11`
- name: `?CleanupSessions@CClientContext@@QEAAXXZ`
- size: `1293`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002ad0`
- `0x180003070`
- `0x180003e40`

## callees

- `0x180003170`
- `0x180004604`
- `0x1800054f4`
- `0x1800057f8`
- `0x180005850`
- `0x18000615c`
- `0x18000a960`
- `0x18003c084`
- `0x18003c514`
- `0x18003ce78`
- `0x180060e4e`
- `0x180060e70`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x1800048eb`
- `KERNEL32!ReleaseSemaphore` at `0x180004917`
- `KERNEL32!ReleaseSemaphore` at `0x180004a82`
- `KERNEL32!ReleaseSemaphore` at `0x180004aae`
- `KERNEL32!ReleaseSemaphore` at `0x1800048eb`
- `KERNEL32!ReleaseSemaphore` at `0x180004917`
- `KERNEL32!ReleaseSemaphore` at `0x180004a82`
- `KERNEL32!ReleaseSemaphore` at `0x180004aae`
- `KERNEL32!GetCurrentThreadId` at `0x180004858`
- `KERNEL32!GetCurrentThreadId` at `0x1800049ef`
- `KERNEL32!GetCurrentThreadId` at `0x180004858`
- `KERNEL32!GetCurrentThreadId` at `0x1800049ef`
- `KERNEL32!EnterCriticalSection` at `0x18000484c`
- `KERNEL32!EnterCriticalSection` at `0x1800049e3`
- `KERNEL32!EnterCriticalSection` at `0x18000484c`
- `KERNEL32!EnterCriticalSection` at `0x1800049e3`
- `KERNEL32!LeaveCriticalSection` at `0x180004943`
- `KERNEL32!LeaveCriticalSection` at `0x180004ada`
- `KERNEL32!LeaveCriticalSection` at `0x180004943`
- `KERNEL32!LeaveCriticalSection` at `0x180004ada`
- `WDSSRV!WdsEndpointClose` at `0x18000495c`
- `WDSSRV!WdsEndpointClose` at `0x1800049a8`
- `WDSSRV!WdsEndpointClose` at `0x18000495c`
- `WDSSRV!WdsEndpointClose` at `0x1800049a8`

## string_xrefs

- `0x18000482b`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180004869`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180004a00`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180004899`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x180004a30`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x1800048c1`: `m_uActiveReaders == 0`
- `0x180004a58`: `m_uActiveReaders == 0`
- `0x1800048fb`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180004a92`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180004927`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`
- `0x180004abe`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

## pseudocode

```c
void __fastcall CClientContext::CleanupSessions(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 v2; // rsi
  unsigned int OwningThread_high; // edi
  unsigned int v4; // r14d
  LONG *p_LockCount; // r8
  __int64 v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // r13
  unsigned int v9; // eax
  unsigned int v10; // eax
  const char *v11; // rdx
  unsigned int v12; // eax
  const char *v13; // rdx
  _QWORD *v14; // rdi
  unsigned int v15; // eax
  const char *v16; // rdx
  void *v17; // rcx
  int v18; // r15d
  LPCRITICAL_SECTION v19; // rbx
  int v20; // r9d
  int DebugInfo; // eax
  int v22; // r9d
  const char *v23; // r8
  unsigned int v24; // edx
  LONG LockSemaphore_high; // edx
  void *v26; // rcx
  unsigned int v27; // r14d
  unsigned int v28; // esi
  _QWORD *i; // rdi
  __int64 v30; // rcx
  int v31; // r9d
  int v32; // eax
  int v33; // r9d
  const char *v34; // r8
  unsigned int v35; // edx
  LONG v36; // edx
  __int64 v37; // [rsp+20h] [rbp-40h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-30h] BYREF
  int v39; // [rsp+38h] [rbp-28h]
  void *v40; // [rsp+40h] [rbp-20h] BYREF
  __int64 v41; // [rsp+48h] [rbp-18h]
  unsigned int v42; // [rsp+90h] [rbp+30h]

  lpCriticalSection = this;
  v40 = 0;
  v41 = 0;
  v39 = 0;
  v2 = 0;
  CAutoWriterLock::Lock((CAutoWriterLock *)&lpCriticalSection);
  OwningThread_high = HIDWORD(this[4].OwningThread);
  v4 = 0;
  v42 = OwningThread_high;
  while ( v4 < OwningThread_high )
  {
    p_LockCount = &this[4].LockCount;
    if ( v4 < HIDWORD(this[4].OwningThread) )
      v2 = *(_QWORD *)(*(_QWORD *)p_LockCount + 8LL * v4);
    v6 = 0;
    if ( *(_DWORD *)(v2 + 28) )
    {
      v7 = 1;
      do
      {
        v8 = *(_QWORD *)(*(_QWORD *)(v2 + 16) + 8 * v6);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 2232), 0) )
        {
          v9 = *(_DWORD *)(v2 + 28);
          if ( (unsigned int)v6 < v9 )
          {
            memmove_0(
              (void *)(*(_QWORD *)(v2 + 16) + 8 * v6),
              (const void *)(*(_QWORD *)(v2 + 16) + 8LL * v7),
              8LL * (v9 - (unsigned int)v6 - 1));
            --*(_DWORD *)(v2 + 28);
          }
          LODWORD(v6) = v6 - 1;
          --v7;
          v10 = CTftpSession::Shutdown((CTftpSession *)v8);
          ElValidateWin32(v10, v11, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x4D7u);
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)(v8 + 8) + 8LL))(v8 + 8);
        }
        v6 = (unsigned int)(v6 + 1);
        ++v7;
      }
      while ( (unsigned int)v6 < *(_DWORD *)(v2 + 28) );
      if ( !*(_DWORD *)(v2 + 28) )
      {
        LODWORD(v37) = 1;
        CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 3, 1, v37);
      }
      OwningThread_high = v42;
      p_LockCount = &this[4].LockCount;
    }
    if ( HIDWORD(::lpCriticalSection[14].DebugInfo) || *(_DWORD *)(v2 + 28) )
    {
      ++v4;
    }
    else
    {
      v12 = CDynArray<CEndpointSessionMapEntry *,CDeallocateNone>::RemoveItem(p_LockCount);
      if ( ElValidateWin32(v12, v13, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x4F4u) )
        goto LABEL_25;
      LODWORD(v37) = 1;
      CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 2, 1, v37);
      v42 = OwningThread_high - 1;
      v14 = (_QWORD *)v2;
      v2 = 0;
      v15 = CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(&v40);
      if ( ElValidateWin32(v15, v16, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x4F4u) )
        goto LABEL_26;
      *v14 = 0;
      v17 = (void *)v14[2];
      if ( v17 )
      {
        operator delete(v17);
        v14[3] = 0;
        v14[2] = 0;
      }
      operator delete(v14);
      OwningThread_high = v42;
    }
  }
  CClientContext::GetEndpointsMarkedToClose(this, &v40);
LABEL_25:
  v14 = 0;
LABEL_26:
  v18 = v39;
  v19 = lpCriticalSection;
  if ( v39 )
  {
    v18 = v39 - 1;
    if ( v39 == 1 )
    {
      EnterCriticalSection(lpCriticalSection);
      if ( LODWORD(v19[1].SpinCount) != GetCurrentThreadId() )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x195u,
          "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
          v20,
          0);
      DebugInfo = (int)v19[2].DebugInfo;
      if ( DebugInfo )
      {
        LODWORD(v19[2].DebugInfo) = DebugInfo - 1;
LABEL_43:
        LeaveCriticalSection(v19);
        goto LABEL_44;
      }
      if ( HIDWORD(v19[1].SpinCount) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x1A1u,
          "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
          v20,
          0);
      v19[1].SpinCount = 0;
      LODWORD(v19[2].DebugInfo) = 0;
      if ( LODWORD(v19[2].LockSemaphore) )
        WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", v20, 0);
      if ( LODWORD(v19[2].SpinCount) )
      {
        if ( ReleaseSemaphore(v19[1].OwningThread, 1, 0) )
          goto LABEL_43;
        v23 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
        v24 = 431;
      }
      else
      {
        LockSemaphore_high = HIDWORD(v19[2].LockSemaphore);
        if ( !LockSemaphore_high || ReleaseSemaphore(*(HANDLE *)&v19[1].LockCount, LockSemaphore_high, 0) )
          goto LABEL_43;
        v23 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
        v24 = 440;
      }
      WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v24, v23, v22, 0);
      goto LABEL_43;
    }
  }
LABEL_44:
  if ( v14 )
  {
    if ( *v14 )
    {
      WdsEndpointClose(*v14);
      *v14 = 0;
    }
    v26 = (void *)v14[2];
    if ( v26 )
    {
      operator delete(v26);
      v14[3] = 0;
      v14[2] = 0;
    }
    operator delete(v14);
  }
  v27 = HIDWORD(v41);
  v28 = 0;
  for ( i = v40; v28 < v27; ++v28 )
  {
    v30 = 0;
    if ( v28 < v27 )
      v30 = i[v28];
    WdsEndpointClose(v30);
  }
  if ( i )
    operator delete(i);
  if ( v18 == 1 )
  {
    EnterCriticalSection(v19);
    if ( LODWORD(v19[1].SpinCount) != GetCurrentThreadId() )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x195u,
        "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
        v31,
        0);
    v32 = (int)v19[2].DebugInfo;
    if ( v32 )
    {
      LODWORD(v19[2].DebugInfo) = v32 - 1;
LABEL_72:
      LeaveCriticalSection(v19);
      return;
    }
    if ( HIDWORD(v19[1].SpinCount) )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x1A1u,
        "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
        v31,
        0);
    v19[1].SpinCount = 0;
    LODWORD(v19[2].DebugInfo) = 0;
    if ( LODWORD(v19[2].LockSemaphore) )
      WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", v31, 0);
    if ( LODWORD(v19[2].SpinCount) )
    {
      if ( ReleaseSemaphore(v19[1].OwningThread, 1, 0) )
        goto LABEL_72;
      v34 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
      v35 = 431;
    }
    else
    {
      v36 = HIDWORD(v19[2].LockSemaphore);
      if ( !v36 || ReleaseSemaphore(*(HANDLE *)&v19[1].LockCount, v36, 0) )
        goto LABEL_72;
      v34 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
      v35 = 440;
    }
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v35, v34, v33, 0);
    goto LABEL_72;
  }
}

```

## disassembly

```asm
0x180004604  mov     [rsp-28h+arg_8], rbx
0x180004609  mov     [rsp-28h+arg_10], rsi
0x18000460e  mov     [rsp-28h+arg_18], rdi
0x180004613  push    rbp
0x180004614  push    r12
0x180004616  push    r13
0x180004618  push    r14
0x18000461a  push    r15
0x18000461c  mov     rbp, rsp
0x18000461f  sub     rsp, 60h
0x180004623  xor     r12d, r12d
0x180004626  mov     [rbp+lpCriticalSection], rcx
0x18000462a  mov     r15, rcx
0x18000462d  mov     [rbp+var_20], r12
0x180004631  lea     rcx, [rbp+lpCriticalSection]; this
0x180004635  mov     [rbp+var_18], r12
0x180004639  mov     r13d, r12d
0x18000463c  mov     [rbp+var_28], r12d
0x180004640  mov     esi, r12d
0x180004643  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180004648  mov     edi, [r15+0B4h]
0x18000464f  mov     r14d, r12d
0x180004652  mov     [rbp+arg_0], edi
0x180004655  test    edi, edi
0x180004657  jz      loc_180004818
0x18000465d  lea     r8, [r15+0A8h]
0x180004664  cmp     r14d, [r8+0Ch]
0x180004668  jnb     short loc_180004674
0x18000466a  mov     rax, [r8]
0x18000466d  mov     ecx, r14d
0x180004670  mov     rsi, [rax+rcx*8]
0x180004674  mov     r12d, [rsi+1Ch]
0x180004678  xor     ebx, ebx
0x18000467a  test    r12d, r12d
0x18000467d  jz      loc_180004750
0x180004683  lea     edi, [rbx+1]
0x180004686  cmp     ebx, r12d
0x180004689  jnb     short loc_180004693
0x18000468b  mov     rax, [rsi+10h]
0x18000468f  mov     r13, [rax+rbx*8]
0x180004693  xor     eax, eax
0x180004695  lock xadd [r13+8B8h], eax
0x18000469e  test    eax, eax
0x1800046a0  jz      short loc_180004702
0x1800046a2  mov     eax, [rsi+1Ch]
0x1800046a5  cmp     ebx, eax
0x1800046a7  jnb     short loc_1800046C9
0x1800046a9  mov     rcx, [rsi+10h]
0x1800046ad  sub     eax, ebx
0x1800046af  lea     r8d, [rax-1]
0x1800046b3  mov     eax, edi
0x1800046b5  shl     r8, 3; Size
0x1800046b9  lea     rdx, [rcx+rax*8]; Src
0x1800046bd  lea     rcx, [rcx+rbx*8]; void *
0x1800046c1  call    memmove_0
0x1800046c6  dec     dword ptr [rsi+1Ch]
0x1800046c9  mov     rcx, r13; this
0x1800046cc  dec     ebx
0x1800046ce  dec     edi
0x1800046d0  call    ?Shutdown@CTftpSession@@QEAAKXZ; CTftpSession::Shutdown(void)
0x1800046d5  mov     ecx, eax; unsigned int
0x1800046d7  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800046de  mov     r9d, 4D7h; unsigned int
0x1800046e4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800046e9  test    r13, r13
0x1800046ec  jz      short loc_180004702
0x1800046ee  lea     rcx, [r13+8]
0x1800046f2  mov     rax, [rcx]
0x1800046f5  mov     rax, [rax+8]
0x1800046f9  call    cs:__guard_dispatch_icall_fptr
0x1800046ff  xor     r13d, r13d
0x180004702  inc     ebx
0x180004704  inc     edi
0x180004706  cmp     ebx, [rsi+1Ch]
0x180004709  jb      short loc_18000468B
0x18000470b  test    r12d, r12d
0x18000470e  jz      short loc_180004746
0x180004710  xor     r12d, r12d
0x180004713  cmp     [rsi+1Ch], r12d
0x180004717  jnz     short loc_18000473A
0x180004719  lea     edx, [r12+1]; unsigned int
0x18000471e  mov     [rsp+60h+var_40], 1
0x180004726  mov     r9d, edx
0x180004729  lea     r8d, [r12+3]
0x18000472e  lea     rcx, qword_1800779F0; this
0x180004735  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x18000473a  mov     edi, [rbp+arg_0]
0x18000473d  lea     r8, [r15+0A8h]
0x180004744  jmp     short loc_180004753
0x180004746  mov     edi, [rbp+arg_0]
0x180004749  lea     r8, [r15+0A8h]
0x180004750  xor     r12d, r12d
0x180004753  mov     rax, cs:lpCriticalSection
0x18000475a  cmp     [rax+234h], r12d
0x180004761  jnz     loc_18000480C
0x180004767  cmp     [rsi+1Ch], r12d
0x18000476b  jnz     loc_18000480C
0x180004771  mov     edx, r14d
0x180004774  mov     rcx, r8
0x180004777  call    ?RemoveItem@?$CDynArray@PEAVCEndpointSessionMapEntry@@VCDeallocateNone@@@@QEAAKK@Z; CDynArray<CEndpointSessionMapEntry *,CDeallocateNone>::RemoveItem(ulong)
0x18000477c  mov     r9d, 4F4h; unsigned int
0x180004782  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x180004789  mov     ecx, eax; unsigned int
0x18000478b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004790  test    eax, eax
0x180004792  jnz     loc_180004824
0x180004798  mov     eax, 1
0x18000479d  lea     rcx, qword_1800779F0; this
0x1800047a4  mov     r9d, eax
0x1800047a7  mov     [rsp+60h+var_40], eax
0x1800047ab  mov     edx, eax; unsigned int
0x1800047ad  lea     r8d, [rax+1]
0x1800047b1  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x1800047b6  dec     edi
0x1800047b8  lea     rcx, [rbp+var_20]
0x1800047bc  mov     [rbp+arg_0], edi
0x1800047bf  mov     rdi, rsi
0x1800047c2  mov     rsi, r12
0x1800047c5  mov     rdx, [rdi]
0x1800047c8  call    ?AddItem@?$CDynArray@PEAVCTptReadFile@@VCDeallocateNone@@@@QEAAKPEAVCTptReadFile@@@Z; CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(CTptReadFile *)
0x1800047cd  mov     r9d, 4F4h; unsigned int
0x1800047d3  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800047da  mov     ecx, eax; unsigned int
0x1800047dc  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800047e1  test    eax, eax
0x1800047e3  jnz     short loc_180004827
0x1800047e5  mov     [rdi], r12
0x1800047e8  mov     rcx, [rdi+10h]; void *
0x1800047ec  test    rcx, rcx
0x1800047ef  jz      short loc_1800047FF
0x1800047f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800047f6  and     qword ptr [rdi+18h], 0
0x1800047fb  mov     [rdi+10h], r12
0x1800047ff  mov     rcx, rdi; void *
0x180004802  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004807  mov     edi, [rbp+arg_0]
0x18000480a  jmp     short loc_18000480F
0x18000480c  inc     r14d
0x18000480f  cmp     r14d, edi
0x180004812  jb      loc_18000465D
0x180004818  lea     rdx, [rbp+var_20]
0x18000481c  mov     rcx, r15
0x18000481f  call    ?GetEndpointsMarkedToClose@CClientContext@@AEAAKPEAV?$CDynArray@PEAXVCDeallocateNone@@@@@Z; CClientContext::GetEndpointsMarkedToClose(CDynArray<void *,CDeallocateNone> *)
0x180004824  mov     rdi, r12
0x180004827  mov     r15d, [rbp+var_28]
0x18000482b  lea     r13, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180004832  mov     rbx, [rbp+lpCriticalSection]
0x180004836  test    r15d, r15d
0x180004839  jz      loc_18000494F
0x18000483f  add     r15d, 0FFFFFFFFh
0x180004843  jnz     loc_18000494F
0x180004849  mov     rcx, rbx; lpCriticalSection
0x18000484c  call    cs:__imp_EnterCriticalSection
0x180004853  nop     dword ptr [rax+rax+00h]
0x180004858  call    cs:__imp_GetCurrentThreadId
0x18000485f  nop     dword ptr [rax+rax+00h]
0x180004864  cmp     [rbx+48h], eax
0x180004867  jz      short loc_180004882
0x180004869  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x180004870  mov     [rsp+60h+var_40], r12d; int
0x180004875  mov     edx, 195h; unsigned int
0x18000487a  mov     rcx, r13; char *
0x18000487d  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004882  mov     eax, [rbx+50h]
0x180004885  test    eax, eax
0x180004887  jz      short loc_180004893
0x180004889  dec     eax
0x18000488b  mov     [rbx+50h], eax
0x18000488e  jmp     loc_180004940
0x180004893  cmp     [rbx+4Ch], r12d
0x180004897  jz      short loc_1800048B2
0x180004899  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x1800048a0  mov     [rsp+60h+var_40], r12d; int
0x1800048a5  mov     edx, 1A1h; unsigned int
0x1800048aa  mov     rcx, r13; char *
0x1800048ad  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800048b2  xor     eax, eax
0x1800048b4  mov     [rbx+48h], rax
0x1800048b8  mov     [rbx+50h], eax
0x1800048bb  cmp     [rbx+68h], r12d
0x1800048bf  jz      short loc_1800048DA
0x1800048c1  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x1800048c8  mov     [rsp+60h+var_40], r12d; int
0x1800048cd  mov     edx, 1A4h; unsigned int
0x1800048d2  mov     rcx, r13; char *
0x1800048d5  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800048da  cmp     [rbx+70h], r12d
0x1800048de  jz      short loc_180004909
0x1800048e0  mov     rcx, [rbx+38h]; hSemaphore
0x1800048e4  xor     r8d, r8d; lpPreviousCount
0x1800048e7  lea     edx, [r8+1]; lReleaseCount
0x1800048eb  call    cs:__imp_ReleaseSemaphore
0x1800048f2  nop     dword ptr [rax+rax+00h]
0x1800048f7  test    eax, eax
0x1800048f9  jnz     short loc_180004940
0x1800048fb  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180004902  mov     edx, 1AFh
0x180004907  jmp     short loc_180004933
0x180004909  mov     edx, [rbx+6Ch]; lReleaseCount
0x18000490c  test    edx, edx
0x18000490e  jz      short loc_180004940
0x180004910  mov     rcx, [rbx+30h]; hSemaphore
0x180004914  xor     r8d, r8d; lpPreviousCount
0x180004917  call    cs:__imp_ReleaseSemaphore
0x18000491e  nop     dword ptr [rax+rax+00h]
0x180004923  test    eax, eax
0x180004925  jnz     short loc_180004940
0x180004927  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x18000492e  mov     edx, 1B8h; unsigned int
0x180004933  mov     rcx, r13; char *
0x180004936  mov     [rsp+60h+var_40], r12d; int
0x18000493b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004940  mov     rcx, rbx; lpCriticalSection
0x180004943  call    cs:__imp_LeaveCriticalSection
0x18000494a  nop     dword ptr [rax+rax+00h]
0x18000494f  test    rdi, rdi
0x180004952  jz      short loc_18000498A
0x180004954  mov     rcx, [rdi]
0x180004957  test    rcx, rcx
0x18000495a  jz      short loc_18000496B
0x18000495c  call    cs:__imp_WdsEndpointClose
0x180004963  nop     dword ptr [rax+rax+00h]
0x180004968  mov     [rdi], r12
0x18000496b  mov     rcx, [rdi+10h]; void *
0x18000496f  test    rcx, rcx
0x180004972  jz      short loc_180004982
0x180004974  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004979  and     qword ptr [rdi+18h], 0
0x18000497e  mov     [rdi+10h], r12
0x180004982  mov     rcx, rdi; void *
0x180004985  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000498a  mov     r14d, dword ptr [rbp+var_18+4]
0x18000498e  mov     esi, r12d
0x180004991  mov     rdi, [rbp+var_20]
0x180004995  test    r14d, r14d
0x180004998  jz      short loc_1800049BB
0x18000499a  mov     rcx, r12
0x18000499d  cmp     esi, r14d
0x1800049a0  jnb     short loc_1800049A8
0x1800049a2  mov     eax, esi
0x1800049a4  mov     rcx, [rdi+rax*8]
0x1800049a8  call    cs:__imp_WdsEndpointClose
0x1800049af  nop     dword ptr [rax+rax+00h]
0x1800049b4  inc     esi
0x1800049b6  cmp     esi, r14d
0x1800049b9  jb      short loc_18000499A
0x1800049bb  test    rdi, rdi
0x1800049be  jz      short loc_1800049CB
0x1800049c0  mov     rcx, rdi; void *
0x1800049c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800049c8  mov     rdi, r12
0x1800049cb  test    r15d, r15d
0x1800049ce  jz      loc_180004AE6
0x1800049d4  lea     eax, [r15-1]
0x1800049d8  test    eax, eax
0x1800049da  jnz     loc_180004AE6
0x1800049e0  mov     rcx, rbx; lpCriticalSection
0x1800049e3  call    cs:__imp_EnterCriticalSection
0x1800049ea  nop     dword ptr [rax+rax+00h]
0x1800049ef  call    cs:__imp_GetCurrentThreadId
0x1800049f6  nop     dword ptr [rax+rax+00h]
0x1800049fb  cmp     [rbx+48h], eax
0x1800049fe  jz      short loc_180004A19
0x180004a00  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x180004a07  mov     [rsp+60h+var_40], r12d; int
0x180004a0c  mov     edx, 195h; unsigned int
0x180004a11  mov     rcx, r13; char *
0x180004a14  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004a19  mov     eax, [rbx+50h]
0x180004a1c  test    eax, eax
0x180004a1e  jz      short loc_180004A2A
0x180004a20  dec     eax
0x180004a22  mov     [rbx+50h], eax
0x180004a25  jmp     loc_180004AD7
0x180004a2a  cmp     [rbx+4Ch], r12d
0x180004a2e  jz      short loc_180004A49
0x180004a30  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x180004a37  mov     [rsp+60h+var_40], r12d; int
0x180004a3c  mov     edx, 1A1h; unsigned int
0x180004a41  mov     rcx, r13; char *
0x180004a44  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004a49  xor     eax, eax
0x180004a4b  mov     [rbx+48h], rax
0x180004a4f  mov     [rbx+50h], eax
0x180004a52  cmp     [rbx+68h], r12d
0x180004a56  jz      short loc_180004A71
0x180004a58  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x180004a5f  mov     [rsp+60h+var_40], r12d; int
0x180004a64  mov     edx, 1A4h; unsigned int
0x180004a69  mov     rcx, r13; char *
0x180004a6c  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004a71  cmp     [rbx+70h], r12d
0x180004a75  jz      short loc_180004AA0
0x180004a77  mov     rcx, [rbx+38h]; hSemaphore
0x180004a7b  xor     r8d, r8d; lpPreviousCount
0x180004a7e  lea     edx, [r8+1]; lReleaseCount
0x180004a82  call    cs:__imp_ReleaseSemaphore
0x180004a89  nop     dword ptr [rax+rax+00h]
0x180004a8e  test    eax, eax
0x180004a90  jnz     short loc_180004AD7
  ... truncated ...
```
