# cxl::tp2::TimerWorkItem::~TimerWorkItem(void)

- ea: `0x1800189e4`
- end: `0x180018a29`
- name: `??1TimerWorkItem@tp2@cxl@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018d60`

## callees

- `0x180018948`
- `0x1800189e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180018a03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180018a03`

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
0x1800189e4  push    rbx
0x1800189e6  sub     rsp, 20h
0x1800189ea  lea     rax, ??_7TimerWorkItem@tp2@cxl@@6B@; const cxl::tp2::TimerWorkItem::`vftable'
0x1800189f1  mov     rbx, rcx
0x1800189f4  mov     [rcx], rax
0x1800189f7  mov     eax, [rcx+18h]
0x1800189fa  cmp     eax, 3
0x1800189fd  jz      short loc_180018A0F
0x1800189ff  mov     rcx, [rcx+38h]; pti
0x180018a03  call    cs:__imp_CloseThreadpoolTimer
0x180018a0a  nop     dword ptr [rax+rax+00h]
0x180018a0f  lea     rcx, [rbx+20h]; this
0x180018a13  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x180018a18  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x180018a1f  mov     [rbx], rax
0x180018a22  add     rsp, 20h
0x180018a26  pop     rbx
0x180018a27  retn
```
