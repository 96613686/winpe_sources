# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800283ec`
- end: `0x180028421`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800282cc`
- `0x180035f94`

## callees

- `0x1800283ec`
- `0x1800369d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002840e`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  wil::details *LockSemaphore; // rcx

  LockSemaphore = (wil::details *)this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    wil::details::FreeProcessHeap(LockSemaphore, a2);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800283ec  push    rbx
0x1800283ee  sub     rsp, 20h
0x1800283f2  mov     rbx, rcx
0x1800283f5  mov     rcx, [rcx+40h]; this
0x1800283f9  mov     qword ptr [rbx+40h], 0
0x180028401  test    rcx, rcx
0x180028404  jnz     short loc_18002841A
0x180028406  mov     rcx, rbx
0x180028409  add     rsp, 20h
0x18002840d  pop     rbx
0x18002840e  jmp     cs:__imp_DeleteCriticalSection
0x18002841a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002841f  jmp     short loc_180028406
```
