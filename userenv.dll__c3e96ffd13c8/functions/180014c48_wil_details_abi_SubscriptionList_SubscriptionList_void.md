# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180014c48`
- end: `0x180014c76`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014b4c`
- `0x180014b7c`

## callees

- `0x1800078a0`
- `0x180014c48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014c6f`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180014c48  push    rbx
0x180014c4a  sub     rsp, 20h
0x180014c4e  mov     rbx, rcx
0x180014c51  mov     rcx, [rcx+40h]
0x180014c55  mov     qword ptr [rbx+40h], 0
0x180014c5d  test    rcx, rcx
0x180014c60  jz      short loc_180014C67
0x180014c62  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180014c67  mov     rcx, rbx
0x180014c6a  add     rsp, 20h
0x180014c6e  pop     rbx
0x180014c6f  jmp     cs:__imp_DeleteCriticalSection
```
