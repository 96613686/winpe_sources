# WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::~CMaUsbNotificationWaiter(void)

- ea: `0x18004c908`
- end: `0x18004c954`
- name: `??1CMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@UEAA@XZ`
- size: `76`
- prototype: `void __fastcall(WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter *this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004c960`

## callees

- `0x18000475c`
- `0x18004c908`
- `0x18005ce24`
- `0x18005d09c`
- `0x18005dca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c941`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c941`

## pseudocode

```c
void __fastcall WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::~CMaUsbNotificationWaiter(
        WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter *this,
        bool a2)
{
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::`vftable';
  WFDSConMgr::SingleObjectWaiter::Cancel(this, a2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 30);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  WFDSConMgr::CEventWrapper::~CEventWrapper((void **)this + 20);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  WFDSConMgr::SingleObjectWaiter::~SingleObjectWaiter(this);
}

```

## disassembly

```asm
0x18004c908  push    rbx
0x18004c90a  sub     rsp, 20h
0x18004c90e  lea     rax, ??_7CMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@6B@; const WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::`vftable'
0x18004c915  mov     rbx, rcx
0x18004c918  mov     [rcx], rax
0x18004c91b  call    ?Cancel@SingleObjectWaiter@WFDSConMgr@@QEAAX_N@Z; WFDSConMgr::SingleObjectWaiter::Cancel(bool)
0x18004c920  mov     rcx, [rbx+0F0h]; this
0x18004c927  test    rcx, rcx
0x18004c92a  jz      short loc_18004C931
0x18004c92c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c931  lea     rcx, [rbx+0A0h]; this
0x18004c938  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x18004c93d  lea     rcx, [rbx+70h]; lpCriticalSection
0x18004c941  call    cs:__imp_DeleteCriticalSection
0x18004c947  mov     rcx, rbx; this
0x18004c94a  add     rsp, 20h
0x18004c94e  pop     rbx
0x18004c94f  jmp     ??1SingleObjectWaiter@WFDSConMgr@@UEAA@XZ; WFDSConMgr::SingleObjectWaiter::~SingleObjectWaiter(void)
```
