# TLPCMgr::TLPCMgr(TLoad64BitDllsMgr *)

- ea: `0x140010400`
- end: `0x1400105dc`
- name: `??0TLPCMgr@@QEAA@PEAVTLoad64BitDllsMgr@@@Z`
- size: `476`
- prototype: `TLPCMgr *__fastcall(TLPCMgr *__hidden this, struct TLoad64BitDllsMgr *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140007a9c`

## callees

- `0x140001b50`
- `0x1400085d8`
- `0x140010400`
- `0x140012fdc`
- `0x140013f74`
- `0x140013ff8`
- `0x1400142b8`
- `0x140016010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001058a`
- `KERNEL32!SetLastError` at `0x14001058a`
- `KERNEL32!InitializeCriticalSection` at `0x140010582`
- `KERNEL32!InitializeCriticalSection` at `0x140010582`
- `KERNEL32!GetLastError` at `0x14001059a`
- `KERNEL32!GetLastError` at `0x14001059a`

## string_xrefs

- `0x1400105a3`: `Failed to create the list of connected clients.  Error %d.`

## pseudocode

```c
TLPCMgr *__fastcall TLPCMgr::TLPCMgr(TLPCMgr *this, struct TLoad64BitDllsMgr *a2)
{
  const char *v2; // r9
  __int64 v4; // rbp
  char *v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // r8
  char *v9; // rax
  _QWORD *v10; // rax
  unsigned int v11; // edx
  __int64 v12; // rax
  int v13; // eax
  _OWORD *v14; // rax
  _OWORD *v15; // rbx
  _BYTE *v16; // rcx
  const char *v17; // rax
  _BYTE *v18; // rax
  DWORD LastError; // eax
  LPCRITICAL_SECTION v21; // [rsp+40h] [rbp+8h] BYREF

  v2 = "TLPCMgr";
  v4 = 2147483646;
  v5 = (char *)this + 16;
  v6 = 32;
  v7 = 2147483646;
  v8 = 32;
  *(_OWORD *)v5 = 0;
  *((_OWORD *)v5 + 1) = 0;
  do
  {
    if ( !v7 )
      break;
    if ( !*v2 )
      break;
    *v5++ = *v2++;
    --v7;
    --v8;
  }
  while ( v8 );
  v9 = v5 - 1;
  if ( v8 )
    v9 = v5;
  *v9 = 0;
  *(_QWORD *)this = &TLPCMgr::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = a2;
  *((_QWORD *)this + 8) = 0;
  NThreadingLibrary::TWorkCrew::TWorkCrew((struct _RTL_CRITICAL_SECTION *)((char *)this + 88));
  *((_QWORD *)this + 11) = &TLPCMgr::TWorkCrewForUniqueProcess::`vftable'{for `NCoreLibrary::TReferenceCount'};
  *((_QWORD *)this + 13) = &TLPCMgr::TWorkCrewForUniqueProcess::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'};
  v10 = (_QWORD *)NAdvancedLibrary::TCopyCritsec::TCopyCritsec((NAdvancedLibrary::TCopyCritsec *)&v21);
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 43) = (char *)this + 336;
  *((_QWORD *)this + 42) = (char *)this + 336;
  *((_QWORD *)this + 44) = NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::Delete;
  *((_QWORD *)this + 40) = &NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::`vftable';
  *((_QWORD *)this + 45) = 0;
  *((_DWORD *)this + 92) = 0;
  *((_DWORD *)this + 94) = 1818391656;
  *((_QWORD *)this + 48) = *v10;
  *v10 = 0;
  v12 = *((_QWORD *)this + 48);
  if ( v12 )
    v13 = *(_DWORD *)(v12 + 48);
  else
    v13 = -2147024882;
  *((_DWORD *)this + 99) = v13;
  if ( v13 >= 0 )
    *((_DWORD *)this + 99) = NAdvancedLibrary::THashTableBase::Initialize((TLPCMgr *)((char *)this + 320), v11);
  NAdvancedLibrary::TCopyCritsec::~TCopyCritsec(&v21);
  *((_QWORD *)this + 10) = 0;
  v14 = operator new(0x60u);
  v15 = v14;
  if ( v14 )
  {
    v16 = v14;
    *v14 = 0;
    v14[1] = 0;
    v17 = "TLstMgr";
    do
    {
      if ( !v4 )
        break;
      if ( !*v17 )
        break;
      *v16++ = *v17++;
      --v4;
      --v6;
    }
    while ( v6 );
    v18 = v16 - 1;
    if ( v6 )
      v18 = v16;
    *v18 = 0;
    *((_QWORD *)v15 + 4) = 0;
    *((_QWORD *)v15 + 5) = 0;
    *((_DWORD *)v15 + 12) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 56));
    SetLastError(0);
    *((_QWORD *)this + 10) = v15;
  }
  else
  {
    *((_QWORD *)this + 10) = 0;
    LastError = GetLastError();
    SplWow64Telemetry::WriteDbgTraceError(
      "TLPCMgr::TLPCMgr",
      L"Failed to create the list of connected clients.  Error %d.",
      LastError);
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
  return this;
}

```

## disassembly

```asm
0x140010400  mov     [rsp+arg_8], rbx
0x140010405  mov     [rsp+arg_10], rbp
0x14001040a  push    rsi
0x14001040b  push    rdi
0x14001040c  push    r14
0x14001040e  sub     rsp, 20h
0x140010412  xorps   xmm0, xmm0
0x140010415  lea     r9, aTlpcmgr; "TLPCMgr"
0x14001041c  mov     rdi, rcx
0x14001041f  mov     ebp, 7FFFFFFEh
0x140010424  add     rcx, 10h
0x140010428  mov     esi, 20h ; ' '
0x14001042d  mov     r10, rdx
0x140010430  mov     eax, ebp
0x140010432  mov     r8d, esi
0x140010435  xor     r14d, r14d
0x140010438  movups  xmmword ptr [rcx], xmm0
0x14001043b  movups  xmmword ptr [rcx+10h], xmm0
0x14001043f  test    rax, rax
0x140010442  jz      short loc_14001045C
0x140010444  mov     dl, [r9]
0x140010447  test    dl, dl
0x140010449  jz      short loc_14001045C
0x14001044b  mov     [rcx], dl
0x14001044d  inc     r9
0x140010450  inc     rcx
0x140010453  dec     rax
0x140010456  sub     r8, 1
0x14001045a  jnz     short loc_14001043F
0x14001045c  lea     rax, [rcx-1]
0x140010460  test    r8, r8
0x140010463  lea     rbx, [rdi+58h]
0x140010467  cmovnz  rax, rcx
0x14001046b  mov     rcx, rbx; this
0x14001046e  mov     [rax], r14b
0x140010471  lea     rax, ??_7TLPCMgr@@6B@; const TLPCMgr::`vftable'
0x140010478  mov     [rdi], rax
0x14001047b  mov     [rdi+8], r14d
0x14001047f  mov     [rdi+30h], r10
0x140010483  mov     [rdi+40h], r14
0x140010487  call    ??0TWorkCrew@NThreadingLibrary@@QEAA@XZ; NThreadingLibrary::TWorkCrew::TWorkCrew(void)
0x14001048c  lea     rax, ??_7TWorkCrewForUniqueProcess@TLPCMgr@@6BTReferenceCount@NCoreLibrary@@@; const TLPCMgr::TWorkCrewForUniqueProcess::`vftable'{for `NCoreLibrary::TReferenceCount'}
0x140010493  mov     [rbx], rax
0x140010496  lea     rcx, [rsp+38h+arg_0]; this
0x14001049b  lea     rax, ??_7TWorkCrewForUniqueProcess@TLPCMgr@@6BTTpSetWorkEnv@NThreadingLibrary@@@; const TLPCMgr::TWorkCrewForUniqueProcess::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'}
0x1400104a2  mov     [rbx+10h], rax
0x1400104a6  add     rbx, 0E8h
0x1400104ad  call    ??0TCopyCritsec@NAdvancedLibrary@@QEAA@XZ; NAdvancedLibrary::TCopyCritsec::TCopyCritsec(void)
0x1400104b2  lea     rcx, [rbx+10h]
0x1400104b6  mov     [rbx+8], r14
0x1400104ba  mov     [rcx+8], rcx
0x1400104be  mov     [rcx], rcx
0x1400104c1  lea     rcx, ?Delete@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@KAXPEAVTHashElementBase@2@@Z; NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::Delete(NAdvancedLibrary::THashElementBase *)
0x1400104c8  mov     [rbx+20h], rcx
0x1400104cc  lea     rcx, ??_7?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@6B@; const NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::`vftable'
0x1400104d3  mov     [rbx], rcx
0x1400104d6  mov     [rbx+28h], r14
0x1400104da  mov     [rbx+30h], r14d
0x1400104de  mov     dword ptr [rbx+38h], 6C627468h
0x1400104e5  mov     rcx, [rax]
0x1400104e8  mov     [rbx+40h], rcx
0x1400104ec  mov     [rax], r14
0x1400104ef  mov     rax, [rbx+40h]
0x1400104f3  test    rax, rax
0x1400104f6  jz      short loc_1400104FD
0x1400104f8  mov     eax, [rax+30h]
0x1400104fb  jmp     short loc_140010502
0x1400104fd  mov     eax, 8007000Eh
0x140010502  mov     [rbx+4Ch], eax
0x140010505  test    eax, eax
0x140010507  js      short loc_140010514
0x140010509  mov     rcx, rbx; this
0x14001050c  call    ?Initialize@THashTableBase@NAdvancedLibrary@@QEAAJK@Z; NAdvancedLibrary::THashTableBase::Initialize(ulong)
0x140010511  mov     [rbx+4Ch], eax
0x140010514  lea     rcx, [rsp+38h+arg_0]; this
0x140010519  call    ??1TCopyCritsec@NAdvancedLibrary@@QEAA@XZ; NAdvancedLibrary::TCopyCritsec::~TCopyCritsec(void)
0x14001051e  mov     ecx, 60h ; '`'; Size
0x140010523  mov     [rdi+50h], r14
0x140010527  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001052c  mov     rbx, rax
0x14001052f  test    rax, rax
0x140010532  jz      short loc_140010596
0x140010534  xorps   xmm0, xmm0
0x140010537  mov     rcx, rbx
0x14001053a  movups  xmmword ptr [rax], xmm0
0x14001053d  movups  xmmword ptr [rax+10h], xmm0
0x140010541  lea     rax, aTlstmgr; "TLstMgr"
0x140010548  test    rbp, rbp
0x14001054b  jz      short loc_140010564
0x14001054d  mov     dl, [rax]
0x14001054f  test    dl, dl
0x140010551  jz      short loc_140010564
0x140010553  mov     [rcx], dl
0x140010555  inc     rax
0x140010558  inc     rcx
0x14001055b  dec     rbp
0x14001055e  sub     rsi, 1
0x140010562  jnz     short loc_140010548
0x140010564  lea     rax, [rcx-1]
0x140010568  test    rsi, rsi
0x14001056b  cmovnz  rax, rcx
0x14001056f  lea     rcx, [rbx+38h]; lpCriticalSection
0x140010573  mov     [rax], r14b
0x140010576  mov     [rbx+20h], r14
0x14001057a  mov     [rbx+28h], r14
0x14001057e  mov     [rbx+30h], r14d
0x140010582  call    cs:__imp_InitializeCriticalSection
0x140010588  xor     ecx, ecx; dwErrCode
0x14001058a  call    cs:__imp_SetLastError
0x140010590  mov     [rdi+50h], rbx
0x140010594  jmp     short loc_1400105B6
0x140010596  mov     [rdi+50h], r14
0x14001059a  call    cs:__imp_GetLastError
0x1400105a0  mov     r8d, eax
0x1400105a3  lea     rdx, aFailedToCreate_3; "Failed to create the list of connected "...
0x1400105aa  lea     rcx, aTlpcmgrTlpcmgr; "TLPCMgr::TLPCMgr"
0x1400105b1  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400105b6  mov     rcx, [rdi+30h]
0x1400105ba  mov     rax, [rcx]
0x1400105bd  mov     rax, [rax+8]
0x1400105c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400105c6  mov     rbx, [rsp+38h+arg_8]
0x1400105cb  mov     rax, rdi
0x1400105ce  mov     rbp, [rsp+38h+arg_10]
0x1400105d3  add     rsp, 20h
0x1400105d7  pop     r14
0x1400105d9  pop     rdi
0x1400105da  pop     rsi
0x1400105db  retn
```
