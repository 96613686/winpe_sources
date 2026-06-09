# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18001867c`
- end: `0x1800186a8`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800185b0`
- `0x18001d880`
- `0x180031077`
- `0x1800310a6`
- `0x180031369`
- `0x180031398`
- `0x180031c80`
- `0x180031f7c`

## callees

- `0x180018704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001869b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001869b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(LPCRITICAL_SECTION lpCriticalSection)
{
  wil::details_abi::heap_buffer::~heap_buffer((wil::details_abi::heap_buffer *)&lpCriticalSection[1]);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18001867c  mov     [rsp+arg_0], rcx
0x180018681  push    rbx
0x180018682  sub     rsp, 20h
0x180018686  mov     rbx, rcx
0x180018689  add     rcx, 28h ; '('; this
0x18001868d  mov     [rsp+28h+arg_8], rcx
0x180018692  call    ??1heap_buffer@details_abi@wil@@QEAA@XZ; wil::details_abi::heap_buffer::~heap_buffer(void)
0x180018697  nop
0x180018698  mov     rcx, rbx; lpCriticalSection
0x18001869b  call    cs:__imp_DeleteCriticalSection
0x1800186a1  nop
0x1800186a2  add     rsp, 20h
0x1800186a6  pop     rbx
0x1800186a7  retn
```
