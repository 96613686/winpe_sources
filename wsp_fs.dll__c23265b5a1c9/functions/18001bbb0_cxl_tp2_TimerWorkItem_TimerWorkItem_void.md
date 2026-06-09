# cxl::tp2::TimerWorkItem::~TimerWorkItem(void)

- ea: `0x18001bbb0`
- end: `0x18001bbf5`
- name: `??1TimerWorkItem@tp2@cxl@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(cxl::tp2::TimerWorkItem *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bf30`

## callees

- `0x18001bb14`
- `0x18001bbb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bbcf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bbcf`

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
0x18001bbb0  push    rbx
0x18001bbb2  sub     rsp, 20h
0x18001bbb6  lea     rax, ??_7TimerWorkItem@tp2@cxl@@6B@; const cxl::tp2::TimerWorkItem::`vftable'
0x18001bbbd  mov     rbx, rcx
0x18001bbc0  mov     [rcx], rax
0x18001bbc3  mov     eax, [rcx+18h]
0x18001bbc6  cmp     eax, 3
0x18001bbc9  jz      short loc_18001BBDB
0x18001bbcb  mov     rcx, [rcx+38h]; pti
0x18001bbcf  call    cs:__imp_CloseThreadpoolTimer
0x18001bbd6  nop     dword ptr [rax+rax+00h]
0x18001bbdb  lea     rcx, [rbx+20h]; this
0x18001bbdf  call    ??1DelegateBase@detail@cxl@@QEAA@XZ; cxl::detail::DelegateBase::~DelegateBase(void)
0x18001bbe4  lea     rax, ??_7RefCounted@cxl@@6B@; const cxl::RefCounted::`vftable'
0x18001bbeb  mov     [rbx], rax
0x18001bbee  add     rsp, 20h
0x18001bbf2  pop     rbx
0x18001bbf3  retn
```
