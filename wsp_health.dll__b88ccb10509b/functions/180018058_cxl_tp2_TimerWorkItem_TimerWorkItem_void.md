# cxl::tp2::TimerWorkItem::~TimerWorkItem(void)

- ea: `0x180018058`
- end: `0x180018096`
- name: `??1TimerWorkItem@tp2@cxl@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800183c0`

## callees

- `0x180017fbc`
- `0x180018058`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180018077`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180018077`

## pseudocode

```c
void __fastcall cxl::tp2::TimerWorkItem::~TimerWorkItem(PTP_TIMER *this)
{
  *this = (PTP_TIMER)&cxl::tp2::TimerWorkItem::`vftable';
  if ( *((_DWORD *)this + 6) != 3 )
    CloseThreadpoolTimer(this[7]);
  cxl::detail::DelegateBase::~DelegateBase((cxl::detail::DelegateBase *)(this + 4));
  *this = (PTP_TIMER)&cxl::RefCounted::`vftable';
}

```

## disassembly

```asm
0x180018058  push    rbx
0x18001805a  sub     rsp, 20h
0x18001805e  lea     rax, ??_7TimerWorkItem@tp2@cxl@@6B@; const cxl::tp2::TimerWorkItem::`vftable'
0x180018065  mov     rbx, rcx
0x180018068  mov     [rcx], rax
0x18001806b  mov     eax, [rcx+18h]
0x18001806e  cmp     eax, 3
0x180018071  jz      short loc_18001807D
0x180018073  mov     rcx, [rcx+38h]; pti
0x180018077  call    cs:__imp_CloseThreadpoolTimer
0x18001807d  lea     rcx, [rbx+20h]; this
0x180018081  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x180018086  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001808d  mov     [rbx], rax
0x180018090  add     rsp, 20h
0x180018094  pop     rbx
0x180018095  retn
```
