# WFDSConMgr::CQueryStateWork::~CQueryStateWork(void)

- ea: `0x1800547ac`
- end: `0x1800547e4`
- name: `??1CQueryStateWork@WFDSConMgr@@UEAA@XZ`
- size: `56`
- prototype: `void __fastcall(WFDSConMgr::CQueryStateWork *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180054bf0`

## callees

- `0x18000475c`
- `0x18003cf08`
- `0x1800547ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800547b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800547b9`

## pseudocode

```c
void __fastcall WFDSConMgr::CQueryStateWork::~CQueryStateWork(WFDSConMgr::CQueryStateWork *this)
{
  std::_Ref_count_base *v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 7);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  *(_QWORD *)this = &WFDSConMgr::CSessionWorkErrorHandler::`vftable';
  WFDSConMgr::ISessionWork::~ISessionWork(this);
}

```

## disassembly

```asm
0x1800547ac  push    rbx
0x1800547ae  sub     rsp, 20h
0x1800547b2  mov     rbx, rcx
0x1800547b5  add     rcx, 40h ; '@'; lpCriticalSection
0x1800547b9  call    cs:__imp_DeleteCriticalSection
0x1800547bf  mov     rcx, [rbx+38h]; this
0x1800547c3  test    rcx, rcx
0x1800547c6  jz      short loc_1800547CD
0x1800547c8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800547cd  lea     rax, ??_7CSessionWorkErrorHandler@WFDSConMgr@@6B@; const WFDSConMgr::CSessionWorkErrorHandler::`vftable'
0x1800547d4  mov     rcx, rbx; this
0x1800547d7  mov     [rbx], rax
0x1800547da  add     rsp, 20h
0x1800547de  pop     rbx
0x1800547df  jmp     ??1ISessionWork@WFDSConMgr@@UEAA@XZ; WFDSConMgr::ISessionWork::~ISessionWork(void)
```
