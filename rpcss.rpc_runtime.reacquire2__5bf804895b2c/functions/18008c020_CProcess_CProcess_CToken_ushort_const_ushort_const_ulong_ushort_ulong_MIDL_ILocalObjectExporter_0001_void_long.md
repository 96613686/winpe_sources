# CProcess::CProcess(CToken * &,ushort const *,ushort const *,ulong,ushort,ulong,__MIDL_ILocalObjectExporter_0001 *,void *,long &)

- ea: `0x18008c020`
- end: `0x18008c81e`
- name: `??0CProcess@@QEAA@AEAPEAVCToken@@PEBG1KGKPEAU__MIDL_ILocalObjectExporter_0001@@PEAXAEAJ@Z`
- size: `2046`
- prototype: `CProcess *__usercall@<rax>(CProcess *__hidden this@<rcx>, struct CToken **@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned int, unsigned __int16, bool, struct __MIDL_ILocalObjectExporter_0001 *, void *, int *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008c830`

## callees

- `0x180011db0`
- `0x180013b18`
- `0x180013cd4`
- `0x180018d24`
- `0x180018d8c`
- `0x180019b00`
- `0x18001eeac`
- `0x18002f3e0`
- `0x18002f5a0`
- `0x18002f670`
- `0x180034260`
- `0x180054dfc`
- `0x18006a430`
- `0x18006c3a4`
- `0x180072840`
- `0x18008172c`
- `0x1800856a8`
- `0x180086954`
- `0x18008c020`
- `0x180093410`
- `0x180095c0c`
- `0x180098298`
- `0x18009e160`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18008c234`
- `RPCRT4!UuidCreate` at `0x18008c234`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18008c6dc`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18008c6dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008c27c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008c2e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008c346`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008c596`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008c27c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008c2e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008c346`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008c596`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18008c11a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18008c14a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18008c181`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18008c194`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18008c11a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18008c14a`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18008c181`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18008c194`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008c224`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008c224`
- `api-ms-win-core-wow64-l1-1-2!IsWow64GuestMachineSupported` at `0x18008c44b`
- `api-ms-win-core-wow64-l1-1-2!IsWow64GuestMachineSupported` at `0x18008c44b`

## string_xrefs

- `0x18008c461`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18008c65a`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18008c721`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18008c715`: `Failed to open handle to PID %x (%!WINERROR!)`

## pseudocode

```c
CProcess *__fastcall CProcess::CProcess(
        CProcess *this,
        struct CToken **a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 a6,
        unsigned int a7,
        struct __MIDL_ILocalObjectExporter_0001 *a8,
        RPC_BINDING_HANDLE Binding,
        int *a10)
{
  unsigned __int64 v14; // rcx
  int *v15; // rdi
  unsigned int v16; // r13d
  _BYTE *v17; // rax
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  SIZE_T v20; // rax
  unsigned __int64 v21; // kr00_8
  unsigned __int16 *v22; // rax
  __int64 v23; // rax
  unsigned __int64 v24; // rsi
  SIZE_T v25; // rax
  unsigned __int64 v26; // kr10_8
  unsigned __int16 *v27; // rax
  CToken *v28; // rcx
  int HasSysAppId; // eax
  __int64 v30; // rcx
  int LifecycleManagerInfo; // eax
  int v32; // eax
  int v33; // eax
  unsigned __int16 v34; // si
  int v35; // eax
  struct __MIDL_ILocalObjectExporter_0001 *v36; // rsi
  unsigned int ArchitecturePointerSizeInBytes; // r9d
  __int64 v38; // rdx
  unsigned int v39; // edx
  unsigned int v40; // edx
  int v41; // r8d
  _OWORD *v42; // rax
  __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // rcx
  int v46; // eax
  CToken *v47; // rcx
  RPC_STATUS v48; // eax
  int v49; // r9d
  RPC_STATUS v50; // r8d
  unsigned __int16 v51; // ax
  int v52; // eax
  CookieToPHPROCESSMap *v53; // rcx
  int v54; // ecx
  int v55; // r9d
  int v57; // [rsp+20h] [rbp-38h]
  __int64 v58; // [rsp+28h] [rbp-30h]
  __int64 v59; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CProcess::`vftable';
  *((_QWORD *)this + 15) = 0;
  CBList::CBList((CProcess *)((char *)this + 168), 4u);
  CBList::CBList((CProcess *)((char *)this + 184), 0x10u);
  CBList::CBList((CProcess *)((char *)this + 200), 8u);
  *((_QWORD *)this + 27) = (char *)this + 216;
  *((_QWORD *)this + 28) = (char *)this + 216;
  *((_QWORD *)this + 29) = (char *)this + 216;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = (char *)this + 248;
  *((_QWORD *)this + 32) = (char *)this + 248;
  *((_QWORD *)this + 33) = (char *)this + 248;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = (char *)this + 288;
  *((_QWORD *)this + 37) = (char *)this + 288;
  *((_QWORD *)this + 38) = (char *)this + 288;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_WORD *)this + 214) = 0;
  *((_BYTE *)this + 430) = 0;
  *((_QWORD *)this + 54) = 0;
  InitializeSRWLock((PSRWLOCK)this + 55);
  *((_QWORD *)this + 56) = (char *)this + 448;
  *((_QWORD *)this + 57) = (char *)this + 448;
  *((_QWORD *)this + 58) = (char *)this + 448;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  InitializeSRWLock((PSRWLOCK)this + 61);
  *((_QWORD *)this + 62) = (char *)this + 496;
  *((_QWORD *)this + 63) = (char *)this + 496;
  *((_QWORD *)this + 64) = (char *)this + 496;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_BYTE *)this + 536) = 0;
  InitializeSRWLock((PSRWLOCK)this + 68);
  InitializeSRWLock((PSRWLOCK)this + 69);
  *((_QWORD *)this + 70) = 0;
  *((_BYTE *)this + 576) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_DWORD *)this + 4) = 1;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 23) = 4;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 36) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_DWORD *)this + 94) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_DWORD *)this + 106) = 0;
  GetSystemTimeAsFileTime((LPFILETIME)this + 16);
  UuidCreate((UUID *)((char *)this + 104));
  v15 = a10;
  v16 = a7;
  *((_DWORD *)this + 40) = 0;
  *v15 = 0;
  *((_QWORD *)this + 10) = 0;
  *(GUID *)((char *)this + 392) = GUID_NULL;
  if ( !a3 )
    goto LABEL_38;
  v17 = HeapAlloc(g_hHeap, 0, 0x18u);
  if ( v17 )
  {
    v14 = (unsigned __int64)qword_180143A30;
    v17[8] = 1;
    *(_QWORD *)v17 = qword_180143A30;
    *((_QWORD *)v17 + 2) = 0;
  }
  else
  {
    v17 = 0;
  }
  *((_QWORD *)this + 5) = v17;
  if ( !v17 )
    *v15 = 14;
  if ( !*v15 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a3[v18] );
    v19 = v18 + 1;
    v21 = v18 + 1;
    v20 = 2 * (v18 + 1);
    if ( !is_mul_ok(v21, 2u) )
      v20 = -1;
    v22 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v20);
    *((_QWORD *)this + 4) = v22;
    if ( !v22 )
      goto LABEL_40;
    StringCchCopyW(v22, v19, a3);
    if ( *v15 )
      goto LABEL_41;
    v23 = -1;
    do
      ++v23;
    while ( a4[v23] );
    v24 = v23 + 1;
    v26 = v23 + 1;
    v25 = 2 * (v23 + 1);
    if ( !is_mul_ok(v26, 2u) )
      v25 = -1;
    v27 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v25);
    *((_QWORD *)this + 48) = v27;
    if ( v27 )
    {
      StringCchCopyW(v27, v24, a4);
      if ( !*v15 )
      {
        v28 = *a2;
        *((_QWORD *)this + 3) = *a2;
        *a2 = 0;
        LOBYTE(a7) = 0;
        HasSysAppId = CToken::HasSysAppId(v28, (bool *)&a7);
        if ( HasSysAppId < 0 )
        {
          *v15 = (unsigned __int16)HasSysAppId;
        }
        else if ( (_BYTE)a7 )
        {
          *((_DWORD *)this + 23) |= 0x800u;
        }
        if ( !*v15 )
        {
          v30 = *((_QWORD *)this + 3);
          a7 = 0;
          LODWORD(a10) = 0;
          LifecycleManagerInfo = GetLifecycleManagerInfo(*(void **)(v30 + 72), (int *)&a7, (int *)&a10);
          if ( LifecycleManagerInfo < 0 )
          {
            *v15 = (unsigned __int16)LifecycleManagerInfo;
          }
          else
          {
            v32 = *((_DWORD *)this + 23);
            v33 = a7 ? v32 | 0x1000 : v32 | 0x400;
            *((_DWORD *)this + 23) = v33;
          }
          if ( !*v15 )
          {
            LOWORD(a7) = 0;
            if ( (int)QueryProcessArchitecture(v16, (unsigned __int16 *)&a7) < 0 )
            {
LABEL_38:
              *v15 = 87;
              goto LABEL_41;
            }
            v34 = a7;
            if ( a6 != (_WORD)a7 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v14);
              v34 = a7;
            }
            *((_WORD *)this + 214) = v34;
            if ( v34 != GetNativeArchitecture() )
            {
              LODWORD(a10) = 0;
              v35 = IsWow64GuestMachineSupported(v34, &a10);
              if ( v35 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x24D,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
                  (const char *)(unsigned int)v35,
                  v57);
                goto LABEL_38;
              }
              *((_BYTE *)this + 430) = (_DWORD)a10 != 0;
            }
          }
        }
      }
    }
    else
    {
LABEL_40:
      *v15 = 14;
    }
  }
LABEL_41:
  if ( *v15 )
    goto LABEL_91;
  v14 = a5;
  if ( (a5 & 1) != 0 )
    *((_DWORD *)this + 23) |= 0x80u;
  if ( (a5 & 6) != 0 )
  {
    if ( (a5 & 2) != 0 )
      *((_DWORD *)this + 23) |= 0x2000u;
    if ( (a5 & 4) != 0 )
      *((_DWORD *)this + 23) |= 0x4000u;
  }
  v36 = a8;
  if ( a8 )
  {
    ArchitecturePointerSizeInBytes = GetArchitecturePointerSizeInBytes(*((_WORD *)this + 214));
    if ( *((_DWORD *)v36 + 15) > 0x1000u
      || (v38 = *((unsigned int *)v36 + 4), (unsigned int)v38 > 0x1000)
      || *((_DWORD *)v36 + 12) > 0x1000u
      || (v14 = v38 - 4, *((unsigned int *)v36 + 6) > (unsigned __int64)(v38 - 4))
      || *((unsigned int *)v36 + 5) > v14
      || (v14 = *((unsigned int *)v36 + 7), v14 > v38 - 16)
      || (v39 = v38 - ArchitecturePointerSizeInBytes, *((_DWORD *)v36 + 8) > v39)
      || *((_DWORD *)v36 + 9) > v39
      || (v14 = *((unsigned int *)v36 + 12) - 4LL, *((unsigned int *)v36 + 13) > v14)
      || *((unsigned int *)v36 + 14) > v14
      || (v40 = *((_DWORD *)v36 + 15) - ArchitecturePointerSizeInBytes, *((_DWORD *)v36 + 16) > v40)
      || (v14 = *((unsigned int *)v36 + 15) - 16LL, *((unsigned int *)v36 + 19) > v14)
      || *((_DWORD *)v36 + 17) > v40
      || *((_DWORD *)v36 + 18) > v40 )
    {
      *v15 = 87;
    }
    v41 = *v15;
    if ( *v15 )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
          (unsigned int)"CProcess::CProcess",
          667,
          0,
          (__int64)L"%!WINERROR!",
          v41);
    }
    else
    {
      v42 = HeapAlloc(g_hHeap, 0, 0x60u);
      *((_QWORD *)this + 51) = v42;
      if ( !v42 )
      {
        *v15 = 14;
        goto LABEL_91;
      }
      *v42 = *(_OWORD *)v36;
      v42[1] = *((_OWORD *)v36 + 1);
      v42[2] = *((_OWORD *)v36 + 2);
      v42[3] = *((_OWORD *)v36 + 3);
      v42[4] = *((_OWORD *)v36 + 4);
      v42[5] = *((_OWORD *)v36 + 5);
    }
  }
  if ( !*v15 )
  {
    v43 = *((_QWORD *)this + 3);
    a7 = 0;
    v44 = IsTokenBoolPresent(*(void **)(v43 + 72), TokenIsAppContainer, (int *)&a7);
    if ( v44 < 0 )
    {
      *v15 = (unsigned __int16)v44;
    }
    else if ( a7 )
    {
      *((_DWORD *)this + 23) |= 0x200u;
    }
    if ( !*v15 )
    {
      v45 = *((_QWORD *)this + 3);
      a7 = 0;
      v46 = IsTokenBoolPresent(*(void **)(v45 + 72), TokenAppContainerNumber|TokenAuditPolicy, (int *)&a7);
      if ( v46 < 0 )
      {
        *v15 = (unsigned __int16)v46;
      }
      else if ( a7 )
      {
        *((_DWORD *)this + 23) |= 0x10000u;
      }
      if ( !*v15 )
      {
        v47 = (CToken *)*((_QWORD *)this + 3);
        a7 = 0;
        if ( (int)CToken::Impersonate(v47, 1, (int *)&a7) >= 0 )
        {
          v48 = I_RpcOpenClientProcess(Binding, 0x100000u, (void **)this + 15);
          v50 = v48;
          if ( v48 )
          {
            *((_DWORD *)this + 140) = v48;
            if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
            {
              LODWORD(v58) = v16;
              ComTraceMessageT<unsigned long,long>(
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
                (unsigned int)"CProcess::CProcess",
                726,
                v49,
                (__int64)L"Failed to open handle to PID %x (%!WINERROR!)",
                v58,
                v50);
            }
          }
          CToken::Revert(*((CToken **)this + 3), a7);
        }
      }
    }
  }
LABEL_91:
  *((_DWORD *)this + 22) = v16;
  if ( !*v15 )
  {
    v51 = CookieToPHPROCESSMap::Add((CookieToPHPROCESSMap *)v14, this, (unsigned __int64 *)this + 73);
    *v15 = v51;
    if ( !v51 )
    {
      CSharedLock::LockExclusive((CSharedLock *)gpProcessListLock);
      v52 = (unsigned int)VerifyNewProcess(v16) ? CBList::Insert(gpProcessList, this) : 5;
      *v15 = v52;
      CSharedLock::UnlockExclusive((CSharedLock *)gpProcessListLock);
      if ( *v15 )
        CookieToPHPROCESSMap::Remove(v53, *((_QWORD *)this + 73));
    }
  }
  if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(4) )
  {
    LODWORD(v59) = *((_DWORD *)this + 22);
    ComTraceMessageT<CProcess *,unsigned long,unsigned short *,unsigned __int64>(
      v54,
      (unsigned int)"CProcess::CProcess",
      763,
      v55,
      (__int64)L"this:%p PID:%x %ws GUID:%!GUID!",
      this,
      v59,
      *((_QWORD *)this + 48),
      (char *)this + 104);
  }
  return this;
}

```

## disassembly

```asm
0x18008c020  push    rbp
0x18008c022  push    rbx
0x18008c023  push    rsi
0x18008c024  push    rdi
0x18008c025  push    r12
0x18008c027  push    r13
0x18008c029  push    r14
0x18008c02b  push    r15
0x18008c02d  mov     rbp, rsp
0x18008c030  sub     rsp, 58h
0x18008c034  mov     edi, 1
0x18008c039  lea     rax, ??_7CProcess@@6B@; const CProcess::`vftable'
0x18008c040  mov     r12, rdx
0x18008c043  mov     [rcx+8], edi
0x18008c046  mov     rbx, rcx
0x18008c049  mov     [rcx], rax
0x18008c04c  xor     esi, esi
0x18008c04e  mov     r15, r9
0x18008c051  mov     [rcx+78h], rsi
0x18008c055  lea     r13d, [rdi+3]
0x18008c059  mov     edx, r13d; unsigned __int16
0x18008c05c  add     rcx, 0A8h; this
0x18008c063  mov     r14, r8
0x18008c066  call    ??0CBList@@QEAA@G@Z; CBList::CBList(ushort)
0x18008c06b  lea     edx, [rdi+0Fh]; unsigned __int16
0x18008c06e  lea     rcx, [rbx+0B8h]; this
0x18008c075  call    ??0CBList@@QEAA@G@Z; CBList::CBList(ushort)
0x18008c07a  lea     edx, [rdi+7]; unsigned __int16
0x18008c07d  lea     rcx, [rbx+0C8h]; this
0x18008c084  call    ??0CBList@@QEAA@G@Z; CBList::CBList(ushort)
0x18008c089  lea     rax, [rbx+0D8h]
0x18008c090  mov     [rax], rax
0x18008c093  lea     rcx, [rbx+1B8h]; SRWLock
0x18008c09a  mov     [rax+8], rax
0x18008c09e  mov     [rax+10h], rax
0x18008c0a2  mov     [rax+18h], rsi
0x18008c0a6  lea     rax, [rbx+0F8h]
0x18008c0ad  mov     [rax], rax
0x18008c0b0  mov     [rax+8], rax
0x18008c0b4  mov     [rax+10h], rax
0x18008c0b8  mov     [rax+18h], rsi
0x18008c0bc  xor     eax, eax
0x18008c0be  mov     [rbx+118h], rax
0x18008c0c5  lea     rax, [rbx+120h]
0x18008c0cc  mov     [rax], rax
0x18008c0cf  mov     [rax+8], rax
0x18008c0d3  mov     [rax+10h], rax
0x18008c0d7  mov     [rax+18h], rsi
0x18008c0db  mov     [rbx+140h], rsi
0x18008c0e2  mov     [rbx+148h], rsi
0x18008c0e9  mov     [rbx+150h], rsi
0x18008c0f0  mov     [rbx+158h], rsi
0x18008c0f7  mov     [rbx+160h], rsi
0x18008c0fe  mov     [rbx+168h], rsi
0x18008c105  mov     [rbx+1ACh], si
0x18008c10c  mov     [rbx+1AEh], sil
0x18008c113  mov     [rbx+1B0h], rsi
0x18008c11a  call    cs:__imp_InitializeSRWLock
0x18008c121  nop     dword ptr [rax+rax+00h]
0x18008c126  lea     rax, [rbx+1C0h]
0x18008c12d  mov     [rax], rax
0x18008c130  lea     rcx, [rbx+1E8h]; SRWLock
0x18008c137  mov     [rax+8], rax
0x18008c13b  mov     [rax+10h], rax
0x18008c13f  mov     [rax+18h], rsi
0x18008c143  mov     [rbx+1E0h], rsi
0x18008c14a  call    cs:__imp_InitializeSRWLock
0x18008c151  nop     dword ptr [rax+rax+00h]
0x18008c156  lea     rax, [rbx+1F0h]
0x18008c15d  mov     [rax], rax
0x18008c160  lea     rcx, [rbx+220h]; SRWLock
0x18008c167  mov     [rax+8], rax
0x18008c16b  mov     [rax+10h], rax
0x18008c16f  mov     [rax+18h], rsi
0x18008c173  mov     [rbx+210h], rsi
0x18008c17a  mov     [rbx+218h], sil
0x18008c181  call    cs:__imp_InitializeSRWLock
0x18008c188  nop     dword ptr [rax+rax+00h]
0x18008c18d  lea     rcx, [rbx+228h]; SRWLock
0x18008c194  call    cs:__imp_InitializeSRWLock
0x18008c19b  nop     dword ptr [rax+rax+00h]
0x18008c1a0  mov     [rbx+230h], rsi
0x18008c1a7  mov     [rbx+240h], sil
0x18008c1ae  mov     [rbx+248h], rsi
0x18008c1b5  mov     [rbx+18h], rsi
0x18008c1b9  mov     [rbx+20h], rsi
0x18008c1bd  mov     [rbx+58h], esi
0x18008c1c0  mov     [rbx+238h], rsi
0x18008c1c7  mov     [rbx+10h], edi
0x18008c1ca  mov     [rbx+30h], rsi
0x18008c1ce  mov     [rbx+38h], rsi
0x18008c1d2  mov     [rbx+48h], rsi
0x18008c1d6  mov     [rbx+5Ch], r13d
0x18008c1da  mov     [rbx+60h], rsi
0x18008c1de  mov     [rbx+40h], esi
0x18008c1e1  lea     rcx, [rbx+80h]; lpSystemTimeAsFileTime
0x18008c1e8  mov     [rbx+88h], rsi
0x18008c1ef  mov     [rbx+90h], esi
0x18008c1f5  mov     [rbx+98h], rsi
0x18008c1fc  mov     [rbx+170h], rsi
0x18008c203  mov     [rbx+178h], esi
0x18008c209  mov     [rbx+180h], rsi
0x18008c210  mov     [rbx+198h], rsi
0x18008c217  mov     [rbx+1A0h], rsi
0x18008c21e  mov     [rbx+1A8h], esi
0x18008c224  call    cs:__imp_GetSystemTimeAsFileTime
0x18008c22b  nop     dword ptr [rax+rax+00h]
0x18008c230  lea     rcx, [rbx+68h]; Uuid
0x18008c234  call    cs:__imp_UuidCreate
0x18008c23b  nop     dword ptr [rax+rax+00h]
0x18008c240  mov     rdi, [rbp+arg_48]
0x18008c247  mov     r13d, [rbp+arg_30]
0x18008c24b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18008c252  mov     [rbx+0A0h], esi
0x18008c258  mov     [rdi], esi
0x18008c25a  mov     [rbx+50h], rsi
0x18008c25e  movdqu  xmmword ptr [rbx+188h], xmm0
0x18008c266  test    r14, r14
0x18008c269  jz      loc_18008C475
0x18008c26f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18008c276  lea     r8d, [rsi+18h]; dwBytes
0x18008c27a  xor     edx, edx; dwFlags
0x18008c27c  call    cs:__imp_HeapAlloc
0x18008c283  nop     dword ptr [rax+rax+00h]
0x18008c288  test    rax, rax
0x18008c28b  jz      short loc_18008C2A1
0x18008c28d  lea     rcx, qword_180143A30
0x18008c294  mov     byte ptr [rax+8], 1
0x18008c298  mov     [rax], rcx
0x18008c29b  mov     [rax+10h], rsi
0x18008c29f  jmp     short loc_18008C2A4
0x18008c2a1  mov     rax, rsi
0x18008c2a4  mov     [rbx+28h], rax
0x18008c2a8  test    rax, rax
0x18008c2ab  jnz     short loc_18008C2B3
0x18008c2ad  mov     dword ptr [rdi], 0Eh
0x18008c2b3  cmp     [rdi], esi
0x18008c2b5  jnz     loc_18008C496
0x18008c2bb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008c2bf  mov     rax, rcx
0x18008c2c2  inc     rax
0x18008c2c5  cmp     [r14+rax*2], si
0x18008c2ca  jnz     short loc_18008C2C2
0x18008c2cc  lea     rsi, [rax+1]
0x18008c2d0  mov     eax, 2
0x18008c2d5  mul     rsi
0x18008c2d8  cmovb   rax, rcx
0x18008c2dc  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18008c2e3  mov     r8, rax; dwBytes
0x18008c2e6  xor     edx, edx; dwFlags
0x18008c2e8  call    cs:__imp_HeapAlloc
0x18008c2ef  nop     dword ptr [rax+rax+00h]
0x18008c2f4  mov     [rbx+20h], rax
0x18008c2f8  test    rax, rax
0x18008c2fb  jz      loc_18008C48E
0x18008c301  mov     r8, r14; unsigned __int16 *
0x18008c304  mov     rdx, rsi; unsigned __int64
0x18008c307  mov     rcx, rax; unsigned __int16 *
0x18008c30a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008c30f  xor     esi, esi
0x18008c311  cmp     [rdi], esi
0x18008c313  jnz     loc_18008C496
0x18008c319  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008c31d  mov     rax, rcx
0x18008c320  inc     rax
0x18008c323  cmp     [r15+rax*2], si
0x18008c328  jnz     short loc_18008C320
0x18008c32a  lea     rsi, [rax+1]
0x18008c32e  mov     eax, 2
0x18008c333  mul     rsi
0x18008c336  cmovb   rax, rcx
0x18008c33a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18008c341  mov     r8, rax; dwBytes
0x18008c344  xor     edx, edx; dwFlags
0x18008c346  call    cs:__imp_HeapAlloc
0x18008c34d  nop     dword ptr [rax+rax+00h]
0x18008c352  mov     [rbx+180h], rax
0x18008c359  test    rax, rax
0x18008c35c  jz      loc_18008C48E
0x18008c362  mov     r8, r15; unsigned __int16 *
0x18008c365  mov     rdx, rsi; unsigned __int64
0x18008c368  mov     rcx, rax; unsigned __int16 *
0x18008c36b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008c370  xor     esi, esi
0x18008c372  cmp     [rdi], esi
0x18008c374  jnz     loc_18008C496
0x18008c37a  mov     rcx, [r12]; this
0x18008c37e  lea     rdx, [rbp+arg_30]; bool *
0x18008c382  mov     [rbx+18h], rcx
0x18008c386  mov     [r12], rsi
0x18008c38a  mov     byte ptr [rbp+arg_30], sil
0x18008c38e  call    ?HasSysAppId@CToken@@QEAAJPEA_N@Z; CToken::HasSysAppId(bool *)
0x18008c393  test    eax, eax
0x18008c395  js      short loc_18008C3A9
0x18008c397  cmp     byte ptr [rbp+arg_30], sil
0x18008c39b  jz      short loc_18008C3AE
0x18008c39d  mov     eax, [rbx+5Ch]
0x18008c3a0  bts     eax, 0Bh
0x18008c3a4  mov     [rbx+5Ch], eax
0x18008c3a7  jmp     short loc_18008C3AE
0x18008c3a9  movzx   eax, ax
0x18008c3ac  mov     [rdi], eax
0x18008c3ae  cmp     [rdi], esi
0x18008c3b0  jnz     loc_18008C496
0x18008c3b6  mov     rcx, [rbx+18h]
0x18008c3ba  lea     r8, [rbp+arg_48]; int *
0x18008c3c1  lea     rdx, [rbp+arg_30]; int *
0x18008c3c5  mov     [rbp+arg_30], esi
0x18008c3c8  mov     dword ptr [rbp+arg_48], esi
0x18008c3ce  mov     rcx, [rcx+48h]; void *
0x18008c3d2  call    ?GetLifecycleManagerInfo@@YAJPEAXPEAH1@Z; GetLifecycleManagerInfo(void *,int *,int *)
0x18008c3d7  test    eax, eax
0x18008c3d9  js      short loc_18008C3F2
0x18008c3db  mov     eax, [rbx+5Ch]
0x18008c3de  cmp     [rbp+arg_30], esi
0x18008c3e1  jz      short loc_18008C3E9
0x18008c3e3  bts     eax, 0Ch
0x18008c3e7  jmp     short loc_18008C3ED
0x18008c3e9  bts     eax, 0Ah
0x18008c3ed  mov     [rbx+5Ch], eax
0x18008c3f0  jmp     short loc_18008C3F7
0x18008c3f2  movzx   eax, ax
0x18008c3f5  mov     [rdi], eax
0x18008c3f7  cmp     [rdi], esi
0x18008c3f9  jnz     loc_18008C496
0x18008c3ff  lea     rdx, [rbp+arg_30]; unsigned __int16 *
0x18008c403  mov     word ptr [rbp+arg_30], si
0x18008c407  mov     ecx, r13d; unsigned int
0x18008c40a  call    ?QueryProcessArchitecture@@YAJKPEAG@Z; QueryProcessArchitecture(ulong,ushort *)
0x18008c40f  test    eax, eax
0x18008c411  js      short loc_18008C475
0x18008c413  movzx   esi, word ptr [rbp+arg_30]
0x18008c417  cmp     [rbp+arg_28], si
0x18008c41b  jz      short loc_18008C426
0x18008c41d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008c422  movzx   esi, word ptr [rbp+arg_30]
0x18008c426  mov     [rbx+1ACh], si
0x18008c42d  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x18008c432  cmp     si, ax
0x18008c435  jz      short loc_18008C494
0x18008c437  lea     rdx, [rbp+arg_48]
0x18008c43e  mov     dword ptr [rbp+arg_48], 0
0x18008c448  movzx   ecx, si
0x18008c44b  call    cs:__imp_IsWow64GuestMachineSupported
0x18008c452  nop     dword ptr [rax+rax+00h]
0x18008c457  xor     esi, esi
0x18008c459  test    eax, eax
0x18008c45b  jns     short loc_18008C47D
0x18008c45d  mov     rcx, [rbp+40h]; this
0x18008c461  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x18008c468  mov     r9d, eax; char *
0x18008c46b  mov     edx, 24Dh; void *
0x18008c470  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008c475  mov     dword ptr [rdi], 57h ; 'W'
0x18008c47b  jmp     short loc_18008C496
0x18008c47d  cmp     dword ptr [rbp+arg_48], esi
0x18008c483  setnz   al
0x18008c486  mov     [rbx+1AEh], al
0x18008c48c  jmp     short loc_18008C496
0x18008c48e  mov     dword ptr [rdi], 0Eh
0x18008c494  xor     esi, esi
0x18008c496  lea     r15, aCprocessCproce_0; "CProcess::CProcess"
0x18008c49d  cmp     [rdi], esi
0x18008c49f  jnz     loc_18008C747
0x18008c4a5  mov     ecx, [rbp+arg_20]
0x18008c4a8  test    cl, 1
0x18008c4ab  jz      short loc_18008C4B7
0x18008c4ad  mov     eax, [rbx+5Ch]
0x18008c4b0  bts     eax, 7
0x18008c4b4  mov     [rbx+5Ch], eax
0x18008c4b7  test    cl, 6
0x18008c4ba  jz      short loc_18008C4DA
0x18008c4bc  test    cl, 2
0x18008c4bf  jz      short loc_18008C4CB
0x18008c4c1  mov     eax, [rbx+5Ch]
0x18008c4c4  bts     eax, 0Dh
0x18008c4c8  mov     [rbx+5Ch], eax
0x18008c4cb  test    cl, 4
0x18008c4ce  jz      short loc_18008C4DA
0x18008c4d0  mov     eax, [rbx+5Ch]
0x18008c4d3  bts     eax, 0Eh
0x18008c4d7  mov     [rbx+5Ch], eax
0x18008c4da  mov     rsi, [rbp+arg_38]
0x18008c4e1  test    rsi, rsi
0x18008c4e4  jz      loc_18008C5E9
0x18008c4ea  movzx   ecx, word ptr [rbx+1ACh]; unsigned __int16
0x18008c4f1  call    ?GetArchitecturePointerSizeInBytes@@YAKG@Z; GetArchitecturePointerSizeInBytes(ushort)
0x18008c4f6  mov     r9d, eax
0x18008c4f9  mov     eax, 1000h
0x18008c4fe  cmp     [rsi+3Ch], eax
0x18008c501  ja      short loc_18008C577
0x18008c503  mov     edx, [rsi+10h]
0x18008c506  cmp     edx, eax
0x18008c508  ja      short loc_18008C577
0x18008c50a  cmp     [rsi+30h], eax
0x18008c50d  ja      short loc_18008C577
0x18008c50f  mov     eax, [rsi+18h]
0x18008c512  lea     rcx, [rdx-4]
0x18008c516  cmp     rax, rcx
0x18008c519  ja      short loc_18008C577
  ... truncated ...
```
