# W3WP_HOST::~W3WP_HOST(void)

- ea: `0x180002c20`
- end: `0x180002f3d`
- name: `??1W3WP_HOST@@QEAA@XZ`
- size: `797`
- prototype: `void __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002fb0`

## callees

- `0x180001be0`
- `0x180001fa8`
- `0x180002bb4`
- `0x180002bfc`
- `0x180002c20`
- `0x180002f44`
- `0x180002fd8`
- `0x18000381c`
- `0x180003b30`
- `0x18000840c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002d4b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002d4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d82`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180002f0d`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180002f0d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002ef3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002f00`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002ef3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002f00`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002f36`
- `nativerd!TerminateNativeConfiguration` at `0x180002db5`
- `nativerd!TerminateNativeConfiguration` at `0x180002db5`

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
0x180002c20  push    rbx
0x180002c22  push    rbp
0x180002c23  push    rsi
0x180002c24  push    rdi
0x180002c25  sub     rsp, 38h
0x180002c29  mov     dword ptr [rcx+48h], 58683377h
0x180002c30  lea     rax, ??_7W3WP_HOST@@6BIWorkerProcessFramework@@@; const W3WP_HOST::`vftable'{for `IWorkerProcessFramework'}
0x180002c37  mov     [rcx], rax
0x180002c3a  mov     rbx, rcx
0x180002c3d  lea     rax, ??_7W3WP_HOST@@6BIWpfApplicationInfoUtil@@@; const W3WP_HOST::`vftable'{for `IWpfApplicationInfoUtil'}
0x180002c44  xor     r9d, r9d
0x180002c47  mov     [rcx+8], rax
0x180002c4b  xor     edx, edx
0x180002c4d  lea     rax, ??_7W3WP_HOST@@6BIWpfSettings@@@; const W3WP_HOST::`vftable'{for `IWpfSettings'}
0x180002c54  mov     [rcx+10h], rax
0x180002c58  lea     rax, ??_7W3WP_HOST@@6BIWpfActions@@@; const W3WP_HOST::`vftable'{for `IWpfActions'}
0x180002c5f  mov     [rcx+18h], rax
0x180002c63  lea     r8d, [r9+3]
0x180002c67  lea     rax, ??_7W3WP_HOST@@6BIWpfExposeProtocolManagerCustomInterface@@@; const W3WP_HOST::`vftable'{for `IWpfExposeProtocolManagerCustomInterface'}
0x180002c6e  mov     [rcx+20h], rax
0x180002c72  lea     rax, ??_7W3WP_HOST@@6BIIisCoreReportCounters@@@; const W3WP_HOST::`vftable'{for `IIisCoreReportCounters'}
0x180002c79  mov     [rcx+28h], rax
0x180002c7d  lea     rax, ??_7W3WP_HOST@@6BIWPInstanceCountersManager@@@; const W3WP_HOST::`vftable'{for `IWPInstanceCountersManager'}
0x180002c84  mov     [rcx+30h], rax
0x180002c88  lea     rax, ??_7W3WP_HOST@@6BIWpfApplicationPreloadUtil@@@; const W3WP_HOST::`vftable'{for `IWpfApplicationPreloadUtil'}
0x180002c8f  mov     [rcx+38h], rax
0x180002c93  lea     rax, ??_7W3WP_HOST@@6BIWPInstanceSendData@@@; const W3WP_HOST::`vftable'{for `IWPInstanceSendData'}
0x180002c9a  mov     [rcx+40h], rax
0x180002c9e  mov     rcx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180002ca5  add     rcx, 30h ; '0'
0x180002ca9  mov     rax, [rcx]
0x180002cac  mov     rax, [rax+20h]
0x180002cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb5  mov     rcx, [rbx+60h]; this
0x180002cb9  xor     ebp, ebp
0x180002cbb  test    rcx, rcx
0x180002cbe  jz      short loc_180002CC9
0x180002cc0  call    ??_GWP_IDLE_TIMER@@QEAAPEAXI@Z; WP_IDLE_TIMER::`scalar deleting destructor'(uint)
0x180002cc5  mov     [rbx+60h], rbp
0x180002cc9  mov     rcx, [rbx+58h]; this
0x180002ccd  test    rcx, rcx
0x180002cd0  jz      short loc_180002CE4
0x180002cd2  call    ?Terminate@WP_IPM@@QEAAJXZ; WP_IPM::Terminate(void)
0x180002cd7  mov     rcx, [rbx+58h]; Block
0x180002cdb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ce0  mov     [rbx+58h], rbp
0x180002ce4  mov     rcx, [rbx+628h]
0x180002ceb  test    rcx, rcx
0x180002cee  jz      short loc_180002D03
0x180002cf0  mov     rax, [rcx]
0x180002cf3  mov     rax, [rax+10h]
0x180002cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cfc  mov     [rbx+628h], rbp
0x180002d03  mov     rdi, [rbx+68h]
0x180002d07  test    rdi, rdi
0x180002d0a  jz      short loc_180002D20
0x180002d0c  mov     rcx, rdi; lpCriticalSection
0x180002d0f  call    ??1WP_RECYCLER@@QEAA@XZ; WP_RECYCLER::~WP_RECYCLER(void)
0x180002d14  mov     rcx, rdi; Block
0x180002d17  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d1c  mov     [rbx+68h], rbp
0x180002d20  mov     rcx, [rbx+130h]
0x180002d27  test    rcx, rcx
0x180002d2a  jz      short loc_180002D3F
0x180002d2c  mov     rax, [rcx]
0x180002d2f  mov     rax, [rax+10h]
0x180002d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d38  mov     [rbx+130h], rbp
0x180002d3f  mov     rcx, [rbx+620h]; hLibModule
0x180002d46  test    rcx, rcx
0x180002d49  jz      short loc_180002D58
0x180002d4b  call    cs:__imp_FreeLibrary
0x180002d51  mov     [rbx+620h], rbp
0x180002d58  cmp     [rbx+0C8h], ebp
0x180002d5e  jz      short loc_180002D73
0x180002d60  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x180002d67  call    cs:__imp_DeleteCriticalSection
0x180002d6d  mov     [rbx+0C8h], ebp
0x180002d73  cmp     [rbx+0F8h], ebp
0x180002d79  jz      short loc_180002D8E
0x180002d7b  lea     rcx, [rbx+100h]; lpCriticalSection
0x180002d82  call    cs:__imp_DeleteCriticalSection
0x180002d88  mov     [rbx+0F8h], ebp
0x180002d8e  mov     rcx, [rbx+0C0h]
0x180002d95  test    rcx, rcx
0x180002d98  jz      short loc_180002DAD
0x180002d9a  mov     rax, [rcx]
0x180002d9d  mov     rax, [rax+10h]
0x180002da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da6  mov     [rbx+0C0h], rbp
0x180002dad  cmp     [rbx+0B8h], ebp
0x180002db3  jz      short loc_180002DC1
0x180002db5  call    cs:__imp_?TerminateNativeConfiguration@@YAXXZ; TerminateNativeConfiguration(void)
0x180002dbb  mov     [rbx+0B8h], ebp
0x180002dc1  xor     edx, edx; unsigned int
0x180002dc3  lea     rcx, [rbx+30h]; this
0x180002dc7  call    ?DeleteCounterSetInstance@W3WP_HOST@@UEAAJK@Z; W3WP_HOST::DeleteCounterSetInstance(ulong)
0x180002dcc  lea     rdi, [rbx+158h]
0x180002dd3  mov     rcx, rdi; this
0x180002dd6  call    ?Clear@ARRAY_LIST@@QEAAXXZ; ARRAY_LIST::Clear(void)
0x180002ddb  mov     rax, [rbx+138h]
0x180002de2  cmp     [rax+58h], ebp
0x180002de5  jz      loc_180002EE0
0x180002deb  test    rax, rax
0x180002dee  jz      loc_180002EE0
0x180002df4  mov     rcx, [rax+28h]; Block
0x180002df8  test    rcx, rcx
0x180002dfb  jz      short loc_180002E0D
0x180002dfd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e02  mov     rax, [rbx+138h]
0x180002e09  mov     [rax+28h], rbp
0x180002e0d  mov     rax, [rbx+138h]
0x180002e14  mov     rcx, [rax+68h]; Block
0x180002e18  test    rcx, rcx
0x180002e1b  jz      short loc_180002E2D
0x180002e1d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e22  mov     rax, [rbx+138h]
0x180002e29  mov     [rax+68h], rbp
0x180002e2d  mov     rax, [rbx+138h]
0x180002e34  mov     rcx, [rax+30h]; Block
0x180002e38  test    rcx, rcx
0x180002e3b  jz      short loc_180002E4D
0x180002e3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e42  mov     rax, [rbx+138h]
0x180002e49  mov     [rax+30h], rbp
0x180002e4d  mov     rax, [rbx+138h]
0x180002e54  mov     rcx, [rax+40h]; Block
0x180002e58  test    rcx, rcx
0x180002e5b  jz      short loc_180002E6D
0x180002e5d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e62  mov     rax, [rbx+138h]
0x180002e69  mov     [rax+40h], rbp
0x180002e6d  mov     rax, [rbx+138h]
0x180002e74  mov     rcx, [rax+48h]; Block
0x180002e78  test    rcx, rcx
0x180002e7b  jz      short loc_180002E8D
0x180002e7d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e82  mov     rax, [rbx+138h]
0x180002e89  mov     [rax+48h], rbp
0x180002e8d  mov     rax, [rbx+138h]
0x180002e94  mov     rcx, [rax+18h]; Block
0x180002e98  test    rcx, rcx
0x180002e9b  jz      short loc_180002EAD
0x180002e9d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ea2  mov     rax, [rbx+138h]
0x180002ea9  mov     [rax+18h], rbp
0x180002ead  mov     rax, [rbx+138h]
0x180002eb4  mov     rcx, [rax+50h]; Block
0x180002eb8  test    rcx, rcx
0x180002ebb  jz      short loc_180002ECD
0x180002ebd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ec2  mov     rax, [rbx+138h]
0x180002ec9  mov     [rax+50h], rbp
0x180002ecd  mov     rcx, [rbx+138h]; Block
0x180002ed4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ed9  mov     [rbx+138h], rbp
0x180002ee0  lea     rcx, [rbx+640h]; this
0x180002ee7  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x180002eec  lea     rcx, [rbx+3D0h]
0x180002ef3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002ef9  lea     rcx, [rbx+190h]
0x180002f00  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002f06  lea     rcx, [rbx+170h]
0x180002f0d  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180002f13  mov     rcx, rdi; this
0x180002f16  call    ??1ARRAY_LIST@@QEAA@XZ; ARRAY_LIST::~ARRAY_LIST(void)
0x180002f1b  lea     rcx, [rbx+140h]; this
0x180002f22  call    ??1PROTOCOL_MANAGER_LIST@@QEAA@XZ; PROTOCOL_MANAGER_LIST::~PROTOCOL_MANAGER_LIST(void)
0x180002f27  lea     rcx, [rbx+80h]
0x180002f2e  add     rsp, 38h
0x180002f32  pop     rdi
0x180002f33  pop     rsi
0x180002f34  pop     rbp
0x180002f35  pop     rbx
0x180002f36  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
