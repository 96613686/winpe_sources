# cxl::tp2::TimerWorkItem::~TimerWorkItem(void)

- ea: `0x18001b140`
- end: `0x18001b17e`
- name: `??1TimerWorkItem@tp2@cxl@@UEAA@XZ`
- size: `62`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b4a0`

## callees

- `0x18001b0a4`
- `0x18001b140`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b15f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b15f`

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
0x18001b140  push    rbx
0x18001b142  sub     rsp, 20h
0x18001b146  lea     rax, ??_7TimerWorkItem@tp2@cxl@@6B@; const cxl::tp2::TimerWorkItem::`vftable'
0x18001b14d  mov     rbx, rcx
0x18001b150  mov     [rcx], rax
0x18001b153  mov     eax, [rcx+18h]
0x18001b156  cmp     eax, 3
0x18001b159  jz      short loc_18001B165
0x18001b15b  mov     rcx, [rcx+38h]; pti
0x18001b15f  call    cs:__imp_CloseThreadpoolTimer
0x18001b165  lea     rcx, [rbx+20h]; this
0x18001b169  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x18001b16e  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001b175  mov     [rbx], rax
0x18001b178  add     rsp, 20h
0x18001b17c  pop     rbx
0x18001b17d  retn
```
