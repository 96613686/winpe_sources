# CWcnThreadpoolSession::~CWcnThreadpoolSession(void)

- ea: `0x1800566cc`
- end: `0x180056740`
- name: `??1CWcnThreadpoolSession@@UEAA@XZ`
- size: `116`
- prototype: `void __fastcall(CWcnThreadpoolSession *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180056750`

## callees

- `0x1800566cc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800566f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800566f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180056702`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180056711`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180056702`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180056711`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWcnThreadpoolSession::~CWcnThreadpoolSession(CWcnThreadpoolSession *this)
{
  struct _TP_WORK *v2; // rcx
  struct _TP_WORK *v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &CWcnThreadpoolSession::`vftable'{for `IWcnTransportSession'};
  *((_QWORD *)this + 4) = &CWcnThreadpoolSession::`vftable'{for `IWcnThreadpoolSessionCallback'};
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 9));
  }
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 10);
  if ( v3 )
    CloseThreadpoolWork(v3);
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 7);
  if ( v4 )
    (**v4)(v4, 1);
  *(_QWORD *)this = &IWcnTransportSession::`vftable';
}

```

## disassembly

```asm
0x1800566cc  push    rbx
0x1800566ce  sub     rsp, 20h
0x1800566d2  lea     rax, ??_7CWcnThreadpoolSession@@6BIWcnTransportSession@@@; const CWcnThreadpoolSession::`vftable'{for `IWcnTransportSession'}
0x1800566d9  mov     rbx, rcx
0x1800566dc  mov     [rcx], rax
0x1800566df  lea     rax, ??_7CWcnThreadpoolSession@@6BIWcnThreadpoolSessionCallback@@@; const CWcnThreadpoolSession::`vftable'{for `IWcnThreadpoolSessionCallback'}
0x1800566e6  mov     [rcx+20h], rax
0x1800566ea  mov     rcx, [rcx+48h]; pwk
0x1800566ee  test    rcx, rcx
0x1800566f1  jz      short loc_180056708
0x1800566f3  mov     edx, 1; fCancelPendingCallbacks
0x1800566f8  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800566fe  mov     rcx, [rbx+48h]; pwk
0x180056702  call    cs:__imp_CloseThreadpoolWork
0x180056708  mov     rcx, [rbx+50h]; pwk
0x18005670c  test    rcx, rcx
0x18005670f  jz      short loc_180056717
0x180056711  call    cs:__imp_CloseThreadpoolWork
0x180056717  mov     rcx, [rbx+38h]
0x18005671b  test    rcx, rcx
0x18005671e  jz      short loc_180056730
0x180056720  mov     rax, [rcx]
0x180056723  mov     edx, 1
0x180056728  mov     rax, [rax]
0x18005672b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056730  lea     rax, ??_7IWcnTransportSession@@6B@; const IWcnTransportSession::`vftable'
0x180056737  mov     [rbx], rax
0x18005673a  add     rsp, 20h
0x18005673e  pop     rbx
0x18005673f  retn
```
