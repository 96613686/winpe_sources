# CClientContext::CleanupEndpoints(void)

- ea: `0x180004b18`
- end: `0x180004f87`
- name: `?CleanupEndpoints@CClientContext@@QEAAKXZ`
- size: `1135`
- prototype: `unsigned int __fastcall(CClientContext *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002ad0`

## callees

- `0x180003170`
- `0x180004b18`
- `0x1800054f4`
- `0x1800057f8`
- `0x180005850`
- `0x18000a960`
- `0x18003c084`
- `0x18003c514`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180004d73`
- `KERNEL32!ReleaseSemaphore` at `0x180004d9f`
- `KERNEL32!ReleaseSemaphore` at `0x180004f02`
- `KERNEL32!ReleaseSemaphore` at `0x180004f2e`
- `KERNEL32!ReleaseSemaphore` at `0x180004d73`
- `KERNEL32!ReleaseSemaphore` at `0x180004d9f`
- `KERNEL32!ReleaseSemaphore` at `0x180004f02`
- `KERNEL32!ReleaseSemaphore` at `0x180004f2e`
- `KERNEL32!GetCurrentThreadId` at `0x180004ccb`
- `KERNEL32!GetCurrentThreadId` at `0x180004e6f`
- `KERNEL32!GetCurrentThreadId` at `0x180004ccb`
- `KERNEL32!GetCurrentThreadId` at `0x180004e6f`
- `KERNEL32!EnterCriticalSection` at `0x180004cbf`
- `KERNEL32!EnterCriticalSection` at `0x180004e63`
- `KERNEL32!EnterCriticalSection` at `0x180004cbf`
- `KERNEL32!EnterCriticalSection` at `0x180004e63`
- `KERNEL32!LeaveCriticalSection` at `0x180004dcb`
- `KERNEL32!LeaveCriticalSection` at `0x180004f5a`
- `KERNEL32!LeaveCriticalSection` at `0x180004dcb`
- `KERNEL32!LeaveCriticalSection` at `0x180004f5a`
- `WDSSRV!WdsEndpointClose` at `0x180004de4`
- `WDSSRV!WdsEndpointClose` at `0x180004e2c`
- `WDSSRV!WdsEndpointClose` at `0x180004de4`
- `WDSSRV!WdsEndpointClose` at `0x180004e2c`

## string_xrefs

- `0x180004ca0`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180004cdc`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180004e80`: `m_ActiveWriter.m_uThreadId == GetCurrentThreadId()`
- `0x180004d21`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x180004eb0`: `m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0`
- `0x180004d49`: `m_uActiveReaders == 0`
- `0x180004ed8`: `m_uActiveReaders == 0`
- `0x180004d83`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180004f12`: `ReleaseSemaphore(m_hReaderDone, 1, 0)`
- `0x180004daf`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`
- `0x180004f3e`: `ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)`

## pseudocode

```c
__int64 __fastcall CClientContext::CleanupEndpoints(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v2; // r13d
  unsigned int OwningThread_high; // esi
  unsigned int v4; // r14d
  __int64 v5; // rdi
  __int64 v6; // rbx
  unsigned int v7; // r12d
  __int64 v8; // rdx
  const char *v9; // rdx
  const char *v10; // rdx
  void *v11; // rcx
  int v12; // esi
  LPCRITICAL_SECTION v13; // rbx
  int v14; // r9d
  int DebugInfo; // eax
  int v16; // r9d
  const char *v17; // r8
  unsigned int v18; // edx
  LONG LockSemaphore_high; // edx
  void *v20; // rcx
  unsigned int i; // edi
  __int64 v22; // rcx
  int v23; // r9d
  int v24; // eax
  int v25; // r9d
  const char *v26; // r8
  unsigned int v27; // edx
  LONG v28; // edx
  __int64 v30; // [rsp+20h] [rbp-40h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-30h] BYREF
  int v32; // [rsp+38h] [rbp-28h]
  void *v33; // [rsp+40h] [rbp-20h] BYREF
  __int64 v34; // [rsp+48h] [rbp-18h]
  unsigned int v35; // [rsp+90h] [rbp+30h]

  lpCriticalSection = this;
  v2 = 0;
  v32 = 0;
  CAutoWriterLock::Lock((CAutoWriterLock *)&lpCriticalSection);
  OwningThread_high = HIDWORD(this[4].OwningThread);
  v4 = 0;
  v33 = 0;
  v5 = 0;
  v34 = 0;
  if ( OwningThread_high > 2 )
  {
    v6 = 0;
    v7 = OwningThread_high >> 1;
    while ( 1 )
    {
      v8 = 0;
      v5 = 0;
      v35 = 0;
      if ( (unsigned int)v6 < HIDWORD(this[4].OwningThread) )
      {
        v5 = *(_QWORD *)(*(_QWORD *)&this[4].LockCount + 8 * v6);
      }
      else
      {
        v8 = 1413;
        v35 = 1413;
      }
      if ( ElValidateWin32(v8, (const char *)v8, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x54Au) )
        break;
      if ( *(_DWORD *)(v5 + 28) || !*(_DWORD *)(v5 + 12) )
      {
        ++*(_DWORD *)(v5 + 12);
        v6 = (unsigned int)(v6 + 1);
      }
      else
      {
        v35 = CDynArray<CEndpointSessionMapEntry *,CDeallocateNone>::RemoveItem(&this[4].LockCount);
        if ( ElValidateWin32(v35, v9, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x557u) )
          break;
        LODWORD(v30) = 1;
        CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 2, 1, v30);
        --OwningThread_high;
        v35 = CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(&v33);
        if ( ElValidateWin32(v35, v10, "base\\eco\\wds\\transport\\server\\tftp\\clientcontext.cpp", 0x557u) )
        {
          v2 = v35;
          goto LABEL_18;
        }
        *(_QWORD *)v5 = 0;
        v11 = *(void **)(v5 + 16);
        if ( v11 )
        {
          operator delete(v11);
          *(_QWORD *)(v5 + 16) = 0;
          *(_QWORD *)(v5 + 24) = 0;
        }
        operator delete((void *)v5);
        v4 = HIDWORD(v34);
      }
      if ( v4 == v7 || (unsigned int)v6 >= OwningThread_high )
      {
        v2 = v35;
        CClientContext::GetEndpointsMarkedToClose(this, &v33);
        v5 = 0;
LABEL_18:
        v4 = HIDWORD(v34);
        goto LABEL_19;
      }
    }
    v2 = v35;
    v5 = 0;
  }
LABEL_19:
  v12 = v32;
  v13 = lpCriticalSection;
  if ( v32 )
  {
    v12 = v32 - 1;
    if ( v32 == 1 )
    {
      EnterCriticalSection(lpCriticalSection);
      if ( LODWORD(v13[1].SpinCount) != GetCurrentThreadId() )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x195u,
          "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
          v14,
          0);
      DebugInfo = (int)v13[2].DebugInfo;
      if ( DebugInfo )
      {
        LODWORD(v13[2].DebugInfo) = DebugInfo - 1;
LABEL_38:
        LeaveCriticalSection(v13);
        goto LABEL_39;
      }
      if ( HIDWORD(v13[1].SpinCount) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x1A1u,
          "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
          v14,
          0);
      v13[1].SpinCount = 0;
      LODWORD(v13[2].DebugInfo) = 0;
      if ( LODWORD(v13[2].LockSemaphore) )
        WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", v14, 0);
      if ( LODWORD(v13[2].SpinCount) )
      {
        if ( ReleaseSemaphore(v13[1].OwningThread, 1, 0) )
          goto LABEL_38;
        v17 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
        v18 = 431;
      }
      else
      {
        LockSemaphore_high = HIDWORD(v13[2].LockSemaphore);
        if ( !LockSemaphore_high || ReleaseSemaphore(*(HANDLE *)&v13[1].LockCount, LockSemaphore_high, 0) )
          goto LABEL_38;
        v17 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
        v18 = 440;
      }
      WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v18, v17, v16, 0);
      goto LABEL_38;
    }
  }
LABEL_39:
  if ( v5 )
  {
    if ( *(_QWORD *)v5 )
    {
      WdsEndpointClose(*(_QWORD *)v5);
      *(_QWORD *)v5 = 0;
    }
    v20 = *(void **)(v5 + 16);
    if ( v20 )
    {
      operator delete(v20);
      *(_QWORD *)(v5 + 24) = 0;
      *(_QWORD *)(v5 + 16) = 0;
    }
    operator delete((void *)v5);
  }
  for ( i = 0; i < v4; ++i )
  {
    v22 = 0;
    if ( i < v4 )
      v22 = *((_QWORD *)v33 + i);
    WdsEndpointClose(v22);
  }
  if ( v33 )
    operator delete(v33);
  if ( v12 == 1 )
  {
    EnterCriticalSection(v13);
    if ( LODWORD(v13[1].SpinCount) != GetCurrentThreadId() )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x195u,
        "m_ActiveWriter.m_uThreadId == GetCurrentThreadId()",
        v23,
        0);
    v24 = (int)v13[2].DebugInfo;
    if ( v24 )
    {
      LODWORD(v13[2].DebugInfo) = v24 - 1;
LABEL_67:
      LeaveCriticalSection(v13);
      return v2;
    }
    if ( HIDWORD(v13[1].SpinCount) )
      WdsAssert(
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
        0x1A1u,
        "m_ActiveWriter.m_uNestedReaders == 0 && m_ActiveWriter.m_uNestedWriters == 0",
        v23,
        0);
    v13[1].SpinCount = 0;
    LODWORD(v13[2].DebugInfo) = 0;
    if ( LODWORD(v13[2].LockSemaphore) )
      WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0x1A4u, "m_uActiveReaders == 0", v23, 0);
    if ( LODWORD(v13[2].SpinCount) )
    {
      if ( ReleaseSemaphore(v13[1].OwningThread, 1, 0) )
        goto LABEL_67;
      v26 = "ReleaseSemaphore(m_hReaderDone, 1, 0)";
      v27 = 431;
    }
    else
    {
      v28 = HIDWORD(v13[2].LockSemaphore);
      if ( !v28 || ReleaseSemaphore(*(HANDLE *)&v13[1].LockCount, v28, 0) )
        goto LABEL_67;
      v26 = "ReleaseSemaphore(m_hWriterDone, m_uWaitingReaders, 0)";
      v27 = 440;
    }
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", v27, v26, v25, 0);
    goto LABEL_67;
  }
  return v2;
}

```

## disassembly

```asm
0x180004b18  mov     [rsp-28h+arg_8], rbx
0x180004b1d  mov     [rsp-28h+arg_10], rsi
0x180004b22  mov     [rsp-28h+arg_18], rdi
0x180004b27  push    rbp
0x180004b28  push    r12
0x180004b2a  push    r13
0x180004b2c  push    r14
0x180004b2e  push    r15
0x180004b30  mov     rbp, rsp
0x180004b33  sub     rsp, 60h
0x180004b37  mov     r15, rcx
0x180004b3a  mov     [rbp+lpCriticalSection], rcx
0x180004b3e  xor     r12d, r12d
0x180004b41  lea     rcx, [rbp+lpCriticalSection]; this
0x180004b45  mov     r13d, r12d
0x180004b48  mov     [rbp+var_28], r12d
0x180004b4c  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180004b51  mov     esi, [r15+0B4h]
0x180004b58  mov     r14d, r12d
0x180004b5b  mov     [rbp+var_20], r12
0x180004b5f  mov     edi, r12d
0x180004b62  mov     [rbp+var_18], r12
0x180004b66  cmp     esi, 2
0x180004b69  jbe     loc_180004C9D
0x180004b6f  mov     r12d, esi
0x180004b72  xor     ebx, ebx
0x180004b74  shr     r12d, 1
0x180004b77  test    esi, esi
0x180004b79  jz      loc_180004C87
0x180004b7f  lea     r13, [r15+0A8h]
0x180004b86  xor     edx, edx; char *
0x180004b88  xor     edi, edi
0x180004b8a  mov     [rbp+arg_0], edx
0x180004b8d  cmp     ebx, [r13+0Ch]
0x180004b91  jb      short loc_180004B9D
0x180004b93  mov     edx, 585h
0x180004b98  mov     [rbp+arg_0], edx
0x180004b9b  jmp     short loc_180004BA5
0x180004b9d  mov     rax, [r13+0]
0x180004ba1  mov     rdi, [rax+rbx*8]
0x180004ba5  mov     r9d, 54Ah; unsigned int
0x180004bab  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x180004bb2  mov     ecx, edx; unsigned int
0x180004bb4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004bb9  test    eax, eax
0x180004bbb  jnz     loc_180004D0F
0x180004bc1  cmp     [rdi+1Ch], eax
0x180004bc4  jnz     loc_180004C71
0x180004bca  cmp     [rdi+0Ch], eax
0x180004bcd  jbe     loc_180004C71
0x180004bd3  mov     edx, ebx
0x180004bd5  mov     rcx, r13
0x180004bd8  call    ?RemoveItem@?$CDynArray@PEAVCEndpointSessionMapEntry@@VCDeallocateNone@@@@QEAAKK@Z; CDynArray<CEndpointSessionMapEntry *,CDeallocateNone>::RemoveItem(ulong)
0x180004bdd  mov     r9d, 557h; unsigned int
0x180004be3  mov     [rbp+arg_0], eax
0x180004be6  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x180004bed  mov     ecx, eax; unsigned int
0x180004bef  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004bf4  test    eax, eax
0x180004bf6  jnz     loc_180004D0F
0x180004bfc  mov     eax, 1
0x180004c01  lea     rcx, qword_1800779F0; this
0x180004c08  mov     r9d, eax
0x180004c0b  mov     [rsp+60h+var_40], eax
0x180004c0f  mov     edx, eax; unsigned int
0x180004c11  lea     r8d, [rax+1]
0x180004c15  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180004c1a  mov     rdx, [rdi]
0x180004c1d  lea     rcx, [rbp+var_20]
0x180004c21  dec     esi
0x180004c23  call    ?AddItem@?$CDynArray@PEAVCTptReadFile@@VCDeallocateNone@@@@QEAAKPEAVCTptReadFile@@@Z; CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(CTptReadFile *)
0x180004c28  mov     r9d, 557h; unsigned int
0x180004c2e  mov     [rbp+arg_0], eax
0x180004c31  lea     r8, aBaseEcoWdsTran_0; "base\\eco\\wds\\transport\\server\\tftp"...
0x180004c38  mov     ecx, eax; unsigned int
0x180004c3a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004c3f  xor     r14d, r14d
0x180004c42  test    eax, eax
0x180004c44  jnz     loc_180004D06
0x180004c4a  mov     [rdi], r14
0x180004c4d  mov     rcx, [rdi+10h]; void *
0x180004c51  test    rcx, rcx
0x180004c54  jz      short loc_180004C63
0x180004c56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c5b  mov     [rdi+10h], r14
0x180004c5f  mov     [rdi+18h], r14
0x180004c63  mov     rcx, rdi; void *
0x180004c66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c6b  mov     r14d, dword ptr [rbp+var_18+4]
0x180004c6f  jmp     short loc_180004C76
0x180004c71  inc     dword ptr [rdi+0Ch]
0x180004c74  inc     ebx
0x180004c76  cmp     r14d, r12d
0x180004c79  jz      short loc_180004C83
0x180004c7b  cmp     ebx, esi
0x180004c7d  jb      loc_180004B86
0x180004c83  mov     r13d, [rbp+arg_0]
0x180004c87  lea     rdx, [rbp+var_20]
0x180004c8b  mov     rcx, r15
0x180004c8e  call    ?GetEndpointsMarkedToClose@CClientContext@@AEAAKPEAV?$CDynArray@PEAXVCDeallocateNone@@@@@Z; CClientContext::GetEndpointsMarkedToClose(CDynArray<void *,CDeallocateNone> *)
0x180004c93  xor     r12d, r12d
0x180004c96  mov     edi, r12d
0x180004c99  mov     r14d, dword ptr [rbp+var_18+4]
0x180004c9d  mov     esi, [rbp+var_28]
0x180004ca0  lea     r15, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180004ca7  mov     rbx, [rbp+lpCriticalSection]
0x180004cab  test    esi, esi
0x180004cad  jz      loc_180004DD7
0x180004cb3  add     esi, 0FFFFFFFFh
0x180004cb6  jnz     loc_180004DD7
0x180004cbc  mov     rcx, rbx; lpCriticalSection
0x180004cbf  call    cs:__imp_EnterCriticalSection
0x180004cc6  nop     dword ptr [rax+rax+00h]
0x180004ccb  call    cs:__imp_GetCurrentThreadId
0x180004cd2  nop     dword ptr [rax+rax+00h]
0x180004cd7  cmp     [rbx+48h], eax
0x180004cda  jz      short loc_180004CF5
0x180004cdc  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x180004ce3  mov     [rsp+60h+var_40], r12d; int
0x180004ce8  mov     edx, 195h; unsigned int
0x180004ced  mov     rcx, r15; char *
0x180004cf0  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004cf5  mov     eax, [rbx+50h]
0x180004cf8  test    eax, eax
0x180004cfa  jz      short loc_180004D1B
0x180004cfc  dec     eax
0x180004cfe  mov     [rbx+50h], eax
0x180004d01  jmp     loc_180004DC8
0x180004d06  mov     r13d, [rbp+arg_0]
0x180004d0a  xor     r12d, r12d
0x180004d0d  jmp     short loc_180004C99
0x180004d0f  mov     r13d, [rbp+arg_0]
0x180004d13  xor     r12d, r12d
0x180004d16  mov     edi, r12d
0x180004d19  jmp     short loc_180004C9D
0x180004d1b  cmp     [rbx+4Ch], r12d
0x180004d1f  jz      short loc_180004D3A
0x180004d21  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x180004d28  mov     [rsp+60h+var_40], r12d; int
0x180004d2d  mov     edx, 1A1h; unsigned int
0x180004d32  mov     rcx, r15; char *
0x180004d35  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004d3a  xor     eax, eax
0x180004d3c  mov     [rbx+48h], rax
0x180004d40  mov     [rbx+50h], eax
0x180004d43  cmp     [rbx+68h], r12d
0x180004d47  jz      short loc_180004D62
0x180004d49  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x180004d50  mov     [rsp+60h+var_40], r12d; int
0x180004d55  mov     edx, 1A4h; unsigned int
0x180004d5a  mov     rcx, r15; char *
0x180004d5d  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004d62  cmp     [rbx+70h], r12d
0x180004d66  jz      short loc_180004D91
0x180004d68  mov     rcx, [rbx+38h]; hSemaphore
0x180004d6c  xor     r8d, r8d; lpPreviousCount
0x180004d6f  lea     edx, [r8+1]; lReleaseCount
0x180004d73  call    cs:__imp_ReleaseSemaphore
0x180004d7a  nop     dword ptr [rax+rax+00h]
0x180004d7f  test    eax, eax
0x180004d81  jnz     short loc_180004DC8
0x180004d83  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180004d8a  mov     edx, 1AFh
0x180004d8f  jmp     short loc_180004DBB
0x180004d91  mov     edx, [rbx+6Ch]; lReleaseCount
0x180004d94  test    edx, edx
0x180004d96  jz      short loc_180004DC8
0x180004d98  mov     rcx, [rbx+30h]; hSemaphore
0x180004d9c  xor     r8d, r8d; lpPreviousCount
0x180004d9f  call    cs:__imp_ReleaseSemaphore
0x180004da6  nop     dword ptr [rax+rax+00h]
0x180004dab  test    eax, eax
0x180004dad  jnz     short loc_180004DC8
0x180004daf  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x180004db6  mov     edx, 1B8h; unsigned int
0x180004dbb  mov     rcx, r15; char *
0x180004dbe  mov     [rsp+60h+var_40], r12d; int
0x180004dc3  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004dc8  mov     rcx, rbx; lpCriticalSection
0x180004dcb  call    cs:__imp_LeaveCriticalSection
0x180004dd2  nop     dword ptr [rax+rax+00h]
0x180004dd7  test    rdi, rdi
0x180004dda  jz      short loc_180004E12
0x180004ddc  mov     rcx, [rdi]
0x180004ddf  test    rcx, rcx
0x180004de2  jz      short loc_180004DF3
0x180004de4  call    cs:__imp_WdsEndpointClose
0x180004deb  nop     dword ptr [rax+rax+00h]
0x180004df0  mov     [rdi], r12
0x180004df3  mov     rcx, [rdi+10h]; void *
0x180004df7  test    rcx, rcx
0x180004dfa  jz      short loc_180004E0A
0x180004dfc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004e01  and     qword ptr [rdi+18h], 0
0x180004e06  mov     [rdi+10h], r12
0x180004e0a  mov     rcx, rdi; void *
0x180004e0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004e12  mov     edi, r12d
0x180004e15  test    r14d, r14d
0x180004e18  jz      short loc_180004E3F
0x180004e1a  mov     rcx, r12
0x180004e1d  cmp     edi, r14d
0x180004e20  jnb     short loc_180004E2C
0x180004e22  mov     rax, [rbp+var_20]
0x180004e26  mov     ecx, edi
0x180004e28  mov     rcx, [rax+rcx*8]
0x180004e2c  call    cs:__imp_WdsEndpointClose
0x180004e33  nop     dword ptr [rax+rax+00h]
0x180004e38  inc     edi
0x180004e3a  cmp     edi, r14d
0x180004e3d  jb      short loc_180004E1A
0x180004e3f  mov     rcx, [rbp+var_20]; void *
0x180004e43  test    rcx, rcx
0x180004e46  jz      short loc_180004E4D
0x180004e48  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004e4d  test    esi, esi
0x180004e4f  jz      loc_180004F66
0x180004e55  lea     eax, [rsi-1]
0x180004e58  test    eax, eax
0x180004e5a  jnz     loc_180004F66
0x180004e60  mov     rcx, rbx; lpCriticalSection
0x180004e63  call    cs:__imp_EnterCriticalSection
0x180004e6a  nop     dword ptr [rax+rax+00h]
0x180004e6f  call    cs:__imp_GetCurrentThreadId
0x180004e76  nop     dword ptr [rax+rax+00h]
0x180004e7b  cmp     [rbx+48h], eax
0x180004e7e  jz      short loc_180004E99
0x180004e80  lea     r8, aMActivewriterM_0; "m_ActiveWriter.m_uThreadId == GetCurren"...
0x180004e87  mov     [rsp+60h+var_40], r12d; int
0x180004e8c  mov     edx, 195h; unsigned int
0x180004e91  mov     rcx, r15; char *
0x180004e94  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004e99  mov     eax, [rbx+50h]
0x180004e9c  test    eax, eax
0x180004e9e  jz      short loc_180004EAA
0x180004ea0  dec     eax
0x180004ea2  mov     [rbx+50h], eax
0x180004ea5  jmp     loc_180004F57
0x180004eaa  cmp     [rbx+4Ch], r12d
0x180004eae  jz      short loc_180004EC9
0x180004eb0  lea     r8, aMActivewriterM; "m_ActiveWriter.m_uNestedReaders == 0 &&"...
0x180004eb7  mov     [rsp+60h+var_40], r12d; int
0x180004ebc  mov     edx, 1A1h; unsigned int
0x180004ec1  mov     rcx, r15; char *
0x180004ec4  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004ec9  xor     eax, eax
0x180004ecb  mov     [rbx+48h], rax
0x180004ecf  mov     [rbx+50h], eax
0x180004ed2  cmp     [rbx+68h], r12d
0x180004ed6  jz      short loc_180004EF1
0x180004ed8  lea     r8, aMUactivereader_0; "m_uActiveReaders == 0"
0x180004edf  mov     [rsp+60h+var_40], r12d; int
0x180004ee4  mov     edx, 1A4h; unsigned int
0x180004ee9  mov     rcx, r15; char *
0x180004eec  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004ef1  cmp     [rbx+70h], r12d
0x180004ef5  jz      short loc_180004F20
0x180004ef7  mov     rcx, [rbx+38h]; hSemaphore
0x180004efb  xor     r8d, r8d; lpPreviousCount
0x180004efe  lea     edx, [r8+1]; lReleaseCount
0x180004f02  call    cs:__imp_ReleaseSemaphore
0x180004f09  nop     dword ptr [rax+rax+00h]
0x180004f0e  test    eax, eax
0x180004f10  jnz     short loc_180004F57
0x180004f12  lea     r8, aReleasesemapho_1; "ReleaseSemaphore(m_hReaderDone, 1, 0)"
0x180004f19  mov     edx, 1AFh
0x180004f1e  jmp     short loc_180004F4A
0x180004f20  mov     edx, [rbx+6Ch]; lReleaseCount
0x180004f23  test    edx, edx
0x180004f25  jz      short loc_180004F57
0x180004f27  mov     rcx, [rbx+30h]; hSemaphore
0x180004f2b  xor     r8d, r8d; lpPreviousCount
0x180004f2e  call    cs:__imp_ReleaseSemaphore
0x180004f35  nop     dword ptr [rax+rax+00h]
0x180004f3a  test    eax, eax
0x180004f3c  jnz     short loc_180004F57
0x180004f3e  lea     r8, aReleasesemapho_0; "ReleaseSemaphore(m_hWriterDone, m_uWait"...
0x180004f45  mov     edx, 1B8h; unsigned int
0x180004f4a  mov     rcx, r15; char *
0x180004f4d  mov     [rsp+60h+var_40], r12d; int
0x180004f52  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180004f57  mov     rcx, rbx; lpCriticalSection
0x180004f5a  call    cs:__imp_LeaveCriticalSection
0x180004f61  nop     dword ptr [rax+rax+00h]
0x180004f66  lea     r11, [rsp+60h+var_s0]
0x180004f6b  mov     eax, r13d
0x180004f6e  mov     rbx, [r11+38h]
0x180004f72  mov     rsi, [r11+40h]
0x180004f76  mov     rdi, [r11+48h]
0x180004f7a  mov     rsp, r11
0x180004f7d  pop     r15
0x180004f7f  pop     r14
0x180004f81  pop     r13
0x180004f83  pop     r12
0x180004f85  pop     rbp
0x180004f86  retn
```
