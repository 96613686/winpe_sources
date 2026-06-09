# CVdsService::~CVdsService(void)

- ea: `0x140036f88`
- end: `0x14003703b`
- name: `??1CVdsService@@QEAA@XZ`
- size: `179`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002fefc`
- `0x140053d90`

## callees

- `0x14001ad0c`
- `0x140036f88`
- `0x14003bbec`
- `0x14003d538`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140036ffd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140036ffd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140036fb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140036fb9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140036fcd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140036fcd`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x140036fef`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x140036fef`
- `vdsutil!??1CRtlMap@@UEAA@XZ` at `0x140037017`
- `vdsutil!??1CRtlMap@@UEAA@XZ` at `0x140037021`
- `vdsutil!??1CRtlMap@@UEAA@XZ` at `0x140037017`
- `vdsutil!??1CRtlMap@@UEAA@XZ` at `0x140037021`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140036fab`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140036fab`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037009`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037009`

## string_xrefs

- `0x140036f9a`: `CVdsService::~CVdsService()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsService::~CVdsService(struct _RTL_CRITICAL_SECTION *this)
{
  _BYTE v2[40]; // [rsp+20h] [rbp-28h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v2, 0x5Eu, "CVdsService::~CVdsService()");
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( LODWORD(this[4].DebugInfo) == 1 )
    DeleteCriticalSection(this + 3);
  CVdsService::UnregisterServiceInstance((struct CVdsService *)this);
  CVdsService::RemoveAllFSPropertiesFromMap((CVdsService *)this);
  CRtlMap::RemoveAll((CRtlMap *)&this[4].LockCount, 0);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v2);
  CRtlMap::~CRtlMap((CRtlMap *)&this[7].LockSemaphore);
  CRtlMap::~CRtlMap((CRtlMap *)&this[4].LockCount);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((__int64)&this[1].LockSemaphore);
}

```

## disassembly

```asm
0x140036f88  mov     [rsp+arg_8], rbx
0x140036f8d  mov     [rsp+arg_0], rcx
0x140036f92  push    rdi
0x140036f93  sub     rsp, 40h
0x140036f97  mov     rdi, rcx
0x140036f9a  lea     r8, aCvdsserviceCvd_0; "CVdsService::~CVdsService()"
0x140036fa1  mov     edx, 5Eh ; '^'
0x140036fa6  lea     rcx, [rsp+48h+var_28]
0x140036fab  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140036fb1  nop
0x140036fb2  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140036fb9  call    cs:__imp_EnterCriticalSection
0x140036fbf  nop
0x140036fc0  cmp     dword ptr [rdi+0A0h], 1
0x140036fc7  jnz     short loc_140036FD3
0x140036fc9  lea     rcx, [rdi+78h]; lpCriticalSection
0x140036fcd  call    cs:__imp_DeleteCriticalSection
0x140036fd3  mov     rcx, rdi; struct CVdsService *
0x140036fd6  call    ?UnregisterServiceInstance@CVdsService@@CAXPEAV1@@Z; CVdsService::UnregisterServiceInstance(CVdsService *)
0x140036fdb  mov     rcx, rdi; this
0x140036fde  call    ?RemoveAllFSPropertiesFromMap@CVdsService@@QEAAXXZ; CVdsService::RemoveAllFSPropertiesFromMap(void)
0x140036fe3  lea     rbx, [rdi+0A8h]
0x140036fea  xor     edx, edx
0x140036fec  mov     rcx, rbx
0x140036fef  call    cs:__imp_?RemoveAll@CRtlMap@@QEAAXH@Z; CRtlMap::RemoveAll(int)
0x140036ff5  nop
0x140036ff6  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140036ffd  call    cs:__imp_LeaveCriticalSection
0x140037003  nop
0x140037004  lea     rcx, [rsp+48h+var_28]
0x140037009  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003700f  nop
0x140037010  lea     rcx, [rdi+130h]
0x140037017  call    cs:__imp_??1CRtlMap@@UEAA@XZ; CRtlMap::~CRtlMap(void)
0x14003701d  nop
0x14003701e  mov     rcx, rbx
0x140037021  call    cs:__imp_??1CRtlMap@@UEAA@XZ; CRtlMap::~CRtlMap(void)
0x140037027  nop
0x140037028  lea     rcx, [rdi+40h]
0x14003702c  mov     rbx, [rsp+48h+arg_8]
0x140037031  add     rsp, 40h
0x140037035  pop     rdi
0x140037036  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
