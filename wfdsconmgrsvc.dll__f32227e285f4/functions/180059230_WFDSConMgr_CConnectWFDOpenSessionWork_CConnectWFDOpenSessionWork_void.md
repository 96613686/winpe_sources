# WFDSConMgr::CConnectWFDOpenSessionWork::~CConnectWFDOpenSessionWork(void)

- ea: `0x180059230`
- end: `0x180059267`
- name: `??1CConnectWFDOpenSessionWork@WFDSConMgr@@UEAA@XZ`
- size: `55`
- prototype: `void __fastcall(WFDSConMgr::CConnectWFDOpenSessionWork *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180059640`

## callees

- `0x18000475c`
- `0x180059230`
- `0x180059270`
- `0x18005dca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180059246`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180059246`

## pseudocode

```c
void __fastcall WFDSConMgr::CConnectWFDOpenSessionWork::~CConnectWFDOpenSessionWork(
        WFDSConMgr::CConnectWFDOpenSessionWork *this)
{
  std::_Ref_count_base *v2; // rcx

  WFDSConMgr::CEventWrapper::~CEventWrapper((WFDSConMgr::CConnectWFDOpenSessionWork *)((char *)this + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 5);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  WFDSConMgr::IConnectSubStateWork::~IConnectSubStateWork(this);
}

```

## disassembly

```asm
0x180059230  push    rbx
0x180059232  sub     rsp, 20h
0x180059236  mov     rbx, rcx
0x180059239  add     rcx, 60h ; '`'; this
0x18005923d  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x180059242  lea     rcx, [rbx+30h]; lpCriticalSection
0x180059246  call    cs:__imp_DeleteCriticalSection
0x18005924c  mov     rcx, [rbx+28h]; this
0x180059250  test    rcx, rcx
0x180059253  jz      short loc_18005925A
0x180059255  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005925a  mov     rcx, rbx; this
0x18005925d  add     rsp, 20h
0x180059261  pop     rbx
0x180059262  jmp     ??1IConnectSubStateWork@WFDSConMgr@@UEAA@XZ; WFDSConMgr::IConnectSubStateWork::~IConnectSubStateWork(void)
```
