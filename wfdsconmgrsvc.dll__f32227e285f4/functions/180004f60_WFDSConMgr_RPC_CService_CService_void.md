# WFDSConMgr::RPC::CService::~CService(void)

- ea: `0x180004f60`
- end: `0x180005098`
- name: `??1CService@RPC@WFDSConMgr@@UEAA@XZ`
- size: `312`
- prototype: `void __fastcall(WFDSConMgr::RPC::CService *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x180005350`

## callees

- `0x1800010b8`
- `0x18000475c`
- `0x180004794`
- `0x180004934`
- `0x180004ef4`
- `0x180004f60`
- `0x1800059c0`
- `0x180006740`
- `0x18005cd7c`
- `0x18005d27c`
- `0x18005dca0`
- `0x18005e168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000500f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000500f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000506a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000506a`

## pseudocode

```c
void __fastcall WFDSConMgr::RPC::CService::~CService(WFDSConMgr::RPC::CService *this, bool a2)
{
  __int64 v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  std::_Ref_count_base *v5; // rcx
  std::_Ref_count_base *v6; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &WFDSConMgr::RPC::CService::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, this);
  }
  v3 = *((_QWORD *)this + 31);
  if ( v3 )
  {
    WFDSConMgr::CriticalSection::Lock(v3 + 16, &lpCriticalSection);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, v3);
    }
    v4 = lpCriticalSection;
    *(_QWORD *)(v3 + 56) = 0;
    if ( v4 )
      LeaveCriticalSection(v4);
  }
  WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers((WFDSConMgr::RPC::CService *)((char *)this + 64), a2);
  TraceLoggingUnregister_EventUnregister();
  WppCleanupUm();
  WFDSConMgr::Timer::~Timer((WFDSConMgr::RPC::CService *)((char *)this + 264));
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 32);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  WFDSConMgr::CEventWrapper::~CEventWrapper((void **)this + 30);
  std::unique_ptr<void *,WFDSConMgr::RPC::UnregisterWaitDeleter>::~unique_ptr<void *,WFDSConMgr::RPC::UnregisterWaitDeleter>((_QWORD *)this + 29);
  WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment((WFDSConMgr::RPC::CService *)((char *)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v6 )
    std::_Ref_count_base::_Decwref(v6);
  *(_QWORD *)this = &WFDSConMgr::RPC::IServiceLifetimeManager::`vftable';
}

```

## disassembly

```asm
0x180004f60  mov     [rsp+arg_8], rbx
0x180004f65  mov     [rsp+arg_10], rsi
0x180004f6a  push    rdi
0x180004f6b  sub     rsp, 20h
0x180004f6f  lea     rax, ??_7CService@RPC@WFDSConMgr@@6B@; const WFDSConMgr::RPC::CService::`vftable'
0x180004f76  mov     rbx, rcx
0x180004f79  mov     [rcx], rax
0x180004f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f83  lea     rsi, WPP_GLOBAL_Control
0x180004f8a  cmp     rcx, rsi
0x180004f8d  jz      short loc_180004FB3
0x180004f8f  cmp     byte ptr [rcx+19h], 4
0x180004f93  jb      short loc_180004FB3
0x180004f95  test    byte ptr [rcx+1Ch], 1
0x180004f99  jz      short loc_180004FB3
0x180004f9b  mov     rcx, [rcx+10h]
0x180004f9f  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x180004fa6  mov     edx, 0Bh
0x180004fab  mov     r9, rbx
0x180004fae  call    WPP_SF_q
0x180004fb3  mov     rdi, [rbx+0F8h]
0x180004fba  test    rdi, rdi
0x180004fbd  jz      short loc_180005015
0x180004fbf  lea     rcx, [rdi+10h]
0x180004fc3  lea     rdx, [rsp+28h+lpCriticalSection]
0x180004fc8  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x180004fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fd4  cmp     rcx, rsi
0x180004fd7  jz      short loc_180004FFD
0x180004fd9  cmp     byte ptr [rcx+19h], 4
0x180004fdd  jb      short loc_180004FFD
0x180004fdf  test    byte ptr [rcx+1Ch], 1
0x180004fe3  jz      short loc_180004FFD
0x180004fe5  mov     rcx, [rcx+10h]
0x180004fe9  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x180004ff0  mov     edx, 29h ; ')'
0x180004ff5  mov     r9, rdi
0x180004ff8  call    WPP_SF_q
0x180004ffd  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x180005002  mov     qword ptr [rdi+38h], 0
0x18000500a  test    rcx, rcx
0x18000500d  jz      short loc_180005015
0x18000500f  call    cs:__imp_LeaveCriticalSection
0x180005015  lea     rcx, [rbx+40h]; this
0x180005019  call    ?CleanupGroupMembers@CThreadpoolEnvironment@WFDSConMgr@@QEAAX_N@Z; WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18000501e  call    TraceLoggingUnregister_EventUnregister
0x180005023  call    WppCleanupUm
0x180005028  lea     rcx, [rbx+108h]; this
0x18000502f  call    ??1Timer@WFDSConMgr@@UEAA@XZ; WFDSConMgr::Timer::~Timer(void)
0x180005034  mov     rcx, [rbx+100h]; this
0x18000503b  test    rcx, rcx
0x18000503e  jz      short loc_180005045
0x180005040  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180005045  lea     rcx, [rbx+0F0h]; this
0x18000504c  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x180005051  lea     rcx, [rbx+0E8h]
0x180005058  call    ??1?$unique_ptr@PEAXUUnregisterWaitDeleter@RPC@WFDSConMgr@@@std@@QEAA@XZ; std::unique_ptr<void *,WFDSConMgr::RPC::UnregisterWaitDeleter>::~unique_ptr<void *,WFDSConMgr::RPC::UnregisterWaitDeleter>(void)
0x18000505d  lea     rcx, [rbx+40h]; this
0x180005061  call    ??1CThreadpoolEnvironment@WFDSConMgr@@UEAA@XZ; WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x180005066  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000506a  call    cs:__imp_DeleteCriticalSection
0x180005070  mov     rcx, [rbx+10h]; this
0x180005074  test    rcx, rcx
0x180005077  jz      short loc_18000507E
0x180005079  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000507e  mov     rsi, [rsp+28h+arg_10]
0x180005083  lea     rax, ??_7IServiceLifetimeManager@RPC@WFDSConMgr@@6B@; const WFDSConMgr::RPC::IServiceLifetimeManager::`vftable'
0x18000508a  mov     [rbx], rax
0x18000508d  mov     rbx, [rsp+28h+arg_8]
0x180005092  add     rsp, 20h
0x180005096  pop     rdi
0x180005097  retn
```
