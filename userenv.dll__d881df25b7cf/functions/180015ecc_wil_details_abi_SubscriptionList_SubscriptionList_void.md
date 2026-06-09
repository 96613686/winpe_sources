# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180015ecc`
- end: `0x180015eff`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180015dcc`
- `0x180015dfc`

## callees

- `0x180008940`
- `0x180015ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015ef3`

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
0x180015ecc  push    rbx
0x180015ece  sub     rsp, 20h
0x180015ed2  mov     rbx, rcx
0x180015ed5  mov     rcx, [rcx+40h]
0x180015ed9  mov     qword ptr [rbx+40h], 0
0x180015ee1  test    rcx, rcx
0x180015ee4  jz      short loc_180015EEB
0x180015ee6  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180015eeb  mov     rcx, rbx
0x180015eee  add     rsp, 20h
0x180015ef2  pop     rbx
0x180015ef3  jmp     cs:__imp_DeleteCriticalSection
```
