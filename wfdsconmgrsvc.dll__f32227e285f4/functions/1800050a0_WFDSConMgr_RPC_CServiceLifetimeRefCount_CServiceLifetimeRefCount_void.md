# WFDSConMgr::RPC::CServiceLifetimeRefCount::~CServiceLifetimeRefCount(void)

- ea: `0x1800050a0`
- end: `0x1800050c7`
- name: `??1CServiceLifetimeRefCount@RPC@WFDSConMgr@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(WFDSConMgr::RPC::CServiceLifetimeRefCount *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006610`

## callees

- `0x180004794`
- `0x1800050a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800050ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800050ad`

## pseudocode

```c
void __fastcall WFDSConMgr::RPC::CServiceLifetimeRefCount::~CServiceLifetimeRefCount(
        WFDSConMgr::RPC::CServiceLifetimeRefCount *this)
{
  std::_Ref_count_base *v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
  if ( v2 )
    std::_Ref_count_base::_Decwref(v2);
}

```

## disassembly

```asm
0x1800050a0  push    rbx
0x1800050a2  sub     rsp, 20h
0x1800050a6  mov     rbx, rcx
0x1800050a9  add     rcx, 10h; lpCriticalSection
0x1800050ad  call    cs:__imp_DeleteCriticalSection
0x1800050b3  mov     rcx, [rbx+8]; this
0x1800050b7  test    rcx, rcx
0x1800050ba  jz      short loc_1800050C1
0x1800050bc  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800050c1  add     rsp, 20h
0x1800050c5  pop     rbx
0x1800050c6  retn
```
