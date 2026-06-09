# W3WP_HOST::~W3WP_HOST(void)

- ea: `0x180002dbc`
- end: `0x180003108`
- name: `??1W3WP_HOST@@QEAA@XZ`
- size: `844`
- prototype: `void __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003188`

## callees

- `0x180001c80`
- `0x1800020d0`
- `0x180002d40`
- `0x180002d94`
- `0x180002dbc`
- `0x180003110`
- `0x1800031b0`
- `0x180003abc`
- `0x180003e20`
- `0x180008cfc`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002ee7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002ee7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f2a`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800030cd`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800030cd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800030a7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800030ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800030a7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800030ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800030fc`
- `nativerd!TerminateNativeConfiguration` at `0x180002f63`
- `nativerd!TerminateNativeConfiguration` at `0x180002f63`

## pseudocode

```c
void __fastcall W3WP_HOST::~W3WP_HOST(W3WP_HOST *this)
{
  unsigned int v2; // edx
  WP_IDLE_TIMER *v3; // rcx
  WP_IPM *v4; // rcx
  __int64 v5; // rcx
  void *v6; // rdi
  __int64 v7; // rcx
  HMODULE v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx

  *((_DWORD *)this + 18) = 1483223927;
  *(_QWORD *)this = &W3WP_HOST::`vftable'{for `IWorkerProcessFramework'};
  *((_QWORD *)this + 1) = &W3WP_HOST::`vftable'{for `IWpfApplicationInfoUtil'};
  *((_QWORD *)this + 2) = &W3WP_HOST::`vftable'{for `IWpfSettings'};
  *((_QWORD *)this + 3) = &W3WP_HOST::`vftable'{for `IWpfActions'};
  *((_QWORD *)this + 4) = &W3WP_HOST::`vftable'{for `IWpfExposeProtocolManagerCustomInterface'};
  *((_QWORD *)this + 5) = &W3WP_HOST::`vftable'{for `IIisCoreReportCounters'};
  *((_QWORD *)this + 6) = &W3WP_HOST::`vftable'{for `IWPInstanceCountersManager'};
  *((_QWORD *)this + 7) = &W3WP_HOST::`vftable'{for `IWpfApplicationPreloadUtil'};
  *((_QWORD *)this + 8) = &W3WP_HOST::`vftable'{for `IWPInstanceSendData'};
  (*(void (__fastcall **)(char *, _QWORD, __int64))(*((_QWORD *)g_pW3WPHost + 6) + 32LL))(
    (char *)g_pW3WPHost + 48,
    0,
    3);
  v3 = (WP_IDLE_TIMER *)*((_QWORD *)this + 12);
  if ( v3 )
  {
    WP_IDLE_TIMER::`scalar deleting destructor'(v3, v2);
    *((_QWORD *)this + 12) = 0;
  }
  v4 = (WP_IPM *)*((_QWORD *)this + 11);
  if ( v4 )
  {
    WP_IPM::Terminate(v4);
    operator delete(*((void **)this + 11));
    *((_QWORD *)this + 11) = 0;
  }
  v5 = *((_QWORD *)this + 197);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 197) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 13);
  if ( v6 )
  {
    WP_RECYCLER::~WP_RECYCLER(*((LPCRITICAL_SECTION *)this + 13));
    operator delete(v6);
    *((_QWORD *)this + 13) = 0;
  }
  v7 = *((_QWORD *)this + 38);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 38) = 0;
  }
  v8 = (HMODULE)*((_QWORD *)this + 196);
  if ( v8 )
  {
    FreeLibrary(v8);
    *((_QWORD *)this + 196) = 0;
  }
  if ( *((_DWORD *)this + 50) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
    *((_DWORD *)this + 50) = 0;
  }
  if ( *((_DWORD *)this + 62) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
    *((_DWORD *)this + 62) = 0;
  }
  v9 = *((_QWORD *)this + 24);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 24) = 0;
  }
  if ( *((_DWORD *)this + 46) )
  {
    TerminateNativeConfiguration();
    *((_DWORD *)this + 46) = 0;
  }
  W3WP_HOST::DeleteCounterSetInstance((W3WP_HOST *)((char *)this + 48), 0);
  ARRAY_LIST::Clear((W3WP_HOST *)((char *)this + 344));
  v10 = *((_QWORD *)this + 39);
  if ( *(_DWORD *)(v10 + 88) && v10 )
  {
    v11 = *(void **)(v10 + 40);
    if ( v11 )
    {
      operator delete(v11);
      *(_QWORD *)(*((_QWORD *)this + 39) + 40LL) = 0;
    }
    v12 = *(void **)(*((_QWORD *)this + 39) + 104LL);
    if ( v12 )
    {
      operator delete(v12);
      *(_QWORD *)(*((_QWORD *)this + 39) + 104LL) = 0;
    }
    v13 = *(void **)(*((_QWORD *)this + 39) + 48LL);
    if ( v13 )
    {
      operator delete(v13);
      *(_QWORD *)(*((_QWORD *)this + 39) + 48LL) = 0;
    }
    v14 = *(void **)(*((_QWORD *)this + 39) + 64LL);
    if ( v14 )
    {
      operator delete(v14);
      *(_QWORD *)(*((_QWORD *)this + 39) + 64LL) = 0;
    }
    v15 = *(void **)(*((_QWORD *)this + 39) + 72LL);
    if ( v15 )
    {
      operator delete(v15);
      *(_QWORD *)(*((_QWORD *)this + 39) + 72LL) = 0;
    }
    v16 = *(void **)(*((_QWORD *)this + 39) + 24LL);
    if ( v16 )
    {
      operator delete(v16);
      *(_QWORD *)(*((_QWORD *)this + 39) + 24LL) = 0;
    }
    v17 = *(void **)(*((_QWORD *)this + 39) + 80LL);
    if ( v17 )
    {
      operator delete(v17);
      *(_QWORD *)(*((_QWORD *)this + 39) + 80LL) = 0;
    }
    operator delete(*((void **)this + 39));
    *((_QWORD *)this + 39) = 0;
  }
  SMALL_STRU::Reset((W3WP_HOST *)((char *)this + 1600));
  STRU::~STRU((W3WP_HOST *)((char *)this + 976));
  STRU::~STRU((W3WP_HOST *)((char *)this + 400));
  CReaderWriterLock3::~CReaderWriterLock3((W3WP_HOST *)((char *)this + 368));
  ARRAY_LIST::~ARRAY_LIST((W3WP_HOST *)((char *)this + 344));
  PROTOCOL_MANAGER_LIST::~PROTOCOL_MANAGER_LIST((W3WP_HOST *)((char *)this + 320));
  STRU::~STRU((W3WP_HOST *)((char *)this + 128));
}

```

## disassembly

```asm
0x180002dbc  push    rbx
0x180002dbe  push    rbp
0x180002dbf  push    rsi
0x180002dc0  push    rdi
0x180002dc1  sub     rsp, 38h
0x180002dc5  mov     dword ptr [rcx+48h], 58683377h
0x180002dcc  lea     rax, ??_7W3WP_HOST@@6BIWorkerProcessFramework@@@; const W3WP_HOST::`vftable'{for `IWorkerProcessFramework'}
0x180002dd3  mov     [rcx], rax
0x180002dd6  mov     rbx, rcx
0x180002dd9  lea     rax, ??_7W3WP_HOST@@6BIWpfApplicationInfoUtil@@@; const W3WP_HOST::`vftable'{for `IWpfApplicationInfoUtil'}
0x180002de0  xor     r9d, r9d
0x180002de3  mov     [rcx+8], rax
0x180002de7  xor     edx, edx
0x180002de9  lea     rax, ??_7W3WP_HOST@@6BIWpfSettings@@@; const W3WP_HOST::`vftable'{for `IWpfSettings'}
0x180002df0  mov     [rcx+10h], rax
0x180002df4  lea     rax, ??_7W3WP_HOST@@6BIWpfActions@@@; const W3WP_HOST::`vftable'{for `IWpfActions'}
0x180002dfb  mov     [rcx+18h], rax
0x180002dff  lea     r8d, [r9+3]
0x180002e03  lea     rax, ??_7W3WP_HOST@@6BIWpfExposeProtocolManagerCustomInterface@@@; const W3WP_HOST::`vftable'{for `IWpfExposeProtocolManagerCustomInterface'}
0x180002e0a  mov     [rcx+20h], rax
0x180002e0e  lea     rax, ??_7W3WP_HOST@@6BIIisCoreReportCounters@@@; const W3WP_HOST::`vftable'{for `IIisCoreReportCounters'}
0x180002e15  mov     [rcx+28h], rax
0x180002e19  lea     rax, ??_7W3WP_HOST@@6BIWPInstanceCountersManager@@@; const W3WP_HOST::`vftable'{for `IWPInstanceCountersManager'}
0x180002e20  mov     [rcx+30h], rax
0x180002e24  lea     rax, ??_7W3WP_HOST@@6BIWpfApplicationPreloadUtil@@@; const W3WP_HOST::`vftable'{for `IWpfApplicationPreloadUtil'}
0x180002e2b  mov     [rcx+38h], rax
0x180002e2f  lea     rax, ??_7W3WP_HOST@@6BIWPInstanceSendData@@@; const W3WP_HOST::`vftable'{for `IWPInstanceSendData'}
0x180002e36  mov     [rcx+40h], rax
0x180002e3a  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180002e41  add     rcx, 30h ; '0'
0x180002e45  mov     rax, [rcx]
0x180002e48  mov     rax, [rax+20h]
0x180002e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e51  mov     rcx, [rbx+60h]; this
0x180002e55  xor     ebp, ebp
0x180002e57  test    rcx, rcx
0x180002e5a  jz      short loc_180002E65
0x180002e5c  call    ??_GWP_IDLE_TIMER@@QEAAPEAXI@Z; WP_IDLE_TIMER::`scalar deleting destructor'(uint)
0x180002e61  mov     [rbx+60h], rbp
0x180002e65  mov     rcx, [rbx+58h]; this
0x180002e69  test    rcx, rcx
0x180002e6c  jz      short loc_180002E80
0x180002e6e  call    ?Terminate@WP_IPM@@QEAAJXZ; WP_IPM::Terminate(void)
0x180002e73  mov     rcx, [rbx+58h]; Block
0x180002e77  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e7c  mov     [rbx+58h], rbp
0x180002e80  mov     rcx, [rbx+628h]
0x180002e87  test    rcx, rcx
0x180002e8a  jz      short loc_180002E9F
0x180002e8c  mov     rax, [rcx]
0x180002e8f  mov     rax, [rax+10h]
0x180002e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e98  mov     [rbx+628h], rbp
0x180002e9f  mov     rdi, [rbx+68h]
0x180002ea3  test    rdi, rdi
0x180002ea6  jz      short loc_180002EBC
0x180002ea8  mov     rcx, rdi; lpCriticalSection
0x180002eab  call    ??1WP_RECYCLER@@QEAA@XZ; WP_RECYCLER::~WP_RECYCLER(void)
0x180002eb0  mov     rcx, rdi; Block
0x180002eb3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002eb8  mov     [rbx+68h], rbp
0x180002ebc  mov     rcx, [rbx+130h]
0x180002ec3  test    rcx, rcx
0x180002ec6  jz      short loc_180002EDB
0x180002ec8  mov     rax, [rcx]
0x180002ecb  mov     rax, [rax+10h]
0x180002ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed4  mov     [rbx+130h], rbp
0x180002edb  mov     rcx, [rbx+620h]; hLibModule
0x180002ee2  test    rcx, rcx
0x180002ee5  jz      short loc_180002EFA
0x180002ee7  call    cs:__imp_FreeLibrary
0x180002eee  nop     dword ptr [rax+rax+00h]
0x180002ef3  mov     [rbx+620h], rbp
0x180002efa  cmp     [rbx+0C8h], ebp
0x180002f00  jz      short loc_180002F1B
0x180002f02  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x180002f09  call    cs:__imp_DeleteCriticalSection
0x180002f10  nop     dword ptr [rax+rax+00h]
0x180002f15  mov     [rbx+0C8h], ebp
0x180002f1b  cmp     [rbx+0F8h], ebp
0x180002f21  jz      short loc_180002F3C
0x180002f23  lea     rcx, [rbx+100h]; lpCriticalSection
0x180002f2a  call    cs:__imp_DeleteCriticalSection
0x180002f31  nop     dword ptr [rax+rax+00h]
0x180002f36  mov     [rbx+0F8h], ebp
0x180002f3c  mov     rcx, [rbx+0C0h]
0x180002f43  test    rcx, rcx
0x180002f46  jz      short loc_180002F5B
0x180002f48  mov     rax, [rcx]
0x180002f4b  mov     rax, [rax+10h]
0x180002f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f54  mov     [rbx+0C0h], rbp
0x180002f5b  cmp     [rbx+0B8h], ebp
0x180002f61  jz      short loc_180002F75
0x180002f63  call    cs:__imp_?TerminateNativeConfiguration@@YAXXZ; TerminateNativeConfiguration(void)
0x180002f6a  nop     dword ptr [rax+rax+00h]
0x180002f6f  mov     [rbx+0B8h], ebp
0x180002f75  xor     edx, edx; unsigned int
0x180002f77  lea     rcx, [rbx+30h]; this
0x180002f7b  call    ?DeleteCounterSetInstance@W3WP_HOST@@UEAAJK@Z; W3WP_HOST::DeleteCounterSetInstance(ulong)
0x180002f80  lea     rdi, [rbx+158h]
0x180002f87  mov     rcx, rdi; this
0x180002f8a  call    ?Clear@ARRAY_LIST@@QEAAXXZ; ARRAY_LIST::Clear(void)
0x180002f8f  mov     rax, [rbx+138h]
0x180002f96  cmp     [rax+58h], ebp
0x180002f99  jz      loc_180003094
0x180002f9f  test    rax, rax
0x180002fa2  jz      loc_180003094
0x180002fa8  mov     rcx, [rax+28h]; Block
0x180002fac  test    rcx, rcx
0x180002faf  jz      short loc_180002FC1
0x180002fb1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002fb6  mov     rax, [rbx+138h]
0x180002fbd  mov     [rax+28h], rbp
0x180002fc1  mov     rax, [rbx+138h]
0x180002fc8  mov     rcx, [rax+68h]; Block
0x180002fcc  test    rcx, rcx
0x180002fcf  jz      short loc_180002FE1
0x180002fd1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002fd6  mov     rax, [rbx+138h]
0x180002fdd  mov     [rax+68h], rbp
0x180002fe1  mov     rax, [rbx+138h]
0x180002fe8  mov     rcx, [rax+30h]; Block
0x180002fec  test    rcx, rcx
0x180002fef  jz      short loc_180003001
0x180002ff1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ff6  mov     rax, [rbx+138h]
0x180002ffd  mov     [rax+30h], rbp
0x180003001  mov     rax, [rbx+138h]
0x180003008  mov     rcx, [rax+40h]; Block
0x18000300c  test    rcx, rcx
0x18000300f  jz      short loc_180003021
0x180003011  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003016  mov     rax, [rbx+138h]
0x18000301d  mov     [rax+40h], rbp
0x180003021  mov     rax, [rbx+138h]
0x180003028  mov     rcx, [rax+48h]; Block
0x18000302c  test    rcx, rcx
0x18000302f  jz      short loc_180003041
0x180003031  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003036  mov     rax, [rbx+138h]
0x18000303d  mov     [rax+48h], rbp
0x180003041  mov     rax, [rbx+138h]
0x180003048  mov     rcx, [rax+18h]; Block
0x18000304c  test    rcx, rcx
0x18000304f  jz      short loc_180003061
0x180003051  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003056  mov     rax, [rbx+138h]
0x18000305d  mov     [rax+18h], rbp
0x180003061  mov     rax, [rbx+138h]
0x180003068  mov     rcx, [rax+50h]; Block
0x18000306c  test    rcx, rcx
0x18000306f  jz      short loc_180003081
0x180003071  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003076  mov     rax, [rbx+138h]
0x18000307d  mov     [rax+50h], rbp
0x180003081  mov     rcx, [rbx+138h]; Block
0x180003088  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000308d  mov     [rbx+138h], rbp
0x180003094  lea     rcx, [rbx+640h]; this
0x18000309b  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x1800030a0  lea     rcx, [rbx+3D0h]
0x1800030a7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800030ae  nop     dword ptr [rax+rax+00h]
0x1800030b3  lea     rcx, [rbx+190h]
0x1800030ba  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800030c1  nop     dword ptr [rax+rax+00h]
0x1800030c6  lea     rcx, [rbx+170h]
0x1800030cd  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800030d4  nop     dword ptr [rax+rax+00h]
0x1800030d9  mov     rcx, rdi; this
0x1800030dc  call    ??1ARRAY_LIST@@QEAA@XZ; ARRAY_LIST::~ARRAY_LIST(void)
0x1800030e1  lea     rcx, [rbx+140h]; this
0x1800030e8  call    ??1PROTOCOL_MANAGER_LIST@@QEAA@XZ; PROTOCOL_MANAGER_LIST::~PROTOCOL_MANAGER_LIST(void)
0x1800030ed  lea     rcx, [rbx+80h]
0x1800030f4  add     rsp, 38h
0x1800030f8  pop     rdi
0x1800030f9  pop     rsi
0x1800030fa  pop     rbp
0x1800030fb  pop     rbx
0x1800030fc  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
