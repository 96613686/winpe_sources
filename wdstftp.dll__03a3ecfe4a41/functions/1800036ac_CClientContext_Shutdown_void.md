# CClientContext::Shutdown(void)

- ea: `0x1800036ac`
- end: `0x180003b24`
- name: `?Shutdown@CClientContext@@QEAAKXZ`
- size: `1144`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001754`
- `0x18000362c`

## callees

- `0x180003170`
- `0x1800036ac`
- `0x1800054f4`
- `0x180005850`
- `0x18000615c`
- `0x18000a960`
- `0x18003a940`
- `0x18003c084`
- `0x18003c514`
- `0x18003ce78`
- `0x180060e70`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180003a90`
- `KERNEL32!ReleaseSemaphore` at `0x180003abc`
- `KERNEL32!ReleaseSemaphore` at `0x180003a90`
- `KERNEL32!ReleaseSemaphore` at `0x180003abc`
- `KERNEL32!GetCurrentThreadId` at `0x1800039f6`
- `KERNEL32!GetCurrentThreadId` at `0x1800039f6`
- `KERNEL32!EnterCriticalSection` at `0x1800036e0`
- `KERNEL32!EnterCriticalSection` at `0x1800039ea`
- `KERNEL32!EnterCriticalSection` at `0x1800036e0`
- `KERNEL32!EnterCriticalSection` at `0x1800039ea`
- `KERNEL32!LeaveCriticalSection` at `0x180003ae8`
- `KERNEL32!LeaveCriticalSection` at `0x180003af8`
- `KERNEL32!LeaveCriticalSection` at `0x180003ae8`
- `KERNEL32!LeaveCriticalSection` at `0x180003af8`
- `WDSSRV!WdsEndpointClose` at `0x18000399a`
- `WDSSRV!WdsEndpointClose` at `0x18000399a`

## string_xrefs

- `0x180003a02`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180003a0e`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180003a3e`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x180003a66`: `m_uActiveReaders == 0`
- `0x180003aa0`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180003acc`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

## pseudocode

```c
__int64 __fastcall CClientContext::Shutdown(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v1; // r12d
  const char *v3; // rdx
  unsigned int v4; // r15d
  LPCRITICAL_SECTION v5; // rbx
  unsigned int EndpointsMarkedToClose; // edi
  __int64 v7; // r14
  const char *v8; // rdx
  unsigned int v9; // edi
  __int64 v10; // r13
  const char *v11; // rdx
  const char *v12; // rdx
  void *v13; // rcx
  const char *v14; // rdx
  const char *v15; // rdx
  void *v16; // rcx
  void *v17; // rcx
  const char *v18; // rdx
  int v19; // esi
  _QWORD *v20; // r14
  unsigned int v21; // r15d
  unsigned int i; // r12d
  const char *v23; // rdx
  int v24; // r9d
  int DebugInfo; // eax
  int v26; // r9d
  const char *v27; // r8
  unsigned int v28; // edx
  LONG LockSemaphore_high; // edx
  __int64 v31; // [rsp+20h] [rbp-48h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-38h] BYREF
  int v33; // [rsp+38h] [rbp-30h]
  void *v34; // [rsp+40h] [rbp-28h] BYREF
  __int64 v35; // [rsp+48h] [rbp-20h]
  unsigned int v36; // [rsp+B0h] [rbp+48h]
  CTftpSession *v37; // [rsp+B8h] [rbp+50h]
  struct _RTL_CRITICAL_SECTION *v38; // [rsp+C8h] [rbp+60h]

  v1 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  v38 = this + 3;
  EnterCriticalSection(this + 3);
  lpCriticalSection = this;
  v33 = 0;
  CAutoWriterLock::Lock((CAutoWriterLock *)&lpCriticalSection);
  v4 = 0;
  v5 = lpCriticalSection;
  LODWORD(this[4].DebugInfo) = 1;
  if ( HIDWORD(this[4].OwningThread) )
  {
    do
    {
      EndpointsMarkedToClose = 0;
      if ( v4 < HIDWORD(this[4].OwningThread) )
      {
        v7 = *(_QWORD *)(*(_QWORD *)&this[4].LockCount + 8LL * v4);
      }
      else
      {
        EndpointsMarkedToClose = 1413;
        v7 = 0;
      }
      if ( ElValidateWin32(
             EndpointsMarkedToClose,
             v3,
             "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp",
             0x18Fu) )
      {
        goto LABEL_42;
      }
      v9 = *(_DWORD *)(v7 + 28);
      v36 = v9;
      if ( v9 )
      {
        v10 = 0;
        do
        {
          EndpointsMarkedToClose = 0;
          if ( v1 < *(_DWORD *)(v7 + 28) )
            v37 = *(CTftpSession **)(*(_QWORD *)(v7 + 16) + v10);
          else
            EndpointsMarkedToClose = 1413;
          if ( ElValidateWin32(
                 EndpointsMarkedToClose,
                 v8,
                 "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp",
                 0x19Eu) )
          {
            goto LABEL_42;
          }
          EndpointsMarkedToClose = 0;
          if ( v1 < *(_DWORD *)(v7 + 28) )
            *(_QWORD *)(*(_QWORD *)(v7 + 16) + v10) = 0;
          else
            EndpointsMarkedToClose = 1413;
          if ( ElValidateWin32(
                 EndpointsMarkedToClose,
                 v11,
                 "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp",
                 0x1A1u) )
          {
            goto LABEL_42;
          }
          EndpointsMarkedToClose = CTftpSession::Shutdown(v37);
          if ( ElValidateWin32(
                 EndpointsMarkedToClose,
                 v12,
                 "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp",
                 0x1A4u) )
          {
            goto LABEL_42;
          }
          if ( v37 )
          {
            (*(void (__fastcall **)(__int64))(*((_QWORD *)v37 + 1) + 8LL))((__int64)v37 + 8);
            v37 = 0;
          }
          v9 = v36;
          ++v1;
          v10 += 8;
        }
        while ( v1 < v36 );
      }
      v13 = *(void **)(v7 + 16);
      v1 = 0;
      if ( v13 )
      {
        operator delete(v13);
        *(_QWORD *)(v7 + 16) = 0;
        *(_QWORD *)(v7 + 24) = 0;
      }
      if ( v9 )
      {
        LODWORD(v31) = 1;
        CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 3, 1, v31);
      }
      EndpointsMarkedToClose = CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(&v34);
      if ( ElValidateWin32(
             EndpointsMarkedToClose,
             v14,
             "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp",
             0x1BCu) )
      {
        goto LABEL_42;
      }
      EndpointsMarkedToClose = 0;
      if ( v4 < HIDWORD(this[4].OwningThread) )
        *(_QWORD *)(*(_QWORD *)&this[4].LockCount + 8LL * v4) = 0;
      else
        EndpointsMarkedToClose = 1413;
      if ( ElValidateWin32(
             EndpointsMarkedToClose,
             v15,
             "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp",
             0x1BFu) )
      {
        goto LABEL_42;
      }
      LODWORD(v31) = 1;
      CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 2, 1, v31);
      v16 = *(void **)(v7 + 16);
      if ( v16 )
      {
        operator delete(v16);
        *(_QWORD *)(v7 + 16) = 0;
        *(_QWORD *)(v7 + 24) = 0;
      }
      operator delete((void *)v7);
    }
    while ( ++v4 < HIDWORD(this[4].OwningThread) );
  }
  v17 = *(void **)&this[4].LockCount;
  if ( v17 )
  {
    operator delete(v17);
    this[4].OwningThread = 0;
    *(_QWORD *)&this[4].LockCount = 0;
  }
  EndpointsMarkedToClose = CClientContext::GetEndpointsMarkedToClose(this, &v34);
  if ( ElValidateWin32(
         EndpointsMarkedToClose,
         v18,
         "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp",
         0x1D3u) )
  {
LABEL_42:
    v20 = v34;
    v19 = v33;
    goto LABEL_43;
  }
  v19 = v33;
  if ( v33 )
  {
    v19 = v33 - 1;
    if ( v33 == 1 )
      CMRSWLock::WriterRelease((CMRSWLock *)v5);
  }
  v20 = v34;
  v21 = 0;
  for ( i = HIDWORD(v35); v21 < i; ++v21 )
  {
    EndpointsMarkedToClose = WdsEndpointClose(v20[v21]);
    if ( ElValidateWin32(
           EndpointsMarkedToClose,
           v23,
           "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp",
           0x1E1u) )
    {
      break;
    }
  }
LABEL_43:
  if ( v19 != 1 )
    goto LABEL_60;
  EnterCriticalSection(v5);
  if ( LODWORD(v5[1].SpinCount) != GetCurrentThreadId() )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x195u,
      "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
      v24,
      0);
  DebugInfo = (int)v5[2].DebugInfo;
  if ( !DebugInfo )
  {
    if ( HIDWORD(v5[1].SpinCount) )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x1A1u,
        "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
        v24,
        0);
    v5[1].SpinCount = 0;
    LODWORD(v5[2].DebugInfo) = 0;
    if ( LODWORD(v5[2].LockSemaphore) )
      WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", v24, 0);
    if ( LODWORD(v5[2].SpinCount) )
    {
      if ( ReleaseSemaphore(v5[1].OwningThread, 1, 0) )
        goto LABEL_59;
      v27 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
      v28 = 431;
    }
    else
    {
      LockSemaphore_high = HIDWORD(v5[2].LockSemaphore);
      if ( !LockSemaphore_high || ReleaseSemaphore(*(HANDLE *)&v5[1].LockCount, LockSemaphore_high, 0) )
        goto LABEL_59;
      v27 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
      v28 = 440;
    }
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v28, v27, v26, 0);
    goto LABEL_59;
  }
  LODWORD(v5[2].DebugInfo) = DebugInfo - 1;
LABEL_59:
  LeaveCriticalSection(v5);
LABEL_60:
  LeaveCriticalSection(v38);
  if ( v20 )
    operator delete(v20);
  return EndpointsMarkedToClose;
}

```

## disassembly

```asm
0x1800036ac  push    rbp
0x1800036ae  push    rbx
0x1800036af  push    rsi
0x1800036b0  push    rdi
0x1800036b1  push    r12
0x1800036b3  push    r13
0x1800036b5  push    r14
0x1800036b7  push    r15
0x1800036b9  mov     rbp, rsp
0x1800036bc  sub     rsp, 68h
0x1800036c0  xor     r12d, r12d
0x1800036c3  lea     rax, [rcx+78h]
0x1800036c7  mov     rsi, rcx
0x1800036ca  mov     [rbp+arg_8], r12
0x1800036ce  mov     rcx, rax; lpCriticalSection
0x1800036d1  mov     [rbp+var_28], r12
0x1800036d5  mov     [rbp+var_20], r12
0x1800036d9  mov     r13d, r12d
0x1800036dc  mov     [rbp+arg_18], rax
0x1800036e0  call    cs:__imp_EnterCriticalSection
0x1800036e7  nop     dword ptr [rax+rax+00h]
0x1800036ec  lea     rcx, [rbp+lpCriticalSection]; this
0x1800036f0  mov     [rbp+lpCriticalSection], rsi
0x1800036f4  mov     [rbp+var_30], r12d
0x1800036f8  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x1800036fd  mov     r15d, r12d
0x180003700  mov     rbx, [rbp+lpCriticalSection]
0x180003704  mov     dword ptr [rsi+0A0h], 1
0x18000370e  cmp     [rsi+0B4h], r12d
0x180003715  jbe     loc_180003921
0x18000371b  mov     edi, r12d
0x18000371e  cmp     r15d, [rsi+0B4h]
0x180003725  jb      short loc_180003731
0x180003727  mov     edi, 585h
0x18000372c  mov     r14, r12
0x18000372f  jmp     short loc_18000373F
0x180003731  mov     rax, [rsi+0A8h]
0x180003738  mov     ecx, r15d
0x18000373b  mov     r14, [rax+rcx*8]
0x18000373f  mov     r9d, 18Fh; unsigned int
0x180003745  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x18000374c  mov     ecx, edi; unsigned int
0x18000374e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180003753  test    eax, eax
0x180003755  jnz     loc_1800039CA
0x18000375b  mov     edi, [r14+1Ch]
0x18000375f  mov     [rbp+arg_0], edi
0x180003762  test    edi, edi
0x180003764  jz      loc_180003830
0x18000376a  xor     r13d, r13d
0x18000376d  xor     edi, edi
0x18000376f  cmp     r12d, [r14+1Ch]
0x180003773  jb      short loc_18000377C
0x180003775  mov     edi, 585h
0x18000377a  jmp     short loc_180003788
0x18000377c  mov     rax, [r14+10h]
0x180003780  mov     rax, [rax+r13]
0x180003784  mov     [rbp+arg_8], rax
0x180003788  mov     r9d, 19Eh; unsigned int
0x18000378e  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x180003795  mov     ecx, edi; unsigned int
0x180003797  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000379c  test    eax, eax
0x18000379e  jnz     loc_1800039CA
0x1800037a4  xor     edi, edi
0x1800037a6  cmp     r12d, [r14+1Ch]
0x1800037aa  jb      short loc_1800037B3
0x1800037ac  mov     edi, 585h
0x1800037b1  jmp     short loc_1800037BB
0x1800037b3  mov     rax, [r14+10h]
0x1800037b7  and     [rax+r13], rdi
0x1800037bb  mov     r9d, 1A1h; unsigned int
0x1800037c1  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800037c8  mov     ecx, edi; unsigned int
0x1800037ca  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800037cf  test    eax, eax
0x1800037d1  jnz     loc_1800039CA
0x1800037d7  mov     rcx, [rbp+arg_8]; this
0x1800037db  call    ?Shutdown@CTftpSession@@QEAAKXZ; CTftpSession::Shutdown(void)
0x1800037e0  mov     r9d, 1A4h; unsigned int
0x1800037e6  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800037ed  mov     ecx, eax; unsigned int
0x1800037ef  mov     edi, eax
0x1800037f1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800037f6  test    eax, eax
0x1800037f8  jnz     loc_1800039CA
0x1800037fe  mov     rax, [rbp+arg_8]
0x180003802  test    rax, rax
0x180003805  jz      short loc_18000381D
0x180003807  lea     rcx, [rax+8]
0x18000380b  mov     rax, [rcx]
0x18000380e  mov     rax, [rax+8]
0x180003812  call    cs:__guard_dispatch_icall_fptr
0x180003818  and     [rbp+arg_8], 0
0x18000381d  mov     edi, [rbp+arg_0]
0x180003820  inc     r12d
0x180003823  add     r13, 8
0x180003827  cmp     r12d, edi
0x18000382a  jb      loc_18000376D
0x180003830  mov     rcx, [r14+10h]; void *
0x180003834  xor     r12d, r12d
0x180003837  test    rcx, rcx
0x18000383a  jz      short loc_180003849
0x18000383c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003841  mov     [r14+10h], r12
0x180003845  mov     [r14+18h], r12
0x180003849  mov     r13d, 1
0x18000384f  test    edi, edi
0x180003851  jz      short loc_18000386E
0x180003853  mov     r9d, r13d
0x180003856  mov     [rsp+68h+var_48], r13d
0x18000385b  lea     r8d, [r13+2]
0x18000385f  mov     edx, r13d; unsigned int
0x180003862  lea     rcx, qword_1800779F0; this
0x180003869  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x18000386e  mov     rdx, [r14]
0x180003871  lea     rcx, [rbp+var_28]
0x180003875  call    ?AddItem@?$CDynArray@PEAVCTptReadFile@@VCDeallocateNone@@@@QEAAKPEAVCTptReadFile@@@Z; CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(CTptReadFile *)
0x18000387a  mov     r9d, 1BCh; unsigned int
0x180003880  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x180003887  mov     ecx, eax; unsigned int
0x180003889  mov     edi, eax
0x18000388b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180003890  test    eax, eax
0x180003892  jnz     loc_1800039CA
0x180003898  mov     edi, r12d
0x18000389b  cmp     r15d, [rsi+0B4h]
0x1800038a2  jb      short loc_1800038AB
0x1800038a4  mov     edi, 585h
0x1800038a9  jmp     short loc_1800038B9
0x1800038ab  mov     rax, [rsi+0A8h]
0x1800038b2  mov     ecx, r15d
0x1800038b5  mov     [rax+rcx*8], r12
0x1800038b9  mov     r9d, 1BFh; unsigned int
0x1800038bf  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800038c6  mov     ecx, edi; unsigned int
0x1800038c8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800038cd  test    eax, eax
0x1800038cf  jnz     loc_1800039CA
0x1800038d5  mov     r9d, r13d
0x1800038d8  mov     [rsp+68h+var_48], r13d
0x1800038dd  lea     r8d, [rax+2]
0x1800038e1  mov     edx, r13d; unsigned int
0x1800038e4  lea     rcx, qword_1800779F0; this
0x1800038eb  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x1800038f0  mov     rcx, [r14+10h]; void *
0x1800038f4  test    rcx, rcx
0x1800038f7  jz      short loc_180003906
0x1800038f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800038fe  mov     [r14+10h], r12
0x180003902  mov     [r14+18h], r12
0x180003906  mov     rcx, r14; void *
0x180003909  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000390e  add     r15d, r13d
0x180003911  cmp     r15d, [rsi+0B4h]
0x180003918  jb      loc_18000371B
0x18000391e  mov     r13, r12
0x180003921  mov     rcx, [rsi+0A8h]; void *
0x180003928  test    rcx, rcx
0x18000392b  jz      short loc_180003941
0x18000392d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003932  and     qword ptr [rsi+0B0h], 0
0x18000393a  mov     [rsi+0A8h], r12
0x180003941  lea     rdx, [rbp+var_28]
0x180003945  mov     rcx, rsi
0x180003948  call    ?GetEndpointsMarkedToClose@CClientContext@@AEAAKPEAV?$CDynArray@PEAXVCDeallocateNone@@@@@Z; CClientContext::GetEndpointsMarkedToClose(CDynArray<void *,CDeallocateNone> *)
0x18000394d  mov     r9d, 1D3h; unsigned int
0x180003953  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x18000395a  mov     ecx, eax; unsigned int
0x18000395c  mov     edi, eax
0x18000395e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180003963  test    eax, eax
0x180003965  jnz     short loc_1800039CA
0x180003967  mov     esi, [rbp+var_30]
0x18000396a  test    esi, esi
0x18000396c  jz      short loc_18000397B
0x18000396e  add     esi, 0FFFFFFFFh
0x180003971  jnz     short loc_18000397B
0x180003973  mov     rcx, rbx; this
0x180003976  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x18000397b  mov     r14, [rbp+var_28]
0x18000397f  mov     r15d, r12d
0x180003982  mov     r12d, dword ptr [rbp+var_20+4]
0x180003986  test    r12d, r12d
0x180003989  jz      short loc_1800039D1
0x18000398b  cmp     r15d, r12d
0x18000398e  jnb     short loc_180003997
0x180003990  mov     eax, r15d
0x180003993  mov     r13, [r14+rax*8]
0x180003997  mov     rcx, r13
0x18000399a  call    cs:__imp_WdsEndpointClose
0x1800039a1  nop     dword ptr [rax+rax+00h]
0x1800039a6  mov     r9d, 1E1h; unsigned int
0x1800039ac  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800039b3  mov     ecx, eax; unsigned int
0x1800039b5  mov     edi, eax
0x1800039b7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800039bc  test    eax, eax
0x1800039be  jnz     short loc_1800039D1
0x1800039c0  inc     r15d
0x1800039c3  cmp     r15d, r12d
0x1800039c6  jb      short loc_180003990
0x1800039c8  jmp     short loc_1800039D1
0x1800039ca  mov     r14, [rbp+var_28]
0x1800039ce  mov     esi, [rbp+var_30]
0x1800039d1  xor     r15d, r15d
0x1800039d4  test    esi, esi
0x1800039d6  jz      loc_180003AF4
0x1800039dc  lea     eax, [rsi-1]
0x1800039df  test    eax, eax
0x1800039e1  jnz     loc_180003AF4
0x1800039e7  mov     rcx, rbx; lpCriticalSection
0x1800039ea  call    cs:__imp_EnterCriticalSection
0x1800039f1  nop     dword ptr [rax+rax+00h]
0x1800039f6  call    cs:__imp_GetCurrentThreadId
0x1800039fd  nop     dword ptr [rax+rax+00h]
0x180003a02  lea     rsi, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180003a09  cmp     [rbx+48h], eax
0x180003a0c  jz      short loc_180003A27
0x180003a0e  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x180003a15  mov     [rsp+68h+var_48], r15d; int
0x180003a1a  mov     edx, 195h; unsigned int
0x180003a1f  mov     rcx, rsi; char *
0x180003a22  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180003a27  mov     eax, [rbx+50h]
0x180003a2a  test    eax, eax
0x180003a2c  jz      short loc_180003A38
0x180003a2e  dec     eax
0x180003a30  mov     [rbx+50h], eax
0x180003a33  jmp     loc_180003AE5
0x180003a38  cmp     [rbx+4Ch], r15d
0x180003a3c  jz      short loc_180003A57
0x180003a3e  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x180003a45  mov     [rsp+68h+var_48], r15d; int
0x180003a4a  mov     edx, 1A1h; unsigned int
0x180003a4f  mov     rcx, rsi; char *
0x180003a52  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180003a57  xor     eax, eax
0x180003a59  mov     [rbx+48h], rax
0x180003a5d  mov     [rbx+50h], eax
0x180003a60  cmp     [rbx+68h], r15d
0x180003a64  jz      short loc_180003A7F
0x180003a66  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x180003a6d  mov     [rsp+68h+var_48], r15d; int
0x180003a72  mov     edx, 1A4h; unsigned int
0x180003a77  mov     rcx, rsi; char *
0x180003a7a  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180003a7f  cmp     [rbx+70h], r15d
0x180003a83  jz      short loc_180003AAE
0x180003a85  mov     rcx, [rbx+38h]; hSemaphore
0x180003a89  xor     r8d, r8d; lpPreviousCount
0x180003a8c  lea     edx, [r8+1]; lReleaseCount
0x180003a90  call    cs:__imp_ReleaseSemaphore
0x180003a97  nop     dword ptr [rax+rax+00h]
0x180003a9c  test    eax, eax
0x180003a9e  jnz     short loc_180003AE5
0x180003aa0  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180003aa7  mov     edx, 1AFh
0x180003aac  jmp     short loc_180003AD8
0x180003aae  mov     edx, [rbx+6Ch]; lReleaseCount
0x180003ab1  test    edx, edx
0x180003ab3  jz      short loc_180003AE5
0x180003ab5  mov     rcx, [rbx+30h]; hSemaphore
0x180003ab9  xor     r8d, r8d; lpPreviousCount
0x180003abc  call    cs:__imp_ReleaseSemaphore
0x180003ac3  nop     dword ptr [rax+rax+00h]
0x180003ac8  test    eax, eax
0x180003aca  jnz     short loc_180003AE5
0x180003acc  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x180003ad3  mov     edx, 1B8h; unsigned int
0x180003ad8  mov     rcx, rsi; char *
0x180003adb  mov     [rsp+68h+var_48], r15d; int
0x180003ae0  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180003ae5  mov     rcx, rbx; lpCriticalSection
0x180003ae8  call    cs:__imp_LeaveCriticalSection
0x180003aef  nop     dword ptr [rax+rax+00h]
0x180003af4  mov     rcx, [rbp+arg_18]; lpCriticalSection
0x180003af8  call    cs:__imp_LeaveCriticalSection
0x180003aff  nop     dword ptr [rax+rax+00h]
0x180003b04  test    r14, r14
0x180003b07  jz      short loc_180003B11
0x180003b09  mov     rcx, r14; void *
0x180003b0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b11  mov     eax, edi
0x180003b13  add     rsp, 68h
0x180003b17  pop     r15
0x180003b19  pop     r14
0x180003b1b  pop     r13
0x180003b1d  pop     r12
0x180003b1f  pop     rdi
0x180003b20  pop     rsi
0x180003b21  pop     rbx
0x180003b22  pop     rbp
0x180003b23  retn
```
