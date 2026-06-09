# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800060ec`
- end: `0x180006150`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005f24`

## callees

- `0x1800060ec`
- `0x1800064e4`
- `0x180008b90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006132`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006132`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006129`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006129`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000611b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000611b`

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
0x1800060ec  mov     [rsp+arg_0], rbx
0x1800060f1  mov     [rsp+arg_8], rsi
0x1800060f6  push    rdi
0x1800060f7  sub     rsp, 20h
0x1800060fb  mov     rbx, rcx
0x1800060fe  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x180006103  lea     rdi, [rbx+0C8h]
0x18000610a  mov     rsi, [rdi+40h]
0x18000610e  mov     qword ptr [rdi+40h], 0
0x180006116  test    rsi, rsi
0x180006119  jz      short loc_18000612F
0x18000611b  call    cs:__imp_GetProcessHeap
0x180006121  mov     rcx, rax; hHeap
0x180006124  mov     r8, rsi; lpMem
0x180006127  xor     edx, edx; dwFlags
0x180006129  call    cs:__imp_HeapFree
0x18000612f  mov     rcx, rdi; lpCriticalSection
0x180006132  call    cs:__imp_DeleteCriticalSection
0x180006138  lea     rcx, [rbx+8]; this
0x18000613c  mov     rbx, [rsp+28h+arg_0]
0x180006141  mov     rsi, [rsp+28h+arg_8]
0x180006146  add     rsp, 20h
0x18000614a  pop     rdi
0x18000614b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
