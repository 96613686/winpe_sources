# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000b344`
- end: `0x18000b3a8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b250`

## callees

- `0x18000b344`
- `0x18000b614`
- `0x18000db10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b38a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b38a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b373`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b373`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b381`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b381`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rsi
  HANDLE ProcessHeap; // rax

  wil::details_abi::FeatureStateData::ProcessShutdown((wil::details_abi::FeatureStateData *)this);
  LockSemaphore = this[6].LockSemaphore;
  this[6].LockSemaphore = 0;
  if ( LockSemaphore )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, LockSemaphore);
  }
  DeleteCriticalSection(this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)&this->LockCount);
}

```

## disassembly

```asm
0x18000b344  mov     [rsp+arg_0], rbx
0x18000b349  mov     [rsp+arg_8], rsi
0x18000b34e  push    rdi
0x18000b34f  sub     rsp, 20h
0x18000b353  mov     rbx, rcx
0x18000b356  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x18000b35b  lea     rdi, [rbx+0C8h]
0x18000b362  mov     rsi, [rdi+40h]
0x18000b366  mov     qword ptr [rdi+40h], 0
0x18000b36e  test    rsi, rsi
0x18000b371  jz      short loc_18000B387
0x18000b373  call    cs:__imp_GetProcessHeap
0x18000b379  mov     r8, rsi; lpMem
0x18000b37c  xor     edx, edx; dwFlags
0x18000b37e  mov     rcx, rax; hHeap
0x18000b381  call    cs:__imp_HeapFree
0x18000b387  mov     rcx, rdi; lpCriticalSection
0x18000b38a  call    cs:__imp_DeleteCriticalSection
0x18000b390  lea     rcx, [rbx+8]; this
0x18000b394  mov     rbx, [rsp+28h+arg_0]
0x18000b399  mov     rsi, [rsp+28h+arg_8]
0x18000b39e  add     rsp, 20h
0x18000b3a2  pop     rdi
0x18000b3a3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
