# UnifiedStoreRundownProtection::~UnifiedStoreRundownProtection(void)

- ea: `0x18002535c`
- end: `0x1800253ba`
- name: `??1UnifiedStoreRundownProtection@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(UnifiedStoreRundownProtection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002531c`

## callees

- `0x1800252a0`
- `0x18002535c`
- `0x180025720`
- `0x180028dec`
- `0x18002993c`
- `0x18002995c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025379`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002538c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025379`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002538c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800253b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800253b2`

## pseudocode

```c
void __fastcall UnifiedStoreRundownProtection::~UnifiedStoreRundownProtection(UnifiedStoreRundownProtection *this)
{
  struct _TP_TIMER *v2; // rcx

  UnifiedStoreRundownProtection::StopTerminationTimer(this);
  UnifiedStoreRundownProtection::_HandleClientRundown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 15);
  if ( v2 )
    CloseThreadpoolTimer(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 72);
  tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>::_Delete((char *)this + 64);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 8);
}

```

## disassembly

```asm
0x18002535c  push    rbx
0x18002535e  sub     rsp, 20h
0x180025362  mov     rbx, rcx
0x180025365  call    ?StopTerminationTimer@UnifiedStoreRundownProtection@@UEAAJXZ; UnifiedStoreRundownProtection::StopTerminationTimer(void)
0x18002536a  mov     rcx, rbx; this
0x18002536d  call    ?_HandleClientRundown@UnifiedStoreRundownProtection@@AEAAXXZ; UnifiedStoreRundownProtection::_HandleClientRundown(void)
0x180025372  lea     rcx, [rbx+80h]; lpCriticalSection
0x180025379  call    cs:__imp_DeleteCriticalSection
0x18002537f  mov     rcx, [rbx+78h]; pti
0x180025383  test    rcx, rcx
0x180025386  jnz     short loc_1800253B2
0x180025388  lea     rcx, [rbx+50h]; lpCriticalSection
0x18002538c  call    cs:__imp_DeleteCriticalSection
0x180025392  lea     rcx, [rbx+48h]
0x180025396  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18002539b  lea     rcx, [rbx+40h]
0x18002539f  call    ?_Delete@?$auto_xxx@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>::_Delete(void)
0x1800253a4  lea     rcx, [rbx+8]
0x1800253a8  add     rsp, 20h
0x1800253ac  pop     rbx
0x1800253ad  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x1800253b2  call    cs:__imp_CloseThreadpoolTimer
0x1800253b8  jmp     short loc_180025388
```
