# WFDSConMgr::CConnectASPDoQueryWork::~CConnectASPDoQueryWork(void)

- ea: `0x1800591ac`
- end: `0x1800591da`
- name: `??1CConnectASPDoQueryWork@WFDSConMgr@@UEAA@XZ`
- size: `46`
- prototype: `void __fastcall(WFDSConMgr::CConnectASPDoQueryWork *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180059580`

## callees

- `0x18000475c`
- `0x1800591ac`
- `0x180059270`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800591b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800591b9`

## pseudocode

```c
void __fastcall WFDSConMgr::CConnectASPDoQueryWork::~CConnectASPDoQueryWork(WFDSConMgr::CConnectASPDoQueryWork *this)
{
  std::_Ref_count_base *v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 5);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  WFDSConMgr::IConnectSubStateWork::~IConnectSubStateWork(this);
}

```

## disassembly

```asm
0x1800591ac  push    rbx
0x1800591ae  sub     rsp, 20h
0x1800591b2  mov     rbx, rcx
0x1800591b5  add     rcx, 30h ; '0'; lpCriticalSection
0x1800591b9  call    cs:__imp_DeleteCriticalSection
0x1800591bf  mov     rcx, [rbx+28h]; this
0x1800591c3  test    rcx, rcx
0x1800591c6  jz      short loc_1800591CD
0x1800591c8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800591cd  mov     rcx, rbx; this
0x1800591d0  add     rsp, 20h
0x1800591d4  pop     rbx
0x1800591d5  jmp     ??1IConnectSubStateWork@WFDSConMgr@@UEAA@XZ; WFDSConMgr::IConnectSubStateWork::~IConnectSubStateWork(void)
```
